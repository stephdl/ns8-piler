# ns8-piler

This is a template module for [NethServer 8](https://github.com/NethServer/ns8-core).
To start a new module from it:

1. Click on [Use this template](https://github.com/NethServer/ns8-piler/generate).
   Name your repo with `ns8-` prefix (e.g. `ns8-mymodule`). 
   Do not end your module name with a number, like ~~`ns8-baaad2`~~!

1. An automated initialization workflow starts: wait for its completion.
   You can follow the run inside the "Actions" tab, the workflow is named "Initial commit"

1. You can now clone the repository

1. Edit this `README.md` file, by replacing this section with your module
   description

1. Commit and push your local changes

## Install

Instantiate the module with:

    add-module ghcr.io/nethserver/piler:latest 1

The output of the command will return the instance name.
Output example:

    {"module_id": "piler1", "image_name": "piler", "image_url": "ghcr.io/nethserver/piler:latest"}

## Configure

Let's assume that the piler instance is named `piler1`.

Launch `configure-module`, by setting the following parameters:
- `<MODULE_PARAM1_NAME>`: <MODULE_PARAM1_DESCRIPTION>
- `<MODULE_PARAM2_NAME>`: <MODULE_PARAM2_DESCRIPTION>
- ...

Example:

    api-cli run module/piler1/configure-module --data '{}'

The above command will:
- start and configure the piler instance
- (describe configuration process)
- ...

Send a test HTTP request to the piler backend service:

    curl http://127.0.0.1/piler/

## Uninstall

To uninstall the instance:

    remove-module --no-preserve piler1

## Testing

Test the module using the `test-module.sh` script:


    ./test-module.sh <NODE_ADDR> ghcr.io/nethserver/piler:latest

The tests are made using [Robot Framework](https://robotframework.org/)
