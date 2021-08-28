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
description: Découvrez comment utiliser le rapport sur les licences Teams de protection des informations dans le Centre d’administration Microsoft Teams pour voir comment les applications de votre organisation utilisent les API d’abonnement aux événements de notification de modification.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1fc9dd7dc39c8803a87f71f9ef80e2a5609603a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625856"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams de licence de protection des informations

Le rapport sur les licences de protection [](/graph/api/resources/subscription?view=graph-rest-1.0) des informations Teams fournit des informations sur les applications qui se sont abonnées à la modification d’événements de [notification](/graph/api/resources/webhooks?view=graph-rest-1.0) afin d’écouter les messages créés, mis à jour ou supprimés au niveau du client (c’est-à-dire, /teams/getAllMessage ou /chats/getAllMessages). Une notification de modification correspondant au message est envoyée avec succès uniquement lorsque l’utilisateur dispose de [la licence requise.](/graph/teams-licenses)  Vous pouvez voir le nombre de notifications de modification déclenchées par un utilisateur donné.


## <a name="view-the-information-protection-license-report"></a>Afficher le rapport sur les licences de protection des informations

Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le panneau de navigation gauche du Centre Microsoft Teams’administration, sélectionnez **Analyse et**  >  **&'utilisation des rapports.** Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Licence Protection des informations.**
2. Sous **Plage de dates,** sélectionnez une plage.
3. Sous **Applications,** sélectionnez une application, puis **sélectionnez Exécuter le rapport.**

    ![Capture d’écran du Teams licence de protection des informations dans le Centre Teams’administration avec des appels](../media/teams-info-protection-license-report-with-callouts.png "Capture d’écran du Teams licence de protection des informations dans le Centre Teams’administration avec des appels")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport sur les licences de protection des informations permet d’afficher les tendances des 7, 30 ou 90 derniers jours. |
|**2**   |Le nom de l’application affiche la liste de toutes les applications abonnées à la modification des événements de notification des messages des n derniers jours, telles qu’sélectionnées dans la plage de dates. |
|**3**   |Le tableau offre une répartition par utilisateur de l’application sélectionnée.<ul><li>**Le nom d’affichage** est le nom d’affichage de l’utilisateur. Sélectionnez le nom d’affichage pour afficher la page des détails de l’utilisateur dans le Microsoft Teams d’administration.</li><li>**A la licence requise** est oui si l’utilisateur dispose d’une des licences requises telles que définies (ici)[ https://docs.microsoft.com/en-us/graph/teams-licenses ]. Si l’utilisateur n’a pas  la licence requise, le lien Attribuer une licence s’affiche, qui permet d’accéder à la page des détails de la licence de l’utilisateur dans le Centre d’administration Microsoft (utilisateurs actifs et > nom d’utilisateur).  >  </li><li>**Les événements protégés** par licence sont le nombre d’événements de notification de modification uniques envoyés à l’application par rapport à un message qui a été créé, mis à jour ou supprimé par cet utilisateur.</li></ul> |
|**4**   |Exportez le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Sélectionnez **Exporter vers Excel,** puis **l’onglet Téléchargements.** **Sélectionnez** Télécharger pour télécharger le rapport lorsqu’il est prêt. |
|**5**   |Exportez le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Sélectionnez **Exporter vers Excel,** puis **l’onglet Téléchargements.** **Sélectionnez** Télécharger pour télécharger le rapport lorsqu’il est prêt. Lorsque vous affichez le rapport dans Excel, vous voyez  également une colonne d’ID et une colonne de courrier, qui représente l’ID d’utilisateur et l’adresse de courrier de l’utilisateur.  |

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour anonymisation des données du Teams activité des utilisateurs, vous devez être administrateur général. Cela permet de masquer les informations identifiables telles que le nom d’affichage, le courrier électronique et l’ID Azure AD dans les rapports et leurs exportations.

1. Dans le Centre d’administration Microsoft 365, sélectionnez  Paramètres organisation Paramètres, puis sous l’onglet \>  **Services,** sélectionnez **Rapports.**
    
2. Sélectionnez **Rapports,** puis choisissez **d’afficher les identificateurs anonymes.** Ce paramètre est appliqué aux rapports d’utilisation dans le Centre d’administration Microsoft 365 et le Teams d’administration.
  
3. Sélectionnez **Enregistrer les modifications.**
