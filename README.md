# heroku-buildpack-graphdat

Add the Graphdat agent to you heroku dyno.

## Usage

Set `GRAPHDAT_AGENT_TOKEN` variable to your agent's token (from your graphdat settings):

    heroku config:set GRAPHDAT_AGENT_TOKEN=api.bd7060f566

Enable the multipack buildpack

    heroku config:set BUILDPACK_URL=https://github.com/graphdat/heroku-buildpack-multi

Create `.buildpacks` file:

    https://github.com/graphdat/heroku-buildpack-graphdat.git
    https://github.com/heroku/heroku-buildpack-nodejs.git

## Bugs

Please report any bugs to using the issue tracker.

Pull requests are welcome.

## License

Apache v2
