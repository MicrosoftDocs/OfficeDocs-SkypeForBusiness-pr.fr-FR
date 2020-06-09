---
title: Partage d’appel et prise d’appel de groupe
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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Les appels de partage et de groupe permettent aux utilisateurs de partager des appels entrants avec des collègues, de sorte que les appels puissent être capturés quand l’utilisateur n’est pas disponible.
ms.openlocfilehash: 0e21f8ec8b9d913568b87a41b70261ac917260e2
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638853"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="6eb34-103">Partage d’appel et prise d’appel de groupe dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6eb34-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="6eb34-104">Les fonctionnalités de partage d’appel et de cueillette de groupe de Microsoft teams permettent aux utilisateurs de partager leurs appels entrants avec leurs collègues pour permettre aux collègues de répondre aux appels qui se produisent alors que l’utilisateur n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="6eb34-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="6eb34-105">Le regroupement des appels de groupe est moins gênant pour les destinataires que les autres formes de partage d’appel (par exemple, le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer le mode de notification d’un appel partagé entrant (par le biais d’une notification audio et visuelle, d’un élément visuel uniquement ou d’une bannière dans l’application Teams), et ils peuvent</span><span class="sxs-lookup"><span data-stu-id="6eb34-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="6eb34-106">Pour partager les appels, un utilisateur crée un groupe d’appels et ajoute les utilisateurs avec lesquels vous souhaitez partager leurs appels.</span><span class="sxs-lookup"><span data-stu-id="6eb34-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="6eb34-107">Ils choisissent alors un paramètre de sonnerie ou de transfert simultané.</span><span class="sxs-lookup"><span data-stu-id="6eb34-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="6eb34-108">Pour [en savoir plus, voir transfert d’appel et sonnerie simultanée dans teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="6eb34-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6eb34-109">Les utilisateurs, le propriétaire du groupe d’appels et les membres du groupe d’appels doivent être en mode déploiement d’équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="6eb34-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="6eb34-110">Pour plus d’informations sur les modes de déploiement d’équipes, voir comprendre les modes de déploiement de [Microsoft Teams, ainsi que la coexistence et l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6eb34-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6eb34-111">Licence requise</span><span class="sxs-lookup"><span data-stu-id="6eb34-111">License required</span></span>

<span data-ttu-id="6eb34-112">Les utilisateurs doivent être compatibles voix entreprise pour configurer et utiliser le partage d’appel et le regroupement d’appels de groupe.</span><span class="sxs-lookup"><span data-stu-id="6eb34-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="6eb34-113">Pour plus d’informations sur le modèle de gestion des licences, voir [Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="6eb34-113">For additional details on the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="6eb34-114">Configurer le prélèvement d’appels de groupe</span><span class="sxs-lookup"><span data-stu-id="6eb34-114">Configure group call pickup</span></span>

<span data-ttu-id="6eb34-115">Pour configurer la fonction de cueillette d’appel de groupe, un utilisateur configure d’abord un groupe d’appels (ce qui n’est pas le même qu’un groupe de sécurité ou un groupe Microsoft 365), puis ajoute les utilisateurs avec lesquels vous souhaitez partager leurs appels.</span><span class="sxs-lookup"><span data-stu-id="6eb34-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 Group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="6eb34-116">Elle choisit ensuite un paramètre de sonnerie simultanée ou de transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="6eb34-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="6eb34-117">Pour plus d’informations et pour obtenir des procédures pas à pas, voir [transfert d’appel et sonnerie simultanée dans teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="6eb34-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="6eb34-118">Les préférences de création et de notification de groupe d’appels sont des fonctionnalités définies par l’utilisateur. les administrateurs n’ont pas besoin de configurer ces fonctionnalités pour leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6eb34-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="6eb34-119">Les groupes d’appels ne peuvent pas être créés à partir de groupes de sécurité ou de groupes Microsoft 365 ; ils doivent être créés dans Teams.</span><span class="sxs-lookup"><span data-stu-id="6eb34-119">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="6eb34-120">Les administrateurs doivent activer les groupes d’appels via le paramètre **TeamsCallingPolicy AllowCallGroups** pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6eb34-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="6eb34-121">Les administrateurs peuvent également l’activer via le portail d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="6eb34-121">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="6eb34-122">Par ailleurs, l’utilisateur configuré peut également configurer directement ses groupes d’appels via le client.</span><span class="sxs-lookup"><span data-stu-id="6eb34-122">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="6eb34-123">Les utilisateurs d’un administrateur ou d’un utilisateur final ne peuvent pas bloquer la configuration entre eux, mais le portail d’administration teams et le client teams doivent afficher cette relation avec précision dans les deux emplacements.</span><span class="sxs-lookup"><span data-stu-id="6eb34-123">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="6eb34-124">Important : lorsque les administrateurs désactivent les groupes d’appels pour les utilisateurs (une fois qu’il est activé et que les relations du groupe d’appels sont configurées), les administrateurs doivent nettoyer les relations du groupe d’appels pour les utilisateurs dans le centre d’administration teams pour éviter un routage incorrect.</span><span class="sxs-lookup"><span data-stu-id="6eb34-124">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="6eb34-125">Conditions</span><span class="sxs-lookup"><span data-stu-id="6eb34-125">Limitations</span></span>

<span data-ttu-id="6eb34-126">Un locataire peut contenir un maximum de groupes d’appels 32 768.</span><span class="sxs-lookup"><span data-stu-id="6eb34-126">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="6eb34-127">Chaque groupe d’appels peut comporter un maximum de 25 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6eb34-127">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="6eb34-128">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="6eb34-128">More information</span></span>

[<span data-ttu-id="6eb34-129">Transfert d’appel et sonnerie simultanée dans teams</span><span class="sxs-lookup"><span data-stu-id="6eb34-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
