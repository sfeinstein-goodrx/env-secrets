# env-secrets
A script for loading content such as sensitive environment variables into the shell environment from a secure backend.
Currently, LastPass is the default and only backend from which content is loaded.

# Danger! Danger!
This is an unsophisticated script that effectively allows arbitrary execution of whatever it is told to load.  
Make sure you only run this against trusted content.

# Installation and usage
This script requires the [LastPass CLI](https://github.com/lastpass/lastpass-cli), which can be installed as indicated on its GitHub page or via [brew](https://formulae.brew.sh/formula/lastpass-cli).

        brew install lastpass-cli

You'll also want to make sure you are logged in by running `lpass login <your LastPass username>`.

Next, create a Note in LastPass, with any name that you like.
The contents of the note should be whatever you'd like sourced into your shell.

For example, you could create a Note called `env-secrets-goodrx-common` with contents:

        export NPM_TOKEN_GH_GOODRX_CI='your GitHub token value'
        export MAILOSAUR_API_KEY='your Mailosaur API key'

For documentation on the script parameters and usage run:

        ./bin/env-secrets --help
