---
Use Case Name: "{Use Case Name}"
Status: { Draft | Initialized }
Project: "[{Project Name}](../projects/{Project_Name}.md)"
---

<!-- AI_TEMPLATE_INSTRUCTIONS:
This template requires completion of ALL sections below.
- Replace {Use Case Name} in frontmatter with a unique use Use Case Name.
- Replace {Project Name} and {Project_Name} with the actual project name and link to the parent project document
- Set Status to "Planning" initially
- Do not leave placeholder text like "TBD", "TODO", or "[To be determined]"
- Follow VALIDATION guidance in each section (word counts and criteria are targets, not strict limits)
- Refer to inline EXAMPLES (✓ good, ✗ avoid) for quality guidance
- All sections marked AI_REQUIRED must contain substantive, specific content
- Prioritize clarity and specificity over length
- This use case provides detailed HOW (step-by-step actor-system interactions) while the parent project document provides high-level WHAT (features and goals)
- Cross-reference the linked project to ensure alignment with project scope, goals, and stakeholders
-->

## Actors

<!-- AI_GUIDANCE: Actors interact with the system to accomplish the use case goal.
Primary actors initiate the use case or receive direct value from it.
Secondary actors support the use case but don't initiate it or receive primary value.
Use role types (Customer, Administrator), not individual names (John Smith).
-->

### Primary Actors

<!-- AI_REQUIRED: Primary Actors
VALIDATION:
- Target: 1-3 primary actors who directly interact with the system
- Format: Actor role with brief description of their involvement
- Use role types, not individual names
- Primary actors initiate the use case or achieve the goal
- Can include systems, or services in rare circumstances

EXAMPLES:
✓ Good: 
"- Customer: Registered user who browses products and completes purchases
 - Customer Support Agent: Staff member who assists customers and processes returns"

✗ Avoid: "User, Admin" (Too generic, lacks context and descriptions)
-->

### Secondary Actors

<!-- AI_REQUIRED: Secondary Actors
VALIDATION:
- List actors who support the use case but don't initiate it
- Include systems, services, or roles that provide data or receive notifications
- Write "None" if there are no secondary actors

EXAMPLES:
✓ Good:
"- Payment Gateway: Processes credit card transactions and returns authorization
 - Inventory System: Provides real-time product availability data"

✓ Good: "None"

✗ Avoid: Leaving this section empty without "None"
-->

## Description

<!-- AI_REQUIRED: Description
VALIDATION:
- Target length: 2-4 sentences
- Summarize WHAT this use case accomplishes from the actor's perspective
- Include the goal/outcome the actor is trying to achieve
- Focus on the end result, not the detailed steps (those go in Activity section)

EXAMPLES:
✓ Good: "A customer adds items to their shopping cart and proceeds to checkout. The system validates inventory availability, processes payment through the payment gateway, creates an order record, and sends confirmation email to the customer."

✗ Avoid: "This use case handles customer checkout." (Too vague, lacks specific outcome)
-->

## Priority

<!-- AI_REQUIRED: Priority
VALIDATION:
- Set to High, Medium, or Low
- Include 1-2 sentence justification explaining why
- Consider business value, dependencies, and risk

EXAMPLES:
✓ Good: "High - Checkout is a critical revenue-generating function. Any failures directly impact sales and customer satisfaction. Dependencies include payment processing and inventory management."

✗ Avoid: "High" (No justification provided)
-->

## Conditions

### Preconditions

<!-- AI_REQUIRED: Preconditions
VALIDATION:
- List conditions that MUST be true before this use case can start
- Focus on system state, data existence, or actor permissions
- Be specific and testable
- Use bullet points

EXAMPLES:
✓ Good:
"- Customer has items in their shopping cart
 - Customer is logged in or has provided guest checkout information
 - Payment gateway is operational and accessible
 - Selected items are in stock and available for purchase"

✗ Avoid: "System is ready" (Too vague, not testable)
-->

### Postconditions

<!-- AI_REQUIRED: Postconditions
VALIDATION:
- List the state of the system after successful completion
- Should be specific and measurable/verifiable
- Describe what changed or was created
- Use bullet points

EXAMPLES:
✓ Good:
"- Order record created in the database with unique order ID
 - Payment has been authorized and captured
 - Inventory quantities updated to reflect purchased items
 - Confirmation email sent to customer
 - Order appears in customer's order history"

✗ Avoid: "Process completed successfully" (Too vague, not measurable)
-->



## Completion Checklist

<!-- AI_CHECKPOINT: Verify all items below before marking this document complete -->

- [ ] UseCase_ID specified in frontmatter (format: UC-XXX)
- [ ] Status set to "Planning"
- [ ] Project link updated to reference actual project file
- [ ] Primary Actors: 1-3 actors with role descriptions
- [ ] Secondary Actors: Listed with descriptions (or "None")
- [ ] Description: 2-4 sentence summary of use case goal and outcome
- [ ] Priority: High/Medium/Low with justification
- [ ] Preconditions: Specific, testable conditions listed
- [ ] Postconditions: Specific, measurable outcomes listed
- [ ] No placeholder text remains (no "TBD", "TODO", or "[To be determined]")
- [ ] All content is specific and actionable
- [ ] Document aligns with parent project scope and stakeholders