Given an array of integers prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock. Return the maximum profit.

```cpp
    int maxProfit(vector<int>& prices) {
        int buy = INT_MAX;
        int sell = 0;
        for(int i =0; i<prices.size(); i++){
            buy = min(buy,prices[i]);
            sell = max(sell, prices[i]-buy);
        }
    return sell;
    }
```

## Explanation

1. Initialize variables buy and sell. Buy should be set equal to the cpp INT_MAX constant, because initializing to 0 or another small number would be a logic error. (explained later)
2. Iterate through the array of prices. Set buy equal to the minimum function of the current buy price and the currently iterated buy price.  Starting buy with INT_MAX allows the buy variable to accept the first value no matter what.
3. Set the sell variable equal to the largest sale price by using the max function and inputting the previous selling price and the currently iterated price minus the buy.
4. Return the final sale price.