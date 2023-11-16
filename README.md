# Trade Execution Via TradingView Through PENDAX

This project is a Node.js-based application designed to execute trades on the [Bybit](https://www.bybit.com/en-US/invite?ref=LPMYYV) Exchange in response to signals received from TradingView webhooks. It leverages the [PENDAX SDK](https://github.com/CompendiumFi/PENDAX-SDK) for interacting with the [Bybit](https://www.bybit.com/en-US/invite?ref=LPMYYV) API.

## Features

- Receives and processes TradingView webhook signals.
- Executes trades on the [Bybit](https://www.bybit.com/en-US/invite?ref=LPMYYV) Exchange based on the received signals.
- Supports various trade operations including opening long/short positions and closing positions.

## Getting Started

These instructions will guide you on setting up the project on your local machine for development and testing purposes.

### Prerequisites

- Node.js
- npm (Node.js package manager)
- Access to [Bybit](https://www.bybit.com/en-US/invite?ref=LPMYYV) Exchange API credentials

### Installation

1. Clone the repository:

     `git clone https://github.com/CompendiumFi/PENDAX-Trade-Execution.git`

2. Navigate To Project Directory

    `cd PENDAX-Trade-Execution`

3. Install Required Dependencies

    `npm install`

4. Create a `.env` file at the root of the project and add your Bybit API credentials:

`API_KEY=your_bybit_api_key`
`API_SECRET=your_bybit_api_secret`

## Usage
To use this bot, set up webhooks in TradingView to send signals to the endpoint where your server is running.

#### Webhook Signal Format

Signals should be sent as a POST request with a JSON payload containing the following fields:

-   `symbol`: The market symbol for the trade, e.g., "BTC-USDT".
-   `side`: The side of the order, either "buy" or "sell".
-   `orderType`: The type of order, e.g., "limit", "market".
-   `qty`: The quantity to trade.
-   `equity`: The percentage of the total balance to be used in the trade (only applicable for `tradeByEquity` function).
-   `type`: The type of trade operation, e.g., "long", "short", "close long", "close short" (only for `tradeByEquity`).

Example JSON Payload:

    {
        "category": "linear",
        "symbol": "BTCUSDT",
        "side": "buy",
        "orderType": "market",
        "qty": "0.01"
    }

## Running The Server
Start the program on your server by running the following:

    node index.js

## Adding Exchanges From PENDAX
Exchanges can be added to the program as new controllers in the codebase. Please follow the PENDAX standard of operations for including functions to keep your life simple.

Our team will update this repository and documentation with additional exchanges in the near future. Please feel free to make pull requests with new exchanges from the [PENDAX SDK](https://github.com/CompendiumFi/PENDAX-SDK) added!

## Contributing
Contributions to the project are welcome. Please ensure to follow the standard procedures for contributing to this repository.

## Disclaimer
This bot is provided for educational purposes only. Any use of this bot for real trading is at your own risk. The authors are not responsible for any financial losses that may occur.
