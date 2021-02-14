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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurer l’analyse des appels par utilisateur pour identifier et résoudre les problèmes de qualité des appels dans Microsoft Teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581105"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurer l’analyse des appels pour Microsoft Teams

En tant qu’administrateur Microsoft Teams, vous pouvez utiliser l’analyse des appels par utilisateur pour résoudre les problèmes de qualité et de connexion des appels Teams pour **les utilisateurs individuels.** Pour tirer pleinement parti de l’analyse des appels, définissez les informations suivantes :
  
- Attribuez des rôles de support spécialisés aux personnes, telles que les agents du support technique, pour leur permettre d’afficher les données d’analyse des appels pour les utilisateurs. Ces rôles de support ne peuvent pas accéder au reste du Centre d’administration Teams. 
    
- Ajoutez des informations sur le bâtiment, le site et le client à l’analyse des appels par utilisateur en téléchargeant un fichier de données .tsv ou .csv.
    
Lorsque vous êtes prêt à utiliser l’analyse des appels par utilisateur, lisez Utiliser l’analyse des appels par utilisateur pour résoudre les problèmes de qualité [des appels.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Accorder l’autorisation au personnel de support et au support technique

En tant qu’administrateur Teams, vous avez un accès complet aux informations d’analyse des appels pour tous les utilisateurs. Nous avons créé des rôles Azure Active Directory spécialisés que vous pouvez affecter au personnel de support et aux agents du support technique afin qu’ils accèdent également à l’analyse des appels par utilisateur (sans avoir accès au reste du Centre d’administration Teams). Affectez le rôle de spécialiste du support des **communications Teams** aux utilisateurs qui doivent avoir une vue limitée de l’analyse des appels par utilisateur (support de niveau 1). Affectez le rôle d’ingénieur **du support des communications Teams** aux utilisateurs qui ont besoin d’un accès total à l’analyse des appels par utilisateur (support de niveau 2). Aucun rôle n’a accès au reste du Centre d’administration Teams.

Pour savoir ce que fait chacun de ces rôles, lisez ce que [fait chaque rôle du support teams](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Pour plus d’informations sur les rôles d’administrateur Teams, voir [Utiliser les rôles d’administrateur Teams pour gérer Teams.](using-admin-roles.md) Pour découvrir comment attribuer des rôles d’administrateur dans Azure Active Directory, voir Afficher et attribuer des [rôles dans Azure Active Directory.](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Pour découvrir comment attribuer des rôles d’administrateur dans Azure Active Directory, voir Afficher et attribuer des [rôles dans Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Télécharger un fichier .tsv ou .csv pour ajouter des informations sur le bâtiment, le site et le client

Vous pouvez ajouter des informations sur le bâtiment, le site et le client à l’analyse des appels par utilisateur en téléchargeant un fichier .csv ou .tsv. Avec toutes ces informations, l’analyse des appels peut ma mail mail les adresses IP aux emplacements physiques. Les administrateurs et les agents du service d’aide peuvent utiliser ces informations pour détecter les tendances des problèmes d’appel. Par exemple, pourquoi les utilisateurs dans le même bâtiment ont-ils des problèmes de qualité d’appel similaires ? 

Si vous êtes administrateur de Teams ou de Skype Entreprise, vous pouvez utiliser un client existant et créer un fichier de données à partir du tableau de bord de qualité des appels de Teams ou de Skype Entreprise. Tout d’abord, vous téléchargez le fichier à partir du CQD, puis vous le chargez dans les données d’analyse des appels. 

- Pour télécharger un fichier de données existant, allez au Centre d’administration **Microsoft Teams**- Télécharger le tableau de bord de qualité  >    >  **des appels maintenant.** Dans la **liste Mes téléchargements,** cliquez **sur Télécharger** en côté du fichier que vous souhaitez. 

- Pour télécharger le nouveau fichier, sélectionnez Emplacements du centre d’administration **Microsoft Teams,** puis sélectionnez Télécharger les données d’emplacement  >  ou Remplacer les données **d’emplacement.** 
  
Si vous créez le fichier .tsv ou .csv de toutes pièces, voir Télécharger les données du client et [du bâtiment.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Sujets associés

[Utiliser les données d’analyse des appels par utilisateur pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
