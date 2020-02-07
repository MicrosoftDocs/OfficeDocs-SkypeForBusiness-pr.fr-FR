---
title: 'Définir le succès de conférence Audio, Système téléphonique avec forfait d’appel, ou Système téléphonique avec routage direct : Microsoft Teams'
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Évaluez les résultats de votre audioconférence, de votre système téléphonique grâce aux plans d’appel ou du déploiement du routage direct du système téléphonique, et vérifiez que vous avez bien obtenu les résultats souhaités.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3669e904db7dbea805daa5737b0bfb81e931d7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825422"
---
# <a name="define-my-success"></a>Définir ma réussite

Cet article fournit une vue d’ensemble des exigences relatives à la définition du succès pour le déploiement de l’audioconférence, du système téléphonique avec les plans d’appel ou du routage direct du système téléphonique pour votre organisation. En définissant correctement le résultat, vous pouvez mesurer les résultats à mesure que vous progressez dans le cadre de votre déploiement et vérifier que vous avez obtenu les résultats que vous souhaitez.

<!--ENDOFSECTION-->

**Audioconférence** fournit aux organisations des points d’entrée supplémentaires pour toutes les réunions (ad hoc ou programmées) en permettant aux participants d’une réunion de se connecter via un réseau téléphonique commuté (PSTN) en composant un numéro de téléphone fixe ou mobile. Cette fonctionnalité est utile lorsque l’organisateur ou les participants ne se trouvent pas devant un ordinateur, ou lorsque les connexions de données sont indisponibles ou trop fiables pour prendre en charge les communications vocales (par exemple, dans une zone distante avec la protection des données mobiles, ou qui est connectée à un réseau Wi-Fi gratuit et public). service avec une bande passante limitée ou lorsque les participants à la réunion préfèrent se connecter à la réunion via un point de terminaison de téléphonie qui est facilement accessible.

Le **système téléphonique avec des plans d’appels (« plans d’appel »)** donne aux organisations une façon de moderniser leur lieu de travail en permettant aux utilisateurs de passer des appels téléphoniques professionnels depuis leurs ordinateurs et leurs appareils mobiles. La modernisation de l’espace de travail peut faire partie d’un certain nombre de scénarios : une implémentation de travail basée sur une activité, un déplacement de bureau principal, une actualisation de la déconnexion d’Office, la suppression d’une solution PBX héritée, la conclusion d’un contrat de prestataire de services RTC, etc. Avec les offres d’appels, Microsoft facilite la connexion au RTC.

Le **routage direct du système téléphonique (« routage directe »)** donne aux organisations les mêmes avantages que ceux indiqués ci-dessus pour les offres d’appels, sauf que la connectivité PSTN est facilitée par un fournisseur tiers plutôt que Microsoft. Cela permet le déploiement dans des pays où les plans d’appel ne sont pas disponibles, ou dans les déploiements où un contrat de prestataire de services RTC existant doit être maintenu ou l’interopérabilité avec certains systèmes locaux est requis. Un scénario supplémentaire pour considérer le routage direct est l’interopérabilité du système de téléphonie. Lorsque les utilisateurs sont en transition pour appeler dans Teams, certains utilisateurs peuvent rester sur des PBX anciens. Le routage direct permet à la fois de cohabiter des cas d’utilisation. Le trafic des appels entre les utilisateurs sur les systèmes et équipes héritées qui restent au sein de l’organisation.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Définir des cas d’utilisation professionnelle pour les conférences audio, les plans d’appel ou le routage direct

Pour commencer, les parties prenantes de Project doivent définir des cas d’utilisation d’entreprise qui prennent en charge l’implémentation des conférences audio, des plans d’appel ou du routage direct.

Les cas d’utilisation pour les entreprises sont destinés à définir et à documenter les résultats professionnels attendus et mesurables, et notamment :

-   Description du processus professionnel actuel

-   Défis liés au processus professionnel existant

-   Comment la technologie peut aider à surmonter ces difficultés

-   Les résultats pour l'entreprise attendus et mesurables si ces difficultés sont surmontées.

> [!TIP]
> Voici un exemple de cas d’utilisation professionnelle à l’aide de l’audioconférence :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>Contoso fait actuellement appel à des services de conférence PSTN fournis par le fournisseur de téléphonie local titulaire facturés par minutes de réunion pour les réunions internes et celles impliquant des parties externes.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>Contoso passe environ USD1 millions par an au service de conférence RTC actuel et 75% du coût encouru pour les réunions internes. L’utilisation de points de terminaison de téléphonie traditionnels pour participer aux réunions hébergées par le service de conférence RTC n’est pas alignée sur le plan de l’organisation afin d’adopter les équipes comme plate-forme de communication et de collaboration modernes.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Lorsque Microsoft teams est adopté en tant que plateforme de communication et de collaboration moderne, les utilisateurs internes sont censés participer essentiellement à des réunions à l’aide de leurs PC équipés de casques optimisés et d’appareils de salle de réunion. Le service d’audioconférence sera disponible pour prendre en charge les participants externes ou les situations dans lesquelles l’utilisation de l’audio du PC n’est pas favorable pour les participants internes.|
> |**Résultats de l’entreprise attendus et mesurables**<br>Le passage aux équipes en tant que plateforme de communication et de collaboration modernes, combinée au service d’audioconférence, réduit considérablement le coût de remise du service de conférence PSTN.|

<br>

> [!TIP]
> Voici un exemple de cas d’utilisation professionnelle complet pour les offres d’appels.
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>La configuration standard des espaces de travail Office de contoso inclut un téléphone de bureau pour chaque bureau. Chaque employé dispose d’un numéro de téléphone (DID) direct. Les téléphones de bureau sont connectés à un système PBX et connectés au RTC via un Trunk SIP (Session Initiation Protocol). Les employés peuvent uniquement émettre et recevoir des appels téléphoniques sur leur téléphone de bureau.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>L’analyse de l’utilisation des téléphones de bureau montre que seules 10% des téléphones de bureau sont activement utilisées, avec le reste configuré pour transférer les appels vers des téléphones mobiles ou pour sonner simultanément sur des téléphones mobiles. Le maintien du système PBX actuel et des téléphones de bureau associés contribue à 20% du coût de service de téléphonie mensuelle de contoso.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Les plans d’appels permettent à l’ordinateur personnel d’un utilisateur de recevoir des appels téléphoniques sur le réseau de données en tirant parti de l’application Microsoft teams native. Cela évite de déployer et de mettre à jour les téléphones de bureau, et ouvre la possibilité de mettre en réseau le système PBX existant, car le service téléphonique peut être acheminé via le Cloud sur le réseau sans dépendance sur un système téléphonique traditionnel.|
> |**Résultats de l’entreprise attendus et mesurables**<br>Le retrait des exigences de maintenance ou la désactivation de la version PBX et des téléphones de bureau prérequis entraînent une réduction de 20% sur les dépenses de service de téléphonie mensuelles. Les plans d’appel simplifient la gestion des espaces de travail Office, ce qui permet à contoso d’étendre ses opérations en définissant de nouveaux bureaux avec un minimum de coûts de téléphonie.|

<br>

> [!TIP]
> Voici un exemple de cas d’utilisation professionnelle complet pour le routage directe :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>La configuration standard des espaces de travail Office de contoso inclut un téléphone de bureau pour chaque bureau. Chaque employé dispose d’un numéro de téléphone (DID) direct. Les téléphones de bureau sont connectés à un système PBX et connectés au RTC via un Trunk SIP (Session Initiation Protocol). Les employés peuvent uniquement émettre et recevoir des appels téléphoniques sur leur téléphone de bureau.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>L’analyse de l’utilisation des téléphones de bureau montre que seules 10% des téléphones de bureau sont activement utilisées, avec le reste configuré pour transférer les appels vers des téléphones mobiles ou pour sonner simultanément sur des téléphones mobiles. Le maintien du système PBX actuel et des téléphones de bureau associés contribue à 20% du coût de service de téléphonie mensuelle de contoso.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Le contrat du fournisseur de Trunk SIP a été récemment signé et est en place pour trois ans. Le routage direct permet de fournir une connectivité PSTN par le fournisseur SIP Trunk et permettra également à l’ordinateur personnel d’un utilisateur de recevoir des appels téléphoniques sur le réseau de données en tirant parti de l’application Microsoft teams native. Cela évite de déployer et de mettre à jour les téléphones de bureau, et ouvre la possibilité de mettre en place le système PBX existant, tout en conservant un encombrement de contrôleur de la session d’SBC local limité.|
> |**Résultats de l’entreprise attendus et mesurables**<br>Le retrait des exigences de maintenance ou la désactivation de la version PBX et des téléphones de bureau prérequis entraînent une réduction de 20% sur les dépenses de service de téléphonie mensuelles. Le routage direct simplifie les espaces de travail Office, ce qui permet à contoso d’étendre ses opérations en définissant de nouveaux bureaux avec un minimum de coûts de téléphonie.|

Outre la définition des cas d’utilisation de votre entreprise, vous devez définir les limites du projet pour favoriser la clarté :

-   **Étendue de l’Organisation :** L’implémentation de l’audioconférence, des plans d’appel ou du routage direct peut englober l’ensemble de votre organisation ou uniquement des unités commerciales spécifiques.

-   **Barre de planning du projet :** La chronologie spécifique que le projet doit exécuter.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Points de décision|<ul><li>Quels sont les scénarios d’utilisation pour les entreprises que vous pouvez identifier au sein de votre organisation ?</li><li>Quels sont les cas d’utilisation pour les entreprises d’appels que vous pouvez identifier au sein de votre organisation ?</li><li>Quels sont les cas d’utilisation pour le routage direct qui peuvent être identifiés au sein de votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documentez tous les cas d’utilisation pour les entreprises pour votre organisation.</li><li>Documentez tous les cas d’utilisation pour les entreprises pour les offres d’appels de votre organisation.</li><li>Documentez tous les cas d’utilisation pour le routage direct de votre organisation.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identifier les parties prenantes clés

Les cas d’utilisation pour les entreprises définis à l’étape précédente incluent une étendue de l’organisation de l’implémentation de l’audioconférence, des plans d’appel ou du routage direct. En fonction de cela, vous pouvez effectuer la matrice complète des parties prenantes pour inclure les personnes appropriées dans le projet.

> [!TIP]
> Voici un exemple de modèle de matrice des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes intégrées dans le projet :
> 
> |Rôle  |Description  |Nom, informations de contact, emplacement  |
> |---------|---------|---------|
> |Sponsor exécutif du projet|<ul><li>Prenez les responsabilités et la responsabilité ultimes du projet et de la livraison sur les objectifs du projet.</li><li>Aidez-vous à résoudre les problèmes escaladés par le responsable de projet.</li><li>Communication du sponsor au sein de l’entreprise concernant les objectifs du projet.</li><li>Prenez les principales décisions stratégiques.</li><li>Garantir la disponibilité des ressources et du budget requis ;</li><li>Retrouvez des avis trimestriels pour les entreprises (QBRs).</li><li>Acheter du lecteur et soutenir les efforts des campagnes de sensibilisation.</li><li>Faire office de sponsor du projet pour le lancement du programme.</li></ul>|TBA|
> |Chef de projet|<ul><li>Gérer et diriger l’équipe du projet.</li><li>Coordonnées des partenaires et équipes travaillant dans le projet.</li><li>Soyez responsable de la création et de la gestion des plans de projet pour les résultats de clés trimestrielles.</li><li>Résoudre les problèmes liés aux fonctions transversales.</li><li>Fournir des mises à jour régulières aux sponsors de Project.</li><li>Intégrez des aspects adoptés au plan de projet tout-en-un.</li><li>Envoiez les revues mensuelles et les avis opérationnels (MBRs), et contribuez à QBRs.</li></ul>|TBA|
> |Chef/architecte de la collaboration|<ul><li>Exécution sur la stratégie de collaboration définie par les dirigeants de l’entreprise.</li><li>Analysez et sélectionnez des produits de collaboration qui répondent aux objectifs de l’entreprise.</li><li>Opérations de conception pour les produits de collaboration.</li><li>Définir des modèles de fonctionnement et de support.</li><li>Contribuez aux révisions mensuelles et trimestrielles de l’entreprise.</li></ul>|TBA|
> |Consultant|<ul><li>Être responsable de la configuration des services</li><li>Contribuez à l’architecture globale de la solution.</li></ul>|TBA|
> |Gestionnaire de projets|<ul><li>Développement et mise à jour du plan de projet.</li><li>Gérer les livrables du projet en fonction du plan de projet et du budget.</li><li>Enregistrez et gérez les problèmes du projet, y compris les escalades.</li><li>Organisez des appels standup hebdomadaires.</li><li>Mettre en personne et fournir des mises à jour aux sponsors de Project Executive.</li><li>Travaillez avec l’architecte pour définir l’approche de gestion des modifications et les plans de communication.</li></ul>|TBA|
> |Spécialiste en gestion des changements/adoption|<ul><li>Fournir une entrée lors de la phase de découverte aux processus d’adoption et de formation.</li><li>Participez à l’atelier de stratégie adoption.</li><li>Développer et assumer la responsabilité de la stratégie d’adoption.</li><li>Développement et exécution du plan de communication.</li><li>Offrez des formations aux utilisateurs.</li><li>Recueillir des commentaires et conduire des enquêtes.</li></ul>|TBA|
> |Directeur de réseau|<ul><li>Fournir une entrée lors de la phase de découverte à la conception du réseau.</li><li>Participez à la planification pendant l’atelier de phase enVision.</li><li>Coordonner le travail de l’équipe du réseau lors de l’exécution du projet.</li></ul>|TBA|
> |Directeur de la sécurité|<ul><li>Fournir une entrée lors de la phase de découverte à la conception et aux processus de sécurité.</li><li>Participez à la planification pendant l’atelier de phase enVision.</li><li>Coordonner le travail de l’équipe de sécurité lors de l’exécution du projet.</li></ul>|TBA|
> |Directeur de la téléphonie|<ul><li>Fournissez une entrée lors de la phase de découverte au mode de téléphonie.</li><li>Participez à la planification pendant l’atelier de phase enVision.</li><li>Coordonner le travail de l’équipe de téléphonie lors de l’exécution du projet ;</li></ul>|TBA|
> |Directeur de bureau|<ul><li>Fournissez une entrée lors de la phase de découverte aux clients et au processus de mise à jour.</li><li>Participez à la planification pendant l’atelier de enVision.</li><li>Coordonner le travail de l’équipe de bureau lors de l’exécution du projet ;</li></ul>|TBA|
> |Responsable du support|<ul><li>Fournissez une entrée lors de la phase de découverte aux modèles opérationnels et de support.</li><li>Participez à la planification pendant l’atelier de phase enVision.</li><li>Participez à la planification du modèle de support.</li><li>Coordonner le fonctionnement des équipes et des ressources de support lors de l’exécution du projet.</li></ul>|TBA|
> |Représentants d'unité commerciale|<ul><li>Contribuez aux guides d’adoption d’utilisateurs et aux matériaux.</li><li>Contribuez aux cas d’utilisation professionnelle et passez en revue.</li></ul>|TBA|
> |Directeur du déploiement|<ul><li>Assurez-vous que les conditions préalables de déploiement sont remplies.</li><li>Engagez des ressources interintervenantes dans les activités de phases intégrées.</li><li>Participez à des réunions pour revoir et préparer des rapports sur l’état du déploiement.</li></ul>|TBA|
> |Administrateurs informatiques|<ul><li>Assistez à la planification et à l’exécution des tests. Ce rôle est destiné aux professionnels de l’informatique.</li></ul>|TBA|
> |Propriétaire de service|<ul><li>Prendre en charge le fonctionnement des services d’audioconférence, des plans d’appel ou du service de routage direct.</li><li>Possèdent les services d’audioconférence, d’appel ou de routage direct.</li></ul>|TBA|
> |Ambassadeurs de la qualité|<ul><li>La qualité des disques, la fiabilité et les commentaires des utilisateurs.</li><li>Identifiez les tendances en matière de qualité et pilotez la correction avec les équipes respectives.</li><li>Faire remonter le Comité de direction vers le leadership.</li><li>Rendez compte de la qualité, de la fiabilité et du sentiment des utilisateurs par le biais de l’évaluation du montant de votre appel et de votre promoteur.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Points de décision|<ul><li>Qui remplira chaque rôle d’intervenant clé de votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documentez toutes les principales parties prenantes et communiquez les responsabilités et les attentes du rôle à chaque individu affecté.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Définir des OKRs, des KSIs et des risques

Les parties prenantes du projet étant assemblées, vous pouvez traduire des cas d’utilisation professionnelle, l’étendue de l’organisation et les plannings de projet en objectifs et résultats clés (OKRs), et les mesures de réussite du projet peuvent être définies en tant que liste des indicateurs de réussite clés (KSIs).

La participation complète des parties prenantes au projet lors de la définition de OKRs et KSIs est essentielle pour s’assurer qu’elle a un sens de propriété et qu’elle aligne ces mesures de réussite pour les besoins de l’organisation.

OKRs contient les objectifs que vous avez définis au début du projet et vous définissez les résultats de clés mesurables sur une base trimestrielle. Vous pouvez réviser les résultats clés tous les mois pour suivre l’état du projet global et, en fonction de la progression, vous pouvez ajuster les offres trimestrielles selon vos besoins.

> [!TIP]
> Vous trouverez ci-dessous des exemples de OKRs pertinents pour une implémentation de conférences audio :
> <br>
> 
> **Vision : augmenter la productivité an optimisant les investissements dans Office 365**
> 
> |Objectifs  |Résultats clés  |À faire  |
> |---------|---------|---------|
> |Déployer l’audioconférence dans Teams d’ici la fin de l’exercice fiscal 2018|T1 de l’exercice 2018 : déployer l’audioconférence dans Teams globalement|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désactiver l’ancien service de conférence PSTN à l’échelle globale d'ici la fin de l’exercice fiscal 2018|T2 de l’exercice 2018 : désactiver l’ancien service de conférence PSTN à l’échelle globale|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

<br>

> [!TIP]
> Vous trouverez ci-dessous des exemples de OKRs pertinents pour une implémentation de plans d’appel :
> <br>
> 
> **Vision : augmenter la productivité an optimisant les investissements dans Office 365**
> 
> |Objectifs  |Résultats clés  |À faire  |
> |---------|---------|---------|
> |Déploiement de forfaits d’appels dans les bureaux de succursales européens à la fin de l’exercice 2018|FY18Q3 : déploiement d’offres d’appels dans le Bureau de Londres|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désaffecter le PBX hérité dans le Bureau de Londres à la fin de l’exercice 2018|FY18Q4 : le PBX hérité de Londres dans le Bureau de Londres|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|
> 
> [!TIP]
> Vous trouverez ci-dessous des exemples de OKRs pertinents pour une implémentation de routage direct :
> <br>
> 
> **Vision : augmenter la productivité an optimisant les investissements dans Office 365**
> 
> |Objectifs  |Résultats clés  |À faire  |
> |---------|---------|---------|
> |Déployer le routage direct dans les agences canadiennes en fin d’exercice 2018|FY18Q3 : déployer le routage direct dans le Bureau de Toronto|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désaffecter le PBX hérité de la fin de l’année 2018 au bureau de Toronto|FY18Q4 : la mise hors service de PBX vers l’ancien bureau|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

<br>

KSIs Mesurez la qualité et la réussite des principales valeurs et complétez la nature binaire de OKRs (atteint ou inatteint) en détaillant les résultats appropriés et/ou incorrects.

Lors de la définition de KSIs, nous vous recommandons d’utiliser les critères « spécifiques, mesurables, assignable et réaliste » (dynamique) :

-   Spécifique : cibler une zone spécifique à des fins d’amélioration

-   Mesurables : quantification ou au moins une suggestion d’indicateur de la progression

-   Assignable : spécifier les destinataires du programme

-   Réalisme : indiquez les résultats qui peuvent être atteints de manière réaliste, en fonction des ressources disponibles.

-   Durée : spécifier à quel moment les résultats peuvent être atteints

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

Vous devez identifier les risques commerciaux dans le cadre de cet exercice et définir un plan d’atténuation pour chaque risque identifié. Ces informations peuvent être capturées dans un registre de risques.

> [!TIP]
> Votre registre de risques peut être documenté comme suit :
> 
> |Risque  |Probabilité  |Impact  |Global  |Plan d’atténuation  |
> |---------|---------|---------|---------|---------|
> |Une fusion prochaine ajoutera jusqu’à 1000 personnes|Haut|Haut|Haut|<ul><li>Pour les sociétés fusionnées, créez un OKR distinct qui s’applique à leurs propres phases de projet (enVision, OnBoard, valeur du lecteur).</li><li>N’incluez pas ces OKRs dans OKRs existants</li></ul>|
> |Le transfert des numéros de téléphone retardera la réalisation du projet|Haut|Haut|Haut|<ul><li>Préparer toutes les informations nécessaires à la prise en charge du Portage du numéro de téléphone à l’avance (enregistrement du service clientèle, détails de facturation, lettre d’autorisation)</li><li>Ajuster la chronologie du projet pour l’adapter au délai d’exécution du Portage du numéro de téléphone</li><li>Communiquer l’utilisation de nouveaux numéros de conférence rendez-vous aux participants externes</li><li>Utiliser des numéros de téléphone temporaires avec la manipulation d’identification de l’appelant</li></ul>|
> |Reconception du réseau planifiée|Élevée|Moyen|Moyen|<ul><li>Avant d’implémenter les équipes en tant que plateforme de communication et de collaboration moderne, effectuez une analyse de la disponibilité du réseau pour les sites dans le cadre du projet.</li></ul>|
> |Configuration de SBC|Haut|Haut|Haut|<ul><li>Avant d’implémenter les équipes en tant que remplacement pour le PBX existant, assurez-vous que vous pouvez respecter toutes les exigences de configuration de SBC</li><li>Vérifiez que les ressources du support technique SBC disposent de l’ensemble des compétences nécessaires pour configurer SBC pour le routage direct.</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Points de décision|<ul><li>Qu’est-ce que votre organisation&#39;s OKRs et KSIs ?</li><li>Quels risques avez-vous identifiés dans le cadre de l’implémentation de l’audioconférence au sein de votre organisation ? Quels sont les plans d’atténuation pour les risques identifiés ?</li><li>Quels risques avez-vous identifiés dans le cadre de l’implémentation de plans d’appel au sein de votre organisation ? Quels sont les plans d’atténuation pour les risques identifiés ?</li><li>Quels risques avez-vous identifiés dans le cadre de l’implémentation du routage direct au sein de votre organisation ? Quels sont les plans d’atténuation pour les risques identifiés ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Documentez le OKRs et KSIs, puis établissez le registre de risques.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Créer un Comité de direction

Le Comité de direction est un groupe directeur d’acteurs clés et de chefs de projet qui ont été réunis pour diriger un projet ou un programme vers les résultats d’entreprise définis. Le Comité de direction n’est pas directement responsable du fonctionnement du projet, mais *plutôt du* *mode* de livraison du projet à l’entreprise.

Chaque projet nécessite une vision et une Charte de niveau convenu. Pour vous fournir les résultats que vous souhaitez du projet, la vision doit être clairement définie et doit être surveillée et entretenue. C’est la responsabilité du Comité de direction : de prendre des décisions, de conseiller, de soumettre un contrôle stratégique, de faire de la part des partisans de l’Organisation des initiatives du projet et, si nécessaire, de supprimer les bloqueurs.

Il est important de réfléchir à la formation de votre organisation. Le Comité doit veiller à ce que le projet soit conforme aux objectifs de l’entreprise que vous avez définis pour le changement de conduite au sein de l’organisation, à des réunions périodiques pour discuter de l’impulsion actuelle du projet et à débloquer tout obstacle rencontré sur le permettent.

Le Comité devrait définir son Charte pour inclure certains objectifs clés :

-   Restez en contact avec les membres de l’équipe de projet et du cadre de la direction.

-   Donnez un aperçu de l’état du projet au commanditaire ou au leadership de la direction.

-   Permettre au commanditaire ou à l’équipe de direction de la direction de fournir une direction et une entrée au projet et de s’assurer qu’il est conforme aux objectifs d’entreprise surajustables, en ajustant les plans de projet, les résultats clés d’objectif (OKRs) et d’autres activités de projet.

Le Comité de direction se réunit à un intervalle récurrent tout au long de la durée de vie d’un projet pour garantir l’alignement entre le leadership de l’organisation et l’équipe du projet. Cette réunion critique vérifie que la direction du projet dispose d’une prise en charge complète du leadership et qu’elle intègre tout avis fourni par leadership dans le projet pour favoriser le succès. Le Comité utilise ces réunions pour vous familiariser avec l’état du projet et pour :

-   S’engagent sur les résultats de l’entreprise qui sont alignés sur le scénario commercial et de sorte que le projet s’engage à livrer ces résultats.

-   Vérifiez et approuvez le projet pour vérifier sa précision et sa conformité avec le cas commercial.

-   Examiner et vérifier les modifications apportées au cas professionnel qui pourraient affecter les résultats définis.

-   Prenez des décisions stratégiques concernant la hiérarchisation des livrables du projet et approuvez les livrables intermédiaires.

-   Identifier, gérer et limiter les lacunes, les risques et les problèmes pour lesquels une influence supplémentaire est requise du Comité.

-   Rassemblez le support technique du commanditaire ou de l’équipe responsable de la direction pour les problèmes nécessitant une remontée, le classement par priorité et la résolution des conflits entre les unités d’entreprise parties prenantes. 

-   Fournir des commentaires formels et des recommandations au leadership de la direction, au Conseil consultatif ou aux autres parties prenantes, le cas échéant.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Points de décision|<ul><li>Décider s’il est nécessaire de disposer d’un Comité de direction pour votre organisation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Étapes suivantes|<ul><li>Identifier les membres du Comité directeur.</li><li>Planifier des réunions de Comité de direction.</li><li>Préparez-vous à la réunion de la direction.</li><li>Mettre en attente des réunions du Comité d’orientation.</li><li>Agir en fonction de l’entrée de la réunion du Comité d’orientation.</li></ul>|

Vous trouverez des instructions détaillées supplémentaires sur la façon d’utiliser un Comité d’orientation approprié dans le [Guide du Comité d’orientation](envision-steering-committee-complete-guide.md).

<!--ENDOFSECTION-->