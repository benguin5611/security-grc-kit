---
Artefact type: Reference
Owner role: Security/GRC lead (Information Security Manager or equivalent), or whoever holds the key
Review cadence: Annually, and on every key renewal
Version: 1.0 (template)
---

# Managing and using PGP keys for security researchers

> Part of the [security-docs-kit](../../README.md#before-you-rely-on-anything-here), a starting point for a lean security/GRC function rather than a certified or audit-ready control out of the box. Read that disclaimer and this artefact's own "Adapt this to your context" section before relying on it.

The full lifecycle and operational use of a PGP key for security-vulnerability disclosure: creation, renewal, publication, secure distribution, and decryption, plus ownership and hosting responsibilities.

## Creating a new PGP key

### Ownership and authority

Assign clear ownership of the key to a named individual. All updates to the key should happen on their device; a new key pair may be created if that ownership changes.

### Step 1: Install GnuPG

```bash
brew install gnupg
```

Verify:

```bash
gpg --version
```

### Step 2: Generate the key

```bash
gpg --full-generate-key
```

When prompted:

| Prompt | Value |
| --- | --- |
| Key type | `1` (RSA and RSA) |
| Key size | `4096` |
| Expiry | `1y` (renewable annually) |
| Real Name | The key owner's name |
| Email | Your security-reporting address, e.g. `security@yourdomain.com` |
| Comment | `Vulnerability disclosure reporting` |

Confirm with `O` for Okay, then set a strong, unique passphrase and store it in your password manager immediately.

### Step 3: Find your key ID

The generation output includes a line like:

```
pub   rsa4096 2026-02-17 [SC] [expires: 2027-02-17]
      ABCD1234EF5678901234ABCD1234EF5678901234
uid                      Key Owner (Vulnerability disclosure reporting) <security@yourdomain.com>
sub   rsa4096 2026-02-17 [E] [expires: 2027-02-17]
```

The 40-character hex string is your key's fingerprint; gpg accepts it anywhere a key ID is expected, and you'll need it for every command below. Find it again any time with:

```bash
gpg --list-keys security@yourdomain.com
```

### Step 4: Export and store the keys

Two separate commands, run one at a time.

```bash
gpg -a --export YOUR_KEY_ID > your-key.public.asc
gpg -a --export-secret-keys YOUR_KEY_ID > your-key.private.asc
```

Verify both files exist and are non-empty (public key ~3 KB, private key ~7 KB), upload both to your secrets manager or password manager's shared vault, then delete the local copies:

```bash
rm your-key.public.asc your-key.private.asc
```

### Step 5: Prepare the publishing version

```bash
gpg --armor --export YOUR_KEY_ID > pgp-key.txt
```

It should start with `-----BEGIN PGP PUBLIC KEY BLOCK-----` and end with `-----END PGP PUBLIC KEY BLOCK-----`.

## Renewing an existing key

Unless you're creating a new key pair, only the public key needs updating in storage and in every hosted location once renewed.

```bash
gpg --list-keys
gpg --edit-key KEYID
```

At the `gpg>` prompt: `expire` to renew the primary key, then `key 1` and `expire` again to renew the encryption subkey (researchers encrypt to the subkey, so a renewal that skips this step silently breaks the reporting channel when the subkey lapses), then set trust level 5 (ultimate, for your own key) with `trust`, then `save`. Confirm both the `pub` and `sub` lines now show the new expiry with `gpg --list-keys KEYID`, then test it:

```bash
gpg -ea > test-message.asc
gpg -d test-message.asc
```

Re-export and update every stored/hosted copy:

```bash
gpg --armor --export KEYID > pgp-key.txt
```

## Hosting the public key

- Host the public key wherever makes sense for your setup, commonly your website's static assets and/or object storage.
- **Update every hosting location on every rotation.** Don't assume one location is sufficient; a stale copy anywhere is a researcher encrypting to the wrong key.
- Serve it as plaintext (ASCII-armoured), preferred filename `pgp-key.txt`.
- Reference it in your `security.txt` on every primary domain you actually operate; never on a domain you hold only for typosquat protection.

## Providing the key to a researcher

- **Preferred**: link to your `security.txt`, which references the current key.
- **Alternative**: send `pgp-key.txt` directly as a plaintext attachment.

## Using the key to decrypt communications

```bash
gpg --decrypt message.asc         # also reports signature status if the message was signed
gpg --verify message.asc          # clearsigned (unencrypted) messages only
gpg --import researcher-key.asc   # to reply securely
gpg --encrypt --armor -r THEIRKEYID reply.txt
```

## Adapt this to your context

- **Key custody**: a solo practitioner is the sole key holder by default; document a succession plan (who gets access to the private key and passphrase if you're unavailable) rather than leaving that as a single point of failure.
- **Hosting mechanics**: "wherever makes sense for your setup" is deliberate; the specific platform (a static site host, an object-storage bucket, a CDN's security-file feature) varies enormously, and the requirement that matters is consistency across every location you publish it, not any specific platform.
- **Key size and algorithm**: RSA 4096 is a safe, broadly compatible default as of writing; revisit against current cryptographic guidance periodically rather than treating this as permanently settled.

**Frameworks referenced**: none specific; standard OpenPGP/GnuPG practice.
