<h1 align="center">
  <br>
  <a href="http://www.deltadevs.xyz"><img src="https://www.deltadevs.xyz/deimos-logo1.png" alt="DEIMOS" width="300"></a>
  <br>
  <h4 align="center">Blockchain-Enhanced, Rust-Implemented Transparency Dictionary for Secure, Trustless Data Management and Communication.</h4>
  <br>
</h1>

<div align="center">

[![delta devs - building in stealth](https://img.shields.io/badge/building-in_stealth-E58E36)](https://deltadevs.xyz)
![Dependencies](https://img.shields.io/badge/dependencies-up%20to%20date-E58E36.svg)
[![GitHub Issues](https://img.shields.io/github/issues-raw/deltadevsde/transparency-dictionary?color=E58E36)](https://github.com/deltadevsde/transparency-dictionary/issues)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-E58E36.svg)
[![License](https://img.shields.io/badge/license-MIT-E58E36.svg)](https://opensource.org/licenses/MIT)
  
</div>

# Deimos: Transparency Dictionary - Rust Implementation

## 🌕 Overview

This project is a Rust-based implementation of a Transparency Dictionary, strongly inspired by descriptions in [Tzialla et. al](https://eprint.iacr.org/2021/1263.pdf). It offers a secure, scalable solution for managing a label-value map in environments where the service maintaining the map is not completely trusted. The system ensures the integrity and authenticity of operations using cryptographic proofs.

## 🌖 Features 

-	Robust Security: Leverages indexed Merkle trees and zkSNARKs to protect against unauthorized data modifications.
-	Efficient Verification: Offers O(log n) proofs of membership/non-membership ensuring minimal verification time.
-	Scalability: Optimized for large-scale applications, capable of managing millions of labels with low overhead.
-	Rust-Based: Implemented in Rust, offering strong memory safety and performance benefits.

## 🌗 Goals

Here are the key objectives that are driving the current development of our project:

1. Versatile utility: Development of a highly versatile application that ensures data security and automatic verifiability. Our focus is on developing a tool that remains trustworthy even when operated by untrusted providers.

2. Decentralized trust: Implementing a system where trust is decentralized. By using transparency dictionaries such as Deimos, we want to ensure secure and transparent operation, regardless of the trustworthiness of the service provider.

3. Improving light clients: The use of light clients is to be improved by integrating them into the front end using WebAssembly (Wasm). This will allow both web and app applications to utilize the capabilities of Deimos and bridge the gap between traditional web (Web2) and blockchain-based applications (Web3).

4. Security and privacy for Web2 and Web3 applications: By incorporating the features of Deimos, we plan to improve the security and privacy aspects of Web2 and Web3 applications. This is in line with our goal to provide robust data protection for both private and commercial users across different platforms.

5. Maximizing privacy: Our ultimate goal is to maximize privacy for users of all kinds. We aim to create a framework that not only secures data, but also respects and upholds user privacy.

## 🌘 Status

The project is still in the development phase and is not yet suitable for use in production environments.

We have already implemented working zkSNARKs, but are focusing on optimizing the computations within the circuits and making general improvements to the structure of the zkSNARKs code. In addition, we are experimenting with different methods of posting on public ledgers such as blockchains (e.g. Celestia) and exploring the feasibility and effectiveness of P2P solutions consisting solely of transparency dictionaries such as Deimos.

Due to this ongoing development work, changes are still being made that may affect existing functionalities.

The system has not yet been audited for security reasons and should therefore not yet be used in production environments.

We will continuously update the documentation to reflect the completion status of each component. Additionally, we will be adding more contribution notes, including design documents, architecture diagrams, repository layouts and good first issues.

We thank you for your patience and will be happy to answer any questions.

## 🌑 Usage

TBD ... something like "The library is designed to be user-friendly, with clear APIs for interacting with the transparency dictionary. Example code snippets are provided to demonstrate basic operations like adding, retrieving, and verifying entries."
<br/>
lets demonstrate our application here because it could look nice with some pics


## 🌒 Installation

### Prerequisites

To use this project, you need a working database. A reference implementation with Redis is supported. The use of a data availability layer is also required. A reference implementation with Celestia is available for this project, which is a very cost efficient and lightweight blockchain solution and on which the cryptographic commitments and the zero-knowledge proofs are posted and verified by light clients. We are planning further reference implementations; for the moment, we are showing the process and installation of the existing implementations and, based on this, the launch of Deimos.

### Install Redis

Redis serves as a powerful in-memory database that is used to store the label-value pairs. Follow these steps to install Redis:

1. Download Redis from [Redis Download Page](https://redis.io/download/).
2. Follow the installation instructions for your operating system.

You don't have to start redis on your own, Deimos is doing that job for you.

### Install Celestia

A DA layer such as Celestia is an important component for data security and availability. It stores the cryptographic commitments and parameters of the zkSNARKs and ideally enables them to be verified. Follow the instructions [here](https://github.com/rollkit/local-celestia-devnet) to deploy a local testnet.

### Starting the sequencer

If redis is installed and the local devnet is running, Deimos can be started. Deimos can be started in two different ways, as a sequencer (which creates the proofs later on;TODO: more info and link to documentation needed) or as a lightclient (to verify the proofs posted on Celestia using the cryptographic commitments). To start the sequencer, run the following command:

```bash
cargo run sequencer
```

to start the light-client, run the following command:

```bash
cargo run light-client
```

You can then interact with Deimos via the interfaces defined in [webserver.rs](https://github.com/deltadevsde/deimos/blob/main/src/webserver.rs). Based on the data exchanged or stored via the interface the global indexed merkle tree changes and proofs based on these changes then are created in defined epochs (currently 60 seconds) and cryptographic commitments including the proof parameters are posted in the Celestia namespace.

## 🌓 Contributions

Contributions are welcome! I saw a lot of contribution guidelines so we need some and write: "Please refer to our contributing guidelines for information on how to submit pull requests, report issues, and contribute to the codebase."

## 🌔 Documentation

Link to comprehensive documentation, including API reference, design philosophy, and more detailed examples. Should we link other papers that inspired us here?


## 🌕 Last Heading

yaay reached deimos fullmoon again
