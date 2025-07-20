# # Predefined stock prices
stock_prices = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOGL": 140,
    "AMZN": 130,
}

total_investment = 0  # Total value of the stocks

print("📊 Welcome to the Stock Portfolio Tracker!")
print("Enter the stock symbol and quantity you own.")

# Loop to accept stock entries from user
while True:
    stock_name = input("Enter stock symbol (or type 'done' to finish): ").upper()

    if stock_name == "DONE":
        break

    if stock_name in stock_prices:
        quantity = int(input(f"How many shares of {stock_name}? "))
        investment = stock_prices[stock_name] * quantity
        total_investment += investment
        print(f"Added: {quantity} x {stock_name} at ${stock_prices[stock_name]} = ${investment}")
    else:
        print("⚠️ That stock is not in our list.")

# Show final total investment
print("\n💰 Your total investment value is: $", total_investment)

# Optional: Save result to file
with open("portfolio_summary.txt", "w") as file:
    file.write(f"Total Investment Value: ${total_investment}")
