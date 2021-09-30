---
title: Audioconférence, forfaits d’appels ou routage direct
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Définition du succès du déploiement de l’audioconférence, de la Système téléphonique avec des plans d’appel ou Système téléphonique routage direct pour votre organisation.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e669e0454f65ef4d3d5ecc0b4832b33201d2703
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011758"
---
# <a name="define-my-success"></a>Définir ma réussite

Cet article donne une vue d’ensemble des conditions requises pour définir le succès du déploiement de l’audioconférence, des Système téléphonique avec des plans d’appel ou du Système téléphonique routage direct pour votre organisation. En définissant correctement ce à quoi ressemble le succès, vous pouvez mesurer vos résultats à mesure que vous progressez dans votre déploiement et vérifier que les résultats que vous avez obtenus sont ceux que vous vouliez.

<!--ENDOFSECTION-->

**L’audioconférence** fournit aux organisations des points d’entrée supplémentaires pour toutes les réunions (ad hoc ou programmées) en permettant aux participants à la réunion d’y participer via un réseau téléphonique commuté (PSTN) en composant un numéro fixe, privé (PBX) ou un téléphone mobile. Cela est utile lorsque l’organisateur ou les participants ne sont pas devant un ordinateur, ou lorsque les connexions de données sont indisponibles ou peu fiables pour prendre en charge les communications vocales, par exemple, dans une zone distante avec une couverture de données mobile facile à repérer, ou connectées à un service de Wi-Fi public gratuit avec une bande passante limitée, ou lorsque les participants à la réunion préfèrent se connecter à la réunion à l’aide d’un point de terminaison téléphonique facilement accessible.

**Système téléphonique** des forfaits d’appels offre aux organisations un moyen de moderniser leur lieu de travail en permettant aux utilisateurs de passage d’appels téléphoniques professionnels à partir de leurs ordinateurs et appareils mobiles. La sécurité de l’espace de travail peut être dans le cadre de nombreux scénarios : implémentation professionnelle basée sur l’activité, déplacement de bureau majeur, actualisation complète du bureau, retrait d’une solution PBX héritée, conclusion d’un contrat de fournisseur de services PSTN, etc. Avec les forfaits d’appels, Microsoft facilite la connectivité au réseau PSTN.

**Système téléphonique** Routage direct (« Routage direct ») offre aux organisations les mêmes avantages répertoriés ci-dessus pour les plans d’appels, sauf que la connectivité RSTN est facilitée par un fournisseur tiers plutôt que Par Microsoft. Cela permet un déploiement dans les pays où les plans d’appel ne sont pas disponibles, ou dans les déploiements où un contrat de fournisseur de services PSTN existant doit être conservé, ou l’interopérabilité avec certains systèmes locaux est requise. Un autre scénario à envisager pour un routage direct est l’interopérabilité du système téléphonique. Pendant la transition des utilisateurs vers la fonction d’appel Teams, certains utilisateurs peuvent rester sur des systèmes PBX hérités. Le routage direct permet aux deux cas d’utilisation de coexister. Le trafic d’appels entre les utilisateurs sur les systèmes hérités Teams utilisateurs restent au sein de l’organisation.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Définir des cas d’utilisation professionnelle pour l’audioconférence, les forfaits d’appels ou le routage direct

Pour commencer, les principales parties prenantes au projet doivent définir des cas d’utilisation d’entreprise qui supportent l’implémentation de l’audioconférence, des plans d’appel ou du routage direct.

Les cas d’utilisation professionnelle sont destinés à définir et documenter les résultats d’entreprise attendus et mesurables, et incluent les éléments suivants :

-   Description du processus commercial actuel

-   Défis liés au processus d’entreprise existant

-   Comment la technologie peut aider à surmonter ces difficultés

-   Les résultats pour l'entreprise attendus et mesurables si ces difficultés sont surmontées.

> [!TIP]
> Voici un exemple de cas d’utilisation professionnelle complété pour l’audioconférence :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>Contoso fait actuellement appel à des services de conférence PSTN fournis par le fournisseur de téléphonie local titulaire facturés par minutes de réunion pour les réunions internes et celles impliquant des parties externes.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>Contoso dépense environ 1 million de dollars par an pour le service de conférence PSTN actuel, avec 75 % des coûts pour les réunions internes. L’utilisation de points de terminaison téléphoniques traditionnels pour participer aux réunions hébergées par le service de conférence RSTN n’est pas conforme au plan de l’organisation qui permet d’adopter Teams comme plateforme de communication et de collaboration moderne.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Avec l’adoption d’Microsoft Teams comme plateforme de communication et de collaboration moderne, les utilisateurs internes sont censés participer principalement aux réunions à l’aide de leur PC équipé de casques optimisés et d’appareils de salle de réunion. Le service d’audioconférence sera disponible pour prendre en charge des participants externes ou pour prendre en charge des situations dans lesquelles l’utilisation de l’audio sur PC n’est pas gratuite pour les participants internes.|
> |**Résultats de l’entreprise attendus et mesurables**<br>L’Teams en tant que plateforme de communication et de collaboration moderne, combinée au service d’audioconférence, permet de réduire considérablement les coûts de la prestation du service de conférence PSTN.|

<br>

> [!TIP]
> Voici un exemple de cas d’utilisation professionnelle complété pour les plans d’appel :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>La configuration standard des espaces de travail de Bureau de Contoso inclut un téléphone de bureau pour chaque bureau. Un numéro de téléphone personnel (DID) a été attribué à chaque employé. Les téléphones de bureau sont connectés à un système PBX et connectés au réseau PSTN via une ligne SIP (Session Initiation Protocol). Les employés peuvent uniquement appeler et recevoir des appels téléphoniques sur les téléphones de bureau qui leur sont attribués.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>L’analyse de l’utilisation des téléphones de bureau indique que seulement 10 % des téléphones de bureau sont activement utilisés, le reste des téléphones ayant été configurés de manière à pouvoir soit les appeler vers des téléphones mobiles, soit à les faire sonner simultanément. La maintenance du système PBX existant et des téléphones de bureau associés contribue à 20 % des coûts de service téléphonique mensuel de Contoso.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Les forfaits d’appels permettent à l’ordinateur personnel d’un utilisateur de recevoir et de recevoir des appels téléphoniques sur le réseau de données en tirant parti de l’application Microsoft Teams native. Cela supprime la nécessité de déployer et de mettre à jour les téléphones de bureau, et ouvre la possibilité de désaffecter le système PBX existant, car le service téléphonique peut être livré via le cloud sur le réseau sans dépendance sur un système téléphonique traditionnel.|
> |**Résultats de l’entreprise attendus et mesurables**<br>La suppression des exigences de maintenance et de la désaffectation des téléphones de bureau et PBX hérités permettra une réduction de 20 % des dépenses de service téléphoniques mensuelles. Les plans d’appel simplifieront les espaces de travail de bureau, ce qui permettra à Contoso d’étendre ses opérations en établissant de nouveaux bureaux avec un coût téléphonique minimal à l’avance.|

<br>

> [!TIP]
> Voici un exemple de cas d’utilisation professionnelle achevé pour le routage direct :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>La configuration standard des espaces de travail de Bureau de Contoso inclut un téléphone de bureau pour chaque bureau. Un numéro de téléphone personnel (DID) a été attribué à chaque employé. Les téléphones de bureau sont connectés à un système PBX et connectés au réseau PSTN via une ligne SIP (Session Initiation Protocol). Les employés peuvent uniquement appeler et recevoir des appels téléphoniques sur les téléphones de bureau qui leur sont attribués.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>L’analyse de l’utilisation des téléphones de bureau indique que seulement 10 % des téléphones de bureau sont activement utilisés, le reste des téléphones ayant été configurés de manière à pouvoir soit les appeler vers des téléphones mobiles, soit à les faire sonner simultanément. La maintenance du système PBX existant et des téléphones de bureau associés contribue à 20 % des coûts de service téléphonique mensuel de Contoso.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Le contrat de fournisseur de la ligne SIP a récemment été signé et sera en place pendant trois ans. Le routage direct permet à la connectivité PSTN d’être fournie par le fournisseur de ligne SIP et permet également à l’ordinateur personnel d’un utilisateur de recevoir et de passer des appels téléphoniques sur le réseau de données en tirant parti de l’application Microsoft Teams native. Cela supprime la nécessité de déployer et de mettre à jour les téléphones de bureau, et vous permet de désaffecter le système PBX existant, tout en conservant un nombre limité d’empreintes dans le contrôleur de session en session sur site.|
> |**Résultats de l’entreprise attendus et mesurables**<br>La suppression des exigences de maintenance et de la désaffectation des téléphones de bureau et PBX hérités permettra une réduction de 20 % des dépenses de service téléphoniques mensuelles. Le routage direct simplifiera les espaces de travail du bureau, ce qui permettra à Contoso d’étendre ses opérations en établissant de nouveaux bureaux avec un coût téléphonique minimal.|

En plus de définir les cas d’utilisation de votre entreprise, vous devez définir les limites du projet afin de clarifier les éléments :

-   **Étendue organisationnelle :** L’implémentation de l’audioconférence, des plans d’appel ou du routage direct peut inclure l’ensemble de l’organisation ou seulement des unités commerciales spécifiques.

-   **Project chronologie :** Chronologie spécifique qui s’exécutera dans le projet.

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Points de décision|<ul><li>Quels sont les cas d’utilisation de l’audioconférence que vous pouvez identifier dans votre organisation ?</li><li>Quels sont les cas d’utilisation professionnelle des plans d’appels que vous pouvez identifier dans votre organisation ?</li><li>Quels sont les cas d’utilisation professionnelle pour le routage direct que vous pouvez identifier dans votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documenter toutes les affaires d’utilisation pour l’audioconférence pour votre organisation.</li><li>Documentez tous les cas d’utilisation professionnelle pour les plans d’appel pour votre organisation.</li><li>Documenter tous les cas d’utilisation professionnelle pour le routage direct pour votre organisation.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identifier les parties prenantes clés

Les cas d’utilisation d’entreprise définis à l’étape précédente incluent une étendue organisationnelle pour l’audioconférence, les plans d’appel ou l’implémentation du routage direct. Sur cette base, vous pouvez mettre en place la matrice complète des parties prenantes pour inclure les personnes concernées dans le projet.

> [!TIP]
> Voici un exemple de modèle de matrice des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes intégrées dans le projet :
> 
> |Rôle  |Description  |Nom, informations de contact, emplacement  |
> |---------|---------|---------|
> |Sponsor exécutif du projet|<ul><li>Prenez l’autorité et la responsabilité ultimes pour le projet et la livraison sur les objectifs du projet.</li><li>Permet de résoudre les problèmes qui ont été augmentés par le Project de sécurité.</li><li>Sponsoriser la communication au sein de l’entreprise sur les objectifs du projet.</li><li>Prendre des décisions stratégiques clés.</li><li>Assurez la disponibilité des ressources et du budget requis.</li><li>Conduire des examens trimestriels de l’activité (QBR).</li><li>Drive buy-in and support of awareness campaign efforts.</li><li>Servir de sponsor Project pour le déploiement du programme.</li></ul>|TBA|
> |Chef de projet|<ul><li>Gérez et dirigez l’équipe de projet.</li><li>Coordonnez les partenaires et les équipes de travail impliqués dans le projet.</li><li>Soyez responsable de la création et de la gestion de plans de projet afin d’atteindre des résultats clés trimestriels.</li><li>Résolvez les problèmes fonctionnels croisés.</li><li>Fournir des mises à jour régulières aux sponsors de projet.</li><li>Intégrez les aspects d’adoption au plan de projet général.</li><li>Conduire des révisions métiers et opérationnelles mensuelles (MoR), qui contribuent aux QBR.</li></ul>|TBA|
> |Chef/architecte de la collaboration|<ul><li>Exécuter la stratégie de collaboration définie par les cadres de l’entreprise.</li><li>Analyser et choisir des produits de collaboration qui répondent aux objectifs professionnels de l’entreprise.</li><li>Opérations de conception pour les produits de collaboration.</li><li>Définir des modèles d’opération et de support.</li><li>Contribuez aux révisions mensuelles et trimestrielles de l’entreprise.</li></ul>|TBA|
> |Consultant|<ul><li>Être responsable des services de configuration</li><li>Contribuez à l’architecture globale de la solution.</li></ul>|TBA|
> |Gestionnaire de projets|<ul><li>Développez et maintenez le plan du projet.</li><li>Gérez les livrables du projet en ligne avec le plan et le budget du projet.</li><li>Enregistrez et gérez les problèmes du projet, notamment les escalades.</li><li>Effectuer des appels de support hebdomadaires.</li><li>projet avec des cadres délégués de projet et fournir des mises à jour.</li><li>Travaillez avec l’architecture pour définir l’approche de gestion des changements et les plans de communication.</li></ul>|TBA|
> |Spécialiste en gestion des changements/adoption|<ul><li>Fournir des informations pendant la phase de découverte dans les processus d’adoption et de formation.</li><li>Participez à l’atelier de stratégie d’adoption.</li><li>Développez et prenez les responsabilités de la stratégie d’adoption.</li><li>Développez et exécutez le plan de communication.</li><li>Fournir des formations aux utilisateurs.</li><li>Recueillez des commentaires et effectuez des enquêtes.</li></ul>|TBA|
> |Directeur de réseau|<ul><li>Fournir des informations pendant la phase de découverte dans la conception du réseau.</li><li>Participez à la planification pendant l’atelier de phase de conception.</li><li>Coordonnez le travail de l’équipe en réseau pendant l’exécution du projet.</li></ul>|TBA|
> |Directeur de la sécurité|<ul><li>Pendant la phase de découverte, fournissez des informations sur la conception et les processus de sécurité.</li><li>Participez à la planification pendant l’atelier de phase de conception.</li><li>Coordonnez le travail de l’équipe de sécurité pendant l’exécution du projet.</li></ul>|TBA|
> |Directeur de la téléphonie|<ul><li>Fournir des informations pendant la phase de découverte dans la conception téléphonique.</li><li>Participez à la planification pendant l’atelier de phase de conception.</li><li>Coordonnez le travail de l’équipe téléphonique pendant l’exécution du projet.</li></ul>|TBA|
> |Directeur de bureau|<ul><li>Fournir des informations pendant la phase de découverte dans les clients et mettre à jour le processus.</li><li>Participez à la planification pendant l’atelier de planification.</li><li>Coordonnez le travail de l’équipe de bureau pendant l’exécution du projet.</li></ul>|TBA|
> |Responsable du support|<ul><li>Fournir des informations pendant la phase de découverte dans des modèles opérationnels et de support.</li><li>Participez à la planification pendant l’atelier de phase de conception.</li><li>Participez à la planification du modèle de support.</li><li>Coordonnez le travail des équipes et ressources de support pendant l’exécution du projet.</li></ul>|TBA|
> |Représentants d'unité commerciale|<ul><li>Contribuez aux documents et guides d’adoption basés sur l’utilisateur.</li><li>Contribuez et examinez les cas d’utilisation professionnelle.</li></ul>|TBA|
> |Directeur du déploiement|<ul><li>Assurez-vous que les conditions préalables au déploiement sont remplies.</li><li>Impliquez des ressources pour être impliqués dans les activités de phase d’intégration.</li><li>Participez aux réunions pour passer en revue et préparer des rapports sur l’état du déploiement.</li></ul>|TBA|
> |Administrateurs informatiques|<ul><li>Aide pour la planification et l’exécution des tests. Ce rôle est pour les professionnels de l’informatique.</li></ul>|TBA|
> |Propriétaire de service|<ul><li>Soyez responsable du fonctionnement du service d’audioconférence, de plans d’appel ou de routage direct.</li><li>Possédez le service d’audioconférence, de forfaits d’appels ou de routage direct.</li></ul>|TBA|
> |Ambassadeurs de la qualité|<ul><li>Drive quality, reliability, and user feedback.</li><li>Identifiez les tendances de qualité et pilotez des corrections avec les équipes respectives.</li><li>Revenir au comité exécutif pour revenir aux dirigeants.</li><li>Rapportez sur la qualité, la fiabilité et les opinions des utilisateurs grâce à Évaluer mon appel et Net Promoter Score.</li></ul>|TBA|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Points de décision|<ul><li>Qui remplira-t-elle chaque rôle clé des parties prenantes pour votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documenter toutes les parties prenantes clés et communiquer les responsabilités et les attentes du rôle à chaque personne affectée.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Définir les OKR, les KSI et les risques

Une fois les parties prenantes de projet réunies, vous pouvez traduire les cas d’utilisation professionnelle, l’étendue organisationnelle et les échéanciers des projets en objectifs et résultats clés (OKR), et les mesures de réussite des projets peuvent être définies comme une liste d’indicateurs de réussite clés (KSI).

La participation complète des parties prenantes au développement de stratégies d’entreprise et de KSI est essentielle pour leur permettre de s’assurer qu’elles ont un sentiment de propriété et d’aligner ces mesures de réussite par rapport aux besoins de l’entreprise.

Les indicateurs de performance clés contiennent les objectifs que vous avez définis au début du projet, et vous définissez des résultats clés mesurables sur une base trimestrielle. Vous examinez les principaux résultats tous les mois pour suivre l’état du projet global et, en fonction de l’avancement, vous ajustez les plans trimestriels selon vos besoins.

> [!TIP]
> Voici quelques exemples d’ok pertinents pour une implémentation de l’audioconférence :
> <br>
> 
> **Vision : augmentez la productivité en maximisant les Microsoft 365 ou Office 365 investissement**
> 
> |Objectifs  |Résultats clés  |À faire  |
> |---------|---------|---------|
> |Déployer l’audioconférence dans Teams d’ici la fin de l’exercice fiscal 2018|T1 de l’exercice 2018 : déployer l’audioconférence dans Teams globalement|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désactiver l’ancien service de conférence PSTN à l’échelle globale d'ici la fin de l’exercice fiscal 2018|T2 de l’exercice 2018 : désactiver l’ancien service de conférence PSTN à l’échelle globale|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

<br>

> [!TIP]
> Voici quelques exemples d’ok pertinents pour une implémentation de plans d’appels :
> <br>
> 
> **Vision : augmentez la productivité en maximisant les Microsoft 365 ou Office 365 investissement**
> 
> |Objectifs  |Résultats clés  |À faire  |
> |---------|---------|---------|
> |Déployer des plans d’appels dans les succursales européennes avant la fin de l’exercice 2018|FY18Q3 : déploiement de plans d’appels au bureau de Londres|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désaffecter l’ancien PBX au bureau de Londres avant la fin de l’exercice 2018|Pour 18Q4 : désaffecter l’ancien PBX dans le bureau de Londres|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|
> 
> [!TIP]
> Des exemples d’ok pertinents pour une implémentation de routage direct sont référencés ci-dessous :
> <br>
> 
> **Vision : augmentez la productivité en maximisant les Microsoft 365 ou Office 365 investissement**
> 
> |Objectifs  |Résultats clés  |À faire  |
> |---------|---------|---------|
> |Déployer le routage direct dans les succursales du Canada d’ici la fin de l’exercice 2018|Pour 18Q3 : déploiement du routage direct au bureau de Toronto|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désaffecter l’ancien PBX au bureau de Toronto à la fin de l’exercice 2018|Pour 18Q4 : désaffecter l’ancien PBX au bureau de Toronto|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

<br>

Les KSI mesurent la qualité et le succès des résultats clés et complètent la nature binaire des ok (atteints ou non) en détaillant les résultats positifs et/ou mauvais.

Lorsque vous définissez des indicateurs de performance clés, nous vous recommandons d’utiliser des critères SMART (« spécifiques, mesurables, assignables, réalistes, liés à l’heure » :

-   Spécifique : cibler une zone spécifique pour l’amélioration

-   Mesurables : quantifiables ou suggèrent au moins un indicateur de progression

-   Assignable : spécifier qui doit le faire

-   Réaliste : indiquez les résultats qui peuvent être obtenus de manière réaliste, à partir des ressources disponibles

-   En relation avec l’heure : spécifier le moment où les résultats peuvent être obtenus

> [!TIP]
> Voici un exemple d'indicateur de succès clé approprié à ce projet :
> 
> |Type  |Questions sur l'indicateur de succès clé et critères  |Comment les mesurer  |Critères de réussite  |Mesurés  |Responsable  |
> |---------|---------|---------|---------|---------|---------|
> |Utilisation/adoption|La qualité des appels est égale ou meilleure qu’avec la solution précédente|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable des technologies de l’information|
> |Utilisation/adoption|Microsoft Teams a facilité le processus de communication|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
> |Utilisation/adoption|Les utilisateurs utilisent activement la solution|Microsoft 365 rapports de qualité des appels, tableau de bord de qualité des appels|80 % des utilisateurs l’utilisent quotidiennement|Chaque jour|Équipe responsable de la gestion des changements|
> |Utilisation/qualité|Le pourcentage d’appels/conférences médiocres doit être minimal|Tableau de bord de la qualité des appels|< 5 % d'appels médiocres par mois|Chaque jour|Équipe responsable des technologies de l’information|
> |Utilisation/support|Je sais comment obtenir le support technique|Enquête|90% des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
> |Utilisation/support|Je suis satisfait de la qualité du support technique|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après chaque incident|Équipe responsable des technologies de l’information|
> |Financier|Réduction du nombre de minutes de conférence héritée|Système financier|Atteindre le retour sur investissement défini|Basé sur le retour sur investissement|Équipe responsable de la gestion des changements|

Vous devez identifier les risques pour les entreprises dans le cadre de cet exercice et définir un plan d’atténuation pour chaque risque identifié. Ces informations peuvent être capturées dans un registre des risques.

> [!TIP]
> Votre registre des risques peut être consigné dans l’exemple ci-dessous :
> 
> |Risque  |Probabilité  |Impact  |Global  |Plan d’atténuation  |
> |---------|---------|---------|---------|---------|
> |Une fusion prochaine ajoutera jusqu’à 1000 personnes|Élevée|Haut|Haut|<ul><li>Pour les entreprises fusionnées, créez un okR distinct qui s’applique à leurs propres phases de projet (conception, intégration, valeur de lecteur)</li><li>N’incluez pas ces OKR dans les OKR existants</li></ul>|
> |Le transfert des numéros de téléphone retardera la réalisation du projet|Élevée|Haut|Haut|<ul><li>Préparer toutes les informations requises pour prendre en charge le portage de numéro de téléphone à l’avance (enregistrement du service client, détails de facturation, lettre d’autorisation)</li><li>Ajuster la chronologie du projet pour tenir compte du délai d’exécution du portage des numéros de téléphone</li><li>Communiquer l’utilisation de nouveaux numéros de conférence rendez-vous aux participants externes</li><li>Utilisation de numéros de téléphone temporaires avec manipulation d’ID d’appelant</li></ul>|
> |Reconception du réseau planifiée|Élevée|Moyen|Moyen|<ul><li>Avant d’implémenter Teams comme plateforme de communication et de collaboration moderne, effectuez une évaluation de la disponibilité du réseau pour les sites dans l’étendue du projet.</li></ul>|
> |Configuration SBC|Haut|Haut|Haut|<ul><li>Avant d’implémenter Teams remplacement du PBX existant, confirmez que vous pouvez répondre à toutes les exigences de configuration SBC.</li><li>Vérifier que les ressources de support SBC disposent des compétences appropriées pour configurer SBC pour le routage direct</li></ul>|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Points de décision|<ul><li>Quelles sont les&#39;et les KSI de votre organisation ?</li><li>Quels risques avez-vous identifiés en rapport avec l’implémentation de l’audioconférence dans votre organisation ? Quels sont les plans d’atténuation pour les risques identifiés ?</li><li>Quels risques avez-vous identifiés en rapport avec l’implémentation des plans d’appel dans votre organisation ? Quels sont les plans d’atténuation pour les risques identifiés ?</li><li>Quels risques avez-vous identifiés en relation avec l’implémentation du routage direct dans votre organisation ? Quels sont les plans d’atténuation pour les risques identifiés ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documenter les OKR et les KSI, et établir le registre des risques.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Créer un comité directeur

Un comité directeur est un groupe régissant les principales parties prenantes et les chefs de projet qui ont été rassemblés pour guider un projet ou un programme vers les résultats d’entreprise définis. Le comité directeur n’est  pas directement responsable de la  livraison du projet, mais plutôt de ses résultats.

Chaque projet nécessite une vision et une charte d’accord. Pour offrir les résultats escomptés pour le projet, la vision doit être clairement définie, et elle doit être contrôlée et maintenue. Cela devient la responsabilité du comité directeur : conduire des décisions, conseiller, fournir une surveillance stratégique, faire office d’intervenants pour l’organisation pour les initiatives du projet et, si nécessaire, supprimer des bloqueurs.

Votre organisation doit réfléchir de façon significative à la formation du comité directeur. Le comité doit s’assurer que le projet atteint les objectifs d’entreprise que vous avez définis pour l’conduite des changements dans l’organisation, se réunir régulièrement pour discuter du pulse actuel du projet et aider à débloquer les obstacles rencontrés en cours de route.

Le comité doit définir sa charte de manière à inclure certains objectifs clés :

-   Garder un alignement fort entre l’équipe de projet et le sponsor exécutif ou les cadres dirigeants.

-   Fournir des informations sur l’état du projet au sponsor exécutif ou aux cadres dirigeants.

-   Autorisez le sponsor exécutif ou l’équipe de direction à fournir l’orientation et la contribution au projet et à s’assurer qu’il s’aligne sur les objectifs généraux de l’entreprise, en ajustant les plans de projet, les résultats clés d’objectif (OKR) et d’autres activités de projet.

Le comité directeur se réunit à intervalles périodiques pendant toute la durée de vie d’un projet afin de s’assurer de l’alignement entre les dirigeants de l’organisation et l’équipe de projet. Cette réunion critique garantit que l’orientation du projet a le soutien total des dirigeants et intègre les commentaires fournis par les dirigeants dans le projet pour être efficace. Le comité utilise ces réunions pour obtenir des informations sur l’état du projet et :

-   Conviennez de résultats d’entreprise alignés sur l’étude de cas et pour vous assurer que le projet est en cours d’exécution.

-   Vérifiez et approuvez le projet pour plus de précision et de conformité avec l’étude de cas.

-   Examinez et vérifiez les modifications apportées à la étude de cas qui peuvent affecter les résultats définis.

-   Prendre des décisions stratégiques en matière de hiérérisation des livrables du projet et approuver des livrables temporaires.

-   Identifiez, gérez et atténuez les lacunes, les risques et les problèmes pour lequel une influence supplémentaire est requise de la part du comité.

-   Rassemblez l’assistance du sponsor exécutif ou de l’équipe de direction pour les problèmes qui nécessitent une escalade, la hiérérisation et la résolution des conflits entre les unités commerciales des parties prenantes. 

-   Fournir des commentaires formels et des recommandations aux cadres dirigeants, au tableau de bord sur le changement ou aux autres parties prenantes au domaine de l’information et de l’entreprise, le cas échéant.

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Points de décision|<ul><li>Décidez si un comité directeur est nécessaire pour votre organisation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Identifiez les membres du comité directeur.</li><li>Planifier des réunions du comité d’équipe.</li><li>Préparez les réunions du comité directeur.</li><li>Organisez des réunions de comité spécial.</li><li>Prendre des mesures sur la base des commentaires du comité exécutif.</li></ul>|

Vous pouvez obtenir des instructions détaillées supplémentaires sur la manière de mettre en place un comité complémentaire approprié dans le guide du [comité directeur.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->
