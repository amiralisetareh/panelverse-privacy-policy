# TYTO — Policies & Legal

**The Keeper of Stories**  
Official policy documents for [@titoarchivebot](https://t.me/titoarchivebot), previously known as PanelVerse.  
**Effective date:** 17 November 2026 · **Version:** 1.0

## Canonical documents
- [Privacy Policy](PRIVACY_POLICY.md)
- [Terms of Service](TERMS_OF_SERVICE.md)
- [Copyright & Rights Policy](COPYRIGHT_POLICY.md)
- [Community Guidelines](COMMUNITY_GUIDELINES.md)
- [Data Deletion Policy](DATA_DELETION.md)

The short legacy files `PRIVACY.md`, `TERMS.md`, and `COPYRIGHT.md` remain as pointers to the canonical documents.

## Scope verified against source
These documents were drafted after inspecting `amiralisetareh/panelverse_v2` on 17 November 2026. The inspected build:
- does not create persistent accounts for ordinary bot users or store their profile/message history in its own SQLite database;
- stores catalogue records and administrator-managed archive content;
- stores files and technical/extracted metadata through the protected web-admin ingestion workflow;
- uses Telegram identifiers for administrator authorization and keeps temporary admin workflow state in process memory;
- shows an AI assistant placeholder, but does not implement active AI conversations.

The operator must keep the documents aligned with the actual deployed build.

## Launch checklist
- [ ] Add a verified, monitored private privacy/support contact to the policies and bot profile.
- [ ] Add a private copyright-report contact; never direct rights holders to post personal information in public GitHub issues.
- [ ] Verify the public GitHub Pages URL and use the direct privacy-policy page in BotFather.
- [ ] Confirm the production deployment matches the inspected source.
- [ ] Serve the admin interface over HTTPS and never commit bot/admin tokens.
- [ ] Update the policies before enabling AI processing, analytics, user accounts, public uploads, comments, payments, or new third-party services.

## Important
This repository is a public transparency resource, not legal advice or a statement of compliance with any particular jurisdiction. Obtain legal review for the operator's location and intended audience before relying on it as a complete legal framework.

A verified private contact was not provided, so the policy documents explicitly mark that as a launch requirement rather than inventing an address.
