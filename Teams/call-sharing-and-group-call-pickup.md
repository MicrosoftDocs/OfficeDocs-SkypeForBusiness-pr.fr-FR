---
title: Partage d’appel et prise d’appel de groupe dans Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Les appels de partage et de groupe permettent aux utilisateurs de partager des appels entrants avec des collègues, de sorte que les appels puissent être capturés quand l’utilisateur n’est pas disponible.
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283478"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="80a48-103">Partage d’appel et prise d’appel de groupe dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80a48-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="80a48-104">Les fonctionnalités de partage d’appel et de cueillette de groupe de Microsoft teams permettent aux utilisateurs de partager leurs appels entrants avec leurs collègues pour permettre aux collègues de répondre aux appels qui se produisent alors que l’utilisateur n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="80a48-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="80a48-105">Le prélèvement d’appels de groupe est moins gênant pour les destinataires que les autres formes de partage d’appel (par exemple, le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer la façon dont ils veulent être avertis d’un appel partagé entrant (via une notification audio et visuelle, visuel uniquement) ou une bannière dans l’application Teams) et choisir d’y répondre.</span><span class="sxs-lookup"><span data-stu-id="80a48-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="80a48-106">Pour partager les appels, un utilisateur crée un groupe d’appels et ajoute les utilisateurs avec lesquels vous souhaitez partager leurs appels.</span><span class="sxs-lookup"><span data-stu-id="80a48-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="80a48-107">Ils choisissent alors un paramètre de sonnerie ou de transfert simultané.</span><span class="sxs-lookup"><span data-stu-id="80a48-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="80a48-108">Pour [en savoir plus, voir transfert d’appel et sonnerie simultanée dans teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="80a48-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80a48-109">Les utilisateurs, le propriétaire du groupe d’appels et les membres du groupe d’appels doivent être en mode déploiement d’équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="80a48-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="80a48-110">Pour plus d’informations sur les modes de déploiement d’équipes, voir comprendre les modes de déploiement de Microsoft Teams, ainsi [que la coexistence et l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="80a48-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="80a48-111">Licence requise</span><span class="sxs-lookup"><span data-stu-id="80a48-111">License required</span></span>

<span data-ttu-id="80a48-112">Les utilisateurs doivent être compatibles voix entreprise pour configurer et utiliser le partage d’appel et le regroupement d’appels de groupe.</span><span class="sxs-lookup"><span data-stu-id="80a48-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="80a48-113">Pour plus d’informations sur le modèle de gestion des licences, voir gestion [des licences Office 365 pour Microsoft teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="80a48-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="80a48-114">Configurer le prélèvement d’appels de groupe</span><span class="sxs-lookup"><span data-stu-id="80a48-114">Configure group call pickup</span></span>

<span data-ttu-id="80a48-115">Pour configurer la fonction d’appel de groupe, un utilisateur configure d’abord un groupe d’appels (il est différent d’un groupe de sécurité ou d’un groupe Office 365), puis ajoute les utilisateurs avec lesquels vous souhaitez partager leurs appels.</span><span class="sxs-lookup"><span data-stu-id="80a48-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="80a48-116">Elle choisit ensuite un paramètre de sonnerie simultanée ou de transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="80a48-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="80a48-117">Pour plus d’informations et pour obtenir des procédures pas à pas, voir [transfert d’appel et sonnerie simultanée dans teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="80a48-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="80a48-118">Les préférences de création et de notification de groupe d’appels sont des fonctionnalités définies par l’utilisateur. les administrateurs n’ont pas besoin de configurer ces fonctionnalités pour leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="80a48-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="80a48-119">Les groupes d’appels ne peuvent pas être créés à partir de groupes de sécurité ou de groupes Office 365; ils doivent être créés dans Teams.</span><span class="sxs-lookup"><span data-stu-id="80a48-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="80a48-120">Les administrateurs doivent activer les groupes d’appels via le paramètre **TeamsCallingPolicy AllowCallGroups** pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="80a48-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="80a48-121">Les administrateurs peuvent uniquement contrôler si cet utilisateur peut configurer des groupes d’appels.</span><span class="sxs-lookup"><span data-stu-id="80a48-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="80a48-122">Une fois que le bit est défini sur true, les administrateurs ne peuvent pas empêcher l’utilisateur de configurer et d’ajouter les utilisateurs du groupe d’appels de leur choix.</span><span class="sxs-lookup"><span data-stu-id="80a48-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="80a48-123">Conditions</span><span class="sxs-lookup"><span data-stu-id="80a48-123">Limitations</span></span>

<span data-ttu-id="80a48-124">Un locataire peut contenir un maximum de groupes d’appels 32 768.</span><span class="sxs-lookup"><span data-stu-id="80a48-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="80a48-125">Il peut y avoir un maximum de 5 utilisateurs dans chaque groupe d’appels.</span><span class="sxs-lookup"><span data-stu-id="80a48-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="80a48-126">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="80a48-126">More information</span></span>

[<span data-ttu-id="80a48-127">Transfert d’appel et sonnerie simultanée dans teams</span><span class="sxs-lookup"><span data-stu-id="80a48-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)