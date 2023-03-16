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

# Intro

Welcome to the documentation of Fab City Os core platform, one of the main components of the [Interfacer project](https://interfacerproject.eu).

This platform provides innovative tools to support the complexity of a distributed accounting system for flexible collaboration processes, it leverages crypto technology to empower participants with privacy, transparency and data ownership and can be adopted to implement fair and equitable compensation mechanisms.


## Technical features

Internal modules use well-established open-source tools like PostreSQL and Tarantool, among the languages we used, the most used are C, Typescript, Golang, Elixir and Lua. The
modular architecture allows for load distribution, and every single component is tuned to perform
well even on low-power hardware and, in some cases, ARM64 boards like the Raspberry Pi4. In all
cases, the Linux kernel and GNU tools are used where necessary.

#### Cryptography and privacy
* The sign in/up flow of Fab City OS is managed by the [Zenflows-crypto](/pages/zenflows-crypto) scheme: 
  - Each operation performed by the user is signed using the [EDDSA](https://datatracker.ietf.org/doc/rfc8032/) scheme with the user's private key, which are **never communicated to the server**. The server knows only the public keys of each user, so in case of a server-side security breach, the hackers will not be able to impersonate any user. 
  - The user's keyring is generated at sign-up based on the user's answers to a set of security questions.
  - Based on the user's answers to the security questions, a seed as [mnemonic passphrase](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) format is printed out, the seed can be used to recreate the private keys and sign in from the same device or a different one. 
  - In case the seed is lost, it can be recreated by answering the security questions again.

#### GraphQL and Valueflows
* Fab City OS uses [GraphQL](https://graphql.org/) to store and retrieve information in the back end: the front end communicates with the back end via *GraphQL mutations* instead of web APIs, which makes the development more lean and enables third parties to easily create applications that communicate with the back end.
* The data is modeled using the [Valueflows](https://www.valueflo.ws/): an ontology designed to facilitate internetworking of software projects that handle economic transactions.

#### Distributed caching and sharding
* Fab City OS uses [Zenswarm-storage](/pages/zenswarm-storage.md) as a distrbuted caching and sharding engine for images, documents and information. Designed to work as CDN, it can scale easily and deliver data faster. 

#### W3C-DID 
* Users' digital identities (DID) are stored and distributed using the [W3C-DID](https://www.w3.org/TR/did-core/) standard. For each user a W3C-DID document is stored: the document contains no private or sensitive information about the user (no name, email or other) making the whole platform GDPR compliant by design.
* The DIDs are produced, and can be resolved, using Dyne.org's open source [W3C-DID method](https://new.dyne.org/W3C-DID/#/), which is registered in the [W3C-DID method list](https://www.w3.org/TR/did-spec-registries/#did-methods).

#### Blockchain and DPP
* Users' DIDs as well as the DIDs of all the software infrastructure, are stored on blockchain
* Transactions between users are also stored on blockchain
* For any asset created or modified in FabCityOS, a Digital Product Passport (DPP) can be created: each DPP contains the  history of the asset (up the DPP creation time), is stored on blockchain and can be verified on the platform, or by third parties, using a link or a QR code.

#### Import from git or LOSH
* Assets on FabCityOS can be created manually or by importing them from git repositories or from the [LOSH](https://losh.opennext.eu/) database.
-------------------
-------------------


## Components

List of the component stack that power FabCityOS.

#### Back end

* [Zenflows](/pages/zenflows.md):a tool to leverage commons-based peer production by documenting and monitoring the life cycle of products. Written in Elixir, stores data in [GraphQL](https://graphql.org/) using the [Valueflows](https://www.valueflo.ws/) ontology.
* [Zenswarm-storage](/pages/zenswarm-storage.md): a distrbuted caching and sharding engine, powered by Tarantool  
<!-- * [Fabchain](/pages/fabchain.md): a bloat-free toolbox to create and operate new blockchains based on ethereum technology --> 
* Dyne.org's [W3C-DID method](https://new.dyne.org/W3C-DID/#/): stores DID of users and services in a machine readable interchange format, based on privacy by design principles.
* [Zenflows-proxy]: a public Internet gateway service that acts as a proxy to route information flows to each of the back-end services, enabling a secure, modular, and scalable deployment architecture.

#### Front end

* [Interfacer-GUI](/pages/interfacer-gui.md): a Progressive Web App (PWA) acting as Graphical User Interface (GUI) and crypto wallet (end-to-end crypto) for Fab City Os 

<!--
* **Loshifacer** [... learn more about Loshifacer](/pages/loshifacer.md)
-->

#### Sub-modules and sub-components

* [Zenflows-crypto](/pages/zenflows-crypto): library of cryptographic schemes, used in the back end and front end of FabCityOS written in [Zencode](https://decodeproject.eu/blog/smart-contracts-english-speaker.html) and powered by [Zenroom](https://zenroom.org/).
* [Zenroom](https://zenroom.org/): multiplatform cryptographic virtual machine and smart contract executor. It can be programmed using the English-like DSL [Zencode](https://decodeproject.eu/blog/smart-contracts-english-speaker.html), designed to be readable by non-programmers. 
* [Restroom-mw](https://new.dyne.org/restroom-mw/#/): nodeJS based collection of middlewares, that expose Zencode smart contracts to Web APIs and expand the Zencode language.
-------------------
-------------------



## Playgrounds

* **FabCityOS**: 
  - [Front end (staging)](http://interfacer-gui-staging.dyne.org)
  - [Back end (staging)](http://65.109.11.42:8000/api/)
<!-- * **FabChain**:
  - [RPC server](http://test.fabchain.net:8545)
  - [Faucet](https://test.fabchain.net:5000)
  - [Blockchain Explorer](https://test.fabchain.net:8000) -->
* [Apiroom](https://apiroom.net/): Zenroom smart contracts IDE	
