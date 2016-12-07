# twiage-config

##Twiage Common Configuration Library for JavaScript Projects
#####Provides hierarchical configuration with files, environment variables and command-line arguments.

## API

_twiage-config_ will merge configs from several sources into one config.
Therefore it will override configs from following sources from default (1) to most-specific (3):
1. env variables
2. default config
3. process.env.ACTIVE_PROFILE specific config

The default config sets the base, ACTIVE_PROFILE specific config overrules default config and env variable config overrules everything.

Only the env variables specified in _custom_env_ file will be merged into config.

### Config Dir

The default config dir will be <project-root>/config. To change that set the TWIAGE_CONFIG_DIR env variable.

### Default Config

Default configs are stored in a _default.json_ file inside your config dir.

### ACTIVE_PROFILE specific config

To add ACTIVE_PROFILE specific configs add a config file called _{ACTIVE_PROFILE}.json_ to the config dir.

### Env Variables

To add config values from env variables you have to create a file called _custom_env.json_.

### get(configPath)

To get a config value simple require _turing-config_ and call _get(configPath)_ inside the config dir.

    const config = require('twiage-config');

    const myConfigPathValue = config.get('some:config:path');
