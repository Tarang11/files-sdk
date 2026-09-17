---
"files-sdk": minor
---

Support Vercel Blob Signed URLs in the `vercelBlob()` adapter. In `access: "private"` mode, `url()` now mints a presigned GET scoped to the key that honors `expiresIn` (1 hour default, new `defaultUrlExpiresIn` option) instead of throwing, and `capabilities.signedUrl.supported` reports `true`, so the gateway redirects private downloads to storage instead of proxying them. `signedUploadUrl()` now returns a presigned PUT in either mode, with `contentType` and `maxSize` enforced by Vercel's CDN; a positive `minSize` throws because Vercel has no minimum-size constraint. Requires `@vercel/blob` 2.4.0 or later, which is already the adapter's peer range.
