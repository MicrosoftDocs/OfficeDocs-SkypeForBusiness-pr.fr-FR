---
title: Partage d’appel et prise d’appel de groupe
ms.author: serdars
author: SerdarSoysal
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
description: Le partage d’appel et le regroupement d’appels de groupe permet aux utilisateurs de partager des appels entrants avec des collègues afin de pouvoir capturer les appels en cas d’indisponibilité de l’utilisateur.
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717835"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="719f8-103">Partage d’appel et prise d’appel de groupe dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="719f8-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="719f8-104">Les fonctionnalités de partage d’appel et d’appel de groupe de Microsoft Teams permet aux utilisateurs de partager leurs appels entrants avec des collègues afin que leurs collègues peuvent répondre aux appels qui se produisent alors que l’utilisateur n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="719f8-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="719f8-105">Le regroupement d’appels est moins perturbateur pour les destinataires que d’autres formes de partage d’appel (telles que le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer la manière dont ils souhaitent être informés d’un appel partagé entrant (via une notification audio et visuelle, une bannière uniquement visuelle ou une bannière dans l’application Teams), et ils peuvent décider d’y répondre ou non.</span><span class="sxs-lookup"><span data-stu-id="719f8-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="719f8-106">Pour partager des appels avec d’autres personnes, un utilisateur crée un groupe d’appels et ajoute les utilisateurs avec qui ils souhaitent partager leurs appels.</span><span class="sxs-lookup"><span data-stu-id="719f8-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="719f8-107">Ils choisissent ensuite un paramètre de sonnerie ou de avance simultanée.</span><span class="sxs-lookup"><span data-stu-id="719f8-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="719f8-108">Pour [plus d’informations, voir](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) Le Teams d’appel et la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="719f8-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="719f8-109">Notez que les appareils mobiles seront avertis uniquement s’ils sont réglés pour la bannière et la sonnerie.</span><span class="sxs-lookup"><span data-stu-id="719f8-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="719f8-110">Les utilisateurs, le propriétaire du groupe d’appels et les membres du groupe d’appels doivent être en Teams seul mode de déploiement.</span><span class="sxs-lookup"><span data-stu-id="719f8-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="719f8-111">Pour plus d’informations sur Teams modes de déploiement, voir Comprendre Microsoft Teams et Skype Entreprise coexistence et [l’interopérabilité.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="719f8-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="719f8-112">Licence requise</span><span class="sxs-lookup"><span data-stu-id="719f8-112">License required</span></span>

<span data-ttu-id="719f8-113">Les utilisateurs doivent avoir une licence Microsoft Teams Système téléphonique pour configurer et utiliser le partage d’appels et le regroupement d’appels.</span><span class="sxs-lookup"><span data-stu-id="719f8-113">Users must be assigned a Microsoft Teams Phone System license to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="719f8-114">Pour plus d’informations sur le modèle de licence, consultez les informations dont vous [obtenez Système téléphonique.](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)</span><span class="sxs-lookup"><span data-stu-id="719f8-114">For additional details on the licensing model, see [Here's what you get with Phone System](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="719f8-115">Configurer le regroupement d’appels de groupe</span><span class="sxs-lookup"><span data-stu-id="719f8-115">Configure group call pickup</span></span>

<span data-ttu-id="719f8-116">Pour configurer le regroupement d’appels de groupe, un utilisateur configure d’abord un groupe d’appels (ce groupe n’est pas identique à un groupe de sécurité ou à un groupe Microsoft 365), puis ajoute les utilisateurs avec qui ils souhaitent partager leurs appels.</span><span class="sxs-lookup"><span data-stu-id="719f8-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="719f8-117">Ils choisissent ensuite un paramètre de sonnerie simultanée ou de avance d’appel.</span><span class="sxs-lookup"><span data-stu-id="719f8-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="719f8-118">Pour plus d’informations et des procédures pas à pas, voir Le forwarding d’appel et [la sonnerie simultanée Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="719f8-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="719f8-119">Les préférences de création et de notification des groupes d’appels sont des fonctionnalités pilotées par l’utilisateur. administrateurs n’ont pas à configurer ces fonctionnalités pour leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="719f8-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="719f8-120">Les groupes d’appels ne peuvent pas être créés à partir de groupes de sécurité ou Microsoft 365 groupes de sécurité. ils doivent être créés dans Teams.</span><span class="sxs-lookup"><span data-stu-id="719f8-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="719f8-121">Les administrateurs doivent activer les groupes d’appels via le paramètre **TeamsCallingPolicy AllowCallGroups** d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="719f8-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="719f8-122">Les administrateurs peuvent également activer ce système via Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="719f8-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="719f8-123">En outre, l’utilisateur configuré peut également configurer ses groupes d’appels via le client directement.</span><span class="sxs-lookup"><span data-stu-id="719f8-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="719f8-124">Les administrateurs ou les utilisateurs finaux ne peuvent pas bloquer la configuration l’un après l’autre, mais Teams portail d’administration et le client Teams doivent afficher cette relation avec précision aux deux endroits.</span><span class="sxs-lookup"><span data-stu-id="719f8-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="719f8-125">Important : lorsque les administrateurs désactiver les groupes d’appels pour les utilisateurs (après l’avoir été désactivé et les relations de groupe d’appels sont configurées), les administrateurs doivent nettoyer les relations de groupe d’appels pour les utilisateurs dans le Centre d’administration Teams pour éviter un routage d’appel incorrect.</span><span class="sxs-lookup"><span data-stu-id="719f8-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="719f8-126">Limites</span><span class="sxs-lookup"><span data-stu-id="719f8-126">Limitations</span></span>

<span data-ttu-id="719f8-127">Chaque groupe d’appels configuré peut avoir un maximum de 25 utilisateurs ou 32 768 caractères.</span><span class="sxs-lookup"><span data-stu-id="719f8-127">Each configured call group can have a maximum of 25 users or 32,768 characters.</span></span> 

## <a name="more-information"></a><span data-ttu-id="719f8-128">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="719f8-128">More information</span></span>

[<span data-ttu-id="719f8-129">Call forwarding and simultaneous ring in Teams</span><span class="sxs-lookup"><span data-stu-id="719f8-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
