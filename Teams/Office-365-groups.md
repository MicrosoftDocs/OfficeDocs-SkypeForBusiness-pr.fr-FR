---
title: Groupes d’Office 365 et les équipes Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: article
ms.service: msteams
description: Découvrez comment utiliser Groupes Office 365 et les adhésions de groupe avec Microsoft Teams.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9d7c37a0aa53f45036388bdedfc5bdc87b1cc8a
ms.sourcegitcommit: 5fb3957b658b48edf3d9878a9d53a4002b8f55d8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520061"
---
<a name="office-365-groups-and-microsoft-teams"></a>Groupes d’Office 365 et les équipes Microsoft
=====================================

Groupes d’Office 365 est le service d’appartenance entre les applications dans Office 365. Au niveau de la base, un groupe d’Office 365 est un objet dans Azure Active Directory avec une liste des membres et un couplage faible pour un site d’équipe SharePoint, groupe Yammer, y compris les charges de travail associées partagé des ressources de boîte aux lettres Exchange, Planificateur, PowerBI et OneNote. Vous pouvez ajouter ou supprimer des personnes au groupe comme vous le feriez pour n’importe quel autre objet basée sur le groupe de sécurité dans Active Directory.

Un administrateur Office 365 peut définir un groupe d’Office 365, ajouter des membres et tirer parti des fonctionnalités telles que l’échange partagés boîte aux lettres, bibliothèque de documents SharePoint, groupe Yammer et ainsi de suite. Pour plus d’informations sur les groupes d’Office 365, visitez : [en savoir plus sur les groupes d’Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Comment fonctionnent les groupes d’Office 365
--------------------------

Lorsque vous créez un Team Microsoft, sur le serveur principal, vous créez un groupe d’Office 365 et associé à une bibliothèque de documents SharePoint et bloc-notes OneNote, ainsi que des liens vers d’autres applications de nuage Office 365. Si la personne qui a créé l’équipe est un propriétaire d’un existant Office 365 Public ou privé groupe, ils peuvent ajouter des fonctionnalités d’équipes au groupe. Cette opération crée un canal **Général** par défaut de conversation qui résident les messages, documents, OneNote et autres objets. Affichage de la bibliothèque de documents pour le canal révélera le dossier **Général** représentant le canal de l’équipe. De plus, si vous créez votre propre structure de dossiers dans un document library **il ne propage pas** aux équipes comme un canal ; à ce stade, il seulement s’enchaîne d’équipes dans SharePoint.

> [!NOTE]
> Suppression d’un groupe d’Office 365 seront supprimer que l’invite de la boîte aux lettres alias pour des conversations Outlook/OWA permanentes et réunions d’équipes et marque SharePoint de site pour la suppression. Elle prend environ 20 minutes entre la suppression d’une équipe et son incidence sur Outlook. Suppression d’une équipe à partir du client équipes supprimera il immédiatement à partir de la vue à tous ceux qui sont membres de l’équipe. Si vous supprimez des membres d’un groupe Office 365 qui a été activée la fonctionnalité équipes, il peut être un délai d’environ deux heures avant de l’équipe est supprimé de l’affichage dans le client équipes pour les utilisateurs concernés qui ont été supprimées.
>
>Lisez [cette](https://support.office.com/en-us/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) pour plus d’informations sur la restauration d’un groupe Office 365 que vous avez supprimé.

<a name="group-membership"></a>Adhésion à un groupe
----------------

Groupe des fonctionnalités pour vos utilisateurs dépendent où vous l’appartenance au groupe à partir du lecteur. Par exemple, si vous supprimez un membre d’une équipe, ils sont supprimés du groupe ainsi que de Office 365. Suppression du groupe supprime l’équipe immédiatement et canaux à partir du client équipes. Si vous supprimez une personne à partir d’un groupe à l’aide du portail d’administration d’Office 365, ils auront n’est plus accès aux autres aspects collaboration tels que de la bibliothèque de documents SharePoint Online, groupe Yammer ou OneNote partagé. Toutefois, elles auront accès à la fonctionnalité de conversation de l’équipe pendant environ deux heures.

Meilleures pratiques pour la gestion des membres d’équipes : ajouter et supprimer des membres à partir du client équipes pour vous assurer que le contrôle d’accès en cascade correct à d’autres applications cloud dépendant est appliqué. En outre, vous permettront d’éviter personnes quitter disjoint expérience avec l’impression qu’ils ont toujours accès aux ressources qu’ils permet (jusqu'à ce que le cycle de synchronisation suivant ajoute ou révoque l’accès à un composant spécifique du service). Si vous ajoutez ou supprimez des membres de l’équipe en dehors du client équipes (à l’aide du centre d’administration d’Office 365, Azure AD, ou Exchange Online PowerShell), il peut prendre jusqu'à deux heures pour que les modifications soient reflétées dans les équipes.
