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
- [dotenv](https://github.com/motdotla/dotenv) to ensure our configuration variables are where they belong
- [TypeORM](https://typeorm.io/) for database connectios
- [restify](http://restify.com/) for the RESTful API
- [socket.io](https://socket.io/) for socket support
- [mocha](https://mochajs.org/) for testing
- [istanbul](https://istanbul.js.org/) for test coverage results
