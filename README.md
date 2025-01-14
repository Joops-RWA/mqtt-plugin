# MQTT plugin for Joops R.W.A.

MQTT plugin that broadcasts events to an MQTT broker. At the moment this plugin only broadcasts but
might be extended with additional features as well as including an MQTT server so users won't have
to run a separate MQTT broker.


## Installation

### Adding plugin to config

Before restarting your process, you need to add the plugin into the very end  `core.plugins` or `relay.plugins` section of `app.json` file:

```json
{
    "package": "@deadlock-delegate/mqtt",
    "options": {
        "enabled": true,
        "events": ["block.forged"],
        "topic": "ark/events",
        "mqttBroker": "mqtt://localhost:1883"
    }
}
```

### For production (eg. devnet/mainnet):

1. Install plugin: `<command> plugin:install @deadlock-delegate/mqtt`, eg: `ark plugin:install @deadlock-delegate/mqtt` or `solar plugin:install @deadlock-delegate/mqtt`
2. Add plugin to `app.json`
3. Start your node as you usually start it 

### For development (eg. testnet):

You can run a development MQTT broker by navigating to `etc/` directory in this project a run `docker-compose up`. This will start a MQTT broker in docker.

Assuming you don't run testnet locally via docker:

1. Clone this plugin into `plugins/` directory of the `core` project
2. Add plugin to `app.json`, for testnet the file can be found in: `core/packages/core/bin/config/testnet/app.json`
3. Go into the plugin's directory: `cd mqtt`
4. Build plugin: `yarn build`
5. Run `yarn full:testnet` inside `core/packages/core` directory to start testnet with mqtt plugin

## Credits

- [roks0n](https://github.com/roks0n)
- [console](https://github.com/c0nsol3)
- [All Contributors](../../contributors)

## License

[MIT](LICENSE) © deadlock delegate
