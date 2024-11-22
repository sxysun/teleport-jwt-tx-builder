# Teleport x ZK-JWT

What happens when you put Teleport.best NFTs together with zk-JWTs? You get Blind but natively on Twitter.

## ZK-JWT

ZK-JWT is an application that allows for anonymous verification of JWT signatures while masking specific claims. It enables verification of JWTs from specific issuers or subsets of domains, as well as verification based on specific claims in the payload. Our core SDK comes with libraries to assist with circuit generation and utility templates for building zero-knowledge JWT applications.

## Packages Overview

ZK-JWT consists of two core packages:

### @zk-jwt/circuits

Zero-knowledge circuits for JWT verification, including RSA signature validation and anonymous domain verification. [Read more](/packages/circuits/README.md).

### @zk-jwt/helpers

TypeScript utilities for generating circuit inputs, handling JWTs, and managing public keys. [Read more](/packages/helpers/README.md).

### @zk-jwt/contracts

Solidity contracts for on-chain verification of ZK proofs. [Read more](/packages/contracts/README.md).

## Demo

We've built a demo application that uses ZK-JWT to verify Google Sign-In JWTs.

Try it here: [jwt.zk.email](https://jwt.zk.email)

## Contributing

We welcome contributions! For each merged PR addressing an [open issue](link-to-issues), we offer a $50 reward. See our [Contributing Guide](Contributing.md) for details.

## Audits

This project has not yet been audited. Not intended for production use.

## Licensing

Everything we write is MIT-licensed. Note that circom and circomlib is GPL. Broadly we are pro permissive open source usage with attribution! We hope that those who derive profit from this, contribute that money altruistically back to this technology and open source public goods.
