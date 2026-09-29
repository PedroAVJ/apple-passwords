# Apple Passwords

Use saved credentials without exposing them to the assistant.

## Skills

| Skill | Purpose |
| --- | --- |
| `autofill` | Fill saved logins in Chrome through the official iCloud Passwords extension. Website verification follows the normal authorized login workflow. |
| `credential-authorization` | Fill the Mac login password once, after human approval, into a signed native secure dialog through the bundled `macbook-credential-broker` MCP server. |

Install `apple-passwords@package-manager` in Codex or Claude. Run `npm test` to validate the package.

## Credential broker

The broker is deliberately narrower than a password manager. It owns one fixed
alias, `macos-login`, and exposes presence, target inspection, one-time approval
plus fill, and synthetic verification. There is no read, reveal, export, copy,
or unattended-fill operation.

It fills only a native secure field inside a signed allowlisted dialog, rejects
web-page password fields, re-verifies the target after approval, and never
presses Return. The stable helper lives under
`~/Library/Application Support/MacBookCredentialBroker`; its Keychain item uses
service `com.pedroavj.macbook.credential-broker` and is created through a native
secure provisioning dialog, never through chat or a shell argument. These
identities are unchanged from the retired `macbook` plugin, so an existing
provisioned alias keeps working.

`npm test` covers the contract, signature, and MCP approval path. Set
`CREDENTIAL_BROKER_LIVE_TESTS=1` to also run the synthetic Keychain self-test and
the Codex app-server path, which create and delete a temporary Keychain item and
show the broker's own test window.

Newly installed MCP tools become available in fresh Codex or Claude tasks.
