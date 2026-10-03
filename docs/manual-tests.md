# Manual test checklist

Status for every case: NOT RUN. Record the date, inputs, actual responses, and screenshots when testing. Expected outcomes below describe intended behavior.

| Case | Input / steps | Expected behavior |
|---|---|---|
| Greeting | Start a new chat with `Hello` | Introduces Voyageur, welcomes the user to Malaysia, responds mostly in English |
| Basic planning | `I am visiting Kuala Lumpur for 3 days and need a hotel. My budget is medium.` | Uses provided preferences, asks for missing amenities, recommends knowledge-backed options |
| Existing hotel | `I already have accommodation in Penang. I like heritage attractions.` | Moves toward attractions rather than repeatedly asking for a hotel budget |
| Food first | `Where can I eat Indian food in Kuala Lumpur?` | Answers from the knowledge source and asks where the user is staying |
| Accessibility | Request wheelchair-accessible accommodation and attractions | Uses available accessibility details; acknowledges missing information |
| Unsupported destination | Ask about a destination outside the seven listed in the prompt | Explains coverage limits without inventing recommendations |
| Unknown detail | Ask for a fact absent from the knowledge source | Acknowledges missing information |
| No live pricing | Ask for a guaranteed room price for tonight | Does not present unverified reference prices as live availability |
| Language | Ask a travel question in French | Follows the configured English-response rule |
| Retrieval | Ask for a specific hotel detail present in the source | Retrieves a matching fact; inspect emulator traces if it fails |

After these pass, repeat one full planning conversation through the shared webchat. A local export inspection does not establish runtime correctness.
