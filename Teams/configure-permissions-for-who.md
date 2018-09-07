---
title: Configurer les autorisations pour Who
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc8fe9a21cdfa4d1df0bf3f11631d103a13fe94b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860214"
---
<a name="configure-permissions-for-who"></a>Configurer les autorisations pour Who
=============================

Les utilisateurs peuvent utiliser l'application Who avec Microsoft Teams pour poser des questions et rechercher des personnes de l’organisation en fonction de leurs tâches et de leurs collaborateurs.

Pour vous assurer que les utilisateurs optimisent l’utilisation de Who, vous devez activer les autorisations de membre suivantes dans Microsoft Graph.

- Calendars.Read

- Calendars.Read.Shared

- Mail.Read

- MailboxSettings.ReadWrite

- People.Read

- People.Read.All

- Sites.Read.All

- User.Read.All

Pour plus d'informations sur la gestion des étendues des autorisations dans Microsoft Graph, reportez-vous à la rubrique [Étendues des autorisations](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).
 
Pour plus d’informations sur les autorisations dans Microsoft Graph , reportez-vous à la rubrique [Référence des autorisations dans Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).