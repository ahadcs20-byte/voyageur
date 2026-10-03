# Recovery review

Inspected on 4 October 2026 (Malaysia time).

## Recovered

- Export is a readable ZIP archive; bot configuration parses as JSON.
- Four workflows: Main, Error, Timeout, and Conversation End.
- Main includes Start, End, one autonomous agent node, and a video annotation.
- Main-node instructions describe a French-themed assistant answering in English, with accommodation, attractions, and food planning phases.
- One embedded HTML travel knowledge file (86,019 bytes), with indexing-completed metadata.
- No configured secret values were found in the `configVariables` object; it is empty.

## Check before presenting the project

1. The agent instructions list seven destinations, while the knowledge text lists additional destinations. Align intended coverage after testing.
2. Budget categories differ between the instructions and knowledge text. Check whether recommendations consistently map Low / Medium / High to dataset categories.
3. The legacy KnowledgeAgent flag is disabled, but the autonomous node has a knowledge-search tool. This flag alone does not prove retrieval is broken; verify retrieval in the emulator.
4. The main node's knowledge-search selector is empty. Verify which knowledge sources this configuration actually searches in the live bot.
5. Entity and intent descriptions in the knowledge source are text, not configured custom list/pattern entities in the export.
6. Travel data accuracy, source attribution, live demo availability, error behavior, and cleaned-export import compatibility remain unverified.

## Publication preparation

The cleaned export removes session/editor metadata but preserves operational IDs. Keep the original private. The prompt includes a third-party profile-image URL; review that reference and the knowledge data's source permissions before public release. No repository license is assigned because ownership and third-party rights have not been established.
