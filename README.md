# PayWall.NetCore

C# client code for integrating with the PayWall payment orchestration API, with an ASP.NET Core example application.

The checked-in library targets `net5.0`, `net6.0`, `net7.0`, and `net8.0`. These are project targets, not a statement that every runtime is still supported or that the current PayWall API has been verified against this checkout.

## Installation

The existing package identifier is `PayWall.NetCore`:

```sh
dotnet add package PayWall.NetCore
```

The project metadata references [intranettechnology/PayWall.NetCore](https://github.com/intranettechnology/PayWall.NetCore). Verify the package publisher and source correspondence before treating a downloaded package as a build of this repository.

## API areas documented by the project

| Area | Operations |
| --- | --- |
| Stored cards | Register, list, update, and delete cards. |
| Members | Create, update, delete, and search members. |
| Member bank accounts | Add, update, delete, and list bank details. |
| Member settlement and commission | Read and update settings. |
| Payments | Direct (2D) and secure (3D) payments, authorization, installment and BIN inquiries. |
| Reconciliation | Reconcile virtual POS transactions, retrieve results, list reconciliations, and retrieve end-of-day data. |
| Payouts | Check balances, transfer to an IBAN or account, and query transfers or accounts. |
| Recurring payments | Create, update, query, stop, delete, and restart recurring payments; manage associated cards, customers, and products. |
| Link and QR payments | Create payment orders. |
| Checkout | Create a shared checkout page and query a payment. |
| Alternative payment methods | Initiate direct, OTP, QR, or checkout flows; query payments; request full or partial refunds. |
| Card issuance | Create virtual or physical cards, manage status and balance, and query or update card details. |

Consult the current provider documentation and the client implementation for endpoint-specific support. This list is an overview, not a compatibility guarantee.

## Configuration

The client uses a `PayWall` configuration section with `Prod`, `PublicClient`, `PublicKey`, `PrivateClient`, and `PrivateKey` fields. Obtain the corresponding values from the provider's integration settings.

```json
{
  "PayWall": {
    "Prod": false,
    "PublicClient": "",
    "PublicKey": "",
    "PrivateClient": "",
    "PrivateKey": ""
  }
}
```

Supply credentials through your application's secret configuration, such as environment variables or .NET user secrets. Do not commit working credentials. `Prod: false` selects the test environment in the existing configuration model.

## Repository layout

- `src/PayWall.NetCore`: client library.
- `src/PayWall.NetCore.Example`: example application.
- `PayWall.NetCore.sln`: solution.

The repository currently has no GitHub Actions workflow or dedicated automated test project. Validate changes in the provider's test environment before considering production use.

## Reference links

- [PayWall developer documentation](https://developer.paywall.one/)
- [PayWall website](https://paywall.one/)
- [Test dashboard](https://dev-panel.itspaywall.com/)
- [Production dashboard](https://panel.itspaywall.com/)

## License

See the repository's [LICENSE](LICENSE). Package metadata and upstream provenance should be reconciled before publishing a new package from this repository.
