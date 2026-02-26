---
title: "Multi-factor authentication overview"
id: platformMultiFactorAuthenticationOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminEmployeesMfaOmitChunkFromSearchIndex.md
parentSectionTitle: "Multi-factor authentication"
previousSectionFile: adminGuide-adminEmployeesMfaOmitChunkFromSearchIndex.md
previousSectionTitle: "Multi-factor authentication"
nextSectionFile: adminGuide-intAdminMfaEnablingAndDisabling.md
nextSectionTitle: "Enabling and disabling multi-factor authentication"
externalReferences: [https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2, https://duo.com/product/multi-factor-authentication-mfa/duo-mobile-app]
excerpt: "Multi-factor authentication (MFA) is a security feature that requires users to provide multiple forms of authentication to..."
keywords: ["multifactor", "authentication", "overview"]
procedures: 0
codeExamples: 0
---

Multi-factor authentication (MFA) is a security feature that requires users to provide multiple forms of authentication to access an account, making it much harder for unauthorized users to gain access even if they have the password. The multiple forms of authentication are often broken into categories like “something you know” (for example, passwords) and “something you have” (for example, access to a phone that can receive one-time passcodes).

When you use multi-factor authentication, the Toast platform prompts you for a numeric passcode in addition to your username and password when you sign in to Toast Web as an employee. You get the passcode from a short message system (SMS) text message or using an authenticator application that generates a secure passcode. The combination of your username and password and the passcode that you get using a device that only you are likely to have are the multiple factors that increase the security of your employee account.

## Why is enrolling in MFA important?

MFA is one of the simplest and most effective ways for Toast users to protect their accounts and access to proprietary business information and operations. MFA adds an extra layer of security by requiring additional verification beyond a password, which is critical given how easily passwords can be stolen or guessed. This additional layer stops cybercriminals from accessing sensitive data even if they manage to obtain an employee’s password, protecting against phishing attacks and identity theft. By using MFA, Toast users can not only keep their accounts safe, but also gain peace of mind knowing their information is significantly better protected from unauthorized access.

Ideally, anyone with access to critical systems or operations should enroll in MFA, but it is particularly important for users with financial permissions. For this reason, employees with the following permissions are required to use MFA.

- 8.1 Financial Accounts


- 8.7 Instant Deposit



For more information about employee permissions, see [Access permissions reference](docs/en-us/adminGuide-adminPermissions).

## Options for receiving MFA passcodes

You can choose the way that you get the secure passcode for multi-factor authentication.

- You can use any authenticator app to generate secure codes. For example, you can use the [Google Authenticator™ mobile app](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2) or the [Duo™ mobile app](https://duo.com/product/multi-factor-authentication-mfa/duo-mobile-app). For more information about configuring an authenticator app for Toast platform multi-factor authentication, see [Configuring multi-factor authentication using an authenticator app](docs/en-us/adminGuide-intAdminMfaConfiguringQrCode).


- You can receive secure codes through text messages (SMS). For more information about configuring Toast platform multi-factor authentication using SMS text messaging, see [Configuring multi-factor authentication using SMS](docs/en-us/adminGuide-intAdminMfaConfiguringSms).



