# thirdweb go starter

This is a starter project for a web server written in Go. It uses the [Gin](https://gin-gonic.com/) framework.

## How it works

The server is written in Go and uses the Gin framework. It has a single endpoint, `/generate`, which takes a JSON body with a `address` field and returns a signed payload for signature minting an ERC-721 token.

## How to set it up

1. Install Go if you haven't already. You can find instructions [here](https://golang.org/doc/install).
2. Create a new project by cloning this repository and renaming the folder.
3. Export your wallet private key from your wallet and add it to the .env file.

```bash
PRIVATE_KEY=your_private_key
```

Using private keys as an env variable is vulnerable to attacks and is not best practice. We are doing it in this guide for the sake of brevity, but we strongly recommend using a [secret manager to store your private key](https://portal.thirdweb.com/typescript/sdk.thirdwebsdk.fromwallet).

## How to run it

1. Run `make run` to start the server.
2. The starter will be running on `localhost:8080`.
3. You can test the endpoint by sending a POST request to `localhost:8080/generate` with a JSON body containing an `address` field.

## How to make a request

To make a request you can use any HTTP client. Using the client create a `POST` request to `localhost:8080/generate` with a JSON body containing an `address` field. Once you make the request you should receive a response with a signature like this:

```json
{
  "signedPayload": {
    "payload": {
      "to": "0x39Ab29fAfb5ad19e96CFB1E1c492083492DB89d4",
      "price": "0",
      "currencyAddress": "0x0000000000000000000000000000000000000000",
      "mintStartTime": 0,
      "mintEndTime": 0,
      "primarySaleRecipient": "0x0000000000000000000000000000000000000000",
      "royaltyRecipient": "0x0000000000000000000000000000000000000000",
      "royaltyBps": 0,
      "uri": "ipfs://QmdHHJFHjGsqnBNY1qYMh4v15TM4Bwg1Fp8AHfzVyQojdM/0",
      "uid": [
        0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 251, 227, 111, 80, 61,
        117, 69, 188, 148, 117, 146, 193, 213, 158, 239, 226
      ]
    },
    "signature": "0x136f84d347a4cccd84a391d5ab517791f73d9142342c6ea30a39369063246bcc217af35c6987701936a87499f97eaf0fcf9247277bb6ac30f8df3ef572ea79641b"
  }
}
```

## Learn More

To learn more about thirdweb and Next.js, take a look at the following resources:

- [thirdweb go Documentation](https://docs.thirdweb.com/go) - learn about our Go SDK.
- [thirdweb Portal](https://docs.thirdweb.com) - check our guides and development resources.

You can check out [the thirdweb GitHub organization](https://github.com/thirdweb-dev) - your feedback and contributions are welcome!

## Join our Discord!

For any questions, suggestions, join our discord at [https://discord.gg/thirdweb](https://discord.gg/thirdweb).
