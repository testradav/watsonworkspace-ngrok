# watsonworkspace-ngrok

An [ngrok](https://ngrok.com/) utility to aid local development of Watson Workspace chatbots.

## Usage

Add the utility to your chatbot projects.

`npm install watsonworkspace-ngrok --save-dev`

Update run scripts in your `package.json` to launch both your chatbot and watsonworkspace-ngrok. 
For example, the following uses [concurrently](https://github.com/kimmobrunfeldt/concurrently) to launch both.

```
"scripts": {
    "start": "node index.js",
    "test": "jasmine",
    "dev": "concurrently \"node ./node_modules/watsonworkspace-ngrok/index.js\" \"node ./index.js\""
  },
```

The ngrok tunnel will launch with details needed to update your Watson Workspace chatbot's webhook.
This assumes that you are also using the [watsonworkspace-bot](https://github.com/van-ibm/watsonworkspace-bot) framework.

```
[1] [nodemon] 1.14.12
[1] [nodemon] to restart at any time, enter `rs`
[1] [nodemon] watching: *.*
[1] [nodemon] starting `node --debug ./index.js`
[1] Debugger listening on [::]:5858
[0]
[0]     1. Open https://developer.watsonwork.ibm.com/apps/20d70d3c-5ed5-4208-b224-fc73ba0582b1/info
[0]     2. Add the webhook https://ddf483da.ngrok.io/20d70d3c-5ed5-4208-b224-fc73ba0582b1/webhook to you App
```
