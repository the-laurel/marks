:::center
# Marks Factory Tutorial v1
:::

## Intro

This is the Marks Factory. `v1` means `version 1`.
Marks Factory is a dApp (decentralized app) player and an IDE (Integrated development environment) for dApps.

Marks are markdown apps with access to decentralized web tools. This tutorial is a mark.

### Known Issues
- connecting to the IPFS network and loading marks is sometimes slow: refresh the page.

### Top Toolbar
:Button[more]{icon=true} load a recommended mark
:Button[edit]{icon=true}  enter "edit" mode.
:Button[play]{icon=true}  enter "play" mode. This is how your mark is presented to the user.
:Button[export]{icon=true} export your mark to IPFS. If your mark uses contract ABIs and addresses from your workspace, they will also be exported. You will see a QRcode image and if you click on it, the URL will be copied to the clipboard. The URL is of the form `<BASE_URL>/?ipfs=<IPFS_HASH>&input=<PREDEFINED_INPUT>`. You can preset form inputs by filling them in and then exporting.
:Button[eth]{icon=true} Load a contract function form, from the ABIs and addresses saved in the workspace
:Button[component]{icon=true} Load a user interface component or command
:Button[bold]{icon=true} - :Button[deindent]{icon=true} markdown syntax helpers. See https://guides.github.com/features/mastering-markdown/

### Bottom Workspace

Add contract ABI & address information by:
- clicking on the bottom left :Button[more]{icon=true} -> Add item -> filling the form; if you fill in an IPFS hash from a contract saved in the Solidity compiler format, the abi will be loaded automatically -> click on the bottom right :Button[^]{}
- pasting JSON data in the bottom text area, of the form:
```
[{
    "ipfs": "QmP5rC8m7DsZwmRjFr7PESKe9e9o7p7VVNP62jdBbiCGbQ",
    "name": "WETH",
    "address": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
    "abi": []
}]
```

## Add your mark to the menu recommendations

Make a Pull Request to https://github.com/loredanacirstea/recommendations/blob/main/marks/mainMenu.json and add your own mark under an existing category or propose a new category.

### Requirements
- your mark will have the GNU General Public License v3.0 license.
- mark title has the form: `<TITLE> v<VERSION>`, e.g. `Mark Title v1`
- mark contains a video tutorial of how to use the mark
- add a `:Link[created by 0x<ETH_ADDRESS>]{src=<DONATION_MARK>}` at the bottom of your mark, for eventual donations, directing to the Payment mark preset with your data (example at the bottom of this mark). Fill in your data in :Link[Payment Request]{src="/?ipfs=QmfFPi6EutBU2kdQExT57qV4aWtRx7KyrXnVnvQBuEme6k"} and export, to get the link
- the mark's "label" is the same as its title
- export your mark to IPFS first and use the 46 character hash as the mark's value id (e.g. `QmadhiGumnFNeHf8pJge6A2sdunVNXH6VnLuFFvzsAbieC`)

### Info
- if your mark has been approved, updating the mark to a new version will be prioritized. E.g. if others, at a later date will propose a mark with the same functionality, it will not be approved unless exceedingly better.
- if a similar mark already exists, make a PR only if your mark brings significant improvements.

### Resources

- Marks Factory playlist https://www.youtube.com/playlist?list=PL323JufuD9JBUwKSPILGKBaI5JPyAVapn

-----

:::center


::Video[]{src="https://www.youtube.com/embed/6QkiuUSg7L8" width="100%" height="400px"}

The following is the link for supporting/promoting both Marks Factory and this tutorial:

:Link[created by 0x833D4c383Bef3163d447F90DA78f97379bDcC04d]{src="/?ipfs=QmfFPi6EutBU2kdQExT57qV4aWtRx7KyrXnVnvQBuEme6k&input=%7B%22amount_wei%22%3A%7B%22_hex%22%3A%220x071afd498d0000%22%2C%22_isBigNumber%22%3Atrue%7D%2C%22somethingnotexisting%22%3A%7B%22name%22%3A%22ropsten%22%2C%22chainId%22%3A3%2C%22ensAddress%22%3A%220x00000000000C2E074eC69A0dFb2997BA6C7d2e1e%22%7D%2C%22amount%22%3A%220.002%22%2C%22gasLimit%22%3A%2235000%22%2C%22gasPrice%22%3A%2215%22%2C%22receiver%22%3A%220x833D4c383Bef3163d447F90DA78f97379bDcC04d%22%2C%22reason%22%3A%22donation%20for%20creating%20a%20useful%20mark%22%7D"}

--------


:::
