---
title: 'Définir le succès de conférence Audio, Système téléphonique avec forfait d’appel, ou Système téléphonique avec routage direct : Microsoft Teams'
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Mesurer les résultats de votre conférence Audio, le système téléphonique avec des Plans de l’appel, ou le déploiement de routage d’un système téléphonique directe et vérifiez que vous avez obtenu les résultats que vous souhaitiez.
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: becf9e671507f121378a8361677254e2c3c51b69
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304955"
---
# <a name="define-my-success"></a>Définir ma réussite

Cet article donne une vue d’ensemble de la configuration requise pour définir la réussite du déploiement de conférence Audio, le système téléphonique avec des Plans de l’appel, ou acheminement d’un système téléphonique Direct pour votre organisation. En définissant correctement l’aspect de réussite, vous pouvez mesurer les résultats en tant que votre progression par le biais de votre déploiement et vérifier que les résultats que vous obtenez sont celles que vous souhaitiez.

<!--ENDOFSECTION-->

**Conférence audio** permet aux organisations avec les autres points d’entrée pour toutes les réunions (ad hoc ou planifiées) en autorisant les participants pour joindre via le réseau téléphonique commuté (RTC) à l’aide de fixe, privé autocommutateur (PBX) ou des téléphones mobiles. Cela est utile lorsque l’organisateur ou les participants ne sont pas devant un ordinateur, ou lorsque les connexions de données sont indisponibles ou trop peu fiable pour prendre en charge les communications vocales, comme dans une zone à distance avec la couverture de données mobiles taches, ou connecté à un Wi-Fi gratuite, public service avec une bande passante limitée, ou lorsque vous préfèrent vous connecter à la réunion à l’aide d’un point de terminaison de téléphonie accessibles pour les participants à la réunion.

**Système téléphonique avec l’appel Plans (« appel Plans »)** permet aux organisations moderniser leur espace de travail en permettant aux utilisateurs d’effectuer des appels professionnels à partir de leurs ordinateurs et périphériques mobiles. Modernisation de l’espace de travail peut faire partie d’un nombre quelconque de scénarios, une implémentation basée sur les activités de travail, un bureau principal déplacer, une actualisation ajuster à la sortie d’office, le retrait d’une solution PBX héritée, à l’issue d’un contrat de fournisseur de service RTC et ainsi de suite. Avec l’appel prévoit, Microsoft facilite la connectivité au réseau RTC.

**Téléphone système routage Direct (« routage Direct »)** offre les mêmes avantages répertoriés ci-dessus pour les Plans de l’appelant, les organisations sauf qu’une connectivité PSTN est facilitée par un fournisseur tiers au lieu de Microsoft. Ainsi, pour le déploiement dans les pays où des Plans de l’appel ne sont pas disponibles ou dans les déploiements où un contrat de fournisseur de service RTC doit être conservée ou l’interopérabilité avec certains systèmes locaux est nécessaire. Un scénario supplémentaire à prendre en compte le routage Direct est l’interopérabilité de système de téléphonie. Alors que les utilisateurs sont en cours de transition à appeler dans les équipes, certains utilisateurs peuvent rester sur PBX hérité. Cas d’utilisation directe permet routage coexistence. Le trafic d’appel entre les utilisateurs sur les systèmes et les équipes restent dans l’organisation.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Définir des exemples d’utilisation d’audioconférence, l’appel des Plans ou routage Direct

Pour commencer, les parties prenantes du projet principal doivent définir des exemples d’utilisation qui prennent en charge l’implémentation de conférence Audio, des Plans de l’appel ou routage Direct.

Exemples d’utilisation sont destinées à définir et commerciaux attendue et mesurable de document sont les suivantes :

-   Description du processus métiers en cours

-   Problèmes avec le processus d’entreprise

-   Comment la technologie peut aider à surmonter ces difficultés

-   Les résultats pour l'entreprise attendus et mesurables si ces difficultés sont surmontées.

> [!TIP]
> Voici un exemple d’un cas d’utilisation pour une audioconférence business terminé :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>Contoso fait actuellement appel à des services de conférence PSTN fournis par le fournisseur de téléphonie local titulaire facturés par minutes de réunion pour les réunions internes et celles impliquant des parties externes.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>Contoso passe à peu près USD1 millions par an pour la conférence PSTN en cours de service, avec 75 % des coûts engagés pour les réunions internes. L’utilisation de points de terminaison de téléphonie traditionnelle pour participer à des réunions hébergées par le service de conférence PSTN n’est pas alignée sur le plan de l’organisation d’adopter les équipes comme plateforme de collaboration et les communications.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Avec l’adoption de Microsoft Teams comme une communication modernes et la plateforme de collaboration, les utilisateurs internes sont supposés principalement participer à des réunions à l’aide de leur PC équipé de casques optimisées et périphériques salle de réunion. Le service de conférence Audio sera disponible pour prendre en charge les participants externes ou pour prendre en charge les situations où l’utilisation de l’audio de PC n’est pas favorable pour les participants internes.|
> |**Résultats de l’entreprise attendus et mesurables**<br>Le déplacement aux équipes comme plateforme de collaboration, combinées avec le service de conférence Audio, communications modernes et réduire considérablement le coût pour fournir le service de conférence PSTN.|

<br>

> [!TIP]
> Voici un exemple d’un cas d’utilisation de business terminé pour l’appel des Plans :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>Configuration standard des espaces de travail de Contoso office inclut un téléphone de bureau pour chaque bureau. Chaque employé a reçu un direct vers l’intérieur composer le numéro de téléphone (DID)). Les téléphones de bureau sont connectés à un système PBX et connectés au PSTN via une jonction de protocole (SIP) session initiation. Les employés peuvent uniquement émettre et recevoir des appels téléphoniques à leurs téléphones de bureau affectés.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>Analyse de l’utilisation des téléphones de bureau indique que seuls 10 % des téléphones de bureau sont utilisés activement avec le reste configuré pour transférer les appels aux téléphones mobiles ou pour faire sonner simultanément aux téléphones mobiles. Mise à jour le système PBX existant et les téléphones de bureau associées contribue à 20 % du coût de service de téléphonie mensuel de Contoso.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Plans d’appel permettra d’ordinateur du personnel d’un utilisateur recevoir et effectuer des appels téléphoniques via le réseau de données en tirant parti de l’application Microsoft Teams native. Cela élimine le besoin pour déployer et gérer des téléphones de bureau et ouvre la possibilité de mettre hors service le système PBX existant, car le service peut être remis via le nuage via le réseau avec aucune dépendance sur un système téléphonique traditionnel.|
> |**Résultats de l’entreprise attendus et mesurables**<br>Suppression des besoins de maintenance et la mise hors service des PBX hérités et les téléphones de bureau fournira une réduction de 20 % de téléphonie mensuel des frais de service. Plans d’appel simplifie les espaces de travail office permettant de Contoso étendre ses opérations en établissant les nouveaux bureaux avec des frais de téléphone initial minimal.|

<br>

> [!TIP]
> Voici un exemple d’un cas d’utilisation pour le routage Direct business terminé :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>Configuration standard des espaces de travail de Contoso office inclut un téléphone de bureau pour chaque bureau. Chaque employé a reçu un direct vers l’intérieur composer le numéro de téléphone (DID)). Les téléphones de bureau sont connectés à un système PBX et connectés au PSTN via une jonction de protocole (SIP) session initiation. Les employés peuvent uniquement émettre et recevoir des appels téléphoniques à leurs téléphones de bureau affectés.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>Analyse de l’utilisation des téléphones de bureau indique que seuls 10 % des téléphones de bureau sont utilisés activement avec le reste configuré pour transférer les appels aux téléphones mobiles ou pour faire sonner simultanément aux téléphones mobiles. Mise à jour le système PBX existant et les téléphones de bureau associées contribue à 20 % du coût de service de téléphonie mensuel de Contoso.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Le contrat de fournisseur de jonction SIP a été récemment signé et sera en place pour trois ans. Routage direct permet une connectivité PSTN à être fourni par le fournisseur de jonction SIP et permettre également PC d’un utilisateur recevoir et effectuer des appels téléphoniques via le réseau de données en tirant parti de l’application Microsoft Teams native. Cela élimine le besoin pour déployer et gérer des téléphones de bureau et ouvre la possibilité de mettre hors service le système PBX existant, tout en conservant un encombrement limité locale session border controller (SBC).|
> |**Résultats de l’entreprise attendus et mesurables**<br>Suppression des besoins de maintenance et la mise hors service des PBX hérités et les téléphones de bureau fournira une réduction de 20 % de téléphonie mensuel des frais de service. Routage direct simplifie espaces de travail office permettant de Contoso étendre ses opérations en établissant les nouveaux bureaux avec des frais de téléphone initial minimal.|

Outre la définition de votre entreprise cas d’utilisation, pour définir les limites du projet que vous devez viser clarté lecteur autour de :

-   **Étendue d’organisation :** L’implémentation de conférence Audio, des Plans de l’appel ou routage Direct peut englober l’intégralité de votre organisation ou divisions spécifiques.

-   **Chronologie du projet :** Le scénario spécifique au projet sera exécuté.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Quels sont tous les cas d’utilisation de l’entreprise pour une audioconférence permettant d’identifier dans votre organisation ?</li><li>Quels sont tous les cas d’utilisation de l’entreprise pour l’appel des Plans permettant d’identifier dans votre organisation ?</li><li>Quels sont tous les cas d’utilisation de l’entreprise pour le routage Direct vous pouvez identifier dans votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter tous les exemples d’utilisation pour une audioconférence pour votre organisation.</li><li>Tous les exemples d’utilisation du document pour l’appel des Plans pour votre organisation.</li><li>Tous les exemples d’utilisation du document pour le routage directes pour votre organisation.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identifier les parties prenantes clés

Les exemples d’utilisation définies à l’étape précédente incluent une étendue d’organisation pour l’implémentation de conférence Audio, des Plans de l’appel ou routage Direct. Sur la base, vous pouvez effectuer la matrice des parties prenantes complète pour inclure les personnes appropriées impliquer dans le projet.

> [!TIP]
> Voici un exemple de modèle de matrice des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes intégrées dans le projet :
> 
> |Rôle  |Description  |Nom, informations de contact, emplacement  |
> |---------|---------|---------|
> |Sponsor exécutif du projet|<ul><li>Prendre autorité ultime et les responsabilités du projet et de la remise sur les objectifs du projet.</li><li>Résoudre les problèmes transmis par le responsable de projet.</li><li>Promotion de communication au sein de la société sur les objectifs du projet.</li><li>Prendre des décisions stratégiques clées.</li><li>Garantir la disponibilité des ressources nécessaires et de votre budget.</li><li>Mise en œuvre entreprise trimestrielle passe en revue (QBRs).</li><li>Lecteur et prise en charge des efforts de campagne de sensibilisation.</li><li>Servir au Sponsor de projet pour le déploiement de programme.</li></ul>|TBA|
> |Chef de projet|<ul><li>Gérer et responsable de l’équipe de projet.</li><li>Coordonner les partenaires et les équipes de travail dans le projet.</li><li>Être responsable de la création et des plans de gestion de projet répondre aux résultats clés trimestriels.</li><li>Résoudre les problèmes fonctionnel.</li><li>Fournissent des mises à jour régulières aux organisateurs de projet.</li><li>Incorporer des aspects d’adoption dans le plan de projet toutes les.</li><li>Mise en œuvre Business mensuel et révisions opérationnelles (MBR), contribuer à QBRs.</li></ul>|TBA|
> |Chef/architecte de la collaboration|<ul><li>Exécuter la stratégie de collaboration définie par les dirigeants de l’entreprise.</li><li>Analyser et choisir des produits de collaboration qui répondent aux objectifs de la société.</li><li>Concevoir des opérations pour les produits de collaboration.</li><li>Définir l’opération et prend en charge les modèles.</li><li>Contribuer aux analyses d’activité mensuels et trimestriels.</li></ul>|TBA|
> |Consultant|<ul><li>Responsable des services de configuration</li><li>Contribuer à l’architecture de solution globale.</li></ul>|TBA|
> |Gestionnaire de projets|<ul><li>Développer et mettre à jour le plan de projet.</li><li>Gérer les livrables du projet inséré dans le plan de projet et le budget.</li><li>Enregistrer et de gérer les problèmes du projet, y compris les problèmes.</li><li>Mener des appels quotidienne toutes les semaines.</li><li>Sécurité de collaborer avec et fournir des mises à jour pour privilégiées project.</li><li>Travailler avec l’architecte pour définir l’approche et la communication des plans de gestion change.</li></ul>|TBA|
> |Spécialiste en gestion des changements/adoption|<ul><li>Fournir l’entrée pendant la phase de découverte d’adoption et de formation aux processus.</li><li>Participer à l’atelier de stratégie d’adoption.</li><li>Développer et prendre la responsabilité de la stratégie d’adoption.</li><li>Développer et exécuter le plan de communication.</li><li>Fournir des formations pour les utilisateurs.</li><li>Recueillir les commentaires et mener des enquêtes.</li></ul>|TBA|
> |Directeur de réseau|<ul><li>Fournir l’entrée pendant la phase de découverte dans la conception d’un réseau.</li><li>Participer à la planification pendant l’atelier phase prévoir.</li><li>Coordonner le travail de l’équipe de mise en réseau durant l’exécution du projet.</li></ul>|TBA|
> |Directeur de la sécurité|<ul><li>Fournir l’entrée pendant la phase de découverte dans les processus et la conception de la sécurité.</li><li>Participer à la planification pendant l’atelier phase prévoir.</li><li>Coordonner le travail de l’équipe de sécurité lors de l’exécution du projet.</li></ul>|TBA|
> |Directeur de la téléphonie|<ul><li>Fournir l’entrée pendant la phase de découverte dans la conception de téléphonie.</li><li>Participer à la planification pendant l’atelier phase prévoir.</li><li>Coordonner le travail de l’équipe de téléphonie durant l’exécution du projet.</li></ul>|TBA|
> |Directeur de bureau|<ul><li>Fournir une entrée pendant la phase de découverte dans les clients et des mises à jour.</li><li>Participer à la planification pendant l’atelier prévoir.</li><li>Coordonner le travail de l’équipe du bureau pendant l’exécution du projet.</li></ul>|TBA|
> |Responsable du support|<ul><li>Fournir une entrée pendant la phase de découverte dans opérationnels et de prise en charge des modèles.</li><li>Participer à la planification pendant l’atelier phase prévoir.</li><li>Participer à la planification de modèle de prise en charge.</li><li>Coordonner le travail des équipes de support technique et des ressources pendant l’exécution du projet.</li></ul>|TBA|
> |Représentants d'unité commerciale|<ul><li>Contribuer à guides utilisateur Kit d’adoption et de la documentation.</li><li>Contribuer à et consultez les exemples d’utilisation.</li></ul>|TBA|
> |Directeur du déploiement|<ul><li>Assurez-vous que les conditions préalables au déploiement sont réunies.</li><li>Prendre part à être impliqués dans les activités de la phase intégré des ressources.</li><li>Participer à des réunions en revue et établir des rapports sur l’état du déploiement.</li></ul>|TBA|
> |Administrateurs informatiques|<ul><li>Aide à la planification de test et l’exécution. Ce rôle n’est pour les professionnels de l’informatique.</li></ul>|TBA|
> |Propriétaire de service|<ul><li>Être responsable de l’opération de la conférence Audio, des Plans de l’appel ou service Routage Direct, ascendants.</li><li>Propriétaire du service de conférence Audio, des Plans de l’appel ou routage Direct.</li></ul>|TBA|
> |Ambassadeurs de la qualité|<ul><li>Lecteur des commentaires de qualité, la fiabilité et utilisateur.</li><li>Identifier les tendances de qualité et mise à jour avec les équipes respectifs du lecteur.</li><li>Rapport par le biais du comité directeur sur le marché.</li><li>Rapport sur la qualité, la fiabilité et utilisateur ressenti les taux mes appels Net promoteur Score.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Qui remplit chaque rôle principales parties prenantes pour votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter toutes les parties prenantes et communiquer les attentes du rôle et les responsabilités pour chaque personne assignée.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Définir OKRs, KSIs et des risques

Avec les parties prenantes du projet assemblés, capable de traduire les exemples d’utilisation, la portée d’organisation et estimés du projet dans les résultats de la clé (OKRs) et d’objectifs, et les mesures de réussite du projet peuvent être définis comme une liste d’indicateurs de réussite clés (KSIs).

Participer pleinement aux parties prenantes du projet définition OKRs et KSIs est essentielle pour garantir un sentiment de possession et de l’alignement de ces mesures de réussite aux besoins d’organisation.

OKRs contiennent les objectifs que vous définissez au début du projet, et vous définissez résultats clés mesurables sur une base trimestrielle. Vous passez en revue les résultats clés tous les mois pour effectuer le suivi de l’état du projet global, et, en fonction de l’avancement — vous ajustez les planifications trimestrielles selon vos besoins.

> [!TIP]
> Exemples de OKRs pertinents pour une implémentation de conférence Audio peuvent être référencés ci-dessous :
> <br>
> 
> **Vision : augmenter la productivité an optimisant les investissements dans Office 365**
> 
> |Objectifs  |Résultats de la clé  |À suivre  |
> |---------|---------|---------|
> |Déployer l’audioconférence dans Teams d’ici la fin de l’exercice fiscal 2018|T1 de l’exercice 2018 : déployer l’audioconférence dans Teams globalement|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désactiver l’ancien service de conférence PSTN à l’échelle globale d'ici la fin de l’exercice fiscal 2018|T2 de l’exercice 2018 : désactiver l’ancien service de conférence PSTN à l’échelle globale|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

<br>

> [!TIP]
> Exemples de OKRs pertinents pour une mise en œuvre des Plans de l’appel peuvent être référencés ci-dessous :
> <br>
> 
> **Vision : augmenter la productivité an optimisant les investissements dans Office 365**
> 
> |Objectifs  |Résultats de la clé  |À suivre  |
> |---------|---------|---------|
> |Déployer des Plans de l’appel dans les succursales European à la fin de l’année fiscale 2018|FY18Q3 : Déployer des Plans de l’appel dans office Londres|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Mettre hors service des PBX hérités dans office London à la fin de l’année fiscale 2018|FY18Q4 : Mettre hors service des PBX hérités dans office Londres|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|
> 
> [!TIP]
> Exemples de OKRs pertinents pour une implémentation de routage Direct peuvent être référencés ci-dessous :
> <br>
> 
> **Vision : augmenter la productivité an optimisant les investissements dans Office 365**
> 
> |Objectifs  |Résultats de la clé  |À suivre  |
> |---------|---------|---------|
> |Déployez le routage Direct dans les succursales canadien à la fin de l’année fiscale 2018|FY18Q3 : Déployer un routage Direct dans office Toronto|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Mettre hors service un PBX hérité dans office Toronto à la fin de l’année fiscale 2018|FY18Q4 : Mettre hors service un PBX hérité dans office Toronto|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

<br>

KSIs mesurer la qualité et la réussite des résultats et compléter la nature de OKRs (atteint ou ne pas atteint) binaire en détaillant les résultats de la bonne et/ou incorrectes.

Lors de la définition KSIs, nous vous conseillons d’utiliser « spécifiques, mesurables, peut être assignés, réalistes, liées au temps » (dynamique) critères :

-   Spécifiques : cibler une zone spécifique pour d’amélioration du produit

-   Mesurable : quantifier ou proposer au moins un indicateur de progression

-   Peut être assigné : spécifiez qui fera

-   Realistic : indiquer ce que les résultats peuvent réaliste atteint, compte tenu des ressources disponibles

-   Liées au temps : spécifiez si les résultats peuvent être obtenus

> [!TIP]
> Voici un exemple d'indicateur de succès clé approprié à ce projet :
> 
> |Type  |Questions sur l'indicateur de succès clé et critères  |Comment les mesurer  |Critères de réussite  |Mesurés  |Responsable  |
> |---------|---------|---------|---------|---------|---------|
> |Utilisation/adoption|La qualité des appels est égale ou meilleure qu’avec la solution précédente|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable des technologies de l’information|
> |Utilisation/adoption|Microsoft Teams a facilité le processus de communication|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
> |Utilisation/adoption|Les utilisateurs utilisent activement la solution|Rapports Office 365, tableau de bord de la qualité des appels|80 % des utilisateurs l’utilisent quotidiennement|Jour|Équipe responsable de la gestion des changements|
> |Utilisation/qualité|Le pourcentage d’appels/conférences médiocres doit être minimal|Tableau de bord de la qualité des appels|< 5 % d'appels médiocres par mois|Chaque jour|Équipe responsable des technologies de l’information|
> |Utilisation/support|Je sais comment obtenir le support technique|Enquête|90% des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
> |Utilisation/support|Je suis satisfait de la qualité du support technique|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après chaque incident|Équipe responsable des technologies de l’information|
> |Financier|Réduction du nombre de minutes de conférence héritée|Système financier|Atteindre le retour sur investissement défini|Basé sur le retour sur investissement|Équipe responsable de la gestion des changements|

Vous devez identifier les risques dans le cadre de cet exercice et définir un plan d’atténuation pour chaque risque identifié. Ces informations peuvent être capturé dans un Registre de risques.

> [!TIP]
> Votre Registre des risques peut être référencée que dans l’exemple ci-dessous :
> 
> |Risque  |Probabilité  |Impact  |Global  |Plan d’atténuation  |
> |---------|---------|---------|---------|---------|
> |Une fusion prochaine ajoutera jusqu’à 1000 personnes|Haut|Haut|Haut|<ul><li>Pour des sociétés fusionnées, créez un OKR distinct qui s’applique à leurs propres phases du projet (prévoir, Onboard, valeur lecteur)</li><li>N’incluez pas ces OKRs dans OKRs existants</li></ul>|
> |Le transfert des numéros de téléphone retardera la réalisation du projet|Haut|Haut|Haut|<ul><li>Préparer toutes les informations nécessaires pour prendre en charge le numéro de téléphone portage à l’avance (enregistrement de service de client, facturation plus d’informations, lettre d’autorisation)</li><li>Ajuster la chronologie du projet pour prendre en charge le délai d’exécution portage numéro de téléphone</li><li>Communiquer l’utilisation de nouveaux numéros de conférence rendez-vous aux participants externes</li><li>Utilisez les numéros de téléphone temporaire avec manipulation de l’ID de l’appelant</li></ul>|
> |Reconception du réseau planifiée|Élevée|Moyen|Moyen|<ul><li>Avant d’implémenter des équipes comme plateforme de collaboration et communications modernes, mener une évaluation de préparation du réseau pour les sites dans la portée du projet</li></ul>|
> |Configuration de SBC|Haut|Haut|Haut|<ul><li>Avant d’implémenter des équipes en tant que remplacement pour le système PBX existant, vérifiez que vous pouvez vous réunir toutes les exigences de configuration SBC</li><li>Confirmez que les ressources de support SBC ont les compétences approprié pour configurer le contrôleur SBC pour le routage Direct</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Quelles sont vos organization& #39 ; s OKRs et KSIs ?</li><li>Les risques ont identifié pertinents pour l’implémentation de conférence Audio dans votre organisation ? Quels sont les plans d’atténuation des risques identifiés ?</li><li>Les risques ont identifié pertinents pour l’implémentation de Plans de l’appel dans votre organisation ? Quels sont les plans d’atténuation des risques identifiés ?</li><li>Les risques ont identifié pertinents pour l’implémentation de routage Direct dans votre organisation ? Quels sont les plans d’atténuation des risques identifiés ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les OKRs et les KSIs et établir l’historique de risques.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Établir un comité directeur

Un comité directeur est un groupe de gouvernance des principales parties prenantes et les chefs de projet qui ont été introduites pour guider un projet ou un programme vers son commerciaux défini. Comité directeur n’est pas directement responsable de la *façon dont* le projet est remis, mais plutôt *le* que projet fournit à l’entreprise.

Chaque projet nécessite une vision convenues et la charte. Pour fournir les résultats de votre choix dans le projet, la mission doit être clairement définie, et il doit être surveillés et gérés. Devient la responsabilité du comité directeur : lecteur décisions, de notification, fournissez supervision stratégique, en guise de préconise à l’organisation pour les initiatives du projet, et, lorsque cela est nécessaire : supprimer les bloqueurs.

Votre organisation doit mettre pensé significative à la formation du comité directeur. Comité doit s’assurer que le projet atteint les objectifs commerciaux, vous avez défini pour avancer dans toute l’organisation, meet régulièrement pour traiter de la pulse en cours du projet et aider à débloquer les obstacles rencontrés le long de la moyen.

Le comité doit définir sa charte pour inclure certains objectifs principaux :

-   Conserver un alignement fort entre l’équipe de projet et les cadres supérieurs sponsor exécutif.

-   Fournissent des informations sur l’état du projet au sponsor exécutif ou cadres supérieurs.

-   Autoriser le sponsor exécutif ou l’équipe de direction d’exécution fournir la direction et entrée au projet et vous assurer qu’il s’aligne sur commandes changent objectifs d’entreprise, en ajustant les plans de projet, les résultats principaux objectifs (OKRs) et autres activités de projet.

Comité directeur satisfait à intervalles réguliers tout au long de la durée de vie d’un projet pour garantir l’alignement entre la direction d’organisation et l’équipe de projet. Cette réunion critique garantit que la direction du projet est prise en charge complète du leader et incorpore des commentaires fournis par les cadres dirigeants dans le projet à la réussite du lecteur. Comité utilise ces réunions pour mieux en l’état du projet et pour :

-   Accord sur les résultats commerciaux qui s’alignent à l’étude de cas, et pour garantir le projet dirige vers la remise de ces résultats.

-   Vérifier et d’approuver le projet de précision et de conformité avec l’étude de cas.

-   Passez en revue et vérifier les modifications apportées à l’étude de cas susceptibles d’affecter les résultats commerciaux défini.

-   Prendre des décisions stratégiques concernant la définition des priorités des livrables du projet et d’approuver des livrables intermédiaires.

-   Identifier, gérer et atténuer les trous, des risques et problèmes où influence supplémentaire est requise à partir du comité.

-   Rassembler prise en charge de la sponsor exécutif ou de l’équipe de direction d’exécution pour les problèmes qui nécessitent l’escalade, ordre de priorité et résoudre les conflits entre les divisions des parties prenantes. 

-   Fournir des commentaires formelle et des recommandations pour les cadres supérieurs, Conseil des modifications, ou autres métiers et informatiques parties prenantes, le cas échéant.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si un comité directeur est requis pour votre organisation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Identifier les membres du comité directeur.</li><li>Planifier des réunions du comité.</li><li>Préparer pour les réunions du comité.</li><li>Comité directeur de réunions.</li><li>Effectuer une action en fonction de comité d’entrée de la réunion.</li></ul>|

Vous trouverez des instructions détaillées supplémentaires sur la façon d’utiliser un comité approprié dans le [guide du comité directeur](envision-steering-committee-complete-guide.md).

<!--ENDOFSECTION-->