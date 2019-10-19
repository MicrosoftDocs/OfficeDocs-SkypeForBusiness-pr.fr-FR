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
description: Notification d’appel de routage direct
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 07efe11d304107a5a8606a07f5d1c2a7a130bc0b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37595341"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="20958-103">Gérer les notifications d’appel</span><span class="sxs-lookup"><span data-stu-id="20958-103">Manage call notifications</span></span>

<span data-ttu-id="20958-104">Cet article décrit comment gérer les notifications d’appel pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="20958-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="20958-105">Vous pouvez configurer des points de terminaison d’appel vers les deux équipes et vers un système de contrôle de succursale privée ou un contrôleur de bordure de session (SBC) tiers.</span><span class="sxs-lookup"><span data-stu-id="20958-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="20958-106">Cette fonction est utile, par exemple, si vous voulez envoyer un appel vers les téléphones mobiles et de bureau d’un utilisateur en même temps.</span><span class="sxs-lookup"><span data-stu-id="20958-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="20958-107">Dans le diagramme suivant, l’utilisateur Irena possède deux points de terminaison :</span><span class="sxs-lookup"><span data-stu-id="20958-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="20958-108">Un point de terminaison d’équipes</span><span class="sxs-lookup"><span data-stu-id="20958-108">A Teams endpoint</span></span>
- <span data-ttu-id="20958-109">Téléphone SIP connecté à une SBC tierce</span><span class="sxs-lookup"><span data-stu-id="20958-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="20958-110">Lorsqu’un appel arrive, le SBC dévie l’appel entre le routage direct du système téléphonique et le SBC tiers.</span><span class="sxs-lookup"><span data-stu-id="20958-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Diagramme montrant les points de terminaison d’équipes branches](media/direct-routing-call-notification-1.png)

<span data-ttu-id="20958-112">Si l’appel est accepté sur la fourche 2 (par la SBC tierce), teams générera une notification d’appel manqué.</span><span class="sxs-lookup"><span data-stu-id="20958-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="20958-113">Vous pouvez empêcher la notification d’appel manqué en configurant l’SBC pour qu’il envoie une annulation sur Fork 1 comme suit :</span><span class="sxs-lookup"><span data-stu-id="20958-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="20958-114">RAISON : SIP ; cause = 200 ; texte "appel terminé ailleurs"</span><span class="sxs-lookup"><span data-stu-id="20958-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="20958-115">Notez que l’appel n’est pas enregistré dans les enregistrements des détails des appels du système Microsoft Phone en tant qu’appel réussi.</span><span class="sxs-lookup"><span data-stu-id="20958-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="20958-116">L’appel sera enregistré en tant que « tentative » avec le code SIP final « 487 », le sous-code final de Microsoft « 540200 » et l’expression de code SIP finale».</span><span class="sxs-lookup"><span data-stu-id="20958-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>   <span data-ttu-id="20958-117">(Pour consulter les enregistrements des détails des appels, accédez au portail d’administration Teams, aux analyses et aux rapports, rapports d’utilisation, et sélectionnez utilisation de offre PSTN.)</span><span class="sxs-lookup"><span data-stu-id="20958-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSNT Usage.)</span></span>


<span data-ttu-id="20958-118">Le diagramme ci-dessous illustre l’échelle SIP pour la fourche 1, décrit le flux d’appels et la raison attendue du message d’annulation.</span><span class="sxs-lookup"><span data-stu-id="20958-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Diagramme montrant les points de terminaison d’équipes branches](media/direct-routing-call-notification-2.png)
