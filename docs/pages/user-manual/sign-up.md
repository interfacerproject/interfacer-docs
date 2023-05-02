<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Copyright (C) 2022-2023 Dyne.org foundation <foundation@dyne.org>.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
-->

<!--- Future manual, page by page	
[](../_media/examples/zencode_cookbook/credential/credentialAnyoneVerifyProof.zen ':include :type=code gherkin')
![Alice in Wonderland](../_media/images/alice_with_cards-sm.jpg) 
 --->


# Sign-in and sign-up

Welcome to [Interfacer](https://interfacerproject.dyne.org/)! 

Learn how to sign up and sign in on the Interfacer platform. The sign-in page offers you three options: 
 - Sign up
 - Sign in: passphrase 
 - Sign in: answer questions


### Sign-up 

When signing up, you have to type in a valid email, your name and a username

![sign-up](../../_media/user-manual/screenshot_nru/nru_/sign_up.png)

#### Questions

Next, you need to answer as many (at least 3) of these 5 questions: it's important that you choose the questions and the answers carefully, as those can later be used to sign in the platform.

![sign-up](../../_media/user-manual/screenshot_nru/nru_/sign_up_challenges.png)


#### Passphrase

After typing your answers, the platform will return you a **mnemonic passphrase** that you should store somewhere safe as you can later use it for sign-in the platform (from the a different browser or device, or if your browser storage is deleted).

![sign-up](../../_media/user-manual/screenshot_nru/nru_/sign_up_passphrase.png)

## Sign-in for existing users

After you have created a user, you can sign in from a different device (or browser) 

- **Sign-in: passphrase** by entering your email and using your stored passphrase 

- **Sign-in: answer questions** if you don't have your passphrase, you can entering your email and answer to the questions in the same way you did when you first signed-up.




![intro](../../_media/user-manual/screenshot_nru/nru_/sign_in.png)



## Under the hood: sign-up process explained

The sign up process producess a set of crytpographic private and public keys, as well as a passphrase:
- The ***private keys*** are **stored in the browser storage** (and never communicated with the server)
- The ***public key*** is **communicated to the server**
- The ***passphrase*** is something you should to **store somewhere safe**

If the private key is not there (cause you are logging in from a different device/browser or you have deleted the history of your browser), **the passphrase can be used as a substitute to the private key** to sign-in the platform.

Behind the sign-up process is the cryptographic flow [Keypairoom](https://github.com/dyne/keypairoom/).


## Next step: add your first project!

By now you should be logged in, meaning you can create your first project. Click on the **Add Project** link on the left to read about it. 