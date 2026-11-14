# UI Copy and Microcopy

Read for buttons, labels, empty states, success messages, errors, placeholders, helper text, confirmations, onboarding, loading states, and permission prompts. These rules are language-neutral. For wording in a specific language, also read the matching language file.

> Adapted from [bahasa-indonesia-plain](https://gist.github.com/orepras/3e1ca8974fc51d11825f142fa6a66635) and [english-plain](https://gist.github.com/orepras/61f07724a6d02d3f319e3371867dad6a) by [orepras](https://github.com/orepras). See `CREDITS.md` in the source repository for revisions, permission status, and changes.

## Buttons and Calls to Action

- Start with a clear active verb and name the object: "Save document", "Send application", "Continue".
- Avoid "OK", "Submit", "Process", "Yes", and "No" when a specific verb fits.
- Name the outcome when the action is consequential: "Delete 3 files", not "Confirm".
- Keep the button label parallel with the heading or instruction that leads to it.

## Empty States

Explain the condition and offer one next step: "No projects yet. Start by creating your first project."

Do not blame the reader for the empty state. Do not use a decorative illustration as the only explanation.

## Success Messages

Keep it short, warm, and concrete: "Your profile is updated." Not "Operation completed successfully."

Say what changed when the reader needs to know: "Invitation sent to 3 people."

## Error Messages

Include three things:

1. What happened, in plain words.
2. That the reader is not at fault, without over-apologizing.
3. What to do next.

"Your card was declined. Check the expiry date or try another card." Not "Error 402: Payment required."

Keep the error code when support needs it, but put it after the plain explanation.

Do not expose stack traces, internal IDs, or database errors to the reader. Log them; do not display them.

## Placeholders and Labels

- Put the label above the field. Never use the placeholder as the label.
- Use the placeholder for a format example: "For example, name@email.com".
- Keep the label visible when the reader types. A disappearing placeholder erases the question.

## Helper Text and Tooltips

Answer one question in one short sentence: "Why do you need this?" or "What goes here?"

Put the helper text where the reader needs it, not in a tooltip that requires discovery.

## Destructive Confirmations

State the consequence and whether it can be undone: "Delete this project? Its 12 files will be permanently removed and cannot be recovered."

Name the object and the quantity. Do not use "Are you sure?" as the only content.

## Onboarding

Invite, don't require: "Let's set up your profile" is warmer than "Complete your profile to continue."

Explain why a step matters before asking for information. Do not use a progress bar as a substitute for a reason.

## Loading and Waiting

Say what is happening and, when known, how long it will take: "Uploading 3 files. About 20 seconds left."

Do not show an indeterminate spinner with no text for a long operation.

## Consent and Permissions

Explain what you ask for and why, in one plain sentence, before the system prompt appears: "Allow notifications so we can tell you when your report is ready."

Do not pre-check consent. Do not bundle unrelated permissions into one prompt.

## Localization

- Leave room for text expansion. A string that fits in English may need 30% more space in another language.
- Do not build a sentence from concatenated fragments. Translators need the whole sentence and its variables.
- Keep variable names and placeholders intact. Do not put grammar inside code.
- Avoid puns, idioms, and culture-specific references that cannot transfer.
- Test the longest translated string, not only the source language.

## Check Before Shipping

- Does every button name a specific action?
- Does every error say what happened and what to do?
- Does every destructive action state the consequence?
- Is every empty state explaining the next step?
- Is any string using "OK", "Submit", or "Process" where a verb would be clearer?
- Does the copy survive translation without losing meaning?
