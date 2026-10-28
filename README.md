# Vrays — Multi-Timeframe Imbalance Distal Edges

A TradingView indicator (Pine Script v6) that marks the **far edge of a price imbalance** on up to 25 timeframes at once, from 10 seconds to monthly, and removes each level the moment price trades back to it.

## What it does

When price displaces hard away from a candle, the extreme of the candle it left behind (candle 1's high on a bullish move, its low on a bearish one) becomes the **distal edge** of the imbalance being created. Vrays marks that level as soon as the displacement happens, without waiting for the three-candle Fair Value Gap to finish forming.

- **Arms on displacement.** A level appears the moment the forming higher-timeframe candle trades beyond the previous candle's extreme.
- **Dies on contact.** A bullish level only exists while price is above it, and a bearish level only while price is below it. The first trade back into it sweeps it off the chart.
- **Same levels on every chart.** Arming and sweeping run on traded highs and lows, not closes, so a 30m level is identical whether you're on a 1m or a 15m chart.
- **Non-repainting.** Higher-timeframe data comes only from the last closed candle.
- **25 timeframes.** 10s, 15s, 30s, 1m–6m, 10m, 12m, 15m, 20m, 30m, 45m, 1h, 2h, 3h, 4h, 6h, 8h, 12h, 1D, 1W and 1M. Each has its own on/off switch, bull and bear colour, and line style.
- **Staircase labels.** Levels fan out to the right by timeframe so they never stack on top of each other.
- **Price shading.** An optional band between price and each level shows how far price has to travel to reach it. Each timeframe can be shaded independently.
- **Memory-efficient.** Rows that are switched off or hidden don't request their timeframe's data.

## Key settings

| Setting | What it controls |
|---|---|
| Contact tolerance | How close (in points) price must come to a level to sweep it |
| Sweep on chart-TF touch | Off: a still-forming HTF level only dies on a chart close back inside. On: the first chart wick back into it kills it |
| Hide timeframes below chart TF | Skips timeframes lower than the one you're viewing |
| Offset right / Staircase | Where the lines and labels sit to the right of the live candle |
| Line placement | Right of price, or running back from the source candle |
| Show shade | Enables the price-to-level band and its per-timeframe switches |

## Alerts

- **Bullish imbalance filled.** Price retraced down into a higher-timeframe bullish distal edge.
- **Bearish imbalance filled.** Price retraced up into a higher-timeframe bearish distal edge.

## Installation

1. Open TradingView and go to **Pine Editor**.
2. Paste the contents of `Vrays.pine`.
3. Click **Add to chart**.

## Companion indicator

Vrays was split out of a larger script, Vexcision. Its companion, [**VXfvg**](https://github.com/geedenscore/VXfvg), draws the full Fair Value Gap boxes. With **Fill on wick** on in VXfvg, a gap box and its matching ray from Vrays are removed on the same tick.

## License

[Creative Commons Attribution-NonCommercial-ShareAlike 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Free to use and adapt for non-commercial purposes with attribution.

## Disclaimer

This indicator is for educational and informational purposes only and is not financial advice. Trading futures and other leveraged products carries substantial risk of loss.
