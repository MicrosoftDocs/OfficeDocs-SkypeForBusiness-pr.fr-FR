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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Appeler le partage et de groupe ou d’appel permettre aux utilisateurs de partager les appels entrants avec vos collègues afin que les appels peuvent être capturés lorsque l’utilisateur n’est pas disponible.
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211822"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="bee09-103">Partage d’appel et prise d’appel de groupe dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bee09-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="bee09-104">L’appel de partage et le groupe d’appel pickup fonctionnalités de partage permettent aux utilisateurs de Microsoft Teams appels leur entrants avec vos collègues afin que les collègues peuvent répondre aux appels qui se produisent lorsque l’utilisateur n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="bee09-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="bee09-105">Groupe ou d’appel est moins gênants aux destinataires que les autres types d’appel de partage (comme le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer qu’ils veulent être averti d’un appel entrant partagé (via la notification audio et vidéo, visual uniquement, ou des bannières dans l’application équipes), et ils peuvent décider s’il faut répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="bee09-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="bee09-106">Pour partager des appels avec d’autres personnes, un utilisateur crée un groupe d’appel et ajoute les utilisateurs qu’ils souhaitent partager leurs appels avec.</span><span class="sxs-lookup"><span data-stu-id="bee09-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="bee09-107">Puis ils choisir une sonnerie simultanée ou transférer le paramètre.</span><span class="sxs-lookup"><span data-stu-id="bee09-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="bee09-108">Pour plus d’informations, voir [l’appel de sonnerie simultanée et de transfert dans les équipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="bee09-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bee09-109">Les utilisateurs, le propriétaire du groupe appel et membres du groupe d’appel doivent être en mode de déploiement équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="bee09-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="bee09-110">Pour plus d’informations sur les modes de déploiement d’équipes, voir [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="bee09-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="bee09-111">Licence requise</span><span class="sxs-lookup"><span data-stu-id="bee09-111">License required</span></span>

<span data-ttu-id="bee09-112">Les utilisateurs doivent être Enterprise Voice est activé pour configurer et utiliser le partage d’appel et de groupe ou d’appel.</span><span class="sxs-lookup"><span data-stu-id="bee09-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="bee09-113">Pour plus d’informations sur le modèle de licence, voir [Gestion des licences Office 365 pour les équipes Microsoft](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="bee09-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="bee09-114">Configurer le groupe ou d’appel</span><span class="sxs-lookup"><span data-stu-id="bee09-114">Configure group call pickup</span></span>

<span data-ttu-id="bee09-115">Pour configurer le groupe ou d’appel, un utilisateur configure d’abord un groupe d’appel (il n’est pas le même en tant qu’un groupe de sécurité ou un groupe d’Office 365), puis ajoute les utilisateurs qu’ils souhaitent partager leurs appels avec.</span><span class="sxs-lookup"><span data-stu-id="bee09-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="bee09-116">Ensuite, ils choisir une sonnerie simultanée ou paramètres de transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="bee09-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="bee09-117">Pour plus d’informations et procédures pas à pas, voir [appel sonnerie simultanée et de transfert dans les équipes](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="bee09-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="bee09-118">Appels création d’un groupe et notification préférences sont effectuées par les utilisateurs des fonctionnalités ; les administrateurs inutile de configurer ces fonctionnalités pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bee09-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="bee09-119">Groupes d’appel ne peut pas être créés à partir des groupes de sécurité ou Office 365 ; ils doivent être créés dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="bee09-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="bee09-120">Administrateurs doivent activer les groupes d’appel via le paramètre **TeamsCallingPolicy AllowCallGroups** pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bee09-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="bee09-121">Les administrateurs peuvent contrôler uniquement si cet utilisateur peut configurer des groupes d’appel.</span><span class="sxs-lookup"><span data-stu-id="bee09-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="bee09-122">Une fois que le bit est défini sur true, administrateurs ne peuvent pas empêcher les utilisateurs de configuration et en ajoutant les utilisateurs de groupe d’appel de leur choix.</span><span class="sxs-lookup"><span data-stu-id="bee09-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="bee09-123">Limitations</span><span class="sxs-lookup"><span data-stu-id="bee09-123">Limitations</span></span>

<span data-ttu-id="bee09-124">Un client peut contenir un maximum de groupes d’appel 32 768.</span><span class="sxs-lookup"><span data-stu-id="bee09-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="bee09-125">Il peut y avoir un maximum de 5 utilisateurs de chaque groupe d’appel.</span><span class="sxs-lookup"><span data-stu-id="bee09-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="bee09-126">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="bee09-126">More information</span></span>

[<span data-ttu-id="bee09-127">Transfert d’appel et la sonnerie simultanée dans les équipes</span><span class="sxs-lookup"><span data-stu-id="bee09-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)