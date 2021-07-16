Alchemy Notify 🔔 Tutorial
============

dApps on Ethereum have come a long way over the last several years, both in popularity and in complexity. Unfortunately, the user experience of most dApps is still lacking in comparison to web2 applications.

One key piece missing is real-time notifications of events. Users need to know immediately when their trades execute, when their transactions fail, when their auction bid has been accepted, or when a wallet of interest has aped into some new token. Without these notifications, trades can be missed, critical actions are forgotten, and ultimately users end up abandoning your dApp.

Unfortunately, building these real-time notifications into your dApp has traditionally been complicated, time-consuming, and error-prone. But now with Alchemy Notify, sending real-time push notifications to your users for critical events such as dropped transactions, mined transactions, wallet activity, and even gas price changes is straightforward, easy, and dependable.
***

Let’s look at an example of how, with just a few lines of code, your dApp can integrate the power of Alchemy Notify.

For this example, we’ll create a dApp that notifies users, in real-time, when activity happens on a specific Ethereum address. For our architecture, we’ll use Express for our server, WebSockets to communicate between the client and server, and Alchemy Notify to monitor an address and send a push notification when there is activity on that address.

Note that if you don't want to spend mainnet Ethereum to try out this tutorial, select a testnet like Rinkeby so that you can send transactions to and from your target address for testing.

***
For ease of user experience, we configured this particular tutorial to run on Heroku, but you are more than welcome to use other service providers!
***

### 🚀 Launching with Heroku ###

 1. Get the repo!

      * `git clone https://github.com/alchemyplatform/Alchemy-Notify-Tutorial`

For all Heroku dependent documentation, refer to:
https://devcenter.heroku.com/articles/getting-started-with-nodejs?singlepage=true 
for more detailed instructions.  The Heroku instructions included below are abridged.

 2. Install Heroku-CLI and verify/install dependencies.

      * Download Heroku-CLI based on your OS [https://devcenter.heroku.com/articles/heroku-cli]
      * After installation, open your terminal and run `heroku login`; follow the commands that follow to login to your Heroku account.  If you don't have a Heroku account, you can sign up for one!
      * Run `node --version`.  You may have any version of Node greater than 10.  If you don’t have it or have an older version, install a more recent version of Node.
      * Run `npm --version`.  `npm` is installed with Node, so check that it’s there. If you don’t have it, install a more recent version of Node:
      * Run `git --version`   Check to make sure you have git installed.  

 3. Initiate Heroku.

      * Run `heroku create` to create your heroku app. Take note of the info that pops up in the terminal, especially the URL that looks like  http://xxxxxxxxx.herokuapp.com/ We'll be using it!

 3. Swap in your Alchemy webhook id and auth token.

      > Change lines 37 and 43 in `server.js` to reflect your particular Alchemy webhook id and auth token!  Don't forget to sign into your Alchemy account to use the Notify webhook.  See https://docs.alchemy.com/alchemy/documentation/apis/enhanced-apis/notify-api for more specific documentation.  

      If you don’t already have an Alchemy account, [you’ll first need to create one](https://alchemy.com/?r=affiliate:ba2189be-b27d-4ce9-9d52-78ce131fdc2d). The free version will work fine for getting started.  First, create our example notification by clicking “Create Webhook” on Address Activity. 


      ![webhook_1](https://github.com/pileofscraps/alchemy_notify/blob/master/webhook_1.jpg)

      Taking note from the information that followed the `heroku create` command, copy and paste in the http://xxxxxxxxx.herokuapp.com/alchemyhook URL into the webhook entry box.  Select an app from the dropdown menu (Make sure the app selected is on the Ethereum network you want to test on; if you're testing on Rinkeby, select an app configured to it!) Click “Create Webhook” and we’re done!

      ![webhook_2](https://github.com/pileofscraps/alchemy_notify/blob/master/webhook_2.jpg)

 4. Deploy Heroku.

      * Run `git add .`
      * Run `git commit -m "added Alchemy keys"`
      * Run `git push heroku master` to push and deploy your heroku app.
     
🎉 Congratulations on your dApp deployment! Feel free to edit your app, change its behavior, or make the frontend more spiffy!
