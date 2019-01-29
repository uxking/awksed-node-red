# awksed-node-red

Repo for Docker image of node-red with AWS CLI tools installed for troubleshooting.  

## Running the container

`docker run -id --name=awksed-node-red --hostname=awksed-node-red -p 1880:1880 -v ~/node-red:/root/node-red awksed/node-red`  

You should then be able to browse to the image at http://localhost:1880  


## Logon to the container
If you need to login to the container for troubelshooting:  
`docker exec -it awksed-node-red /bin/bash`  

If you choose to use this image you will need to update the "mqtt node" with the appropriate endpoint URL, root-CA, thingCertificate, thingPrivateKey files.  

Files are mounted from the local ~/node-red directory to /root/node-red in the container. This is a good place to upload certificates, etc, as /root/node-red wil persist on your local machine's "node-red" directory since we ran the docker container with the `-v` flag.  

## Follow the documentation to build your first flows
https://nodered.org/docs/getting-started/  
