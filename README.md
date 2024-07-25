### Turbin3-Tutorials
## Explanation
In this tutorial I coded keygen.ts // airdrop.ts // transfer.ts // enroll.ts
# keygen.ts
In the keygen file, i generated a brand new Solana Wallet.
The specific command is -> Keypair.generate()
To run the keygen.ts script, the command is: yarn keygen
# airdrop.ts
In the airdrop file, i used a command to add SOL to the generated Solana Wallet
The specific command is -> await connection.requestAirdrop(keypair.publicKey, 2 * LAMPORTS_PER_SOL);
To run the airdrop.ts script, the command is: yarn airdrop
# transfer.ts
First i generated another new Solana Wallet with yarn keygen. Then, In the transfer file i wrote a function for transferring SOL from firstWallet to newWallet.
The specific command is -> SystemProgram.transfer({
                fromPubkey: from.publicKey,
                toPubkey:  to,
                lamports: LAMPORTS_PER_SOL/100,
            })
To run the transfer.ts script, the command is: yarn airdrop
# enroll.ts
In enroll file, i took IDL of the program and used in the code to prove that i have reached to code and proved my Github account and public key.
The specific command is -> await program.methods
        .complete(github)
        .accounts({
          signer: keypair.publicKey,
        })
        .signers([
          keypair
        ]).rpc();
To run the transfer.ts script, the command is: yarn enroll
# TXs
yarn airdrop tx => https://explorer.solana.com/tx/pNpi9H82YkqZHFNYFMj3eUWd2ToRyxWGMajnkEXPpxZ7VM7HaU1tZqTL5gYvoAH21ovBYLq4CvDx3469hvpLYjW?cluster=devnet

yarn transfer tx => https://explorer.solana.com/tx/29w7dokuZ3xvURMn9kZci4qxbbinokWwuoX2b5qtgDBTukyu1zDYtuqWSBLNq4mA9wkZAN4Q9sWzZijpdu3HkqUs?cluster=devnet

yarn enroll tx => https://explorer.solana.com/tx/2eHijufe9aowVrutEenzkur81vM3r6erd42jmaHV8AjzcbWrJc5nZH6PEj9vmpgZAsiL3vRjxwwAchW8uDHMJNmv?cluster=devnet
