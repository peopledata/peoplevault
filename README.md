# PeopleVault

PeopleVault forked from ![CircleCI](https://circleci.com/gh/hashicorp/vault.svg?style=svg) and tailed for PeopleData Community.

In digital society, there are numerous encrypt/decrypt activities everyday. That's why Key Management System(KMS) play more and more important roler for everyone. In Web1.0 and Web2.0，KMS is centralized and most of time invisable to individual person.  In Web3.0, People will take back their data rights, control their data usage and benefit from their data assets. That's why the community need PeopleVault: a decentralized, distributed KMS for Everyone.


## About Hasicorp/Vault

Vault is a tool for securely accessing secrets. A secret is anything that you want to tightly control access to, such as API keys, passwords, certificates, and more. Vault provides a unified interface to any secret, while providing tight access control and recording a detailed audit log.

A modern system requires access to a multitude of secrets: database credentials, API keys for external services, credentials for service-oriented architecture communication, etc. Understanding who is accessing what secrets is already very difficult and platform-specific. Adding on key rolling, secure storage, and detailed audit logs is almost impossible without a custom solution. This is where Vault steps in.

The key features of Vault are:

* **Secure Secret Storage**: Arbitrary key/value secrets can be stored
  in Vault. Vault encrypts these secrets prior to writing them to persistent
  storage, so gaining access to the raw storage isn't enough to access
  your secrets. Vault can write to disk, [Consul](https://www.consul.io),
  and more.

* **Dynamic Secrets**: Vault can generate secrets on-demand for some
  systems, such as AWS or SQL databases. For example, when an application
  needs to access an S3 bucket, it asks Vault for credentials, and Vault
  will generate an AWS keypair with valid permissions on demand. After
  creating these dynamic secrets, Vault will also automatically revoke them
  after the lease is up.

* **Data Encryption**: Vault can encrypt and decrypt data without storing
  it. This allows security teams to define encryption parameters and
  developers to store encrypted data in a location such as a SQL database without
  having to design their own encryption methods.

* **Leasing and Renewal**: All secrets in Vault have a _lease_ associated
  with it. At the end of the lease, Vault will automatically revoke that
  secret. Clients are able to renew leases via built-in renew APIs.

* **Revocation**: Vault has built-in support for secret revocation. Vault
  can revoke not only single secrets, but a tree of secrets, for example
  all secrets read by a specific user, or all secrets of a particular type.
  Revocation assists in key rolling as well as locking down systems in the
  case of an intrusion.
  
  
- Documentation is available on the [Vault website](https://www.vaultproject.io/docs/).
-	Website: https://www.vaultproject.io
-	Announcement list: [Google Groups](https://groups.google.com/group/hashicorp-announce)
-	Discussion forum: [Discuss](https://discuss.hashicorp.com/c/vault)
- Documentation: [https://www.vaultproject.io/docs/](https://www.vaultproject.io/docs/)
- Tutorials: [HashiCorp's Learn Platform](https://learn.hashicorp.com/vault)
- Certification Exam: [Vault Associate](https://www.hashicorp.com/certification/#hashicorp-certified-vault-associate)


Getting Started
-------------------------------


Developing PeopleVault
--------------------
