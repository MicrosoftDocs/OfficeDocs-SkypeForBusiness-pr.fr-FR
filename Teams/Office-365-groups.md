---
title: Groupes Microsoft 365 et Microsoft teams
ms.reviewer: Kyle Blevins
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: Dans cet article, vous allez découvrir comment utiliser les groupes et appartenances aux groupes Microsoft 365 avec Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4861683d3c46eaa6122ffbac0d2ae17b4f3a7979
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655995"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Groupes Microsoft 365 et Microsoft teams
=====================================

> [!Tip]
> Regardez la session suivante pour découvrir comment les équipes interagissent avec Azure Active Directory (Azure AD), Microsoft 365 Groups, Exchange, SharePoint et OneDrive entreprise : [notions de bases de Microsoft teams](https://aka.ms/teams-foundations)

Microsoft 365 groups est le service d’appartenance à plusieurs applications d’Office 365. Au niveau de base, un groupe Microsoft 365 est un objet dans Azure Active Directory avec une liste de membres et un couplage lâche aux charges de travail associées, y compris un site d’équipe SharePoint, un groupe Yammer, des ressources de boîte aux lettres Exchange partagées, le planificateur, Power BI et OneNote. Vous pouvez ajouter ou supprimer des personnes dans le groupe comme vous le feriez pour n’importe quel autre objet de sécurité en groupe dans Active Directory.

Un administrateur Office 365 peut définir un groupe Microsoft 365, ajouter des membres et bénéficier de fonctionnalités telles qu’une boîte aux lettres partagée Exchange, une bibliothèque de documents SharePoint, un groupe Yammer, etc. Pour plus d’informations sur les groupes Microsoft 365, voir [en savoir plus sur les groupes microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Ne manquez pas les [groupes d’affiches dans Microsoft 365 pour les architectes informatiques](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-microsoft-365-groups-work"></a>Fonctionnement des groupes Microsoft 365
--------------------------

Lorsque vous créez une équipe, sur le système principal, vous créez un groupe Microsoft 365 et la bibliothèque de documents SharePoint associée et un bloc-notes OneNote, ainsi que des liens vers d’autres applications Office 365 Cloud. Si la personne qui crée l’équipe est le propriétaire d’un groupe public ou privé Office 365 existant, elle peut ajouter des fonctionnalités d’équipes au groupe si le nombre de membres du groupe est compris dans les limites spécifiées dans [limites et spécifications pour Microsoft teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) et si le groupe n’a jamais été ajouté à Teams. Cela crée un canal **général** par défaut dans lequel se trouvent les messages de discussion, les documents, OneNote et les autres objets. Le principe d’affichage de la bibliothèque de documents du canal permettra d’afficher le dossier **général** représentant le canal dans l’équipe. Plus important encore, si vous créez votre propre structure de dossiers au sein d’une bibliothèque de documents, **celle-ci n’est pas propagée** aux équipes en tant que canal ; pour l’instant, seules les équipes sont acheminées vers SharePoint.

> [!NOTE]
> Sur la base des commentaires des clients, les nouveaux groupes Microsoft 365 générés suite à la création d’une équipe dans le client Microsoft Teams ne s’afficheront plus dans Outlook par défaut. Pour activer ou désactiver l’affichage des groupes dans Outlook, utilisez l’applet de connexion [Set-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) avec le paramètre **HiddenFromExchangeClientsEnabled** . Les groupes créés via Outlook et les versions ultérieures sont activés pour les équipes continuent à apparaître dans Outlook et Teams. 

> [!NOTE]
> La suppression d’un groupe Microsoft 365 entraîne la suppression de l’alias de boîte aux lettres pour les invitations aux réunions Outlook Le retrait d’une équipe et son impact sur Outlook sont d’environ 20 minutes. La suppression d’une équipe du client teams le supprime immédiatement de l’affichage de tous les membres de l’équipe. Si vous supprimez des membres d’un groupe Microsoft 365 pour lequel la fonctionnalité d’équipe est activée, il peut y avoir un délai d’environ deux heures avant la suppression de l’équipe dans le client teams pour les personnes concernées qui ont été supprimées.
>
>Pour plus d’informations sur la restauration d’un groupe Microsoft 365 que vous avez supprimé, voir [Ceci](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) .

<a name="group-membership"></a>Adhésion à un groupe
----------------

Les fonctionnalités de groupe et les fonctionnalités de vos utilisateurs dépendent de l’emplacement d’appartenance au groupe. Par exemple, si vous supprimez un membre d’une équipe, il est également supprimé du groupe Microsoft 365. La suppression du groupe entraîne la suppression immédiate de l’équipe et des canaux du client Teams. Si vous supprimez un membre d’un groupe à l’aide du centre d’administration Microsoft 365, il n’aura plus accès aux autres aspects de la collaboration tels que la bibliothèque de documents SharePoint Online, le groupe Yammer ou le partage OneNote. Toutefois, ils pourront toujours accéder à la fonctionnalité de conversation de l’équipe pendant environ deux heures.

Pour gérer les membres d’une équipe, vous pouvez ajouter et supprimer des membres du client teams pour vous assurer que le contrôle d’accès en cascade approprié aux autres applications Cloud dépendantes est appliqué. Par ailleurs, vous éviterez une connaissance disconcertée qui laissait des personnes disposant de l’impression d’avoir accès aux ressources qu’elles utilisent (jusqu’à ce que le cycle de synchronisation suivant ajoute ou révoque l’accès à un composant particulier du service). Si vous ajoutez ou supprimez des membres d’une équipe en dehors du client Teams (à l’aide du centre d’administration Microsoft 365, d’Azure AD ou d’Exchange Online PowerShell), il est possible que les modifications soient répercutées dans Teams.

<a name="ability-to-add-group-as-attendee-while-scheduling-meetings"></a>Possibilité d’ajouter un groupe en tant que participant lors de la planification de réunions
----------------------------------------------------------

À compter du 2020, vous pouvez désormais inviter un groupe à une réunion planifiée, en présentant les limitations suivantes :
1. Tous les groupes et équipes Microsoft 365 créés à partir de groupes Microsoft 365 existants pourront être recherchés et pourront être ajoutés à la réunion. Toutefois, les membres recevront l’invitation à la réunion en fonction de leur abonnement au groupe.
2. Les équipes créées de zéro avant le 2018 pourront peut-être effectuer une recherche dans la mesure où les membres ne recevront pas l’invitation à la réunion en raison de leur abonnement par défaut, qui n’est pas la réponse.» Vous pouvez le modifier à partir d’Outlook en modifiant les paramètres du groupe.
3. Les équipes créées à partir de zéro après le 2018 peuvent être recherchées et masquées à l’aide de la propriété « HiddenFromAddressListsEnabled ». Il s’agit d’un paramètre contrôlé par l’administrateur qui peut être modifié par l’administrateur.
