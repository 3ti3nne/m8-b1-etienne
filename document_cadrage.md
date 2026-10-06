# Document de cadrage : Cabinet Maître Devalle

## 1. Synthèse exécutive

Le cabinet perd environ 5 h par jour à retrouver ses propres décisions, plus la rédaction de 15 courriers types par jour, dont la durée n'a pas été mesurée. Nous proposons d'abord une recherche dans les décisions du cabinet, par mots et par le sens (elle retrouve une décision même si l'avocat n'emploie pas ses mots exacts), hébergée en France, qui renvoie toujours la décision d'origine, puis des modèles de courriers pré-remplis que l'avocat relit et signe. Indicateurs clés : une recherche passe de 30 minutes à moins d'une minute ; la bonne décision est dans les 5 premiers résultats 9 fois sur 10 ; zéro décision inventée.

> **Imprévu : le prestataire informatique part le 31/12.** Hébergement en France confirmé ; ajoutés : copie des décisions avant son départ, coupure de ses accès, journal des accès suivi par l'hébergeur (contraintes, risques, architecture, étapes, questions mis à jour).

## 2. Besoin métier et contexte

**Demande exprimée** : « un assistant pour aller plus vite » sur les courriers types, et « retrouver les bonnes jurisprudences en 30 secondes au lieu de 30 minutes ».

**Besoin** : le cabinet perd environ 5 h par jour à retrouver les décisions qu'il a déjà obtenues ou étudiées (10 recherches de 30 minutes, selon le cabinet), plus la rédaction de 15 courriers types par jour, dont la durée n'a pas été mesurée ; il a donc besoin d'un outil fiable afin de regagner ce temps perdu, et il ne peut accepter aucune solution qui exposerait le secret professionnel ou produirait un résultat qu'un avocat ne peut pas vérifier.

**Contraintes** : secret professionnel (responsabilité personnelle de l'avocat) ; résultats toujours vérifiables, l'avocat relit et signe ; hébergement en France, pas de cloud américain ; aucune équipe informatique, et **plus de prestataire après le 31 décembre** ; 15 000 € au démarrage puis quelques centaines d'euros par mois ; un outil fiable sous six mois plutôt que risqué dans un mois.

## 3. Données

| Donnée | Existante / à acquérir | Volume, qualité estimée | Personnelle ? |
|---|---|---|---|
| Décisions du cabinet (PDF, Word) | Existante, serveur du cabinet (sans entretien après le 31/12) | ≈ 2 000 sur 15 ans ; anciennes en scans papier, part illisible à mesurer | **Oui, non anonymisées** : clients, parties adverses, salariés, enfants, santé possible |
| Registre des décisions | Existante, tenu à la main | Date, matière, juridiction, issue, fichier : servira de filtres | Non |
| Courriers archivés, dossier « modèles » | Existants ; courriers dispersés, modèles figés depuis 2019 | Plusieurs milliers, non classés | Oui |
| Modèles de courriers à jour | **À constituer** | Les plus fréquents, choisis avec les assistantes | Non |
| Parties, dates, montants des dossiers | Logiciel de gestion, **accès à confirmer** | Pour remplir les modèles sans ressaisie | Oui |
| Jeu de test | **À constituer** | ≈ 50 vraies recherches avec la décision attendue | Non |

**Constats sur l'extrait du registre** (20 lignes, les décisions elles-mêmes n'ont pas été transmises) :

1. **Colonne « juridiction » non fiable** : « TJ Bordeaux » partout, même pour les 2 décisions de prud'hommes ; inutilisable comme filtre en l'état.
2. **Noms de fichiers muets** (`decision_1000.pdf`), extrait limité à 2020-2025 : chercher par nom ne marche pas ; couverture des 15 ans à vérifier.

## 4. Risques et conformité

**Usage réel** : avocats et assistantes cherchent ; l'outil affiche des décisions du cabinet avec un extrait et le lien vers l'original. Il ne rédige ni ne décide : l'avocat lit et choisit seul ; les courriers pré-remplis sont relus et signés.

**Qualification AI Act** : **aucune obligation spécifique**. Le seul cas proche, l'Annexe III 8 a), vise l'IA d'une juridiction, pas celle d'un avocat. Ni conversation ni texte généré : pas d'art. 50. Reste l'art. 4 : former les utilisateurs. **Bascule** en haut risque si l'outil servait à une juridiction, ou à évaluer le travail des avocats et assistantes via le journal des recherches (Annexe III, 4 b).

**RGPD** : **base légale proposée, l'intérêt légitime** (art. 6.1 f) : le cabinet réutilise des dossiers qu'il détient déjà pour défendre ses clients ; consentement des parties adverses impossible, aucun contrat avec elles. Santé : art. 9.2 f (défense d'un droit en justice). **Pas de profilage** : l'outil classe des documents, pas des personnes. **Art. 22 non applicable** : ni décision exclusivement automatisée, ni effet juridique sur les personnes.

| Risque (éthique, métier, conformité) | Niveau | Obligation ou raison | Traitement dans l'architecture |
|---|---|---|---|
| Fuite de dossiers sous secret (enfants, santé) | 🔴 | Loi du 31/12/1971 art. 66-5 ; Code pénal art. 226-13 ; RGPD art. 9 et 32 | Hébergeur français sous contrat ; données chiffrées ; accès personnels et tracés |
| Décision inventée | 🔴 | Responsabilité de l'avocat : « tout doit être vérifiable » | Aucun texte généré : chaque résultat est un fichier existant |
| Perte des décisions (serveur sans entretien après le 31/12) | 🟠 | Le fonds est « la vraie richesse » du cabinet | Copie complète chez l'hébergeur avant le 31/12, sauvegardée |
| Décision existante non trouvée | 🟠 | L'avocat croit à tort que le cabinet n'a rien | Scans convertis, illisibles listés ; recherche par le sens |
| Avocat accédant à un dossier en conflit d'intérêts | 🟠 | RIN art. 4 | Droits d'accès par dossier si besoin |
| Outil abandonné, comme les modèles de 2019 | 🟠 | Investissement perdu | Dépôt par l'assistante ; une personne référente |
| Courrier pré-rempli erroné | 🟡 | Récupérable avant signature | Champs surlignés ; l'avocat signe |

**Sécurité** : service web réservé au cabinet, sans IA qui rédige ni apprentissage sur l'usage.

| Menace | Plausibilité sur ce cas | Mitigation proposée | Risque résiduel |
|---|---|---|---|
| Copie massive des dossiers par un compte volé ou des accès restés ouverts | 🟠 joignable par internet ; personne pour surveiller après le 31/12 | Double authentification ; accès du prestataire coupés à son départ ; alertes de l'hébergeur à la référente | Un utilisateur autorisé qui copie peu à la fois |
| Fausse décision glissée dans l'outil | 🟡 suppose un compte qui dépose | Seule l'assistante du registre dépose ; l'avocat lit l'original | Une personne du cabinet qui modifie aussi le registre |

Écartées : **consignes cachées dans un document pour détourner une IA** (« prompt injection » : sans objet, aucune IA qui rédige), **recherches piégées** (personne n'a intérêt à tromper l'outil), **vol du modèle** (modèle standard du marché, rien de propre au cabinet).

## 5. Architecture cible et sobriété

Schéma joint (`schema_archi_cible.md`). Une recherche hébergée en France qui combine les mots et le sens (un petit modèle retrouve les décisions qui parlent de la question avec d'autres mots, sans rien rédiger), puis des modèles de courriers pré-remplis. Rien ne dépend du serveur du cabinet : fichiers copiés chez l'hébergeur, nouvelles décisions déposées par l'assistante.

**LLM refusé** (IA qui rédige du texte, type ChatGPT) :
- *Recherche* : une IA qui rédige, même nourrie des décisions du cabinet (ce qu'on appelle un RAG), peut mal résumer ou inventer une référence, ce que le cabinet exclut.
- *Courriers* : le problème est l'absence de modèles à jour, pas la rédaction ; un modèle validé n'a plus que ses champs à relire, un texte généré se relit en entier.
- *Secret* : un service de plus exposé aux dossiers, pour un gain non démontré.

**Écarté aussi** : jurisprudence publique (déjà couverte par l'abonnement) ; entraînement d'un modèle (rien à prédire) ; développement sur mesure (budget) ; installation au cabinet (plus personne pour l'entretenir).

## 6. Indicateurs, seuils, questions ouvertes

| Indicateur | Cible | Seuil d'acceptabilité | Comment on le mesure |
|---|---|---|---|
| Temps pour retrouver une décision | 30 min → moins d'1 min | 5 min (gain encore ≈ 4 h par jour) | Chronométrage d'une semaine, avant et après |
| Bonne décision dans les 5 premiers résultats | 9 sur 10 | 8 sur 10 (proposé, à valider) : en dessous, l'avocat revient à l'ancienne méthode | Jeu de test : recherche par mots seule, puis mots + sens |
| Décisions inventées | 0 | 0 : erreur critique pour l'avocat | Jeu de test ; garanti par la conception (aucun texte généré) |
| Décisions consultables | Toutes les lisibles | 90 % du fonds (proposé, à revoir après mesure des scans) | Consultables ÷ inscrites au registre |
| Temps de rédaction d'un courrier | Départ non mesuré | À fixer après mesure | Chronométrage d'une semaine |

**Objectif « une heure par jour et par avocat »** (12 h par jour) : la recherche rapporte au plus ≈ 4 h 50 par jour, le reste dépend des courriers, non mesurés ; objectif à rediscuter ensemble après la mesure.

**Prochaines étapes** : 1. avant le 31/12, hébergeur choisi, décisions et registre copiés, accès du prestataire coupés ; 2. une semaine de mesure (recherches, courriers, jeu de test) ; 3. test avec quelques avocats, puis export du logiciel de gestion pour les courriers.

**Questions ouvertes** : 1. Combien de temps prend la rédaction d'un courrier type ? 2. Qui sauvegarde le serveur aujourd'hui ? 3. Le prestataire ouvrira-t-il le serveur pour la copie avant son départ ? 4. Le registre couvre-t-il les 15 ans, et la colonne « juridiction » est-elle remplie par défaut ? 5. Tous les avocats doivent-ils voir toutes les décisions ? 6. Des IA grand public sont-elles déjà utilisées pour les dossiers ?
