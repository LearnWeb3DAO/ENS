# The Ethereum Name Service

## Background

When web initially started the only way you could explore information on the web was by entering in its IP address. Then the concept of DNS was introduced which helped us to link a domain name to an IP address.

So whenever you type `learnweb3.io`, DNS takes care of translating it to the respective IP which is what the computer finally understands.

## What is ENS?

- ENS stands for `The Ethereum Name Service` and it behaves very similar to how DNS behaves in the web2 space.
- As we all know that Ethereum has long addresses which are hard to remember or type
- ENS solves this issue by translating these wallet addresses, hashes etc into readable domains which are then saved on Ethereum blockchain
- The best part about ENS is unlike DNS servers which are centralized, ENS works with the help of a smart contract which is censorship resistant.
- So now when you are sending your wallet address to someone which looks like `0x1234huiahi....` you can actually send them `tom.eth` and the ENS would figure out that `tom.eth` is actually equal to your wallet address(`0x1234huiahi....`)

## Build

Its time to build something where we can use ENS.

## Requirements

Develop a website which can display the ENS for an address if it has one.

Lets gooo 🚀

## Setup

- First lets get an ENS name for your address, start by opening up [https://app.ens.domains/](https://app.ens.domains/)
- Make sure when you open the website, your MetaMask is connected to the `Rinkeby testnet` and it has some `Rinkeby Ether`

- Copy your discord username(including the 4 digit code) and remove the hashtag and click search
  ![](https://i.imgur.com/E7hD5Mb.png)

- Click on `Available`

  ![](https://i.imgur.com/1p0EBmv.png)

- Then click on `Request To Register`
  ![](https://i.imgur.com/zBG5JRo.png)

- When the progress bar enters the 3rd step, Click `Register`
  ![](https://i.imgur.com/a4nd6O4.png)

- Then after the progress bar finishes click on `Set As Primary ENS Name`

  ![](https://i.imgur.com/8cXXopd.png)

- From the dropdown then select the ENS name you just created

  ![](https://i.imgur.com/MgSrlyG.png)

- Click `Save`
  ![](https://i.imgur.com/8qOcAnp.png)

- Now you have an ENS registered to your address on Rinkeby

Awesome, You did it ❤️

## Website

- To develop the website we will use [React](https://reactjs.org/) and [Next Js](https://nextjs.org/). React is a javascript framework used to make websites and Next.js is a React framework that also allows writing backend APIs code along with the frontend, so you don't need two separate frontend and backend services.
- First, You will need to create a new `next` app. Your folder structure should look something like

  ```
  - ENS
      - my-app
  ```

- To create this `next-app`, in the terminal point to ENS folder and type

  ```bash
  npx create-next-app@latest
  ```

  and press `enter` for all the questions

- Now to run the app, execute these commands in the terminal

  ```
  cd my-app
  npm run dev
  ```

- Now go to `http://localhost:3000`, your app should be running 🤘

- Now lets install [Web3Modal library](https://github.com/Web3Modal/web3modal). Web3Modal is an easy to use library to help developers easily allow their users to connect to your dApps with all sorts of different wallets. By default Web3Modal Library supports injected providers like (Metamask, Dapper, Gnosis Safe, Frame, Web3 Browsers, etc) and WalletConnect, You can also easily configure the library to support Portis, Fortmatic, Squarelink, Torus, Authereum, D'CENT Wallet and Arkane.
  Open up a terminal pointing at`my-app` directory and execute this command

  ```bash
  npm install web3modal
  ```

- In the same terminal also install `ethers.js`

  ```bash
  npm install ethers
  ```

- In your my-app/public folder, download [this image](https://github.com/LearnWeb3DAO/Whitelist-Dapp/blob/main/my-app/public/learnweb3dev.svg) and rename it to `crypto-devs.svg`

- Now go to styles folder and replace all the contents of `Home.modules.css` file with the following code, this would add some styling to your dapp:

  ```css
  .main {
    min-height: 90vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    font-family: "Courier New", Courier, monospace;
  }

  .footer {
    display: flex;
    padding: 2rem 0;
    border-top: 1px solid #eaeaea;
    justify-content: center;
    align-items: center;
  }

  .image {
    width: 70%;
    height: 50%;
    margin-left: 20%;
  }

  .title {
    font-size: 2rem;
    margin: 2rem 0;
  }

  .description {
    line-height: 1;
    margin: 2rem 0;
    font-size: 1.2rem;
  }

  .button {
    border-radius: 4px;
    background-color: blue;
    border: none;
    color: #ffffff;
    font-size: 15px;
    padding: 20px;
    width: 200px;
    cursor: pointer;
    margin-bottom: 2%;
  }
  @media (max-width: 1000px) {
    .main {
      width: 100%;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  }
  ```
