# PocketIC

PocketIC is a canister smart contract testing solution for the [Internet Computer](https://internetcomputer.org/).


## Download the PocketIC Server
You can find the versions of the PocketIC server below.
Note that older versions might not be available 6 months after they have been released.

| Version   | Release Date | Linux  | macOS	| Changes |
|---        |---           |---     |---    |---      |
| 2.0.0	    | 2023-11-21   | [download](https://download.dfinity.systems/ic/29ec86dc9f9ca4691d4d4386c8b2aa41e14d9d16/openssl-static-binaries/x86_64-linux/pocket-ic.gz) | [download](https://download.dfinity.systems/ic/29ec86dc9f9ca4691d4d4386c8b2aa41e14d9d16/openssl-static-binaries/x86_64-darwin/pocket-ic.gz) | [CHANGELOG.md](CHANGELOG.md#200---2023-11-21) |
| 1.0.0	    | 2023-10-12   | [download](https://download.dfinity.systems/ic/307d5847c1d2fe1f5e19181c7d0fcec23f4658b3/openssl-static-binaries/x86_64-linux/pocket-ic.gz) | [download](https://download.dfinity.systems/ic/307d5847c1d2fe1f5e19181c7d0fcec23f4658b3/openssl-static-binaries/x86_64-darwin/pocket-ic.gz) | [CHANGELOG.md](CHANGELOG.md#100---2023-10-12)|
| 0.1.0	    | 2023-08-31   | [download](https://download.dfinity.systems/ic/865a816108b31956bd449282e5803ce40007789f/openssl-static-binaries/x86_64-linux/pocket-ic.gz) | [download](https://download.dfinity.systems/ic/865a816108b31956bd449282e5803ce40007789f/openssl-static-binaries/x86_64-darwin/pocket-ic.gz) | [CHANGELOG.md](CHANGELOG.md#010---2023-08-31)|

After downloading the binary, unzip the downloaded file and make it executable:
```bash
gzip -d pocket-ic.gz
chmod +x pocket-ic
```

On **macOS**, you might have to additionally run:
```bash
xattr -dr com.apple.quarantine pocket-ic
```
to bypass the developer verification from Apple.
Alternatively, you can open the `pocket-ic` binary by right clicking on it in the Finder and selecting "Open" from the drop-down menu.
Then, confirm opening this application by clicking "Open" in the dialog that pops up.


## Using PocketIC
After completion of above steps, you can verify that everything works by running:
```bash
./pocket-ic --help
```
which prints information on how to use the PocketIC server from the command line.

### Client Libraries
To write canister tests in your projects with PocketIC, it is recommended to use one of the client libraries. The following libraries are available:

* [PocketIC Rust](https://crates.io/crates/pocket-ic)
* [PocketIC Python](https://pypi.org/project/pocket-ic/)
* [Pic JS](https://www.npmjs.com/package/@hadronous/pic) for JavaScript/TypeScript

If you want your client library to be listed here, please post to the [Forum](https://forum.dfinity.org/)!


## Why PocketIC?
Canister developers have several options to test their software, but there are tradeoffs: 
- Install and test on the **mainnet**: The 'real' experience, but you pay with real cycles.
- The **replica** provided by DFX: You get the complete stack of a single IC node.
But therefore, you get no cross- or multisubnet functionality, and likely never will.
Replica is quite heavyweight too, because the nonessential components are not abstracted away.
Furthermore, testing with replica is not deterministic. 

Enter **PocketIC**: 
- *Deterministic*: Synchronous control over the IC's execution environment
- *Lightweight*: Mocks the consensus and networking layers
- *Versatile*: Runs as a service on your test system, and accepts HTTP/JSON.
This enables:
    - Concurrent and independent IC instances by default - sharing is *possible*
    - Multi-language support: Anyone can write an integration library against the PocketIC REST-API in any language
- Support for multiple subnets and Xnet calls

## Source Code
The source code of the PocketIC server is available on [GitHub](https://github.com/dfinity/ic/tree/master/rs/pocket_ic_server).


## Contributing
Would you like to write canister tests in a different language?
The PocketIC server has a JSON/REST interface, against which you may implement a user-facing library in any language.

If you decide to contribute, we encourage you to announce it on the [Forum](https://forum.dfinity.org/)!
