---
title: Gérer teams dans le centre d’administration Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin
description: Découvrez comment afficher ou mettre à jour vos équipes dans le centre d’administration Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f495a9cc5b3bfb1fd270e85b2a1fb17bd5f11e68
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233351"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gérer teams dans le centre d’administration Microsoft teams
==========================================


## <a name="overview"></a>Vue d’ensemble

En tant qu’administrateur informatique, il est possible que vous deviez afficher ou mettre à jour les équipes que votre organisation a configurées pour la collaboration, ou vous devrez peut-être effectuer des actions de correction telles que l’affectation de propriétaires à des équipes propriétaires. Vous pouvez gérer les équipes utilisées dans votre organisation via le module Microsoft teams PowerShell et le centre d’administration Microsoft Teams. Pour pouvoir bénéficier d’une administration complète de ces deux ensembles d’outils, assurez-vous que vous disposez de l’un des rôles suivants:

- Administrateur général
- Administrateur du service Teams

Pour en savoir plus sur les rôles d’administrateur dans équipes, [Utilisez les rôles d’administrateur de Microsoft teams pour gérer teams](using-admin-roles.md), et apprenez-en davantage sur l’utilisation des cmdlets PowerShell pour la gestion des équipes dans la référence des cmdlets de [Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

Cet article fournit une vue d’ensemble des outils de gestion pour teams dans le centre d’administration Microsoft Teams.

## <a name="teams-overview-grid"></a>Grille de vue d’ensemble des équipes

Les outils de gestion pour teams se trouvent sous le nœud **équipes** dans le centre d’administration Microsoft Teams. (Dans le centre d’administration, sélectionnez **équipes** > **gérer les équipes**.) Chaque équipe est stockée par un groupe Office 365 et ce nœud fournit une vue des groupes qui ont été activés par Microsoft teams au sein de votre organisation.

![Capture d’écran de la grille de vue d’ensemble de teams](media/manage-teams-in-modern-portal-image1.png)  

La grille affiche les propriétés suivantes:

- **Nom de l’équipe**
- **Canaux** : nombre de canaux de l’équipe, y compris le canal général par défaut.
- **Utilisateurs** : nombre total d’utilisateurs, y compris les propriétaires, invités et membres de votre client.
- **Propriétaires** -nombre de propriétaires pour cette équipe.
- **Invités** -nombre d’utilisateurs invités d’Azure Active Directory B2B membres de cette équipe.
- **Protection de la vie privée** -le groupe de AccessTypes 365 Office.
- **État** : le statut archivé ou actif de cette équipe.  En savoir plus sur l’archivage d’équipes dans l' [archivage ou la restauration d’une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **GroupID** -le GroupID unique du groupe Office 365 de stockage
- **Classification** : classification (si utilisée au sein de votre organisation) affectée au groupe Office 365 de stockage.  Pour plus d’informations sur [les catégories, voir créer des classifications pour les groupes Office au sein de votre organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **Description** -la description définie pour le groupe de 365 Office

### <a name="search"></a>Rechercher

La recherche prend actuellement en charge la chaîne «commence par» et recherche le champ nom de l' **équipe** .

### <a name="edit"></a>Validation

Vous pouvez modifier les paramètres spécifiques d’une équipe ou d’un groupe en sélectionnant une équipe dans la grille, puis en cliquant sur le bouton **modifier** .

![Capture d’écran des options de modification d’équipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Profil d’équipe

Vous pouvez accéder à la page de profil d’équipe de n’importe quelle équipe à partir de la grille de vue d’ensemble des équipes en cliquant sur le nom de l’équipe. La page de profil d’équipe montre les membres, les propriétaires et les invités qui appartiennent à l’équipe (et à son groupe O365 de stockage), ainsi que les canaux et les paramètres de l’équipe. À partir de la page de profil d’équipe, vous pouvez:

- Ajoutez ou supprimez des membres et des propriétaires.
- Ajoutez ou supprimez des canaux (Notez que vous ne pouvez pas supprimer le canal général).
- Mettez à jour les paramètres d’équipe et de groupe.
 
![Capture d’écran d’un exemple de profil d’équipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Modification d’équipes

Vous pouvez modifier les éléments suivants d’une équipe:
- **Utilisateurs au sein de l’équipe** : vous pouvez ajouter ou supprimer des membres, et promouvoir ou abaisser des propriétaires.
- **Canaux** : vous pouvez ajouter de nouveaux canaux ou supprimer des canaux existants.  Vous ne pouvez pas supprimer le canal «général» par défaut, et une fois créé, vous pouvez uniquement modifier le nom d’un canal, et non une description.
- **Nom de l’équipe**
- **Description de l’équipe**
- **Confidentialité** de l’équipe-public ou privé
- **Classification d’équipe** -par vos classifications de groupe Office 365
- **Paramètres des membres** de l’équipe-sélectionner les paramètres des membres de l’équipe

## <a name="other-supported-changes-to-teams"></a>Autres modifications prises en charge dans teams

- **Supprimer** : la suppression d’une équipe consiste à supprimer par le biais d’une équipe et d’un groupe Office 365 correspondant.  Pour restaurer une équipe supprimée par erreur, suivez les instructions de la procédure de [restauration d’un groupe Office 365 supprimé](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).
- **Archive** -archivage une équipe place l’équipe en mode lecture seule dans Microsoft Teams.  En tant qu’administrateur, vous pouvez archiver et désarchiver des équipes au nom de votre organisation via le portail d’administration.


Les modifications que vous apportez à une équipe sont enregistrées. Si vous modifiez les paramètres de groupe (en modifiant le nom, la description, la photo, la confidentialité, la classification ou les membres d’une équipe), ces modifications vous seront attribuées par le biais du pipeline d’audit. Si vous effectuez des actions sur des paramètres spécifiques aux équipes, vos modifications sont suivies et attribuées dans le canal général de l’équipe.

## <a name="troubleshooting"></a>Résolution des problèmes

**Problème: les équipes n’apparaissent pas dans la grille de vue d’ensemble de l’équipe**

Lorsque vous entrez dans le centre d’administration de Microsoft Teams, certaines de vos équipes ne figurent pas dans la liste de la grille de vue d’ensemble de teams. ****

**Cause**: ce problème se produit lorsque l’équipe a été incorrectement (ou pas encore) profilée par le système qui peut entraîner une propriété manquante pour qu’elle soit reconnue.

**Résolution: définissez manuellement la propriété sur la valeur correcte via MS Graph.**

Remplacez **{GroupID}** dans la requête pour le GroupID réel en question, que vous pouvez obtenir par le biais d’Exchange Online PowerShell avec l’applet de requête **«[Get-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , qui est l’attribut «**ExternalDirectoryObjectId**».

1. [Explorateur de graphiques](https://developer.microsoft.com/en-us/graph/graph-explorer) Access

2. Se connecter à l’Explorateur de graphiques dans le menu de gauche

3. Changer la ligne de requête en: correctif > version 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. Ajoutez la valeur suivante dans le corps de la requête: {"resourceProvisioningOptions": ["équipe"]}

5. Exécuter la requête en haut à droite.

6. Confirmez que l’équipe apparaît correctement dans le centre d’administration Microsoft teams-présentation de l’équipe


## <a name="learn-more"></a>En savoir plus

[Référence sur les applets de passe Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Rôles d’administrateur dans Microsoft teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

