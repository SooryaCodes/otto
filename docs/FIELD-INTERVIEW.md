# Field interview and research

## Who we spoke to

The founder of a gold and silver job-work unit in Kerala: our own family's workshop. He worked as a karigar for years before starting it, so he has stood on both sides of the scale: taking a shop's gold on trust, and now giving gold to his own workers and specialists. 15 to 20 karigars work at its benches, and it also gives gold and orders to independent specialists, such as chain makers. It makes ornaments for big jewellery shops. Statements are paraphrased and translated from Malayalam.

## What we asked

1. How is gold issued and recorded today, and who holds the record?
2. How is wastage agreed, and how often is it disputed?
3. What happens when a piece is late for a wedding?
4. How long does it take to be paid after delivery?
5. What happens when the shop's weight differs from yours?
6. How many shops, workers and open orders are handled at once?

## What we heard, and what it changed

| | What we heard | What we built | Screen |
|---|---|---|---|
| F1 | "We use our own gold. The shop gives back exactly the same weight, nothing extra." | Settlement in fine gold, and a 'whose metal' setting: ours, the shop's, or mixed. | [Onboard2](../screens/2-workshop-owner/03-Onboard2.png) |
| F2 | "There is no wastage deal. What is lost in making is our loss, at most half a gram in 100." | Wastage is an optional term per relationship. Each lot's loss is checked against the unit's own usual. | [LotDetail](../screens/2-workshop-owner/07-LotDetail.png) |
| F3 | "We are paid labour only, ₹350 a gram, by bank, and the shop cuts 1% TDS." | The labour bill is drafted from locked weights; the bank credit is matched to the bill after TDS. | [Payment](../screens/2-workshop-owner/13-Payment.png) |
| F4 | "The gold comes back in about a week. The money takes about two." | Payment days are part of the terms. Late payment shows on both sides and Otto AI reminds the payer. | [JewellerBoard](../screens/3-jeweller/01-JewellerBoard.png) |
| F5 | "If the finish is not right, the shop rejects it and we melt and remake. Rare, but it wipes out the lot." | A rejection flow with the remake cost against the labour, and the labour bill held until it is accepted. | [Rejected](../screens/1-handover/09-Rejected.png) |
| F6 | "Every delivery needs a challan and a labour bill, or a sale bill. Printed, stamped, and emailed. Who hallmarks decides which." | Who hallmarks is set once per shop. The right papers are drafted for every delivery, e-way bill checked. | [DocPack](../screens/2-workshop-owner/12-DocPack.png) |
| F7 | "Big shops won't tap buttons. They want stamped papers and a PDF for accounts." | Workshop-led ledgers: the shop's signed copy and its scale photo stand in for its confirmation. | [JewellerDelivery](../screens/2-workshop-owner/11-JewellerDelivery.png) |
| F8 | "I don't always deliver. One of the workers often takes it." | A delivery person flow: two photos at the shop counter, matched to the lot. | [JewellerDelivery](../screens/2-workshop-owner/11-JewellerDelivery.png) |
| F9 | "Not every unit works like ours. Some get the shop's metal, some agree a wastage." | Every way of working is a setting at onboarding or per shop. The core loop never changes. | [Onboard2](../screens/2-workshop-owner/03-Onboard2.png) |
| F10 | "We also give gold and orders to independent workers, like the ones who specialise in certain chains." | A unit issues to outside specialists on WhatsApp while its bench workers sign at the scale. | [BenchMode](../screens/1-handover/04-BenchMode.png) |

## What published research added

| | Finding | Source | What we built | Screen |
|---|---|---|---|---|
| R1 | 'Wastage is the wage.' The allowance a karigar saves is his pay, about 1.3 g per 100 g. | IIMA and XLRI, 123 karigars in 7 hubs, 2023 | Savings under the agreed wastage show as his earnings, not as a loss to cut. | [KarigarPassport](../screens/4-karigar/05-KarigarPassport.png) |
| R2 | New karigars are trusted with 100 to 250 g. More comes only as trust grows. | IIMA and XLRI, 2023 | A verified record lets a jeweller raise a karigar's limit on evidence, not on memory. | [LenderView](../screens/6-customer-refiner-bank-cafe/03-LenderView.png) |
| R3 | Often there are three parties: the jeweller, a head karigar, and the karigars he hires. | IIMA and XLRI, 2023 | A head karigar is a party of his own: he takes gold from the jeweller and issues it on. | [Main](../screens/7-overview-boards/01-Main.png) |
| R4 | 8 cases of karigars vanishing with about 8.1 kg of gold in the Mumbai region in two years. No written record in any report. | Free Press Journal, Jan 2024 to Jan 2026 | Every handover is confirmed by both sides with a photo, and leftovers carry forward in a running balance. | [JobWorkRegister](../screens/3-jeweller/04-JobWorkRegister.png) |
| R5 | The principal must keep the job-work account. Gold not back within a year is taxed as supplied on the day it left. | CGST Act, section 143 | A job-work register built from signed entries, with the one-year rule flagged early. | [JobWorkRegister](../screens/3-jeweller/04-JobWorkRegister.png) |
| R6 | Kerala wants every holder to record gold held, gold with job workers or hallmarkers, and balance in hand. | Kerala Trade Circular 1/2025 | The ledger produces that record by default, per jeweller and per karigar. | [JewellerBoard](../screens/3-jeweller/01-JewellerBoard.png) |
| R7 | From April 2026, banks may lend gold to jewellers only to have it made by goldsmiths on job work, for up to 270 days. | RBI gold metal loan rules, 2025-26 | A lot trail the bank can follow while its gold sits with karigars. | [LenderView](../screens/6-customer-refiner-bank-cafe/03-LenderView.png) |
| R8 | PM Vishwakarma covers goldsmiths: ₹1 lakh, then ₹2 lakh, collateral-free at 5%. | pmvishwakarma.gov.in | The karigar can share his signed record with a lender, with consent that ends on a date he sets. | [KarigarPassport](../screens/4-karigar/05-KarigarPassport.png) |
| R9 | Bengali karigars go home for Durga Puja every year, and wedding orders run late. | DNA, Mumbai bullion association | Otto AI plans deliveries around each karigar's festival and home-trip dates. | [BridalRisk](../screens/3-jeweller/02-BridalRisk.png) |
| R10 | No software lets the karigar see his own balance, confirm a weight, or carry his record between jewellers. | Our scan of Tally, Marg, SwarnApp, Online Munim, JewelAcc and others | That is the gap we fill: the karigar's own account, in his language. | [KarigarAccount](../screens/4-karigar/01-KarigarAccount.png) |

The full board is in [screens/7-overview-boards](../screens/7-overview-boards/04-FieldResearch.png).

## Next interviews

Karigars at our benches, an outside specialist, a shop's counter staff, a refiner and a co-operative bank, to hear each side in its own words.
