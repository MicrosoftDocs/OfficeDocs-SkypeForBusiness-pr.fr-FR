---
title: Teams comportement des applications pour les utilisateurs non standard
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez le comportement des applications Microsoft Teams utilisateurs non standard.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628923"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="e1d21-103">Microsoft Teams comportement des applications pour les utilisateurs non standard</span><span class="sxs-lookup"><span data-stu-id="e1d21-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="e1d21-104">Cet article décrit le comportement des applications dans Teams lorsque des utilisateurs invités, externes (fédérés) et anonymes sont présents dans un Teams externe.</span><span class="sxs-lookup"><span data-stu-id="e1d21-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="e1d21-105">Un **utilisateur invité est** une personne qui n’est ni un employé, ni un étudiant ni un membre de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e1d21-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="e1d21-106">Il ne dispose pas d'aucun compte scolaire ni professionnel lié à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e1d21-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="e1d21-107">Un **utilisateur externe (fédéré)** appartient à un autre domaine et n’a pas accès aux équipes ou ressources d’équipe de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e1d21-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="e1d21-108">Pour une comparaison plus détaillée des utilisateurs invités et externes, voir [Communiquer avec des utilisateurs d’autres organisations.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="e1d21-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="e1d21-109">Un **utilisateur anonyme** est un concept dans le Teams au cours des réunions où l’utilisateur a rejoint la réunion via un lien.</span><span class="sxs-lookup"><span data-stu-id="e1d21-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="e1d21-110">L’utilisateur n’est pas connecté avec son compte Microsoft ou celui de son organisation.</span><span class="sxs-lookup"><span data-stu-id="e1d21-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="e1d21-111">Utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="e1d21-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="e1d21-112">Installer, mettre à jour et supprimer des utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="e1d21-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="e1d21-113">Les invités ne peuvent pas installer, mettre à jour ou supprimer des applications dans un contexte partagé, tel qu’une conversation, un canal ou une réunion, mais ils peuvent l’utiliser dans leur étendue personnelle à l’aide d’extensions de messages et de liens directs.</span><span class="sxs-lookup"><span data-stu-id="e1d21-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="e1d21-114">Les invités n’ont pas accès à l’App Store Teams à partir de l’application de bureau Teams, mais ils peuvent y accéder à l’aide d’un lien direct.</span><span class="sxs-lookup"><span data-stu-id="e1d21-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="e1d21-115">Comportement et stratégie d’utilisation pour les utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="e1d21-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="e1d21-116">Les invités peuvent utiliser une application si l’application a été installée par un utilisateur natif.</span><span class="sxs-lookup"><span data-stu-id="e1d21-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="e1d21-117">Bots installed to a channel</span><span class="sxs-lookup"><span data-stu-id="e1d21-117">Bots installed to a channel</span></span>

<span data-ttu-id="e1d21-118">Les robots peuvent envoyer un message de façon proactive aux utilisateurs invités, mais les invités ne peuvent pas interagir avec le robot.</span><span class="sxs-lookup"><span data-stu-id="e1d21-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="e1d21-119">Les invités ne peuvent pas envoyer de message à un robot, le mentionner ou interagir avec des cartes adaptatives qui communiquent avec le bot.</span><span class="sxs-lookup"><span data-stu-id="e1d21-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="e1d21-120">Bots personnels installés avec des stratégies</span><span class="sxs-lookup"><span data-stu-id="e1d21-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="e1d21-121">Les invités respecteront les stratégies d’autorisation globales et à l’échelle de l’organisation définies pour le client hôte pour n’importe quelle application.</span><span class="sxs-lookup"><span data-stu-id="e1d21-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="e1d21-122">Si une application est bloquée pour l’ensemble de l’organisation hôte, les invités ne peuvent pas non plus l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="e1d21-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="e1d21-123">Les robots inclus dans la stratégie de configuration d’application par défaut globale sont également installés pour les invités.</span><span class="sxs-lookup"><span data-stu-id="e1d21-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="e1d21-124">Une fois qu’un bot est installé, les robots peuvent communiquer de façon proactive avec les invités et les invités peuvent communiquer avec les bots.</span><span class="sxs-lookup"><span data-stu-id="e1d21-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="e1d21-125">Vous ne pouvez pas supprimer un invité de la stratégie de configuration globale par défaut de l’application.</span><span class="sxs-lookup"><span data-stu-id="e1d21-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="e1d21-126">Pour éviter que les invités accèdent aux bots, vous pouvez créer d’autres stratégies de configuration d’application, les affecter à des utilisateurs internes et installer des bots avec les stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e1d21-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="e1d21-127">Utilisateurs externes (fédérés)</span><span class="sxs-lookup"><span data-stu-id="e1d21-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="e1d21-128">Installer, mettre à jour et supprimer des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="e1d21-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="e1d21-129">Les utilisateurs externes ne peuvent pas installer, mettre à jour ou supprimer des applications dans n’importe quel contexte, tel qu’une conversation personnelle, un canal ou une réunion.</span><span class="sxs-lookup"><span data-stu-id="e1d21-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="e1d21-130">Ils n’ont pas accès au Teams App Store.</span><span class="sxs-lookup"><span data-stu-id="e1d21-130">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="e1d21-131">Comportement et stratégie d’utilisation pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="e1d21-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="e1d21-132">Les utilisateurs externes ne peuvent pas utiliser les applications Teams et lorsqu’un utilisateur externe est ajouté à un contexte avec des utilisateurs natifs, tous les utilisateurs, natifs et externes, ne peuvent plus utiliser d’applications.</span><span class="sxs-lookup"><span data-stu-id="e1d21-132">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>
- <span data-ttu-id="e1d21-133">Les utilisateurs externes ne sont pas impactés par les stratégies d’application, car ils ne peuvent pas Teams applications.</span><span class="sxs-lookup"><span data-stu-id="e1d21-133">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="e1d21-134">Utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="e1d21-134">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="e1d21-135">Installation, mise à jour et suppression pour les utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="e1d21-135">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="e1d21-136">Les utilisateurs anonymes ne peuvent pas installer, mettre à jour ou supprimer des applications dans les réunions.</span><span class="sxs-lookup"><span data-stu-id="e1d21-136">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="e1d21-137">Comportement et stratégie d’utilisation des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="e1d21-137">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="e1d21-138">Les utilisateurs anonymes ne peuvent pas utiliser directement des applications dans les réunions.</span><span class="sxs-lookup"><span data-stu-id="e1d21-138">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="e1d21-139">Les utilisateurs natifs peuvent continuer à utiliser les applications de réunion si des utilisateurs anonymes sont présents.</span><span class="sxs-lookup"><span data-stu-id="e1d21-139">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="e1d21-140">Si une application envoie une carte adaptative dans la conversation, les utilisateurs anonymes peuvent interagir avec la carte.</span><span class="sxs-lookup"><span data-stu-id="e1d21-140">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="e1d21-141">Pour plus d’informations, [voir Autoriser les utilisateurs anonymes à participer à des réunions.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="e1d21-141">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="e1d21-142">Les utilisateurs anonymes héritent de la stratégie d’autorisation globale par défaut au niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e1d21-142">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="e1d21-143">Ils peuvent interagir avec des applications dans Teams réunions si la stratégie d’autorisation au niveau utilisateur a activé l’application.</span><span class="sxs-lookup"><span data-stu-id="e1d21-143">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="e1d21-144">Les utilisateurs anonymes peuvent uniquement interagir avec les applications déjà disponibles dans une réunion et qui ne peuvent pas acquérir et/ou gérer ces applications.</span><span class="sxs-lookup"><span data-stu-id="e1d21-144">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
