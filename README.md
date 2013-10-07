# heroku-buildpack-graphdat

Adda the Graphdat agent to your heroku dyno.

## Usage

Set `GRAPHDAT_AGENT_TOKEN` variable to your agent's token (from your graphdat settings):

    heroku config:set GRAPHDAT_AGENT_TOKEN=api.bd7060f566

Enable the multipack buildpack

    heroku config:set BUILDPACK_URL=https://github.com/graphdat/heroku-buildpack-multi

Create `.buildpacks` file:

    https://github.com/graphdat/heroku-buildpack-apt
    https://github.com/graphdat/heroku-buildpack-graphdat.git
    https://github.com/heroku/heroku-buildpack-nodejs.gitd

Create `Aptfile` packages that Graphdat depends on:
    adduser
    libc6
    libssl0.9.8
    libssh2-1
    libcurl3
    libcap2-bin
    libpcap0.8

## Bugs

Please report any bugs to using the issue tracker.

Pull requests are welcome.

## License

Apache v2
