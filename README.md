# Golden Retirement EA - Expert Advisor for MT4

## Overview
Golden Retirement EA is a high-performance Expert Advisor designed for MetaTrader 4, optimized for trading XAUUSD (Gold) on the M5 timeframe. The EA combines a classic trend-following strategy with advanced filters and robust risk management.

## Version History

### Version 1.6 (Latest) - Enhanced Consistency & Profitability
**Release Date:** November 2024

**Major Improvements:**
- ✅ Configurable ADX parameters for better trend detection
- ✅ Signal Strength Filter (0-100% scoring system)
- ✅ Enhanced spread validation before every trade
- ✅ Volatility-based automatic lot sizing
- ✅ Improved entry logic with multi-factor confirmation

[View detailed improvements](IMPROVEMENTS_V1.6.md)

### Version 1.5 - Performance, Margin and Retry Logic Update
- Enhanced margin validation
- Order retry logic with error handling
- Improved performance optimizations

## Key Features

### Trading Strategy
- **Trend Following**: Uses MA crossovers with ADX confirmation
- **Entry Modes**: 
  - Instant Execution: Immediate market orders
  - ATR Breakout: Pending orders based on volatility
- **Grid System**: Optional averaging down with configurable parameters

### Filters & Confirmations
- **Higher Timeframe Filter**: Trend alignment with larger timeframe
- **News Filter**: Automatic pause during high-impact news events
- **Time Filter**: Trading session management
- **Volatility Filter**: Operates in optimal volatility ranges
- **RSI Filter**: Optional momentum confirmation
- **Sideways Market Filter**: Avoids choppy markets
- **Signal Strength Filter** (v1.6): Multi-indicator confidence scoring

### Risk Management
- **Dynamic Position Sizing**: Based on account equity and risk
- **Volatility-Based Adjustment** (v1.6): Auto-adjusts lot size
- **Breakeven Management**: Automatic breakeven protection
- **Trailing Stop**: Dynamic stop loss following
- **Grid Stop Loss**: Basket-based stop loss for grid systems
- **Partial Close**: Take partial profits at milestones
- **Daily Limits**: Profit targets and loss limits
- **Equity Drawdown Stop**: Account protection mechanism

## Installation

1. Download `GR v1.6.mq4` file
2. Copy to: `MT4_Data_Folder/MQL4/Experts/`
3. Restart MetaTrader 4 or refresh Navigator
4. Drag EA onto XAUUSD M5 chart
5. Enable "Allow live trading" in EA properties
6. Configure parameters as needed

## Recommended Settings

### Conservative Profile
```
Strategy Profile: Medium or Long
ADXMinLevel = 30.0
MinSignalStrength = 70.0
MaxSpread = 30
Initial Lot = 0.01
Grid_Max_Trades = 20
UseGridStopLoss = true
GridStopLossValue = 3.0%
```

### Balanced Profile (Default)
```
Strategy Profile: Medium
ADXMinLevel = 25.0
MinSignalStrength = 60.0
MaxSpread = 40
Initial Lot = 0.01
Grid_Max_Trades = 40
UseGridStopLoss = true
GridStopLossValue = 5.0%
```

### Aggressive Profile
```
Strategy Profile: Short or Medium
ADXMinLevel = 20.0
MinSignalStrength = 55.0
MaxSpread = 40
Initial Lot = 0.02
Grid_Max_Trades = 50
UseGridStopLoss = true
GridStopLossValue = 7.0%
```

## Important Parameters

### Strategy Settings
- **InpStrategyProfile**: Choose between Short (25), Medium (50), Long (100)
- **InpEntryMode**: Instant_Execution or ATR_Breakout
- **ADXPeriod**: Period for ADX calculation (10-20, default: 14)
- **ADXMinLevel**: Minimum ADX for trend confirmation (20-35, default: 25)

### Signal Quality
- **UseSignalStrength**: Enable/disable signal strength filter
- **MinSignalStrength**: Minimum score (0-100%, default: 60%)
- **UseRSIFilter**: Enable RSI confirmation
- **UseSidewaysFilter**: Avoid sideways markets
- **InpVolatilityFilterMode**: Disabled / Range / High_Only

### Risk Management
- **Lots**: Fixed lot size (if MaximumRisk = 0)
- **MaximumRisk**: Risk percentage per trade (0-5%)
- **MaxSpread**: Maximum spread in points (30-50)
- **Grid_Max_Trades**: Maximum positions in grid (20-50)
- **UseGridStopLoss**: Enable basket stop loss
- **GridStopLossValue**: SL value (3-7% recommended)

### Time & Session
- **UseTimeFilter**: Enable trading hours filter
- **StartHour**: Trading start time (default: 1)
- **StopHour**: Trading stop time (default: 21)
- **TradeOnFriday**: Allow Friday trading

### Daily Limits
- **UseDailyLimits**: Enable daily targets/limits
- **DailyProfitTarget**: Close all at profit target
- **DailyDrawdownLimit**: Stop trading at loss limit (%)

## Backtesting Recommendations

1. **Timeframe**: M5 (5 minutes)
2. **Symbol**: XAUUSD (Gold vs USD)
3. **Modeling**: Every tick (most accurate)
4. **Spread**: Use variable spread if available
5. **Period**: Minimum 3 months, ideally 1+ year
6. **Initial Deposit**: $1,000 - $10,000
7. **Optimization**: Test ADXPeriod, ADXMinLevel, MinSignalStrength

## Performance Metrics to Monitor

- **Win Rate**: Target 55-65% with v1.6 improvements
- **Profit Factor**: Target > 1.5
- **Max Drawdown**: Keep under 15-20%
- **Recovery Factor**: Target > 3.0
- **Sharpe Ratio**: Target > 1.0
- **Average Trade Duration**: Varies by strategy profile

## Risk Warning

⚠️ **IMPORTANT**: 
- Trading involves significant risk of loss
- Past performance does not guarantee future results
- Only trade with capital you can afford to lose
- Always test on demo account first
- Use proper risk management (1-2% per trade maximum)
- Monitor your account regularly
- High leverage increases both profit and loss potential

## Support & Updates

- **Telegram**: @jackysondias90
- **MQL5 Profile**: [jackysondias90](https://www.mql5.com/en/users/jackysondias90)
- **Version**: 1.6
- **Last Updated**: November 2024

## License

Copyright 2024, Jackyson Dias
All rights reserved.

## Changelog

### v1.6 (November 2024)
- Added configurable ADX parameters
- Implemented signal strength filter (0-100% scoring)
- Enhanced spread validation before all entries
- Added volatility-based automatic lot sizing
- Improved entry logic with better confirmations
- Better documentation and user guidance

### v1.5
- Performance optimizations
- Enhanced margin validation
- Improved retry logic for order execution
- Better error handling

### v1.0-1.4
- Initial release and iterations
- Core strategy implementation
- Grid system development
- Filter system implementation
