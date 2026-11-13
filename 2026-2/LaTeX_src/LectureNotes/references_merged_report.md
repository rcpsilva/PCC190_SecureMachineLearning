# references_merged.bib: merge and verification report

Sources: the 9 `references.bib` files under `LectureNotes/` (root, Attacks Compendium, Lecture1 to Lecture7). Six of them were byte-identical. Union: 155 keys. Result: **150 entries**, no duplicates.

Verification: every entry was matched against dblp (title + first author). The NIST report, the Science paper (Finlayson et al.) and the arXiv entries were checked on the NIST CSRC, Harvard Law School and arXiv pages. Test compilation with natbib/apalike over all 146 cited keys: 0 BibTeX warnings, 0 undefined citations.

## Duplicates removed (action needed in .tex files)

BibTeX/natbib has no key aliases, so each pair was reduced to one key. Rename these `\cite` keys before switching to the merged file:

| Removed key | Kept key | Cited in |
|---|---|---|
| `engstrom2019exploring` | `engstrom2019spatial` | Lecture2 |
| `brown2017patch` | `brown2017adversarial` | Lecture7 |
| `pierazzi2020intriguing` | `pierazzi2020problemspace` | Lecture2 |
| `gowal2019ibp` | `gowal2019scalable` | Lecture5 |
| `greshake2023indirect` | `greshake2023not` (full AISec record kept) | Lecture7 |

`ebrahimi2018hotflip` appeared with the same key but two different contents; the complete ACL version (pages 31--36) was kept.

Also removed: a stray text line `nces additions · BIB` that existed in 3 of the source files (BibTeX ignores it, but it is junk).

## Corrections per entry

- `liu2017delving`: entry type @article -> @inproceedings (ICLR is a conference)
- `huang2017adversarial`: arXiv preprint -> published in ICLR 2017 Workshop Track
- `chao2023jailbreaking`: year: '2023' -> '2025'; pages: added '23--42'; arXiv preprint -> published at SaTML 2025 (key kept)
- `andriushchenko2024simple`: year: '2024' -> '2025'; arXiv preprint -> published at ICLR 2025 (key kept)
- `robey2023smoothllm`: year: '2023' -> '2025'; arXiv preprint -> published in TMLR 2025 (key kept)
- `carlini2023aligned`: author: replaced "and others" with full NeurIPS author list
- `jain2023baseline`: author: replaced "and others" with full author list
- `uesato2018adversarial`: author order fixed to the ICML/PMLR version (Kohli before van den Oord); pages: '5025--5034' -> '5032--5041'
- `zhu2019transferable`: author: removed Ali Shafahi (listed on arXiv, not on the ICML/PMLR version)
- `carmon2019unlabeled`: author order fixed to the NeurIPS version (Duchi before Liang); pages: added '11190--11201'
- `gao2019strip`: author typo: "Xu, Change" -> "Xu, Chang"
- `abadi2016deep`: author accent: Martin -> Mart\'{\i}n
- `lecuyer2019certified`: author accent: Lecuyer -> L\'ecuyer
- `yin2018byzantine`: author: added middle initial (Peter L. Bartlett); pages: '5650--5659' -> '5636--5645'
- `he2017ensemble`: title: published WOOT version reads "Defense" (singular); arXiv reads "Defenses"
- `geiping2020inverting`: title: matches NeurIPS version ("Inverting Gradients - How easy ...")
- `ilyas2018blackbox`: pages: '2137--2146' -> '2142--2151'
- `wong2018provable`: pages: '5286--5295' -> '5283--5292'
- `zhang2020secret`: pages: '253--261' -> '250--258'; note: old pages were the CVF open-access numbering; new pages follow IEEE Xplore (matches the DOI)
- `moosavi2017universal`: pages: '1765--1773' -> '86--94'; note: old pages were the CVF open-access numbering; new pages follow IEEE Xplore (matches the DOI)
- `xie2017dag`: pages: '1369--1378' -> '1378--1387'; note: old pages were the CVF open-access numbering; new pages follow IEEE Xplore (matches the DOI)
- `gowal2019scalable`: pages: '4842--4851' -> '4841--4850'; note: old pages were the CVF open-access numbering; new pages follow IEEE Xplore (matches the DOI)
- `zhu2019deep`: pages: added '14747--14756'
- `ilyas2019features`: pages: added '125--136'
- `steinhardt2017certified`: pages: added '3517--3529'
- `shafahi2018poison`: pages: added '6106--6116'
- `tran2018spectral`: pages: added '8011--8021'
- `blanchard2017krum`: pages: added '119--129'
- `shafahi2019free`: pages: added '3353--3364'
- `salman2019provably`: pages: added '11289--11300'
- `tramer2019multiple`: pages: added '5858--5868'
- `thys2019fooling`: pages: added '49--55'
- `chen2019activation`: booktitle: 'Workshop on Artificial Intelligence Safety, AAAI' -> 'Workshop on Artificial Intelligence Safety (SafeAI), co-located with AAAI, CEUR Workshop Proceedings 2301'
- `nist2025ai1002`: month: added 'March'

## Additions without changing content

- DOIs added to 63 entries (64 now carry a DOI) (from dblp/publisher records).
- `eprint`/`archivePrefix` added to the 11 arXiv-only entries.

## Points left for your judgement

- `greshake2023not`: ACM/dblp list Sahar Abdelnabi first; arXiv lists Kai Greshake first (equal contribution). The arXiv order was kept.
- `zou2023universal`: dblp still shows 4 authors (arXiv v1); arXiv v2 lists 6 (adds Carlini and Nasr). The 6-author list was kept.
- `nicolae2018art`: title "v1.0.0" corresponds to arXiv v4 (2019); year kept as 2018 (arXiv ID).
- Keys `chao2023jailbreaking`, `andriushchenko2024simple`, `robey2023smoothllm` were kept even though the published years are now 2025, so no `\cite` needs to change.
- `moosavi2017universal`, `xie2017dag`, `zhang2020secret`, `gowal2019scalable`: CVF and IEEE Xplore paginate these papers differently. The merged file uses IEEE Xplore pages so they match the DOI.
- Papers available only on arXiv (e.g. `carlini2019evaluating`, `turner2019label`, `jain2023baseline`) were confirmed to have no later peer-reviewed version in dblp.
