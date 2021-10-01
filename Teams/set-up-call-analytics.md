---
title: Configurer l’analyse des appels pour Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
description: Configurer l’analyse des appels par utilisateur afin d’identifier et de résoudre les Microsoft Teams de qualité des appels.
ms.openlocfilehash: 1f4e3d6586c699a3f8d9fd0cd782f45361bc69d1
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045550"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurer l’analyse des appels pour Microsoft Teams

En tant qu Microsoft Teams utilisateur, vous pouvez utiliser les analyses des appels par utilisateur pour résoudre les problèmes Teams de qualité des appels et de connexion pour **les utilisateurs individuels.** Pour tirer pleinement parti de l’analyse des appels, définissez les informations suivantes :
  
- Attribuez des rôles de support spécialisés aux personnes, telles que les agents du support technique, pour leur permettre d’afficher les données d’analyse des appels pour les utilisateurs. Ces rôles de support ne peuvent pas accéder au reste du Teams d’administration. 
    
- Ajoutez des informations sur le bâtiment, le site et le client à l’analyse des appels en téléchargeant un fichier de données .tsv .csv utilisateur.
    
Lorsque vous êtes prêt à utiliser l’analyse des appels par utilisateur, lisez Utiliser l’analyse des appels par utilisateur pour résoudre les problèmes de [qualité des appels.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Accorder l’autorisation au personnel de support technique et de support technique

En tant qu Teams administrateur de services, vous avez un accès complet aux informations d’analyse des appels pour tous les utilisateurs. Nous avons créé des rôles de Azure Active Directory spécialisés que vous pouvez affecter au personnel de support et aux agents du support technique pour leur permettre également d’accéder aux analyses des appels par utilisateur (sans avoir accès au reste du Centre d’administration Teams). Affectez le **rôle de spécialiste Teams du support** aux communications aux utilisateurs qui doivent avoir un affichage limité de l’analyse des appels par utilisateur (support au niveau 1). Attribuez le **rôle Teams support** aux communications aux utilisateurs qui ont besoin d’un accès total à l’analyse des appels par utilisateur (support de niveau 2). Aucun rôle n’a accès au reste du Centre d’Teams’administration.

Pour savoir ce que font chacun de ces rôles, lisez ce que Teams [rôle support fait-il](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Pour plus d’informations sur Teams rôles d’administrateur, voir Utiliser Teams rôles d’administrateur [pour gérer Teams.](using-admin-roles.md) Pour découvrir comment attribuer des rôles d’administrateur dans Azure Active Directory, voir [Afficher et attribuer des rôles dans Azure Active Directory.](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Pour découvrir comment attribuer des rôles d’Azure Active Directory, voir [Afficher et attribuer des rôles dans Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger fichier .tsv ou .csv ajouter des informations de bâtiment, de site et de client

Vous pouvez ajouter des informations sur le bâtiment, le site et le client à l’analyse des appels par utilisateur en téléchargeant un fichier .csv ou .tsv. Avec toutes ces informations, l’analyse des appels peut ma mail mail les adresses IP aux emplacements physiques. Les administrateurs et les agents du service d’aide peuvent utiliser ces informations pour détecter les tendances des problèmes d’appel. Par exemple, pourquoi les utilisateurs dans le même bâtiment ont-ils des problèmes de qualité d’appel similaires ? 

Si vous êtes un administrateur Teams ou Skype Entreprise, vous pouvez utiliser un client existant et créer un fichier de données à partir du tableau de bord de qualité des appels Teams ou Skype Entreprise. Tout d’abord, vous téléchargez le fichier à partir du DQD, puis vous le chargez dans les données d’analyse des appels. 

- Pour télécharger un fichier de données existant, rendez-vous Microsoft Teams tableau de bord qualité des appels & rapports d’analyse du centre d’administration  >    >    >  **Télécharger maintenant.** Dans la **liste Mes téléchargements,** cliquez **sur Télécharger** en côté du fichier que vous souhaitez. 

- Pour télécharger le nouveau fichier, sélectionnez emplacements du centre **Microsoft Teams,** puis sélectionnez Télécharger d’emplacement ou Remplacer les données  >   **d’emplacement.** 
  
Si vous créez le fichier .tsv ou .csv à partir de zéro, consultez les informations relatives Télécharger [client et à la création.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Voir aussi

[Utiliser les données d’analyse des appels par utilisateur pour résoudre les problèmes de qualité des appels médiocres](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)