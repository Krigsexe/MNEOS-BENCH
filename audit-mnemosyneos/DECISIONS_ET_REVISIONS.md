# Décisions et révisions

## Décisions proposées (pour Julien ; aucune n'a été exécutée à l'extérieur)

| Id | Décision | Raison | Preuves | Condition de révision |
|---|---|---|---|---|
| D01 | Citer les scores Mnemosyne seulement avec leur périmètre : « 37/48, échantillon de développement de 48 questions, juge maison strict sans question, lecteur cloud » | C01, C05, C06 | E06, E12, E17 | Publication d'un run sur l'ensemble complet avec le juge officiel |
| D02 | Ne pas reprendre « 72,9 % borne inférieure » | C07 | E13, E14 | Preuve de monotonie |
| D03 | Mentionner `gpt4_76048e76` comme erreur de notation publiée, avec le calcul conditionnel 36/48 et le p conditionnel de 0,065 | C03, C09 | E09, E10, E16 | Erratum officiel LongMemEval |
| D04 | Ne pas attribuer à Tony Trochet l'annonce « tout est open source » sans citation datée | C14 | E30 | Citation d'un support daté |
| D05 | Ne pas conclure à une falsification. Les pièces sont cohérentes ; les défauts relèvent de l'instrument de notation et de formulations | C01, C02, §5 du rapport | E06, E07, E25 | Découverte d'une incohérence entre journal et registre qui modifie un score |
| D06 | Ne pas comparer OAM à ces résultats (hors mandat), ni utiliser ces défauts comme argument pour OAM | Mandat | n/a | n/a |
| D07 | Ne pas ingérer ce dossier dans Recoll/OAM ni dans une mémoire testée. Ne pas utiliser cette session comme candidat à un benchmark : elle a lu des corrigés LongMemEval et BEAM | Mandat §3 | n/a | n/a |
| D08 | Proposer à Tony, s'il le souhaite, les corrections listées dans `REPONSE_TONY.md` ; Julien décide de l'envoi | Mandat §13 | n/a | n/a |
| D09 | Ne pas exécuter la réévaluation avec gpt-4o (appel payant, données envoyées à un tiers) sans accord explicite | Mandat §1 | n/a | Accord de Julien |

## Révisions en cours d'audit (affirmations provisoires corrigées)

| Id | Hypothèse ou lecture initiale | Correction | Cause |
|---|---|---|---|
| R01 | « Le verdict = l'heuristique quand elle dit HIT » (lecture des premières lignes brutes) | Faux : 4 combinaisons observées ; le juge renverse parfois l'heuristique (E08) | Recalcul complet (T09 §4) |
| R02 | « 16 faux positifs d'abstention BEAM à 100K » (filtre par mots-clés) | 4 faux positifs nets et 5 discutables après lecture humaine ; les autres « candidats » étaient de vraies abstentions | Revue de T10 |
| R03 | « La pondération 8×6 gonfle le score » (piste) | Infirmé : la repondération officielle ne fait pas baisser le score de fusion (calcul conditionnel, n = 8) | T09 §8 |
| R04 | Premier contrôle des journaux de juillet : 16 écarts | Artefact de mon analyseur (format multi-bras) ; après correction, 16/16 verdicts concordants et 2 écarts de texte | T18 |
| R05 | Premier run des tests MCP : échecs `ENETUNREACH` | Artefact de mon isolement réseau (boucle locale inactive) ; T13 invalide, T15 fait foi | T13, T15 |
| R06 | Commentaire prédictif du script de mutation (« A02/A14 resteront en défaut ») | Faux : les 5 cas deviennent conformes ; commentaire corrigé et trace T17 régénérée | T17 |
| R07 | « Toutes les sessions probantes sont préfixées `answer_` » | Non universel : `89527b6b` cite `sharegpt_YkWn1Ne_0` | E28 |
| R08 | « 7 faux positifs nets du juge BEAM en abstention » (revue des réponses seules, T10) | **Infirmé** par la confrontation aux conversations sources (T20) : dans 3 cas l'information existe dans la conversation (rubrique BEAM contredite) ; 4 cas discutables. Calcul conditionnel 60,7 % et 47,7 % retiré ; courrier à Tony corrigé | Demande de Julien d'être « sûr et certain » ; vérification à la source primaire |
| R09 | « Le préfixe `answer_` marque les sessions probantes » | Restreint : observé dans l'oracle, non documenté par le README LongMemEval, non systématique | Vérification du README officiel |
| R10 | Point vélo dans le courrier à Tony | Conservé et marqué « déjà transmis » (Julien l'a signalé la veille ; correction en cours chez Tony) | Information de Julien |
