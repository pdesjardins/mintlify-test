---
title: "Configuring multi-factor authentication using an authenticator app"
id: intAdminMfaConfiguringQrCode
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminEmployeesMfaOmitChunkFromSearchIndex.md
parentSectionTitle: "Multi-factor authentication"
previousSectionFile: adminGuide-intAdminMfaEnablingAndDisabling.md
previousSectionTitle: "Enabling and disabling multi-factor authentication"
nextSectionFile: adminGuide-intAdminMfaConfiguringSms.md
nextSectionTitle: "Configuring multi-factor authentication using SMS"
externalReferences: [https://pos.toasttab.com]
excerpt: "You can choose to set up your multi-factor authentication using a QR code or SMS. To learn how to set it up using SMS, see ."
procedures: 1
codeExamples: 0
---

You can choose to set up your multi-factor authentication using a QR code or SMS. To learn how to set it up using SMS, see [Configuring multi-factor authentication using SMS](docs/en-us/adminGuide-intAdminMfaConfiguringSms).

**Procedure 4.3. To use a QR code for multi-factor authentication**

1. From a browser, go to [https://pos.toasttab.com](https://pos.toasttab.com)and click Login to access the Toast Web login page.


2. Enter your username and password. Select Continue.


3. In the Keep Your Account Safe dialog, select Google Authenticator or similar.

![Example of the Keep Your Account Safe window.](https://doc.toasttab.com/doc/media/mfa_keep_your_account_safe.png)


4. Scan the QR code displayed in the Secure Your Account window using an authenticator app.


5. Enter the one-time code provided in the authenticator app in the edit field, then select Continue.

![Example of the Secure Your Account window.](https://doc.toasttab.com/doc/media/mfa_secure_your_account.png)



In the future, you will be prompted periodically to enter a 6-digit code from your authenticator app when you sign in to Toast Web.

![Example of the Verify Your Identity dialog where you enter the 6-digit-code.](https://doc.toasttab.com/doc/media/mfa_enter_code_screen.png)

