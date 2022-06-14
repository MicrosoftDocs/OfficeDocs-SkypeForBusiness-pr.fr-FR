---
title: Utilisez Power BI pour analyser les données de CQD pour Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Utilisez Power BI pour analyser les données de CQD pour les Microsoft Teams.
ms.openlocfilehash: 7d951c0e96f98c343a388e536311bf00890e5302
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056954"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Utilisez Power BI pour analyser les données de CQD pour Microsoft Teams

Nouveauté de janvier 2020 : [Télécharger Power BI modèles de requête pour les](https://www.microsoft.com/download/details.aspx?id=102291)CQD . Modèles de Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données CQD.

Pour les rapports CQD (Call Quality Dashboard) dans Teams, si vous préférez utiliser Power BI pour interroger et signaler vos données, téléchargez nos modèles de Power BI CQD. Lorsque vous ouvrez les modèles dans Power BI, vous êtes invité à vous connecter avec vos informations d’identification d’administrateur CQD. Vous pouvez personnaliser ces modèles de requête et les distribuer à toute personne de votre organisation disposant d’une licence Power BI et d’autorisations d’administrateur CQD.

Avant de pouvoir utiliser ces fichiers PBIT, vous devez [installer le connecteur Power BI pour Microsoft CQD](CQD-Power-BI-connector.md) à l’aide du fichier *MicrosoftCallQuality.pqx* inclus dans le [téléchargement](https://www.microsoft.com/download/details.aspx?id=102291). 

Assurez-vous que vous disposez du [rôle d’accès CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) approprié pour accéder aux rapports Power BI. 

|Baii |Description |
|:----------|:---------|
|<strong>(Nouveau!)</strong> QER.pbit     |  Le modèle QER (Quality of Experience Report) permet aux clients d’identifier de manière proactive les problèmes qui ont un impact sur la réunion Teams et l’expérience d’appel avant qu’ils ne s’escaladent. Des rapports sont également fournis pour permettre aux administrateurs de répondre rapidement aux problèmes réaffectants et d’aider à répondre à la question « Qu’est-ce qui s’est passé pendant la réunion ? »  Ce modèle fournit les rapports suivants :</p><li>Recherche : permet la recherche par URL de réunion, ID de conférence, sous-réseau ou UPN.</li><li>Détails de l’intégrité de la réunion : métriques détaillées pour une réunion unique.</li><li>Détails de l’intégrité de l’utilisateur : métriques détaillées pour un seul utilisateur.</li><li>Intégrité des médias : vue d’ensemble générale des indicateurs d’intégrité clés (KHI) pour la réunion globale des locataires et l’intégrité des appels.</li><li>Configuration du média : analysez les échecs de configuration du média.</li><li>Fiabilité des médias : analysez les problèmes de fiabilité des supports.</li><li>Intégrité de l’audio/vidéo/partage : passez en revue les khis de niveau intermédiaire pour l’audio, la vidéo ou le partage d’intégrité.</li><li>Détails de l’intégrité audio/vidéo/partage : passez en revue les métriques détaillées sur l’audio, la vidéo ou le partage d’intégrité.</li><li>VPN : passez en revue l’impact du VPN sur l’intégrité de la réunion. (VPN estimé ou mappé)</li><li>10 principaux rapports : identifiez les zones problématiques dans votre locataire.</li><li>Quotidiens : passez en revue le rapport quotidien des khis.</li><li>Utilisation : utilisation des réunions générales et des appels.</li><li>Commentaires des utilisateurs : passez en revue les commentaires de l’enquête utilisateur, également appelés « Rate My Call ».</li><li>Transport : identifier les réseaux qui bloquent UDP.</li><li>Appareils : passez en revue l’impact des appareils.</li><li>Clients : passez en revue les métriques axées sur le client.</li><li>Génération de données : passez en revue le fichier de données de génération dans CQD.</li><li>Détails de l’intégrité et de l’utilisateur RTC : deux rapports qui fournissent un résumé de haut niveau ainsi que l’intégrité des utilisateurs individuels pour les appels rtc.</li><li>Métriques réseau : deux rapports qui affichent les détails bruts des métriques réseau pour la gigue, la perte de paquets et la latence.</li>  |
|CQD Teams standard automatique & rapport historique de file d’attente d’appels.pbit     |  Ce modèle fournit les trois rapports suivants :</p><li>Standard automatique : affichage de l’analytique des appels entrants dans vos standards automatiques.</li><li>File d’attente d’appels : analyse des appels entrant dans vos files d’attente d’appels.</li><li>Chronologie de l’agent : affichage de la chronologie des agents actifs dans les appels de file d’attente d’appels.</li><br>Pour en savoir plus, lisez [le standard automatique & rapport historique de file d’attente d’appels](aa-cq-cqd-historical-reports.md). |
|CQD Helpdesk Report.pbit     |Intégrant les données de génération et d’EUII, ce rapport est conçu pour vous permettre d’explorer à partir d’un seul utilisateur pour trouver la cause racine en amont de la mauvaise qualité des appels pour cet utilisateur (par exemple, l’utilisateur se trouve dans un bâtiment qui rencontre des problèmes réseau). |
|Emplacement CQD amélioré Report.pbit     | Re-imaginer les rapports d’emplacement spd CQD. Inclut 9 rapports, qui fournissent des informations sur la qualité des appels, le wi-fi, la fiabilité et le débit de mon appel (RMC) avec des explorations supplémentaires par bâtiment ou par utilisateur. Veillez à charger les données de génération pour optimiser votre expérience de création de rapports. |
|CQD Mobile Device Report.pbit     | Fournit des insights spécifiquement adaptés aux utilisateurs d’appareils mobiles, notamment la qualité des appels, la fiabilité et la fréquence de mon appel. Afficher les rapports sur le réseau mobile, le réseau Wi-Fi et le système d’exploitation mobile (Android, iOS). |
|CQD PSTN Direct Routing Report.pbit     |Fournit des insights spécifiques pour les appels RTC qui passent par le routage direct. Pour plus d’informations, consultez [Utilisation du rapport de routage direct rtc CQD](CQD-PSTN-report.md). |
|Résumé du CQD Report.pbit     |De meilleures visualisations, une présentation améliorée, une densité d’informations accrue et des dates propagées. Ces rapports facilitent l’identification des valeurs hors norme. Explorez la qualité des appels par emplacement avec une carte interactive facile à utiliser. Neuf nouveaux rapports :</p>- Qualité globale<br>- Fiabilité globale<br>- RMC (Rate My Call) Global<br>- Qualité des conférences<br>- Qualité P2P<br>- Fiabilité des conférences<br>- Fiabilité P2P<br>- Conférence RMC<br>- P2P RMC         |
|CQD Teams Utilization Report.pbit     | Montre comment les utilisateurs de votre organisation utilisent Teams et combien. Veillez à charger les données de génération pour optimiser votre expérience de création de rapports. Pour plus d’informations, consultez [Utiliser le rapport Power BI CQD pour afficher Microsoft Teams utilisation](CQD-teams-utilization-report.md). |
|Commentaires de l’utilisateur CQD (Rate My Call) Report.pbit     | Affiche les données Rate My Call d’une manière que vous pouvez facilement utiliser pour prendre en charge les appels pour votre organisation. Référence croisée avec des commentaires pour identifier les opportunités d’éducation des utilisateurs finaux. |

> [!TIP]
> Une fois que vous avez configuré vos rapports Power BI pour les données CQD, ajoutez-les sous forme d’onglet à un canal. Une fois que vous avez sélectionné **+** dans un canal, sélectionnez **Power BI**, puis recherchez votre rapport. Pour en savoir plus, lisez [le rapport Incorporer avec l’onglet Power BI pour Teams](/power-bi/service-embed-report-microsoft-teams). N’oubliez pas que seules les personnes disposant d’une licence Power BI et d’informations d’identification d’administrateur CQD peuvent accéder à ces rapports.

## <a name="related-topics"></a>Voir aussi

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](./monitor-call-quality-qos.md)
