# Screeps-Performance-Server

This is a Screeps server setup that includes milestones and the [Stats mod](https://github.com/The-International-Screeps-Bot/screepsmod-server-stats) built in. It was originally created by [TooAngel](https://github.com/TooAngel) and this version includes data export for the milestones results. The exported data includes:

1. Milestones reached
2. Room status (ControllerId, creep count, level, progress, structure count)
3. Tick count
4. Start/end time

## Requirements

- Node.js 16.x
- Docker-Compose

## Installation

1. Clone this repo
2. Run `npm install` to install dependencies

## Setup

- Update all `.example` files to your needs. This is not required if you use the default setup.

### Custom bot

1. Create a new folder in the `bots` directory
2. Add your bot's JS files to the new folder (the entry file must be named `main.js`)
3. Update the `config.yml` file's `bots.bot` string to the path of your bot

### Run commands

- `--maxTicks`: limit the number of ticks the server will run
- `--maxBots`: limit the number of bots that can be spawned
- `--serverPort`: change the port the server will run on
- `--cliPort`: change the port the CLI will run on
- `--force`: force the non-`.example` config files to be overwritten
- `--debug`: listen to setup Docker logs

## Usage

- Run `npm run server` to start the server

After you see `Start the simulation with runtime (... ticks if chosen limited tick run)`, go to `localhost:21025` (if not changed) and check out the admin utils dashboard. The default pre-spawned user password is `password`.

You can also start the server using `npx` by running `npm i -g screeps-performance-server` and then `npx screeps-performance-server` with optional parameters (see #Configuration run commands)

## Milestones

You can add milestones to the config file, which will be checked every tick. If one of them is reached, it will be logged. The server should stop after all milestones have been reached.

To add a milestone, you can edit or add one and add/update one of the following options:

- `level` (rcl)
- `creeps` (count)
- `structures` (count)