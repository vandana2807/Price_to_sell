# Price_to_sell
A real estate agent is advising a seller on the price to ask for a home. To do this, the agent will look at homes that have sold in the area and base the valuation on this data. The only factors that will be considered are square footage and sale price.

The agent starts by removing any outliers from the list of comparable homes. 
To determine the outliers:  
  • Select the home to test. 
  • Create a list of prices of other homes of the same size. It will be called compList in the examples. 
  •  If there are no other homes of the same size, the house being tested is not an outlier
  • Otherwise: 
              • Calculate the mean price, Pm and the standard deviation, o, for the homes compList. o
              • lf price[i] - Pm /> 3* o, the house is an outlier.
              
The valuation is then calculated against the resulting list using the following rules: 
• If there are no houses in the list, use 1000 per square foot as the price.
• If there is only 1 house in the list, its square foot price is used.
• If there are 1 or more houses in the list with the exact square footage of the house to price, use the mean of those prices.
• If the required square footage is between the square footage of two houses in the list, interpolate the square foot price using the means of the closest higher and lower priced homes.
• If the required square footage is outside of the range of houses listed, extrapolate the price based on the means of the two square footage values that are closest to the home to value.

In all cases, if the final price is less than 103 or greater than 106, the price will be 103 and 106, respectively. For any square footage, the square foot price is the mean of the prices at that square footage. Return an integer that represents the valuation of the seller's house. 

Complete the 'valuation' function below. 
* The function is expected to return a LONG_INTEGER. 
* The function accepts following parameters: 
   1. LONG_INTEGER reqArea 
   2. LONG_INTEGER_ARRAY area 
   3. LONG_INTEGER_ARRAY price 
function valuation (reqArea, area, price)
