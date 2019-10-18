---
title: Délégation de messages
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Un utilisateur peut définir explicitement un autre utilisateur comme délégué dans son message d’État.
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570357"
---
# <a name="message-delegation"></a><span data-ttu-id="4e34f-103">Délégation de messages</span><span class="sxs-lookup"><span data-stu-id="4e34f-103">Message delegation</span></span>

<span data-ttu-id="4e34f-104">Un utilisateur peut déjà définir son état sur absent (e) ou ne pas déranger, et fournir un texte personnalisé.</span><span class="sxs-lookup"><span data-stu-id="4e34f-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="4e34f-105">La fonctionnalité de délégation des messages fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="4e34f-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="4e34f-106">Un utilisateur @username mention d’un autre utilisateur dans une partie d’un message de statut de texte, ce qui A pour effet de signaler qu’il s’agit de personnes indisponibles pour le contacter à la place, contactez le @username utilisateur mentionné.</span><span class="sxs-lookup"><span data-stu-id="4e34f-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="4e34f-107">La personne qui a été désignée comme délégué est avertie qu’elle a été désignée comme délégué.</span><span class="sxs-lookup"><span data-stu-id="4e34f-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="4e34f-108">Une personne qui tente de contacter le premier utilisateur peut alors pointer sur le délégué désigné et envoyer facilement un message au délégué.</span><span class="sxs-lookup"><span data-stu-id="4e34f-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="4e34f-109">Il s’agit d’un processus initialisé par l’utilisateur dans le client et aucune implication d’administrateur n’est nécessaire pour activer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="4e34f-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="4e34f-110">Scénario d’utilisation de délégation dans la santé</span><span class="sxs-lookup"><span data-stu-id="4e34f-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="4e34f-111">*Exemple d’utilisation sans définir de délégués :*  Dr. Franco Piccio est en communication téléphonique au service de radiologie.</span><span class="sxs-lookup"><span data-stu-id="4e34f-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="4e34f-112">Il reçoit un appel individuel urgent et doit s’éloigner pendant quelques heures.</span><span class="sxs-lookup"><span data-stu-id="4e34f-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="4e34f-113">Il demande à l’un de ses homologues du service de radiologie, Dr. Lena Ehrle, de s’en informer pendant qu’il a disparu.</span><span class="sxs-lookup"><span data-stu-id="4e34f-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="4e34f-114">Il a émis par le biais de son radiomessagerie pour le Dr. Ehrle, qui écoute les messages urgents et les télécommandes sur le téléavertisseur et y réponde au nom de Dr. Piccio en plus de ses responsabilités actuelles.</span><span class="sxs-lookup"><span data-stu-id="4e34f-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="4e34f-115">Les autres membres de l’équipe risquent de ne pas se rendre compte que la délégation informelle s’est déroulée et que le prêt est en conflit avec le patient.</span><span class="sxs-lookup"><span data-stu-id="4e34f-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="4e34f-116">*Exemple d’utilisation avec de définir des délégués :* Dr. Franco Piccio est en communication téléphonique au service de radiologie.</span><span class="sxs-lookup"><span data-stu-id="4e34f-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="4e34f-117">Il reçoit un appel individuel urgent et doit s’éloigner pendant quelques heures.</span><span class="sxs-lookup"><span data-stu-id="4e34f-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="4e34f-118">Il demande l’un de ses pairs au service de radiologie, le Dr. Lena Ehrle pour s’en informer pendant qu’il a disparu.</span><span class="sxs-lookup"><span data-stu-id="4e34f-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="4e34f-119">Il change son message de statut personnalisé pour qu’il ressemble à ce qui suit : «je ne suis pas disponible pendant quelques heures.</span><span class="sxs-lookup"><span data-stu-id="4e34f-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="4e34f-120">Veuillez contacter @DrEhrle pour toute urgence.»</span><span class="sxs-lookup"><span data-stu-id="4e34f-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="4e34f-121">Les autres membres de l’équipe peuvent être conscients que la délégation s’est produite lors de la tentative de contact de la fonction de Piccio.</span><span class="sxs-lookup"><span data-stu-id="4e34f-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="4e34f-122">Le léger risque de confusion avec les soins d’un patient.</span><span class="sxs-lookup"><span data-stu-id="4e34f-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="4e34f-123">Impact des modes de coexistence sur l’état de l’utilisateur dans le client teams</span><span class="sxs-lookup"><span data-stu-id="4e34f-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="4e34f-124">Les administrateurs doivent savoir que les comportements de la délégation et des notes d’État dépendent en partie du mode de coexistence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4e34f-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="4e34f-125">Ce tableau présente les possibilités suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e34f-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="4e34f-126">Mode de coexistence</span><span class="sxs-lookup"><span data-stu-id="4e34f-126">Co-Existence Mode</span></span> | <span data-ttu-id="4e34f-127">Comportement attendu</span><span class="sxs-lookup"><span data-stu-id="4e34f-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="4e34f-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="4e34f-128">TeamsOnly</span></span> |<span data-ttu-id="4e34f-129">Les utilisateurs peuvent définir une note uniquement dans Teams.</span><span class="sxs-lookup"><span data-stu-id="4e34f-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="4e34f-130">La note équipes de l’utilisateur est visible dans équipes & marketing.</span><span class="sxs-lookup"><span data-stu-id="4e34f-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="4e34f-131">Archipels</span><span class="sxs-lookup"><span data-stu-id="4e34f-131">Islands</span></span> | <span data-ttu-id="4e34f-132">Remarque définie par l’utilisateur dans équipes uniquement visible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="4e34f-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="4e34f-133">Note définie par l’utilisateur dans marketing visible uniquement dans marketing</span><span class="sxs-lookup"><span data-stu-id="4e34f-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="4e34f-134">Modes marketing \*</span><span class="sxs-lookup"><span data-stu-id="4e34f-134">SfB\* modes</span></span> | <span data-ttu-id="4e34f-135">Les utilisateurs peuvent définir une note uniquement à partir de marketing.</span><span class="sxs-lookup"><span data-stu-id="4e34f-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="4e34f-136">La note marketing de l’utilisateur est visible dans marketing & Teams.</span><span class="sxs-lookup"><span data-stu-id="4e34f-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="4e34f-137">Un utilisateur peut uniquement définir une note dans teams s’il s’agit du mode TeamsOnly ou îlots.</span><span class="sxs-lookup"><span data-stu-id="4e34f-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="4e34f-138">Affichage de notes dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="4e34f-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="4e34f-139">Il n’y a pas d’indications visuelles indiquant qu’une note a été définie dans Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4e34f-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="4e34f-140">Skype entreprise n’applique aucune limite de caractères aux notes de statut.</span><span class="sxs-lookup"><span data-stu-id="4e34f-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="4e34f-141">Microsoft teams n’affiche que les 280 premiers caractères d’un ensemble de notes dans Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4e34f-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="4e34f-142">Les points de suspension (...) à la fin d’une note indiquent une troncature.</span><span class="sxs-lookup"><span data-stu-id="4e34f-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="4e34f-143">Skype entreprise ne prend pas en charge les délais d’expiration des notes.</span><span class="sxs-lookup"><span data-stu-id="4e34f-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="4e34f-144">La migration de notes de Skype entreprise vers teams n’est pas prise en charge lorsque l’utilisateur a procédé à la mise à niveau vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="4e34f-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e34f-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e34f-145">Related topics</span></span>

[<span data-ttu-id="4e34f-146">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4e34f-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
