# Notes d'entretien : Cas A, Cabinet Maître Devalle

> Mini-cours `01`. Rendez-vous client mardi 06/10/2026, 10h00-10h45.
> **12 réponses max**, **une question à la fois**. Les relances comptent dans les 12.

**Brief** : cabinet d'avocats, 12 avocats, Bordeaux. Maître Élise Devalle reçoit.

> « On rédige beaucoup de courriers types (mise en demeure, transmission dossier).
> On voudrait un assistant pour aller plus vite, et aussi pour retrouver les bonnes
> jurisprudences en 30 secondes au lieu de 30 minutes. »

## 1. Avant le rendez-vous : 12 questions + 3 de réserve

| # | Priorité (1-3) | Catégorie | Question |
|---|---|---|---|
| 1 | 1 | Besoin | Qu'est-ce qui déclenche ce projet maintenant ? |
| 2 | 1 | Besoin (arbitrage) | Si l'outil ne devait régler qu'un seul des deux sujets, courriers ou jurisprudence, lequel choisiriez-vous ? |
| 3 | 1 | Processus actuel | Prenez le dernier courrier type rédigé au cabinet : comment s'est-il fait, étape par étape ? |
| 4 | 1 | Processus actuel / source | Quand un avocat cherche une jurisprudence aujourd'hui, comment s'y prend-il concrètement ? |
| 5 | 1 | Données : volume + labels | Combien de courriers déjà rédigés le cabinet conserve-t-il, classés comment ? |
| 6 | 1 | Données : extrait | Pouvez-vous m'envoyer un exemple réel de courrier type, anonymisé ? |
| 7 | 1 | Succès chiffré | Dans six mois, quel chiffre vous ferait dire que le projet est réussi ? |
| 8 | 1 | Coût d'une erreur | Quelle serait, pour vous, la pire erreur que l'outil pourrait commettre ? |
| 9 | 2 | Confidentialité | Le secret professionnel vous impose-t-il des règles sur les outils en ligne qui touchent aux dossiers clients ? |
| 10 | 2 | Déjà essayé | Qu'avez-vous déjà essayé pour gagner du temps sur ces tâches, y compris ce que les avocats utilisent de leur propre initiative ? |
| 11 | 3 | Utilisateurs | Qui utiliserait l'outil au quotidien : avocats, collaborateurs, secrétariat ? |
| 12 | 3 | Budget | Quel budget annuel le cabinet peut-il consacrer à cet outil ? |
| R1 | réserve | SI / hébergement | Où sont stockés aujourd'hui vos dossiers et vos modèles : logiciel de cabinet, serveur interne, cloud ? |
| R2 | réserve | Délai | Pour quand vous faut-il un premier outil utilisable ? |
| R3 | réserve | Données sensibles | Dans quels domaines du droit intervient le cabinet ? |

### Relances préparées

| Après | Relance | Pourquoi |
|---|---|---|
| Q3 | Quelle étape prend le plus de temps ? | Savoir si un simple modèle suffit ou si le temps passe ailleurs |
| Q3 | Qui relit avant envoi ? | Validation humaine, qualification AI Act |
| Q4 | Dans quelles bases cherchez-vous ? | Source publique, éditeur payant ou fonds interne |
| Q4 | Ces 30 minutes, c'est surtout trouver les décisions ou les lire ? | Meilleure recherche ou aide à la lecture |
| toutes | Pouvez-vous me donner un exemple concret ? | Réponse trop vague |

**Si je relance, je sacrifie dans l'ordre** : Q12, puis Q11, puis Q10.

## 2. Pendant le rendez-vous : dit / interprété

| Question posée (telle quelle) | Ce que le client a **dit** (citation) | Ce que j'en **interprète** |
|---|---|---|
| **1.** Pourquoi avoir recours à l'IA ? | « Deux choses. D'abord les courriers types, mises en demeure, transmissions de dossier : on les réécrit à partir d'anciens courriers, c'est du temps perdu. Ensuite, et c'est le plus pénible, retrouver une décision qu'on a déjà obtenue ou étudiée : trente minutes pour ce qui devrait en prendre trente secondes. » | Pas de vrais modèles de courriers : chacun repart d'un ancien. Le besoin prioritaire n'est pas la jurisprudence publique mais les décisions du cabinet. Q2 (arbitrage) répondue : la recherche est « le plus pénible ». |
| **2.** Prenez le dernier courrier type rédigé au cabinet : comment s'est-il fait, étape par étape ? | « Chaque avocat a ses vieux courriers sur son poste, et on copie-colle. Il y a bien un dossier "modèles" partagé, mais il date de 2019 et personne ne le met à jour. Les assistantes préparent, l'avocat relit et signe. » | Problème d'organisation plus que de rédaction : modèles éparpillés, base commune abandonnée. L'avocat valide et signe toujours, donc pas de décision exclusivement automatisée. Utilisateurs : les assistantes préparent, les avocats valident. Q11 répondue. |
| **3.** La dernière fois qu'un avocat a dû retrouver une décision déjà obtenue, il a procédé comment ? | « Pour la jurisprudence publique, on a un abonnement à une base juridique en ligne. Mais notre vraie richesse, ce sont nos propres dossiers : les décisions qu'on a obtenues ici, à Bordeaux. Elles sont rangées dans des dossiers sur le serveur, et on cherche par nom de fichier… ou on demande au collègue qui s'en souvient. » | Jurisprudence publique déjà couverte par l'abonnement : hors périmètre. Besoin réel : chercher dans le contenu des décisions du cabinet, pas seulement dans les noms de fichiers. Le savoir repose sur la mémoire des collègues, il se perd si quelqu'un part. |
| **4.** Combien de décisions vous gardez sur le serveur ? | « Environ 2 000 décisions sur les quinze dernières années, en PDF ou en Word, plus des milliers de courriers archivés dans les dossiers clients. Les plus anciennes décisions sont des scans papier, pas toujours très lisibles. » | Petit volume : une solution légère suffit, sans entraînement de modèle. Les scans anciens devront être convertis en texte (OCR), une partie restera peut-être inexploitable. Les courriers archivés peuvent servir de base aux modèles, mais ils sont mêlés aux dossiers clients. |
| **5.** Pouvez-vous m'envoyer une décision obtenue par le cabinet, anonymisée bien sûr ? | « Bien sûr : nos clients, les parties adverses, parfois des salariés, des enfants dans les affaires familiales. Les décisions publiques sont anonymisées, les nôtres non. » | Le client a répondu sur les personnes citées, pas sur l'envoi. Fonds interne non anonymisé, avec des mineurs (droit de la famille) et des salariés (droit du travail) : risque 🔴. Données de santé possibles (art. 9 RGPD). |
| **6.** Pouvez-vous m'envoyer un exemple réel de courrier type, anonymisé ? | « Une assistante tient un registre des décisions : numéro, date, matière, juridiction, issue, et le nom du fichier. Je vous en transmets un extrait, seulement le registre, pas les décisions elles-mêmes, vous comprendrez pourquoi. » (fichier transmis) | Les labels existent déjà (matière, juridiction, issue) et serviront de filtres de recherche : question imposée « classées comment ? » couverte. Le contenu des décisions ne sort pas du cabinet, même vers un consultant. Registre saisi à la main : qualité à vérifier sur l'extrait. |
| **7.** Comment on pourrait définir la réussite du projet IA selon vous ? Quels résultats attendus ? | « Si chaque avocat gagne une heure par jour sans prendre le moindre risque déontologique, je signe tout de suite. Et pour la recherche : retrouver la bonne décision en moins d'une minute. » | Deux cibles : recherche de 30 min à moins d'1 min, et 1 h/jour/avocat. Mais ce sont les assistantes qui préparent les courriers : l'heure des avocats doit venir surtout de la recherche. « Aucun risque déontologique » est à traduire en règles vérifiables. (Deux questions en une : à éviter.) |
| **8.** Selon vous, quelles sont les pires erreurs que l'outil pourrait introduire, quelles sont vos craintes ? | « Une erreur dans un courrier ou une jurisprudence qui n'existe pas, c'est ma responsabilité professionnelle engagée. J'ai lu cette histoire d'avocats américains qui ont cité des décisions inventées par une IA. Ça, jamais chez nous. Tout doit être vérifiable. » | Coût d'une erreur critique, seuil : zéro décision inventée. La recherche doit renvoyer de vraies décisions avec leur fichier source, pas du texte généré : LLM génératif refusé pour la recherche, et c'est le client qui le justifie. Courriers : modèles à remplir, l'avocat signe. |
| **9.** Le secret professionnel vous impose des règles sur les outils en ligne, pouvez-vous m'envoyer un résumé succinct mais exhaustif de ces règles ? | « Absolument. Tout ce qui est dans nos dossiers est couvert par le secret professionnel. C'est une obligation déontologique : si ça fuit, c'est ma responsabilité personnelle devant le Barreau, pas seulement une amende. » (aucun document transmis) | Secret sur l'ensemble du fonds, responsabilité disciplinaire personnelle : risque 🔴 n°1. Je source les règles moi-même (loi du 31/12/1971 art. 66-5, RIN, guides du CNB). |
| **10.** Votre serveur est chez vous ou chez un prestataire ? | « Personne en interne. On a un prestataire informatique, un petit cabinet bordelais, qui passe une demi-journée par mois et intervient en cas de panne. Il gère le serveur et les postes. » | Réponse sur qui gère, pas sur où. Aucune compétence informatique interne : la solution doit tourner presque sans maintenance. Le prestataire accède déjà à des données couvertes par le secret (clause de confidentialité ?). Serveur probablement dans les locaux, non confirmé. |
| **11.** Vous avez quel budget annuel à consacrer à cet outil ? | « Serré. On est un cabinet de douze, pas un grand groupe. Mettons 15 000 euros pour démarrer, et ensuite un abonnement mensuel raisonnable, pas plus de quelques centaines d'euros par mois. » | 15 k€ de mise en place, puis quelques centaines d'€/mois (≈ 25 €/avocat/mois). Exclut un développement sur mesure et du matériel de calcul. |
| **12.** Vous avez quelle timeline en tête, quand attendez-vous le premier outil utilisable à disposition ? | « Pas d'urgence absolue. Je préfère quelque chose de fiable dans six mois que quelque chose de risqué dans un mois. » | 6 mois, la fiabilité avant la vitesse (cohérent avec la réponse 8). Place pour deux phases (recherche d'abord, modèles ensuite) et un test avec les avocats. |
| **13.** Combien de fois par jour un avocat cherche une décision du cabinet ? | « Pour tout le cabinet, une quinzaine de courriers types par jour, et une dizaine de recherches de jurisprudence interne par jour. C'est surtout la recherche qui prend du temps. » | Point de départ : 10 × 30 min = 5 h/jour pour le cabinet, gain maximal ≈ 4 h 50/jour (≈ 25 min/avocat). L'objectif « 1 h/avocat/jour » (12 h/jour) n'est pas atteignable par la recherche seule : à recadrer en §6. Courriers : 15/jour, temps unitaire inconnu. |
| **14.** À quelles conditions accepteriez-vous que vos décisions soient confiées à un service en ligne, hors de votre serveur ? | « Je ne veux pas que mes dossiers partent dans un cloud américain. Un hébergeur français avec un contrat sérieux, pourquoi pas, notre logiciel de gestion de cabinet l'est déjà. Mais il faudra me l'expliquer simplement. » | Service géré chez un hébergeur français, sous contrat de confidentialité : acceptable. Fournisseurs américains exclus (Cloud Act), services d'IA hébergés aux États-Unis compris. Le logiciel de gestion est un précédent, et une source possible pour remplir les courriers. Expliquer l'hébergement sans jargon. |

**Relances et questions non prévues**

- **5 puis 6** : extrait demandé deux fois, la première réponse portait sur les personnes citées et pas sur l'envoi.
- **10** : réserve R1 reformulée, car l'hébergement était encore 🔴 à trois questions de la fin.
- **13** : non prévue, pour obtenir le point de départ de l'objectif « 1 h/jour ».
- **14** : non prévue, la réponse 10 ne disait pas si un hébergement externe est acceptable.
- **Non posées car déjà répondues** : Q2 (réponse 1), Q11 (réponse 2), Q10 en partie (réponses 2 et 3), R3 en partie (réponse 5).

### Boussole : ce que j'ai déjà obtenu

> Mets-la à jour **après chaque réponse**. Elle suit des **informations**, pas
> tes questions : une réponse peut en remplir plusieurs, une autre aucune.
> Quand il te reste 3-4 questions, regarde les 🔴 : lequel manquera le plus à
> ton cadrage ? C'est à toi de formuler la question.
>
> 🟢 obtenu · 🟠 partiel / à vérifier · 🔴 à obtenir · ⬜ pas demandé (→ §3)

| Information | Statut | Réponse n° |
|---|---|---|
| Besoin réel (≠ demande exprimée) | 🟢 | 1, 3 |
| Processus actuel | 🟢 | 2, 3 |
| Données : existence | 🟢 | 3, 4, 6 |
| Données : volume | 🟢 | 4 (≈ 2 000 décisions sur 15 ans, des milliers de courriers) |
| Données : qualité | 🟠 | 4 (anciens scans peu lisibles), 6 (registre saisi à la main, à analyser) |
| Données : extrait obtenu | 🟢 | 6 (registre des décisions, pas les décisions elles-mêmes) |
| Données personnelles / confidentialité | 🟢 | 5, 9 |
| Critère de succès chiffré | 🟢 | 7, 13 (point de départ : 10 recherches/jour × 30 min) |
| Coût d'une erreur | 🟢 | 8 |
| Erreurs tolérées (chiffre : fausses alertes, mauvais routage…) | 🟠 | 8 (zéro décision inventée ; résultats hors sujet non chiffrés) |
| Utilisateurs | 🟢 | 2 |
| Validation humaine / qui décide | 🟢 | 2 (l'avocat relit et signe) |
| SI / hébergement | 🟢 | 10, 14 (prestataire externe, hébergeur français accepté, pas de cloud américain) |
| Compétences informatiques internes | 🟢 | 10 (aucune, prestataire une demi-journée par mois) |
| Budget | 🟢 | 11 |
| Délai | 🟢 | 12 |
| Ce qui a déjà été essayé | 🟠 | 2 (dossier « modèles » de 2019), 3 (abonnement à une base en ligne) |

## 3. Après : ce que je n'ai pas pu demander → questions ouvertes

| Je n'ai pas pu demander / pas eu de réponse claire | Pourquoi c'est important | → §6 du cadrage |
|---|---|---|
| Quelle part des décisions scannées est illisible ? | Coût de la conversion en texte, part du fonds réellement exploitable | À mesurer sur un échantillon au démarrage |
| Combien de résultats hors sujet sont tolérés ? | Seuil de qualité de la recherche | Seuil que je propose, à faire valider |
| Combien de temps prend la rédaction d'un courrier type aujourd'hui ? | Sans ce chiffre, le gain sur les 15 courriers par jour reste inconnu (hypothèse H1, section 4) | **Question pour le prochain rendez-vous**, puis mesure sur une semaine |
| Peut-on extraire les informations des dossiers (parties, montants, dates) du logiciel de gestion ? | Remplir les modèles de courriers sans ressaisie | Question pour l'éditeur du logiciel |
| Le contrat du prestataire informatique prévoit-il une clause de confidentialité ? | Il accède déjà à des données couvertes par le secret | Question ouverte, menace interne au §4 |
| Où se trouve le serveur actuel : dans les locaux ou chez le prestataire ? | Sauvegardes et transfert des données vers le futur hébergeur | Question ouverte |
| Tous les avocats peuvent-ils voir toutes les décisions ? | Droits d'accès, conflits d'intérêts | Question ouverte, droits d'accès au §5 |
| Les avocats utilisent-ils déjà des outils d'IA grand public ? | Une fuite existe peut-être déjà | Question ouverte (§6) |
| Le registre couvre-t-il les 15 ans, ou seulement depuis 2020 (l'extrait va de 2020 à 2025) ? | Sans ligne au registre, les décisions anciennes (les scans) n'ont aucun filtre | Question ouverte |
| La colonne « juridiction » est-elle remplie par défaut ? (« TJ Bordeaux » partout, même pour les prud'hommes) | Filtre inutilisable en l'état | À vérifier avec l'assistante qui tient le registre |

## 4. Besoin reformulé (repris au §2 du cadrage)

**Demande exprimée** : « un assistant pour aller plus vite » sur les courriers types, et « retrouver les bonnes jurisprudences en 30 secondes au lieu de 30 minutes ».

**Besoin réel** : le cabinet perd environ 5 h par jour à retrouver les décisions qu'il a déjà obtenues ou étudiées (10 recherches de 30 minutes, selon le client), plus la rédaction de 15 courriers types par jour, dont la durée n'a pas été mesurée ; il a donc besoin d'un outil fiable afin de regagner ce temps perdu, et il ne peut accepter aucune solution qui exposerait le secret professionnel ou produirait un résultat qu'un avocat ne peut pas vérifier.

**Détail des heures (tout le cabinet, par jour)**

| Tâche | Volume | Temps unitaire | Total | Source |
|---|---|---|---|---|
| Retrouver une décision du cabinet | 10 | 30 min, « pour ce qui devrait en prendre trente secondes » | **≈ 5 h** | réponses 1 et 13, déclaré par le client |
| Rédiger un courrier type | 15 | **non mesuré** | **non mesuré** | réponse 13 ; le client dit seulement « c'est surtout la recherche qui prend du temps » |

**Hypothèses** (ce que je ne sais pas, écrit comme tel) :

- **H1, durée des courriers** : la durée de rédaction d'un courrier n'a pas été mesurée. Le gain sur les courriers n'est donc pas chiffré à ce stade ; seul le gain sur la recherche l'est (de 30 min à moins d'1 min, ≈ 4 h 50 par jour, ≈ 25 min par avocat). → question pour le prochain rendez-vous.
- **H2, les 5 h de recherche** sont une estimation du client (10 recherches × 30 min), pas une mesure. → à mesurer pendant une semaine au démarrage.
- **H3, objectif « une heure par jour » par avocat** (réponse 7), soit 12 h par jour : la recherche seule n'y suffit pas, et les courriers sont préparés par les assistantes (réponse 2), pas par les avocats. Atteignable ou non selon H1. → à recadrer au §6.

_Problème : réponses 1, 2, 3, 13. Contrainte : réponses 8, 9. Les chiffres (10 × 30 min, 15 courriers/jour) vont au §6 ; budget, hébergement, informatique et délai vont dans les contraintes du §2._
