---
title: Configurer l’analyse des appels pour Microsoft teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Définissez une analyse d’appel par utilisateur pour identifier et résoudre les problèmes de qualité d’appel dans Microsoft Teams.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085310"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurer l’analyse des appels pour Microsoft teams

En tant qu’administrateur de Microsoft Teams, vous pouvez utiliser une analyse d’appel par utilisateur pour résoudre les problèmes de qualité d’appel et de connexion d’équipes pour **les utilisateurs individuels**. Pour tirer pleinement parti de l’analyse des appels, vous devez configurer les éléments suivants :
  
- Attribuez des rôles de support spécialisés aux utilisateurs, tels que les agents de support technique, pour leur permettre d’afficher les données d’analyse pour les utilisateurs. Ces rôles d’assistance ne peuvent pas accéder au reste du centre d’administration Teams. 
    
- Ajoutez des informations de bâtiment, de site et de client à une analyse d’appel par utilisateur en chargeant un fichier de données. TSV ou. csv.
    
Lorsque vous êtes prêt à commencer à utiliser une analyse d’appel par utilisateur, voir [utiliser une analyse d’appel par utilisateur pour résoudre les problèmes de mauvaise qualité d’appel](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Accorder l’autorisation d’assistance et au personnel du support technique

En tant qu’administrateur Teams, vous disposez d’un accès total aux informations d’analyse des appels pour tous les utilisateurs. Nous avons créé quelques rôles Azure Active Directory spécialisés que vous pouvez affecter au personnel de support technique et aux agents de support technique pour qu’ils puissent également accéder aux analyses d’appel par utilisateur (sans avoir accès au reste du centre d’administration Teams). Affectez au rôle de spécialiste de la **prise en charge des communications équipe** aux utilisateurs qui doivent disposer d’un affichage limité d’une analyse d’appel par utilisateur (prise en charge de niveau 1). Affectez au rôle de **technicien de support communications** de l’équipe aux utilisateurs qui ont besoin d’un accès total à une analyse d’appel par utilisateur (prise en charge de niveau 2). Aucun des rôles n’a accès au reste du centre d’administration Teams.

Pour plus d’informations sur chacun de ces rôles, voir [qu’est-ce que chaque équipe prend en charge](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Pour plus d’informations sur les rôles d’administrateur d’équipe, voir [utiliser des rôles d’administrateur d’équipes pour gérer teams](using-admin-roles.md). Pour plus d’informations sur l’attribution de rôles d’administrateur dans Azure Active Directory, voir [afficher et affecter des rôles dans Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Pour plus d’informations sur l’attribution de rôles d’administrateur dans Azure Active Directory, voir [afficher et affecter des rôles dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger un fichier. TSV ou. csv pour ajouter des informations de bâtiment, de site et de client

Vous pouvez ajouter des informations de bâtiment, de site et de client à une analyse d’appel par utilisateur en chargeant un fichier. csv ou. TSV. À l’aide de ces informations, l’analyse des appels permet de mapper les adresses IP aux emplacements physiques. Les administrateurs et les techniciens du support technique peuvent utiliser ces informations pour détecter les tendances en matière de problèmes d’appel. Par exemple, pourquoi les utilisateurs dans le même bâtiment rencontrent-ils des problèmes de qualité d’appel similaires ? 

Si vous êtes un administrateur teams ou Skype entreprise, vous pouvez utiliser un client existant et créer un fichier de données à partir du tableau de bord des équipes ou de la qualité des appels de Skype entreprise (bord). Tout d’abord, vous devez télécharger le fichier à partir de bord, puis le charger pour appeler Analytics. 

- Pour télécharger un fichier de données existant, accédez au **Centre d’administration Microsoft teams**de  >  **qualité des appels**  >  **Upload now**. Dans la liste **Mes téléchargements** , cliquez sur **Télécharger** en regard du fichier souhaité. 

- Pour télécharger le nouveau fichier, accédez à emplacements du **Centre d’administration de Microsoft teams**  >  **Locations**, puis sélectionnez charger les **données d’emplacement** ou remplacer les **données d’emplacement**.
  
Si vous créez le fichier. TSV ou. csv à partir de zéro, voir [Télécharger le client et générer des données](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Voir aussi

[Utiliser une analyse d’appel par utilisateur pour résoudre les problèmes de mauvaise qualité d’appel](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
