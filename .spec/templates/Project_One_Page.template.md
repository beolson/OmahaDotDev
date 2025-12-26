---
Product: "{Product Name}"
DocumentType: "Project_One_Page"
Status: {Planning | Implementing | Completed}
---

<!-- AI_TEMPLATE_INSTRUCTIONS:
This template requires completion of ALL sections below.
- Replace {Product Name} in frontmatter with the actual product/project name
- Se the Status to "Planning" 
- Do not leave placeholder text like "TBD", "TODO", or "[To be determined]"
- Follow VALIDATION guidance in each section (word counts and criteria are targets, not strict limits)
- Refer to inline EXAMPLES (✓ good, ✗ avoid) for quality guidance
- All sections marked AI_REQUIRED must contain substantive, specific content
- Prioritize clarity and specificity over length
-->

## Problem Alignment

<!-- AI_REQUIRED: This section is mandatory. Complete all subsections below. -->

<!-- AI_REQUIRED: This section is mandatory. Complete all subsections below. -->

<!-- AI_REQUIRED: Problem Statement
VALIDATION:
- Target length: 1-2 sentences (approximately 30-60 words)
- Must include customer/business impact or risk
- Must reference evidence, data, or insights that support the problem
- Avoid describing solutions - focus only on the problem
- Should be understandable to someone outside the immediate team

EXAMPLES:
✓ Good: "Users abandon 40% of transactions when required to create an account before checkout, resulting in significant revenue loss. User research shows friction from password requirements and form length as primary factors."

✗ Avoid: "We need to improve the checkout process." (Too vague, no evidence, no quantified impact)

✗ Avoid: "We should implement guest checkout with optional account creation post-purchase." (Describes solution, not problem)
-->

### High Level Approach

<!-- AI_REQUIRED: High Level Approach
VALIDATION:
- Target length: 2-4 sentences (approximately 40-80 words)
- Describes the conceptual shape/direction, not detailed implementation
- Should help others "see the same shape" when envisioning the solution
- Analogies and metaphors are encouraged for clarity
- Avoid specific technology choices or implementation details

EXAMPLES:
✓ Good: "A streamlined checkout flow that removes account creation as a blocker, similar to how ride-sharing apps let you book first and set up your profile later. Users complete their purchase as guests, then receive a gentle prompt to claim their account for order tracking and future convenience."

✓ Good: "Think of it like a fast-pass lane at an airport - users can move quickly through the express path without stops, while still having the option to enroll in the full program afterward."

✗ Avoid: "We'll use a modal dialog with OAuth integration and store session data in Redis with a 24-hour TTL." (Too implementation-specific, missing the conceptual shape)
-->

### Goals

<!-- AI_REQUIRED: Goals
VALIDATION:
- Target: 2-5 goals (avoid too many; stay focused)
- Must be in priority order (most important first)
- Mix of measurable outcomes (metrics, KPIs) and qualitative goals (user feelings, team impact)
- Each goal should be a single, focused outcome
- Use active, outcome-oriented language
- Avoid listing features or tasks (those belong in Key Features)

EXAMPLES:
✓ Good:
"1. Increase checkout completion rate from 60% to 80% within first quarter post-launch
2. Users feel the checkout process is simple and frictionless (NPS target: +40)
3. Reduce account creation abandonment from 35% to <5%
4. Decrease time-to-first-purchase for new users by 50%"

✗ Avoid:
"1. Build a better checkout experience
2. Add guest checkout option
3. Make it fast and reliable
4. Improve conversion rates"
(First two are features/tasks not goals; third is vague; fourth lacks specificity and measurement)
-->

### Non Goals

<!-- AI_REQUIRED: Non Goals
VALIDATION:
- Target: 1-4 items (enough to clarify scope boundaries)
- Each non-goal must include a brief rationale or explanation
- Should address likely assumptions or expectations
- Helps prevent scope creep and misaligned expectations
- May reference future phases if deferring, not eliminating

EXAMPLES:
✓ Good:
"- Multi-currency pricing: Out of scope for v1; 95% of users transact in USD. Will revisit based on international adoption metrics.
- Social login integration (Google, Facebook): Adds complexity and privacy concerns; focus on email-based guest flow first. Evaluate in Q2 based on user requests.
- Saved payment methods for guest users: Requires account infrastructure; conflicts with streamlined guest experience goal."

✗ Avoid:
"- We won't support international users
- No social login
- Not doing mobile optimization"
(Lacks rationale, context, and consideration of why these are excluded)
-->

## Solution Alignment

### Key Features

<!-- AI_REQUIRED: Key Features
VALIDATION:
- Target: 3-7 features (enough to define the solution perimeter without over-specifying)
- Must be in priority order (most critical first)
- Each feature should be independently valuable
- Defines the boundaries of the solution space
- Avoid implementation details; focus on capabilities and value
- Can include "Future" items for later phases if they inform current design decisions
- Consider if features can be broken down for independent shipping

EXAMPLES:
✓ Good:
"1. Guest checkout flow with minimal required fields (email, shipping, payment)
2. Post-purchase account creation with single-click claim using order email
3. Order tracking for guests via email link (no login required)
4. Persistent cart across guest sessions using browser storage
5. Optional account benefits messaging at strategic points (non-blocking)
6. Future: One-click reorder for claimed accounts (Phase 2)"

✗ Avoid:
"1. Better user experience
2. Fast performance
3. Secure checkout
4. Mobile responsive design"
(Too vague, not actionable features; confuses quality attributes with capabilities)
-->

### Key Flows

<!-- AI_REQUIRED: Key Flows
VALIDATION:
- Target: 1-3 primary end-to-end flows
- Each flow should cover the complete customer journey from start to finish
- Include both happy path and critical edge cases/error scenarios
- Format can be: prose narrative, numbered steps, acceptance criteria, or references to diagrams
- Should be specific enough to guide implementation
- Naturally evolves with design/engineering collaboration over time
- Edge cases should address realistic failure modes and recovery paths

EXAMPLES:
✓ Good:
"**Flow 1: Guest Checkout to Account Claim**
1. User adds items to cart, clicks 'Checkout'
2. System presents guest checkout form (email, shipping address, payment method)
3. User completes purchase without creating account or password
4. System sends order confirmation email with 'Claim Your Account' link
5. User clicks link within 7 days, sets password in single step
6. Account created with order history pre-populated, user logged in automatically

**Edge Case: Email Already Has Account**
- If guest email matches existing account, show 'Sign in to continue' with password reset option
- After login, merge guest cart with account cart (user chooses to combine or replace)
- Complete checkout as authenticated user with saved preferences

**Flow 2: Guest Order Tracking**
1. User receives order confirmation email with unique tracking link
2. User clicks link, views order status without login (token-based authentication)
3. Page shows delivery timeline, tracking number, and support options
4. Gentle reminder about account benefits (order history, faster future checkouts) with single-click claim option"

✗ Avoid:
"User goes to checkout, completes their order as a guest, and can create an account later if they want. They can also track their order."
(Lacks detail, no step-by-step flow, no edge cases, not actionable for implementation)
-->

---

## Completion Checklist

<!-- AI_CHECKPOINT: Verify all items below before marking this document complete -->

- [ ] Product name specified in frontmatter (replaced "{Product Name}")
- [ ] Problem Alignment: Problem statement with evidence and impact (target: 1-2 sentences)
- [ ] Problem Alignment: High level approach with conceptual shape (target: 2-4 sentences)
- [ ] Goals: 2-5 prioritized, outcome-oriented goals (mix of measurable and qualitative)
- [ ] Non-Goals: 1-4 items with rationale explaining scope boundaries
- [ ] Key Features: 3-7 prioritized features defining solution perimeter
- [ ] Key Flows: 1-3 complete end-to-end flows with edge cases
- [ ] No placeholder text remains (no "TBD", "TODO", "[To be determined]", etc.)
- [ ] All content is specific and actionable (avoid vague statements)
- [ ] Document follows validation guidance in each section


