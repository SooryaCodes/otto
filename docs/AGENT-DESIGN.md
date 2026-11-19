# Otto AI: the agent crew that runs every open order (15 Nov 2026)

Otto AI is not a chatbot. It is one orchestrator and nine specialists that watch every gram from the moment it leaves the safe to the day the karigar is paid, and keep a record of every step. Otto reads the same from both sides, like every entry it keeps. Its mascot is a gold owl with a jeweller's loupe.

Rule for every step: **models propose, code decides, people approve.**

## 1. What wakes it up (events)
Every input becomes an event on one append-only log. Nothing happens off the log.

| Event | Where it comes from |
|---|---|
| Scale photo | Owner app, bench mode, counter staff |
| Reply | WhatsApp tap, voice note or text, in any of 11 languages |
| Bench sign | A worker's PIN or voice at the shared tablet |
| Paper photo | Order sheet, signed challan copy, HUID receipt, old notebook page |
| Money | Bank credit or SMS (simulated for now, and labelled) |
| Clock | Daily 8 AM sweep, due dates, payment days, the one-year rule |
| Refiner | Scrap batch sent, fine gold recovered |

## 2. The crew
| Agent | Its one job | Model or code | Can it act alone? |
|---|---|---|---|
| **Otto AI** (orchestrator) | Holds the goal for each open order ("delivered by 15 Jan, settled, papers filed, nobody owed"), plans the steps, routes events, chases what is stuck | LLM planner on Lyzr, state machine underneath | Only for reminders and drafts |
| **Reader** | Reads the scale display, order sheets, HUID receipts, signed copies, old notebook pages | Vision model | No: every reading goes to Checker |
| **Checker** | Format (3 decimals, unit), plausible range, order of steps, fresh photo (not reused), known scale gap, totals | **Plain code, no model.** A model cannot override it | Blocks or passes |
| **Messenger** | Asks the other side to confirm, in their language, by text and voice; reads replies and sorts them: confirm, question, dispute, update | Speech (Sarvam, ElevenLabs), small classifier | Sends confirmations and reminders |
| **Planner** | Works back from the wedding or delivery date: hallmark buffer, fitting, each karigar's load, festival trips (Durga Puja, Onam, Eid); spots a late piece early; proposes two or three re-plans | LLM plus a date solver | No: re-plans need the people affected |
| **Settler** | Drafts each settlement: fine gold in and out, wastage against terms, labour by basis, advances, TDS | **Code computes every number**; LLM writes the explanation in each language | No: both sides approve |
| **Papers** | Challan, labour bill, sale bill with HUIDs, e-way bill check, job-work register, ITC-04, Kerala gold record | Code and templates | Drafts only; the owner sends |
| **Payments** | Matches money received to bills after TDS; flags late pay on both sides; reminds the jeweller of the 45-day rule | Code | Reminders only |
| **Watcher** | Looks for drift: wastage creeping up for one item, scrap coming back lighter than usual, gold out above a karigar's limit, gold away close to one year, a scale gap that changed, a reused photo. Opens a case with the evidence and asks; never accuses | Code rules plus anomaly scores | Opens cases, never decides |
| **Record keeper** | Builds the karigar's signed record every month, including his own one-sided entries when a jeweller never signs; asks his consent before anyone sees it; shares a link that expires | Code | Only with his consent |

## 3. Memory
- **Per relationship:** wastage terms, labour basis and rate, payment days, who hallmarks, the two scales' usual gap, language and channel.
- **Per person:** usual wastage per item, usual speed, festival trips, how they like to be reminded.
- **Per order:** the full event log, every photo, every reply, every draft.

## 4. Where people decide (gates)
Otto AI asks a person before it: sends a bill or challan, sends or changes a settlement, moves or records money, changes a date that affects someone else, shares anyone's record, or closes a dispute. It never edits a locked entry. Corrections are new entries both sides confirm.

## 5. How it recovers
| What goes wrong | What Otto AI does |
|---|---|
| Photo misread or blurred | Checker blocks it; asks for a new photo; after two tries, typed entry that both sides confirm |
| No reply | Reminder after 2 hours, voice note after 6, the owner told after 24 |
| Piece running late | Planner proposes re-plans; Messenger asks the karigar and the jeweller; the customer is told only after both agree |
| Money short or late | Payments shows the gap line by line; reminder goes to the jeweller, not only the karigar |
| WhatsApp down or no data | Link by SMS; bench mode and the app queue photos offline and sync later |
| Numbers disagree | Checks the usual gap between the two scales; beyond it, books a re-weigh on the third scale both named; if still apart, brings in the neutral person both named. Every weighing stays in the record |
| A jeweller never confirms | The karigar's own entry stays in his record as one-sided, with both photos; it becomes two-sided if the jeweller confirms later |

## 6. Everything tracked
Every step is written to the log: what happened, which agent, which tool, which model and version, its confidence, and who approved. Each entry carries a hash of the one before it, so any change breaks the chain. Any lot can be replayed from the first gram to the last rupee. The CA, the jeweller and the karigar each see the part that is theirs.

## 7. What we will measure (targets, not results)
| Measure | Target |
|---|---|
| Scale readings correct on real photos from our workshop | 98% or more, read straight from the photo |
| Wrong readings that reach a person to sign | 0 (Checker catches them) |
| Voice replies understood, per language | 90% or more in Malayalam, Bengali, Hindi, Tamil |
| Time to draft a month-end settlement | Minutes, not a day |
| Steps that needed a person | Tracked per 100 steps |
