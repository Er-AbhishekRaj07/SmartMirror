# Smart Mirror 
A "Smart Mirror" is a two-way mirror with a display behind it that is typically used to display useful information like the time and date, the weather, your calendar, and all sorts of other things! People use them for all kinds of purposes. You'll see them placed in the bathroom, in the kitchen, as a vanity, all over the place!

## Manual Installation
### 1. Download and install the latest Node.js version:

```
curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```
```
sudo apt install -y nodejs
```
### 2. Clone the repository and check out the master branch:

```
git clone https://github.com/MichMich/MagicMirror
```
### 3. Enter the repository:
```
cd MagicMirror/
```
### 4. Install the application:
```
npm install --only=prod --omit=dev
```
### 5. Make a copy of the config sample file:
```
cp config/config.js.sample config/config.js
```

### 6. Start the application:
```
npm run start
```
#### For Server Only use:
```
npm run server
```

## Usage 

`npm start` does not work via SSH. But you can use `DISPLAY=:0` nohup `npm start` & instead. 
This starts the mirror on the remote display.

If you want to debug on your Raspberry Pi you can use npm run  `start:dev`  which will start MM with Dev Tools enabled.


To access the toolbar menu when in mirror mode, hit ALT key.

To toggle the (web) Developer Tools from mirror mode, use CTRL-SHIFT-I or ALT and select View


```
sudo apt-get install python-imaging-tk
```

## Client Only
This is when you already have a server running remotely and want your RPi to connect as a standalone client to this instance, to show the MM from the server. Then from your RPi, you run it with:
```
node clientonly --address 192.168.1.5 --port 8080
```



## Running
To run the application run the following command in this folder

```
cd MagicMirror/
```
```
npm run start
```
## Server Only 
```
let config = {
	address: "0.0.0.0",	// default is "localhost"
	port: 8080,		// default
	ipWhitelist: ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:172.17.0.1"], // default -- need to add your IP here
	...
};
```
## Demo and Build Instructions 
(click image for Video on Youtube)
[![Link to See the Smart-Mirror](https://youtu.be/drt5-oTzF0M)
