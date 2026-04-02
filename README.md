# 📈 Crypto-Exchanges-Tickers

[![Updated](https://img.shields.io/github/last-commit/CryptowChris/Crypto-Exchanges-Tickers)](https://github.com/CryptowChris/Crypto-Exchanges-Tickers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

This repository centralizes and updates daily the ticker lists for the most popular cryptocurrency exchanges. These lists are designed to be easily imported into [TradingView](https://www.tradingview.com/).

**✅ All tickers are updated daily.**

---

## 📑 Table of Contents
- [Description](#-description)
- [Supported Exchanges](#-supported-exchanges)
- [Prerequisites](#-prerequisites)
- [Installation & Usage](#-installation--usage)
- [Developer Documentation](#-developer-documentation)
- [Contributing](#-contributing)
- [License](#-license)
- [Support the Project](#-support-the-project)

---

## 📖 Description

The **Crypto-Exchanges-Tickers** project provides CSV files containing trading pairs (tickers) for the Spot and Futures markets of major crypto exchanges. These lists allow traders to bulk import pairs into their TradingView Watchlist quickly, instead of adding them manually one by one.

---

## 💱 Supported Exchanges

The CSV files for each platform are located in the `tickers/` folder of the project. You can access them directly from the repository or download them using the links below.

| Exchange | Spot Market | Futures Market |
|----------|-------------|----------------|
| **Binance** | [📥 Spot](./tickers/Binance.csv) | [📥 Futures](./tickers/Binance.futures.csv) |
| **BingX** | [📥 Spot](./tickers/BingX.csv) | [📥 Futures](./tickers/BingX.futures.csv) |
| **Bitfinex** | [📥 Spot](./tickers/Bitfinex.csv) | ⏳ *Coming soon* |
| **Bitget** | [📥 Spot](./tickers/Bitget.csv) | [📥 Futures](./tickers/Bitget.futures.csv) |
| **Bitstamp** | [📥 Spot](./tickers/Bitstamp.csv) | ⏳ *Coming soon* |
| **BloFin** | [📥 Spot](./tickers/BloFin.csv) | [📥 Futures](./tickers/BloFin.futures.csv) |
| **Bybit** | [📥 Spot](./tickers/Bybit.csv) | [📥 Futures](./tickers/Bybit.futures.csv) |
| **Coinbase** | [📥 Spot](./tickers/Coinbase.csv) | [📥 Futures](./tickers/Coinbase.futures.csv) |
| **CoinEx** | [📥 Spot](./tickers/CoinEx.csv) | [📥 Futures](./tickers/CoinEx.futures.csv) |
| **Crypto.com** | [📥 Spot](./tickers/Crypto.com.csv) | [📥 Futures](./tickers/CryptoCom.futures.csv) |
| **Gate.io** | [📥 Spot](./tickers/Gateio.csv) | [📥 Futures](./tickers/Gateio.futures.csv) |
| **Gemini** | [📥 Spot](./tickers/Gemini.csv) | [📥 Futures](./tickers/Gemini.futures.csv) |
| **Huobi / HTX** | [📥 Spot](./tickers/Huobi.csv) | [📥 Futures](./tickers/Huobi.futures.csv) |
| **Kraken** | [📥 Spot](./tickers/Kraken.csv) | [📥 Futures](./tickers/Kraken.futures.csv) |
| **KuCoin** | [📥 Spot](./tickers/Kucoin.csv) | [📥 Futures](./tickers/Kucoin.futures.csv) |
| **LBank** | [📥 Spot](./tickers/LBank.csv) | ⏳ *Coming soon* |
| **MEXC** | [📥 Spot](./tickers/Mexc.csv) | [📥 Futures](./tickers/Mexc.futures.csv) |
| **OKX** | [📥 Spot](./tickers/OKX.csv) | [📥 Futures](./tickers/OKX.futures.csv) |
| **Phemex** | [📥 Spot](./tickers/Phemex.csv) | [📥 Futures](./tickers/Phemex.futures.csv) |
| **Poloniex** | [📥 Spot](./tickers/Poloniex.csv) | ⏳ *Coming soon* |
| **Weex** | [📥 Spot](./tickers/Weex.csv) | [📥 Futures](./tickers/Weex.futures.csv) |
| **WhiteBIT** | [📥 Spot](./tickers/Whitebit.csv) | ⏳ *Coming soon* |

*(Note: Dead links from older versions have been fixed and now redirect properly using relative paths)*

---

## 🛠 Prerequisites

- A **TradingView** account (free or premium).
- Optional: A text editor or spreadsheet software (Excel, Google Sheets) if you wish to filter pairs before importing.

---

## 🚀 Installation & Usage

To use these lists in TradingView, you need to import the corresponding `.csv` file into your Watchlist.

### Steps to import tickers:

1. **Download** the `.csv` file for the exchange you are interested in using the links in the table above.
2. Log in to your account on [TradingView](https://www.tradingview.com/).
3. Open a chart (Supercharts).
4. In the right toolbar, click on the **Watchlist** icon.
5. Click on the name of your current watchlist to open the dropdown menu.
6. Select **Import list...**.
7. Choose the previously downloaded `.csv` file.

The list will be automatically loaded and ready to use! 🎉

---

## 👨‍💻 Developer Documentation

Although this project is primarily a data collection, here is how the data is structured if you wish to use it in your own scripts, bots, or applications.

### Data Format
Each CSV file contains a list of tickers formatted to be compatible with TradingView, following the `EXCHANGE:PAIR` pattern.
The file has no header, and each line corresponds to a single ticker.

**Extraction example (`tickers/Binance.csv`):**
```csv
BINANCE:1000PEPEUSDT
BINANCE:1INCHBTC
BINANCE:1INCHUSDT
```

**Python script example to parse the data:**
```python
import csv

def read_tickers(filepath):
    tickers = []
    with open(filepath, mode='r', encoding='utf-8') as file:
        reader = csv.reader(file)
        for row in reader:
            if row:
                tickers.append(row[0])
    return tickers

# Usage
binance_tickers = read_tickers('tickers/Binance.csv')
print(f"{len(binance_tickers)} tickers found on Binance.")
print(binance_tickers[:5])
```

---

## 🤝 Contributing

Contributions are welcome! If you notice a missing exchange, outdated data, or want to make improvements:

1. **Fork** the repository.
2. Create a new branch for your feature (`git checkout -b feature/NewExchange`).
3. Place your `.csv` files in the `tickers/` folder with the format `Exchange.csv` (for Spot) and `Exchange.futures.csv` (for Futures).
4. **Commit** your changes (`git commit -m 'Add support for NewExchange'`).
5. **Push** to the branch (`git push origin feature/NewExchange`).
6. Open a **Pull Request**.

---

## 📄 License

This project is licensed under the **MIT** License. See the [LICENSE](./LICENSE) file for details.

---

## ☕ Support the Project

If you find this project helpful and would like to support its development, you can buy me a coffee in BTC:

**BTC Address (BSC / BEP20):** `0x5306ac8038e62a2d089dbfe6e0ff71b3eadf2003`

<img src="https://github.com/CryptowChris/Crypto-Exchanges-Tickers/blob/main/BtcQrCode.png" width="150" alt="BTC QR Code" />
