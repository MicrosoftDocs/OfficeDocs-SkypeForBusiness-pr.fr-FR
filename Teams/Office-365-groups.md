---
title: Groupes Microsoft 365 et Microsoft teams
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 414ca42153ab336500aa7b2e9de42dd9fe7f2708
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902119"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Groupes Microsoft 365 et Microsoft teams
=====================================

> [!Tip]
> Regardez la session suivante pour découvrir comment les équipes interagissent avec Azure Active Directory (Azure AD), Microsoft 365 Groups, Exchange, SharePoint et OneDrive entreprise : [notions de bases de Microsoft teams](https://aka.ms/teams-foundations)

Microsoft 365 groups est le service d’appartenance à plusieurs applications d’Office 365. Au niveau de base, un groupe Office 365 est un objet dans Azure Active Directory avec une liste de membres et un couplage lâche aux charges de travail associées, y compris un site d’équipe SharePoint, un groupe Yammer, des ressources de boîte aux lettres Exchange partagées, le planificateur, Power BI et OneNote. Vous pouvez ajouter ou supprimer des personnes dans le groupe comme vous le feriez pour n’importe quel autre objet de sécurité en groupe dans Active Directory.

Un administrateur de 365 Office peut définir un groupe 365 Office, ajouter des membres et bénéficier de fonctionnalités telles qu’une boîte aux lettres partagée Exchange, une bibliothèque de documents SharePoint, un groupe Yammer, etc. Pour plus d’informations sur les groupes Microsoft 365, voir [en savoir plus sur les groupes microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Ne manquez pas les [groupes d’affiches dans Microsoft 365 pour les architectes informatiques](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-microsoft-365-groups-work"></a>Fonctionnement des groupes Microsoft 365
--------------------------

Lorsque vous créez une équipe, sur le système principal, vous créez un groupe Office 365 et la bibliothèque de documents SharePoint associée et un bloc-notes OneNote, ainsi que des liens vers d’autres applications Cloud Office 365. Si la personne qui crée l’équipe est le propriétaire d’un groupe public ou privé Office 365 existant, elle peut ajouter des fonctionnalités d’équipe au groupe si elle a moins de 5000 personnes et qu’elle n’a jamais été ajoutée à Teams. Cela crée un canal **général** par défaut dans lequel se trouvent les messages de discussion, les documents, OneNote et les autres objets. Le principe d’affichage de la bibliothèque de documents du canal permettra d’afficher le dossier **général** représentant le canal dans l’équipe. Plus important encore, si vous créez votre propre structure de dossiers au sein d’une bibliothèque de documents, **celle-ci n’est pas propagée** aux équipes en tant que canal ; pour l’instant, seules les équipes sont acheminées vers SharePoint.

> [!NOTE]
> En fonction des commentaires des clients, les nouveaux groupes Microsoft 365 générés suite à la création d’une équipe dans Microsoft Teams ne s’afficheront plus dans Outlook par défaut. Pour les clients souhaitant continuer à utiliser le comportement d’affichage de ces groupes dans Outlook, une cmdlet PowerShell Exchange Online sera fournie, ce qui peut permettre au groupe d’avoir accès à l’environnement Outlook. Les groupes créés via Outlook et les versions ultérieures sont activés pour les équipes continuent à apparaître dans Outlook et Teams. Cette mise à jour sera déployée progressivement entre Outlook et teams dans les prochains mois.

> [!NOTE]
> La suppression d’un groupe Office 365 entraîne la suppression de l’alias de boîte aux lettres pour les invitations aux réunions Outlook Le retrait d’une équipe et son impact sur Outlook sont d’environ 20 minutes. La suppression d’une équipe du client teams le supprime immédiatement de l’affichage de tous les membres de l’équipe. Si vous supprimez des membres d’un groupe Office 365 pour lequel la fonctionnalité d’équipe est activée, il peut y avoir un délai d’environ deux heures avant la suppression de l’équipe dans le client teams pour les personnes concernées qui ont été supprimées.
>
>Pour plus d’informations sur la restauration d’un groupe Office 365 que vous avez supprimé, voir [Ceci](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) .

<a name="group-membership"></a>Adhésion à un groupe
----------------

Les fonctionnalités de groupe et les fonctionnalités de vos utilisateurs dépendent de l’emplacement d’appartenance au groupe. Par exemple, si vous supprimez un membre d’une équipe, il est également supprimé du groupe Office 365. La suppression du groupe entraîne la suppression immédiate de l’équipe et des canaux du client Teams. Si vous supprimez un membre d’un groupe à l’aide du centre d’administration Microsoft 365, il n’aura plus accès aux autres aspects de la collaboration tels que la bibliothèque de documents SharePoint Online, le groupe Yammer ou le partage OneNote. Toutefois, ils pourront toujours accéder à la fonctionnalité de conversation de l’équipe pendant environ deux heures.

Pour gérer les membres d’une équipe, vous pouvez ajouter et supprimer des membres du client teams pour vous assurer que le contrôle d’accès en cascade approprié aux autres applications Cloud dépendantes est appliqué. Par ailleurs, vous éviterez une connaissance disconcertée qui laissait des personnes disposant de l’impression d’avoir accès aux ressources qu’elles utilisent (jusqu’à ce que le cycle de synchronisation suivant ajoute ou révoque l’accès à un composant particulier du service). Si vous ajoutez ou supprimez des membres d’équipe en dehors du client Teams (à l’aide du centre d’administration Microsoft 365, d’Azure AD ou d’Exchange Online PowerShell), les modifications peuvent prendre jusqu’à deux heures pour que les modifications soient répercutées dans Teams.
