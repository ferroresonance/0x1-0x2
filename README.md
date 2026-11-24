# LUKSO 0x01 to 0x02

A public page for switching an existing LUKSO Mainnet validator from `0x01` withdrawal credentials to compounding `0x02` credentials with your own wallet.

Live page: https://ferroresonance.github.io/0x1-0x2/

## What it does

- Connects to the wallet in the browser.
- Uses LUKSO Mainnet, chain ID `42`, and asks the wallet to switch to that network.
- Accepts an existing validator BLS public key (48 bytes, 96 hex characters).
- Sends a self-consolidation request: the source key and the target key are both the pubkey you paste.
- Calls the LUKSO consolidation contract `0x0000bbddc7ce488642fb579f8b00f3a590007251`.
- Pays the request fee of 1000 wei from the connected wallet.
- The connected wallet signs the transaction.

The page does not ask for a seed phrase, a validator keystore, or a withdrawal key. It does not create validators, and it does not top up a validator.

## Before you send

1. Check that the validator still uses `0x01` withdrawal credentials.
2. Connect the wallet that is that validator's `0x01` withdrawal address.
3. Confirm the wallet is on LUKSO, chain ID 42.
4. Confirm the public key in the wallet prompt.
5. Confirm the transaction target is `0x0000bbddc7ce488642fb579f8b00f3a590007251` and the value is 1000 wei.

The request is queued on the consensus layer. The credential change shows on the LUKSO consensus explorer after the queue processes it.
