---
title: Groupes d’Office 365 et les équipes Microsoft
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: msteams
description: Découvrez comment utiliser Groupes Office 365 et les adhésions de groupe avec Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77c8125425bf7aaaf6f619edc9463b17967e4133
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32180263"
---
<a name="office-365-groups-and-microsoft-teams"></a>Groupes d’Office 365 et les équipes Microsoft
=====================================

> [!Tip]
> Regarder la session suivante pour savoir comment les équipes interagit avec Azure Active Directory (AD Azure), groupes d’Office 365, Exchange, SharePoint et OneDrive for Business : [Notions de base sur les équipes de Microsoft](https://aka.ms/teams-foundations)

Groupes d’Office 365 est le service d’appartenance entre les applications dans Office 365. Au niveau de la base, un groupe d’Office 365 est un objet dans Azure Active Directory avec une liste des membres et un couplage faible pour un site d’équipe SharePoint, groupe Yammer, y compris les charges de travail associées partagé des ressources de boîte aux lettres Exchange, Planificateur, Power BI et OneNote. Vous pouvez ajouter ou supprimer des personnes au groupe comme vous le feriez pour n’importe quel autre objet basée sur le groupe de sécurité dans Active Directory.

Un administrateur Office 365 peut définir un groupe d’Office 365, ajouter des membres et tirer parti des fonctionnalités telles que l’échange partagés boîte aux lettres, bibliothèque de documents SharePoint, groupe Yammer et ainsi de suite. Pour plus d’informations sur les groupes d’Office 365, voir [en savoir plus sur les groupes d’Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Ne manquez pas le poster de [groupes dans Microsoft 365 pour les architectes](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-office-365-groups-work"></a>Comment fonctionnent les groupes d’Office 365
--------------------------

Lorsque vous créez une équipe, sur le serveur principal, vous créez un groupe d’Office 365 et associé à une bibliothèque de documents SharePoint et bloc-notes OneNote, ainsi que des liens vers d’autres applications de nuage Office 365. Si la personne qui a créé l’équipe est un propriétaire d’un existant Office 365 Public ou privé groupe, ils peuvent ajouter des fonctionnalités d’équipes au groupe si elle a moins de 5 000 personnes et n’a jamais été ajouté aux équipes. Cette opération crée un canal **Général** par défaut de conversation qui résident les messages, documents, OneNote et autres objets. Affichage de la bibliothèque de documents pour le canal révélera le dossier **Général** représentant le canal de l’équipe. De plus, si vous créez votre propre structure de dossiers dans un document library **il ne propage pas** aux équipes comme un canal ; à ce stade, il seulement s’enchaîne d’équipes dans SharePoint.

> [!NOTE]
> En fonction des commentaires des clients, les nouveaux groupes de 365 Office générés suite à la création d’une équipe dans Microsoft Teams n’apparaît plus dans Outlook par défaut. Pour les clients qui vous souhaitez continuer avec le comportement de l’affichage de ces groupes dans Outlook existant, une applet de commande Exchange Online PowerShell est fournie qui permettent le groupe pour l’expérience Outlook. Groupes créés via Outlook et activé plus tard pour les équipes continuera à afficher dans Outlook et les équipes. Cette mise à jour sera progressivement roll out entre Outlook et les équipes dans les mois à venir.

> [!NOTE]
> Suppression d’un groupe d’Office 365 seront supprimer que l’invite de la boîte aux lettres alias pour des conversations Outlook/OWA permanentes et réunions d’équipes et marque SharePoint de site pour la suppression. Elle prend environ 20 minutes entre la suppression d’une équipe et son incidence sur Outlook. Suppression d’une équipe à partir du client équipes supprimera il immédiatement à partir de la vue à tous ceux qui sont membres de l’équipe. Si vous supprimez des membres d’un groupe Office 365 qui a été activée la fonctionnalité équipes, il peut être un délai d’environ deux heures avant de l’équipe est supprimé de l’affichage dans le client équipes pour les utilisateurs concernés qui ont été supprimées.
>
>Lisez [cette](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) pour plus d’informations sur la restauration d’un groupe Office 365 que vous avez supprimé.

<a name="group-membership"></a>Adhésion à un groupe
----------------

Groupe des fonctionnalités pour vos utilisateurs dépendent où vous l’appartenance au groupe à partir du lecteur. Par exemple, si vous supprimez un membre d’une équipe, ils sont supprimés du groupe ainsi que de Office 365. Suppression du groupe supprime l’équipe immédiatement et canaux à partir du client équipes. Si vous supprimez une personne à partir d’un groupe en utilisant le centre d’administration Office 365, ils n’auront plus accès à d’autres aspects collaboration tels que de la bibliothèque de documents SharePoint Online, Yammer groupe ou OneNote partagé. Toutefois, elles auront accès à la fonctionnalité de conversation de l’équipe pendant environ deux heures.

Meilleure pratique pour la gestion des membres d’équipes, ajouter et supprimer des membres à partir du client équipes pour vous assurer que le contrôle d’accès en cascade correct à d’autres applications cloud dépendant est appliqué. En outre, vous permettront d’éviter personnes quitter disjoint expérience avec l’impression qu’ils ont toujours accès aux ressources qu’ils permet (jusqu'à ce que le cycle de synchronisation suivant ajoute ou révoque l’accès à un composant spécifique du service). Si vous ajoutez ou supprimez des membres de l’équipe en dehors du client équipes (à l’aide du centre d’administration Office 365, Azure AD, ou Exchange Online PowerShell), il peut prendre jusqu'à deux heures pour que les modifications soient reflétées dans les équipes.
