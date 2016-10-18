Distributed banking on git

## Features
 - Distributed
 - Decentralized
 - Codeless architecture

## Installation
Fork this repo
![](https://cloud.githubusercontent.com/assets/677646/19483933/72189c96-9588-11e6-997e-07ee585bf47f.png)

## Creating account
1. Add empty file (representing the account) to account folder
2. Add and commit changes
```bash
touch account/alex
git add .
git commit -m'added account for alex'
```
## Making transaction
1. Subtract desired amount of git coins from the sender account file
2. Add the same amount of git coins to the recipient account file
3. Add and commit changes
```bash
# $ cat account/alex
# 1024
# $ cat account/bruno
# 16
echo 1000 > account/alex
echo 40 > account/bruno
git add .
git commit -m'transferred 24 coins from alex to bruno'
```
## Syncing with peers
Use `git pull/push`, or send a pull request
## Advanced
### Account file format
Each file represents one account and contains amount of git coins on this account
### Validation
Sum of all git coins from all accounts is 9007199254740991
```bash
echo $(($(cat account/* | tr '\n' '+') - 9007199254740991))
# should be 0
```
