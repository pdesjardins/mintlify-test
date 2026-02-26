---
title: "Message signing"
id: apiMessageSigning
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUsingWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Using webhooks"
previousSectionFile: apiDevGuide-apiRetrySupport.md
previousSectionTitle: "Retry support"
nextSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
nextSectionTitle: "Webhooks reference"
excerpt: "The Toast platform implements message signing that allows you to validate the source of data sent to your webhook endpoint."
keywords: ["message", "signing", "Toast-Signature"]
procedures: 0
codeExamples: 1
---

The Toast platform implements message signing that allows you to validate the source of data sent to your webhook endpoint.



> **Note**
> 
> Using message signing to validate a webhook message is not required, however, it is highly recommended.


Using the secret key that is generated when your webhook subscription is created, and the body and timestamp of the message, a signature for each message is computed and published in the `Toast-Signature` HTTP header on the POST request to your endpoint.



> **Note**
> 
> The secret key is unique for each webhook subscription within an environment. For example, a `stock` webhook subscription has a different secret key than a `partner` webhook subscription for the same integration partner and within the same environment. For more information about webhook subscriptions, see [Webhook basics](docs/en-us/apiDevGuide-apiWebhookBasics). For more information about Toast API environments, see [Environments](docs/en-us/apiDevGuide-apiEnvironments).


To validate the message, you compute the signature on your side, using the same process that the Toast platform uses to compute the signature. If the signatures match, then the message is valid and trustworthy.

The signature is derived by concatenating the body and timestamp of the webhook message into a string. This string is hashed and then signed using the HMAC-SHA256 algorithm and the secret key. The following is a code sample for computing the signature:


```
import javax.crypto.spec.SecretKeySpec;
import javax.crypto.Mac;
import javax.xml.bind.DatatypeConverter;
import java.nio.charset.StandardCharsets;

String HMAC = "HmacSHA256";

String getSignature(String secret, String body, String timestamp) {
  SecretKeySpec signingKey = new SecretKeySpec(secret.getBytes(), HMAC);
  try {
      String signature = body + timestamp;
      Mac mac = Mac.getInstance(HMAC);
      mac.init(signingKey);
      byte[] rawHmac = mac.doFinal(signature.getBytes(StandardCharsets.UTF_8));
      return DatatypeConverter.printBase64Binary(rawHmac);
  } catch (Exception e) {
      logger.warn("Failed to generate Webhook Signature", e);
      return null;
  }
}
```

