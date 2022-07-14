---
title: Configurer l’analytique des appels pour Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurez l’analytique des appels par utilisateur pour identifier et résoudre les problèmes de qualité des appels Microsoft Teams.
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789939"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurer l’analytique des appels pour Microsoft Teams

En tant qu’administrateur Microsoft Teams, vous pouvez utiliser l’analytique des appels par utilisateur pour résoudre les problèmes de qualité des appels et de connexion Teams pour **les utilisateurs individuels**. Pour tirer pleinement parti de l’analytique des appels, configurez les éléments suivants :
  
- Attribuez des rôles de support spécialisés à des personnes, telles que des agents du support technique, pour leur permettre d’afficher l’analytique des appels pour les utilisateurs. Ces rôles de support ne peuvent pas accéder au reste du Centre d’administration Teams. 
    
- Ajoutez des informations de construction, de site et de locataire à l’analytique des appels par utilisateur en chargeant un fichier de données .tsv ou .csv.
    
Lorsque vous êtes prêt à commencer à utiliser l’analytique des appels par utilisateur, lisez [Utiliser l’analytique des appels par utilisateur pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Accorder l’autorisation au personnel du support et du support technique

En tant qu’administrateur Teams, vous avez un accès complet aux informations d’analytique des appels pour tous les utilisateurs. Nous avons créé des rôles Azure Active Directory spécialisés que vous pouvez attribuer au personnel du support technique et aux agents du support technique afin qu’ils puissent également accéder à l’analytique des appels par utilisateur (sans avoir accès au reste du centre d’administration Teams). Attribuez le rôle **de spécialiste du support des communications Teams** aux utilisateurs qui doivent avoir une vue limitée de l’analytique des appels par utilisateur (support de niveau 1). Attribuez le rôle **d’ingénieur du support des communications Teams** aux utilisateurs qui ont besoin d’un accès complet à l’analytique des appels par utilisateur (support de niveau 2). Aucun des rôles n’a accès au reste du Centre d’administration Teams.

Pour savoir ce que fait chacun de ces rôles, lisez [Ce que fait chaque rôle de support Teams](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do) ?

Pour plus d’informations sur les rôles d’administrateur Teams, consultez [Utiliser les rôles d’administrateur Teams pour gérer Teams](using-admin-roles.md). Pour savoir comment attribuer des rôles d’administrateur dans Azure Active Directory, consultez [Afficher et attribuer des rôles dans Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Pour savoir comment attribuer des rôles d’administration dans Azure Active Directory, consultez [Afficher et attribuer des rôles dans Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Charger un fichier .tsv ou .csv pour ajouter des informations de bâtiment, de site et de locataire

Vous pouvez ajouter des informations de construction, de site et de locataire à l’analytique des appels par utilisateur en chargeant un fichier .csv ou .tsv. Avec toutes ces informations, l’analytique des appels peut mapper des adresses IP à des emplacements physiques. Les administrateurs et les agents du support technique peuvent utiliser ces informations pour identifier les tendances des problèmes d’appel. Par exemple, pourquoi les utilisateurs du même bâtiment rencontrent-ils des problèmes de qualité d’appel similaires ? 

Si vous êtes administrateur Teams ou Skype Entreprise, vous pouvez utiliser un locataire existant et créer un fichier de données à partir de Teams ou Skype Entreprise tableau de bord de qualité des appels (CQD). Tout d’abord, vous téléchargez le fichier à partir du CQD, puis vous le chargez pour appeler l’analytique. 

- Pour télécharger un fichier de données existant, accédez maintenant au centre  >  d’administration **Microsoft Teams****Analytics & rapports** >  appeler le **chargement** **du tableau de bord** >  qualité. Dans la liste **Mes chargements** , cliquez sur **Télécharger** en regard du fichier souhaité. 

- Pour charger le nouveau fichier, consultez [Ajouter et mettre à jour les étiquettes de création de rapports](/microsoftteams/learn-more-about-site-upload).
  
Si vous créez le fichier .tsv ou .csv à partir de zéro, consultez [Charger le locataire et générer des données](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Sujets associés

[Utiliser l’analytique des appels par utilisateur pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
