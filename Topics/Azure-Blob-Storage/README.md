# Azure Blob Storage

## Introduction to Azure Blob storage

Azure Blob storage is a feature of Microsoft Azure. It allows users to store large amounts of unstructured data on Microsoft’s data storage platform. In this case, Blob stands for Binary Large Object, which includes objects such as images and multimedia files. These are known as unstructured data because they don’t follow any particular data model. 

With Azure Blob storage, the files (photos, videos, training documents, etc.), which are known as blobs, are put in containers which function similar to directories. These are then linked to the storage account. When creating the address to give access to a file in Azure data storage, it will simply join the storage account and the location of the blob. The address will be in a .net format.

One of the big advantages for businesses is that Azure Blob storage allows them to collect all of their content assets in one place. These will then be available all across their different departments and internationally. The speed, scalability, ease of access, and security (both from accidents and criminals) make such cloud storage very attractive for all mid-sized and large organizations.

Resource: click [here](https://www.snaplogic.com/glossary/azure-blob-storage).

---
## Why do we need Blob Storage?
+ Serving images or documents directly to a browser.
+ Storing files for distributed access.
+ Streaming video and audio.
+ Writing to log files.
+ Storing data for backup and restore, disaster recovery, and archiving.
+ Storing data for analysis by an on-premises or Azure-hosted service.
---
### Blob storage offers three types of resources:
+ The storage account: a storage account provides a unique namespace in Azure for your data. Every object that you store in Azure Storage has an address that includes your unique account name. The combination of the account name and the Blob Storage endpoint forms the base address for the objects in your storage account.
+ A container in the storage account: a container organizes a set of blobs, similar to a directory in a file system. A storage account can include an unlimited number of containers, and a container can store an unlimited number of blobs.
+ A blob in a container.
---
### Types of Blobs:

+ Block blobs.
+ Append blobs.
+ Page blobs.

Click [here](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction) to view the whole description for each type.


Resource: [Azure Storage documentation](https://docs.microsoft.com/en-us/azure/storage/).














