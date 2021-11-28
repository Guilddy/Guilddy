# General

## Base Technology

The bot is built upon [Node.JS](https://nodejs.org/), a platform-agnostic runtime that is designed to execute (server-side) JavaScript and takes a modular approach on source code management.

For easy deployment, instance management, cloud execution and security measures, this project includes files for containerization:

- [Docker](https://docs.docker.com/) (via [Dockerfile](https://docs.docker.com/engine/reference/builder/))
- [Docker-Compose](https://docs.docker.com/compose/) (via [docker-compose.yml](https://docs.docker.com/compose/compose-file/))

## Language

The core code, add-on modules and tests are written in

> [TypeScript](https://www.typescriptlang.org/) (there are a lot of tutorials on this language out there but we just wanted to link the official [Guide to TypeScript in 5 Minutes](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html))

while the data transferred comes in the form of

> [JSON](https://www.json.org/)

and

> [MarkDown](https://help.github.com/en/github/writing-on-github)

is used for documentation purposes.

## Libraries

- [Discord.js](https://github.com/discordjs/discord.js) as the main framework
  - [zlib-sync](https://github.com/abalabahaha/zlib-sync) as an optional dependency for WebSocket data compression and inflation
  - [erlpack](https://github.com/discord/erlpack) as an optional dependency for significantly faster WebSocket data (de)serialisation
  - [bufferutil](https://github.com/websockets/bufferutil) as an optional dependency for a much faster WebSocket connection
  - [utf-8-validate](https://www.npmjs.com/package/utf-8-validate) as an optional dependency in combination with bufferutil for much faster WebSocket processing
- [dotenv](https://github.com/motdotla/dotenv) to ensure our configuration variables are where they belong
- [TypeORM](https://typeorm.io/) for database connectios
- [restify](http://restify.com/) for the RESTful API
- [socket.io](https://socket.io/) to provide socket support for the API
- [axios](https://axios-http.com/) for asynchronous HTTP requests
- [mocha](https://mochajs.org/) for testing
- [istanbul](https://istanbul.js.org/) for test coverage results
