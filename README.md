# v1-calculator-spreadsheet
Spreadsheet to calculate P/L, Time to Liquidation, Delta, Leverage, and Cost to open a long volatility position in GammaSwap

## Instructions
Only edit orange fields.

## Field Description
"Deposit (USDC Buffer)" refers to the "Deposit" column when you have a position open in app.gammaSwap.com. In this spreadsheet you enter how much you want to have as collateral buffer for your position. This field refers to the "Collateral Buffer Formula" from above.

"LTV" is the Loan To Value ratio of the liquidity debt to liquidity collateral of the position. A higher LTV, the closer to liquidation it will be, therefore the less "Time to Liquidation (Days)"

"Strike Price (Coll. Ratio)" refers to the collateral ratio (aka strike price) of the position you want to open. Different strike prices have different deltas as given by the formula above

"Time to Liquidation (Days)" refers to how many days till liquidation this position will have with the given LTV.

"Deposit Price" is the price you are paying per unit of "Deposit (USDC Buffer)". In the example above that means 1.0474 USDC per 1 USDC Deposit.

"Initial Deposit (USDC)" refers to how much you'll have to deposit in the "Initial Deposit" input box of the trade page of app.gammaswap.com. This means to get a 100 USDC Deposit you have to deposit 104.74 USDC.

"Delta" is the change in value of the position per every 1 USDC change in the price of the volatile asset (in this case WETH). In the example above that's 25 cents per every 1 USDC price change in WETH. The delta increases as the price of WETH increases.

"Leverage" is how much leverage you are getting opening this position. In the example, it's 4x. Therefore opening this position with a collateral buffer of 100 USDC (Deposit (USDC Buffer)), is the same as having an ETH position worth 399.68 USDC

"Size (USDC)" refers to the leveraged size of the position (100 x 4 ~ 399.68)

"ETH Price in USDC" in the "Post Trade" section refers to the price of ETH after opening a position with a 100 USDC buffer.

"Price Impact" in the "Post Trade" section refers to how much the price was moved by the opening of the position. In the example above opening the position moved the price of ETH 2 basis points. The inputs for the CFMM and GammaSwap are given below

"Current ETH Price (USDC)" refers to the current price of ETH in terms of USDC in the CFMM.

"Liquidity Invariant" is the geometric mean, i.e. sqrt(X*Y), of the reserve assets (ETH and USDC) inside the CFMM

"fee" is the trading fee charged by the CFMM

"ETH in CFMM" and "USDC in CFMM" is how much ETH and USDC is in the CFMM given the "Liquidity Invariant" and "Current ETH Price" inputs

"Borrow Rate" is the rate per year charged by GammaSwap to liquidity borrowers (buyers of volatility) including the trading fees in the CFMM. This is a variable number but can be averaged over periods of time to get a fair estimate of expected costs.

"Max LTV" refer sto the maximum LTV allowed by the GammaSwap pool before a liquidity loan goes is subject to liquidation (is expired).

"Origination Fee" refers to the origination fee charged by the GammaSwap pool at the current time. This is also variable, depending on the utilization rate of the pool but it is only paid once, up front when opening a liquidity loan.

"Px Change" column is how much the price of the underlying asset in the CFMM has changed

"Price (USD)" is the price of the volatile asset

"Pos Size (USD)" is the value of the position in USD terms

"P/L %" is the profit and loss in percentage terms of the position as the price of the volatile asset changes

"P/L (USD)" is the profit and loss of the position as the price changes
"Delta" is the delta of the position as the price changes. A GammaSwap position is a volatility trade, therefore the delta will increase as the price of the asset increases. The returns are therefore nonlinear and the P/L will grow faster than linear. 
"Leverage" is the leverage the position represents as the price changes. Leverage as in relative to how much was the collateral buffer (Deposit) used to open the position.
