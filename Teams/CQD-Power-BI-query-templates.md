---
title: Utiliser Power BI pour analyser des données bord pour Microsoft teams
ms.author: lolaj
author: LolaJacobsen
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
description: Utilisez Power BI pour analyser les données de bord pour Microsoft Teams.
ms.openlocfilehash: af540f09fefc27b99e1c084d2571fe51d47a393c
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170502"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Utiliser Power BI pour analyser des données bord pour Microsoft teams

Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.

Pour les rapports bord dans Microsoft Teams, si vous préférez utiliser Power BI pour interroger et créer des rapports sur vos données, téléchargez nos modèles Power BI bord. Lorsque vous ouvrez les modèles dans Power BI, vous êtes invité à vous connecter à l’aide de vos informations d’identification d’administrateur bord. Vous pouvez personnaliser ces modèles de requête et les distribuer à toutes les personnes de votre organisation disposant d’une licence Power BI et d’autorisations d’administrateur bord.

Pour pouvoir utiliser ces fichiers PBIX, vous devez [installer le connecteur Power bi pour Microsoft bord](CQD-Power-BI-connector.md) à l’aide du fichier *MicrosoftCallQuality. pqx* inclus dans le [Téléchargement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


|  |  |
|---------|---------|
|Rapport du support bord. PBiT     |En intégrant les données de bâtiment et de EUII, ce rapport est conçu pour vous permettre d’effectuer un zoom avant d’un utilisateur unique pour rechercher la cause initiale de la mauvaise qualité d’appel pour cet utilisateur (par exemple, l’utilisateur se trouve dans un bâtiment rencontrant des problèmes de réseau).         |
|Rapport bord emplacement amélioré. PBiT     | Réimaginer les rapports d’emplacement SPD bord. Inclut 9 rapports, offrant une qualité d’appel, des informations de fiabilité et de fréquence d’appel, en créant ou en fonction de l’utilisateur.  Assurez-vous de télécharger les données de bâtiment pour optimiser votre qualité de création de rapports.        |
|Rapport sur les appareils mobiles bord. PBiT     | Fournit des informations spécifiquement adaptées aux utilisateurs d’appareils mobiles, notamment la qualité des appels, la fiabilité et les tarifs d’appel. Afficher les rapports sur le réseau mobile, le réseau WiFi et le système d’exploitation mobile (Android, iOS).        |
|Rapport de routage direct RTC de bord. PBiT     |Fournit des informations spécifiques aux appels RTC qui passent par le routage direct. Pour en savoir plus, lisez [utilisation du rapport de routage direct RTC bord](CQD-PSTN-report.md).         |
|BORD rapport de synthèse. PBiT     |Des visualisations améliorées, une présentation améliorée, une plus grande densité d’information et des dates de roulement. Ces rapports permettent d’identifier plus facilement les valeurs extrêmes. Explorez la qualité des appels à l’aide d’une carte interactive facile à utiliser. 9 nouveaux rapports :</p>-Globalement-qualité<br>– Fiabilité globale<br>-Centre RMC (évaluer mon appel) en général<br>-Qualité de la Conférence<br>-Qualité P2P<br>-Fiabilité des conférences<br>-Fiabilité P2P<br>-Centre d’audioconférence<br>-CENTRE RMC         |
|<strong>(Nouveau !)</strong> Rapport sur l’utilisation des équipes bord. PBiT     | Décrit la façon dont les utilisateurs de votre organisation utilisent des équipes et combien de temps. Assurez-vous de télécharger les données de bâtiment pour optimiser votre qualité de création de rapports. Pour en savoir plus, voir [utiliser le rapport Power bi bord pour afficher le taux d’utilisation de Microsoft teams](CQD-teams-utilization-report.md).        |
|Rapport sur les utilisateurs bord (évaluer mon appel). PBiT     | Le mode d’affichage des données d’appel vous permet de classer facilement les appels au sein de votre organisation. Référence croisée avec Verbatim pour identifier les opportunités de la formation des utilisateurs finaux.        |

> [!TIP]
> Une fois que vous avez configuré vos rapports Power BI pour bord données, ajoutez-les comme onglet à un canal. Après avoir sélectionné **+** dans un canal, sélectionnez **Power bi** , puis recherchez votre rapport. N’oubliez pas que seules les personnes disposant d’une licence Power BI et les informations d’identification d’administrateur bord peuvent accéder à ces rapports.


## <a name="related-topics"></a>Voir aussi

[Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le tableau de bord de qualité des appels](stream-classification-in-call-quality-dashboard.md)

[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Tableau de bord Analyse des appels et Qualité des appels](difference-between-call-analytics-and-call-quality-dashboard.md)
 
