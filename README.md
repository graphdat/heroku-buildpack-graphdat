# heroku-buildpack-graphdat

Add the Graphdat agent to your heroku dyno.

## Usage

Set `GRAPHDAT_AGENT_TOKEN` variable to be your agent's token (from your graphdat settings -> agent API token):

    heroku config:set GRAPHDAT_AGENT_TOKEN=api.bd7060f566

Enable the multipack buildpack

    heroku config:set BUILDPACK_URL=https://github.com/graphdat/heroku-buildpack-multi

Create a file named `.buildpacks` with the following lines in it:

For NodeJS projects, add these lines

    https://github.com/graphdat/heroku-buildpack-apt
    https://github.com/graphdat/heroku-buildpack-graphdat.git
    https://github.com/heroku/heroku-buildpack-nodejs.git

For Ruby projects, add these lines

    https://github.com/graphdat/heroku-buildpack-apt
    https://github.com/graphdat/heroku-buildpack-graphdat.git
    https://github.com/heroku/heroku-buildpack-ruby

Create a file named `Aptfile` containing all of the packages the Graphdat agent depends on:

    adduser
    libc6
    libssl0.9.8
    libssh2-1
    libcurl3
    libcap2-bin
    libpcap0.8


The buildpack currently depends on the [user env compile](https://devcenter.heroku.com/articles/labs-user-env-compile) labs addon to be able to access the Graphdat API key.  To enable run:

    heroku labs:enable user-env-compile

On your next deployment, the Graphdat agent will install along with your application.

## Bugs

Please report any bugs to using the issue tracker.

Pull requests are welcome.

## License

Apache v2
