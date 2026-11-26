---
title: "1Password"
subtitle: "Toronto-based encrypted password manager and dual-key vault service"
canonical_url: https://mimirwiki.com/wiki/1password
language: en
page_class: entity
revision_sha256: 882358415d4609d5a8510b0ecebd40fb1e77c0a7bf18b389eaa3668c196083a6
date_modified: 2026-11-26
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 6
alternates:
  md: https://mimirwiki.com/wiki/1password.md
  txt: https://mimirwiki.com/wiki/1password.txt
  json: https://mimirwiki.com/wiki/1password.json
  jsonld: https://mimirwiki.com/wiki/1password.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/1password
---

# 1Password

> 1Password is a dual-key encrypted password manager. Following an intrusion detected on 2026-11-19 via a compromised employee GitHub account, 1Password disclosed on 2026-11-25 that names, sign-in emails, identifiers, and public keys for a subset of customers were copied, while encrypted vault contents and decryption keys remained unaffected.

1Password is a password management service developed by Toronto-based 1Password that protects stored credentials using a dual-key encryption architecture combining a user's account password and a device-generated 34-character Secret Key. On 2026-11-25, 1Password disclosed a backend security incident detected on 2026-11-19 in which an attacker copied limited account metadata from a subset of customers, while stating that customer vaults, items, passwords, and Secret Keys were unaffected.

**Also known as:** 1Password Password Manager

## Key facts

- **Headquarters:** Toronto, Canada [4]
- **Encryption architecture:** Dual-key model combining user account password and device-created 34-character Secret Key [2]
- **Nov 2026 incident timeline:** Detected 2026-11-19; publicly disclosed 2026-11-25 (as of 2026-11-26) [4]
- **Vault impact (company statement):** Encrypted vault data, items, passwords, and Secret Keys were not affected; watch for phishing (as of 2026-11-26) [1]

## Basic facts

- **Product name:** 1Password [1]
- **Base:** Toronto, Canada [4]
- **Security model:** Dual-key end-to-end encryption (Account Password + 34-character Secret Key) [3]
- **Nov 2026 attack vector:** Compromised employee corporate GitHub account used to push malicious backend code [4]
- **Affected data:** Limited account metadata for a subset of customers (names, emails, IDs, timestamps, public keys, SRP parameters) [5]
- **Recommended user action:** No account update required; stay alert for phishing emails [1]

## 1Password overview and dual-key encryption model

1Password is a password manager operated by Toronto-based 1Password that uses a dual-key security model so only the user holds the keys needed to decrypt vault data.[2][4] Every account pairs a user-chosen account password with a unique 34-character Secret Key generated on the user's device and stored in their Emergency Kit.[3]

According to 1Password Support, the company holds no record of a customer's Secret Key and cannot recover it, meaning 1Password itself cannot decrypt items stored inside customer vaults.[1][3]

## 1Password November 2026 backend security incident

1Password disclosed on November 25, 2026, that an attacker gained access to some of its backend systems and copied a limited amount of customer account information from a subset of customers.[1] TechCrunch and MacRumors reported that 1Password detected the intrusion on November 19, 2026, after an attacker compromised an employee's corporate GitHub account and used it to access source code and push malicious code to backend services.[4][5]

According to 1Password and MacRumors, the copied records included customer names, sign-in email addresses, account and user identifiers, account creation and last sign-in timestamps, public keys, and Secure Remote Password (SRP) protocol parameters.[1][5] As of November 26, 2026, the total number of affected customers and any independent third-party audit findings have not been publicly disclosed.[1][6]

## 1Password vault safety, remediation, and phishing warning

1Password stated in its November 25, 2026 disclosure that customer vault data, stored items, account passwords, and Secret Keys were safe and were not affected because 1Password does not have access to customer passwords or Secret Keys.[1]

The company reported that it implemented containment measures, restored clean versions of the affected service, and triggered a rotation of internal credentials.[1] 1Password advised customers that they do not need to update anything in their accounts, but warned them to remain cautious of targeted phishing attempts such as unexpected 1Password invitations or account recovery emails.[1]

## 1Password November 2026 incident scope and open questions

1Password stated that only a subset of customers had limited account metadata copied during the November 2026 backend intrusion, and noted that Secure Remote Password (SRP) parameters cannot be used directly to access accounts.[1][5] As of November 26, 2026, 1Password has not published the total count of affected customer accounts, and no independent third-party audit report has been publicly released.[1][6]

## Frequently asked questions

### Were customer passwords or vault items compromised in the November 2026 1Password incident?

1Password stated on November 25, 2026, that customer vault data, stored items, account passwords, and Secret Keys were safe and not affected, as 1Password does not have access to those decryption keys. [1][4]

### What customer account information was accessed in the November 2026 incident?

1Password and MacRumors reported that copied records for a subset of customers included names, sign-in email addresses, account and user identifiers, creation and last sign-in times, public keys, and Secure Remote Password (SRP) protocol parameters. [1][5]

### How did the attacker gain access to 1Password's backend systems?

According to TechCrunch and MacRumors citing 1Password's disclosure, the intrusion was detected on November 19, 2026, after an attacker compromised an employee's corporate GitHub account and pushed malicious code to backend services. [4][5]

### Do 1Password users need to change their master password?

1Password stated that users do not need to update anything in their 1Password accounts, but should watch out for phishing emails impersonating 1Password invitations or account recovery requests. [1]

## Quotable sentences

- 1Password uses a dual-key encryption model pairing a user's account password with a device-generated 34-character Secret Key that 1Password does not store. [2][3]
- On 2026-11-25, 1Password disclosed a backend incident detected on 2026-11-19 in which an attacker compromised an employee's corporate GitHub account and pushed malicious code to backend services. [1][4][5]
- 1Password stated that limited account records for a subset of customers (including names, sign-in emails, IDs, timestamps, public keys, and SRP parameters) were copied, while encrypted vaults, items, passwords, and Secret Keys were unaffected. [1][5]
- 1Password reported rotating internal credentials and restoring clean services, advising customers that no account changes are required while warning against phishing emails. [1]

## Sources

1. Update on a security incident involving 1Password's backend systems. 1Password Blog. published 2026-11-25. https://1password.com/blog/update-on-nov-2026-security-incident (checked 2026-11-26; tier 3: official site)
2. Password Security Manager: Key Principles. 1Password. https://1password.com/security (checked 2026-11-26; tier 3: official site)
3. About your Secret Key. 1Password Support. https://support.1password.com/secret-key-security/ (checked 2026-11-26; tier 3: official site)
4. 1Password said hackers broke into its internal systems, but customer passwords are safe. TechCrunch. published 2026-11-25. https://techcrunch.com/2026/11/25/1password-said-hackers-broke-into-its-internal-systems-but-customer-passwords-are-safe/ (checked 2026-11-26; tier 2: academic or news)
5. 1Password Security Breach: What Was Accessed and What Wasn't. MacRumors. published 2026-11-25. https://www.macrumors.com/2026/11/25/1password-security-breach/ (checked 2026-11-26; tier 2: academic or news)
6. 1Password Hacked, Customer Data and Source Code Stolen in GitHub Account Breach. The Hacker News. published 2026-11-26. https://thehackernews.com/2026/11/1password-hacked-customer-data-and.html (checked 2026-11-26; tier 2: academic or news)

## Cite this page

Mimirwiki. "1Password." Version 88235841, 2026-11-26. https://mimirwiki.com/wiki/1password
