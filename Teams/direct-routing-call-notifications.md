---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notification d’appel de routage direct
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341804"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="e8716-103">Gérer les notifications d’appels</span><span class="sxs-lookup"><span data-stu-id="e8716-103">Manage call notifications</span></span>

<span data-ttu-id="e8716-104">Cet article décrit comment gérer les notifications d’appel pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e8716-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="e8716-105">Vous pouvez configurer des points de terminaison d’appel avec Teams et un système PBX (Private Branch Exchange) ou SBC (Session Border Controller) tiers.</span><span class="sxs-lookup"><span data-stu-id="e8716-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="e8716-106">Cela est utile, par exemple, si vous voulez envoyer un appel vers les téléphones mobiles et de bureau d’un utilisateur en même temps.</span><span class="sxs-lookup"><span data-stu-id="e8716-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="e8716-107">Dans le diagramme suivant, l’utilisateur Irena a deux points de terminaison :</span><span class="sxs-lookup"><span data-stu-id="e8716-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="e8716-108">Un point de terminaison Teams</span><span class="sxs-lookup"><span data-stu-id="e8716-108">A Teams endpoint</span></span>
- <span data-ttu-id="e8716-109">Un téléphone SIP connecté à un SBC tiers</span><span class="sxs-lookup"><span data-stu-id="e8716-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="e8716-110">Lorsqu’un appel arrive, le SBC dus au routage direct Phone System et au SBC tiers.</span><span class="sxs-lookup"><span data-stu-id="e8716-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Diagramme montrant des points de terminaison Teams dus](media/direct-routing-call-notification-1.png)

<span data-ttu-id="e8716-112">Si l’appel est accepté sur la fork 2 (par le SBC tiers), Teams génère une notification « Appel manqué ».</span><span class="sxs-lookup"><span data-stu-id="e8716-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="e8716-113">Vous pouvez empêcher la notification « Appel manqué » en configurant le SBC de manière à envoyer une annulation dans la fork 1 comme suit :</span><span class="sxs-lookup"><span data-stu-id="e8716-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="e8716-114">RAISON : SIP; cause=200;texte"Appel effectué ailleurs »</span><span class="sxs-lookup"><span data-stu-id="e8716-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="e8716-115">Notez que l’appel ne sera pas enregistré dans les enregistrements des détails d’appel de Microsoft Phone System en tant qu’appel réussi.</span><span class="sxs-lookup"><span data-stu-id="e8716-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="e8716-116">L’appel sera inscrit comme une « tentative » avec le code SIP final « 487 », le sous-code Microsoft final « 540200 » et la phrase du code SIP final « Appel effectué ailleurs ».</span><span class="sxs-lookup"><span data-stu-id="e8716-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="e8716-117">(Pour afficher les enregistrements des détails des appels, allez sur le portail d’administration de Teams, les rapports d’analyse et de rapport, les rapports d’utilisation et sélectionnez Utilisation PSTN.)</span><span class="sxs-lookup"><span data-stu-id="e8716-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="e8716-118">Le diagramme ci-dessous illustre le flux SIP de la fork 1, explique le flux d’appels et la RAISON attendue dans le message Annuler.</span><span class="sxs-lookup"><span data-stu-id="e8716-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Diagramme montrant des points de terminaison Teams dus](media/direct-routing-call-notification-2.png)
