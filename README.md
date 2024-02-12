# PocketIC

PocketIC is a canister smart contract testing solution for the [Internet Computer](https://internetcomputer.org/).


## Download the PocketIC Server
You can find the versions of the PocketIC server under the [Releases](https://github.com/dfinity/pocketic/releases) tab on the right.
For macOS, choose `pocket-ic-x86_64-darwin.gz`, for Linux, choose `pocket-ic-x86_64-linux.gz`.

Save the downloaded file as `pocket-ic.gz`, decompress it, and make it executable:

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
To write canister tests in your projects with PocketIC, it is recommended to use one of the client libraries.
The following libraries are available:

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

To see a documentation of the server's endpoints, PocketIC offers an endpoint `/api.json`, which will return an OpenAPI specification.
You can then use tools like the [Swagger Editor](https://editor-next.swagger.io/) to display the returned JSON in a more human readable way.

If you decide to contribute, we encourage you to announce it on the [Forum](https://forum.dfinity.org/)!
