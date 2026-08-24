# Azure Storage and SAS Configuration

## Overview

This document describes the Azure Storage configuration used for the Contoso Coffee solution.

The storage solution is used to store image files for the Contoso Coffee website and provide controlled access to the files.

## Azure Storage Account

An Azure Storage Account was created for the Contoso Coffee solution.

The storage account is used for:

* Blob Storage
* Website image storage
* Lifecycle management
* Shared Access Signature (SAS) access

## Blob Storage

A Blob Storage container was created to store images used by the Contoso Coffee website.

Example structure:

```text
Storage Account
└── Blob Container
    ├── image1.jpg
    ├── image2.jpg
    └── other website images
```

A test image was uploaded to the Blob container to verify that the storage configuration was working correctly.

## Lifecycle Management

A lifecycle management policy was configured for the Blob Storage account.

Lifecycle management can automatically manage blobs based on conditions such as:

* Blob age
* Creation time
* Last modification time
* Blob prefix

This can be used to reduce storage costs by automatically moving older data to cheaper storage tiers or deleting data that is no longer required.

## Shared Access Signature (SAS)

A Shared Access Signature was created to provide temporary and controlled access to a Blob.

The SAS configuration included:

* Limited permissions
* Start time
* Expiration time
* Access to the required Blob resource only

The generated Blob SAS URL was tested in a web browser.

The test was successful and the image could be accessed using the SAS URL.

## SAS URL Format

A Blob SAS URL typically consists of:

```text
https://<storage-account>.blob.core.windows.net/<container>/<blob>?<sas-token>
```

The SAS token contains the permissions and validity period for the request.

## Security

SAS tokens should be treated as sensitive information.

The actual SAS token used during testing is **not stored in this GitHub repository**.

SAS tokens should:

* Have only the permissions required
* Use a limited expiration time
* Be regenerated when necessary
* Never be committed to a public GitHub repository

## Verification

The following functionality was tested successfully:

* Storage Account created
* Blob container created
* Image uploaded to Blob Storage
* Lifecycle management configured
* SAS token generated
* Blob SAS URL tested
* Image successfully accessed using the SAS URL

## Responsibility

**Kristoffer – Azure Storage, Blob Storage, lifecycle management and SAS access**
