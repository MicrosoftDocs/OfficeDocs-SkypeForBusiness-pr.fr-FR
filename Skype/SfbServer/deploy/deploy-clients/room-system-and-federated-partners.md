---
title: Partenaires fédérés de Skype Room System et Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.
ms.openlocfilehash: e954bf5d7586c651d9d045b2d428f86f01de8a30
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219387"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="82650-103">Partenaires fédérés de Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="82650-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="82650-104">Consultez cette rubrique pour obtenir plus d’informations sur la façon de configurer Skype Room System pour Skype Entreprise pour les entreprises partenaires fédérées.</span><span class="sxs-lookup"><span data-stu-id="82650-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="82650-105">Partenaires fédérés de Skype Room System et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="82650-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="82650-106">Système de salle Skype repose sur la Skype joindre pour le lien de la réunion d’entreprise dans la demande de réunion du calendrier.</span><span class="sxs-lookup"><span data-stu-id="82650-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="82650-107">Le lien de participation se trouve généralement dans le corps d’une demande de réunion.</span><span class="sxs-lookup"><span data-stu-id="82650-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="82650-108">Toutefois, Skype salle système dépend de ce lien pour être présents dans les propriétés MAPI du message.</span><span class="sxs-lookup"><span data-stu-id="82650-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="82650-109">Lorsque cette réunion est envoyée pour les organisations à distance (Skype pour les partenaires fédérés), par défaut sera Skype salle système de l’organisation distante pas la participation aux réunions lien dans le calendrier pour afficher.</span><span class="sxs-lookup"><span data-stu-id="82650-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="82650-110">En fait, les utilisateurs d’Outlook dans l’organisation distante ne pourront pas participer à la Skype pour la réunion d’entreprise en un clic droit du calendrier, élément ou de dans le rappel de réunion.</span><span class="sxs-lookup"><span data-stu-id="82650-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="82650-111">Ils doivent invitation à la réunion, cliquez sur Skype joindre pour Business réunion dans le corps du message.</span><span class="sxs-lookup"><span data-stu-id="82650-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="82650-112">La raison de cette limitation est qu’Outlook et Microsoft Exchange n’utilisent pas de méthode spéciale pour regrouper des informations lorsque des messages sont envoyés sur Internet.</span><span class="sxs-lookup"><span data-stu-id="82650-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="82650-113">Cette méthode, appelée format Transport Neutral Encapsulation (TNEF), est désactivée par défaut pour les messages d’une organisation Exchange envoyés en externe.</span><span class="sxs-lookup"><span data-stu-id="82650-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="82650-114">Pour une réunion lien participer à une doit apparaître sur un système de salle Skype à distance, l’organisation émettrice doit activer TNEF à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="82650-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="82650-115">Après l’activation de la TNEF pour l’organisation, tous les messages envoyés sur Internet à l’organisation sont envoyés en tant que pièce jointe au format TNEF.</span><span class="sxs-lookup"><span data-stu-id="82650-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="82650-116">Avec TNEF activé, lorsqu’un Skype pour une demande de réunion Business est envoyé à la Skype des partenaires fédérés, Skype salle système pourront restituer la jointure Skype pour une réunion d’affaires et les utilisateurs distants pourront participer à Skype pour les réunions d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="82650-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 