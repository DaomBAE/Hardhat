# Hardhat 배포 및 Verify하기 

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a script that deploys that contract.

Try running some of the following tasks:

```
npm install --save -dev hardhat
npm install --save-dev @nomicfoundation/hardhat-toolbox
npx hardhat

npx hardhat compile

// 터미널 2개 띄우기, 지금까지 한 것은 왼쪽
// 오른쪽에서는 
npx hardhat node

------------------local에서 배포하기---------------------------
// 왼쪽
npx hardhat run --network localhost .\scripts\deploy.js
// 왼쪽에서는 전체 정보 혹은 컨트랙트의 주소 확인
// 오른쪽에서 거래 결과 확인

------------------배포한 contract verify------------------------
npx hardhat compile
npx hardhat run --network goerli ./scripts/deploy_abc.js

npx hardhat verify --network goerli CONTRACT 주소

------------------배포한 contract verify(constructor 있는 contract//ERC20)------------------------
npx hardhat compile
npx hardhat run --network goerli ./scripts/deploy_erc_20.js

npx hardhat verify --network goerli CONTRACT 주소 123456789 /*얘는 constructor의 input 값*/

---------------------port 죽이기------------------------
netstat -ano | findstr :8545
stop-process 13744

Get-Process -Id (Get-NetTCPConnection -LocalPort "8545").OwningProcess | Stop-Process
```
