# BillingBird Google Play Listing Draft

Prepared: July 16, 2026
Last revised: October 14, 2026 (support contact and URL alignment record, Contacts disclosure, release identity)

Status: Local draft only. Nothing in this file has been uploaded or submitted to Google Play.

## Main Listing

- App name: `BillingBird`
- Default language: English (United States) — `en-US`
- Suggested category: Business
- Support email (this listing and all three public pages): `contact@deadstick.net`
- In-app support address (`SUPPORT_EMAIL`, `src/utils/constants.ts:11`, identical in the `android/` and `ios/` repositories; used by Settings > Support and the startup-failure screens): `support@billingbird.app`
- Privacy policy: https://deadstick-digital.github.io/BillingBird-Store-Pages/privacy.html
- Support: https://deadstick-digital.github.io/BillingBird-Store-Pages/support.html
- Account deletion: https://deadstick-digital.github.io/BillingBird-Store-Pages/account-deletion.html

The three public URLs returned HTTPS 200 on July 16, 2026. The email change to
`contact@deadstick.net` is local-only until this repository is reviewed, committed, pushed,
and GitHub Pages finishes rebuilding. Recheck the deployed pages before entering them in
Play Console.

### Contact And URL Alignment

| Surface | Value today | Source |
| --- | --- | --- |
| Play listing support email | `contact@deadstick.net` | this file |
| Public privacy, support and deletion pages | `contact@deadstick.net` | `store-pages/docs/*.html` |
| In-app support email | `support@billingbird.app` | `src/utils/constants.ts:11` (both repositories) |
| Apple-facing legal links (iOS and Mac surfaces) | `https://www.deadstick.net/privacy.html#apps`, `https://www.deadstick.net/terms.html#apps-billingbird`, `https://www.deadstick.net/deletion.html#billingbird` | `src/constants/appleLegal.ts` |
| Android privacy information in the app | on-screen text, no URL | `app/settings/privacy.tsx` |

OWNER DECISION (default recorded, nothing applied to the app): the listing keeps
`contact@deadstick.net`, the only support address the three public pages publish and the one
Play Console must verify. The in-app address differs. Before any upload the owner confirms
that `support@billingbird.app` receives mail, or approves a follow-up change that sets
`SUPPORT_EMAIL` to `contact@deadstick.net` in both repositories' `src/utils/constants.ts` and
in the literal that `scripts/verify-settings-support.cjs` asserts (line 171). That follow-up
touches shared, gate-asserted code, so it is not part of this documentation task. The privacy
text on the github.io page, the deadstick.net page and the in-app privacy screen must say the
same thing about Contacts, backup and subscriptions; recheck all three after publication.

### Short Description

Create invoices, organize receipts, run reports, and export your records.

Character count: 73 of 80.

### Full Description

BillingBird helps contractors and small service businesses handle everyday billing without
turning simple work into complicated accounting software.

Create and manage invoices, organize receipts, generate PDFs, review business reports, and
export your records when you need a copy outside the app.

Built for practical day-to-day work:

- Create and manage invoices
- Keep receipts organized with the records they support
- Generate professional PDF documents
- Review reports that make business activity easier to understand
- Export records and documents when you choose

BillingBird is local-first. Core invoice, receipt, report, and export workflows are designed
to work with records stored on your device, so you stay in control of your business data.

BillingBird is designed for business owners who want a focused way to stay on top of billing
and paperwork from one workspace.

Character count: 885 of 4,000, including paragraph breaks and list markers.

Do not add Google Drive backup, BillingBird Cloud, online payments, or Google Play Billing to
this description until the exact Android App Bundle intended for release proves that feature
is present, working, and covered by the privacy policy and Play declarations.

### Release Notes Draft

Initial release: Create and manage invoices, organize receipts, generate PDFs and reports,
and export your business records from a local-first workspace.

## Store Asset Requirements And Inventory

Google Play requirements can change. Recheck the official preview-asset guidance immediately
before upload.

| Asset | Current Google Play requirement | Repository inventory | Next action |
| --- | --- | --- | --- |
| App icon | Required; 512 x 512 px, 32-bit PNG with alpha, no larger than 1,024 KB | Draft present: `store-assets/google-play/app-icon-512.png` (512 x 512 32-bit PNG with alpha, 274 KB) | Review against Play's icon treatment and the release-approved Android source before upload. |
| Feature graphic | Required; 1,024 x 500 px, JPEG or 24-bit PNG without alpha | Draft present: `store-assets/google-play/feature-graphic-1024x500.jpg` (1,024 x 500 JPEG, 106 KB, no alpha) | Review branding and safe-area composition before upload. |
| Phone screenshots | At least two screenshots are required across supported device types; JPEG or 24-bit PNG without alpha, each side 320–3,840 px, with the long side no more than twice the short side | Missing | Capture at least four polished 1,080 x 1,920 portrait screenshots from the release build for stronger merchandising eligibility. |
| Tablet screenshots | Up to eight per supported tablet type; four large-screen screenshots at 1,080–7,680 px and 9:16 or 16:9 are recommended when tablet support is shipped | Missing | Capture only after tablet behavior is verified in the release build. |
| Screenshot alt text | Recommended for every graphic asset, 140 characters or fewer | Missing | Draft from the final screenshots and describe the visible task, not decorative details. |
| Preview video | Optional for apps; must use a public or unlisted embeddable YouTube URL with ads disabled and no age restriction | Not planned | Skip for the initial listing unless release-ready footage is available. |

Recommended screenshot story, using only release-proven screens:

1. Create and review an invoice.
2. Organize receipts.
3. Generate or preview a PDF.
4. Review a business report.
5. Export records or documents.

Do not show sample customer details, real financial information, notifications, personal
accounts, test credentials, or features that are absent from the release artifact.

Official asset reference:
https://support.google.com/googleplay/android-developer/answer/9866151

## Play App-Content Checklist

Complete every questionnaire Play Console presents for the exact Android App Bundle. Treat
the release artifact and its SDK/network audit as the source of truth; do not copy answers
from the Apple build or from planned Android features.

- [x] Privacy policy URL is live over HTTPS; recheck after the local email update is deployed.
- [x] Support URL is live over HTTPS; recheck after the local email update is deployed.
- [x] Account-deletion URL is live over HTTPS; recheck after the local email update is deployed.
- [ ] App access: confirm whether every reviewed screen works without sign-in. If any released
  feature requires an account, provide complete reviewer access instructions without placing
  credentials in this repository.
- [ ] Ads: inspect the release artifact and declare whether it contains ads or an ads SDK.
- [ ] Content rating: complete the IARC questionnaire from the released app's actual content.
- [ ] Target audience and content: business audience is the intended positioning; confirm the
  precise age groups and whether the app is not designed for children.
- [ ] Data safety: audit app code, bundled SDKs, permissions, network traffic, support flows,
  exported files, and any account/payment functionality before answering collection, sharing,
  encryption, deletion, and data-purpose questions.
- [ ] Account deletion: if the Android release lets users create a BillingBird account, verify
  both an in-app deletion path and the public web path against the release build. If the release
  has no account creation, answer the Play form based on that artifact and keep the listing copy
  free of unshipped cloud claims.
- [ ] News app declaration: verify and answer from the released app; expected answer is no.
- [ ] Government app declaration: verify and answer from the released app; expected answer is no.
- [ ] Financial features declaration: review the current Play questionnaire carefully. Invoicing
  and business recordkeeping must be classified from actual functionality; do not imply banking,
  lending, investing, money transfer, or payment processing unless shipped.
- [ ] Health app declaration: verify and answer from the released app; expected answer is no.
- [ ] Permissions and sensitive APIs: reconcile every manifest permission and Play declaration
  with an active, user-visible feature in the release build. The release declares CAMERA,
  READ_CONTACTS and WRITE_CONTACTS (client import and save-back, on the device only),
  POST_NOTIFICATIONS, RECEIVE_BOOT_COMPLETED, WAKE_LOCK, VIBRATE, USE_BIOMETRIC,
  USE_FINGERPRINT, INTERNET, ACCESS_NETWORK_STATE, the two legacy external-storage entries
  and `com.android.vending.BILLING`; the exact list is `config/android-data-flow-inventory.json`
  in the Android repository. The public privacy policy discloses Contacts in its "Device Contacts"
  section; republish the privacy page before submission.
- [ ] Store listing contact details: enter and verify `contact@deadstick.net` as the customer-facing
  support email, subject to Play's email verification step.
- [ ] Developer account details: use the verified DeadStick Digital organization information and
  keep Google's private account-contact address separate from the public app-support address where
  practical.
- [ ] Package and release identity: verify package name, app signing enrollment, upload key
  custody, version name, and monotonically increasing version code before any upload. The
  first signed candidate is version name `1.0.4`, version code `2` (`app.json`, decision D7);
  the signed AAB comes from `npm run sign:android:release` and its receipt
  `build/android-release-signed-receipt.json`.
- [ ] Testing: use an internal track for the first approved upload, then closed testing for
  controlled validation before any production rollout.
- [ ] Billing and subscriptions: do not configure or advertise Play Billing or RevenueCat products
  until the release artifact implements and validates purchase, restore, cancellation, renewal,
  refund, revocation, and entitlement behavior.

Official app-content references:

- Data safety: https://support.google.com/googleplay/android-developer/answer/10787469
- Account deletion: https://support.google.com/googleplay/android-developer/answer/13327111
- Developer contact information: https://support.google.com/googleplay/android-developer/answer/10840893
- Create and set up an app: https://support.google.com/googleplay/android-developer/answer/9859152

## Publication Gate

Before any Play Console upload, submission, or release:

1. Obtain explicit owner approval for the external action.
2. Verify the exact Android release artifact and all claims in this listing.
3. Publish and recheck the local support-email update on all three public pages.
4. Complete the missing store assets from the release build.
5. Finish the app-content questionnaires from artifact-backed evidence.
6. Record the package name, version, signing mode, track, countries, and final validation result
   in the Android repository handoff without storing secrets.
