---
title: Gérer teams dans le centre d’administration Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Découvrez comment afficher ou mettre à jour les équipes que votre organisation a configurées pour la collaboration dans le centre d’administration Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c83d985a277c8341565e44878ba03385e23a358
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904996"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gérer teams dans le centre d’administration Microsoft teams
==========================================

## <a name="overview"></a>Vue d’ensemble

Cet article fournit une vue d’ensemble des outils de gestion pour teams dans le centre d’administration Microsoft Teams.

En tant qu’administrateur, il est possible que vous deviez afficher ou mettre à jour les équipes que votre organisation a configurées pour la collaboration, ou vous devrez peut-être effectuer des actions de correction, comme affecter des propriétaires à des équipes propriétaires. Vous pouvez gérer les équipes utilisées dans votre organisation via le module Microsoft teams PowerShell et le centre d’administration Microsoft Teams. Pour pouvoir bénéficier d’une administration complète de ces deux ensembles d’outils, assurez-vous que vous disposez de l’un des rôles suivants :

- Administrateur général
- Administrateur du service Teams

Pour en savoir plus sur les rôles d’administrateur dans équipes, [Utilisez les rôles d’administrateur de Microsoft teams pour gérer teams](using-admin-roles.md), et apprenez-en davantage sur l’utilisation des cmdlets PowerShell pour la gestion des équipes dans la [référence des cmdlets de Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).



## <a name="teams-overview-grid"></a>Grille de vue d’ensemble des équipes

Les outils de gestion pour teams se trouvent sous le nœud **équipes** dans le centre d’administration Microsoft Teams. (Dans le centre d’administration, sélectionnez **équipes** > **gérer les équipes**.) Chaque équipe est stockée par un groupe Office 365 et ce nœud fournit une vue des groupes qui ont été activés par Microsoft teams au sein de votre organisation.

![Capture d’écran de la grille de vue d’ensemble de teams](media/manage-teams-in-modern-portal-grid.png)  

La grille affiche les propriétés suivantes :

- **Nom de l’équipe**
- **Canaux** : nombre de canaux de l’équipe, y compris le canal général par défaut.
- **Membres** d’une équipe : nombre total d’utilisateurs, y compris les propriétaires, invités et membres de votre client.
- **Propriétaires** -nombre de propriétaires pour cette équipe.
- **Invités** -nombre d’utilisateurs invités d’Azure Active Directory B2B membres de cette équipe.
- **Protection de la vie privée** -le groupe de AccessTypes 365 Office.
- **État** : le statut archivé ou actif de cette équipe. En savoir plus sur l’archivage d’équipes dans l' [archivage ou la restauration d’une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **Description** : description du groupe de stockage 365.
- **Classification** : classification (si utilisée au sein de votre organisation) affectée au groupe Office 365 de stockage. Pour plus d’informations sur [les catégories, voir créer des classifications pour les groupes Office au sein de votre organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **GroupID** -le GroupID unique du groupe Office 365 de stockage.

> [!NOTE]
> Si vous ne voyez pas ces propriétés dans la grille, cliquez sur l’icône **modifier les colonnes** . Dans le volet **modifier les colonnes** , vous pouvez utiliser les boutons bascule pour activer ou désactiver les colonnes dans la grille. Lorsque vous avez terminé, cliquez sur **appliquer**.

### <a name="add"></a>Ajoutée

Pour ajouter une nouvelle équipe, cliquez sur **Ajouter**. Dans le volet **Ajouter une nouvelle équipe** , attribuez un nom et une description à l’équipe, définissez si vous souhaitez la définir comme une équipe privée ou publique et définir la classification.

### <a name="edit"></a>Validation

Pour modifier les paramètres spécifiques d’une équipe ou d’un groupe, sélectionnez l’équipe en cliquant à gauche du nom de l’équipe, puis sélectionnez **modifier**.

### <a name="archive"></a>Archivage

Vous pouvez archiver une équipe. L’archivage d’une équipe place l’équipe en mode lecture seule dans Teams. En tant qu’administrateur, vous pouvez archiver et désinstaller des équipes au nom de votre organisation dans le centre d’administration. 

### <a name="delete"></a>Annuler

La suppression d’une équipe consiste à supprimer de l’équipe et au groupe Office 365 correspondant. Pour restaurer une équipe supprimée par erreur, suivez les instructions de la procédure de [restauration d’un groupe Office 365 supprimé](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).

### <a name="search"></a>Rechercher

La recherche prend actuellement en charge la chaîne « commence par » et recherche le champ nom de l' **équipe** .

## <a name="team-profile"></a>Profil d’équipe

Vous pouvez accéder à la page de profil d’équipe de n’importe quelle équipe à partir de la grille de vue d’ensemble des équipes en cliquant sur le nom de l’équipe. La page de profil de l’équipe montre les membres, les propriétaires et les invités qui appartiennent à l’équipe (et à son groupe Office 365), ainsi que les canaux et les paramètres de l’équipe. À partir de la page de profil d’équipe, vous pouvez :

- Ajoutez ou supprimez des membres et des propriétaires.
- Ajoutez ou supprimez des canaux (Notez que vous ne pouvez pas supprimer le canal général).
- Modifiez les paramètres d’équipe et de groupe.
 
![Capture d’écran d’un exemple de profil d’équipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Modification d’équipes

Dans la page de profil de l’équipe, vous pouvez modifier les éléments suivants d’une équipe :

- **Membres** : ajoutez ou supprimez des membres et promouvez ou abaissez les propriétaires.
- **Canaux** : ajoutez de nouveaux canaux, puis modifiez ou supprimez des canaux existants. N’oubliez pas que vous ne pouvez pas supprimer le canal général par défaut.
- **Nom de l’équipe**
- **Description**
- **Confidentialité** : définissez si l’équipe est publique ou privée.
- **Classification** : cette catégorie est stockée par vos classifications de groupes Office 365. Sélectionnez **confidentiel**, **hautement confidentiel**ou **général**.
- **Paramètres des conversations** : définir si les membres peuvent modifier et supprimer les messages envoyés.
- **Paramètres des canaux** : définir si les membres peuvent créer de nouveaux canaux et modifier les canaux existants, et ajouter, modifier et supprimer des onglets, des connecteurs et des applications.

Les modifications que vous apportez à une équipe sont enregistrées. Si vous modifiez les paramètres de groupe (en modifiant le nom, la description, la photo, la confidentialité, la classification ou les membres d’une équipe), les modifications vous sont attribuées via le pipeline d’audit. Si vous effectuez des actions sur des paramètres spécifiques aux équipes, vos modifications sont suivies et attribuées dans le canal général de l’équipe.

## <a name="troubleshooting"></a>Résolution des problèmes

**Problème : les équipes n’apparaissent pas dans la grille de vue d’ensemble de l’équipe**

Certaines de vos équipes ne figurent pas dans la liste des équipes de la grille de vue d’ensemble de teams.

**Cause**: ce problème se produit lorsque l’équipe a été incorrectement (ou pas encore) profilée par le système qui peut entraîner une propriété manquante pour qu’elle soit reconnue.

**Résolution : définissez manuellement la propriété sur la valeur correcte via MS Graph.**

Remplacez **{GroupID}** dans la requête pour le GroupID réel en question, que vous pouvez obtenir par le biais d’Exchange Online PowerShell avec l’applet de requête **«[Get-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , qui est l’attribut «**ExternalDirectoryObjectId**».

1. [Explorateur de graphiques](https://developer.microsoft.com/graph/graph-explorer)Access.

2. Connectez-vous à l’Explorateur de graphiques dans le menu de gauche.

3. Modifiez la ligne de requête en : PATCH > > https://graph.microsoft.com/v1.0/groups/{groupid}.

4. Ajoutez la valeur suivante dans le corps de la requête : {"resourceProvisioningOptions" : ["équipe"]}.

5. Exécuter la requête en haut à droite.

6. Confirmez que l’équipe apparaît correctement dans le centre d’administration Microsoft teams-présentation de l’équipe.

## <a name="learn-more"></a>En savoir plus

- [Référence sur les applets de fonction teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [Utiliser les rôles d’administrateur d’équipes pour gérer teams](using-admin-roles.md)
- [Planifier la gestion du cycle de vie dans Teams](plan-teams-lifecycle.md)
