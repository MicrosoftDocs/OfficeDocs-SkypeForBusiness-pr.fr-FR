---
title: Partenaires fédérés de Skype Room System et Skype Entreprise
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
ms.openlocfilehash: 8ded7ba9be24cf1ac700be0ead1c7e0c3637becd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002994"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="1e2bf-103">Partenaires fédérés de Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="1e2bf-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="1e2bf-104">Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="1e2bf-105">Partenaires fédérés de Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="1e2bf-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="1e2bf-106">Le système de salle Skype repose sur le lien participer à une réunion Skype entreprise dans la demande de réunion du calendrier.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="1e2bf-107">Le lien de participation se trouve généralement dans le corps d’une demande de réunion.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="1e2bf-108">En revanche, le système de salle Skype dépend du lien que vous souhaitez présenter dans les propriétés MAPI du message.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="1e2bf-109">Lorsque cette demande de réunion est envoyée à des organisations distantes (partenaires fédérés Skype entreprise), par défaut, le système de salle Skype de l’organisation distante ne montre pas le lien de participation à la réunion dans le calendrier.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="1e2bf-110">En fait, les utilisateurs Outlook de l’organisation à distance ne seront pas en mesure de rejoindre la réunion Skype entreprise en cliquant avec le bouton droit sur l’élément de calendrier ou à partir du rappel de réunion.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="1e2bf-111">Elle doit ouvrir l’invitation à la réunion et cliquer sur participer à une réunion Skype entreprise dans le corps du message.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="1e2bf-112">La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour regrouper des informations lorsque des messages sont envoyés sur Internet.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="1e2bf-113">Cette méthode, appelée format Transport Neutral Encapsulation (TNEF), est désactivée par défaut pour les messages d’une organisation Exchange envoyés en externe.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="1e2bf-114">Pour qu’un lien de participation à une réunion apparaisse dans un système de salle Skype distant, l’organisation d’expédition doit activer TNEF en utilisant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1e2bf-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="1e2bf-115">Après l’activation de la TNEF pour l’organisation, tous les messages envoyés sur Internet à l’organisation sont envoyés en tant que pièce jointe au format TNEF.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="1e2bf-116">Lorsque TNEF est activé, lors de l’envoi d’une demande de réunion Skype entreprise au partenaire fédéré Skype entreprise, le système de salle Skype est en mesure d’effectuer la participation à une réunion Skype entreprise et les utilisateurs distants pourront participer à des réunions Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1e2bf-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
