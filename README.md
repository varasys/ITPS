# ITPS
Identity Transport Protocol - Secure

ITPS is meant as the successor to the HTTPS protocal, based on [libsodium](https://download.libsodium.org/doc/) (which in turn is based on [Daniel Bernsein's](https://en.wikipedia.org/wiki/Daniel_J._Bernstein) [NaCl](https://nacl.cr.yp.to/) cryptography library), intended to utilize current best practices in networking and strong cryptography.

Unlike HTTPS which fundamentally relies on centralized Root Certificates, ITPS has no concept of a root certificate authority, and all servers will generate their own keypair and then advertise/vouch for other sub-servers as appropriate.

ITPS will allow users to select different identities for performing different actions. For instance, a user may select one "identity" to use when shopping online (and thus building a history and reputation as that identity), while selecting a different "identity" to use when interacting with a volunteer organization they contribute to (and thus building a history and reputation as that entity).

[Public Key Infrastructure (PKI)](https://en.wikipedia.org/wiki/Public_key_infrastructure) and particularely key management will be front and center and not obfuscated for the sake of user friendlyness. Instead focus will be on providing clear and meaningful key managument interfaces to generate new keys, and manage "trust graphs". Having said that, it is expected that users will generally use "trust graphs" prepared by trusted third parties instead of fully developing their own. The point is that the user *has the ability* to granularely manage the trust graphs which provides incentive for third parties to manage them better. Also the user can use unions and intersections of third party develop trust graphs instead of the current "all or nothing" root CA model (technically users can manage their root certificate bundles, but this is generally to hidden for people to actually do it, and also for each root CA it is a "take it or leave" it proposition).

ITPS is meant to be a complete replacement for SSL/TLS (OpenSSL) and GnuPG providing the following:
1. Data in Motion
    * encryption (secrecy)
    * optional anonaminity
    * authentication (allow/deny access)
    * authenticity (no errors)
    * validation (digitally signed)
2. Data at Rest
    * encryption (secrecy)
    * authenticity (no errors)
    * validation (digitally signed)

ITPS is meant as the network protocol underpinning the [MyDroid](https://github.com/varasys/MyDroid) and [MyCloud](https://github.com/varasys/MyCloud) projects.

## Team Skills Needed
1. Network Protocol Developer (consider whether WireGuard provides a starting point for this?)
2. Linux Kernel Developer (for kernel modules - again, WireGuard seems to have figured this out)
3. Cryptography Expert (to validate implementation)
4. Networking Engineers (to finalize network discovery, routing, etc.)
