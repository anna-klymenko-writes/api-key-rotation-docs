# api-key-rotation-docs

This repo is a docs-as-code writing sample: one page on rotating a Stripe API key without breaking live traffic, with navigation, an automated check and an open PR.

## Reviews

   - The **technical reviewer** is accountable that the steps are safe to follow in production and match the current product.
   - The **docs reviewer** is accountable for style, terms and consistency with the rest of the docs.
The author merges only after both reviewers approved.

## Keeping samples and screenshots current

The author adds screenshots and code samples after the text is approved. The author updates them when the feature changes. 

**When to change:** The release notes describing the feature, change log, or a request for change from an SME.

## What I didn't automate, and why

**What:** checking that the steps still match the real Dashboard.

**Why:** a linter checks format, not whether the product behaves as described. Only someone testing in the sandbox can confirm it, which is how I verified this page.

## What I'd do next

   - Add screenshots.
   - Write the API keys overview and Handle a leaked API key pages.
   - Add automated checks: link checker and Vale for style guide rules.

