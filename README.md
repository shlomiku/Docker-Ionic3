Ionic App Base
=====================

This is the base template for Ionic starter apps.

## Using this project

You need docker and docker compose installed

run this command:

docker-compose -f dev.yml up -d

you can also run it using docker like this:

docker run -it -v \`pwd\`:/opt/project -v /opt/project/node_modules -p 8100:8100 <image_name>

where image name is the built image name ( you build it using docker-compose up ) and may be obtained using 
`"docker images | grep ionic"`

the image will contain all node packages required to run

put your code in the src/pages folder

support for google maps was added, and in order for that to work you must add you google api key. this key may be obtained through this link:

https://developers.google.com/maps/documentation/javascript/get-api-key

and should be copied to :

/src/app/app.module.ts like so:

```imports: [
    BrowserModule,
    IonicModule.forRoot(MyApp),
    AgmCoreModule.forRoot({
      apiKey: 'your key here'       <----------------------  key goes here
    })
  ],
```

you can now browse to your app under port 8100 (ip should be checked via docker)
