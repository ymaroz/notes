# Q-Components Discussion

Q-Components-React is a new repository we are developing to create standardized components for use in other client repositories as well as demonstrating/documenting Front End standards and code examples.

## Design and Requirements/Specifications

We should be putting some consideration into both the design and specifications for any given component. The goal is to create longterm, stable components that consume simple, reusable interfaces.

## Possible Common Utilities

- Spacing (margin/padding)
- Flex (grid?)
- Positioning?
- Elevation/Shadows (can create a scale for depth of shadow)
- Border/Border-Radius

## Possible Element List

This is a list of common elements that we could/should be focusing on early. Many of these can/should be extended to build other more complex components. Items with a `*` exist within the library already.

- Nav\*
- Box/Container
  - Card
  - Page
- Button/Link
  - variants (Normal/Round/Outlined/Unstyled/WithIcon?)
  ![buttons][button-variants]
- Footer
- Error
  - Banner
  - Toast
- Tooltip
- Accordion\*
- Menu\*
- Modal\*
- Spinner\*
- Form Related
  - Form
  - Field
    - Standard input types (text, number, checkbox)
    - Extended types (range, toggle)
    - Third party types (date-picker, select) - should eventually be replaced
    - Special Questionnaire types (inputs from questions/fields not already covered)

[button-variants]: ./assets/button-variants.png
