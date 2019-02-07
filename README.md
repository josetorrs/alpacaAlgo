# Theory
Every day the portfolio refreshes based on the EMA ranking among the universe (e.g. SP500 stocks), it ranks by daily (price - EMA) 
percentage as of trading time and keep positions in sync with lowest ranked stocks.

The idea is the low (price - EMA) vs price ration indicates there is a big dip in a short time. Since the universe is SP500 
which means there is some fundamental strengths, the belief is that the price should be recovered to some extent. Also with the assumption that liquidty wouldn't be an issue

## How to run

First set up you rAPI key in environment variables.

```
$ export APCA_API_KEY_ID=xxx
$ export APCA_API_SCRET_KEY=yyy
```

The only dependency is the alpace-trade-api module. You can set up the environment by pipenv. If python 3 and the dependency is ready,

```
$ python main.py
```

## Customization
universe.Universe is hard-coded. Easy customization is to change this to a more dynamic set of stocks with some filters like per-share price set to a minimum or maximum. The assumption is that at most a position can take is up 20% of the portfolio. If your account siz varies or risk tolerance then changing the values is needed.

## For the future
btes.py runs a simple simulation. Module needs more easy visualization or integrated setup.
