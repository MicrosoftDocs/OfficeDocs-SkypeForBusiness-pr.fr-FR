---
title: Tableau de bord de qualité d’appel (bord) Forum aux questions (FAQ)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lisez le Forum aux questions et répondez aux questions sur le tableau de bord de qualité des appels de Microsoft Teams (bord).
ms.openlocfilehash: 43dd0f85c21914320ff48c2e0aab82614670ff90
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372123"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Tableau de bord de qualité d’appel (bord) Forum aux questions (FAQ)

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

[Pourquoi bord marque-t-on comme bon dans le cas d’un ou plusieurs participants à la réunion ?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Pourquoi est-ce que je reçois une différence de 0,2% sur les mesures et le nombre d’utilisateurs et la façon d’obtenir des volumes plus précis ?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Pourquoi les données bord de Skype entreprise sont-elles différentes de celles bord de teams ?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Pourquoi ne puis-je pas voir EUII dans bord ?](#why-cant-i-see-euii-in-cqd)

[Pourquoi des informations Skype entreprise s’afficheront dans bord lorsque j’ai filtré uniquement pour les équipes ?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Pourquoi bord marque-t-on comme bon dans le cas d’un ou plusieurs participants à la réunion ?

Découvrez les règles utilisées par bord pour la [classification des flux](stream-classification-in-call-quality-dashboard.md).
 
Dans le cas des flux audio, l’un des cinq classifieurs, qui est calculé pour la moyenne en fonction de la longueur de l’appel, peut être un paramètre « Good ». Cela ne signifie pas que les utilisateurs n’ont pas eu d’action ayant contribué à une chute ou un problème audio. 

Pour savoir s’il s’agit d’un problème de réseau, observez le delta entre les valeurs moyennes de la session et les valeurs maximales. Les valeurs maximales sont le maximum détecté et signalé lors de la session.
 
Voici un exemple de procédure à suivre pour résoudre ce problème. Imaginons que vous suiviez une trace réseau lors d’un appel et les 20 premières minutes qu’il n’y a pas de paquets perdus, mais que vous avez un espace de 1,5 secondes de paquets et que vous avez l’habitude de le reste de l’appel. La moyenne est <de 10% (0,1) de perte de paquets même dans une analyse RTP de suivi Wireshark. Quelle a été la perte de paquets maximale ? 1,5 secondes sur une période de 5 secondes seraient de 30% (0,3). A-t-il observé au cours de la période de cinq secondes (peut-être, ou peut-être fractionné au cours de la période d’échantillonnage) ?
 
Si les métriques du réseau s’importent correctement dans les valeurs moyenne et maximale, accédez à d’autres données de télémétrie : 
- Vérifiez le ratio d’événement d’UC insuffisant pour vérifier si les ressources de l’UC détectées disponibles étaient insuffisantes et ont une mauvaise qualité. 
- Le périphérique audio est-il en mode half duplex pour éviter les commentaires en raison de micros à proximité des haut-parleurs ? 
- Vérifiez le coefficient d’événement AEC en mode half duplex. Le périphérique est-il en faute d’introduction ou de problème de micro, en raison d’une chute USB ou d’une station d’accueil USB, s’il est connecté à un concentrateur ou une station d’ancrage :  
- Vérifiez les ratios d’événement liés aux problèmes liés aux périphériques et aux problèmes de micro. Est-ce que l’appareil proprement dit fonctionne correctement ?  
- Vérifiez que l’appareil de capture et de rendu ne fonctionne pas.


Pour en savoir plus sur les dimensions et les mesures disponibles dans la télémétrie bord, voir [dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md).

Pour bruit de fond, activez la case à cocher Désactiver le coefficient d’événement pour voir la durée pendant laquelle les participants ont été désactivés.
 
Créez des rapports détaillés dans bord et filtrez sur ID de réunion pour consulter tous les utilisateurs et les flux d’une réunion et ajouter les champs qui vous intéressent. Il est possible qu’un utilisateur signalant ce problème ne soit pas celui qui rencontre le problème. Ils signalent simplement l’utilisateur.
 
La télémétrie ne sera pas nécessairement à l’origine du problème, mais elle peut vous aider à mieux comprendre la façon dont vous pouvez trouver et informer vos décisions. S’agit-il des mises à jour du réseau, du périphérique, du pilote ou du microprogramme, de l’utilisation ou de l’utilisateur ?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Pourquoi est-ce que je reçois une différence de 0,2% sur les mesures et le nombre d’utilisateurs et la façon d’obtenir des volumes plus précis ? 
Pour calculer le nombre d’appels et les mesures de nombre d’utilisateurs, une opération NB.si distincte est effectuée par rapport aux identificateurs d’appel ou d’utilisateur du jeu de données. Dans le cas d’un grand nombre de jeux de données, une erreur de 0,2% est inhérente à l’opération NB.si distincte. Pour obtenir le volume le plus précis, vous devez vous fier aux mesures de nombre de flux, car elles ne dépendent pas de cette opération NB.si distincte. Le filtrage permettant de réduire le volume de données risque de réduire l’erreur, mais n’a pas pu éliminer cette source d’erreur dans les compteurs d’appels et d’utilisateurs distincts. Reportez-vous aux [sections Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md) pour lesquels des mesures sont affectées.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Pourquoi les données bord de Skype entreprise sont-elles différentes de celles bord de teams ? 


> [!IMPORTANT]
> À compter du 1er juillet, 2020, l’ancien bord (CQD.lync.com) utilise les données du dernier bord (bord. Teams.microsoft.com). Les données bord plus anciennes ne sont plus disponibles et vous ne pouvez pas exporter les données de votre bâtiment ou de votre rapport. Vous pouvez toujours utiliser CQD.lync.com (disponible dans le centre d’administration Skype entreprise), mais nous vous conseillons de désactiver l’accès à CQD.lync.com bientôt, donc vous devez accéder à bord. Teams.microsoft.com si vous ne l’avez pas déjà fait.


Si vous essayez de comparer des données entre l’ancien bord du portail hérité Skype entreprise (cqd.lync.com) et le dernier bord à partir du centre d’administration Teams (cqd.teams.microsoft.com), vous remarquerez rapidement que les données ne correspondent pas. Ce n’est pas parce que les derniers rapports bord sur de nombreux scénarios d’appels supplémentaires. Si vous utilisez toujours des rapports de l’ancien bord, utilisez cet article pour vous aider à interpréter ces rapports : [tableau de bord de qualité des appels pour Skype entreprise Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Pourquoi ne puis-je pas voir EUII dans bord ?

Ces rôles d’administrateur peuvent accéder à bord, mais ils ne peuvent pas afficher EUII (informations d’identification de l’utilisateur final) :
- Lecteur de rapports Microsoft 365
- Spécialiste du support des communications teams

Pour en savoir plus sur les rôles qui peuvent accéder à bord, y compris les [rôles d’attribution de EUII-lecture des rôles pour accéder à bord](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Pourquoi des informations Skype entreprise s’afficheront dans bord lorsque j’ai filtré uniquement pour les équipes ?

Lorsque vous filtrez les équipes uniquement dans les rapports bord (isTeams = 1), vous filtrez tous les appels dans lesquels le *premier point de terminaison* est Teams. Si le *deuxième point de terminaison* est Skype entreprise, ces informations apparaissent dans votre rapport bord.

CQDv2 et CQDv3 ont toujours un nombre total différent, car CQDv3 aura de nouveaux scénarios qu’CQDv2 n’aura pas. C’est pourquoi comparer le total de synthèse ou les nombres cumulés cumulés sans aucun filtre n’aura de différences attendues.  

En fonction du scénario des clients, CQDv3 inclut des appels locaux marketing 2019 (si marketing 2019 est utilisé avec un connecteur de données), des appels Skype bot (AA, CVI, VDI), des événements en direct et des appels PSTN. Scénarios et fonctionnalités disponibles pour les clients, mais leurs données ne sont pas dans bord v2.

Par exemple, il est probable que vos clients et vous verrez des flux audio 200 000, avec 5000 échecs dans le rapport de synthèse bord v2. différences entre les flux audio 300 000 et les échecs 5500 (provenant de 2019 appels locaux, d’appels CVI, d’appels RTC, etc.) dans bord v3.

Pour déterminer s’il existe des différences inattendues, vous devez examiner les différentes répartitions des données globales.  Comparer avec intention.  Le fait de découper les données par paire de catégorie de l’agent utilisateur est l’un des premiers points recommandés.  Le *premier produit* et le *second produit* sont également des segments appropriés.  


## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Qu’est-ce que bord ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Télécharger le client et générer des données](CQD-upload-tenant-building-data.md)

[Rapports et données bord](CQD-data-and-reports.md)

[Utiliser bord pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans bord](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)