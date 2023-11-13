# PocketIC

PocketIC is a canister smart contract testing solution for the [Internet Computer](https://internetcomputer.org/).

## Download
You can find the versions of the PocketIC server binary below.
Note that older versions might not be available 6 months after they have been released.

| Version   | Release Date | Linux  | macOS	| Changes |
|---        |---           |---     |---    |---      |
| 2.0.0	    | 2023-11-XX   | download  	|  download 	| [CHANGELOG.md](CHANGELOG.md#200---2023-11-xx) |
| 1.0.0	    | 2023-10-12   | [download](https://download.dfinity.systems/ic/307d5847c1d2fe1f5e19181c7d0fcec23f4658b3/openssl-static-binaries/x86_64-linux/pocket-ic.gz) | [download](https://download.dfinity.systems/ic/307d5847c1d2fe1f5e19181c7d0fcec23f4658b3/openssl-static-binaries/x86_64-darwin/pocket-ic.gz)   | [CHANGELOG.md](CHANGELOG.md#100---2023-10-12)|
| 0.1.0	    | 2023-08-31   | [download](https://download.dfinity.systems/ic/865a816108b31956bd449282e5803ce40007789f/openssl-static-binaries/x86_64-linux/pocket-ic.gz) | [download](https://download.dfinity.systems/ic/865a816108b31956bd449282e5803ce40007789f/openssl-static-binaries/x86_64-darwin/pocket-ic.gz)   | [CHANGELOG.md](CHANGELOG.md#010---2023-08-31)|

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

* [PocketIC for Rust](https://crates.io/crates/pocket-ic)
* [PocketIC for Python](https://pypi.org/project/pocket-ic/)
* [Pic JS for JavaScript/TypeScript](https://www.npmjs.com/package/@hadronous/pic)

If you want your client library to be listed here, please post to the [Forum](https://forum.dfinity.org/)!
