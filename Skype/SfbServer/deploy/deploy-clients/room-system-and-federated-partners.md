---
title: Partenaires fédérés de Skype Room System et Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
ms.openlocfilehash: 040af495217217b3bfd10fb577b7194df354e027
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="f91da-103">Partenaires fédérés de Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f91da-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="f91da-104">Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.</span><span class="sxs-lookup"><span data-stu-id="f91da-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="f91da-105">Partenaires fédérés de Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f91da-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="f91da-106">Système de chambre de Skype s’appuie sur le Skype joindre pour le lien de réunion d’affaires dans la demande de réunion du calendrier.</span><span class="sxs-lookup"><span data-stu-id="f91da-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="f91da-107">Le lien de participation se trouve généralement dans le corps d’une demande de réunion.</span><span class="sxs-lookup"><span data-stu-id="f91da-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="f91da-108">Toutefois, Skype espace système dépend de ce lien dans les propriétés du message MAPI.</span><span class="sxs-lookup"><span data-stu-id="f91da-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="f91da-109">Lors de cette réunion est envoyée aux organisations à distance (Skype pour partenaires fédérés), par défaut ne de Skype espace système de l’organisation à distance affiche pas lier de la jointure de la réunion dans le calendrier.</span><span class="sxs-lookup"><span data-stu-id="f91da-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="f91da-110">En fait, tous les utilisateurs d’Outlook de l’organisation à distance ne pourront pas participer à la Skype pour une réunion d’affaires avec un clic droit du calendrier article ou à partir de dans le rappel de réunion.</span><span class="sxs-lookup"><span data-stu-id="f91da-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="f91da-111">Ils doivent ouvrir l’invitation à une réunion et cliquez sur Joindre un Skype pour une réunion d’affaires dans le corps du message.</span><span class="sxs-lookup"><span data-stu-id="f91da-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="f91da-112">La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour regrouper des informations lorsque des messages sont envoyés sur Internet.</span><span class="sxs-lookup"><span data-stu-id="f91da-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="f91da-113">Cette méthode, appelée format Transport Neutral Encapsulation (TNEF), est désactivée par défaut pour les messages d’une organisation Exchange envoyés en externe.</span><span class="sxs-lookup"><span data-stu-id="f91da-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="f91da-114">Pour une réunion lien de jointure doit apparaître sur un système distant salle de Skype, l’organisation émettrice doit activer TNEF à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f91da-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="f91da-115">Après l’activation de la TNEF pour l’organisation, tous les messages envoyés sur Internet à l’organisation sont envoyés en tant que pièce jointe au format TNEF.</span><span class="sxs-lookup"><span data-stu-id="f91da-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="f91da-116">Avec le format TNEF est activée, lorsqu’un Skype pour entreprise demande de réunion envoyée à la Skype des partenaires fédérés, Skype espace système pourront rendre la jointure Skype pour une réunion d’affaires et les utilisateurs distants pourront joindre Skype pour les réunions d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f91da-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 