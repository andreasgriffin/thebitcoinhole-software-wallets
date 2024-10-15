# The Bitcoin Hole - Software Wallets

## Introduction

Software wallets, also known as hot wallets, are applications that enable users to store, manage, and transact with Bitcoin. Unlike hardware wallets, which are physical devices, software wallets are digital and run on various platforms, including desktop, mobile, and web.

This project goal is to have the more complete database of Bitcoin Software Wallets features, so they can be compared, helping users to choose wisely. The database is open-source, meaning anyone can collaborate to improve and correct any wrong data or add new wallets.

## Collaboration

Inside the `items` directory, there is a JSON file for each wallet, with all the data about it. To collaborate (adding missing data, fixing wrong data or adding a new wallet), just fork the repository and send a pull request with the changes.
Before sending the pull request, please run the following commands to format the JSON:

```
cd scripts/
node json-format.js
```

## JSON format

The following is a sample of the JSON format:

```json
{
    "id": "wallet-id",
    "name": "Wallet Name",
    "category-name": {
      "feature-name-1": {
        "value": "YES", 
        "flag": "positive",
        "supported": true,
        "texts": [
          "Optional contextual text describing the feature"
        ],
        "links": [
          {
            "title": "Optional contextual link referencing official documentation",
            "url": "url"
          }
        ]
      },
      "feature-name-2": {
        "value": "Experimental",
        "flag": "neutral",
        "supported": true
      },
      "feature-name-3": {
        "value": "NO",
        "flag": "negative",
        "supported": false
      }
    }
}
```

JSON fields:

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| id | string | true | The wallet id. It matches with the JSON file name. |
| name | string | true | The wallet name. |
| category-name.feature-name-1.value | string | yes | The visible feature value. For example: `"YES"`, `"NO"`, `"Experimental"`, etc |
| category-name.feature-name-1.flag | string | no | The flag of the wallet feature. Possible values: `"positive"`, `"neutral"` or `"negative"` |
| category-name.feature-name-1.supported | boolean | no | If the feature is supported by the wallet. This is used to filter by this feature |
| category-name.feature-name-1.texts | array of strings | no | Official Texts with info about the feature |
| category-name.feature-name-1.links | array of objects | no | Official links with info about the feature |
| category-name.feature-name-1.links.title | string | yes | The title of the link |
| category-name.feature-name-1.links.url | string | yes | The url of the link |

On each pull request, the JSON files are verified to be sure they are valid and well-formatted. You can run the following command inside the `scripts` directory to format the JSON before sending a pull request:

```
node json-format.js
```

All the features supported:

| Category | Category Id | Feature | Feature Id |
| --- | --- | --- | --- |
| Basic Information | basic-information | Launch Year | year |
| Company / Project | company | Brand | brand |
| Company / Project | company | Headquarters / Location | headquarters |
| Company / Project | company | Website | website |
| Company / Project | company | Blog | blog |
| Company / Project | company | X (Twitter) | twitter |
| Company / Project | company | Nostr | nostr |
| Company / Project | company | YouTube | youtube |
| Company / Project | company | GitHub / GitLab | github |
| Company / Project | company | Slack | slack |
| Company / Project | company | Discord | discord |
| Communities | communities | Telegram | telegram |
| Communities | communities | Reddit | reddit |
| Networks | networks | Bitcoin-only | bitcoin-only |
| Networks | networks | Bitcoin Mainnet | btc-mainnet |
| Networks | networks | Bitcoin Testnet | btc-testnet |
| Networks | networks | Bitcoin Regtest | btc-regtest |
| Networks | networks | Bitcoin signet | btc-signet |
| Networks | networks | Lightning Network | lightning-network |
| Currency | currency | Fiat Denominations | fiat |
| Currency | currency | Bitcoin Unit (BTC) | btc |
| Currency | currency | Bitcoin Unit (SAT) | sats |
| Currency | currency | Exchange Rate Provider | exchange-rate-provider |
| App Lock | app-lock | PIN Lock | pin-lock |
| App Lock | app-lock | Duress PIN | duress-pin |
| App Lock | app-lock | Dynamic Keypad | dynamic-keypad |
| App Lock | app-lock | Countdown to Reset PIN | countdown-reset-pin |
| App Lock | app-lock | Alphanumeric PIN | alphanumeric-pin |
| App Lock | app-lock | Pattern Lock | pattern-lock |
| App Lock | app-lock | Fingerprint Lock | fingerprint-lock |
| App Lock | app-lock | Dummy/Decoy Wallet | dummy-wallet |
| Private Keys | private-keys | Hot Keys Support | hot-keys |
| Private Keys | private-keys | Mulitple Wallets at the same time | multiple-wallets |
| Private Keys | private-keys | User Added Entropy | user-added-entropy |
| Private Keys | private-keys | Passphrases support | passphrase-support |
| Private Keys | private-keys | Master Key Fingerprint | master-key-fingerprint |
| Private Keys | private-keys | Backup Output Descriptor | backup-output-descriptor |
| Private Keys | private-keys | Restore from Output Descriptor | restore-output-descriptor |
| Private Keys | private-keys | Backup / recovery with BIP39 seed phrase | backup-recovery-seedphrase |
| Private Keys | private-keys | 12 Words BIP39 Seed Creation | create-12-words |
| Private Keys | private-keys | 24 Words BIP39 Seed Creation | create-24-words |
| Private Keys | private-keys | 12 Words BIP39 Seed Import | import-12-words |
| Private Keys | private-keys | 24 Words BIP39 Seed Import | import-24-words |
| Private Keys | private-keys | Seed Phrase Autocomplete | seed-phrase-autocomplete |
| Private Keys | private-keys | In-App Keyboard | inapp-keyboard |
| Private Keys | private-keys | SeedQR | seed-qr |
| Address Format | address-format | Legacy (P2PKH) | legacy |
| Address Format | address-format | Nested Segwit (P2SH) | nested-segwit |
| Address Format | address-format | Native Segwit (P2WPKH) | native-segwit |
| Address Format | address-format | Taproot (P2TR) | taproot |
| Receive Addresses | addresses | View Address as Text | view-address-text |
| Receive Addresses | addresses | View Address as QR | view-address-qr |
| Receive Addresses | addresses | Display Multiple Addresses | display-multiple-addresses |
| Receive Addresses | addresses | Verify Address from Text | verify-address-text |
| Receive Addresses | addresses | Verify Address from QR | verify-address-qr |
| Signing | signing | Multi-sig (PSBTs) | multi-sig |
| Signing | signing | Frost | frost |
| Signing | signing | Sign by USB | usb-data |
| Signing | signing | Sign by NFC | nfc |
| Signing | signing | Sign by QR | qr |
| Signing | signing | UR2.0 Animated QRs | ur-2-animated-qrs |
| Signing | signing | BBQr | bbqr |
| Fees | fees | Fee Control | fee-control |
| Fees | fees | Replace-by-fee (RBF) | replace-by-fee |
| Fees | fees | Child-pays-for-parent (CPFP) | child-pays-for-parent |
| Privacy | privacy | Coin Control | coin-control |
| Privacy | privacy | Coinjoin | coinjoin |
| Privacy | privacy | Hide Sensitive Data | hide-sensitive-data |
| Privacy | privacy | Stealth Mode | stealth-mode |
| Privacy | privacy | Built-in secure communication | built-in-secure-communication |
| Privacy | privacy | PayNyms | paynyms |
| Privacy | privacy | Silent Payments | silent-payments |
| Full Node Integration | node-integration | Own Node Support | own-node |
| Full Node Integration | node-integration | Embedded Node | local-node |
| Full Node Integration | node-integration | Bitcoin Core Integration | bitcoin-core |
| Full Node Integration | node-integration | Electrum Server Integration | electrum-server |
| Full Node Integration | node-integration | Fulcrum Server Integration | fulcrum-server |
| Full Node Integration | node-integration | Dojo Server Integration | dojo-server |
| Full Node Integration | node-integration | Tor | tor |
| Other Features | other-features | Transaction Labeling | transaction-labeling |
| Other Features | other-features | Batch Transactions | batch-transactions |
| Other Features | other-features | Miniscript | miniscript |
| Other Features | other-features | Timelocks | timelocks |
| Other Features | other-features | Encrypted Storage | encrypted-storage |
| Other Features | other-features | Dark Mode | dark-mode |
| Other Features | other-features | Wallet Rollover | wallet-rollover |
| Android Support | android-support | Supported | android-supported |
| Android Support | android-support | Google Play | android-googleplay-support |
| Android Support | android-support | Direct APK Download | android-apk-support |
| Android Support | android-support | Latest Version | android-latest-version |
| Android Support | android-support | Latest Release Date | android-latest-release-date |
| Android Support | android-support | Release Notes | android-release-notes |
| Android Support | android-support | Source-available | android-source-available |
| Android Support | android-support | Free & Open Source (FOSS) | android-open-source |
| Android Support | android-support | License | android-license |
| Android Support | android-support | Reproducible Builds | android-reproducible-builds |
| iOS Support | ios-support | Supported | ios-supported |
| iOS Support | ios-support | Latest Version | ios-latest-version |
| iOS Support | ios-support | Latest Release Date | ios-latest-release-date |
| iOS Support | ios-support | Release Notes | ios-release-notes |
| iOS Support | ios-support | Source-available | ios-source-available |
| iOS Support | ios-support | Free & Open Source (FOSS) | ios-open-source |
| iOS Support | ios-support | License | ios-license |
| iOS Support | ios-support | Reproducible Builds | ios-reproducible-builds |
| Web Support | web-support | Supported | web-supported |
| Web Support | web-support | Release Notes | web-release-notes |
| Web Support | web-support | Source-available | web-source-available |
| Web Support | web-support | Free & Open Source (FOSS) | web-open-source |
| Web Support | web-support | License | web-license |
| Web Support | web-support | Reproducible Builds | web-reproducible-builds |
| MacOS Support | macos-support | Supported | macos-supported |
| MacOS Support | macos-support | Latest Version | macos-latest-version |
| MacOS Support | macos-support | Latest Release Date | macos-latest-release-date |
| MacOS Support | macos-support | Release Notes | macos-release-notes |
| MacOS Support | macos-support | Source-available | macos-source-available |
| MacOS Support | macos-support | Free & Open Source (FOSS) | macos-open-source |
| MacOS Support | macos-support | License | macos-license |
| MacOS Support | macos-support | Reproducible Builds | macos-reproducible-builds |
| Linux Support | linux-support | Supported | linux-supported |
| Linux Support | linux-support | Latest Version | linux-latest-version |
| Linux Support | linux-support | Latest Release Date | linux-latest-release-date |
| Linux Support | linux-support | Release Notes | linux-release-notes |
| Linux Support | linux-support | Source-available | linux-source-available |
| Linux Support | linux-support | Free & Open Source (FOSS) | linux-open-source |
| Linux Support | linux-support | License | linux-license |
| Linux Support | linux-support | Reproducible Builds | linux-reproducible-builds |
| Windows Support | windows-support | Supported | windows-supported |
| Windows Support | windows-support | Latest Version | windows-latest-version |
| Windows Support | windows-support | Latest Release Date | windows-latest-release-date |
| Windows Support | windows-support | Release Notes | windows-release-notes |
| Windows Support | windows-support | Source-available | windows-source-available |
| Windows Support | windows-support | Free & Open Source (FOSS) | windows-open-source |
| Windows Support | windows-support | License | windows-license |
| Windows Support | windows-support | Reproducible Builds | windows-reproducible-builds |
| Umbrel OS Support | umbrel-os-support | Supported | umbrel-os-supported |
| Umbrel OS Support | umbrel-os-support | Latest Version | umbrel-os-latest-version |
| Umbrel OS Support | umbrel-os-support | Latest Release Date | umbrel-os-latest-release-date |
| Umbrel OS Support | umbrel-os-support | Release Notes | umbrel-os-release-notes |
| Umbrel OS Support | umbrel-os-support | Source-available | umbrel-os-source-available |
| Umbrel OS Support | umbrel-os-support | Free & Open Source (FOSS) | umbrel-os-open-source |
| Umbrel OS Support | umbrel-os-support | License | umbrel-os-license |
| Umbrel OS Support | umbrel-os-support | Reproducible Builds | umbrel-os-reproducible-builds |
| Start OS Support | start-os-support | Supported | start-os-supported |
| Start OS Support | start-os-support | Latest Version | start-os-latest-version |
| Start OS Support | start-os-support | Latest Release Date | start-os-latest-release-date |
| Start OS Support | start-os-support | Release Notes | start-os-release-notes |
| Start OS Support | start-os-support | Source-available | start-os-source-available |
| Start OS Support | start-os-support | Free & Open Source (FOSS) | start-os-open-source |
| Start OS Support | start-os-support | License | start-os-license |
| Start OS Support | start-os-support | Reproducible Builds | start-os-reproducible-builds |
| Hardware Wallets Support | hardware-wallets-support | Jade | jade |
| Hardware Wallets Support | hardware-wallets-support | Coldcard Mk4 | coldcard-mk4 |
| Hardware Wallets Support | hardware-wallets-support | Coldcard Q | coldcard-q |
| Hardware Wallets Support | hardware-wallets-support | BitBox02 | bitbox02-btconly |
| Hardware Wallets Support | hardware-wallets-support | Keystone 3 Pro | keystone-3-pro |
| Hardware Wallets Support | hardware-wallets-support | Passport Batch 2 | passport-batch-2 |
| Hardware Wallets Support | hardware-wallets-support | Trezor Model One | trezor-model-one |
| Hardware Wallets Support | hardware-wallets-support | Trezor Model T | trezor-model-t |
| Hardware Wallets Support | hardware-wallets-support | Trezor Safe 3 | trezor-safe-3 |
| Hardware Wallets Support | hardware-wallets-support | Trezor Safe 5 | trezor-safe-5 |
| Hardware Wallets Support | hardware-wallets-support | Ledger Nano S Plus | ledger-nano-s-plus |
| Hardware Wallets Support | hardware-wallets-support | Ledger Nano X | ledger-nano-x |
| Hardware Wallets Support | hardware-wallets-support | SeedSigner | seedsigner |
| Hardware Wallets Support | hardware-wallets-support | Specter DIY | specter-diy |
| Hardware Wallets Support | hardware-wallets-support | Krux | krux |
| Hardware Wallets Support | hardware-wallets-support | Tapsigner | tapsigner |
| Paid Services | paid-services | Assisted Self-custody | assisted-self-custody |
| Paid Services | paid-services | Inheritance Planning | inheritance-planning |

## Website

The [thebitcoinhole.com](https://thebitcoinhole.com/) website offers a Software Wallet Comparison using this database. This website is the most comprehensive resource for comparing the features of top software wallets. It provides an in-depth analysis of each wallet’s security features, privacy, usability, compatibility, and more.

## Sponsor this project
Sponsor this project to help us get the funding we need to continue working on it.

* [Donate with Bitcoin Lightning](https://getalby.com/p/thebitcoinhole) ⚡️ [thebitcoinhole@getalby.com](https://getalby.com/p/thebitcoinhole)
* [Donate with PayPal or a credit card using Ko-fi](https://ko-fi.com/thebitcoinhole)
* [Donate on Patreon](https://www.patreon.com/TheBitcoinHole)

## Follow us
* [Twitter](http://x.com/thebitcoinhole)
* [Nostr](https://primal.net/p/npub1mtd7s63xd85ykv09p7y8wvg754jpsfpplxknh5xr0pu938zf86fqygqxas)
* [Medium](https://medium.com/the-bitcoin-hole)
* [GitHub](https://github.com/thebitcoinhole)
