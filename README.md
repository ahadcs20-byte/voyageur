# Voyageur — Malaysia Travel Assistant

Voyageur is a Botpress conversational AI project for personalized Malaysia travel planning. Its agent instructions guide a conversation through accommodation, attractions, and food recommendations using a supplied travel knowledge base.

This repository documents a recovered academic project. The export has been inspected locally; live behavior and re-import have not yet been verified. This is a Botpress project, so it runs through Botpress rather than as a standalone Python or JavaScript application.

## Demo

[Open the shared webchat](https://cdn.botpress.cloud/webchat/v3.7/shareable.html?configUrl=https://files.bpcontent.cloud/2026/04/01/08/20260401083202-0EDPDYQT.json)

The link was supplied by the project owner. Availability and responses need manual confirmation.

## Designed behavior

- Gather destination and stay duration.
- Ask whether accommodation is already arranged; otherwise gather budget and amenities.
- Recommend attractions based on interests, accessibility needs, and proximity to accommodation.
- Suggest food places based on cuisine, budget, and location.
- Handle users who ask about food or attractions first.
- Answer in English with occasional translated French expressions.
- Use knowledge-base information and acknowledge unsupported requests.

These are configured instructions, not measured guarantees. No booking, live pricing, or map routing integration was found in the inspected main workflow.

## Technology and architecture

Botpress Studio, an autonomous AI node, and a rich-text travel knowledge source. The Main workflow sends the conversation from Start to AutonomousNode. The node has a Search Knowledge Bases tool. Separate Error, Timeout, and Conversation End workflows are also present.

The export contains no registered custom list or pattern entities. Entity and intent descriptions appear in the knowledge text; these should not be described as separately implemented entity extractors.

## Repository files

- `botpress/voyageur-metadata-cleaned.bpz`: export copy with session metadata, historical version references, table editor identities, and a stale generated bot summary removed. Operational bot/file IDs remain. Import compatibility has not been tested.
- `docs/agent-instructions.md`: original main-node instructions in readable form.
- `knowledge/malaysia-travel.html`: recovered rich-text source.
- `knowledge/malaysia-travel.txt`: readable extraction of that source.
- `docs/manual-tests.md`: live checks to perform before claiming the project works.
- `docs/recovery-review.md`: findings and remaining issues.

## Open or restore

1. Prefer opening the existing Voyageur bot with Edit in Studio.
2. Keep the original export privately as the untouched recovery backup.
3. If testing an import, create a separate test bot and use Studio's Import / Export menu. Import the metadata-cleaned `.bpz` there. Menu labels can vary by Botpress version.
4. Confirm the knowledge source appears and is indexed, and the autonomous node can retrieve from it.
5. Run the manual tests in Studio's emulator, then check the existing shared webchat. Do not publish over the existing bot until testing is complete.

If the cleaned export cannot be imported, use the original private export and review the resulting configuration. The cleaned copy is a portfolio aid, not a verified replacement backup.

## Knowledge data limitations

The recovered source includes accommodation, attraction, food, and travel reference information. Prices, ratings, availability, and accessibility details were not independently verified. Treat them as project reference data, not current travel advice. Review source ownership and attribution before publishing the knowledge files.

## Portfolio evidence

Add a Studio screenshot showing the main workflow and knowledge source, plus screenshots of successful accommodation, attraction, and food conversations. Describe your own contribution precisely if this was a team project. Do not claim evaluation metrics until you have recorded test results.

## Author

Ahad Khan
