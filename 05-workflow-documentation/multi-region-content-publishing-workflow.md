# Content Publishing Workflow — Multi-Region Documentation

**Document type:** Workflow Documentation  
**Version:** 1.0  
**Author:** Anugraha S  
**Last updated:** April 2026  

---

## Overview

This document describes the end-to-end workflow for publishing structured content across multiple regional markets. It covers the roles involved, the stages of the publishing pipeline, quality checkpoints, and escalation paths for common issues.

This workflow applies to structured documentation published to a centralised repository and distributed to regional marketplace endpoints.

---

## Scope

| In scope | Out of scope |
|----------|-------------|
| Content creation and authoring | Graphic design and visual asset production |
| Translation and localisation review | Legal review and regulatory approval |
| QA and content validation | IT infrastructure and system configuration |
| Publishing and deployment | Post-publication analytics |

---

## Roles and responsibilities

| Role | Responsibility |
|------|---------------|
| **Content Author** | Creates and updates structured documentation. Responsible for accuracy, tone, and format compliance. |
| **Content Reviewer** | Reviews authored content against style guide and client SOPs before it moves to QA. |
| **QA Specialist** | Validates content against technical requirements, checks for broken links, formatting errors, and completeness. |
| **Localisation Coordinator** | Manages translation handoff for non-English markets. Coordinates with translation vendors and reviews translated output. |
| **Publishing Specialist** | Executes the final publish to the content repository. Verifies successful deployment across all target regions. |
| **Content Manager** | Oversees the workflow, resolves escalations, and approves high-risk changes before publishing. |

---

## Workflow stages

### Stage 1 — Content request and intake

**Trigger:** A content request is raised via the project management system (new content, update, or correction).

**Steps:**
1. Content Manager reviews the incoming request and classifies it as: new content, minor update, major update, or urgent correction.
2. Request is assigned to a Content Author with a due date based on priority level.
3. Author confirms receipt and acknowledges the scope.

**Output:** Assigned content task with clear brief, deadline, and any reference materials attached.

---

### Stage 2 — Authoring

**Owner:** Content Author

**Steps:**
1. Author reviews the brief, reference materials, and any existing content on the topic.
2. Author creates or updates the content in the authoring tool (oXygen XML Editor for DITA content, or the relevant CMS for other formats).
3. Content is written according to the applicable style guide and topic type requirements.
4. Author performs a self-review checklist before submitting for review:
   - Is the content accurate and complete?
   - Does it follow the correct topic type structure (concept / task / reference)?
   - Are all steps numbered and in logical sequence?
   - Is tone consistent with the client's voice guidelines?
   - Are there any broken internal links or missing references?
5. Author submits content for review and updates the task status.

**Output:** Draft content ready for review.

---

### Stage 3 — Content review

**Owner:** Content Reviewer

**Steps:**
1. Reviewer picks up the submitted content within the agreed SLA (typically 1 business day for standard content, 4 hours for urgent corrections).
2. Reviewer checks content against:
   - Client tone of voice and style guide
   - Structural requirements for the content type
   - Factual accuracy against approved source materials
   - Consistency with existing published content on related topics
3. Reviewer either:
   - **Approves** the content and moves it to QA, or
   - **Returns** the content to the Author with specific comments for revision.
4. If returned, Author revises and resubmits. The review loop repeats until approval.

**Output:** Approved content ready for QA.

---

### Stage 4 — Quality assurance

**Owner:** QA Specialist

**Steps:**
1. QA Specialist validates the content against a defined QA checklist:
   - Formatting is correct and renders as expected in the target output format
   - All internal and external links are functional
   - Images or media references (if applicable) are correctly attached
   - Metadata (title, tags, product associations) is complete and accurate
   - Content is free of placeholder text or incomplete sections
2. For multi-region content, QA verifies that regional variants are correctly tagged and routed to the appropriate marketplace endpoints.
3. QA Specialist either:
   - **Passes** the content and routes it to Publishing, or
   - **Flags** issues and returns to the Author or Reviewer for correction.

**Output:** QA-cleared content ready for localisation (if applicable) or publishing.

---

### Stage 5 — Localisation (for non-English markets)

**Owner:** Localisation Coordinator  
**Applies to:** Content destined for EU-5, CA (French), or other non-English regional markets.

**Steps:**
1. Localisation Coordinator exports the approved English source content and prepares a handoff package for the translation vendor.
2. Translation is completed by the vendor within the agreed turnaround time.
3. Localisation Coordinator reviews the translated content against the source for:
   - Completeness (no segments missing or untranslated)
   - Consistency with previously approved terminology
   - Correct formatting preserved from the source
4. Approved translations are returned to QA for a final check before publishing.

**Output:** Translated and reviewed content for all target markets.

---

### Stage 6 — Publishing

**Owner:** Publishing Specialist

**Steps:**
1. Publishing Specialist receives QA-cleared content for all applicable regions.
2. Content is uploaded to the publishing system (e.g., AJUDA repository or equivalent CMS).
3. Publishing Specialist sets the correct regional routing, effective date, and visibility settings.
4. A test publish is performed in the staging environment before pushing to production (for major updates only).
5. Content is published to production.
6. Publishing Specialist verifies the live content renders correctly across all target regions.
7. Task status is updated to **Published** and the content requester is notified.

**Output:** Content live across all target markets.

---

## Error and escalation handling

| Issue | First response | Escalation path |
|-------|---------------|-----------------|
| Factual error identified post-publish | Author creates correction task immediately. Urgent priority. | Content Manager notified if correction affects more than one region. |
| Translation vendor misses deadline | Localisation Coordinator contacts vendor and reports to Content Manager. | Content Manager decides whether to delay publish or release English-only content first. |
| Publishing system failure | Publishing Specialist logs the issue with IT support. | Content Manager and IT escalate based on severity. |
| Content approved with incorrect formatting | QA flags for correction. Author and Reviewer both notified. | If systemic, Content Manager initiates a style guide review. |

---

## SLA reference

| Content type | Authoring | Review | QA | Localisation | Total (EN only) |
|-------------|-----------|--------|-----|-------------|-----------------|
| New article (standard) | 2 days | 1 day | 1 day | 3 days | 4 days |
| Minor update | 4 hours | 4 hours | 2 hours | 1 day | 1 day |
| Urgent correction | 1 hour | 1 hour | 30 mins | 4 hours | 2.5 hours |

---

## Related documents

- Content Style Guide
- DITA Authoring Standards and SOPs
- Translation Vendor Briefing Template
- QA Checklist (full version)

---

*This document is a technical writing portfolio sample by Anugraha S, demonstrating workflow documentation for a multi-region content publishing operation.*
