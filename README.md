# Manual Installation :- 

1. Download and install the latest Node.js version:
  
  -> curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
  -> sudo apt install -y nodejs

2. Clone the repository and check out the master branch: git clone
   URL:-   https://github.com/MichMich/MagicMirror

3. Enter the repository: cd MagicMirror/

4. Install the application: "npm install --only=prod --omit=dev"

5. Make a copy of the config sample file: "cp config/config.js.sample config/config.js'

6. Start the application: "npm run start"

   # For Server Only use: npm run server


# Usage

Note the following: 


$  npm start does not work via SSH. But you can use DISPLAY=:0  nohup npm start & instead.
       This starts the mirror on the remote display.

$ If you want to debug on your Raspberry Pi you can use npm run  "start:dev"  which will start MM with Dev Tools enabled.

$ To access the toolbar menu when in mirror mode, hit ALT key.

$ To toggle the (web) Developer Tools from mirror mode, use CTRL-SHIFT-I or ALT and select View

# Client Only

This is when you already have a server running remotely and want your RPi to connect as a standalone client to this instance, to show the MM from the server. Then from your RPi, you run it with: node clientonly --address 192.168.1.5 --port 8080. 
 (Specify the ip address and port number of the server)


 # Server Only 

 let config = {
	address: "0.0.0.0",	// default is "localhost"
	port: 8080,		// default
	ipWhitelist: ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:172.17.0.1"], // default -- need to add your IP here
	...
};
