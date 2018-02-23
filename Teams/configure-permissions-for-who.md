---
title: Configurer les autorisations pour Who
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
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

Pour plus d'informations sur la gestion des étendues des autorisations dans Microsoft Graph, reportez-vous à la rubrique [Étendues des autorisations](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).
 
Pour plus d’informations sur les autorisations dans Microsoft Graph , reportez-vous à la rubrique [Référence des autorisations dans Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).