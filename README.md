# ns8-tig
NS8 module based on https://github.com/InfluxCommunity/TIG-Stack-using-InfluxDB-3

Delivers a modern Telegraf - Influxdb3 - grafana setup.
Used for home automation logging

NS8 uses a default monitoring stack as a core module too.
Used for logging through MQTT enabled home automation stuff and Athom Homey influxdb integrations.


1. Adjust `.github/workflows` to your needs. `clean-registry.yml` might
   need the proper list of image names to work correctly. Unused workflows
   can be disabled from the GitHub Actions interface.

## Install

Instantiate the module with:

    add-module ghcr.io/maja2020/tig:latest 1

The output of the command will return the instance name.
Output example:

    {"module_id": "tig1", "image_name": "tig", "image_url": "ghcr.io/maja2020/tig:latest"}

## Configure

Let's assume that the tig instance is named `tig1`.

Launch `configure-module`, by setting the following parameters:
- `<MODULE_PARAM1_NAME>`: <MODULE_PARAM1_DESCRIPTION>
- `<MODULE_PARAM2_NAME>`: <MODULE_PARAM2_DESCRIPTION>
- ...

Example:

    api-cli run module/tig1/configure-module --data '{}'

The above command will:
- start and configure the tig instance
- (describe configuration process)
- ...

Send a test HTTP request to the tig backend service:

    curl http://127.0.0.1/tig/

## Uninstall

To uninstall the instance:

    remove-module --no-preserve tig1

## Testing

Test the module using the `test-module.sh` script:


    ./test-module.sh <NODE_ADDR> ghcr.io/nethserver/tig:latest

The tests are made using [Robot Framework](https://robotframework.org/)

## UI translation

Translated with [Weblate](https://hosted.weblate.org/projects/ns8/).

To setup the translation process:

- add [GitHub Weblate app](https://docs.weblate.org/en/latest/admin/continuous.html#github-setup) to your repository
- add your repository to [hosted.weblate.org]((https://hosted.weblate.org) or ask a NethServer developer to add it to ns8 Weblate project
