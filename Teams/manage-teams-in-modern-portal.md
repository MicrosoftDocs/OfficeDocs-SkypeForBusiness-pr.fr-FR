---
title: Gérer les équipes dans le centre Microsoft Teams’administration
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Découvrez comment afficher ou mettre à jour les équipes que votre organisation a définies pour la collaboration dans le Microsoft Teams d’administration.
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
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237540"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gérer les équipes dans le centre Microsoft Teams’administration
==========================================

## <a name="overview"></a>Présentation

Cet article fournit une vue d’ensemble des outils de gestion Teams dans le Microsoft Teams d’administration.

En tant qu’administrateur, vous devrez peut-être afficher ou mettre à jour les équipes que votre organisation a définies pour la collaboration, ou vous devrez peut-être effectuer des actions de correction, telles que l’attribution de propriétaires à des équipes sans propriétaire. Vous pouvez gérer les équipes utilisées dans votre organisation à la fois via le module Microsoft Teams PowerShell et le Microsoft Teams d’administration. Vous pouvez accéder au Centre d’administration à <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> l’adresse . Pour des fonctionnalités d’administration complètes utilisant ces deux jeux d’outils, vous devez vous assurer qu’un des rôles suivants vous est attribué :

- Administrateur général
- Administrateur Teams

Vous pouvez en savoir plus sur les rôles d’administrateur dans Teams dans Utiliser les rôles d’administrateur Microsoft Teams pour gérer [des Teams,](using-admin-roles.md)et en savoir plus sur l’utilisation des cmdlets PowerShell pour la gestion des équipes dans la référence de l’cmdlet [Microsoft Teams.](/powershell/teams/?view=teams-ps)



## <a name="teams-overview-grid"></a>Teams de vue d’ensemble

Les outils de gestion pour les équipes se **Teams** le nœud de gestion dans Microsoft Teams d’administration. (Dans le Centre d’administration, **sélectionnez Teams**  >  **Gérer les équipes**.) Chaque équipe est backed by a Microsoft 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.

![Capture d’écran de la Teams de vue d’ensemble](media/manage-teams-in-modern-portal-grid.png)  

La grille affiche les propriétés suivantes :

- **Nom de l’équipe**
- **Canaux** : un nombre de canaux dans l’équipe, y compris le canal Général par défaut.
- **Membres d’une** équipe : un nombre total d’utilisateurs, y compris les propriétaires, invités et membres de votre client.
- **Propriétaires** : un nombre de propriétaires pour cette équipe.
- **Invités** : nombre d’Azure Active Directory invités B2B qui sont membres de cette équipe.
- **Confidentialité** - Visibilité/Type d’accès du groupe Microsoft 365 de sécurité.
- **État** : état Archivé ou Actif pour cette équipe. En savoir plus sur l’archivage des équipes [dans Archiver ou restaurer une équipe.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)
- **Description** : description du groupe de Microsoft 365.)
- **Classification** : classification (si elle est utilisée dans votre organisation) assignée au groupe Microsoft 365 personnel. Pour plus d’informations sur les [classifications, Office classifications pour les groupes de votre organisation.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GroupID** - GroupID unique du groupe de Microsoft 365 groupe.

> [!NOTE]
> Si vous ne voyez pas toutes ces propriétés dans la grille, cliquez sur **l’icône Modifier les colonnes.** Dans le **volet Modifier les** colonnes, vous pouvez utiliser les boutons bascule pour activer ou désactiver les colonnes dans la grille. Lorsque vous avez terminé, cliquez sur **Appliquer.**

### <a name="add"></a>Ajouter

Pour ajouter une équipe, cliquez sur **Ajouter.** Dans le **volet Ajouter** une nouvelle équipe, donnez un nom et une description à l’équipe, définissez si vous souhaitez en faire une équipe privée ou publique et définissez la classification.

> [!NOTE]
> Les équipes nouvellement créées peuvent être gérées immédiatement dans le Teams d’administration, contrairement à l’expérience d’autres clients tels que Outlook.

### <a name="edit"></a>Modifier

Pour modifier les paramètres des groupes et des équipes, sélectionnez l’équipe en cliquant à gauche du nom de l’équipe, puis sélectionnez **Modifier.**

### <a name="archive"></a>Archivage

Vous pouvez archiver une équipe. L’archivage d’une équipe place l’équipe en mode lecture seule dans Teams. En tant qu’administrateur, vous pouvez archiver et dés archiver des équipes pour le compte de votre organisation dans le Centre d’administration. 

### <a name="delete"></a>Supprimer

La suppression d’une équipe est une suppression (suppression soft) de l’équipe et de la Microsoft 365 groupe. Pour restaurer une équipe supprimée par erreur, suivez les instructions dans [Restaurer un groupe supprimé.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>Rechercher

La recherche prend actuellement en charge la chaîne « Commence par » et recherche dans le champ Nom de **l’équipe.**

## <a name="team-profile"></a>Profil d’équipe

Vous pouvez accéder à la page de profil d’une équipe à partir de la grille de vue d’ensemble principale des équipes en cliquant sur le nom de l’équipe. La page de profil d’équipe affiche les membres, les propriétaires et les invités qui appartiennent à l’équipe (et son groupe Microsoft 365), ainsi que les canaux et paramètres de l’équipe. Dans la page de profil de l’équipe, vous pouvez :

- Ajoutez ou supprimez des membres et des propriétaires.
- Ajouter ou supprimer des canaux (notez que vous ne pouvez pas supprimer le canal Général).
- Modifiez les paramètres des équipes et des groupes.
 
![Capture d’écran d’un exemple de profil d’équipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Apporter des modifications aux équipes

Dans la page de profil de l’équipe, vous pouvez modifier les éléments suivants d’une équipe :

- **Membres :** ajouter ou supprimer des membres et promouvoir ou rétrograder des propriétaires.
- **Canaux** : ajoutez de nouveaux canaux et modifiez ou supprimez des canaux existants. N’oubliez pas que vous ne pouvez pas supprimer le canal Général par défaut.
- **Nom de l’équipe**
- **Description**
- **Confidentialité** : définir si l’équipe est publique ou privée.
- **Classification** : cette classification est backed by your Microsoft 365 group classifications. Sélectionnez **Confidentiel,** **Hautement confidentiel** ou **Général.**
- **Paramètres des conversations** : définir si les membres peuvent modifier et supprimer les messages envoyés.
- **Paramètres des canaux** : définir si les membres peuvent créer et modifier des canaux existants, et ajouter, modifier et supprimer des onglets, des connecteurs et des applications.

Les modifications que vous a apportées à une équipe sont enregistrées. Si vous modifiez les paramètres du groupe (modification du nom, de la description, de la photo, de la confidentialité, de la classification ou des membres d’une équipe), les modifications vous sont attribuées via le pipeline d’audit. Si vous effectuez des actions par rapport Teams paramètres spécifiques, vos modifications sont suivis et vous sont attribuées dans le canal Général de l’équipe.

## <a name="troubleshooting"></a>Résolution des problèmes

**Problème : Teams manquants dans la grille de vue d’ensemble de l’équipe**

Certaines de vos équipes sont manquantes dans la liste des équipes dans la Teams de vue d’ensemble.

**Cause**: ce problème se produit lorsque l’équipe a été profilée de façon incorrecte (ou pas encore) par le système, ce qui peut entraîner une propriété manquante pour qu’elle soit reconnue.

**Résolution : définir manuellement la propriété sur la valeur correcte via MS Graph**

Remplacez **{groupid}** dans la requête pour le GroupId réel en question, que vous pouvez obtenir via la Exchange Online powershell, par l’attribut « **[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** comme attribut **« ExternalDirectoryObjectId**».

1. Accédez [Graph Explorer.](https://developer.microsoft.com/graph/graph-explorer)

2. Connectez-vous Graph explorer dans le menu de gauche.

3. Modifiez la ligne de requête en : PATCH > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.

4. Ajoutez la valeur suivante dans le corps de la demande : {"resourceProvisioningOptions »: ["Team"]}.

5. Exécutez la requête en haut à droite.

6. Confirmez que l’équipe s’affiche correctement dans le Microsoft Teams d’administration - Vue d’ensemble de l’équipe.

## <a name="learn-more"></a>En savoir plus

- [Teams des cmdlet](/powershell/teams/?view=teams-ps)  
- [Utiliser Teams rôles d’administrateur pour gérer les Teams](using-admin-roles.md)
- [Planifier la gestion du cycle de vie dans Teams](plan-teams-lifecycle.md)