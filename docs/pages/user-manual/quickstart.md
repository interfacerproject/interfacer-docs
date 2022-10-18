<!--- Future manual, page by page	
[](../_media/examples/zencode_cookbook/credential/credentialAnyoneVerifyProof.zen ':include :type=code gherkin')
![Alice in Wonderland](../_media/images/alice_with_cards-sm.jpg) 
 --->

# Intro

Welcome to Interfacer. 
On the landing page you can click on **sign in** to sign-in (if you haven't yet created a user) or sign-up.

![intro](../../_media/user-manual/screenshot_nru/nru_.png) 



# Sign-in

The sign-in page offers you three options: 
 - Sign up
 - Sign in: passphrase 
 - Sign in: answer questions

![intro](../../_media/user-manual/screenshot_nru/nru_/sign_in.png)


## Sign-up 

When signing up, you have to type in a valid email, your name and a username

![sign-up](../../_media/user-manual/screenshot_nru/nru_/sign_up.png)

### Sign-up questions

Next, you need to answer as many (at least 3) of these 5 questions: it's important that you choose the questions and the answers carefully, as those can later be used to sign in the platform.

![sign-up](../../_media/user-manual/screenshot_nru/nru_/sign_up_challenges.png)


### Sign-up passphrase

After typing your answers, the platform will return you a **mnemonic passphrase** that you should store somewhere safe as you can later to use it sign-in the platform (from the a different browser or device, or if your browser storage is deleted).

![sign-up](../../_media/user-manual/screenshot_nru/nru_/sign_up_passphrase.png)

## Sign-in for existing users

After you have created a user, you can sign in from a different device (or browser) 

- **Sign-in: passphrase** by entering your email and using your stored passphrase 

- **Sign-in: answer questions** if you don't have your passphrase, you can entering your email and answer to the questions in the same way you did when you first signed-up.

## Under the hood: sign-up process explained

The sign up process producess a set of crytpographic private and public keys, as well as a passphrase:
- The ***private keys*** are **stored in the browser storage** (and never communicated with the server)
- The ***public key*** is **communicated to the server**
- The ***passphrase*** is something you should to **store somewhere safe**

If the private key is not there (cause you are logging in from a different device/browser or you have deleted the history of your browser), **the passphrase can be used as a substitute to the private key** to sign-in the platform.

Behind the sign-up process is the cryptographic flow [Keypairoom](https://github.com/dyne/keypairoom/).





# Assets

New assets can be manually created, imported, or claimed. Existing assets can be searched. 

## Create asset

You can currently create an asset manually (or claim it from the ones imported from LOSH, see below). It's important to fill all the required fields:

![create-asset](../../_media/user-manual/screenshot_ru/create_asset.png)

## Asset page 

The asset page contains all the information about the asset, including: 
 - Name
 - Location
 - Screenshot
 - (more to come)

![asset](../../_media/user-manual/screenshot_ru/asset/061P0XBBP4CXZ3A9T57QA3ZJ9M.png)


## My assets

Your list of assets can be found in the **Assets > My assets** submenu. Your assets can be filtered and searched. You can open an asset by clicking onto its name.

![asset](../../_media/user-manual/screenshot_ru/profile/my_profile.png)


## Latest assets

In **Assets > Latest assets** you can find the list of all the assets in the platform, sorted chronologically. The assets can be searched and filtered.

![asset](../../_media/user-manual/screenshot_ru/assets.png)

## Imported from LOSH

In **Assets > Imported from LOSH** you can find all the assets imported from [https://losh.opennext.eu/](https://losh.opennext.eu/). You can claim your assets and added to your asset list.

![asset](../../_media/user-manual/screenshot_ru/resources.png)


# Report a bug

You can report a bug by creating an **issue** on the [interfacer-gui](https://github.com/dyne/interfacer-gui/issues/new) repo.


