# PeopleVault

PeopleVault forked from Hashicopr/Vault and tailed for PeopleData Community.

In digital society, there are numerous encrypt/decrypt activities everyday. That's why Key Management System(KMS) play more and more important roler for everyone. In Web1.0 and Web2.0，KMS is centralized and most of time invisable to individual person.  In Web3.0, People will take back their data rights, control their data usage and benefit from their data assets. That's why the community need PeopleVault: a decentralized, distributed KMS for Everyone.


## About Hasicorp/Vault

![image](https://user-images.githubusercontent.com/79302978/166898005-591b851b-fd77-4d42-9816-7685cf326c48.png)


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

## About PeopleVault
KMS is alwasy a complicated work, even to experts. Our mission is to make everyone to use KMS as easy as we can. Hashicorp/Vault provide powerful ability to help us achive this goal. 

PeopleVault did not make any changes on Vault's core, but make some optimized and add some functions on its body. 

![peoplevault arch](https://github.com/peopledata/peoplevault/blob/ffefadddb58ba8470563421a3b9efd0cdf3e37e0/peopleVault-arc.png)

PeopleVault is a two-tier KMS, which a Root Vault is deployed close with individual person and a Vault Pod in remote cloud. The Root Vault is the root of the Vault Pod, and invesibale from outside. The Vault Pod is intermediate Vault which provider major KMS service to outside. The individual person just manage the Root vault and hold a root phase word/pin only, the rest KMS service will be automatically processed by Root Vault and Vault Pod.  

The Root Vault has two kind of implementation: VaH and VaD.
 - Vault at Home(VaH): PeopleVault will be deployed on a local linux-machine as Root Vault. Individual person can start/stop/terminated the Root Vault, and generate new root-key, Root-CAs or Root-like token on demand. 
 - Vault at Device(VaD): PeopleVault will be depolyed on a device (such as U disk, safe hard device...etc）as Root Vault. It is a simple and cheap way for individual person to manage their root vault. It has limited function.   

The Vaule Pod is a vault server on duty, and handle most of the KMS service for individual person. 
 - Valut Pod: PeopleVault deplyed on k8s pod, and will automatically process most of KMS service. 
