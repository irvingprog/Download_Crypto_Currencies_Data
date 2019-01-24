# Download_Crypto_Currencies_Data

[![PyPI](https://img.shields.io/pypi/v/dccd.svg)](https://pypi.org/project/dccd/)
[![Status](https://img.shields.io/pypi/status/dccd.svg?colorB=blue)](https://pypi.org/project/dccd/)
[![Build Status](https://travis-ci.org/ArthurBernard/Download_Crypto_Currencies_Data.svg?branch=master)](https://travis-ci.org/ArthurBernard/Download_Crypto_Currencies_Data)
[![license](https://img.shields.io/github/license/ArthurBernard/Download_Crypto_Currencies_Data.svg)](https://github.com/ArthurBernard/Download_Crypto_Currencies_Data/blob/master/LICENSE.txt)
[![Downloads](https://pepy.tech/badge/dccd)](https://pepy.tech/project/dccd)

#### This is a beta version of a python package to *download* and *upload* data about *crypto-currencies* (bitcoin, ether, litecoin, etc.) from different API exchanges (allow only Binance, GDAX, Kraken and Poloniex for the moment).

## Presentation:

The **'dccd'** package contains a main class and four classes to download and update data for each exchange, and a module **'time_tools'** to manage specific time functions needed for each API.

The four classes to download data are **FromBinance**, **FromGDax**, **FromKraken** and **FromPoloniex**. All have the same methods and almost the same parameters:    
- **\_\_init\_\_(path, crypto, span, fiat(optional), form(optional))** initialisation with **path** is the path where save the data (string), **crypto** is a crypto currency (string) and **span** is the interval time between each observation in seconds (integer) or can be a string as 'hourly', 'daily', etc. (see details on the doc string). The optional parameters are **fiat** the second currency (default is 'USD' and 'USDT' for poloniex and binance) and **form** the format to save the data (default is 'xlsx').    

- **import\_data(start, end)** download data with **start** and **end** the timestamp (integer) or the date and time (string as 'yyyy-mm-dd hh:mm:ss'), respectively of the first observation and the last observation (default are special parameters **start='last'** allow the last data saved and **end='now'** allow the last observation available). Exclusion: Kraken don't allow the **end** parameter and provide only the thousand last observations.    

- **save(form(optional), by(optional))** save the data with **form** the format of the saved data (default is 'xlsx') and **by** is the "size" of each saved file (default is 'Y' as an entire year). Exclusion: This optional parameters are in progress, let the default parameter for the moment, other are not allow.    

- **get_data()** returns the data frame without any parameter.    

Method chaining is available.

## Supported exchanges:

- **Binance.**

- **GDAX.**

- **Kraken.**

- **Poloniex.**

## Installation:

Install the library from pip:

> pip install dccd

***
*Package not achieved, always in progress. This is my first one package, all advice is welcome.*
