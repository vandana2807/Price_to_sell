# Price_to_sell
# problem statement
A real estate agent is advising a seller on the price to ask for a home. To do this, the agent will look at homes that have sold in the area and base the valuation on this data. The only factors that will be considered are square footage and sale price.

The agent starts by removing any outliers from the list of comparable homes. 
To determine the outliers:  
  1. Select the home to test.
  2. Create a list of prices of other homes of the same size. It will be called compList in the examples. 
  3. If there are no other homes of the same size, the house being tested is not an outlier
  4. Otherwise: 
              * Calculate the mean price, Pm and the standard deviation, o, for the homes compList. o
              * lf price[i] - Pm /> 3* o, the house is an outlier.
              
The valuation is then calculated against the resulting list using the following rules: 
1. If there are no houses in the list, use 1000 per square foot as the price.
2. If there is only 1 house in the list, its square foot price is used.
3. If there are 1 or more houses in the list with the exact square footage of the house to price, use the mean of those prices.
4. If the required square footage is between the square footage of two houses in the list, interpolate the square foot price using the means of the closest higher and lower priced homes.
5. If the required square footage is outside of the range of houses listed, extrapolate the price based on the means of the two square footage values that are closest to the home to value.

In all cases, if the final price is less than 10^3 or greater than 10^6, the price will be 10^3 and 10^6, respectively. For any square footage, the square foot price is the mean of the prices at that square footage. Return an integer that represents the valuation of the seller's house. 


# solution

Function starts with finding duplicates of each element in area list if there are no duplicates then its not an outlier and is added to final list
if there are duplicates in area list then we take the mean of prices of those duplicates area in a cmplist, find the mean and standard deviation of it
if mod of difference between price and mean price is less than 3 times standard deviation add it to final list

Once we get the final list add the necessary rules to find the price
