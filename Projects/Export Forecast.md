```r
# Load data
Sales <- read.csv("Sales.csv")
Units <- Sales[, c("Date", "Units.Sold")]
Units$Units.Sold <- as.numeric(gsub("[\\$,]", "", Units$Units.Sold))

# Convert Date to Date format
Units$Date <- as.Date(Units$Date, format="%m/%d/%Y")

# Log-transform Total Sale Price
Units$Log.Units.Sold <- log(Units$Units.Sold)

# Feature Engineering
Units <- Units %>% mutate(
  Year = year(Date),
  Month = month(Date),
  Day = day(Date),
  DayOfWeek = wday(Date, label=FALSE)
)

# Train-Test Split
set.seed(123)
train_index <- sample(seq_len(nrow(Units)), size = 0.8 * nrow(Units))
train_data <- Units[train_index, ]
test_data <- Units[-train_index, ]

# Split data into training (historical) and future (to predict)
train_data <- Units[Units$Date < as.Date("2023-02-01"), ]

future_dates <- seq(from = max(Units$Date) - 30, by = "day", length.out = 30) 

future_data <- data.frame(
  Date = future_dates,
  Year = year(future_dates),
  Month = month(future_dates),
  Day = day(future_dates),
  DayOfWeek = wday(future_dates, label=FALSE)
)

# Train Random Forest model
rf_model <- randomForest(
  Log.Units.Sold ~ Year + Month + Day + DayOfWeek,
  data = train_data,
  ntree = 500,
  mtry = 4,
  nodesize = 5,
  importance = TRUE
)

future_data$Predicted_Log_Units <- predict(rf_model, future_data)
future_data$Predicted_Units <- exp(future_data$Predicted_Log_Units)
future_data <- future_data[!duplicated(future_data$Predicted_Units),]

# Determine the last available date
last_date <- max(Units$Date)
last_month_data <- Units %>%
  filter(Date >= last_date - 60)

last_month_predictions <- future_data %>%
  filter(Date <= last_date + 30)

ggplot() +
  geom_line(data = last_month_data, aes(x = Date, y = exp(Log.Units.Sold), color = "red"), size = .7) +
  geom_line(data = last_month_predictions, aes(x = Date, y = Predicted_Units, color = "blue"), size = .7) +
  labs(title = "Next Month Units Forecast", x = "Date", y = "Units") +
  theme_minimal()
future_data
```
