---
title: "Groupes Office 365 et Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: overview
ms.prod: teams
description: "Découvrez comment utiliser Groupes Office 365 et les adhésions de groupe avec Microsoft Teams."
ms.openlocfilehash: d2a0f9c4d12a1c2e92f552b0293610d5d0ecadc9
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2017
---
<a name="office-365-groups-and-microsoft-teams"></a>Groupes Office 365 et Microsoft Teams
=====================================

Groupes Office 365 est le service d'adhésion inter-applications dans Office 365. Au niveau de base, un groupe Office 365 est un objet dans Azure Active Directory comprenant une liste des membres et un couplage faible aux charges de travail relatives incluant un site d'équipe SharePoint, un groupe Yammer, des ressources de boîtes aux lettres Exchange partagées, le Planificateur, PowerBI et OneNote. Vous pouvez ajouter ou supprimer des contacts du groupe, comme avec tout autre objet de sécurité basé sur un groupe dans Active Directory.

Un administrateur Office 365 peut définir un groupe Office 365, ajouter des membres et utiliser des fonctionnalités telles que la boîte aux lettres partagée Exchange, la bibliothèque de documents SharePoint, le groupe Yammer, etc. Pour plus d'informations sur les groupes, rendez-vous sur la page : [En savoir plus sur les groupes Office 365](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Fonctionnement des groupes Office 365
--------------------------

Lors de la création d'une équipe Microsoft Teams, vous créez en arrière-plan un groupe Office 365 avec la bibliothèque de documents SharePoint et le bloc-notes OneNote associés, ainsi que des liens vers d'autres applications Office 365 cloud. Si l'utilisateur qui crée l'équipe est propriétaire d'un groupe Office 365 public ou privé existant, il peut ajouter la fonctionnalité Teams au groupe. Un canal Général contenant des messages, documents OneNote ainsi que d'autres objets est ainsi créé par défaut. La vue de la bibliothèque de documents du canal affichera le dossier Général représentant le canal dans l'équipe. Plus important encore, si vous créez votre propre structure de dossiers dans une bibliothèque de documents, **elle ne se propage pas** dans Teams en tant que canal ; elle se propage uniquement de Teams à SharePoint pour le moment.

|||
|---------|---------|
|  Remarque sur ![](media/Understand_Office_365_groups_and_Microsoft_Teams_image1.png)    |La suppression d'un groupe Office 365 supprimera l'alias de boîte aux lettres pour les conversations permanentes Outlook/OWA et les invitations aux réunions Teams ; le site SharePoint sera également marqué pour suppression. L'action de suppression d'une équipe prend effet après environ 20 minutes. Lorsque vous supprimez une équipe du client Teams, tous les autres membres ne peuvent plus l'afficher. Si vous supprimez un membre d'un groupe Office 365 qui disposait de la fonctionnalité Teams activée, il pourra encore afficher l'équipe pendant environ une heure avant sa suppression effective du client Teams.         |


<a name="group-membership"></a>Adhésion à un groupe
----------------

Les fonctionnalités disponibles pour vos utilisateurs dépendent de l'emplacement du processus d'adhésion. Par exemple, si vous supprimer un membre d'une équipe, il sera également supprimé du groupe Office 365. Supprimer du groupe implique la suppression immédiate de l'équipe et des canaux du client Teams. Si vous supprimez une personne d'un groupe à l'aide du portail d'administration Office 365, elle ne pourra plus accéder aux autres éléments de collaboration tels que la bibliothèque de documents SharePoint Online, le groupe Yammer, ou le bloc-notes OneNote partagé. Toutefois, elle aura accès aux fonctionnalités de conversation de Teams pendant environ une heure.

En ce qui concerne la gestion des membres d'équipe, nous recommandons d'utiliser la fonctionnalité d'ajout/de suppression via le client Teams pour garantir la réplication en cascade du contrôle d'accès aux autres applications cloud dépendantes. Vous éviterez ainsi toute incohérence pouvant laisser penser aux utilisateurs qu'ils ont toujours accès aux ressources habituelles, jusqu'au prochain cycle de synchronisation qui ajoutera ou supprimera l'accès à un composant particulier du service.
