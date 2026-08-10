# BRAINIALL IBAN validator contract

This small, provider-neutral contract keeps **IBAN format validation** separate from bank-account and payee verification.

The corresponding Apify Actor validates characters, country-specific length, and the ISO 13616 MOD-97 checksum inside the Apify run. It does not contact a bank, prove that an account exists, verify an account holder, perform Verification of Payee, screen sanctions, or authorize a payment.

## Safe evaluation

1. Start with the synthetic examples in `fixtures/synthetic-ibans.json`.
2. Confirm that every output keeps `accountExistsVerified`, `accountHolderVerified`, and `verificationOfPayeePerformed` set to `false`.
3. Use `examples/apify-input.json` for a bounded two-item run.
4. Review Apify input retention and access controls before using any real bank identifier.

The output dataset contains a mask and correlation fingerprint, not the full normalized IBAN. The Actor input is still stored by Apify as part of the run.

## Product route

- [Free browser-only preflight](https://www.brainiall.com/tools/iban-checksum-validator)
- [Apify Actor](https://apify.com/vivid_astronaut/iban-validator)
- [Format validation vs Verification of Payee](https://www.brainiall.com/guides/iban-validation-vs-verification-of-payee)

## Partner pilot

Accounts-payable, payroll, marketplace payout, and ERP integration teams can use issue #1 to request an opt-in pilot with synthetic fixtures. BRAINIALL does not accept tenant access or personal bank data for the discovery step.

## Identity

Maintained publicly as **BRAINIALL**. Do not include personal contact information in issues.
