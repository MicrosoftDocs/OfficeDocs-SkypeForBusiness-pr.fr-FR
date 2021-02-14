---
title: Partenaires fédérés Skype Room System et Skype Entreprise
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lisez cette rubrique pour découvrir comment configurer Skype Room System pour les partenaires fédérés Skype Entreprise.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820804"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="63efa-103">Partenaires fédérés Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="63efa-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="63efa-104">Lisez cette rubrique pour découvrir comment configurer Skype Room System pour les partenaires fédérés Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="63efa-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="63efa-105">Partenaires fédérés Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="63efa-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="63efa-106">Skype Room System s’appuie sur le lien Participer à une réunion Skype Entreprise dans la demande de réunion de calendrier.</span><span class="sxs-lookup"><span data-stu-id="63efa-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="63efa-107">Le lien de connexion se trouve généralement dans le corps d’une demande de réunion.</span><span class="sxs-lookup"><span data-stu-id="63efa-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="63efa-108">Toutefois, Skype Room System dépend de ce lien pour être présent dans les propriétés MAPI du message.</span><span class="sxs-lookup"><span data-stu-id="63efa-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="63efa-109">Lorsque cette demande de réunion est envoyée à des organisations distantes (partenaires fédérés Skype Entreprise), par défaut le système Skype Room de l’organisation distante n’affiche pas le lien de la réunion dans le calendrier.</span><span class="sxs-lookup"><span data-stu-id="63efa-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="63efa-110">En fait, tous les utilisateurs Outlook de l’organisation distante ne pourront pas participer à la réunion Skype Entreprise en cliquant avec le bouton droit sur l’élément de calendrier ou à partir du rappel de réunion.</span><span class="sxs-lookup"><span data-stu-id="63efa-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="63efa-111">Ils doivent ouvrir l’invitation à une réunion et cliquer sur Participer à une réunion Skype Entreprise dans le corps du message.</span><span class="sxs-lookup"><span data-stu-id="63efa-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="63efa-112">La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour mettre en package des informations pour l’envoi de messages sur Internet.</span><span class="sxs-lookup"><span data-stu-id="63efa-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="63efa-113">Cette méthode, appelée TNEF (Transport Neutral Encapsulation Format), est désactivée par défaut pour les messages envoyés en externe à partir d’une organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="63efa-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="63efa-114">Pour qu’un lien de rejoindre une réunion apparaisse sur un système Skype Room distant, l’organisation d’envoi doit activer le TNEF à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="63efa-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="63efa-115">Une fois le format TNEF activé pour l’organisation distante, tout message envoyé via Internet à l’organisation est envoyé en tant que pièce jointe au format TNEF.</span><span class="sxs-lookup"><span data-stu-id="63efa-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="63efa-116">Avec le TNEF activé, lorsqu’une demande de réunion Skype Entreprise est envoyée au partenaire fédéré Skype Entreprise, Skype Room System peut restituer la réunion Skype Entreprise et les utilisateurs distants peuvent participer aux réunions Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="63efa-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
