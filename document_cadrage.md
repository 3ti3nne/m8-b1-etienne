# Document de cadrage : Cabinet Maître Devalle

## 1. Synthèse exécutive

Le cabinet perd environ 5 h par jour à retrouver ses propres décisions, plus la rédaction de 15 courriers types par jour, dont la durée n'a pas été mesurée. Nous proposons d'abord un moteur de recherche dans les décisions du cabinet, hébergé en France, qui renvoie toujours le document d'origine, puis une bibliothèque de modèles de courriers pré-remplis que l'avocat relit et signe. Aucune IA qui rédige, donc aucune décision inventée. Indicateurs clés : une recherche passe de 30 minutes à moins d'une minute ; la bonne décision est dans les 5 premiers résultats 9 fois sur 10 ; zéro décision inventée. Le gain sur les courriers sera chiffré après mesure.

> **Imprévu client (14h30), ce que ça change** : _à compléter._

## 2. Besoin métier et contexte

**Demande exprimée** : « un assistant pour aller plus vite » sur les courriers types, et « retrouver les bonnes jurisprudences en 30 secondes au lieu de 30 minutes ».

**Besoin** : le cabinet perd environ 5 h par jour à retrouver les décisions qu'il a déjà obtenues ou étudiées (10 recherches de 30 minutes, selon le client), plus la rédaction de 15 courriers types par jour, dont la durée n'a pas été mesurée ; il a donc besoin d'un outil fiable afin de regagner ce temps perdu, et il ne peut accepter aucune solution qui exposerait le secret professionnel ou produirait un résultat qu'un avocat ne peut pas vérifier.

**Contraintes** : secret professionnel, dont la violation engage la responsabilité personnelle de l'avocat ; résultats toujours vérifiables, l'avocat relit et signe ; hébergement en France, pas de cloud américain ; aucune équipe informatique, seulement un prestataire une demi-journée par mois ; 15 000 € au démarrage puis quelques centaines d'euros par mois ; un outil fiable sous six mois plutôt que risqué dans un mois.

## 3. Données

| Donnée | Existante / à acquérir | Volume, qualité estimée | Personnelle ? |
|---|---|---|---|
| Décisions du cabinet (PDF, Word) | Existante, serveur du cabinet | ≈ 2 000 sur 15 ans ; les anciennes sont des scans papier, part illisible à mesurer | **Oui, non anonymisées** : clients, parties adverses, salariés, enfants, santé possible |
| Registre des décisions | Existante, tenu à la main | Date, matière, juridiction, issue, fichier : servira de filtres, rien à entraîner | Non |
| Courriers archivés, dossier « modèles » | Existants ; courriers dispersés, modèles figés depuis 2019 | Plusieurs milliers, non classés | Oui |
| Modèles de courriers à jour | **À constituer** | Les plus fréquents, choisis avec les assistantes | Non |
| Parties, dates, montants des dossiers | Logiciel de gestion, **accès à confirmer** | Pour remplir les modèles sans ressaisie | Oui |
| Jeu de test | **À constituer** | ≈ 50 vraies recherches avec la décision attendue (§6) | Non |

**Constats sur l'extrait du registre** (20 lignes) :

1. **Colonne « juridiction » non fiable** : « TJ Bordeaux » partout, même pour les 2 décisions de prud'hommes, et aucune décision d'appel. Remplie par défaut, inutilisable comme filtre en l'état.
2. **Noms de fichiers muets** (`decision_1000.pdf`) et extrait limité à 2020-2025 : la recherche par nom ne peut pas marcher, et la couverture des 15 ans est à vérifier.

Les décisions n'ont pas été transmises (secret) : la qualité de leur texte se mesurera sur place.

## 4. Risques et conformité

**Usage réel** : avocats et assistantes cherchent ; l'outil affiche des décisions du cabinet avec un extrait et le lien vers l'original. Il ne rédige ni ne décide : l'avocat lit la décision et choisit seul de s'en servir. Les courriers pré-remplis sont relus par l'assistante, corrigés et signés par l'avocat.

**Qualification AI Act** : **aucune obligation spécifique**. Le seul cas proche, l'Annexe III 8 a), vise l'IA utilisée par une juridiction ou pour son compte, pas par un avocat. Ni conversation ni texte généré : pas d'art. 50. Reste l'art. 4 : former les utilisateurs. **Bascule** en haut risque si l'outil servait à une juridiction (8 a) ou à évaluer le travail des avocats et assistantes, par exemple via le journal des recherches (Annexe III, 4 b).

**RGPD** : **base légale proposée, l'intérêt légitime** (art. 6.1 f) : le cabinet réutilise des dossiers qu'il détient déjà pour défendre ses clients ; le consentement des parties adverses est impossible et aucun contrat ne les lie au cabinet. Santé : art. 9.2 f (défense d'un droit en justice). **Pas de profilage** : l'outil classe des documents, pas des personnes. **Art. 22 non applicable** : ni décision exclusivement automatisée, ni effet juridique sur les personnes citées.

| Risque (éthique, métier, conformité) | Niveau | Obligation ou raison | Traitement dans l'archi |
|---|---|---|---|
| Fuite de dossiers sous secret (enfants, santé) | 🔴 | Loi du 31/12/1971 art. 66-5 ; art. 226-13 Code pénal ; RGPD art. 9 et 32 | Hébergeur français sous contrat ; chiffrement ; accès nominatif journalisé ; aucun envoi à une IA extérieure |
| Décision inventée | 🔴 | Responsabilité professionnelle : « tout doit être vérifiable » | Aucun texte généré : chaque résultat est un fichier existant |
| Décision existante non trouvée | 🟠 | L'avocat croit à tort que le cabinet n'a rien | Scans convertis en texte, illisibles listés, registre corrigé |
| Accès à un dossier dont l'avocat doit être écarté | 🟠 | Conflits d'intérêts (RIN art. 4) | Droits d'accès par dossier si besoin (§6) |
| Outil abandonné, comme les modèles de 2019 | 🟠 | Investissement perdu | Ajout automatique des nouvelles décisions ; une personne référente |
| Courrier pré-rempli erroné | 🟡 | Récupérable avant signature | Champs surlignés ; l'avocat signe |

**Sécurité** : service web réservé au cabinet, sans IA générative ni apprentissage sur l'usage.

| Menace | Plausibilité sur ce cas | Mitigation proposée | Risque résiduel |
|---|---|---|---|
| Aspiration du fonds via un compte volé ou un intervenant extérieur | 🟠 joignable par internet, personne pour surveiller | Double authentification ; accès depuis le cabinet ; alerte si volume anormal ; journal relu chaque mois | Utilisateur légitime sous le seuil |
| Fausse décision glissée sur le serveur | 🟡 suppose un accès en écriture | Seules les décisions du registre sont ajoutées ; l'avocat lit l'original | Interne qui modifie aussi le registre |

Écartées : **prompt injection** (aucune IA générative ; à revoir si l'on ajoute des résumés), **entrées trompeuses** (personne n'a intérêt à tromper la recherche), **vol du modèle** (rien de propre au cabinet).

## 5. Architecture cible et sobriété

Schéma : `schema_archi_cible.md`. D'abord un moteur de recherche dans les décisions du cabinet, hébergé en France ; ensuite des modèles de courriers pré-remplis.

**LLM refusé** :
- *Recherche* : une IA qui rédige peut inventer une décision, ce que le cabinet exclut ; l'outil rend la décision elle-même.
- *Courriers* : le problème est l'absence de modèles à jour, pas la rédaction ; un modèle validé n'a plus que ses champs à relire, un texte généré se relit en entier.
- *Secret* : un service de plus exposé aux dossiers, pour un gain non démontré.

**Écarté aussi** : jurisprudence publique (déjà couverte par l'abonnement) ; recherche « par le sens » (rouverte si le seuil du §6 n'est pas atteint) ; entraînement d'un modèle (rien à prédire) ; développement sur mesure (budget) ; installation au cabinet (dépendrait du prestataire).

## 6. Indicateurs, seuils, questions ouvertes

| Indicateur | Cible | Seuil d'acceptabilité | Comment on le mesure |
|---|---|---|---|
| Temps pour retrouver une décision | 30 min → moins d'1 min | 5 min (gain encore ≈ 4 h par jour) | Chronométrage d'une semaine, avant et après |
| Bonne décision dans les 5 premiers résultats | 9 sur 10 | 8 sur 10 (proposé) : en dessous, l'avocat revient à l'ancienne méthode ; on ajoute la recherche « par le sens » | Jeu de test (≈ 50 recherches) |
| Décisions inventées | 0 | 0 : erreur critique pour la responsabilité de l'avocat | Jeu de test ; garanti par l'archi |
| Décisions consultables | Toutes les lisibles, illisibles listées | 90 % du fonds (proposé, à revoir après mesure des scans) | Consultables ÷ inscrites au registre |
| Temps de rédaction d'un courrier | Départ non mesuré | À fixer après mesure | Chronométrage d'une semaine |

**Objectif « une heure par jour et par avocat »** (12 h par jour) : la recherche seule rapporte au mieux ≈ 4 h 50 par jour, soit ≈ 25 min par avocat ; le reste dépend des courriers, non mesurés et préparés par les assistantes. À recadrer après mesure.

**Prochaines étapes** : 1. une semaine de mesure (recherches, courriers, jeu de test) ; 2. vérification des données sur place (scans, registre, export du logiciel de gestion) ; 3. choix d'un hébergeur français et test avec quelques avocats.

**Questions ouvertes** :
1. Combien de temps prend aujourd'hui la rédaction d'un courrier type ?
2. Le registre couvre-t-il les 15 ans, et sa colonne « juridiction » est-elle remplie par défaut ?
3. Le seuil de 8 recherches réussies sur 10 vous convient-il ?
4. Tous les avocats doivent-ils pouvoir consulter toutes les décisions ?
5. Le contrat du prestataire informatique prévoit-il une clause de confidentialité ?
6. Les avocats utilisent-ils déjà des outils d'IA grand public pour leurs dossiers ?
