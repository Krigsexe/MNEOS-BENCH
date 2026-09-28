# Suivi des corrections

## 2026-09-28 : MnemosyneOS---benchmarks@7c2b09d (erratum)

Vérifié hors réseau (traces T21 à T25).

| Point de l'audit | État à 7c2b09d | Preuve |
|---|---|---|
| gpt4_76048e76 compté HIT | Corrigé : MISS par audit humain, verdict du juge conservé et visible | `lexical-2026-08/human-audit.json`, registres, T21 |
| 6ade9755 (run 2 contradictoire) | Corrigé : MISS par audit humain (règle des deux runs) | idem |
| 0edc2aef (préférence discutable) | Maintenu HIT, avec justification publiée | `human-audit.json` |
| Scores strict et flexible | 35/48 et 37/48, recalculés ; +9/−3 (p = 0,146) et +7/−4 (p = 0,549), vérifiés | T21, calcul indépendant |
| « 72,9 % lower bound » | Retiré | `ERRATUM.md` |
| Règle heuristique et juge | Publiée : `finalVerdict()`, le juge décide, l'heuristique est informative | `scoring.js`, selftest 22/22 (T22) |
| Juge sans question, « strict » = branche par défaut | Documenté | `ERRATUM.md`, `METHODOLOGY.md` |
| Repli `includes(numericRaw)` | Corrigé (nombres entiers seulement) ; 5 cas numériques adverses conformes (T25) | `scoring.js` |
| « Every HIT replayed » | Corrigé : les bras à un seul run sont nommés | `ERRATUM.md` §4 |
| Holdout « confirmed » | Corrigé : récupération seulement | `ERRATUM.md` §5 |
| Régénération des registres | Identique à l'octet (T24) | `extract-ledgers.mjs` |
| BEAM « 0.30 → 0.12, 60 % » | **Non corrigé** : `README.md` L94, `beam-2026-09/verify.js` L189-L190 | grep |
| README produit (77,1 %, « lower bound », « never leaves it ») | **Non corrigé** : Mnemosyne-Neural-OS main inchangé depuis 580f1fe | grep |
| Sorties brutes du juge, transcription aae3761f, règle du holdout, version du corpus | Annoncés, non publiés | `ERRATUM.md` |
| Protocole du nouveau run | Accepté (5 points), non publié | commentaire PR n° 47 |

Nuance : l'audit humain a relu les HIT du bras fusion seulement. Les HIT du bras de référence et les MISS des deux bras n'ont pas été relus. C'est conservateur pour le gain annoncé, mais le delta apparié pourrait encore bouger dans un sens ou dans l'autre.

Défauts résiduels de l'heuristique (négation, unités, ordre) : sans effet sur les verdicts, puisque le juge décide seul. `parseJudgeVerdict` (règle « dernier YES/NO ») reste inchangé ; effet non observable sans les sorties brutes du juge.
