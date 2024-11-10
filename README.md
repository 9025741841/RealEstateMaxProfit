# RealEstateMaxProfit

def max_profit(prices):
    # If there are fewer than 2 days, no transaction can be made
    if len(prices) < 2:
        return 0

    # Initialize min_price to the first day's price and max_profit to 0
    min_price = prices[0]
    max_profit = 0

    # Loop through prices starting from the second day
    for price in prices[1:]:
        # Calculate potential profit if we sell on the current day
        potential_profit = price - min_price

        # Update max_profit if the potential profit is higher
        max_profit = max(max_profit, potential_profit)

        # Update min_price if the current price is lower
        min_price = min(min_price, price)

    return max_profit
