---
title: Configurer l’analyse des appels pour les Microsoft Teams
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
description: Configurer l’analyse des appels par utilisateur afin d’identifier et de résoudre Microsoft Teams problèmes de qualité des appels.
ms.openlocfilehash: be93a24f7d18e5b347c6375622ca47c3bdaeae26
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556475"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurer l’analyse des appels pour les Microsoft Teams

En tant qu Microsoft Teams d’utilisateurs, vous pouvez utiliser l’analyse des appels par utilisateur pour résoudre les Teams de qualité et de connexion des utilisateurs **individuels**. Pour tirer pleinement parti de l’analyse des appels, définissez les informations suivantes :
  
- Attribuez des rôles de support spécialisés aux personnes, telles que les agents du support technique, pour leur permettre d’afficher les données d’analyse des appels pour les utilisateurs. Ces rôles de support ne peuvent pas accéder au reste du Centre d’Teams’administration. 
    
- Ajoutez des informations sur le bâtiment, le site et le client à l’analyse des appels en téléchargeant un fichier de données .tsv ou .csv utilisateur.
    
Lorsque vous êtes prêt à utiliser l’analyse des appels par utilisateur, lisez Utiliser l’analyse des appels par utilisateur pour résoudre les problèmes de [qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Accorder l’autorisation au personnel de support et au support technique

En tant qu Teams administrateur de services, vous avez un accès complet aux informations d’analyse des appels pour tous les utilisateurs. Nous avons créé des rôles de Azure Active Directory spécialisés que vous pouvez affecter au personnel de support et aux agents du support technique pour leur permettre également d’accéder aux analyses des appels par utilisateur (sans avoir accès au reste du Centre d’administration Teams). Affectez le **rôle Teams du support aux communications** aux utilisateurs qui doivent avoir un affichage limité de l’analyse des appels par utilisateur (support de niveau 1). Attribuez le **rôle Teams support aux communications** aux utilisateurs qui ont besoin d’un accès total à l’analyse des appels par utilisateur (support de niveau 2). Aucun de ces rôles n’a accès au reste Teams centre d’administration.

Pour savoir ce que font chacun de ces rôles, lisez ce que Teams [rôle support fait-il](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do) ?

Pour plus d’informations sur Teams rôles d’administrateur, voir Utiliser Teams rôles d’administrateur [pour gérer Teams](using-admin-roles.md). Pour découvrir comment attribuer des rôles d’administrateur dans Azure Active Directory, voir [Afficher et attribuer des rôles dans Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Pour découvrir comment attribuer des rôles d’Azure Active Directory, voir [Afficher et attribuer des rôles dans Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger fichier .tsv ou .csv ajouter des informations de bâtiment, de site et de client

Vous pouvez ajouter des informations sur le bâtiment, le site et le client à l’analyse des appels par utilisateur en téléchargeant un fichier .csv ou .tsv. Avec toutes ces informations, l’analyse des appels peut ma mail mail les adresses IP aux emplacements physiques. Les administrateurs et les agents du service d’aide peuvent utiliser ces informations pour détecter les tendances des problèmes d’appel. Par exemple, pourquoi les utilisateurs dans le même bâtiment ont-ils des problèmes de qualité d’appel similaires ? 

Si vous êtes un administrateur Teams ou Skype Entreprise, vous pouvez utiliser un client existant et créer un fichier de données à partir du tableau de bord de qualité des appels Teams ou Skype Entreprise. Tout d’abord, vous téléchargez le fichier à partir du CQD, puis vous le chargez dans les données d’analyse des appels. 

- Pour télécharger un fichier de données existant,  >  rendez-vous Microsoft Teams centre d’administrationAnalytics **& ReportsCall** >  **Quality Dashboard** >  **Télécharger maintenant**. Dans la **liste Mes téléchargements** , cliquez **sur Télécharger** en côté du fichier que vous souhaitez. 

- Pour télécharger le nouveau fichier, voir Ajouter [et mettre à jour les étiquettes de rapports](/microsoftteams/learn-more-about-site-upload).
  
Si vous créez le fichier .tsv ou .csv à partir de zéro, consultez les informations relatives Télécharger [client et à la création](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Sujets associés

[Utiliser les données d’analyse des appels par utilisateur pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
