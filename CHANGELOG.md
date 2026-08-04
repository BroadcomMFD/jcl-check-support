# Change Log

All notable changes to the "JCL Check" extension will be documented in this file.

## Recent Changes

- Refine VS Code behavior for user profile execution.
- Update JCLCheck scan logic to handle non-standard JCL return codes.
- Additional messages for non‑standard maximum severity code and non-zero JCLCheck codes are written to the `Output` view under the `JCL Check` channel.
- Enable JCLCheck Features by default.
- Security updates.
- Updates dependencies to maintain technical currency
- Remediates CVE-2026-33228
- Remediates CVE-2026-4800
- Remediates CVE-2026-29786
- Remediates CVE-2026-24842
- Remediates CVE-2026-2327
- Remediates CVE-2026-24001
- Remediates CVE-2026-26996
- Remediates CVE-2026-27601
- Remediates CVE-2026-27903
- Remediates CVE-2026-27904
- Remediates CVE-2026-26960
- Remediates CVE-2026-32141
- Remediates CVE-2026-33750

## `3.0.3`

- Vault Configuration and library updates.

## `3.0.2`

- Updated the `ProfilesLoader` class to reuse the cache from Zowe Explorer if the user has it installed. Otherwise, the extension continues to use its own instance of the `ProfileInfo` class to access/manage Zowe profiles.
- Fixed an issue where the user was prompted to enter in credentials after already responding to the same prompts from the Zowe Explorer extension. Now, once the user has entered in their credentials through Zowe Explorer, the JCL Check extension reuses those credentials and no longer prompts the user.
- Changes for Code4z related documentation.

## `3.0.1`

- Updated README and documentation.

## `3.0.0`

- Renamed the extension to JCL Check from JCL Language Support
- Added dependency of JCL Language Support for basic JCL syntax highlighting, coloring and generating code snippets.
- Added support for Zowe V3
- Support for Zowe Explorer

## `2.0.0`

- Added support for Zowe v2 team config profiles.

## `1.0.1`

- Updated packages fixing vulnerabilities

## `1.0.0`

- Add support for base profiles
- Add support for SSO and Token Login via Zowe API Mediation Layer
- Add the Common Reports to the markdown report generator
- Fix incorrect parsing of empty inline DDs and multiline EXEC statements

## `0.1.0`

- Initial release
- Add the ability to lint JCL by issuing a command
- Add the ability to lint JCL by manually saving
- Add the ability to generate JCLCheck reports
- Add the ability to use JCL snippets
