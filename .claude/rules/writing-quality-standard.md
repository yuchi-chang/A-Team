---
name: Writing Quality Standard
description: Specify writing style, language requirements, and quality standards for all generated .md files
---

# Writing Quality Standard

## Applicability

- Applies to: `agent-writer`, `skill-writer`, `rule-writer`, `prompt-optimizer`

## Rule Content

### Tone and Style

All generated .md files must use imperative sentences as the primary tone.

- Correct: "You must confirm input completeness after receiving a task"
- Incorrect: "This role should confirm input completeness after receiving a task"
- Incorrect: "It is recommended to confirm input completeness after receiving a task"

### Prohibited Vague Words

The following words are prohibited in .md files unless immediately followed by clear judgment criteria:

Prohibited words: "try to", "appropriately", "reasonably", "if needed", "as appropriate", "roughly", "probably", "things like that"

- Violation: "Try to maintain code quality"
- Correct: "All code must pass linter checks and have test coverage no less than 80%"
- Allowed: "Reasonable error handling (defined as: every public function must have error return with context)"

### Length Limits

- Single agent .md: No more than 300 lines
- Single skill .md: No more than 200 lines
- Single rule .md: No more than 100 lines
- If content exceeds limits, must split into multiple files or use references for detailed content

### Example Requirements

- Each skill .md must contain at least one input/output example
- Each rule .md must contain at least one violation scenario description

## Violation Determination

- Using descriptive tone instead of imperative sentences → Violation
- Prohibited vague words appear without accompanying judgment criteria → Violation
- File exceeds length limit → Violation
- skill .md has no examples → Violation
- rule .md has no violation determination → Violation

## Exceptions

This rule has no exceptions.
