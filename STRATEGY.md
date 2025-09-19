## Bollinger Bands Backtest Implementation

This implementation provides a complete Bollinger Bands mean reversion trading strategy backtest.

### Strategy Logic

The strategy implements a classic mean reversion approach using Bollinger Bands:

1. **Buy Signal**: When the price touches the lower Bollinger Band (indicating oversold conditions)
2. **Sell Signal**: When the price touches the upper Bollinger Band (indicating overbought conditions)
3. **Risk Management**: Each position includes stop-loss and take-profit levels

### Parameters

The backtest expects the following parameters via the `FinData` object:

- `period`: Number of periods for the moving average (e.g., 20)
- `multiplier`: Standard deviation multiplier for the bands (e.g., 2.0)
- `sl`: Stop loss percentage (e.g., 0.02 for 2%)
- `tp`: Take profit percentage (e.g., 0.04 for 4%)

### Output

The backtest returns detailed results including:

- `trades`: Complete list of all executed trades
- `total_profit`: Total profit/loss from all trades
- `num_trades`: Total number of trades executed
- `winning_trades`: Number of profitable trades
- `losing_trades`: Number of losing trades
- `win_rate`: Percentage of winning trades

### Example Usage

The function is designed to be used as an Extism plugin. It expects candle data in the "symbol_data" field and trading parameters as call arguments.

### Strategy Behavior

- **Position Size**: Fixed at 1.0 unit per trade
- **Position Management**: Only one position open at a time
- **Entry Conditions**: Price must touch the band and then move away from it
- **Exit Conditions**: Either stop-loss, take-profit, or opposite signal

This implementation provides a solid foundation for backtesting Bollinger Bands strategies and can be extended with additional features like dynamic position sizing, trailing stops, or multiple timeframe analysis.