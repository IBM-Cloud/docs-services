---

copyright:

  years:  2020

lastupdated: "2020-06-29"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About CRYPTOENTER - Blockchain based infrastructure for digital banking + social network
{: #gettingstarted}

Keyes for Hyperledger: the organization on its side creates a private key in accordance with the requirements of Hyperledger (encryption algorithm, key length, required fields), signs it in its certification center and gives us the public key of its CA and the certificate signed by it. We enter these keys into the channel blocks on the order.

{:shortdesc}

## Getting started

Keys for the backend: the organization creates on its side a pair - a private and public key.
the public key is transferred to us, we save it in Hyperledger. Next, the organization creates nodes for peers, ui and his backend.

Cryptoenter gets access, including to its private keys of peers and backends. Cryptoenter registers the public keys of the organization in Hyperledger and provide an API for working with Hyperledger and wallets.

A third-party organization independently connects the peers to the channels, configures ui and backend.

