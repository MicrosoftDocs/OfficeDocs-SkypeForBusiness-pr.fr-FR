---
title: Microsoft Teams rapport de licence de protection des informations
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
description: Découvrez comment utiliser le rapport de licence Teams Information Protection dans le centre d’administration Microsoft Teams pour voir comment les applications de votre organisation utilisent les API d’abonnement aux événements de notification de modification.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681535"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams rapport de licence de protection des informations


Teams rapport sur les licences de protection des informations fournit des insights sur l’utilisation des API [Microsoft Graph qui ont des exigences de licence et de paiement](/graph/teams-licenses). Ce rapport met en évidence toutes les applications qui utilisent ces API dans [model=A](/graph/teams-licenses#modela-requirements). Il n’affiche pas l’utilisation lorsque les API sont utilisées en [mode model=B](/graph/teams-licenses#modelb-requirements) ou [d’évaluation](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Afficher le rapport de licence de protection des informations

Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, sélectionnez **Analyse & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports**, sous **Rapport**, sélectionnez **Information Protection Licence**.
2. Sous **Plage de dates**, sélectionnez une plage.
3. Sous **Applications**, sélectionnez une application, puis **sélectionnez Exécuter le rapport**.

    ![Capture d’écran de la liste déroulante de Teams rapport de licence de protection des informations dans le centre d’administration Teams avec des légendes.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Capture d’écran de la liste déroulante de Teams rapport de licence de protection des informations dans le centre d’administration Teams avec des légendes.")

4. Pour chaque catégorie, les métriques sur les utilisateurs disposant d’une licence, les utilisateurs sans licence, la capacité initiale et la capacité utilisée peuvent être affichées. 

    ![Capture d’écran du graphique récapitulatif de Teams rapport de licence de protection des informations dans le centre d’administration Teams de notification de modification avec légendes.](../media/teams-info-protection-license-report-chart-with-callouts.png "Capture d’écran du graphique récapitulatif de Teams rapport de licence de protection des informations dans le centre d’administration Teams de notification de modification avec légendes.")

5. Vous pouvez exporter les données en cliquant sur le bouton Exporter. Vous pouvez changer les données de table en cliquant sur les onglets de Teams API de notification de modification, Teams l’API patch, Teams exporter des API (conversation) et Teams exporter des API (équipes). 

    ![Capture d’écran des différents onglets de Teams rapport de licence de protection des informations dans le centre d’administration Teams des onglets avec légendes.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Capture d’écran des différents onglets de Teams rapport de licence de protection des informations dans le centre d’administration Teams des onglets avec légendes.")

    ![Capture d’écran de l’onglet Notification de modification du rapport de licence de Teams protection des informations dans le centre d’administration Teams avec des légendes.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Capture d’écran de l’onglet Notification de modification du rapport de licence de Teams protection des informations dans le centre d’administration Teams avec des légendes.")


## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport sur les licences de protection des informations peut être consulté pour les tendances des trois derniers mois. |
|**2**   |Le nom de l’application affiche la liste de toutes les applications qui ont utilisé [Microsoft API Graph qui a des exigences de licence et de paiement](/graph/teams-licenses) pendant la période sélectionnée.|
|**3**   |Nombre d’utilisateurs disposant [de licences valides](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Nombre d’utilisateurs qui n’ont pas de [licence](/graph/teams-licenses#required-licenses-for-modela) valide.  |
|**5**   |Volume total d’appels d’API autorisés à une application au-delà duquel des frais de consommation par appel d’API seront facturés à l’application. |
|**6**   |Volume total d’appels d’API utilisé par l’application pour la plage de dates donnée. |
|**7**   |Exportez le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter vers Excel**, puis l’onglet **Téléchargements**. Sélectionnez **Télécharger** pour télécharger le rapport lorsqu’il est prêt. Cette exportation exporte uniquement l’onglet actuellement sélectionné.|
|**8**   |Sélectionnez une étiquette spécifique pour l’afficher ou la masquer dans un graphique. |
|**9**   |Chaque onglet affiche l’utilisation d’un ensemble particulier d’API, à savoir la [notification de modification](/graph/api/resources/webhooks), [l’API d’exportation](/microsoftteams/export-teams-content) et l’API [de message de mise à jour](/graph/api/message-update). Sélectionnez un onglet pour afficher les détails d’utilisation de cette API. |
|**10**   |**Modifier l’utilisation de l’API de notification**<li>**Nom d’affichage** : nom d’affichage de l’utilisateur sur lequel une notification de modification a été déclenchée.</li><li>**Licence requise** : indique si l’utilisateur donné dispose de la licence requise pour envoyer correctement une notification de modification à l’application.</li><li>**Nombre de tentatives** : nombre total de notifications de modification qui ont été déclenchées en raison de cet utilisateur.</li><li>**Notification de modification envoyée** : nombre total de notifications de modification envoyées à l’application. Cette valeur est inférieure au nombre total de notifications de modification déclenchées si l’utilisateur n’a pas de licence valide.</li>|
|**11**|**Patch API**<li>**Nom d’affichage** : nom complet de l’utilisateur dans lequel une tentative de mise à jour du message a été effectuée.</li> <li>**Licence requise** : indique si l’utilisateur donné dispose de la licence requise pour que le message soit correctement mis à jour.</li><li>**Nombre de tentatives** : nombre total de tentatives de mise à jour des messages.</li><li>**Message corrigé** : nombre total de messages qui ont été correctement mis à jour.</li>|
|**12**|**Utilisation de l’API d’exportation de conversation**<li>**Nom d’affichage** : nom d’affichage de l’utilisateur où une tentative d’exportation du message de conversation de l’utilisateur a été effectuée.</li><li>**Licence requise** : indique si l’utilisateur donné dispose de la licence requise pour que le message soit correctement exporté.</li><li>**Nombre de tentatives** : nombre total de tentatives d’exportation de messages de conversation.</li><li>**Message exporté** : nombre total de tentatives où le message de conversation a été exporté avec succès.</li> |
|**13**|**Utilisation de l’API d’exportation d’équipe**<li>**Nom d’affichage** : nom complet de l’équipe dans laquelle une tentative d’exportation du message de cette équipe a été effectuée.</li><li>**Nombre de tentatives** : nombre total de tentatives d’exportation de messages d’équipe.</li><li>**Message exporté** : nombre total de tentatives où le message d’équipe a été correctement exporté.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques à l’utilisateur anonymes

Pour rendre les données du rapport d’activité utilisateur Teams anonymes, vous devez être administrateur général. Cela masque les informations d’identification telles que le nom d’affichage, l’e-mail et l’ID Azure AD dans les rapports et leurs exportations.

1. Dans le Centre d'administration Microsoft 365, accédez à **Paramètres** \> **Paramètres d’organisation** et, sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis choisissez **d’afficher les identificateurs anonymes**. Ce paramètre est appliqué aux rapports d’utilisation dans le Centre d'administration Microsoft 365 et au centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.