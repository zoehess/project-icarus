# Project Icarus 

Icarus, a reference implementation for a lightweight wallet, which will enable developers to create their own wallets for Cardano. Icarus runs in a browser as a Google Chrome extension and offers an easy-to-use alternative to Daedalus. This wallet does not need to download and validate a copy of the Cardano blockchain, instead, it uses a copy of the blockchain on a server, so it offers advantages in terms of speed of use. Icarus is secure – private keys are encrypted on the user's browser and not shared with servers. Releasing the source code will mean the community can develop wallets and integrate with Cardano as required and Cardano moves further towards decentralisation.

## Getting started

Have a look at the project's architecture to get a better understanding of the project:
<https://github.com/input-output-hk/project-icarus/wiki/Architecture>

### Project layout

Here are the different pieces of the architecture:

* [backend/](https://github.com/input-output-hk/project-icarus-backend-service) - the source of the backend webapp
* [importer/](https://github.com/input-output-hk/project-icarus-importer) - the chain importer
* [chrome-extension/](https://github.com/input-output-hk/project-icarus-chrome) - the source of the chrome extension

### Quickstart

Here are the instructions to build and run everything locally. It requires Nix, Docker and docker-compose to be installed on the machine.

To build and start the backend run these commands:

```sh
docker load -i "$(nix-build importer/ -A dockerImages.testnetBlockchainImporter --argstr gitrev "undefined" --no-out-link)"
docker-compose up -d
```

It will start the database, importer and webapp. The API is now reachable at <https://localhost:8080/>.

Now that the backend is running, let's build and run the Chrome Extension.

TODO: how to do that?

## License

Licensed under the [Apache License, Version 2.0](LICENSE.md)
