# GLA 1.0 License

**Version 4 · Applies to GLA 1.0 only · Proprietary access license**

Copyright © ATEC (Advancement Through Engineering & Creation). All rights reserved except as expressly granted below.

> **This is a proprietary license, not an open-source license.**
> GLA 1.0 (Graph-Language Assistant) is owned by ATEC (Advancement Through Engineering & Creation) and is **not released**: it is not available for download, it is not distributed in any form, and the public `gla-api` library cannot run it. Its weights and files never leave ATEC. This License does not give You a copy of anything — it only sets the terms for using GLA 1.0 through **access that ATEC grants** (for example an API key to its GLA 1.0 server).

**In plain words** (a guide only; the numbered Sections are what bind You):

| With access granted by ATEC, You **may** | You **may not** |
|---|---|
| Use GLA 1.0 commercially inside **your own** website, application or API service, and charge users of that service | Download, copy, extract or reconstruct the model, or use a copy obtained any other way (Sections 2 and 4) |
| Use the outputs it produces | Modify, share, publish or distribute the model, free or paid |
| | **Sell or resell** the model, or sell, share or transfer Your access or API keys |
| | Train another model on its outputs to imitate it, without written permission |

You must **always credit** the main developer: **Built with GLA 1.0 by ATEC**.

---

## 1. Definitions

- **"Licensor"** means ATEC (Advancement Through Engineering & Creation), the main developer and owner of GLA 1.0.
- **"GLA"** means Graph-Language Assistant, the Licensor's family of AI models and the name of their architecture. GLA was previously called "CodeMind"; anything labelled "CodeMind 1.0" is the same Model and is covered by this License.
- **"Model"** means GLA 1.0: its trained weights, configuration, vocabularies, tokenizer, generation settings, manifest, metadata, the server software that runs it, and any copy, part, conversion or quantization of these, in any format or precision.
- **"Access"** means the ability to send inputs to the Model and receive Outputs, granted by the Licensor — for example an API key, an account, or a written permission naming You. Access never includes a copy of the Model.
- **"Credentials"** means API keys, tokens, accounts or other secrets that give Access.
- **"Output"** means the text, code or other content the Model returns in response to an input.
- **"Your Service"** means a website, an application or an API that You operate and that uses Your Access to the Model to serve Your own users.
- **"You"** means the person or organization that received Access, and anyone acting on Your behalf.
- **"Attribution Notice"** means the notice described in Section 7.

## 2. The Model is not distributed

1. **No release.** The Licensor does not publish, release, sell or distribute the Model, and does not offer it for download. No part of this License is a permission to obtain, hold or share a copy of it.
2. **Not supported by the public library.** The public `gla-api` library does not load or run GLA 1.0. Any software, package, file or service claiming to provide GLA 1.0 weights for download or local use is not authorized by the Licensor.
3. **Unauthorized copies.** A copy of the Model obtained in any way other than from the Licensor in writing — including by leak, breach, extraction, or from a third party — is **not licensed**. Using, storing, sharing or offering it is an infringement, not a use under this License.
4. **Licensor-run only.** The Model runs only on infrastructure the Licensor operates or expressly authorizes in writing.

## 3. What You may do with Access

Subject to Your compliance with this License and with any limits attached to Your Access, the Licensor grants You a worldwide, non-exclusive, non-transferable, non-sublicensable, revocable license to:

1. **Use** the Model through Your Access for any lawful purpose, including **commercial purposes**.
2. **Build Your Service** on top of it — a website, an application or an API — and **charge Your users for Your Service**, for example by subscription, per-use fees or advertising, provided Your Service adds its own product or function and Your users never receive the Model, Credentials, or a pass-through of Your Access (Section 4.4).
3. **Use Outputs** freely, including commercially, subject to Sections 8 and 9.

## 4. What is never permitted

You may not, and may not permit or help anyone else to:

1. **Obtain a copy.** Download, copy, record, extract or reconstruct the Model's weights or files, or try to do so by any technical means, including through Outputs, timing, error messages or internal states.
2. **Modify the Model.** Fine-tune, re-train, merge, quantize, convert or otherwise create a modified version of the Model. (Access never includes the files needed for this; any attempt to do it with an unauthorized copy is covered by Section 2.3.)
3. **Distribute.** Share, publish, upload, mirror or give the Model or any part of it to anyone, free of charge or not, as open source or otherwise.
4. **Sell or resell.** Sell, rent, lease or license the Model, any part of it, or **Access** to it — including selling, sharing, lending or transferring Credentials, offering a service whose main purpose is to pass Your Access through to others, or reselling the Model's capacity under another name.
5. **Imitate it.** Use Outputs, collected systematically, to train, distill or improve a model that imitates or competes with the Model, without the Licensor's written permission.
6. **Bypass limits.** Circumvent rate limits, usage limits, authentication, safety measures or monitoring attached to Your Access, or use more than one set of Credentials to avoid them.
7. **Misrepresent.** State or imply that the Licensor endorses, certifies or is responsible for Your Service or its content, or present the Model as Your own work.
8. **Use the names.** Use the names "GLA", "Graph-Language Assistant", "ATEC", "Advancement Through Engineering & Creation" or the earlier name "CodeMind", or their logos, except for the Attribution Notice and to state truthfully that Your Service uses GLA 1.0 (Section 11).
9. **Break the law** or make any use listed in Section 8.

## 5. Access

1. **Granted by the Licensor.** Access is given at the Licensor's discretion and may carry limits (for example requests, tokens, concurrency, permitted uses or a time period). Those limits form part of this License.
2. **Your Credentials.** Keep Credentials secret and use them only for You and Your Service. You are responsible for all use made with them. Tell the Licensor promptly if they are lost or exposed.
3. **Changes.** The Licensor may change, suspend or end the Model, the server or Your Access at any time, including to protect security, comply with law or respond to a breach. GLA 1.0 may be withdrawn without replacement.
4. **No service level.** Unless a separate signed agreement says otherwise, Access is provided without any promise of availability, speed, support or continuity.

## 6. Your users

When Your Service uses the Model:

1. You are responsible for Your Service, its users and the content it delivers.
2. Your terms of service must not grant Your users any right in the Model beyond using Your Service.
3. You must not let Your users reach the Model's Access directly or obtain Credentials.

## 7. Credit to the main developer (attribution)

**7.1 The Attribution Notice.** Your Service must credit the main developer with this notice, or a clearly equivalent one:

> **Built with GLA 1.0 by ATEC** — https://github.com/ATECTechnologies/Graph-Language-Assistant

**7.2 Where it must appear.**

- **Websites and applications:** in a place a user can reasonably find — for example an "About", "Credits", "Legal" or "Powered by" page, screen or footer.
- **APIs:** in the API's public documentation, and in the model-information response if Your API provides one.
- **Publications, papers, benchmarks and announcements** describing results obtained with the Model: by citation.

**7.3 Always.** The obligation to credit continues for as long as You use the Model or offer Your Service with it.

## 8. Acceptable use

You may not use the Model or Outputs:

1. to violate any applicable law, regulation or the rights of others;
2. to create or distribute malware, exploits intended for unauthorized access, or tools whose main purpose is to harm systems or data;
3. to harass, threaten, defame, impersonate or deceive people, or to generate content that sexualizes minors;
4. to collect, infer or expose personal data without a lawful basis;
5. to infringe intellectual property, including by presenting Outputs that copy protected works as Your own;
6. to probe, attack or test the security of the Licensor's systems without written permission (report vulnerabilities as described in Section 16.6).

## 9. Inputs and Outputs

1. **Your inputs.** You must have the right to send what You send. Do not send data You are not permitted to share.
2. **Outputs.** As between You and the Licensor, the Licensor claims no ownership of Outputs. Outputs may be wrong, incomplete or unsafe; You are responsible for checking them before relying on or publishing them, and for whether they infringe the rights of others.
3. **Operation data.** The Licensor may process inputs, Outputs and usage data to provide Access, enforce limits, keep the service secure and enforce this License.

## 10. Protection of intellectual property

1. **Ownership.** The Licensor owns and keeps all rights, title and interest in GLA 1.0, including its architecture (the Graph-Language Assistant architecture), design, training methods, weights, vocabularies, server software, documentation and the names and marks "GLA", "Graph-Language Assistant", "ATEC", "Advancement Through Engineering & Creation" and the earlier name "CodeMind". This License grants only the rights expressly stated; all other rights are reserved.
2. **Trade secrets.** The weights, training source code, training data, configurations and internal tools of GLA 1.0 are confidential and are not licensed under this License. Information about them that You learn through Access, other than what the Licensor publishes, may not be disclosed or used outside this License.
3. **No reverse engineering.** You may not decompile, disassemble or reverse-engineer the Model, the server software or any component the Licensor provides, or attempt to reconstruct the training data, code, hyper-parameters or weights, except to the extent applicable law expressly permits this despite this restriction.
4. **Technical protection.** You may not remove, disable or work around keys, signatures, checksums, watermarks, monitoring or other protection measures.
5. **Documentation.** The published GLA 1.0 documentation describes the Model for information only. It is not a release of the Model and grants no right to build, train or reproduce it.
6. **Enforcement.** The Licensor may seek any remedy available by law for a breach of Sections 2, 4 or 10, including injunctions and the removal of unauthorized copies, in addition to ending Your Access.
7. **Feedback.** If You give the Licensor suggestions or feedback, the Licensor may use them without obligation to You.

## 11. Names and trademarks

This License does not grant rights to use "GLA", "Graph-Language Assistant", "ATEC", "Advancement Through Engineering & Creation" or the earlier name "CodeMind", or related names, logos or marks, except to provide the Attribution Notice and to state truthfully that Your Service uses GLA 1.0. You may not use these names as the name of Your product or service, or in a way likely to cause confusion about who made it or whether it is official.

## 12. Termination

1. **Automatic termination.** Your rights under this License end automatically if You breach it, and the Licensor may end Your Access immediately.
2. **Reinstatement.** For a breach that can be cured, if You cure it within 30 days of becoming aware of it, the Licensor may restore Your Access — once. A breach of Sections 2, 4.1, 4.3, 4.4 or 10 ends Your rights permanently.
3. **Effect.** On termination You must stop using the Model and remove it from Your Service. Outputs You lawfully obtained before termination remain Yours to use, subject to Sections 8 and 9.
4. **Survival.** Sections 2, 4, 9, 10, 13, 14 and 16 survive termination.

## 13. No warranty

THE MODEL AND ACCESS ARE PROVIDED **"AS IS"** AND **"AS AVAILABLE"**, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, ACCURACY, AVAILABILITY, SECURITY, NON-INFRINGEMENT, OR THAT OUTPUTS WILL BE CORRECT OR SAFE. You use the Model and Outputs at Your own risk.

## 14. Limitation of liability

TO THE MAXIMUM EXTENT PERMITTED BY LAW, THE LICENSOR WILL NOT BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL OR PUNITIVE DAMAGES, OR FOR LOSS OF PROFITS, DATA, GOODWILL OR BUSINESS, ARISING FROM THIS LICENSE, ACCESS, THE MODEL OR OUTPUTS, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. You will indemnify the Licensor against claims arising from Your Service, Your inputs or Your breach of this License.

## 15. This version only

This License applies to GLA 1.0 only. It grants no rights in any other version of GLA, and the license of any other version grants no rights in GLA 1.0.

## 16. General

1. **Governing law.** This License is governed by the laws of the Kingdom of Thailand, without regard to conflict-of-laws rules. Courts in Thailand have jurisdiction, unless the Licensor chooses to bring an action where You are located.
2. **Severability.** If any provision is held unenforceable, it is limited to the minimum extent necessary and the rest of the License stays in effect.
3. **No waiver.** Failure to enforce a provision is not a waiver of it.
4. **Entire agreement.** This License, with the limits attached to Your Access, is the entire agreement about the Model between You and the Licensor, unless You have a separate written agreement signed by the Licensor, which then prevails where it differs.
5. **Updates.** The Licensor may publish new versions of this License; continued use of Access after a new version is published means You accept it.
6. **Contact.** Requests for Access, permissions beyond this License, and vulnerability reports: through the repository, https://github.com/ATECTechnologies/Graph-Language-Assistant.
7. **Not open source.** This License is a proprietary license. GLA 1.0 is not open source, not in the public domain and not available under any other license. Publishing its documentation does not change this.

---

*GLA 1.0 License — Copyright © ATEC (Advancement Through Engineering & Creation).*
