Files in this repo:

UserData.ipynb -- a notebook that ingests 21 separate csv files related to service users and hosts and handles data cleaning and wrangling. It generates a clean data file on free-tier users only.

EtherscanFetch.ipynb -- a notebook that ingests 3 csv files containing wallet IDs for all hosts paid and then calls on the Etherscan API to retrieve transaction data involving those wallets (which I've called 'tier one'). It then stores all other wallets involved in those transactions and calls the API again to retrieve data involving those wallets (which I've called 'tier two'). The goal was to see who the hosts have transacted with directly and who they've transacted with at one degree of separation.

OperatorData.ipynb -- a notebook that ingests 21 separate csv files related to service users and hosts and handles data cleaning and wrangling. Pulls in the transactional data collected by EtherscanFetch to create a full overview of node host data. Also identifies a number of wallets for which no transactions could be found on Etherscan and stores those for later use.

ReducedEtherscan.ipynb -- limits the Etherscan transaction data to just those wallets that have been paid by the company in the last six months (since the goal is to find current cheaters, making inactive wallets irrelevant). It also breaks out those transactions into 'from' and 'to' so that it's possible to see who each operator made payments to vs. who they received payments from.
