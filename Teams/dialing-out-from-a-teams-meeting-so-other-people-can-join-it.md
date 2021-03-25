---
title: Appel sortant d’une réunion pour que d’autres personnes y participent
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Les organisateurs de réunions peuvent découvrir comment appeler à l’aide de l’application Teams pour laisser d’autres personnes participer à la réunion à l’aide de leur téléphone.
ms.openlocfilehash: 55cbd5ccc9e9c364bcb829d9a392f61cbdd2f7f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119283"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="16ad1-103">Appel sortant depuis une réunion Microsoft Teams pour permettre à d'autres personnes d’y participer</span><span class="sxs-lookup"><span data-stu-id="16ad1-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="16ad1-104">En tant qu’organisateur de la réunion, vous pouvez appeler à l’aide de l’application Teams pour laisser d’autres personnes participer à la réunion à l’aide de leur téléphone.</span><span class="sxs-lookup"><span data-stu-id="16ad1-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="16ad1-105">Lorsque vous dial out to someone, we recommend you do so using their full phone numbers (including the country/region code - E.164 format).</span><span class="sxs-lookup"><span data-stu-id="16ad1-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="16ad1-106">Notez que :</span><span class="sxs-lookup"><span data-stu-id="16ad1-106">Please note that:</span></span>

- <span data-ttu-id="16ad1-107">Vous ne pouvez appeler un appel sortant que si vous participez à une réunion en utilisant Teams.</span><span class="sxs-lookup"><span data-stu-id="16ad1-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="16ad1-108">L’organisateur de la réunion a été activé pour l’audioconférence OU, dans le cas où aucune licence d’audioconférence n’est attribuée, est autorisé à passer des appels vers le réseau téléphonique commuté public via des plans d’appel en ligne ou un routage direct.</span><span class="sxs-lookup"><span data-stu-id="16ad1-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="16ad1-109">L’organisateur de la réunion se vu accorder une stratégie d’appel sortant en ligne qui autorise l’appel sortant [des conférences](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="16ad1-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="16ad1-110">Pour que l’appel sortant fonctionne, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="16ad1-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="16ad1-111">**Étape 1 :** Dans la réunion, utilisez la capture d’écran **Ajouter** des personnes de l’option Ajouter des personnes pour ![ composer un numéro de ](media/add-people-button.png) téléphone.</span><span class="sxs-lookup"><span data-stu-id="16ad1-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="16ad1-112">**Étape 2 :** Entrez le numéro de téléphone complet, y compris l’code du pays/de la région dans la zone Inviter une **personne ou composez un** numéro.</span><span class="sxs-lookup"><span data-stu-id="16ad1-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Capture d’écran de la zone Inviter une personne ou composer un numéro](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="16ad1-114">Pays et régions pris en charge</span><span class="sxs-lookup"><span data-stu-id="16ad1-114">Supported countries and regions</span></span>

<span data-ttu-id="16ad1-115">La mise en conférence n'est disponible que vers certains pays ou certaines régions.</span><span class="sxs-lookup"><span data-stu-id="16ad1-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="16ad1-116">Pour obtenir la liste complète, consultez la disponibilité des pays et régions pour les plans [d’audioconférence et d’appel.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="16ad1-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="16ad1-117">Autoriser les utilisateurs à composer le numéro</span><span class="sxs-lookup"><span data-stu-id="16ad1-117">Allow users to dial in</span></span>

<span data-ttu-id="16ad1-118">Si vous recherchez des instructions sur la manière de laisser vos utilisateurs se composer pour se rendre à une réunion Teams, veuillez consulter les numéros de téléphone pour l’audioconférence [dans Microsoft Teams.](phone-numbers-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="16ad1-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="16ad1-119">Vous souhaitez en savoir plus sur l’audioconférence ?</span><span class="sxs-lookup"><span data-stu-id="16ad1-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="16ad1-120">Essayer ou acheter l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="16ad1-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="16ad1-121">Licences de module complémentaire Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16ad1-121">Microsoft Teams add-on licensing</span></span>](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)