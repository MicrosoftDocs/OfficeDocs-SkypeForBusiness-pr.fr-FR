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
<a name="configure-permissions-for-who"></a><span data-ttu-id="0ddc0-103">Configurer les autorisations pour Who</span><span class="sxs-lookup"><span data-stu-id="0ddc0-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="0ddc0-104">Les utilisateurs peuvent utiliser l'application Who avec Microsoft Teams pour poser des questions et rechercher des personnes de l’organisation en fonction de leurs tâches et de leurs collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="0ddc0-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="0ddc0-105">Pour vous assurer que les utilisateurs optimisent l’utilisation de Who, vous devez activer les autorisations de membre suivantes dans Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="0ddc0-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="0ddc0-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="0ddc0-106">Calendars.Read</span></span>

- <span data-ttu-id="0ddc0-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="0ddc0-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="0ddc0-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="0ddc0-108">Mail.Read</span></span>

- <span data-ttu-id="0ddc0-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0ddc0-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="0ddc0-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="0ddc0-110">People.Read</span></span>

- <span data-ttu-id="0ddc0-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="0ddc0-111">People.Read.All</span></span>

- <span data-ttu-id="0ddc0-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="0ddc0-112">Sites.Read.All</span></span>

- <span data-ttu-id="0ddc0-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="0ddc0-113">User.Read.All</span></span>

<span data-ttu-id="0ddc0-114">Pour plus d'informations sur la gestion des étendues des autorisations dans Microsoft Graph, reportez-vous à la rubrique [Étendues des autorisations](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span><span class="sxs-lookup"><span data-stu-id="0ddc0-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="0ddc0-115">Pour plus d’informations sur les autorisations dans Microsoft Graph , reportez-vous à la rubrique [Référence des autorisations dans Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="0ddc0-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span></span>