
When first getting my development setup after reading the readme quick overview I did not setup the proper linking to the react-sdk & js-sdk for the elements to show all the ui components outside the node modules as I was not used to setting up that instance in previous projects.

When first setting up the environment for the Element Client & Matrix Server I ran into the issue of not being able to see all the Ui components within the src of the Element Client. 

To resolve the issue I followed the guide of linking the react-sdk and js-sdk to the element client and was able to easily view the ui components for the developer environment. Setting up my docker instance of Syapse was easy enough as well after following the guide that element provides and linking that to my client through the config.js 

In conclusion here are the steps for proper setup 
Setup 1 
Synapse Docker setup 
docker run -it --rm \ -v "$PWD:/data" \ -e SYNAPSE_SERVER_NAME=my.matrix.host \ -e SYNAPSE_REPORT_STATS=no \ matrixdotorg/synapse:latest generate

Setup 2 - Clone Each Project needed into a folder 


git clone https://github.com/matrix-org/matrix-js-sdk.git 
git clone https://github.com/matrix-org/matrix-react-sdk.git 
git clone https://github.com/element-hq/element-web.git

Setup 3 -  Linking each project


cd matrix-js-sdk
yarn link
yarn install

cd ../matrix-react-sdk
yarn link
yarn link matrix-js-sdk
yarn install

cd ../element-web
yarn link matrix-js-sdk
yarn link matrix-react-sdk
yarn install

Setup 4 -  Link localhost Synapse Server to the Element Client


"default_server_config": { "m.homeserver": { "base_url": "http://localhost:8008", "server_name": "localhost" }, "m.identity_server": { "base_url": "" } }

Setup 5 - Yarn Start 


Yarn Start on the element client
