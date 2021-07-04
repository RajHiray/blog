---
title: "Azure Key Vault Fundamentals"
description: "Azure Key vault Fundamentals"
date: 2021-01-09T17:33:56+05:30
draft: false
tags: ["Azure", "csharp","MSI","Azure-Key-Vault"]
categories : ["posts"]
image: "azure-keyvault.png"
---

---
You’ve probably heard some version of the story about a developer who mistakenly `checked in` his key/secrete to `source code.`

As developers we all understand and care about keeping dev and production secrets safe but managing those secrets on your own or especially in a team can be cumbersome. 


__Safeguarding Secrets In software Development__ <br>
Most of us know it’s a best practice to keep secret settings like __connection strings, domain passwords, or other credentials as a runtime configuration and outside the source code.__ `Azure Key Vault` provides a security location to safeguard keys and other secrets used in software development.

## About Azure Key Vault ##
Azure Key Vault allows you to securely store and manage application credentials such as secrets, keys, and certificates in a central and secure cloud repository. __Key Vault eliminates the need to store credentials in your applications.__ Your applications can authenticate to Key Vault at run time to retrieve credentials.
Azure Key Vault helps solve the following problems:

- __Secrets Management__ - Azure Key Vault can be used to Securely store and tightly control access to tokens, passwords, certificates, API keys, and other secrets.
- __Key Management__ - Azure Key Vault can also be used as a Key Management solution. Azure Key Vault makes it easy to create and control the encryption keys used to encrypt your data.
- __Certificate Management__ - Azure Key Vault is also a service that lets you easily provision, manage, and deploy public and private Transport Layer Security/Secure Sockets Layer (TLS/SSL) certificates for use with Azure and your internal connected resources.
- __Hardware Security Modules__ – Secrets and keys can be protected by software, or `FIPS 140-2` Level 2 validated HSMs.

## Key Vault Authentication ##

To do any operations with Key Vault, you first need to `authenticate` to it. There are three ways to authenticate to Key Vault:

- __Managed Identities for Azure Resources__: When you deploy an app on a virtual machine in Azure, you can assign an identity to your virtual machine that has access to Key Vault. You can also assign identities to other Azure resources. The benefit of this approach is that the app or service isn't managing the rotation of the first secret. Azure automatically rotates the identity. I recommend this approach as a best practice.
- __Service Principal and Certificate__: You can use a service principal and an associated certificate that has access to Key Vault. I don't recommend this approach because the application owner or developer must rotate the certificate.
- __Service Principal and Secret__: Although you can use a service principal and a secret to authenticate to Key Vault, I don't recommend it. It's hard to automatically rotate the bootstrap secret that's used to authenticate to Key Vault.

As an administrator, you can tightly control which users and applications can access your key vault and you can limit and audit the operations they perform.

