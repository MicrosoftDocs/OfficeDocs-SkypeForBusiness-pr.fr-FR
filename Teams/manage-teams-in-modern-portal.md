---
title: Gérer les équipes dans le Centre d’administration Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Découvrez comment afficher ou mettre à jour les équipes que votre organisation a configurées pour la collaboration dans le Centre d’administration Microsoft Teams.
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d99dacdd0580d2ee9eaf775d843c5c46a0960259
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023997"
---
# <a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gérer les équipes dans le Centre d’administration Microsoft Teams

## <a name="overview"></a>Vue d’ensemble

Cet article fournit une vue d’ensemble des outils de gestion pour Teams dans le Centre d’administration Microsoft Teams.

En tant qu’administrateur, vous devrez peut-être afficher ou mettre à jour les équipes que votre organisation a configurées pour la collaboration, ou vous devrez peut-être effectuer des actions de correction telles que l’attribution de propriétaires pour les équipes sans propriétaire. Vous pouvez gérer les équipes utilisées dans votre organisation via le module Microsoft Teams PowerShell et le Centre d’administration Microsoft Teams. Vous pouvez accéder au Centre d’administration sur <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. Pour bénéficier de fonctionnalités d’administration complètes à l’aide de ces deux ensembles d’outils, vous devez vous assurer que l’un des rôles suivants vous est attribué :

- Administrateur général
- Administrateur Teams

Vous pouvez en savoir plus sur les rôles d’administrateur dans Teams dans [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams](using-admin-roles.md), et vous pouvez en savoir plus sur l’utilisation des applets de commande PowerShell pour la gestion des équipes dans les [informations de référence sur les applets de commande Microsoft Teams](/powershell/teams/).

> [!NOTE]
> Les administrateurs de Skype Entreprise Online peuvent gérer à la fois les stratégies des applications **Teams** et **Skype Entreprise Online** à travers PowerShell.

## <a name="teams-overview-grid"></a>Grille de vue d’ensemble de Teams

Les outils de gestion pour les équipes se trouvent sous le nœud **Teams** dans le Centre d’administration Microsoft Teams. (Dans le Centre d’administration, sélectionnez **Teams** > **Gérer les équipes**.) Chaque équipe est soutenue par un groupe Microsoft 365, et ce nœud fournit une vue des groupes qui ont été compatibles avec Microsoft Teams dans votre organisation.

![Capture d’écran de la grille de vue d’ensemble de Teams.](media/manage-teams-in-modern-portal-grid.png)  

La grille affiche les propriétés suivantes :

- **Nom de l’équipe**
- **Canaux** : Nombre de tous les canaux de l’équipe, y compris le canal Général par défaut.
- **Les membres de l’équipe** : Nombre total d’utilisateurs, y compris les propriétaires, les invités et les membres de votre client.
- **Propriétaires** : Nombre de propriétaires pour cette équipe.
- **Invités** : Nombre d’utilisateurs invités B2B Azure Active Directory membres de cette équipe.
- **Privacy** : Visibilité et accès au groupe de sauvegardes Microsoft 365.
- **Status** : État archivé ou actif pour cette équipe. En savoir plus sur l’archivage des équipes dans [Archiver ou restaurer une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **Description** : Description du groupe de sauvegardes Microsoft 365.
- **Classification** : Classification (si elle est utilisée dans votre organisation) affectée au groupe de sauvegardes Microsoft 365. Pour en savoir plus sur les classifications, consultez la page [Créer des classifications pour les groupes Microsoft 365 dans votre organisation](/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell#create-classifications-for-microsoft-365-groups-in-your-organization).
- **GroupID** : l’ID de groupe unique du groupe de sauvegardes Microsoft 365.

> [!NOTE]
> Si vous ne voyez pas toutes ces propriétés dans la grille, cliquez sur l’icône **Modifier les colonnes** . Dans le volet **Modifier les colonnes**, vous pouvez utiliser les boutons bascules pour activer ou désactiver les colonnes de la grille. Lorsque vous avez terminé, cliquez sur **Appliquer**.

### <a name="add"></a>Ajouter

Pour ajouter une nouvelle équipe, cliquez sur **Ajouter**. Dans le volet **Ajouter une nouvelle équipe**, donnez un nom et une description à l’équipe, indiquez si vous souhaitez en faire une équipe privée ou publique, puis définissez la classification.

> [!NOTE]
> Les équipes nouvellement créées peuvent être gérées immédiatement dans le Centre d’administration Teams, contrairement à l’expérience d’autres clients comme Outlook.

### <a name="edit"></a>Modifier

Pour modifier les paramètres spécifiques au groupe et à l’équipe, sélectionnez l’équipe en cliquant à gauche du nom de l’équipe, puis sélectionnez **Modifier**.

### <a name="archive"></a>Archiver

Vous pouvez archiver une équipe. L’archivage d’une équipe place l’équipe en mode lecture seule dans Teams. En tant qu'administrateur, vous pouvez archiver et désarchiver des équipes au nom de votre organisation dans le centre d'administration. 

### <a name="delete"></a>Supprimer

La suppression d’une équipe est une suppression réversible de l’équipe et du groupe Microsoft 365 correspondant. Pour restaurer une équipe supprimée par erreur, suivez les instructions de [Restaurer un groupe supprimé](/microsoft-365/admin/create-groups/restore-deleted-group).

### <a name="search"></a>Rechercher

La recherche prend actuellement en charge la chaîne « Commence par » et effectue une recherche dans le champ **nom de l’équipe**.

## <a name="team-profile"></a>Profil d’équipe

Vous pouvez accéder à la page de profil d’équipe de n’importe quelle équipe à partir de la grille principale de vue d’ensemble des équipes en cliquant sur le nom de l’équipe. La page de profil d’équipe affiche les membres, les propriétaires et les invités qui appartiennent à l’équipe (et le groupe de sauvegardes Microsoft 365), ainsi que les canaux et paramètres de l’équipe. À partir de la page de profil d’équipe, vous pouvez :

- Ajoutez ou supprimez des membres et des propriétaires.
- Ajouter ou supprimer des canaux (notez que vous ne pouvez pas supprimer le canal Général).
- Modifiez les paramètres d’équipe et de groupe.
 
![Capture d'écran d'un exemple de profil d'équipe.](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Apporter des modifications aux équipes

Dans la page de profil de l’équipe, vous pouvez modifier les éléments suivants d’une équipe :

- **Membres** : Ajouter ou supprimer des membres et promouvoir ou rétrograder des propriétaires.
- **Canaux** : Ajoutez de nouveaux canaux et modifiez ou supprimez des canaux existants. N’oubliez pas que vous ne pouvez pas supprimer le canal Général par défaut.
- **Nom de l’équipe**
- **Description**
- **Confidentialité** : Définissez si l’équipe est publique ou privée.
- **Classification** : Elle est sauvegardée par vos classifications de groupe Microsoft 365. Choisissez **confidentiel**, **hautement confidentiel** ou **général**.
- **Paramètres de conversation** : Définissez si les membres peuvent modifier et supprimer des messages envoyés.
- **Paramètres de canaux** : Définissez si les membres peuvent créer des canaux et modifier des canaux existants, et ajouter, modifier et supprimer des onglets, des connecteurs et des applications.

Les modifications que vous apportez à une équipe sont enregistrées. Si vous modifiez les paramètres de groupe (modification du nom, de la description, de la photo, de la confidentialité, de la classification ou des membres de l’équipe), les modifications vous sont attribuées via le pipeline d’audit. Si vous effectuez des actions sur des paramètres spécifiques à Teams, vos modifications sont suivies et attribuées à vous dans le canal Général de l’équipe.

## <a name="troubleshooting"></a>Résolution des problèmes

**Problème : Teams manquant dans la grille de vue d’ensemble de l’équipe**

Certaines de vos équipes sont manquantes dans la liste des équipes dans la grille de vue d’ensemble de Teams.

**Cause** : ce problème se produit lorsque l’équipe a été profilée de façon incorrecte (ou pas encore) par le système, ce qui peut entraîner une propriété manquante pour qu’elle soit reconnue.

**Résolution : Définir manuellement la propriété sur la valeur correcte via MS Graph**

Remplacez **{groupid}** dans la requête pour le GroupId réel en question, que vous pouvez obtenir via Exchange Online PowerShell, par l'applet de commande **«[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup)»**, en tant qu’attribut «**ExternalDirectoryObjectId**».

1. Accéder à [l’Afficheur Graph](https://developer.microsoft.com/graph/graph-explorer).

2. Connectez-vous à l’Afficheur Graph dans le menu de gauche.

3. Remplacez la ligne de requête par : PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.

4. Ajoutez la valeur suivante dans le corps de la demande : {"resourceProvisioningOptions »: ["Team"]}.

5. Exécutez la requête en haut à droite.

6. Vérifiez que l’équipe s’affiche correctement dans le Centre d’administration Microsoft Teams – Vue d’ensemble de l’équipe.

## <a name="learn-more"></a>En savoir plus

- [Informations de référence sur les applets de commande Teams](/powershell/teams/)  
- [Utiliser des rôles d’administrateur Teams pour gérer Teams](using-admin-roles.md).
- [Planifier la gestion du cycle de vie dans Teams](plan-teams-lifecycle.md)
