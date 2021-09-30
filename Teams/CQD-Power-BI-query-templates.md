---
title: Utiliser Power BI pour analyser les données du sous-Microsoft Teams
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
description: Utilisez Power BI pour analyser les données du CQD à des Microsoft Teams.
ms.openlocfilehash: 4a96a53454f1f4d89feed3ea87342a7991d7975c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013768"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Utiliser Power BI pour analyser les données du sous-Microsoft Teams

Nouveautés de janvier 2020 : télécharger Power BI modèles de [requête pour le CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données de CQD.

Pour les rapports du tableau de bord de qualité des appels dans Teams, si vous préférez utiliser Power BI pour interroger et signaler vos données, téléchargez notre tableau de bord de qualité Power BI modèles. Lorsque vous ouvrez les modèles dans Power BI, vous êtes invité à vous connectez avec vos informations d’identification d’administrateur du CQD. Vous pouvez personnaliser ces modèles de requête et les distribuer à tous les membres de votre organisation qui disposent d’une licence Power BI et des autorisations d’administrateur du CQD.

Pour pouvoir utiliser ces fichiers PBIT, vous devez installer le connecteur Power BI pour le fichier [CQD Microsoft](CQD-Power-BI-connector.md) à l’aide du fichier *MicrosoftCallQuality.pqx* inclus dans le [téléchargement.](https://www.microsoft.com/download/details.aspx?id=102291) 

Assurez-vous que vous avez le rôle [d’accès du CQD droit pour](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) accéder aux Power BI rapports. 

|&nbsp;|&nbsp;|
|---------|---------|
|<strong>(Nouveau!)</strong> CQD Teams Standard automatique & Call Queue Historical Report.pbit     |  Ce modèle fournit les trois rapports suivants :</p><li>Standard automatique affiche les données d’analyse des appels qui arrivent dans vos attendants automatiques.</li><li>File d’attente d’appels affichant les données d’analyse des appels qui arrivent dans vos files d’attente.</li><li>Chronologie de l’agent : affichage chronologique des agents actifs dans les appels de la file d’attente d’appels.</li><br>Pour en savoir plus, lisez Standard automatique & [historique de la file d’attente d’appels.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |En intégrant les données bâtiment et EUII, ce rapport est conçu pour vous permettre d’aller d’un utilisateur à l’autre afin de trouver la cause première en amont d’une mauvaise qualité des appels pour cet utilisateur (par exemple, l’utilisateur se trouve dans un bâtiment qui rencontre des problèmes de réseau).         |
|Rapport amélioré.pbit de l’emplacement du CQD     | Re-imaginant les rapports d’emplacement du SPD CQD. Comprend 9 rapports, fournissant des informations sur la qualité des appels, le WiFi du bâtiment, la fiabilité et l’évaluer (RMC) avec des drill-thrus supplémentaires par bâtiment ou par utilisateur.  Veillez à charger les données de création afin d’optimiser votre expérience de création de rapports.        |
|CQD Mobile Device Report.pbit     | Fournit des informations spécifiquement conçus pour les utilisateurs d’appareils mobiles, notamment la qualité, la fiabilité et la fréquence d’appel. Afficher les rapports sur le réseau mobile, le réseau WiFi et le système d’exploitation mobile (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Fournit des informations spécifiques pour les appels RST qui traversent un routage direct. Pour en savoir plus, [lisez l’utilisation](CQD-PSTN-report.md)du rapport de routage RQD direct.         |
|Rapport.pbit de synthèse du tableau de procédure     |Visualisations améliorées, présentation améliorée, densité d’informations accrue et dates de roulement. Ces rapports facilitent l’identificateur des valeurs hors valeur. Drill into call quality by location with an easy-to-use interactive map. 9 nouveaux rapports :</p>- Qualité globale<br>- Fiabilité globale<br>- RMC (évaluation de mon appel) global<br>- Qualité de la conférence<br>- Qualité P2P<br>- Fiabilité de la conférence<br>- Fiabilité de P2P<br>- Conférence RMC<br>- P2P RMC         |
|<strong>(Nouveau!)</strong> Rapport d’utilisation du Teams.pbit du Teams de la faq     | Indique comment les utilisateurs de votre organisation utilisent Teams et le nombre d’utilisations. Veillez à charger les données de création afin d’optimiser votre expérience de création de rapports. Pour en savoir plus, [lisez Utiliser le point de Power BI rapport pour afficher Microsoft Teams utilisation.](CQD-teams-utilization-report.md)        |
|Commentaires des utilisateurs du CQD (rate My Call) Report.pbit     | Affiche les données évaluer mon appel d’une façon que vous pouvez facilement utiliser pour aider à prendre en charge les appels pour votre organisation. Référence croisée avec des verbatims pour identifier les opportunités de formation des utilisateurs finaux.        |

> [!TIP]
> Une fois que vous avez Power BI de tableau de qualité des Power BI, ajoutez-les sous la direction d’un onglet à un canal. Après avoir sélectionné **+** dans un canal, **sélectionnez Power BI** recherchez votre rapport. Pour en savoir plus, [lisez Incorporer le rapport avec l’Power BI’onglet pour Teams.](/power-bi/service-embed-report-microsoft-teams) Rappelez-vous que seules les personnes Power BI licence utilisateur et les informations d’identification d’administrateur du CQD peuvent accéder à ces rapports.


## <a name="related-topics"></a>Voir aussi

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](./monitor-call-quality-qos.md)
