# 🔐 Azure Storage Account Networking Lab

This project demonstrates how to secure an Azure Storage Account using network access control rules. The work was completed as part of a hands-on lab to build and reinforce Azure Administration skills aligned with the AZ-104 certification.

---

## 🧪 Lab Overview

- **Storage Account Name**: `calabstorage2020`
- **Public IP Allowed**: `95.144.187.133`
- **Service**: Azure Blob Storage (via Storage Account)
- **Azure Region**: West Europe
- **Lab Objective**: Restrict access to a storage account using network and IP-based firewall rules.

---

## ✅ What Was Configured

### 1. Azure Storage Account Created
- Provisioned a general-purpose v2 storage account via the Azure Portal.
- Chose standard performance and locally redundant storage (LRS).

### 2. Managed Access Keys
- Viewed and understood the use of primary and secondary access keys.
- Emphasized the importance of key rotation for security.

### 3. Generated a Shared Access Signature (SAS)
- Configured a SAS token with limited permissions and expiration time for secure access sharing.

### 4. Hardened Network Access
- Disabled access from **All Networks**.
- Allowed access **only** from:
  - Public IP address: `95.144.187.133`
  - **Trusted Microsoft Services** (enabled via the Exceptions setting)

### 5. Saved and Validated Access Settings
- Ensured only my IP could access the storage account.
- Blocked all other sources by default.

---

## 🗺️ Architecture Overview

```mermaid
graph TD
    UserIP[Your IP: 95.144.187.133]
    TrustedMS[Trusted Microsoft Services]
    Storage[Azure Storage Account: calabstorage2020]

    UserIP -->|Allowed Access| Storage
    TrustedMS -->|Allowed Access| Storage

    Internet[Other Networks] -->|Blocked| Storage
