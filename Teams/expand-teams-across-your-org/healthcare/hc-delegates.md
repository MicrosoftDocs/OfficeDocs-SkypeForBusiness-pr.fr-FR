---
title: Délégation de messages
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Découvrez comment un utilisateur ayant le statut Absent(e) ou Ne pas déranger peut définir explicitement un autre utilisateur comme délégué dans son message d’état.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790466"
---
# <a name="message-delegation"></a><span data-ttu-id="d70e3-103">Délégation de messages</span><span class="sxs-lookup"><span data-stu-id="d70e3-103">Message delegation</span></span>

<span data-ttu-id="d70e3-104">Un utilisateur peut déjà définir explicitement son statut sur Absent(0) ou Ne pas déranger et fournir un texte personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d70e3-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="d70e3-105">La fonctionnalité de délégation de message fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="d70e3-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="d70e3-106">Un utilisateur @username mentionne un autre utilisateur dans une partie d’un message texte, ce qui suggère que, bien qu’indisponibles, les personnes qui souhaitent les contacter à la place contactent l'@username utilisateur mentionné.</span><span class="sxs-lookup"><span data-stu-id="d70e3-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="d70e3-107">La personne désignée comme délégué est notifiée qu’elle a été désignée comme délégué.</span><span class="sxs-lookup"><span data-stu-id="d70e3-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="d70e3-108">Une personne qui essaie de contacter le premier utilisateur peut ensuite pointer sur le délégué désigné et envoyer facilement un message au délégué.</span><span class="sxs-lookup"><span data-stu-id="d70e3-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="d70e3-109">Il s’agit d’un processus initié par l’utilisateur dans le client, et aucune implication de l’administrateur n’est requise pour activer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d70e3-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="d70e3-110">Scénario d’utilisation de la délégation dans les soins de santé</span><span class="sxs-lookup"><span data-stu-id="d70e3-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="d70e3-111">*Exemple d’utilisation sans définir de délégués :*  Le dr.Nt Piccio est en appel au service de radiologye.</span><span class="sxs-lookup"><span data-stu-id="d70e3-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="d70e3-112">Il reçoit un appel personnel urgent et doit s’éloigner pour les prochaines heures.</span><span class="sxs-lookup"><span data-stu-id="d70e3-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="d70e3-113">Il demande à l’un de ses pairs du service de radioologie, Dr. Lena Ehrle, de le couvrir pendant son absence.</span><span class="sxs-lookup"><span data-stu-id="d70e3-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="d70e3-114">Il place son pager à l’ami ami. Ehrle, qui est à l’écoute des messages urgents et des appels ping sur le pageur, et qui y répond au nom du Dr. Piccio, en plus de ses responsabilités actuelles.</span><span class="sxs-lookup"><span data-stu-id="d70e3-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="d70e3-115">D’autres membres de l’équipe peuvent ne pas se rendre compte du fait que la délégation informelle s’est produite, et une confusion se produit avec les soins d’un patient.</span><span class="sxs-lookup"><span data-stu-id="d70e3-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="d70e3-116">*Exemple d’utilisation avec définition de délégués :* Le dr.Nt Piccio est en appel au service de radiologye.</span><span class="sxs-lookup"><span data-stu-id="d70e3-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="d70e3-117">Il reçoit un appel personnel urgent et doit s’éloigner pour les prochaines heures.</span><span class="sxs-lookup"><span data-stu-id="d70e3-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="d70e3-118">Il demande à l’un de ses pairs du service de radiologye, Dr. Lena Ehrle, de le couvrir pendant son absence.</span><span class="sxs-lookup"><span data-stu-id="d70e3-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="d70e3-119">Il modifie son message de statut personnalisé pour dire quelque chose de similaire à « Je ne suis pas disponible pour les prochaines heures.</span><span class="sxs-lookup"><span data-stu-id="d70e3-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="d70e3-120">Contactez le @DrEhrle pour toute urgence ».</span><span class="sxs-lookup"><span data-stu-id="d70e3-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="d70e3-121">D’autres membres de l’équipe réalisent que la délégation s’est produite alors qu’ils tentent de contacter le dr Piccio. Ils savent maintenant contacter le dr Ehrle en attendant.</span><span class="sxs-lookup"><span data-stu-id="d70e3-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="d70e3-122">Il n’y a pas de confusion entre les soins d’un patient et peu à peu de confusion.</span><span class="sxs-lookup"><span data-stu-id="d70e3-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="d70e3-123">Impact des modes de co-existence sur l’état de l’utilisateur dans le client Teams</span><span class="sxs-lookup"><span data-stu-id="d70e3-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="d70e3-124">Les administrateurs doivent savoir que les remarques d’état et les comportements de mention de délégation dépendent en partie du mode de co-existence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d70e3-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="d70e3-125">Cette matrice présente les possibilités :</span><span class="sxs-lookup"><span data-stu-id="d70e3-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="d70e3-126">mode Co-Existence'écran</span><span class="sxs-lookup"><span data-stu-id="d70e3-126">Co-Existence Mode</span></span> | <span data-ttu-id="d70e3-127">Comportement attendu</span><span class="sxs-lookup"><span data-stu-id="d70e3-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="d70e3-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="d70e3-128">TeamsOnly</span></span> |<span data-ttu-id="d70e3-129">Les utilisateurs peuvent uniquement définir une note à partir de Teams.</span><span class="sxs-lookup"><span data-stu-id="d70e3-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="d70e3-130">La note Teams de l’utilisateur est visible dans Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="d70e3-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="d70e3-131">Île</span><span class="sxs-lookup"><span data-stu-id="d70e3-131">Islands</span></span> | <span data-ttu-id="d70e3-132">Le jeu de notes de l’utilisateur dans Teams est visible uniquement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d70e3-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="d70e3-133">Note de l’utilisateur définie en SfB visible uniquement dans SfB</span><span class="sxs-lookup"><span data-stu-id="d70e3-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="d70e3-134">Modes SfB\*</span><span class="sxs-lookup"><span data-stu-id="d70e3-134">SfB\* modes</span></span> | <span data-ttu-id="d70e3-135">Les utilisateurs peuvent uniquement définir une note à partir de SfB.</span><span class="sxs-lookup"><span data-stu-id="d70e3-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="d70e3-136">La note SfB de l’utilisateur est visible dans SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="d70e3-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="d70e3-137">Un utilisateur peut uniquement définir une note dans Teams si son mode est TeamsOnly ou Islands.</span><span class="sxs-lookup"><span data-stu-id="d70e3-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="d70e3-138">Affichage de notes définies dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d70e3-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="d70e3-139">Aucune indication visuelle n’indique qu’une note a été définie à partir de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d70e3-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="d70e3-140">Skype Entreprise n’applique pas de limite de caractères aux notes de statut.</span><span class="sxs-lookup"><span data-stu-id="d70e3-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="d70e3-141">Microsoft Teams n’affiche que les 280 premiers caractères d’un jeu de notes à partir de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d70e3-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="d70e3-142">Une ellipse (...) à la fin d’une note indique une troncation.</span><span class="sxs-lookup"><span data-stu-id="d70e3-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="d70e3-143">Skype Entreprise ne prend pas en charge les heures d’expiration des notes.</span><span class="sxs-lookup"><span data-stu-id="d70e3-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="d70e3-144">La migration des notes de Skype Entreprise vers Teams n’est pas prise en charge lors de la mise à niveau d’un utilisateur vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="d70e3-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d70e3-145">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="d70e3-145">Related topics</span></span>

[<span data-ttu-id="d70e3-146">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d70e3-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
