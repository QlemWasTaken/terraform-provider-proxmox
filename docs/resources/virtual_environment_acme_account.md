---
layout: page
title: proxmox_virtual_environment_acme_account
parent: Resources
subcategory: Virtual Environment
description: |-
  Manages an ACME account in a Proxmox VE cluster.
  ~> This resource requires root@pam authentication.
---

# Resource: proxmox_virtual_environment_acme_account

Manages an ACME account in a Proxmox VE cluster.

~> This resource requires `root@pam` authentication.

## Example Usage

```terraform
resource "proxmox_virtual_environment_acme_account" "example" {
  name      = "example"
  contact   = "example@email.com"
  directory = "https://acme-staging-v02.api.letsencrypt.org/directory"
  tos       = "https://letsencrypt.org/documents/LE-SA-v1.3-September-21-2022.pdf"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `contact` (String) The contact email addresses.

### Optional

- `directory` (String) The URL of the ACME CA directory endpoint.
- `eab_hmac_key` (String) The HMAC key for External Account Binding.
- `eab_kid` (String) The Key Identifier for External Account Binding.
- `name` (String) The ACME account config file name.
- `tos` (String) The URL of CA TermsOfService - setting this indicates agreement.

### Read-Only

- `created_at` (String) The timestamp of the ACME account creation.
- `location` (String) The location of the ACME account.

## Import

Import is supported using the following syntax:

```shell
#!/usr/bin/env sh
# ACME accounts can be imported using their name, e.g.:
terraform import proxmox_virtual_environment_acme_account.example example
```