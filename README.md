# Passwords

Use the official iCloud Passwords extension in Google Chrome as a blind autofill
path. The assistant operates the surrounding interface while saved passwords,
passkeys, and website verification codes stay outside its context.

Install `apple-passwords@package-manager` in Codex or Claude. This skill needs
macOS, the official extension, and the host's Chrome/native UI tools. The
optional approved native Passwords unlock uses `macbook@package-manager`; Claude
installs that dependency, and other hosts must make its broker available before
using that lane. No credential is bundled or requested by this plugin.

Optional private host observations belong in `~/.config/apple-passwords/preferences.md`
or a file selected by `APPLE_PASSWORDS_PREFERENCES_PATH`. Preferences do not
authorize authentication or bypass challenges. The skill preserves each exact
challenge and distinguishes autofill from authorized submission.

Run `npm test` for package validation. No authentication or credential access is
part of that check. See `PROVENANCE.md`, `ICON-SOURCES.md`, and `LICENSE`.
