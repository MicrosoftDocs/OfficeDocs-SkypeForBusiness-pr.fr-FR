---
title: Utiliser Power BI pour analyser les données du CQD pour Microsoft Teams
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
localization_priority: Normal
description: Utilisez Power BI pour analyser les données du CQD pour Microsoft Teams.
ms.openlocfilehash: 5ef98f75854cb4a255bf3f01aeb32de66c059b76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096520"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Utiliser Power BI pour analyser les données du CQD pour Microsoft Teams

Nouveautés de Janvier 2020 : Téléchargez les modèles de requête [Power BI pour CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler les données de votre CQD.

Pour les rapports de tableau de bord de qualité des appels dans Teams, si vous préférez utiliser Power BI pour interroger et signaler vos données, téléchargez nos modèles Power BI du tableau de bord de qualité des appels. Lorsque vous ouvrez les modèles dans Power BI, vous êtes invité à vous connectez avec vos informations d’identification d’administrateur du CQD. Vous pouvez personnaliser ces modèles de requête et les distribuer à tous les membres de votre organisation qui disposent d’une licence Power BI et d’autorisations d’administrateur du CQD.

Pour pouvoir utiliser ces fichiers PBIT, vous devez installer Power BI Connector pour [le CQD Microsoft](CQD-Power-BI-connector.md) à l’aide du fichier *MicrosoftCallQuality.pqx* inclus dans le [téléchargement.](https://www.microsoft.com/download/details.aspx?id=102291) 

Assurez-vous que vous avez le rôle [d’accès de CQD droit pour](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) accéder aux rapports Power BI. 

|  |  |
|---------|---------|
|<strong>(Nouveau!)</strong> CQD Teams Standard automatique & Call Queue Historical Report.pbit     |  Ce modèle fournit les trois rapports suivants :</p><li>Standard automatique affiche les données d’analyse des appels qui arrivent dans vos attendants automatiques.</li><li>File d’attente d’appels affichant les données d’analyse des appels qui arrivent dans vos files d’attente.</li><li>Chronologie de l’agent : affichage chronologique des agents actifs dans les appels de la file d’attente d’appels.</li><br>Pour en savoir plus, lisez Standard automatique & [historique de la file d’attente d’appels.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |En intégrant les données bâtiment et EUII, ce rapport est conçu pour vous permettre d’aller plus haut d’un utilisateur à la recherche de la cause première en amont d’une mauvaise qualité des appels pour cet utilisateur (par exemple, l’utilisateur se trouve dans un bâtiment qui rencontre des problèmes de réseau).         |
|Rapport amélioré.pbit de l’emplacement du CQD     | Re-imaginant les rapports d’emplacement du SPD CQD. Comprend 9 rapports, fournissant des informations sur la qualité des appels, le WiFi du bâtiment, la fiabilité et l’évaluer (RMC) avec des drill-thrus supplémentaires par bâtiment ou par utilisateur.  Veillez à charger les données de création afin d’optimiser votre expérience de création de rapports.        |
|CQD Mobile Device Report.pbit     | Fournit des informations spécifiquement conçus pour les utilisateurs d’appareils mobiles, notamment la qualité, la fiabilité et la fréquence d’appel. Afficher les rapports sur le réseau mobile, le réseau WiFi et le système d’exploitation mobile (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Fournit des informations spécifiques pour les appels RST qui traversent un routage direct. Pour en savoir plus, [lisez l’utilisation](CQD-PSTN-report.md)du rapport de routage RQD direct.         |
|Rapport.pbit de synthèse du tableau de procédure     |Visualisations améliorées, présentation améliorée, densité d’informations accrue et dates de roulement. Ces rapports facilitent l’identificateur des valeurs hors valeur. Drill into call quality by location with an easy-to-use interactive map. 9 nouveaux rapports :</p>- Qualité globale<br>- Fiabilité globale<br>- RMC (évaluation de mon appel) global<br>- Qualité de la conférence<br>- Qualité P2P<br>- Fiabilité de la conférence<br>- Fiabilité de P2P<br>- Conférence RMC<br>- P2P RMC         |
|<strong>(Nouveau!)</strong> Rapport.pbit sur l’utilisation des équipes du CQD     | Indique comment les utilisateurs de votre organisation utilisent Teams et le nombre d’utilisations. Veillez à charger les données de création afin d’optimiser votre expérience de création de rapports. Pour en savoir plus, [lisez Utiliser le rapport Power BI du CQD pour afficher l’utilisation de Microsoft Teams.](CQD-teams-utilization-report.md)        |
|Commentaires des utilisateurs du CQD (rate My Call) Report.pbit     | Affiche les données évaluer mon appel d’une façon que vous pouvez facilement utiliser pour aider à prendre en charge les appels pour votre organisation. Référence croisée avec des verbatims pour identifier les opportunités de formation des utilisateurs finaux.        |

> [!TIP]
> Une fois que vous avez installé vos rapports Power BI pour les données du tableau de qualité des qualités des données, ajoutez-les sous la direction d’un onglet à un canal. Une fois que vous **+** avez sélectionné dans un canal, **sélectionnez Power BI,** puis recherchez votre rapport. Pour en savoir plus, [lisez Incorporer le rapport avec l’onglet Power BI pour Teams.](/power-bi/service-embed-report-microsoft-teams) Rappelez-vous que seules les personnes titulaires d’une licence Power BI et d’informations d’identification d’administrateur du CQD peuvent accéder à ces rapports.


## <a name="related-topics"></a>Rubriques connexes

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](./monitor-call-quality-qos.md)
