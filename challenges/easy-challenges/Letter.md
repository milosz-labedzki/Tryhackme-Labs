# Letter Walkthrough

### Tools Used
- `Gallica (BnF)` - Digital archive of the French National Library, used to search through issues of the L'Ouest-Éclair newspaper.
- `Google Search` - Used to pin down the dates of historical events (Amundsen's flight, Painlevé's government) and to verify the rescuer's identity.
- `Google Maps` - Used to find the postal code of the town of Penmarc'h.
- `Wikipedia` - Used to confirm the dates of Amundsen's expedition and Paul Painlevé's government.

### Step-by-Step Methodology
- **Step 1** - Unzip the challenge file and review the provided materials: a photo of the damaged envelope, a newspaper clipping from L'Ouest-Éclair, and a handwritten note from Audette to Edouard.
- **Step 2** - Read the note and extract the key clues: the subject is Edouard's great-grandfather, he was the "benjamin de l'équipe" (youngest member of the team), he wasn't even old enough to drive yet, and the event took place "sur l'eau" (on the water).
- **Step 3** - Read "SNSM" on the envelope and determine it's a French maritime rescue organization founded in 1967 — too late for the note's context, pointing instead to its predecessors: SCSN and HSB.
- **Step 4** - On the newspaper clipping, read the surviving secondary headlines despite the damage: "Amundsen a-t-il atteint le pôle Nord ?" and "M. Herriot se déclare solidaire de M. Painlevé".
- **Step 5** - Look up the date of Amundsen's North Pole flight (May 21, 1925) and the start of Paul Painlevé's government (April 1925), narrowing the event window to late May 1925.
- **Step 6** - In the Gallica archive, open the L'Ouest-Éclair (Rennes) edition and browse directly through the issues from May 22–24, 1925, instead of relying on full-text keyword search.
- **Step 7** - Read the torn main headline: "Une catastrophe sur le [...]" and the phrase "sept noyés" (seven drowned), pointing to a maritime disaster in the Finistère region of Brittany, in the town of Penmarc'h.
- **Step 8** - Search a combined query: `sauvetage penmarc'h 1925 "benjamin" ans mousse`, leading to historical sources describing Yves-Marie Gourlaouen — a 15-year-old ship's boy (mousse) who took part in the rescue and was awarded a silver medal for bravery.
- **Step 9** - Determine the postal code of Penmarc'h (29760) as the answer to the first question.
- **Step 10** - Assemble the flag in the required format `THM{Name_Surname_age}`, yielding `THM{Yves-Marie_Gourlaouen_15}`.
