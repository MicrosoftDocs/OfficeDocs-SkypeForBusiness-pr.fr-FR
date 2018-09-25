---
title: Gérer les équipes Microsoft Teams et Skype entreprise centre d’administration
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Découvrez comment afficher ou mettre à jour vos équipes Microsoft Teams et Skype entreprise centre d’administration.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dbfddf2f9cfba12943b8b2e18326de1877e1de3
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018822"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>Gérer les équipes Microsoft Teams et Skype entreprise centre d’administration
==========================================

## <a name="overview"></a>Vue d’ensemble

En tant qu’un administrateur informatique, vous devrez peut-être afficher ou mettre à jour les équipes de votre organisation a configuré pour la collaboration, ou vous devrez effectuer des actions telles que l’affectation de propriétaires pour les équipes ownerless correction. Vous pouvez gérer les équipes utilisés dans votre organisation via le module PowerShell d’équipes Microsoft et les Microsoft Teams & Skype entreprise centre d’administration. Pour les fonctionnalités d’administration complète à l’aide de ces deux ensembles d’outils, assurez-vous que vous sont affectés à un des rôles suivants :

- Administrateur global
- Administrateur de Service des équipes

Vous en apprendrez plus sur les rôles d’administrateur dans Microsoft Teams [ici](using-admin-roles.md), et vous pouvez en savoir plus sur la façon d’utiliser les applets de commande PowerShell pour la gestion des équipes dans la [référence d’applet de commande équipes Microsoft](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).  

Cet article fournit une vue d’ensemble des outils de gestion pour les équipes Microsoft Teams et Skype entreprise centre d’administration.

## <a name="teams-overview-grid"></a>Vue d’ensemble des équipes

Outils de gestion pour les équipes sont sous le nœud **équipes** Microsoft Teams et Skype entreprise centre d’administration. (Dans le centre d’administration, sélectionnez **les équipes** > **Gérer les équipes**.) Chaque équipe bénéficie d’un groupe d’Office 365, et ce nœud fournit un affichage de tous les groupes qui ont été Microsoft équipes activées dans votre organisation.

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
- **Photo de l’équipe**
- **Confidentialité de l’équipe** - public ou privé
- **Classement de l’équipe** - soutenues par vos classifications de groupe Office 365
- **Paramètres du membre d’équipe** - paramètres du membre d’équipe select


Les modifications que vous apportez à une équipe sont consignées. Si vous modifiez les paramètres de groupe (modifier le nom, description, photo, confidentialité, classement ou membres de l’équipe), ces modifications à attribuer à votre via le pipeline d’audit. Si vous effectuez des actions sur les paramètres spécifiques d’équipes, vos modifications seront suivies et attribuer aux vous dans le canal généraux de l’équipe.


## <a name="learn-more"></a>En savoir plus

[Référence d’applet de commande Microsoft Teams](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[Rôles d’administrateur dans Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

