---
title: Groupes Office 365 et Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Découvrez comment utiliser Groupes Office 365 et les adhésions de groupe avec Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2018
---
<a name="office-365-groups-and-microsoft-teams"></a>Groupes Office 365 et Microsoft Teams
=====================================

Groupes Office 365 est le service d'adhésion inter-applications dans Office 365. Au niveau de base, un groupe Office 365 est un objet dans Azure Active Directory comprenant une liste des membres et un couplage faible aux charges de travail relatives incluant un site d'équipe SharePoint, un groupe Yammer, des ressources de boîtes aux lettres Exchange partagées, le Planificateur, PowerBI et OneNote. Vous pouvez ajouter ou supprimer des contacts du groupe, comme avec tout autre objet de sécurité basé sur un groupe dans Active Directory.

Un administrateur Office 365 peut définir un groupe Office 365, ajouter des membres et utiliser des fonctionnalités telles que la boîte aux lettres partagée Exchange, la bibliothèque de documents SharePoint, le groupe Yammer, etc. Pour plus d'informations sur les groupes, rendez-vous sur la page : [En savoir plus sur les groupes Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Fonctionnement des groupes Office 365
--------------------------

Lors de la création d'une équipe Microsoft Teams, vous créez en arrière-plan un groupe Office 365 avec la bibliothèque de documents SharePoint et le bloc-notes OneNote associés, ainsi que des liens vers d'autres applications Office 365 cloud. Si l'utilisateur qui crée l'équipe est propriétaire d'un groupe Office 365 public ou privé existant, il peut ajouter la fonctionnalité Teams au groupe. Un canal Général contenant des messages, documents OneNote ainsi que d'autres objets est ainsi créé par défaut. La vue de la bibliothèque de documents du canal affichera le dossier Général représentant le canal dans l'équipe. Plus important encore, si vous créez votre propre structure de dossiers dans une bibliothèque de documents, **elle ne se propage pas** dans Teams en tant que canal ; elle se propage uniquement de Teams à SharePoint pour le moment.




> [!NOTE]
> La suppression d'un groupe Office 365 supprimera l'alias de boîte aux lettres pour les conversations permanentes Outlook/OWA et les invitations aux réunions Teams ; le site SharePoint sera également marqué pour suppression. L'action de suppression d'une équipe prend effet après environ 20 minutes. Lorsque vous supprimez une équipe du client Teams, tous les autres membres ne peuvent plus l'afficher. Si vous supprimez un membre d'un groupe Office 365 qui disposait de la fonctionnalité Teams activée, il pourra encore afficher l'équipe pendant environ une heure avant sa suppression effective du client Teams.

<a name="group-membership"></a>Adhésion à un groupe
----------------

Les fonctionnalités de groupe et les capacités de vos utilisateurs dépend où vous l’appartenance au groupe à partir du lecteur. Par exemple, si vous supprimez un membre d’une équipe, ils sont supprimés du groupe ainsi que de Office 365. Suppression du groupe supprime l’équipe immédiatement et canaux du client d’équipes. Si vous supprimez une personne d’un groupe en utilisant le portail d’administration d’Office 365, ils n’auront plus accès aux autres aspects collaboration comme bibliothèque de documents SharePoint Online, le groupe de Yammer, ou partagé OneNote. Toutefois, ils auront toujours accès à la fonctionnalité de conversation de l’équipe pendant environ une heure.

Meilleures pratiques pour la gestion des membres des équipes : ajouter et supprimer des membres à partir du client aux équipes pour assurer le contrôle d’accès en cascade correct à d’autres applications de cloud dépendant est appliqué. En outre, vous éviterez un expérience disjoint de personnes quitter avec l’impression qu’ils ont toujours accès aux ressources qui que leur permettant (jusqu'à ce que le prochain cycle de synchronisation ajoute ou révoque l’accès à un composant particulier du service). Si vous ajoutez ou supprimez des membres de l’équipe en dehors du client équipes (à l’aide du centre d’administration Office 365, AD Azure, ou Exchange Online PowerShell), il faut parfois jusqu'à une heure pour que les modifications se reflètent dans les équipes.
