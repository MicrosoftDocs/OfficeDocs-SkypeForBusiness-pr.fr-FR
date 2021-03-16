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
description: Découvrez comment un utilisateur ayant le statut Absent ou Ne pas déranger peut définir explicitement un autre utilisateur en tant que délégué dans son message d’état.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790466"
---
# <a name="message-delegation"></a><span data-ttu-id="69663-103">Délégation de messages</span><span class="sxs-lookup"><span data-stu-id="69663-103">Message delegation</span></span>

<span data-ttu-id="69663-104">Un utilisateur peut déjà définir explicitement son statut sur Absent(s) ou Ne pas déranger, et fournir un texte personnalisé.</span><span class="sxs-lookup"><span data-stu-id="69663-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="69663-105">La fonctionnalité de délégation de message fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="69663-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="69663-106">Un utilisateur @username mentionne un autre utilisateur dans une partie d'un message d'état textuel, suggérant que pendant qu'ils sont indisponibles, les personnes qui veulent les contacter doivent plutôt contacter l'utilisateur mentionné @username.</span><span class="sxs-lookup"><span data-stu-id="69663-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="69663-107">La personne qui a été désignée comme déléguée est informée qu'elle a été désignée pour être déléguée.</span><span class="sxs-lookup"><span data-stu-id="69663-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="69663-108">Une personne qui tente de contacter le premier utilisateur peut alors passer la souris sur le délégué désigné et lui envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="69663-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="69663-109">Il s’agit d’un processus initié par l’utilisateur dans le client. Aucune implication de l’administrateur n’est nécessaire pour activer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="69663-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="69663-110">Scénario d'utilisation de la délégation dans le secteur des soins de santé</span><span class="sxs-lookup"><span data-stu-id="69663-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="69663-111">*Exemple d’utilisation sans définition de délégués :*  Le Dr Franco Piccio est de garde au service de radiologie.</span><span class="sxs-lookup"><span data-stu-id="69663-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="69663-112">Il reçoit un appel personnel urgent et doit s’absenter pendant les prochaines heures.</span><span class="sxs-lookup"><span data-stu-id="69663-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="69663-113">Il demande à l'une de ses collègues du service de radiologie, le Dr Lena Ehrle, de le remplacer pendant son absence.</span><span class="sxs-lookup"><span data-stu-id="69663-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="69663-114">Il remet officieusement son téléavertisseur au Dr Ehrle, qui est à l'écoute des messages urgents et des bips sur le téléavertisseur et y répond au nom du Dr Piccio en plus de ses responsabilités actuelles.</span><span class="sxs-lookup"><span data-stu-id="69663-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="69663-115">Les autres membres de l'équipe peuvent ne pas se rendre compte que la délégation informelle a eu lieu, et il s'ensuit une confusion dans les soins prodigués au patient.</span><span class="sxs-lookup"><span data-stu-id="69663-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="69663-116">*Exemple d’utilisation avec définition de délégués :* Le Dr Franco Piccio est de garde au service de radiologie.</span><span class="sxs-lookup"><span data-stu-id="69663-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="69663-117">Il reçoit un appel personnel urgent et doit s’absenter pendant les prochaines heures.</span><span class="sxs-lookup"><span data-stu-id="69663-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="69663-118">Il demande à l'une de ses collègues du service de radiologie, le Dr Lena Ehrle de le remplacer pendant son absence.</span><span class="sxs-lookup"><span data-stu-id="69663-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="69663-119">Il modifie son message d’état personnalisé de façon à dire « Je ne suis pas disponible pendant les prochaines heures.</span><span class="sxs-lookup"><span data-stu-id="69663-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="69663-120">Veuillez contacter le @DrEhrle en cas d’urgence. »</span><span class="sxs-lookup"><span data-stu-id="69663-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="69663-121">Les autres membres de l'équipe réalisent que la délégation s'est produite alors qu'ils tentaient de contacter le Dr Piccio. Ils savent donc qu'ils doivent contacter le Dr Ehrle en attendant.</span><span class="sxs-lookup"><span data-stu-id="69663-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="69663-122">Il y a peu ou pas de confusion dans les soins prodigués au patient.</span><span class="sxs-lookup"><span data-stu-id="69663-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="69663-123">Impact des modes de coexistence sur le statut de l'utilisateur dans le client Teams</span><span class="sxs-lookup"><span data-stu-id="69663-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="69663-124">Les administrateurs doivent savoir que le comportement des notes d'état et des mentions de délégation dépendra en partie du mode de coexistence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69663-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="69663-125">Cette matrice affiche les possibilités qui s’offrent à vous :</span><span class="sxs-lookup"><span data-stu-id="69663-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="69663-126">Mode de coexistence</span><span class="sxs-lookup"><span data-stu-id="69663-126">Co-Existence Mode</span></span> | <span data-ttu-id="69663-127">Comportement attendu</span><span class="sxs-lookup"><span data-stu-id="69663-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="69663-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="69663-128">TeamsOnly</span></span> |<span data-ttu-id="69663-129">Les utilisateurs peuvent définir une note à partir de Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="69663-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="69663-130">La note Teams de l’utilisateur est visible dans Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="69663-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="69663-131">Île</span><span class="sxs-lookup"><span data-stu-id="69663-131">Islands</span></span> | <span data-ttu-id="69663-132">Le jeu de notes de l’utilisateur dans Teams n’est visible que dans Teams.</span><span class="sxs-lookup"><span data-stu-id="69663-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="69663-133">Le jeu de notes de l’utilisateur dans SfB n’est visible que dans SfB.</span><span class="sxs-lookup"><span data-stu-id="69663-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="69663-134">Modes SfB\*</span><span class="sxs-lookup"><span data-stu-id="69663-134">SfB\* modes</span></span> | <span data-ttu-id="69663-135">Les utilisateurs peuvent définir une note à partir de SfB uniquement.</span><span class="sxs-lookup"><span data-stu-id="69663-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="69663-136">La note SfB de l’utilisateur est visible dans SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="69663-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="69663-137">Un utilisateur peut seulement définir une note dans Teams si son mode est TeamsOnly ou Îles.</span><span class="sxs-lookup"><span data-stu-id="69663-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="69663-138">Affichage de notes définies dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="69663-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="69663-139">Il n’existe aucune indication visuelle qu’une note a été définie à partir de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="69663-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="69663-140">Skype Entreprise n’applique pas une limite de caractères aux notes d’état.</span><span class="sxs-lookup"><span data-stu-id="69663-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="69663-141">Microsoft Teams affiche uniquement les 280 premiers caractères d’un jeu de notes à partir de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="69663-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="69663-142">Une ellipse (...) à la fin d’une note indique une troncation.</span><span class="sxs-lookup"><span data-stu-id="69663-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="69663-143">Skype Entreprise ne prend pas en charge les délais d’expiration des notes.</span><span class="sxs-lookup"><span data-stu-id="69663-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="69663-144">La migration des notes de Skype Entreprise vers Teams n’est pas prise en charge lorsqu’un utilisateur est mis à niveau vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="69663-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69663-145">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="69663-145">Related topics</span></span>

[<span data-ttu-id="69663-146">Coexistence avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="69663-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
