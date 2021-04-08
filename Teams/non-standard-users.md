---
title: Comportement des applications Teams pour les utilisateurs non standard
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez le comportement des applications dans Microsoft Teams pour les utilisateurs non standard.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb4b5dfebabfcd0bc86006d93272c3901e7dcfc7
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617847"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="05db6-103">Comportement des applications Microsoft Teams pour les utilisateurs non standard</span><span class="sxs-lookup"><span data-stu-id="05db6-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="05db6-104">Cet article décrit le comportement des applications dans Teams lorsque des utilisateurs invités, externes (fédérés) et anonymes sont présents dans un contexte Teams.</span><span class="sxs-lookup"><span data-stu-id="05db6-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="05db6-105">Un **utilisateur invité est** une personne qui n’est ni un employé, ni un étudiant ni un membre de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="05db6-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="05db6-106">Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="05db6-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="05db6-107">Un **utilisateur externe (fédéré)** appartient à un autre domaine et n’a pas accès aux équipes ou ressources d’équipe de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="05db6-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="05db6-108">Pour une comparaison plus détaillée des utilisateurs invités et externes, voir [Communiquer avec des utilisateurs d’autres organisations.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="05db6-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="05db6-109">Un **utilisateur anonyme est** un concept dans les réunions Teams où l’utilisateur a rejoint la réunion via un lien.</span><span class="sxs-lookup"><span data-stu-id="05db6-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="05db6-110">L’utilisateur n’est pas connecté avec son compte Microsoft ou celui de son organisation.</span><span class="sxs-lookup"><span data-stu-id="05db6-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="05db6-111">Accès des utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="05db6-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="05db6-112">Installer, mettre à jour et supprimer des utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="05db6-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="05db6-113">Les invités ne peuvent pas installer, mettre à jour ou supprimer des applications dans un contexte partagé, tel qu’une conversation, un canal ou une réunion.</span><span class="sxs-lookup"><span data-stu-id="05db6-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="05db6-114">Ils peuvent installer, mettre à jour ou supprimer des applications dans leur étendue personnelle à l’aide d’extensions de messages et de liens directs.</span><span class="sxs-lookup"><span data-stu-id="05db6-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="05db6-115">Les invités n’ont pas accès au magasin d’applications Teams.</span><span class="sxs-lookup"><span data-stu-id="05db6-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="05db6-116">Comportement et stratégie d’utilisation pour les utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="05db6-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="05db6-117">Les invités peuvent utiliser une application si l’application a été installée par un utilisateur natif.</span><span class="sxs-lookup"><span data-stu-id="05db6-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="05db6-118">Les robots peuvent envoyer un message de façon proactive aux utilisateurs invités, mais les invités ne peuvent pas interagir avec le robot.</span><span class="sxs-lookup"><span data-stu-id="05db6-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="05db6-119">Les invités ne peuvent pas envoyer de message au bot 1:1, @mentionner le robot ou interagir avec des cartes adaptatives qui communiquent avec le bot.</span><span class="sxs-lookup"><span data-stu-id="05db6-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="05db6-120">Les invités respecteront les stratégies d’autorisation globales et à l’échelle de l’organisation définies pour le client hôte pour n’importe quelle application.</span><span class="sxs-lookup"><span data-stu-id="05db6-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="05db6-121">En d’autres termes, si une application est bloquée pour l’ensemble de l’organisation hôte, les invités ne peuvent pas non plus l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="05db6-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="05db6-122">Les stratégies d’installation ne s’appliquent pas aux utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="05db6-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="05db6-123">Cela signifie que l’application épinglée par l’administrateur à partir de la stratégie par défaut n’affecte pas les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="05db6-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="05db6-124">Accès des utilisateurs externes (fédérés)</span><span class="sxs-lookup"><span data-stu-id="05db6-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="05db6-125">Installer, mettre à jour et supprimer des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="05db6-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="05db6-126">Les utilisateurs externes ne peuvent pas installer, mettre à jour ou supprimer des applications dans n’importe quel contexte, tel qu’une conversation personnelle, un canal ou une réunion.</span><span class="sxs-lookup"><span data-stu-id="05db6-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="05db6-127">Ils n’ont pas accès au magasin d’applications Teams.</span><span class="sxs-lookup"><span data-stu-id="05db6-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="05db6-128">Comportement et stratégie d’utilisation pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="05db6-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="05db6-129">Les utilisateurs externes ne peuvent pas utiliser les applications Teams et, lorsqu’un utilisateur externe est ajouté à un contexte avec des utilisateurs natifs, tous les utilisateurs, natifs et externes, ne peuvent plus utiliser d’applications.</span><span class="sxs-lookup"><span data-stu-id="05db6-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="05db6-130">Les utilisateurs externes ne sont pas impactés par les stratégies d’application, car ils ne peuvent pas utiliser les applications Teams.</span><span class="sxs-lookup"><span data-stu-id="05db6-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="05db6-131">Utilisateur anonyme dans l’accès aux réunions</span><span class="sxs-lookup"><span data-stu-id="05db6-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="05db6-132">Installation, mise à jour et suppression pour les utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="05db6-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="05db6-133">Les utilisateurs anonymes ne peuvent pas installer, mettre à jour ou supprimer des applications dans les réunions.</span><span class="sxs-lookup"><span data-stu-id="05db6-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="05db6-134">Comportement et stratégie d’utilisation des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="05db6-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="05db6-135">Les utilisateurs anonymes ne peuvent pas utiliser directement des applications dans les réunions.</span><span class="sxs-lookup"><span data-stu-id="05db6-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="05db6-136">Les utilisateurs natifs peuvent continuer à utiliser les applications de réunion si des utilisateurs anonymes sont présents.</span><span class="sxs-lookup"><span data-stu-id="05db6-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="05db6-137">Si une application envoie une carte adaptative dans la conversation, les utilisateurs anonymes peuvent interagir avec la carte pour plus d’informations, voir Autoriser les utilisateurs anonymes à [participer à des réunions.](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="05db6-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card For more information, see [Allow anonymous users to join meetings](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="05db6-138">Les utilisateurs anonymes héritent de la stratégie d’autorisation globale par défaut au niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="05db6-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="05db6-139">Ils peuvent interagir avec des applications dans les réunions Teams si la stratégie d’autorisation au niveau utilisateur a activé l’application.</span><span class="sxs-lookup"><span data-stu-id="05db6-139">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="05db6-140">Les utilisateurs anonymes peuvent uniquement interagir avec les applications déjà disponibles dans une réunion et qui ne peuvent pas acquérir et/ou gérer ces applications.</span><span class="sxs-lookup"><span data-stu-id="05db6-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
