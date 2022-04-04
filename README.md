# ns8-prometheus

This module runs [Prometheus](https://prometheus.io/) as a rootless module.

## Install

Instantiate the module with:

    add-module ghcr.io/nethserver/prometheus:latest 1

The output of the command will return the instance name.
Output example:

    {"module_id": "prometheus1", "image_name": "prometheus", "image_url": "ghcr.io/nethserver/prometheus:latest"}

## Configure

Let's assume that the prometheus instance is named `prometheus1`.

Launch `configure-module`, by setting the following parameters:
- `<MODULE_PARAM1_NAME>`: <MODULE_PARAM1_DESCRIPTION>
- `<MODULE_PARAM2_NAME>`: <MODULE_PARAM2_DESCRIPTION>
- ...

Example:

    api-cli run module/prometheus1/configure-module --data '{}'

The above command will:
- start and configure the prometheus instance
- (describe configuration process)
- ...

Send a test HTTP request to the prometheus backend service:

    curl http://127.0.0.1/prometheus/

## Uninstall

To uninstall the instance:

    remove-module --no-preserve prometheus1

## Testing

Test the module using the `test-module.sh` script:


    ./test-module.sh <NODE_ADDR> ghcr.io/nethserver/prometheus:latest

The tests are made using [Robot Framework](https://robotframework.org/)
