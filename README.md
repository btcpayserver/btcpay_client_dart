# BTCPay client library for Dart

[![pub package](https://img.shields.io/pub/v/btcpay_client.svg)](https://pub.dartlang.org/packages/btcpay_client)

This client takes care of communications to a BTCPay server. This is heavily
dependent on PointyCastle but eschews reflection so it can be used in Flutter.

This is not a complete library. Pairing and creating invoices is supported but 
other endpoints are not. Note that most of the heavy lifting is done. The 
generation of the SIN and the signing of requests.

## Installing

Add it to your `pubspec.yaml`:

```
dependencies:
  btcpay_client: ^0.1.2
```

## Getting Started

Have a look in the [`example`](example) directory for several examples.

Creating a client is done by passing a URL on which to reach your BTCPay server 
and either a `BigInt` or a 
[`AsymmetricKeyPair`](https://pub.dartlang.org/documentation/pointycastle/1.0.0-rc4/pointycastle.api/AsymmetricKeyPair-class.html).

```dart
var client = Client.fromBarePrivateKey("url-to-btcpay-server", someBigInt);
await client.createInvoice(10.0, "EUR");
```

## Tests

```
$ pub run test
```

## Licence overview

All files in this repository fall under the license specified in 
[COPYING](COPYING). The project is licensed as [AGPL with a lesser 
clause](https://www.gnu.org/licenses/agpl-3.0.en.html). It may be used within a 
proprietary project, but the core library and any changes to it must be 
published online. Source code for this library must always remain free for 
everybody to access.
