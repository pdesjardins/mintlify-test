---
title: "SSH keys"
id: adminSshKeys
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformDataExportFilesOmitChunkFromSearchIndex.md
parentSectionTitle: "Data export files"
previousSectionFile: adminGuide-adminDataExportOverview.md
previousSectionTitle: "Data export files overview"
nextSectionFile: adminGuide-configuringExports.md
nextSectionTitle: "Configuring exports"
excerpt: "Toast sFTP data exports require the use of a public SSH key. Use the below sections to learn how to generate public SSH keys, and where to place them within Toast Web."
procedures: 0
codeExamples: 0
---

Toast sFTP data exports require the use of a public SSH key. Use the below sections to learn how to generate public SSH keys, and where to place them within Toast Web.



> **Note**
> 
> Private SSH keys are not supported.


### How to generate an SSH key with macOS™ or Windows™

This section includes information about how to generate an SSH key using macOS or Windows.

#### macOS

Open a terminal window and use the below command to create a new SSH key.

```
ssh-keygen -t rsa -f ~/.ssh/`\{filename\}`
```

Replace *`\{filename\}`* with the desired name of your SSH key file.



> **Note**
> 
> When asked for a passphrase, you can enter any phrase, or press Return twice to continue without one.


The command shown above saves a private key and a public key in the ~/.ssh directory as *`filename`* (private key) and *`filename.pub`* (public key.) Open the .pub file in a text editor to retrieve your public key to add to the Toast Web.

#### Windows

Open a command prompt and use the below command to create a new SSH key.

```
ssh-keygen -t rsa -f "C:\Users\`\{user\}`\.ssh\`\{filename\}"`
```

Replace the following from the above command:

- `\{user\}`: Your desktop user name


- `\{filename\}`: The desired name of your SSH key file.



The above command saves a private key and public key in the C:\Users\user\.ssh directory as *`filename`*(private key) and *`filename.pub`* (public key). Open the .pub file in a text editor to retrieve your public key to add to Toast Web.

#### Add your SSH key to Toast Web

Toast Web allows up to 10 SSH keys. It is recommended to add a new SSH key for each operator, or data export user, instead of sharing one. If a user outside of your restaurant needs access to your sFTP, they should create their SSH key and share it with someone that can add the key to Toast Web. After being generated, SSH keys must be added to the SSH Keys page at Reports \> Settings \> SSH Keys. The following information includes the necessary steps for adding SSH keys to the Toast Web.

1. Navigate to Reports \> Settings \> SSH Keys.

![Image](https://doc.toasttab.com/doc/media/nav_ssh_keys.png)




2. Select Add new key.

![Image](https://doc.toasttab.com/doc/media/new_ssh_key.png)




3. Enter your SSH key in the text box and select Add key. When pasting your SSH key, include the "=" and everything before; do not include the device name after the "=".

![Image](https://doc.toasttab.com/doc/media/add_key_ssh.png)



After your SSH key is added to Toast Web, you can continue with [downloading data export files.](downloading_data_export_files.html)



