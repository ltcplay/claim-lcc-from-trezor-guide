# How to claim your LCC from a Trezor based LTC wallet

A guide that shows how to claim LCC from a trezor

### What you're going to need:

1. Your trezor
2. The 24 word key your trezor's private key is based on
3. Offline version of this tool: https://iancoleman.io/bip39/
4. Synced LCC wallet (https://litecoinca.sh/#download - you may want to download the bootstrap if you haven't already, otherwise it will take many hours to sync)
5. Patience

I know this works as I've done it myself.

Here's an overview followed by more detailed instructions:

1. Send whatever currencies currently on your trezor to another secure wallet or trezor.
2. Create an offline version of https://iancoleman.io/bip39/
3. Open the BIP39 tool in your browser, and paste your 24 word seed phrase into text box labelled: "BIP39 Mnemonic"
4. Once the tool is done processing (should only take a few seconds), click 'BIP49' under the Derivation Path tabs:
![alt text](https://i.imgur.com/iTEawaD.png)
5. Scroll down to the Derived Addresses.
6. Open your (now empty) Trezor, switch to the LTC wallet, and copy any of the addresses that had LTC at the time of the fork into a text file
7. Find these addresses in the Derived Addresses table, and copy the private keys into your text file next to each address you copied from step 5.
8. Open your LCC wallet, and go to Main Menu -> Help -> Debug Window -> Console
9. Enter each of the private keys from step 6 in the following format: importprivkey [PASTE PRIVATE KEY HERE] LABELFORKEY false
If it asks you to rescan, just say no. You don't have to do that after every key and it will take forever if you do.
10. Once your done entering your keys, close your LCC wallet, and create a shortcut with -rescan at the end of the target.
11. Run the shortcut and wait for it to finish rescan. It will take at least an hour, if not more.
12. Now you need to enter your recieving address in the debug console.
13. In the LCC wallet, go to Main Menu -> File -> Receiving Addressed
14. There should be an address for each key you entered in step 9. Right click on each key, select "Copy Address" from the menu, and paste those somewhere in your text file. Copy each address off for the next step.
15. Open the debug console again () and enter the recieving addresses using this format: addwitnessaddress [PASTE RECEIVING ADDRESS HERE]
16. Close your wallet, and run the rescan shortcut again.
17. Once it's done, you should see your LCC.

## TODO

Add information about rekeying trezor so it can be reused.
