---
title: "Assigner des rôles et des autorisations dans Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: "Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5fb972106200306f64db27a33f16df98e56b8c0
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>Assigner des rôles et des autorisations dans Microsoft Teams
===============================================

Microsoft Teams inclut deux rôles : **Propriétaire** et **Membre**. Par défaut, un utilisateur qui crée une équipe a le statut de Propriétaire. Si une équipe est créée à partir d'un groupe existant Office 365, les autorisations sont héritées.

Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre :

|  |Propriétaire d'équipe  |Membre d'équipe  |
|---------|---------|---------|
|**Créer une équipe**     |Oui        |Non         |
|**Quitter une équipe**     |Oui         |Oui         |
|**Modifier le nom/la description d'une équipe**      |Oui         |Non         |
|**Supprimer une équipe**      |Oui         |Non         |
|**Ajouter un canal**      |Oui         |Oui*         |
|**Modifier le nom/la description d'un canal**      |Oui         |Oui*         |
|**Supprimer un canal**      |Oui         |Oui*         |
|**Ajouter des membres**      |Oui**         |Non         |
|**Ajouter des onglets**      |Oui         |Oui*         |
|**Ajouter des connecteurs**      |Oui         |Oui*         |
|**Ajouter des bots**      |Oui         |Oui*         |
\* Ces éléments peuvent être désactivés par un propriétaire au niveau d'une équipe, auquel cas les membres n'y auront pas accès.

\*\*Après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de Propriétaire. Il est également possible pour un propriétaire de rétrograder son propre statut à celui de membre.



> [!NOTE]
> Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes. Une équipe peut compter 100 propriétaires maximum. Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation. Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Autorisations de créations d'équipes
---------------------------

Par défaut, tous les utilisateurs disposant d'une boîte aux lettres dans Exchange Online disposent d'autorisations de créer des groupes Office 365 et par conséquent une équipe dans Microsoft Teams. Vous pouvez davantage contrôler et limiter la création d'équipes et donc de groupes Office 365 en délégant les droits de gestion et de création de groupes à un ensemble d'utilisateurs.

Si votre organisation est intéressée, les instructions ci-après présentent les tâches requises à cet effet.

1.  Identifiez ou créez un groupe de sécurité (GS) d'utilisateurs qui disposeront d'autorisations déléguées pour créer des groupes Office 365.

    a.  **Action :** Configurez un groupe de sécurité dans Office 365 de manière à ajouter les utilisateurs qui peuvent créer des groupes Office 365.

    b.  Pour plus d'informations, reportez-vous au document [Créer, modifier ou supprimer un groupe de sécurité dans le centre d'administration Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).

2.  Vérifiez que le contrôle au niveau de l'entreprise permettant aux utilisateurs de créer des groupes est activé.

    a.  **Action :** Exécutez le script PowerShell suivant et vérifiez que le paramètre UsersPermissiontoCreateGroupsEnabled est défini sur **True.**

    ```
    Connect-MsolService

    Get-MsolCompanyInformation
    ```

    b.  S'il n'est pas défini sur True, exécutez l'applet de commande Set-MsolCompanySettings **pour le définir sur True**.
Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True

    c. Pour plus d'informations, reportez-vous à la page suivante : [Gérer les utilisateurs qui peuvent créer des groupes Office 365.](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)

3.  Configurez des paramètres de groupe Office 365 pour permettre uniquement au groupe de sécurité identifié disposant d'autorisations de créer des groupes.

    a.  **Action :** Créez un objet de paramètres de groupe contenant les paramètres de configuration du groupe auquel des autorisations déléguées de création de groupes seront affectées. 

    ```
    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "false"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings
    ```

    b. Pour plus d'informations, reportez-vous à la page suivante : [Gérer les utilisateurs qui peuvent créer des groupes Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3).


||||
|---------|---------|---------|
| ![Icône Point de décision.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Point de décision         |Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?         |
| ![Icône Étapes suivantes.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Étapes suivantes         |Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.         |
