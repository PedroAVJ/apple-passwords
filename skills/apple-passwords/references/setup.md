# Portable setup

Apple Passwords requires macOS, the official iCloud Passwords Chrome extension,
and a supported Chrome/native UI integration supplied by the host. The official
extension ID is `pejdijmoenmkgeppbflobdenhhabjlaj`; verify the installed extension
and visible challenge rather than assuming a particular version or profile.

A native Passwords unlock can use the separate `macbook@package-manager` plugin
when its broker exposes `credential_status`, `inspect_credential_target`, and
`authorize_and_fill_credential`. The only supported alias is `macos-login` and
the only permitted target for this skill is `passwords-unlock`. Broker setup and
one-time human authorization stay with that plugin. Never collect or import a
Mac password through this skill.

No Chrome profile, extension toggle, credential alias configuration, current
pairing state, or account is assumed to exist. Keep personal choices in the
optional external preferences file and reverify observations that can drift.
If a required tool or authorized pairing surface is unavailable, preserve the
challenge and report the exact missing component. Do not substitute secret
extraction, manual token copying, or account recovery.
