---
title: Gérer les équipes dans le & Microsoft Teams Skype entreprise centre d’administration
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Découvrez comment afficher ou mettre à jour vos équipes dans le & Microsoft Teams Skype entreprise centre d’administration.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 210824858d953a99844817b3ef27265626d91928
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562782"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>Gérer les équipes dans le & Microsoft Teams Skype entreprise centre d’administration
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>Vue d’ensemble

En tant qu’un administrateur informatique, vous devrez peut-être afficher ou mettre à jour les équipes de votre organisation a configuré pour la collaboration, ou vous devrez effectuer des actions telles que l’affectation de propriétaires pour les équipes ownerless correction. Vous pouvez gérer les équipes utilisés dans votre organisation via le module PowerShell d’équipes Microsoft et la & Microsoft Teams Skype entreprise centre d’administration. Pour les fonctionnalités d’administration complète à l’aide de ces deux ensembles d’outils, assurez-vous que vous sont affectés à un des rôles suivants :

- Administrateur global
- Administrateur du service Teams

Vous devez également vous assurer que votre compte a été attribué une licence d’équipes non-version d’évaluation pour la gestion. Dans le cadre d’un problème connu, vous devez vous assurer que votre compte qu' **un** administrateur rôle a été attribué.  Vous en apprendrez plus sur les rôles d’administrateur dans Microsoft Teams dans [utiliser des équipes Microsoft des rôles d’administration pour gérer des équipes](using-admin-roles.md), et vous pouvez en savoir plus sur la façon d’utiliser les applets de commande PowerShell pour la gestion des équipes dans la [référence d’applet de commande équipes Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

Cet article fournit une vue d’ensemble des outils de gestion des équipes dans le & Microsoft Teams Skype entreprise centre d’administration.

## <a name="teams-overview-grid"></a>Vue d’ensemble des équipes

Outils de gestion pour les équipes sont sous le nœud **d’équipes** dans le & Microsoft Teams Skype entreprise centre d’administration. (Dans le centre d’administration, sélectionnez **les équipes** > **Gérer les équipes**.) Chaque équipe bénéficie d’un groupe d’Office 365, et ce nœud fournit une vue des groupes qui ont été Microsoft équipes activées dans votre organisation.

> [!NOTE]
> Est en cours de renvoi créé précédemment équipes pour vous assurer qu’ils s’affichent dans cette vue.

![Vue d’ensemble des équipes](media/manage-teams-in-modern-portal-image1.png)  

La grille affiche les propriétés suivantes :

- **Nom de l'équipe**
- **Canaux** - un décompte de tous les canaux de l’équipe, y compris le canal général par défaut.
- **Utilisateurs** : nombre d’utilisateurs au total, y compris les propriétaires, les invités et membres de votre client.
- **Propriétaires** - nombre de propriétaires pour cette association.
- **Les invités** - un décompte d’Azure Active Directory B2B invité utilisateurs sont membres de cette association.
- **Confidentialité** - le AccessType du groupe sauvegarde Office 365.

### <a name="search"></a>Recherche

Recherche actuellement prend en charge la chaîne « Commence par » et recherche dans le champ **nom de l’équipe** .

### <a name="edit"></a>Modifier

Vous pouvez modifier les paramètres de groupe et spécifiques à l’équipe en sélectionnant une équipe à partir de la grille, puis cliquez sur le bouton **Modifier** .

![Modifier l’équipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Profil de l’équipe

Vous pouvez naviguer vers la page de profil de l’équipe de toute l’équipe à partir de la grille de vue d’ensemble des équipes principale en cliquant sur le nom de l’équipe. La page de profil de l’équipe affiche les membres, les propriétaires et les invités qui appartiennent à l’équipe (et sa sauvegarde O365 groupe), ainsi que les canaux et les paramètres de l’équipe. Dans la page de profil de l’équipe, vous pouvez :

- Ajouter ou supprimer des membres et propriétaires.
- Ajouter ou supprimer des canaux (Notez que vous ne pouvez pas supprimer le canal général).
- Mettre à jour de l’équipe et les paramètres de groupe.
 
![Profil de l’équipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Apporter des modifications aux équipes

Vous pouvez modifier les éléments d’une équipe suivants :
- **Les utilisateurs de l’équipe** : vous pouvez ajouter ou supprimer des membres et promouvoir ou rétrograder des propriétaires de
- **Canaux** - vous pouvez ajouter de nouvelles voies ou supprimer des canaux existants.  Vous ne pouvez pas supprimer le canal « General » par défaut, une fois créée, vous ne pouvez modifier que le nom de canal, pas de description.
- **Nom de l'équipe**
- **Description de l’équipe**
- **Confidentialité de l’équipe** - public ou privé
- **Classement de l’équipe** - soutenues par vos classifications de groupe Office 365
- **Paramètres du membre d’équipe** - paramètres du membre d’équipe select


Les modifications que vous apportez à une équipe sont consignées. Si vous modifiez les paramètres de groupe (modifier le nom, description, photo, confidentialité, classement ou membres de l’équipe), ces modifications à attribuer à votre via le pipeline d’audit. Si vous effectuez des actions sur les paramètres spécifiques d’équipes, vos modifications seront suivies et attribuer aux vous dans le canal généraux de l’équipe.

## <a name="troubleshooting"></a>Résolution des problèmes

**Problème : Les équipes manquantes dans la grille de vue d’ensemble de l’équipe**

Lorsque vous entrez les & Microsoft Teams Skype entreprise centre d’administration, sous l’option **équipes** manque certains de vos équipes à partir de la liste dans la vue d’ensemble des équipes.

**Cause**: ce problème se produit lorsque l’équipe a été incorrectement (ou non) de profilage par le système qui peut entraîner une propriété manquante pour qu’il puisse être reconnu.

**Solution : Définissez manuellement la propriété à la valeur correcte via MS Graph**

Remplacez **{groupid}** dans la requête de GroupId réel en question, que vous pouvez obtenir via le Exchange Online powershell, l’applet de commande **«[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)»** , en tant que l’attribut «**ExternalDirectoryObjectId**».

1. Accès [graphique Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. Se connecter à l’Explorateur de graphique dans le menu de gauche

3. Modifiez la ligne de requête : correctif > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. Ajoutez la valeur suivante dans le corps de la demande : {« resourceProvisioningOptions » : [« Team »]}

5. Exécutez la requête sur le coin supérieur droit.

6. Vérifiez que l’équipe s’affiche correctement sur la & Microsoft Teams Skype pour Business Admin Center - vue d’ensemble de l’équipe


## <a name="learn-more"></a>En savoir plus

[Référence d’applet de commande Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Rôles d’administrateur dans Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

