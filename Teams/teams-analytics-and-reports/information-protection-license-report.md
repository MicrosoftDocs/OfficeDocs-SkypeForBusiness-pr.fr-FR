---
title: Microsoft Teams de licence de protection des informations
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport Teams licence de protection des informations dans le Centre d’administration Microsoft Teams pour voir comment les applications de votre organisation utilisent les API d’abonnement aux événements de notification de modification.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435858"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams de licence de protection des informations


Teams de la licence de protection des informations fournit des informations sur l’utilisation des API [microsoft et Graph API qui ont des conditions de licence et de paiement requises](/graph/teams-licenses). Ce rapport met en évidence toutes les applications qui utilisent ces API dans [model=A](/graph/teams-licenses#modela-requirements). Elle n’affiche pas l’utilisation lorsque des API sont utilisées [en mode model=B](/graph/teams-licenses#modelb-requirements) [ou d’évaluation](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Afficher le rapport sur les licences de protection des informations

Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans la barre de navigation gauche du Microsoft Teams d’administration, sélectionnez **Analyse & rapports d’utilisation** >  **des rapports**. Sous **l’onglet Afficher les rapports** , sous **Rapport**, sélectionnez **Licence Protection des informations**.
2. Sous **Plage de dates**, sélectionnez une plage.
3. Sous **Applications**, sélectionnez une application, puis sélectionnez **Exécuter le rapport**.

    ![Capture d’écran de la Teams du rapport sur les licences de protection des informations dans le Teams d’administration avec des appels.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Capture d’écran de la Teams du rapport sur les licences de protection des informations dans le Teams d’administration avec des appels.")

4. Pour chaque catégorie, les mesures sur les utilisateurs titulaires d’une licence, les utilisateurs sans licence, la capacité sous-utilisée et la capacité utilisée peuvent être vues. 

    ![Capture d’écran du graphique de synthèse Teams rapport sur les licences de protection des informations dans le Teams d’administration de la notification de modification avec des appels.](../media/teams-info-protection-license-report-chart-with-callouts.png "Capture d’écran du graphique de synthèse Teams rapport sur les licences de protection des informations dans le Teams d’administration de la notification de modification avec des appels.")

5. Les données peuvent être exportées en cliquant sur le bouton d’exportation. Vous pouvez changer les données du tableau en cliquant sur les onglets de l’API de notification de modification de Teams, de l’API Teams patch API, de l’api Teams exporter des API (conversation) et d’Teams d’exportation d’API (teams). 

    ![Capture d’écran des différents onglets Teams rapport sur les licences de protection des informations dans le Teams d’administration des onglets avec des appels.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Capture d’écran des différents onglets Teams rapport sur les licences de protection des informations dans le Teams d’administration des onglets avec des appels.")

    ![Capture d’écran de l’onglet de notification de modification Teams rapport sur les licences de protection des informations dans le Teams d’administration avec des appels.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Capture d’écran de l’onglet de notification de modification Teams rapport sur les licences de protection des informations dans le Teams d’administration avec des appels.")


## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport sur les licences de protection des informations peut être pris en compte pour les tendances des trois derniers mois. |
|**2**   |Le nom de l’application affiche la liste de toutes les applications qui ont utilisé [l’API Microsoft Graph](/graph/teams-licenses) qui a des conditions de licence et de paiement requises pendant la période sélectionnée.|
|**3**   |Nombre d’utilisateurs titulaires de [licences valides](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Nombre d’utilisateurs n’ayant pas de licence [valide](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |Volume total d’appel d’API autorisé pour une application au-delà duquel des frais de consommation par appel d’API sont facturés à l’application. |
|**6**   |Volume total d’appel de l’API utilisé par l’application pour la plage de dates donnée. |
|**7**   |Exportez le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. **Sélectionnez Exporter vers Excel**, puis l’onglet **Téléchargements**. Sélectionnez Télécharger  pour télécharger le rapport lorsqu’il est prêt. Cette exportation exportera uniquement l’onglet actuellement sélectionné.|
|**8**   |Sélectionnez une étiquette spécifique pour l’afficher ou la masquer dans un graphique. |
|**9**   |Chaque onglet affiche l’utilisation d’un ensemble particulier d’API, à savoir modifier [les notifications](/graph/api/resources/webhooks), [exporter l’API](/microsoftteams/export-teams-content) et mettre à jour [l’API de message](/graph/api/message-update). Sélectionnez un onglet pour afficher les détails d’utilisation de cette API. |
|**10**   |**Modifier l’utilisation de l’API de notification**<li>**Nom d’affichage** - Nom d’affichage de l’utilisateur pour lequel une notification de modification a été déclenchée.</li><li>**Licence requise** : si l’utilisateur donné dispose de la licence requise pour envoyer avec succès une notification de modification à l’application.</li><li>**Nombre de tentatives** - Nombre total de notifications de modification déclenchées en raison de l’utilisateur.</li><li>**Notification de modification envoyée** - Nombre total de notifications de modification envoyées à l’application. Cette valeur sera inférieure à la quantité totale de notifications de modification déclenchée si l’utilisateur n’a pas de licence valide.</li>|
|**11**|**Patch API**<li>**Nom d’affichage** - Nom d’affichage de l’utilisateur pour lequel une tentative de mise à jour du message a été effectuée.</li> <li>**Licence requise** : si l’utilisateur donné dispose de la licence requise pour que le message soit correctement mis à jour.</li><li>**Nombre d’tentatives** - Nombre total de tentatives de mise à jour des messages.</li><li>**Message Patched** - Nombre total de messages qui ont été mis à jour correctement.</li>|
|**12**|**Utilisation de l’API Exportation de conversation**<li>**Nom d’affichage** - Nom d’affichage de l’utilisateur pour lequel une tentative d’exportation du message de conversation de l’utilisateur a été effectuée.</li><li>**Licence requise** : si l’utilisateur donné dispose de la licence requise pour l’exportation du message.</li><li>**Nombre d’tentatives** - Nombre total d’tentatives d’exportation de messages de conversation.</li><li>**Message exporté :** nombre total de tentatives d’exportation d’un message de conversation.</li> |
|**13**|**Utilisation de l’API Team Export**<li>**Nom d’affichage** - Nom d’affichage de l’équipe dans laquelle une tentative d’exportation du message de cette équipe a été effectuée.</li><li>**Nombre d’tentatives** - Nombre total d’tentatives d’exportation de messages d’équipe.</li><li>**Message exporté :** nombre total de tentatives pour laquelle le message d’équipe a été correctement exporté.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour anonymisation des données Teams rapport d’activité des utilisateurs, vous devez être administrateur général. Cela a pour effet de masquer les informations identifiables telles que le nom d’affichage, le courrier électronique et Azure AD ID dans les rapports et leurs exportations.

1. Dans le Centre d'administration Microsoft 365, sélectionnez  \> Paramètres **organisation** Paramètres, puis sous l’onglet **Services**, sélectionnez **Rapports**.
    
2. **Sélectionnez Rapports**, puis choisissez **d’afficher les identificateurs anonymes**. Ce paramètre est appliqué aux rapports d’utilisation dans le Centre d Centre d'administration Microsoft 365'administration Teams’utilisation.
  
3. **Sélectionnez Enregistrer les modifications**.