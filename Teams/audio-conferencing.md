---
title: "Audioconférence dans Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guide pratique pour le déploiement de l’audioconférence dans Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5a65f305d924c5e5e6dac01d2391a62d8abd1243
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="449f5-103">Audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="449f5-103">Audio Conferencing in Microsoft Teams</span></span>
=====================================

> [!IMPORTANT]
> <span data-ttu-id="449f5-104">L’audioconférence est en préversion publique.</span><span class="sxs-lookup"><span data-stu-id="449f5-104">Audio conferencing is in public preview.</span></span> <span data-ttu-id="449f5-105">Elle est disponible pour les utilisateurs précoces et les utilisateurs de la préversion et est susceptible d’être modifiée lors de sa publication ou mise à jour.</span><span class="sxs-lookup"><span data-stu-id="449f5-105">It's available to Early Adopters (EA) and preview customers and could change as it is released or updated.</span></span>

<span data-ttu-id="449f5-106">L’audioconférence dans Office 365 (appelée auparavant Conférence PSTN) permet aux participants de rejoindre vos réunions depuis n’importe quel téléphone.</span><span class="sxs-lookup"><span data-stu-id="449f5-106">Audio Conferencing in Office 365 (formerly known as PSTN Conferencing) allows participants to join your meetings from any telephone.</span></span> <span data-ttu-id="449f5-107">Cette fonction est maintenant disponible dans Microsoft Teams, en préversion publique, et permet aux utilisateurs de rejoindre des réunions Teams en utilisant leurs téléphones.</span><span class="sxs-lookup"><span data-stu-id="449f5-107">This feature is now available in Microsoft Teams, in public preview, allowing users to join Teams meetings using their phones.</span></span> <span data-ttu-id="449f5-108">Le guide pratique dans cet article vous dirige étape par étape à travers le parcours du client FastTrack Office 365 pour l’audioconférence : planifier, intégrer et générer une valeur ajoutée.</span><span class="sxs-lookup"><span data-stu-id="449f5-108">The practical guidance in this article steps you through the Office 365 FastTrack customer journey framework for Audio Conferencing - Envision, Onboard, and Drive value.</span></span>

<span data-ttu-id="449f5-109">Voici les avantages de [l’audioconférence](https://go.microsoft.com/fwlink/?linkid=858992) dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="449f5-109">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="449f5-110">L’audioconférence prend en charge Teams et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="449f5-110">Audio Conferencing supports both Teams and Skype for Business Online.</span></span> <span data-ttu-id="449f5-111">Actuellement, le centre d’administration de Skype Entreprise et le PowerShell distant existants fournissent les interfaces d’administration permettant de gérer l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-111">Currently, the existing Skype for Business Admin center and remote PowerShell provide the administrative interfaces to manage Audio Conferencing.</span></span>


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

<span data-ttu-id="449f5-112">Concevoir <a name="Envision_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="449f5-112">Envision <a name="Envision_AudioConferencing"> </a></span></span>
=========

<span data-ttu-id="449f5-113">La phase Planifier fournit les bases du parcours du client Office 365 et s’applique à toutes les charges de travail comme l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-113">The Envision phase provides the foundation for the Office 365 customer journey and is applicable to all workloads such as Audio Conferencing.</span></span>

<span data-ttu-id="449f5-114">Dans cette phase, les objectifs de l’entreprise sont déterminés, avec les parties prenantes impliquées dans le projet réunies, pour fournir par la suite :</span><span class="sxs-lookup"><span data-stu-id="449f5-114">In this phase, business goals are captured, with relevant project stakeholders assembled, to ultimately deliver:</span></span>

-   <span data-ttu-id="449f5-115">un plan de réussite général contenant les cas d’utilisation professionnelle, les parties prenantes clés, les objectifs et les résultats clés, les indicateurs de succès clés, les risques, l’évaluation de l’environnement, la préparation à l’adoption et un plan opérationnel.</span><span class="sxs-lookup"><span data-stu-id="449f5-115">a high-level success plan that contains business use cases, key stakeholders, objectives and key results (OKRs), key success indicators (KSIs), risks, environmental assessment, adoption readiness, and operational plan.</span></span>

-   <span data-ttu-id="449f5-116">Ensuite, un plan d’implémentation technique de l’audioconférence détaillé pour parvenir à l’état final souhaité.</span><span class="sxs-lookup"><span data-stu-id="449f5-116">and subsequently, a detailed Audio Conferencing technical implementation plan to achieve the desired end state.</span></span>

<a name="define-business-use-cases-for-audio-conferencing"></a><span data-ttu-id="449f5-117">Définir les cas d'utilisation professionnelle de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-117">Define business use cases for Audio Conferencing</span></span>
------------------------------------------------

<span data-ttu-id="449f5-118">L’audioconférence fournit aux organisations des points d’entrée supplémentaires à toutes les réunions planifiées en permettant aux participants de rejoindre les réunions via PSTN en composant des numéros de téléphone de ligne fixe traditionnels, PBX ou de mobile.</span><span class="sxs-lookup"><span data-stu-id="449f5-118">Audio Conferencing provides organizations with additional entry points to any scheduled meetings by allowing meeting participants to join via PSTN by dialing in using traditional landline, PBX, or mobile phones.</span></span>

<span data-ttu-id="449f5-119">Cela est utile lorsque la personne qui a organisé la réunion ou les participants ne se trouvent pas devant un ordinateur, ou lorsque les connexions de données sont indisponibles ou non fiables pour prendre en charge des communications vocales - par exemple lorsque les participants se trouvent dans une zone avec une couverture de données mobiles inégale, ou s’ils sont connectés à un service Wi-Fi gratuit public avec une bande passante limitée, ou lorsqu'ils préfèrent rejoindre la réunion à l’aide d'un point de terminaison de téléphonie qui leur est facilement accessible.</span><span class="sxs-lookup"><span data-stu-id="449f5-119">This is useful when the organizer or participants are not in front of a computer, or when data connections are unavailable or unreliable to support voice communications—such as when in a remote area with spotty mobile data coverage, or if connected to a free, public Wi-Fi service with limited bandwidth, or when meeting participants prefer to dial in to the meeting using telephony endpoint readily accessible to them.</span></span>

<span data-ttu-id="449f5-120">Dans cette étape, les principales parties prenantes impliquées dans le projet définiront des cas d’utilisation professionnelle qui prennent en charge l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-120">In this step, core project stakeholders will define business use cases that support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="449f5-121">Les cas d’utilisation professionnelle sont destinés à définir et documenter des résultats de l’entreprise attendus et mesurables, et incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="449f5-121">Business use cases are meant to define and document the expected and measurable business outcomes, and include the following:</span></span>

-   <span data-ttu-id="449f5-122">Description du processus d’entreprise actuel.</span><span class="sxs-lookup"><span data-stu-id="449f5-122">Description of current business process.</span></span>

-   <span data-ttu-id="449f5-123">Difficultés par rapport au processus d’entreprise existant définies.</span><span class="sxs-lookup"><span data-stu-id="449f5-123">Challenges with existing business process defined.</span></span>

-   <span data-ttu-id="449f5-124">Comment la technologie peut aider à surmonter ces difficultés.</span><span class="sxs-lookup"><span data-stu-id="449f5-124">How technology can help overcome these challenges.</span></span>

-   <span data-ttu-id="449f5-125">Le résultat de l'entreprise attendu et mesurable si ces difficultés sont surmontées.</span><span class="sxs-lookup"><span data-stu-id="449f5-125">The expected and measurable business outcome if these challenges are overcome.</span></span>

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><span data-ttu-id="449f5-126"><strong>Description du processus d’entreprise actuel</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-126"><strong>Description of current business process</strong></span></span></p>
<p><span data-ttu-id="449f5-127">Contoso fait actuellement appel à des services de conférence PSTN fournis par le fournisseur de téléphonie local titulaire facturés par minutes de réunion pour les réunions internes et celles impliquant des parties externes.</span><span class="sxs-lookup"><span data-stu-id="449f5-127">Contoso currently relies on PSTN conferencing services provided by the incumbent local telephony provider chargeable by meeting minutes for internal meetings and meetings involving external parties.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><span data-ttu-id="449f5-128"><strong>Difficultés par rapport au processus d’entreprise existant</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-128"><strong>Challenges with existing business process</strong></span></span></p>
<p><span data-ttu-id="449f5-129">Contoso dépense environ 1 million de dollars par an pour le service de conférence PSTN actuel, les réunions internes représentant 75 % du coût.</span><span class="sxs-lookup"><span data-stu-id="449f5-129">Contoso spends roughly USD 1 million per year for the current PSTN conferencing service, with 75% of the cost incurred for internal meetings.</span></span></p>
<p><span data-ttu-id="449f5-130">L’utilisation de points de terminaison de téléphonie traditionnels pour participer aux réunions hébergées par le service de conférence PSTN ne correspond pas au plan pour que l’organisation adopte Teams comme plate-forme de communication et de collaboration moderne.</span><span class="sxs-lookup"><span data-stu-id="449f5-130">The use of traditional telephony endpoints to join the meetings hosted by the PSTN conferencing service is not aligned with the plan for the organization to adopt Teams as modern communications and collaboration platform.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><span data-ttu-id="449f5-131"><strong>Comment la technologie peut surmonter ces difficultés</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-131"><strong>How technology can overcome these challenges</strong></span></span></p>
<p><span data-ttu-id="449f5-132">Avec l’adoption de Microsoft Teams comme plate-forme de communication et de collaboration moderne, les utilisateurs internes devraient principalement rejoindre les réunions en utilisant leurs PC équipés de casques optimisés et de dispositifs de salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="449f5-132">With the adoption of Microsoft Teams as modern communications and collaboration platform, internal users are expected to primarily join meetings using their PCs equipped with optimized headsets and meeting room devices.</span></span> <span data-ttu-id="449f5-133">Le service d’audioconférence sera disponible pour prendre en charge les participants externes ou les situations où l’utilisation de l’audio sur PC n’est pas avantageuse pour les participants internes.</span><span class="sxs-lookup"><span data-stu-id="449f5-133">Audio Conferencing service will be available to support external participants or to support situations where the use of PC audio is not favorable for the internal participants.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><span data-ttu-id="449f5-134"><strong>Résultats de l’entreprise attendus et mesurables</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-134"><strong>Expected, measurable, business outcomes</strong></span></span></p>
<p><span data-ttu-id="449f5-135">Le passage à Teams comme plate-forme de communication et de collaboration moderne, combinée au service d’audioconférence, réduira considérablement le coût de la prestation du service de conférence PSTN, Contoso devant dépenser seulement 20 % environ du coût annuel du service de conférence PSTN existant.</span><span class="sxs-lookup"><span data-stu-id="449f5-135">The move to Teams as modern communications and collaboration platform, combined with Audio Conferencing service, will greatly reduce the cost to deliver the PSTN conferencing service to the point that Contoso is expected to only spend approximately 20% of the annual cost of the existing PSTN conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-136">_Tableau 1 - exemple de cas d’utilisation professionnelle_</span><span class="sxs-lookup"><span data-stu-id="449f5-136">_Table 1 Business use case example_</span></span>


<span data-ttu-id="449f5-137">En plus de définir les cas d’utilisation professionnelle, avoir une vision claire de la portée organisationnelle et du planning du projet à cette étape permet de passer à l’étape suivante de la phase Planifier.</span><span class="sxs-lookup"><span data-stu-id="449f5-137">In addition to defining the business use cases, having a clarity around the organizational scope and project timelines at this step helps move onto the next step of the Envision phase.</span></span>

<a name="identify-key-stakeholders"></a><span data-ttu-id="449f5-138">Identifier les parties prenantes clés</span><span class="sxs-lookup"><span data-stu-id="449f5-138">Identify key stakeholders</span></span>
-------------------------

<span data-ttu-id="449f5-139">Les cas d’utilisation professionnelle définis à l’étape précédente incluront la portée organisationnelle de l’implémentation de l’audioconférence et, de ce fait, la matrice complète des parties prenantes peut être complétée pour inclure les personnes adéquates à inclure dans le projet.</span><span class="sxs-lookup"><span data-stu-id="449f5-139">The business use cases defined in the previous step will include organizational scope of Audio Conferencing implementation, and based on that, the comprehensive stakeholder matrix can be completed to include the right people to be involved in the project.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-140">Rôle</span><span class="sxs-lookup"><span data-stu-id="449f5-140">Role</span></span></th>
<th align="left"><span data-ttu-id="449f5-141">Description</span><span class="sxs-lookup"><span data-stu-id="449f5-141">Description</span></span></th>
<th align="left"><span data-ttu-id="449f5-142">Nom, informations de contact, emplacement</span><span class="sxs-lookup"><span data-stu-id="449f5-142">Name, contact information, location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-143"><strong>Sponsor exécutif du projet</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-143"><strong>Project Executive Sponsor</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-144">Autorité et responsabilité ultimes du projet et réalisation des objectifs du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-144">Ultimate authority and accountability for the project and delivery on project objectives</span></span></li>
<li><span data-ttu-id="449f5-145">Aide à résoudre les problèmes transmis par le chef de projet</span><span class="sxs-lookup"><span data-stu-id="449f5-145">Help resolve issues escalated by Project Lead</span></span></li>
<li><span data-ttu-id="449f5-146">Organise la communication au sein de l’entreprise au sujet des objectifs du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-146">Sponsors communication within the company about project goals</span></span></li>
<li><span data-ttu-id="449f5-147">Chargé de prendre les décisions stratégiques clés</span><span class="sxs-lookup"><span data-stu-id="449f5-147">Responsible for making key strategic decisions</span></span></li>
<li><span data-ttu-id="449f5-148">Chargé de la disponibilité des ressources nécessaires et du budget</span><span class="sxs-lookup"><span data-stu-id="449f5-148">Responsible for availability of required resources and budget</span></span></p>
<li><span data-ttu-id="449f5-149">Principale évaluation trimestrielle des activités</span><span class="sxs-lookup"><span data-stu-id="449f5-149">Leading Quarterly Business Reviews (QBR)</span></span></li>
<li><span data-ttu-id="449f5-150">Adhésion et appui à la campagne de sensibilisation</span><span class="sxs-lookup"><span data-stu-id="449f5-150">Buy-In and support of awareness campaign effort</span></span></li>
<li><span data-ttu-id="449f5-151">Est le sponsor du projet pour le lancement du programme</span><span class="sxs-lookup"><span data-stu-id="449f5-151">Serving as the Project Sponsor to the program rollout</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-152">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-152">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-153"><strong>Chef de projet</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-153"><strong>Project Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-154">Gestion et direction de l’équipe du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-154">Managing and leading project team</span></span></li>
<li><span data-ttu-id="449f5-155">Coordonne les partenaires et les équipes qui participent au projet</span><span class="sxs-lookup"><span data-stu-id="449f5-155">Coordinates partners and working teams engaged in the project</span></span></li>
<li><span data-ttu-id="449f5-156">Responsable de la création et de la gestion des plans du projet pour obtenir les principaux résultats trimestriels</span><span class="sxs-lookup"><span data-stu-id="449f5-156">Accountable for creating and managing project plans to meet quarterly key results</span></span></li>
<li><span data-ttu-id="449f5-157">Résoudre les problèmes fonctionnels croisés</span><span class="sxs-lookup"><span data-stu-id="449f5-157">Resolving cross-functional issues</span></span></li>
<li><span data-ttu-id="449f5-158">Fournir des informations actualisées périodiques aux sponsors du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-158">Providing regular updates to the project sponsors</span></span></li>
<li><span data-ttu-id="449f5-159">Incorporer les aspects relatifs à l’adoption dans l’ensemble du plan du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-159">Incorporating Adoption aspects into the all-up project plan</span></span></li>
<li><span data-ttu-id="449f5-160">Diriger les évaluations mensuelles des activités et opérationnelles, contribuer aux évaluations trimestrielles des activités</span><span class="sxs-lookup"><span data-stu-id="449f5-160">Leading Monthly Business and Operational Reviews (MBR), contributing to Quarterly Business Reviews</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-161">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-161">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-162"><strong>Chef/architecte de la collaboration</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-162"><strong>Collaboration Lead/Architect</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-163">Chargé de l’exécution de la stratégie de collaboration définie par la direction de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="449f5-163">Responsible for execution on collaboration strategy defined by company executives</span></span></li>
<li><span data-ttu-id="449f5-164">Analyse et choisit les produits de collaboration pour l’entreprise permettant d’atteindre les objectifs professionnels</span><span class="sxs-lookup"><span data-stu-id="449f5-164">Analyzing and choosing collaboration products for the company that meets business goals</span></span></li>
<li><span data-ttu-id="449f5-165">Chargé de la conception des opérations des produits de collaboration</span><span class="sxs-lookup"><span data-stu-id="449f5-165">Responsible for the design of the operations for collaboration products</span></span></li>
<li><span data-ttu-id="449f5-166">Définit un modèle d'opération et de prise en charge</span><span class="sxs-lookup"><span data-stu-id="449f5-166">Defines operation and support model</span></span></li>
<li><span data-ttu-id="449f5-167">Contribue aux évaluations mensuelles et trimestrielles des activités</span><span class="sxs-lookup"><span data-stu-id="449f5-167">Contributing to Monthly and Quarterly Business Reviews</span></span></li><ul></td>
<td align="left"><span data-ttu-id="449f5-168">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-168">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-169"><strong>Consultant</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-169"><strong>Consultant</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-170">Chargé des services de configuration</span><span class="sxs-lookup"><span data-stu-id="449f5-170">Responsible for configuration services</span></span></li>
<li><span data-ttu-id="449f5-171">Contribue à l'architecture de solutions globale</span><span class="sxs-lookup"><span data-stu-id="449f5-171">Contributes in overall solution architecture</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-172">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-172">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-173"><strong>Gestionnaire de projets</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-173"><strong>Project Manager</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-174">Élaborer et tenir à jour les plans de projet</span><span class="sxs-lookup"><span data-stu-id="449f5-174">Developing and maintaining project plan</span></span></li>
<li><span data-ttu-id="449f5-175">Gérer les livrables du projet conformément au plan et au budget du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-175">Managing project deliverables in line with project plan and budget</span></span></li>
<li><span data-ttu-id="449f5-176">Noter et gérer les problèmes liés au projet, y compris les remontées</span><span class="sxs-lookup"><span data-stu-id="449f5-176">Recording and managing project issues, including escalations</span></span></li>
<li><span data-ttu-id="449f5-177">Effectuer des appels d'intervention hebdomadaires</span><span class="sxs-lookup"><span data-stu-id="449f5-177">Conducting weekly stand up calls</span></span></li>
<li><span data-ttu-id="449f5-178">Assurer la liaison avec, et fournir des informations actualisées aux sponsors exécutifs du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-178">Liaises with, and provides updates to project executive sponsors</span></span></li>
<li><span data-ttu-id="449f5-179">Collaborer avec l’architecte pour définir le mode de gestion des changements et les plans de communication</span><span class="sxs-lookup"><span data-stu-id="449f5-179">Working with the Architect to define the Change Management approach and Communication Plans</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-180">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-180">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-181"><strong>Spécialiste en gestion des changements/adoption</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-181"><strong>Change Management/Adoption Specialist</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-182">Formuler des recommandations lors de la phase de découverte sur les processus d’adoption et de formation</span><span class="sxs-lookup"><span data-stu-id="449f5-182">Provide input on Discovery phase into adoption and training processes</span></span></li>
<li><span data-ttu-id="449f5-183">Participer à l’atelier sur la stratégie d’adoption</span><span class="sxs-lookup"><span data-stu-id="449f5-183">Participate in adoption strategy workshop</span></span></li>
<li><span data-ttu-id="449f5-184">Développer et être responsable de la stratégie d’adoption</span><span class="sxs-lookup"><span data-stu-id="449f5-184">Developing and responsible for adoption strategy</span></span></li>
<li><span data-ttu-id="449f5-185">Développer et exécuter le plan de communication</span><span class="sxs-lookup"><span data-stu-id="449f5-185">Developing and executing communication plan</span></span></li>
<li><span data-ttu-id="449f5-186">Chargé de dispenser des formations aux utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="449f5-186">Responsible for delivering trainings to end users</span></span></li>
<li><span data-ttu-id="449f5-187">Recueillir les commentaires et réaliser des enquêtes</span><span class="sxs-lookup"><span data-stu-id="449f5-187">Collect feedback and conduct surveys</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-188">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-188">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-189"><strong>Directeur de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-189"><strong>Network Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-190">Formuler des recommandations lors de la phase de découverte sur la conception du réseau</span><span class="sxs-lookup"><span data-stu-id="449f5-190">Providing input on Discovery phase into network design</span></span></li>
<li><span data-ttu-id="449f5-191">Participer à la planification lors de l’atelier sur la planification</span><span class="sxs-lookup"><span data-stu-id="449f5-191">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="449f5-192">Coordonner le travail de l’équipe de mise en réseau lors de l’exécution du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-192">Coordinates work of networking team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-193">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-193">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-194"><strong>Directeur de la sécurité</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-194"><strong>Security Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-195">Formuler des recommandations lors de la phase de découverte sur les processus et la conception de la sécurité</span><span class="sxs-lookup"><span data-stu-id="449f5-195">Providing input on Discovery phase into security design and processes</span></span></li>
<li><span data-ttu-id="449f5-196">Participer à la planification lors de l’atelier sur la planification</span><span class="sxs-lookup"><span data-stu-id="449f5-196">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="449f5-197">Coordonner le travail de l’équipe chargée de la sécurité lors de l’exécution du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-197">Coordinates work of security team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-198">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-198">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-199"><strong>Directeur de la téléphonie</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-199"><strong>Telephony Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-200">Formuler des recommandations lors de la phase de découverte sur la conception de la téléphonie</span><span class="sxs-lookup"><span data-stu-id="449f5-200">Providing input on Discovery phase into telephony design</span></span></li>
<li><span data-ttu-id="449f5-201">Participer à la planification lors de l’atelier sur la planification</span><span class="sxs-lookup"><span data-stu-id="449f5-201">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="449f5-202">Coordonner le travail de l’équipe chargée de la téléphonie lors de l’exécution du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-202">Coordinates work of telephony team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-203">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-203">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-204"><strong>Directeur de bureau</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-204"><strong>Desktop Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-205">Formuler des recommandations lors de la phase de découverte sur les clients et le processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="449f5-205">Providing input on Discovery phase into clients and update process</span></span></li>
<li><span data-ttu-id="449f5-206">Participer à la planification lors de l’atelier sur la planification</span><span class="sxs-lookup"><span data-stu-id="449f5-206">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="449f5-207">Coordonner le travail de l’équipe chargée des bureaux lors de l’exécution du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-207">Coordinates work of desktop team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-208">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-208">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-209"><strong>Accompagner/aider le directeur de bureau</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-209"><strong>Support/Help Desk Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-210">Formuler des recommandations lors de la phase de découverte sur le modèle opérationnel et de prise en charge</span><span class="sxs-lookup"><span data-stu-id="449f5-210">Providing input on Discovery phase into operational and support model</span></span></li>
<li><span data-ttu-id="449f5-211">Participer à la planification lors de l’atelier sur la planification</span><span class="sxs-lookup"><span data-stu-id="449f5-211">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="449f5-212">Participer à la planification du modèle de prise en charge</span><span class="sxs-lookup"><span data-stu-id="449f5-212">Participating into support model planning</span></span></li>
<li><span data-ttu-id="449f5-213">Coordonner le travail de l’équipe chargée de la prise en charge/des ressources lors de l’exécution du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-213">Coordinates work of support teams/resources during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-214">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-214">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-215"><strong>Représentants d’unité commerciale</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-215"><strong>Business Unit Representatives</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-216">Contribuer aux guides et supports d’adoption basés sur les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="449f5-216">Contribute in End User based adoption guides and materials</span></span></li>
<li><span data-ttu-id="449f5-217">Évaluer et contribuer aux cas d’utilisation professionnelle</span><span class="sxs-lookup"><span data-stu-id="449f5-217">Contribute to and review Business Use Cases</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-218">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-218">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-219"><strong>Directeur du déploiement</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-219"><strong>Deployment Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-220">S’assurer que les conditions préalables au déploiement sont remplies</span><span class="sxs-lookup"><span data-stu-id="449f5-220">Ensure that deployment prerequisites are met</span></span></li>
<li><span data-ttu-id="449f5-221">Impliquer des ressources des clients dans l’affectation, la préparation et le déploiement des activités de l’étape</span><span class="sxs-lookup"><span data-stu-id="449f5-221">Engage customer resources to engage on prepare and deploy stage activities</span></span></li>
<li><span data-ttu-id="449f5-222">Participer à des réunions pour évaluer l’état de préparation et du déploiement</span><span class="sxs-lookup"><span data-stu-id="449f5-222">Participate in meetings to review prepare and deploy status</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-223">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-223">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-224"><strong>Administrateurs informatiques</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-224"><strong>IT Admins</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-225">Spécialistes des technologies de l'information pour aider à la planification et l’exécution des tests</span><span class="sxs-lookup"><span data-stu-id="449f5-225">IT Pros responsible for assistance with test planning and execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-226">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-226">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-227"><strong>Propriétaire de service</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-227"><strong>Service Owner</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-228">Responsable du fonctionnement de l’ensemble du service d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-228">Is responsible for the operation of the Audio Conferencing service all up</span></span></li>
<li><span data-ttu-id="449f5-229">Propriétaire du service d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-229">Owner of Audio Conferencing service</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-230">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-230">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-231"><strong>Ambassadeur de la qualité</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-231"><strong>Quality Champion</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-232">Génère des commentaires sur la qualité, la fiabilité et des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="449f5-232">Drives quality, reliability and user feedback</span></span></li>
<li><span data-ttu-id="449f5-233">Identifie les tendances en matière de qualité et génère les corrections avec les équipes respectives</span><span class="sxs-lookup"><span data-stu-id="449f5-233">Identifies the quality trends and drive remediation with the respective teams</span></span></li>
<li><span data-ttu-id="449f5-234">Fait des rapports par le biais du comité de pilotage à la direction</span><span class="sxs-lookup"><span data-stu-id="449f5-234">Reports through the steering committee back to leadership</span></span></li>
<li><span data-ttu-id="449f5-235">Fait des rapports sur la qualité, la fiabilité et l’opinion des utilisateurs par l’intermédiaire de Rate My Call et de Net Promoter Score</span><span class="sxs-lookup"><span data-stu-id="449f5-235">Reports on quality, reliability, and user sentiment through Rate My Call and Net Promoter Score</span></span></li></ul></td>
<td align="left"><span data-ttu-id="449f5-236">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-236">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-237">_Tableau 2 - exemple de modèle de matrice des parties prenantes_</span><span class="sxs-lookup"><span data-stu-id="449f5-237">_Table 2 Stakeholder matrix template example_</span></span>


> [!NOTE]
> <span data-ttu-id="449f5-238">Le tableau d’exemple ci-dessus et les tableaux suivants dans ce document sont utilisés comme modèle</span><span class="sxs-lookup"><span data-stu-id="449f5-238">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="449f5-239">« TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.</span><span class="sxs-lookup"><span data-stu-id="449f5-239">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a><span data-ttu-id="449f5-240">Définir les objectifs et les résultats clés, les indicateurs de succès clés et les risques</span><span class="sxs-lookup"><span data-stu-id="449f5-240">Define objectives and key results, key success indicators, and risks</span></span>
--------------------------------------------------------------------

<span data-ttu-id="449f5-241">Avec les parties prenantes impliquées dans le projet réunies, les cas d’utilisation professionnelle, la portée organisationnelle et le planning du projet peuvent être transposés en objectifs et résultats clés et les mesures de réussite du projet peuvent être définies dans une liste d’indicateurs de succès clés.</span><span class="sxs-lookup"><span data-stu-id="449f5-241">With the project stakeholders assembled, business use cases, organizational scope and project timelines can be translated into objectives and key results (OKRs) and the measures of project success can be defined into a list of key success indicators (KSIs).</span></span>

<span data-ttu-id="449f5-242">L’entière participation des parties prenantes impliquées dans le projet lors de la définition des objectifs et résultats clés et des indicateurs de succès clés garantira le sentiment d’appartenance et qu'ils correspondent aux besoins de l’entreprise en matière d’organisation.</span><span class="sxs-lookup"><span data-stu-id="449f5-242">Full participation from project stakeholders when defining the OKRs and KSIs will ensure sense of ownership and they are aligned to organizational business requirements.</span></span>

<span data-ttu-id="449f5-243">Les objectifs et résultats clés contiennent la liste des objectifs définis au début du projet, les résultats clés mesurables étant définis chaque trimestre.</span><span class="sxs-lookup"><span data-stu-id="449f5-243">OKRs will contain the list of objectives set in the beginning of the project, with measurable key results defined in a quarterly basis.</span></span> <span data-ttu-id="449f5-244">Les résultats clés sont vérifiés chaque mois pour effectuer le suivi du projet global et, en fonction de l’évolution, les plans trimestriels peuvent être adaptés lorsque cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="449f5-244">The key results are reviewed monthly to track status of the overall project, and based on progress, adjustment to the quarterly plans can be made as needed.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><p><span data-ttu-id="449f5-245"><strong>Vision</strong> : augmenter la productivité an optimisant les investissements dans Office 365</span><span class="sxs-lookup"><span data-stu-id="449f5-245"><strong>Vision</strong>: Increase productivity by maximizing Office 365 investments</span></span></p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-246"><strong>Objectifs</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-246"><strong>Objectives</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-247"><strong>Résultats clés</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-247"><strong>Key Results</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-248"><strong>Action</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-248"><strong>To Do</strong></span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-249">Déployer l’audioconférence dans Teams d’ici la fin de l’exercice fiscal 2018</span><span class="sxs-lookup"><span data-stu-id="449f5-249">Deploy Audio Conferencing in Teams by end of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="449f5-250">T1 de l’exercice 2018 : déployer l’audioconférence dans Teams globalement</span><span class="sxs-lookup"><span data-stu-id="449f5-250">FY18Q1: Deploy Audio Conferencing in Teams globally</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-251">Concevoir</span><span class="sxs-lookup"><span data-stu-id="449f5-251">Envision</span></span></p>
<ul><li><span data-ttu-id="449f5-252">Créer un plan de réussite</span><span class="sxs-lookup"><span data-stu-id="449f5-252">Create success plan</span></span></li>
<li><span data-ttu-id="449f5-253">Créer un plan d’implémentation technique détaillé</span><span class="sxs-lookup"><span data-stu-id="449f5-253">Create detailed technical implementation plan</span></span></li></ul>
<p><span data-ttu-id="449f5-254">Intégrer</span><span class="sxs-lookup"><span data-stu-id="449f5-254">Onboard</span></span></p>
<ul><li><span data-ttu-id="449f5-255">Exécuter le plan de réussite</span><span class="sxs-lookup"><span data-stu-id="449f5-255">Execute success plan</span></span></li>
<li><span data-ttu-id="449f5-256">Exécuter le plan d’implémentation technique</span><span class="sxs-lookup"><span data-stu-id="449f5-256">Execute technical implementation plan</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-257">Désactiver l’ancien service de conférence PSTN à l’échelle globale d'ici la fin de l’exercice fiscal 2018</span><span class="sxs-lookup"><span data-stu-id="449f5-257">Decommission legacy PSTN Conferencing service globally by mid of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="449f5-258">T2 de l’exercice 2018 : désactiver l’ancien service de conférence PSTN à l’échelle globale</span><span class="sxs-lookup"><span data-stu-id="449f5-258">FY18Q2: Decommission legacy PSTN Conferencing service globally</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-259">Générer une valeur ajoutée</span><span class="sxs-lookup"><span data-stu-id="449f5-259">Drive Value</span></span></p>
<ul><li><span data-ttu-id="449f5-260">Favoriser l’implication des utilisateurs et encourager l'adoption</span><span class="sxs-lookup"><span data-stu-id="449f5-260">Boost user engagement and drive adoption</span></span></li>
<li><span data-ttu-id="449f5-261">Gérer et préparer le changement</span><span class="sxs-lookup"><span data-stu-id="449f5-261">Manage and prepare change</span></span></li>
<li><span data-ttu-id="449f5-262">Mesurer, partager la réussite et retravailler</span><span class="sxs-lookup"><span data-stu-id="449f5-262">Measure, share success, and iterate</span></span></li></ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-263">_Tableau 3 - exemple d’objectifs et résultats clés_</span><span class="sxs-lookup"><span data-stu-id="449f5-263">_Table 3 Example of OKRs_</span></span>


<span data-ttu-id="449f5-264">Les indicateurs de succès clés mesurent la qualité et la réussite des résultats clés et complètent la nature binaire des objectifs et résultats clés (obtenus ou non), en détaillant les bons et les mauvais résultats.</span><span class="sxs-lookup"><span data-stu-id="449f5-264">KSIs measure quality and success of the key results and complement the binary nature of OKRs (achieved or not achieved), by detailing the good and/or bad results.</span></span> <span data-ttu-id="449f5-265">Lors de la définition des indicateurs de réussite clés, nous recommandons d’utiliser les critères « spécifique, mesurable, attribuable, réaliste, temporel » ou SMART.</span><span class="sxs-lookup"><span data-stu-id="449f5-265">When defining KSIs, we recommend leveraging the “specific, measurable, assignable, realistic, time-related” or SMART criteria.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-266">Type</span><span class="sxs-lookup"><span data-stu-id="449f5-266">Type</span></span></th>
<th align="left"><p><span data-ttu-id="449f5-267">Questions d’indicateurs de réussite clés &amp;</span><span class="sxs-lookup"><span data-stu-id="449f5-267">KSI questions &amp;</span></span></p>
<p><span data-ttu-id="449f5-268">critères</span><span class="sxs-lookup"><span data-stu-id="449f5-268">criteria</span></span></p></th>
<th align="left"><span data-ttu-id="449f5-269">Comment les mesurer</span><span class="sxs-lookup"><span data-stu-id="449f5-269">How measured</span></span></th>
<th align="left"><span data-ttu-id="449f5-270">Critères de réussite</span><span class="sxs-lookup"><span data-stu-id="449f5-270">Success criteria</span></span></th>
<th align="left"><span data-ttu-id="449f5-271">Mesurés</span><span class="sxs-lookup"><span data-stu-id="449f5-271">Measured</span></span></th>
<th align="left"><span data-ttu-id="449f5-272">Responsable</span><span class="sxs-lookup"><span data-stu-id="449f5-272">Responsible</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-273"><strong>Utilisation/adoption</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-273"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-274">La qualité des appels est égale ou meilleure qu’avec la solution précédente</span><span class="sxs-lookup"><span data-stu-id="449f5-274">Call quality is equal to or better than the previous solution</span></span></td>
<td align="left"><span data-ttu-id="449f5-275">Enquête</span><span class="sxs-lookup"><span data-stu-id="449f5-275">Survey</span></span></td>
<td align="left"><span data-ttu-id="449f5-276">80 % des utilisateurs sont d’accord ou tout à fait d’accord</span><span class="sxs-lookup"><span data-stu-id="449f5-276">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="449f5-277">Après activation et chaque trimestre</span><span class="sxs-lookup"><span data-stu-id="449f5-277">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="449f5-278">Équipe responsable des technologies de l’information</span><span class="sxs-lookup"><span data-stu-id="449f5-278">Information Technology team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-279"><strong>Utilisation/adoption</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-279"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-280">Les équipes ont facilité le processus de communication</span><span class="sxs-lookup"><span data-stu-id="449f5-280">Teams made the communication process easier</span></span></td>
<td align="left"><span data-ttu-id="449f5-281">Enquête</span><span class="sxs-lookup"><span data-stu-id="449f5-281">Survey</span></span></td>
<td align="left"><span data-ttu-id="449f5-282">80 % des utilisateurs sont d’accord ou tout à fait d’accord</span><span class="sxs-lookup"><span data-stu-id="449f5-282">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="449f5-283">Après activation et chaque trimestre</span><span class="sxs-lookup"><span data-stu-id="449f5-283">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="449f5-284">Équipe responsable de la gestion des changements</span><span class="sxs-lookup"><span data-stu-id="449f5-284">Change Management team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-285"><strong>Utilisation/adoption</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-285"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-286">Les utilisateurs utilisent activement la solution</span><span class="sxs-lookup"><span data-stu-id="449f5-286">Users actively use the solution</span></span></td>
<td align="left"><span data-ttu-id="449f5-287">Rapports Office 365, tableau de bord de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="449f5-287">Office 365 reports, Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="449f5-288">80 % des utilisateurs l’utilisent quotidiennement</span><span class="sxs-lookup"><span data-stu-id="449f5-288">80% of users are active daily users</span></span></td>
<td align="left"><span data-ttu-id="449f5-289">Chaque jour</span><span class="sxs-lookup"><span data-stu-id="449f5-289">Daily</span></span></td>
<td align="left"><span data-ttu-id="449f5-290">Équipe responsable de la gestion des changements</span><span class="sxs-lookup"><span data-stu-id="449f5-290">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-291"><strong>Utilisation/qualité</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-291"><strong>Usage/quality</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-292">Le pourcentage d’appels/conférences médiocres doit être minimal</span><span class="sxs-lookup"><span data-stu-id="449f5-292">Percentage of poor calls/conferences should be minimal</span></span></td>
<td align="left"><span data-ttu-id="449f5-293">Tableau de bord de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="449f5-293">Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="449f5-294">&lt; 5 % d’appels médiocres par mois</span><span class="sxs-lookup"><span data-stu-id="449f5-294">&lt; 5% of poor calls per month</span></span></td>
<td align="left"><span data-ttu-id="449f5-295">Chaque jour</span><span class="sxs-lookup"><span data-stu-id="449f5-295">Daily</span></span></td>
<td align="left"><span data-ttu-id="449f5-296">Équipe responsable des technologies de l’information</span><span class="sxs-lookup"><span data-stu-id="449f5-296">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-297"><strong>Utilisation/support</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-297"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-298">Je sais comment obtenir le support technique</span><span class="sxs-lookup"><span data-stu-id="449f5-298">I know how to get technical support</span></span></td>
<td align="left"><span data-ttu-id="449f5-299">Enquête</span><span class="sxs-lookup"><span data-stu-id="449f5-299">Survey</span></span></td>
<td align="left"><span data-ttu-id="449f5-300">90% des utilisateurs sont d’accord ou tout à fait d’accord</span><span class="sxs-lookup"><span data-stu-id="449f5-300">90% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="449f5-301">Après activation et chaque trimestre</span><span class="sxs-lookup"><span data-stu-id="449f5-301">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="449f5-302">Équipe responsable de la gestion des changements</span><span class="sxs-lookup"><span data-stu-id="449f5-302">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-303"><strong>Utilisation/support</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-303"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-304">Je suis satisfait de la qualité du support technique</span><span class="sxs-lookup"><span data-stu-id="449f5-304">I am satisfied with the quality of technical support</span></span></td>
<td align="left"><span data-ttu-id="449f5-305">Enquête</span><span class="sxs-lookup"><span data-stu-id="449f5-305">Survey</span></span></td>
<td align="left"><span data-ttu-id="449f5-306">80 % des utilisateurs sont d’accord ou tout à fait d’accord</span><span class="sxs-lookup"><span data-stu-id="449f5-306">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="449f5-307">Après chaque incident</span><span class="sxs-lookup"><span data-stu-id="449f5-307">After each incident</span></span></td>
<td align="left"><span data-ttu-id="449f5-308">Équipe responsable des technologies de l’information</span><span class="sxs-lookup"><span data-stu-id="449f5-308">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-309"><strong>Financier</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-309"><strong>Financial</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-310">Réduction du nombre de minutes de conférence héritée</span><span class="sxs-lookup"><span data-stu-id="449f5-310">Reduction of legacy conferencing minutes</span></span></td>
<td align="left"><span data-ttu-id="449f5-311">Système financier</span><span class="sxs-lookup"><span data-stu-id="449f5-311">Financial system</span></span></td>
<td align="left"><span data-ttu-id="449f5-312">Atteindre le retour sur investissement défini</span><span class="sxs-lookup"><span data-stu-id="449f5-312">Meet defined ROI</span></span></td>
<td align="left"><span data-ttu-id="449f5-313">Basé sur le retour sur investissement</span><span class="sxs-lookup"><span data-stu-id="449f5-313">Based on ROI</span></span></td>
<td align="left"><span data-ttu-id="449f5-314">Équipe responsable de la gestion des changements</span><span class="sxs-lookup"><span data-stu-id="449f5-314">Change Management team</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-315">_Tableau 4 - exemple d’indicateurs de réussite clés_</span><span class="sxs-lookup"><span data-stu-id="449f5-315">_Table 4 Example of KSIs_</span></span>


<span data-ttu-id="449f5-316">Vous devez identifier les risques d’entreprise dans le cadre de cette activité et définir un plan d’atténuation pour chaque risque identifié.</span><span class="sxs-lookup"><span data-stu-id="449f5-316">You need to identify business risks as part of this exercise and define a mitigation plan for each identified risk.</span></span> <span data-ttu-id="449f5-317">Ces informations peuvent être consignées dans un plan de gestion des risques</span><span class="sxs-lookup"><span data-stu-id="449f5-317">This information can be captured into a risk plan.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-318">Risque</span><span class="sxs-lookup"><span data-stu-id="449f5-318">Risk</span></span></th>
<th align="left"><span data-ttu-id="449f5-319">Probabilité</span><span class="sxs-lookup"><span data-stu-id="449f5-319">Likelihood</span></span></th>
<th align="left"><span data-ttu-id="449f5-320">Impact</span><span class="sxs-lookup"><span data-stu-id="449f5-320">Impact</span></span></th>
<th align="left"><span data-ttu-id="449f5-321">Global</span><span class="sxs-lookup"><span data-stu-id="449f5-321">Overall</span></span></th>
<th align="left"><span data-ttu-id="449f5-322">Plan d’atténuation</span><span class="sxs-lookup"><span data-stu-id="449f5-322">Mitigation plan</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-323">Une fusion prochaine ajoutera jusqu’à 1000 personnes</span><span class="sxs-lookup"><span data-stu-id="449f5-323">Upcoming merger will add up to 1,000 people</span></span></td>
<td align="left"><span data-ttu-id="449f5-324">Élevée</span><span class="sxs-lookup"><span data-stu-id="449f5-324">High</span></span></td>
<td align="left"><span data-ttu-id="449f5-325">Élevée</span><span class="sxs-lookup"><span data-stu-id="449f5-325">High</span></span></td>
<td align="left"><span data-ttu-id="449f5-326">Élevée</span><span class="sxs-lookup"><span data-stu-id="449f5-326">High</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-327">Pour les entreprises ayant fusionné, différenciez l’objectif et résultat clé avec le processus propre (Planifier, Intégrer, Générer une valeur ajoutée)</span><span class="sxs-lookup"><span data-stu-id="449f5-327">For merged companies, separate OKR with own process (Envision, Onboard, Drive Value)</span></span></p>
<p><span data-ttu-id="449f5-328">Ne les incluez pas dans les objectifs et résultats clés existants</span><span class="sxs-lookup"><span data-stu-id="449f5-328">Do not include them in existing OKRs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-329">Le transfert des numéros de téléphone retardera la réalisation du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-329">Telephone number porting will delay project completion</span></span></td>
<td align="left"><span data-ttu-id="449f5-330">Élevée</span><span class="sxs-lookup"><span data-stu-id="449f5-330">High</span></span></td>
<td align="left"><span data-ttu-id="449f5-331">Élevée</span><span class="sxs-lookup"><span data-stu-id="449f5-331">High</span></span></td>
<td align="left"><span data-ttu-id="449f5-332">Élevée</span><span class="sxs-lookup"><span data-stu-id="449f5-332">High</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-333">Préparer toutes les informations nécessaires pour prendre en charge le transfert des numéros de téléphone au préalable (enregistrement de service client, informations de facturation, courrier d’autorisation)</span><span class="sxs-lookup"><span data-stu-id="449f5-333">Prepare all the required information to support telephone number porting ahead of time (i.e.: customer service record, billing details, Letter of Authorization)</span></span></p>
<p><span data-ttu-id="449f5-334">Ajuster le planning du projet pour concilier la durée de bouclage de l’exécution du transfert des numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="449f5-334">Adjust project timeline to accommodate turnaround time of telephone number porting execution</span></span></p>
<p><span data-ttu-id="449f5-335">Communiquer l’utilisation de nouveaux numéros de conférence rendez-vous aux participants externes</span><span class="sxs-lookup"><span data-stu-id="449f5-335">Communicate the use of new dial-in conferencing numbers to external participants</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-336">Reconception du réseau planifiée</span><span class="sxs-lookup"><span data-stu-id="449f5-336">Planned network redesign</span></span></td>
<td align="left"><span data-ttu-id="449f5-337">Élevée</span><span class="sxs-lookup"><span data-stu-id="449f5-337">High</span></span></td>
<td align="left"><span data-ttu-id="449f5-338">Moyenne</span><span class="sxs-lookup"><span data-stu-id="449f5-338">Medium</span></span></td>
<td align="left"><span data-ttu-id="449f5-339">Moyenne</span><span class="sxs-lookup"><span data-stu-id="449f5-339">Medium</span></span></td>
<td align="left"><span data-ttu-id="449f5-340">Avant d’implémenter Teams comme plate-forme de communication et de collaboration moderne, exécuter l’évaluation de la préparation du réseau pour les sites dans le champ du projet</span><span class="sxs-lookup"><span data-stu-id="449f5-340">Before implementing Teams as modern communications and collaboration platform, run network readiness assessment for sites in scope of the project</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-341">_Tableau 5 - exemple de plan de gestion des risques_</span><span class="sxs-lookup"><span data-stu-id="449f5-341">_Table 5 Risk plan example_</span></span>


<a name="assess-environment-and-evaluate-adoption-readiness"></a><span data-ttu-id="449f5-342">Évaluer l'environnement et la préparation à l'adoption</span><span class="sxs-lookup"><span data-stu-id="449f5-342">Assess environment and evaluate adoption readiness</span></span>
--------------------------------------------------

<span data-ttu-id="449f5-343">Pour atteindre les objectifs et résultats clés, vous devez définir l’architecture globale de la solution.</span><span class="sxs-lookup"><span data-stu-id="449f5-343">To achieve the intended OKRs, you may have to define the high-level architecture of the solution.</span></span> <span data-ttu-id="449f5-344">Évaluer tous les aspects relatifs à l’infrastructure informatique et de téléphonie, à la mise en réseau et aux opérations nécessite une découverte de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="449f5-344">It takes environmental discovery to evaluate all aspects relating to IT and telephony infrastructure, networking, and operations.</span></span>

<span data-ttu-id="449f5-345">Toutes les questions liées à l’environnement informatique des utilisateurs finaux, tels que l’évaluation de la préparation des ordinateurs personnels et appareils mobiles pour prendre en charge les cas d’utilisation professionnelle de l’audioconférence, de la configuration matérielle requise à la configuration logicielle requise, seront incluses dans le cadre de la découverte de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="449f5-345">All matters related to end-user computing, such as readiness assessment of the personal computers and mobile devices to support Audio Conferencing business use cases, from hardware requirements to software requirements, will be included as part of the environmental discovery.</span></span>

<span data-ttu-id="449f5-346">La découverte de l’environnement peut également révéler s’il existe des exigences relatives au [transfert des numéros de téléphone à Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="449f5-346">Environmental discovery can also uncover if there are requirements to [transfer phone numbers to Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span> <span data-ttu-id="449f5-347">Cela permettra à votre organisation d’ajuster le plan du projet en conséquence et de préparer les infirmations nécessaires pour le transfert des numéros.</span><span class="sxs-lookup"><span data-stu-id="449f5-347">This will help your organization to adjust the project plan accordingly and prepare the necessary information required for number porting.</span></span> <span data-ttu-id="449f5-348">Vous pouvez effectuer la découverte de l’environnement en utilisant le [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995) suivant.</span><span class="sxs-lookup"><span data-stu-id="449f5-348">You can perform environmental discovery by leveraging the following [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995).</span></span>

<span data-ttu-id="449f5-349">La découverte de l’environnement doit inclure l’évaluation de la préparation du réseau pour s’assurer que celui-ci est prêt à prendre en charge l’implémentation du service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-349">Environmental discovery must include network readiness assessment to ensure the network is ready to support the implementation of the Audio Conferencing service.</span></span>

<span data-ttu-id="449f5-350">La préparation du réseau pour prendre en charge le service d’audioconférence peut être déterminée en utilisant les informations capturées par le biais de la découverte de l’environnement (comme les informations sur la connectivité Internet et la topologie du réseau étendu, les liens de sites, la bande passante disponible et les données d’analyse des personnes (qui peuvent être converties en utilisation prévue de chaque charge de travail) dans l’outil [My Advisor Network Planner](https://go.microsoft.com/fwlink/?linkid=858999).</span><span class="sxs-lookup"><span data-stu-id="449f5-350">Network readiness to support the Audio Conferencing service can be determined by leveraging the information captured through the environmental discovery (such as details of internet connectivity and WAN topology, site links, available bandwidth, and persona analysis data (that can be translated into an expected usage of each workload) into the [My Advisor Network Planner tool](https://go.microsoft.com/fwlink/?linkid=858999).</span></span> <span data-ttu-id="449f5-351">Pour confirmer la préparation du réseau, une simulation du trafic en temps réel peut être effectuée à l’aide des solutions fournies par [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) ou par les [partenaires d'outils d’évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=859003).</span><span class="sxs-lookup"><span data-stu-id="449f5-351">To further confirm network readiness, real-time media traffic simulation can be performed using the solutions provided by [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) or by [Network Readiness Assessment tools partners](https://go.microsoft.com/fwlink/?linkid=859003).</span></span>

<span data-ttu-id="449f5-352">Les résultats de l’évaluation de la préparation du réseau donneront une image plus claire de l’optimisation du réseau nécessaire ou de la correction requise pour réussir l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-352">The results of the Network Readiness Assessment will paint a clearer picture of the required network optimization or remediation required for the success of Audio Conferencing implementation.</span></span>

<span data-ttu-id="449f5-353">La préparation à l’adoption peut être évaluée en exécutant une analyse des personnes qui établira une liste des personnes dans l'organisation qui peuvent être ciblées pour l’implémentation du service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-353">Adoption readiness can be evaluated by executing persona analysis to come up with a list of personas in the organization who can be targeted for the implementation of Audio Conferencing service.</span></span> <span data-ttu-id="449f5-354">L’analyse des personnes inclut l’identification des périphériques ou dispositifs requis pour aboutir aux résultats de l’entreprise attendus.</span><span class="sxs-lookup"><span data-stu-id="449f5-354">The persona analysis includes the identification of additional peripherals or devices required to realize the intended business outcomes.</span></span>

<span data-ttu-id="449f5-355">Pour effectuer une analyse des personnes, vous pouvez organiser un atelier en impliquant les parties prenantes impliquées dans le projet, à l’aide du support d’atelier [Alignement des personnes](https://go.microsoft.com/fwlink/?linkid=859005) et de la [Matrice des fonctionnalités des personnes](https://go.microsoft.com/fwlink/?linkid=859006).</span><span class="sxs-lookup"><span data-stu-id="449f5-355">To perform persona analysis, you can conduct a workshop by involving relevant project stakeholders, leveraging the [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) workshop deck and [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span></span> <span data-ttu-id="449f5-356">Le résultat de l’atelier d’analyse des personnes peut être résumé dans un rapport à l’aide du modèle [Rapport d’analyse des personnes](https://go.microsoft.com/fwlink/?linkid=859007).</span><span class="sxs-lookup"><span data-stu-id="449f5-356">The result of persona analysis workshop can be summarized into a report using the [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) template.</span></span>


> [!NOTE]
> <span data-ttu-id="449f5-357">Les exemples de questionnaire de découverte et d’analyse des personnes ont été rédigés initialement pour Skype Entreprise Online, mais la plus grande partie du contenu s’applique à Teams.</span><span class="sxs-lookup"><span data-stu-id="449f5-357">While the Discovery Questionnaire and Persona Analysis examples were initially written for Skype for Business Online, a majority of the content is relevant to Teams.</span></span> <span data-ttu-id="449f5-358">N’hésitez pas à modifier et supprimer les éléments non pertinents par rapport aux objectifs du projet.</span><span class="sxs-lookup"><span data-stu-id="449f5-358">Feel free to modify and remove items that are not relevant to the project goals.</span></span>


<span data-ttu-id="449f5-359">Vous pouvez identifier les risques techniques dans le cadre de l’évaluation de l’environnement et de la préparation à l’adoption et élaborer un plan d’atténuation pour chaque risque identifié.</span><span class="sxs-lookup"><span data-stu-id="449f5-359">You can identify technical risks as part of an environmental assessment and adoption readiness evaluation and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="449f5-360">Ces informations doivent être incorporées dans le plan de gestion des risques.</span><span class="sxs-lookup"><span data-stu-id="449f5-360">This information should be incorporated as part of the risk plan.</span></span>

<a name="map-operational-roles"></a><span data-ttu-id="449f5-361">Mapper les rôles opérationnels</span><span class="sxs-lookup"><span data-stu-id="449f5-361">Map operational roles</span></span>
---------------------

<span data-ttu-id="449f5-362">La planification des opérations et l identification des équipes qui utiliseront le service d’audioconférence sont une étape importante, les opérations devant commencer lorsque les premiers utilisateurs pilotes sont activés.</span><span class="sxs-lookup"><span data-stu-id="449f5-362">Planning for operations and identifying the teams that will operate the Audio Conferencing service is an important step, as operations must start when the first pilot users are enabled.</span></span> <span data-ttu-id="449f5-363">Chaque équipe identifiée doit vérifier et contenir des tâches et responsabilités identifiées et commencer la préparation pour utiliser le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-363">Each identified team must review and agree on the tasks and responsibilities identified and start the preparation to operate the Audio Conferencing service.</span></span> <span data-ttu-id="449f5-364">La préparation doit inclure la formation et la préparation, le personnel supplémentaire ou s’assurer que les fournisseurs externes sont configurés pour fournir le service.</span><span class="sxs-lookup"><span data-stu-id="449f5-364">The preparation might include training and readiness, additional staffing, or ensuring external providers are set up to deliver the service.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-365">Rôle opérationnel</span><span class="sxs-lookup"><span data-stu-id="449f5-365">Operational Role</span></span></th>
<th align="left"><span data-ttu-id="449f5-366">Description</span><span class="sxs-lookup"><span data-stu-id="449f5-366">Description</span></span></th>
<th align="left"><span data-ttu-id="449f5-367">Équipe</span><span class="sxs-lookup"><span data-stu-id="449f5-367">Team</span></span></th>
<th align="left"><span data-ttu-id="449f5-368">Détails du contact</span><span class="sxs-lookup"><span data-stu-id="449f5-368">Contact Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-369">Propriétaire de service</span><span class="sxs-lookup"><span data-stu-id="449f5-369">Service Owner</span></span></td>
<td align="left"><span data-ttu-id="449f5-370">Propriétaire de service, interface avec les divisions de l’entreprise, stratégie</span><span class="sxs-lookup"><span data-stu-id="449f5-370">Service owner, interface to business divisions, strategy</span></span></td>
<td align="left"><span data-ttu-id="449f5-371">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-371">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-372">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-372">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-373">Opérations d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-373">Audio Conferencing Operations</span></span></td>
<td align="left"><span data-ttu-id="449f5-374">Opérations quotidiennes, déplacement/ajout/modification des comptes d’utilisateurs et d’appareils, supervision</span><span class="sxs-lookup"><span data-stu-id="449f5-374">Daily operations, user and device account move/add/change, monitoring</span></span></td>
<td align="left"><span data-ttu-id="449f5-375">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-375">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-376">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-376">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-377">Administration des clients</span><span class="sxs-lookup"><span data-stu-id="449f5-377">Tenant Admin</span></span></td>
<td align="left"><span data-ttu-id="449f5-378">Modifier les paramètres à l'échelle du client, activer les nouvelles fonctions</span><span class="sxs-lookup"><span data-stu-id="449f5-378">Change tenant-wide settings, enable new features</span></span></td>
<td align="left"><span data-ttu-id="449f5-379">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-379">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-380">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-380">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-381">Support technique</span><span class="sxs-lookup"><span data-stu-id="449f5-381">Help Desk</span></span></td>
<td align="left"><span data-ttu-id="449f5-382">Interface permettant aux utilisateurs finaux d’obtenir un support</span><span class="sxs-lookup"><span data-stu-id="449f5-382">Interface for end-users to get support</span></span></td>
<td align="left"><span data-ttu-id="449f5-383">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-383">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-384">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-384">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-385">Opérations réseau</span><span class="sxs-lookup"><span data-stu-id="449f5-385">Network Operations</span></span></td>
<td align="left"><span data-ttu-id="449f5-386">Exécution du réseau local, étendu, Wi-Fi et accès à Internet</span><span class="sxs-lookup"><span data-stu-id="449f5-386">Runs LAN, WAN, Wi-Fi, and Internet Access</span></span></td>
<td align="left"><span data-ttu-id="449f5-387">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-387">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-388">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-388">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-389">Équipe responsable des points de terminaison &amp; de client</span><span class="sxs-lookup"><span data-stu-id="449f5-389">Client &amp; Endpoints Team</span></span></td>
<td align="left"><span data-ttu-id="449f5-390">Gérer les déploiements de bureau</span><span class="sxs-lookup"><span data-stu-id="449f5-390">Manage desktop deployments</span></span></td>
<td align="left"><span data-ttu-id="449f5-391">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-391">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-392">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-392">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-393">Opérations d’identité</span><span class="sxs-lookup"><span data-stu-id="449f5-393">Identity Operations</span></span></td>
<td align="left"><span data-ttu-id="449f5-394">Gérer l’infrastructure d’identité (AD, ADFS, Azure AD)</span><span class="sxs-lookup"><span data-stu-id="449f5-394">Manage identity infrastructure (AD, ADFS, Azure AD)</span></span></td>
<td align="left"><span data-ttu-id="449f5-395">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-395">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-396">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-396">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-397">Adoption/gestion des changements</span><span class="sxs-lookup"><span data-stu-id="449f5-397">Adoption/change management</span></span></td>
<td align="left"><span data-ttu-id="449f5-398">Gérer la sensibilisation, la formation et l’adoption de la solution</span><span class="sxs-lookup"><span data-stu-id="449f5-398">Manage awareness, training and adoption for the solution</span></span></td>
<td align="left"><span data-ttu-id="449f5-399">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-399">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-400">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-400">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-401">Opérations Exchange</span><span class="sxs-lookup"><span data-stu-id="449f5-401">Exchange Operations</span></span></td>
<td align="left"><span data-ttu-id="449f5-402">Gère l’environnement Exchange</span><span class="sxs-lookup"><span data-stu-id="449f5-402">Manages the Exchange environment</span></span></td>
<td align="left"><span data-ttu-id="449f5-403">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-403">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-404">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-404">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-405">_Tableau 6 - exemple de mappage des rôles opérationnels_</span><span class="sxs-lookup"><span data-stu-id="449f5-405">_Table 6 Example of operational roles mapping_</span></span>


<span data-ttu-id="449f5-406">Pour permettre un mappage des rôles opérationnels plus détaillé, incluant les tâches associées à chaque rôle opérationnel, vous pouvez utiliser le [Classeur de mappage des rôles opérationnels](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) pour capturer les détails qui permettront d’avoir une vision claire des rôles et responsabilités pour la prise en charge du service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-406">To facilitate a more detailed operational roles mapping, including the tasks associated with each operational role, you can use the [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) to capture the details that will provide the clarity around roles and responsibilities to support Audio Conferencing service.</span></span>

<a name="document-success-plan"></a><span data-ttu-id="449f5-407">Documenter le plan de réussite</span><span class="sxs-lookup"><span data-stu-id="449f5-407">Document success plan</span></span>
---------------------

<span data-ttu-id="449f5-408">Un plan de réussite est une documentation créée dans la phase Planifier constituée d'un script commercial, de la préparation du service, d'un plan d’adoption et d’un plan opérationnel.</span><span class="sxs-lookup"><span data-stu-id="449f5-408">A success plan is the documentation created in the Envision phase that consists of business case, service readiness, adoption plan, and operational plan.</span></span>

<span data-ttu-id="449f5-409">Le plan de réussite fournira l’équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec des informations suffisantes pour réaliser les objectifs de l’organisation avec le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-409">The success plan will provide the project team, which can include FastTrack or deployment partner, with sufficient information to realize the organization’s goals with Audio Conferencing service.</span></span>

<span data-ttu-id="449f5-410">Généralement, un plan de réussite contiendra les sections principales suivantes :</span><span class="sxs-lookup"><span data-stu-id="449f5-410">In general, a success plan will contain the following main sections:</span></span>

-   <span data-ttu-id="449f5-411">Script commercial</span><span class="sxs-lookup"><span data-stu-id="449f5-411">Business case</span></span>

-   <span data-ttu-id="449f5-412">Préparation du service</span><span class="sxs-lookup"><span data-stu-id="449f5-412">Service readiness</span></span>

-   <span data-ttu-id="449f5-413">Plan d’adoption</span><span class="sxs-lookup"><span data-stu-id="449f5-413">Adoption plan</span></span>

-   <span data-ttu-id="449f5-414">Plan opérationnel</span><span class="sxs-lookup"><span data-stu-id="449f5-414">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="449f5-415">Script commercial</span><span class="sxs-lookup"><span data-stu-id="449f5-415">Business case</span></span>

<span data-ttu-id="449f5-416">Les cas d’utilisation professionnelle, les parties prenantes, les objectifs et résultats clés et les indicateurs de réussite clés, les risques et le planning du projet constituent généralement l’essentiel des informations nécessaires pour un script commercial.</span><span class="sxs-lookup"><span data-stu-id="449f5-416">Business use cases, stakeholders, OKRs and KSIs, risks, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="449f5-417">Vous devez les documenter dans le cadre du plan de réussite.</span><span class="sxs-lookup"><span data-stu-id="449f5-417">You need to document them as part of the success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="449f5-418">Préparation du service</span><span class="sxs-lookup"><span data-stu-id="449f5-418">Service readiness</span></span>

<span data-ttu-id="449f5-419">L’évaluation de l’environnement fournit les informations initiales nécessaires pour déterminer la préparation technique de l’organisation pour implémenter l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-419">Environmental assessment provides the initial information required to determine technical readiness for the organization to implement Audio Conferencing.</span></span>

<span data-ttu-id="449f5-420">Le plan pour régler les éléments nécessitant une correction découverts par le biais de l’évaluation de l’environnement est inclus ici.</span><span class="sxs-lookup"><span data-stu-id="449f5-420">Included here is the plan to address areas needing remediation discovered through environmental assessment.</span></span> <span data-ttu-id="449f5-421">Vous devez inclure l’évaluation de la préparation du service et le plan de correction au plan de réussite.</span><span class="sxs-lookup"><span data-stu-id="449f5-421">You need to include the service readiness assessment and remediation plan as part of the success plan.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="449f5-422">Plan d’adoption</span><span class="sxs-lookup"><span data-stu-id="449f5-422">Adoption plan</span></span>

<span data-ttu-id="449f5-423">Après l’évaluation de la préparation à l’adoption, une planification plus détaillée doit être fournie pour que l’équipe du projet puisse générer un ensemble complet de plans de communication, un plan de formation et des activités d’adoption avant, pendant et après le lancement.</span><span class="sxs-lookup"><span data-stu-id="449f5-423">Following an adoption readiness assessment, further detailed planning must be completed for the project team to come up with a comprehensive set of communication plans, training plan, and pre-launch, at-launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="449f5-424">Les ressources permettant d’appuyer les activités liées à l’adoption sont des prospectus, des courriers électroniques de bienvenue et les supports de formation identifiés dans cette étape, ainsi que les personnalisations nécessaires pour répondre aux besoins de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="449f5-424">Resources to support adoption activities such as flyers, welcome emails, and training materials are identified at this step, along with any customizations needed to meet organizational requirements.</span></span>

<span data-ttu-id="449f5-425">Les modèles d’activités d’adoption sont disponibles [ici](https://www.microsoft.com/download/details.aspx?id=54244).</span><span class="sxs-lookup"><span data-stu-id="449f5-425">The templates for adoption activities are available [here](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="449f5-426">Plan opérationnel</span><span class="sxs-lookup"><span data-stu-id="449f5-426">Operational plan</span></span>

<span data-ttu-id="449f5-427">L’activité de mappage des rôles opérationnels établira les rôles et les responsabilités, ainsi que les équipes affectées à chaque rôle opérationnel pour prendre en charge l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-427">Operational roles mapping exercise will establish the roles and responsibilities, and the teams assigned to each operational role to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="449f5-428">Vous devez effectuer cette étape et inclure le plan opérationnel dans le plan de réussite pour garantir la préparation opérationnelle de la solution.</span><span class="sxs-lookup"><span data-stu-id="449f5-428">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<span data-ttu-id="449f5-429">Planification de l’audioconférence dans Teams  <a name="Planning_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="449f5-429">Planning for Audio Conferencing in Teams  <a name="Planning_AudioConferencing"> </a></span></span>
========================================

<span data-ttu-id="449f5-430">Pour planifier l’implémentation de l’audioconférence dans Teams, une série de décisions doivent être prises au préalable afin de mieux préparer votre organisation à implémenter une solution qui répond aux besoins de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="449f5-430">To plan for the implementation of Audio Conferencing in Teams, a series of decisions must be made ahead of time to better prepare your organization to implement a solution that meets business requirements.</span></span> <span data-ttu-id="449f5-431">Ces décisions seront documentées dans un plan d’implémentation technique.</span><span class="sxs-lookup"><span data-stu-id="449f5-431">These decisions will be documented into a technical implementation plan.</span></span>

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a><span data-ttu-id="449f5-432">Disponibilité de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-432">Availability of Audio Conferencing</span></span>

<span data-ttu-id="449f5-433">L’audioconférence est disponible dans les [pays et régions suivants :](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="449f5-433">Audio Conferencing is available in these [countries and regions](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="449f5-434">En raison de contraintes juridiques, pour que l’audioconférence soit disponible dans les organisations multinationales, le contrat des abonnements Office 365 doit souscrit dans les pays et régions couverts par le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-434">Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions covered by Audio Conferencing service.</span></span>

<span data-ttu-id="449f5-435">Après avoir vérifié l’admissibilité de votre organisation à obtenir le service d’audioconférence, établissez la liste des emplacements des utilisateurs ou des bureaux où le service d’audioconférence sera implémenté en vous basant sur la liste des pays et régions disponibles.</span><span class="sxs-lookup"><span data-stu-id="449f5-435">After confirming your organization’s eligibility for obtaining the Audio Conferencing service, compile the list of user locations or offices where Audio Conferencing service will be implemented based on the list of available countries and regions.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="449f5-436">Points de décision</span><span class="sxs-lookup"><span data-stu-id="449f5-436">Decision Points</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-437">Déterminez les emplacements des utilisateurs ou les bureaux qui implémenteront le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-437">Decide which user locations or offices will implement the Audio Conferencing service.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="449f5-438">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="449f5-438">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-439">Consignez les emplacements des utilisateurs ou les bureaux qui seront habilités pour le service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-439">Document the user locations or offices to be enabled for the Audio Conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-440">Bureau</span><span class="sxs-lookup"><span data-stu-id="449f5-440">Office</span></span></th>
<th align="left"><span data-ttu-id="449f5-441">Emplacement</span><span class="sxs-lookup"><span data-stu-id="449f5-441">Location</span></span></th>
<th align="left"><span data-ttu-id="449f5-442">Service de conférence PSTN</span><span class="sxs-lookup"><span data-stu-id="449f5-442">PSTN Conference Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-443">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-443">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-444">Australie</span><span class="sxs-lookup"><span data-stu-id="449f5-444">Australia</span></span></td>
<td align="left"><span data-ttu-id="449f5-445">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-445">Audio Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-446">100 Cyberport Road</span><span class="sxs-lookup"><span data-stu-id="449f5-446">100 Cyberport Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-447">Hong Kong R.A.S.</span><span class="sxs-lookup"><span data-stu-id="449f5-447">Hong Kong SAR</span></span></td>
<td align="left"><span data-ttu-id="449f5-448">Conférence PSTN héritée</span><span class="sxs-lookup"><span data-stu-id="449f5-448">Legacy PSTN Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-449">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-449">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-450">Singapour</span><span class="sxs-lookup"><span data-stu-id="449f5-450">Singapore</span></span></td>
<td align="left"><span data-ttu-id="449f5-451">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-451">Audio Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-452">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-452">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-453">Royaume-Uni</span><span class="sxs-lookup"><span data-stu-id="449f5-453">United Kingdom</span></span></td>
<td align="left"><span data-ttu-id="449f5-454">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-454">Audio Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-455">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-455">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-456">France</span><span class="sxs-lookup"><span data-stu-id="449f5-456">France</span></span></td>
<td align="left"><span data-ttu-id="449f5-457">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-457">Audio Conferencing</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-458">_Tableau 7 - exemple de liste d’habilitations de sites pour le service d’audioconférence_</span><span class="sxs-lookup"><span data-stu-id="449f5-458">_Table 7 Example of Audio Conferencing service site enablement list_</span></span>


## <a name="licensing-for-audio-conferencing"></a><span data-ttu-id="449f5-459">Licences pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-459">Licensing for Audio Conferencing</span></span>

<span data-ttu-id="449f5-460">[La licence pour l’audioconférence](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), appelée auparavant Licence de conférence PSTN Skype Entreprise, est disponible dans le cadre des plans d’abonnement Office 365 E5, ou en tant que complément des plans d’abonnement Office 365 E1 ou Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="449f5-460">[Audio Conferencing license](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), formerly known as Skype for Business PSTN Conferencing license, is available as part of Office 365 E5 subscription plans, or as an add-on to Office 365 E1 or Office 365 E3 subscription plans.</span></span>

> [!NOTE]
> <span data-ttu-id="449f5-p120">La conférence PSTN ou rendez-vous dans Teams ne prend pas en charge les<sup></sup>-fournisseurs de service d’audioconférence tiers (ACP). </span><span class="sxs-lookup"><span data-stu-id="449f5-p120">PSTN or dial-in conferencing in Teams does not support 3<sup>rd</sup>-party Audio Conferencing Providers (ACPs). </span></span><br><span data-ttu-id="449f5-462">Si vous utilisez déjà la conférence PSTN Skype Entreprise Online, vous pouvez bénéficier immédiatement de l’audioconférence dans Teams.</span><span class="sxs-lookup"><span data-stu-id="449f5-462">If you already use Skype for Business Online PSTN Conferencing today, you can immediately take advantage of Audio Conferencing in Teams.</span></span>

<span data-ttu-id="449f5-463">Pour fournir des numéros gratuits de pont de téléconférence et pour prendre en charge les appels de téléconférence vers des numéros internationaux, vous devez configurer des [crédits de communication](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="449f5-463">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to International phone numbers, you need to setup [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) for your organization.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="449f5-464">Certains pays sont desservis uniquement par des numéros gratuits de téléconférence et, dans ce cas, l’utilisation de crédits de communication est obligatoire pour prendre en charge la composition de numéros pour ces pays.</span><span class="sxs-lookup"><span data-stu-id="449f5-464">Some countries are serviced by toll-free conference bridge phone numbers only, and in this case the use of Communications Credits is a mandatory requirement to support dial in for such countries.</span></span>

<span data-ttu-id="449f5-465">Le premier élément à prendre en compte lors de l’implémentation de crédits de communication est de décider du montant initial des fonds à acheter.</span><span class="sxs-lookup"><span data-stu-id="449f5-465">The first consideration to make when implementing Communications Credits is to decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="449f5-466">Les montants de financement recommandés peuvent être obtenus dans la documentation sur les [crédits de communication](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).</span><span class="sxs-lookup"><span data-stu-id="449f5-466">Recommended funding amounts can be referenced from the [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span>

<span data-ttu-id="449f5-467">Si votre organisation choisit d’utiliser la recharge automatique, une recommandation sur le déclencheur (montant des fonds le moins élevé) est également incluse dans la documentation sur les [crédits de communication](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).</span><span class="sxs-lookup"><span data-stu-id="449f5-467">If your organization chooses to use auto-recharge, a recommendation on the trigger (lowest amount of funds) is also included in the [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span> <span data-ttu-id="449f5-468">Le montant de la recharge automatique doit être déterminé par l’utilisation réelle.</span><span class="sxs-lookup"><span data-stu-id="449f5-468">Auto-recharge amount needs to be determined by the actual usage.</span></span> <span data-ttu-id="449f5-469">L’utilisation des crédits de communication doit être contrôlée au fil du temps et le montant de la recharge doit être ajusté en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="449f5-469">Communications Credits usage should be monitored over time and the recharge amount needs to be adjusted as required.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="449f5-470">Points de décision</span><span class="sxs-lookup"><span data-stu-id="449f5-470">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-471">Si votre organisation n’a pas déjà acheté les licences requises pour l’audioconférence, déterminez si les licences seront acquises en passant à des niveaux d’abonnement Office 365 supérieurs ou en achetant des compléments pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-471">If your organization has not already purchased the required Audio Conferencing licensing, decide whether Audio Conferencing licenses will be acquired by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-ons.</span></span></li>
<li><span data-ttu-id="449f5-472">Déterminez si des crédits de communication sont requis pour l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-472">Decide if Communications Credits is required for Audio Conferencing implementation.</span></span> <span data-ttu-id="449f5-473">Si c’est le cas, déterminez le montant initial des fonds qui doit être acheté.</span><span class="sxs-lookup"><span data-stu-id="449f5-473">If so, decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="449f5-474">Le cas échéant, déterminez le montant déclencheur et celui de la recharge automatique.</span><span class="sxs-lookup"><span data-stu-id="449f5-474">Where applicable, decide the trigger amount and auto-recharge amount.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="449f5-475">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="449f5-475">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-476">Consignez les utilisateurs à qui une licence d’audioconférence sera attribuée.</span><span class="sxs-lookup"><span data-stu-id="449f5-476">Document the users that will be assigned Audio Conferencing license.</span></span></li>
<li><span data-ttu-id="449f5-477">Documentez le plan de crédits de communication (montant initial, montant déclencheur, montant de la recharge automatique).</span><span class="sxs-lookup"><span data-stu-id="449f5-477">Document the Communications Credits plan (initial amount, trigger amount, auto-recharge amount).</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-478">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="449f5-478">User</span></span></th>
<th align="left"><span data-ttu-id="449f5-479">Bureau</span><span class="sxs-lookup"><span data-stu-id="449f5-479">Office</span></span></th>
<th align="left"><span data-ttu-id="449f5-480">Licence Office 365</span><span class="sxs-lookup"><span data-stu-id="449f5-480">Office 365 License</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-481">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="449f5-481">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="449f5-482">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-482">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-483">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="449f5-483">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-484">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="449f5-484">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="449f5-485">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-485">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-486">Office 365 E3, complément pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-486">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-487">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="449f5-487">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="449f5-488">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-488">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-489">Office 365 E3, complément pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-489">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-490">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="449f5-490">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="449f5-491">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-491">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-492">Office 365 E3, complément pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-492">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-493">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="449f5-493">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="449f5-494">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-494">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-495">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="449f5-495">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-496">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="449f5-496">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="449f5-497">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-497">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-498">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="449f5-498">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-499">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="449f5-499">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="449f5-500">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-500">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-501">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="449f5-501">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-502">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="449f5-502">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="449f5-503">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-503">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-504">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="449f5-504">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-505">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="449f5-505">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="449f5-506">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-506">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-507">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="449f5-507">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-508">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="449f5-508">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="449f5-509">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-509">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-510">Office 365 E3, complément pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-510">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-511">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="449f5-511">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="449f5-512">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-512">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-513">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="449f5-513">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-514">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="449f5-514">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="449f5-515">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-515">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-516">Office 365 E3, complément pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-516">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-517">_Tableau 8 - exemple de liste d’attributions de licences pour les organisateurs de réunions en audioconférence_</span><span class="sxs-lookup"><span data-stu-id="449f5-517">_Table 8 Example of license assignment list for Audio Conferencing meeting organizers_</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-518">Montant initial</span><span class="sxs-lookup"><span data-stu-id="449f5-518">Initial amount</span></span></th>
<td align="left"><span data-ttu-id="449f5-519">1 000 $</span><span class="sxs-lookup"><span data-stu-id="449f5-519">$ 1,000</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-520">Montant déclencheur</span><span class="sxs-lookup"><span data-stu-id="449f5-520">Trigger amount</span></span></th>
<td align="left"><span data-ttu-id="449f5-521">400 $</span><span class="sxs-lookup"><span data-stu-id="449f5-521">$ 400</span></span></td>
</tr>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-522">Montant de la recharge automatique</span><span class="sxs-lookup"><span data-stu-id="449f5-522">Auto-recharge amount</span></span></th>
<td align="left"><span data-ttu-id="449f5-523">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-523">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-524">_Tableau 9 - exemple de numéros de planification de crédits de communication_</span><span class="sxs-lookup"><span data-stu-id="449f5-524">_Table 9 Example of Communications Credits planning numbers_</span></span>


## <a name="conference-bridge-phone-numbers"></a><span data-ttu-id="449f5-525">Numéros de pont de téléconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-525">Conference bridge phone numbers</span></span>

<span data-ttu-id="449f5-526">Le service d’audioconférence dans Office 365 inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="449f5-526">The Audio Conferencing service in Office 365 includes:</span></span>

-   <span data-ttu-id="449f5-527">plusieurs types de numéros de pont de téléconférence (payants et gratuits) ;</span><span class="sxs-lookup"><span data-stu-id="449f5-527">Multiple types of conference bridge phone numbers (Toll and Toll-Free)</span></span>

-   <span data-ttu-id="449f5-528">plusieurs catégories de numéros de téléphone (dédiés et partagés) ;</span><span class="sxs-lookup"><span data-stu-id="449f5-528">Multiple categories of the phone number (dedicated and shared)</span></span>

-   <span data-ttu-id="449f5-529">prise en charge de plusieurs langues pour le pont de téléconférence (principale et secondaire) ;</span><span class="sxs-lookup"><span data-stu-id="449f5-529">Support for multiple languages for the conference bridge (primary and secondary)</span></span>

-   <span data-ttu-id="449f5-530">numéro de téléphone par défaut du client.</span><span class="sxs-lookup"><span data-stu-id="449f5-530">A default phone number for the tenant.</span></span>

<span data-ttu-id="449f5-531">Vous trouverez une description complète des fonctionnalités incluses dans les rubriques [Configurer la conférence rendez-vous ou PSTN dans Skype Entreprise](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) et [Numéros de téléphone pour la conférence rendez-vous](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span><span class="sxs-lookup"><span data-stu-id="449f5-531">Full description of the included capabilities can be referenced from [Set up dial-in or PSTN conferencing for Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) and [Phone numbers for dial-in conferencing](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span></span>

> [!NOTE]
> <span data-ttu-id="449f5-532">Les numéros de pont de téléconférence dédiés sont inclus dans le calcul de la limite du nombre de numéros de téléphone qui peuvent être achetés par client, en fonction du nombre de licences applicables comme il est décrit dans la rubrique [Obtenir des numéros de téléphone du service Skype Entreprise](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span><span class="sxs-lookup"><span data-stu-id="449f5-532">Dedicated conference bridge phone numbers are counted towards the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses as described in [Getting Skype for Business service phone numbers](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span></span> <span data-ttu-id="449f5-533">Les numéros de pont de téléconférence gratuits requièrent des crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="449f5-533">Toll-free conference bridge phone numbers require Communications Credits.</span></span>

<span data-ttu-id="449f5-534">Si des numéros de pont de téléconférence existants doivent être transférés vers le service d’audioconférence, en partant du principe qu'ils répondent aux exigences spécifiques au pays, ils peuvent être transférés vers Microsoft.</span><span class="sxs-lookup"><span data-stu-id="449f5-534">If there are existing conference bridge phone numbers that must be transferred to the Audio Conferencing service, assuming they are meeting the country-specific requirements, then the existing conference bridge phone numbers can be transferred to Microsoft.</span></span>


> [!NOTE]
> <span data-ttu-id="449f5-535">Le transfert de numéros de téléphone vers Microsoft est plus ou moins complexe selon les pays ou régions, les opérateurs, le nombre de circuits concernés et de nombreux autres facteurs.</span><span class="sxs-lookup"><span data-stu-id="449f5-535">Complexity of transferring phone numbers to Microsoft varies greatly based on the countries or regions, carriers, the number of circuits involved, and many other contributing factors.</span></span> <span data-ttu-id="449f5-536">Pour planifier un transfert de numéros de téléphone, consultez le [Guide de transfert de numéros](https://go.microsoft.com/fwlink/?linkid=859011).</span><span class="sxs-lookup"><span data-stu-id="449f5-536">To plan for phone number porting, check out the [Number Porting Guide](https://go.microsoft.com/fwlink/?linkid=859011).</span></span>

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

<span data-ttu-id="449f5-537">Vous trouverez des informations complémentaires sur le transfert de numéros de téléphone vers le service d’audioconférence dans la rubrique [Transférer des numéros de téléphone vers Skype Entreprise Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="449f5-537">Additional details on transferring phone numbers to Audio Conferencing service can be found in [Transfer phone numbers to Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="449f5-538">Points de décision</span><span class="sxs-lookup"><span data-stu-id="449f5-538">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-539">Déterminer si l’organisation a besoin de numéros de pont de téléconférence dédiés</span><span class="sxs-lookup"><span data-stu-id="449f5-539">Decide whether the organization requires dedicated conference bridge phone numbers</span></span></li>
<li><span data-ttu-id="449f5-540">Déterminer comment les numéros de pont de téléconférence dédiés seront obtenus pour les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence (les obtenir auprès de Microsoft ou transférer des numéros de téléphone existants)</span><span class="sxs-lookup"><span data-stu-id="449f5-540">Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (obtain from Microsoft or transfer existing phone numbers)</span></span></li>
<li><span data-ttu-id="449f5-541">Si vous choisissez de les obtenir auprès de Microsoft, décider de la méthode pour les obtenir (envoi de formulaire ou automatisé) pour les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-541">If you choose to obtain from Microsoft, decide the method to obtain phone numbers (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation</span></span></li>
<li><span data-ttu-id="449f5-542">Déterminer les préférences de langue à configurer pour chaque numéro de pont de téléconférence dédié</span><span class="sxs-lookup"><span data-stu-id="449f5-542">Decide the language preferences to be set up for each dedicated conference bridge phone number</span></span></li>
<li><span data-ttu-id="449f5-543">Décider du numéro de pont de téléconférence par défaut du client</span><span class="sxs-lookup"><span data-stu-id="449f5-543">Decide the tenant default conference bridge phone number</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="449f5-544">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="449f5-544">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-545">Documentez le plan général d’acquisition de numéros de téléphone, en détaillant comment les numéros de téléphone seront obtenus pour chaque emplacement d’utilisateur ou bureau concernés par l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-545">Document the master plan for phone numbers acquisition, detailing how phone numbers will be obtained for each user location or office in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="449f5-546">Le cas échéant, remplir <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">le formulaire de demande de nouveau numéro de téléphone</a> (un formulaire par emplacement ou bureau)</span><span class="sxs-lookup"><span data-stu-id="449f5-546">If applicable, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">the New Telephone Number Request form</a>, one form for each location or office</span></span></li>
<li><span data-ttu-id="449f5-547">Si vous choisissez de transférer des numéros de téléphone existants, consultez le <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guide de transfert de numéros</a> pour le planifier et ajuster le planning d’implémentation de l’audioconférence en conséquence.</span><span class="sxs-lookup"><span data-stu-id="449f5-547">If you choose to transfer existing phone numbers, check out the <a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide</a> to plan it and adjust Audio Conferencing implementation timeline accordingly.</span></span></li>
<li><span data-ttu-id="449f5-548">Documenter les configurations détaillées des numéros de pont de téléconférence (numéros de pont de téléconférence partagés et dédiés, préférences de langue pour chaque numéro de pont de téléconférence dédié, numéro de pont de téléconférence par défaut du client)</span><span class="sxs-lookup"><span data-stu-id="449f5-548">Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number)</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-549">Bureau</span><span class="sxs-lookup"><span data-stu-id="449f5-549">Office</span></span></th>
<th align="left"><span data-ttu-id="449f5-550">Acquisition de numéro de pont de téléconférence et type de pont</span><span class="sxs-lookup"><span data-stu-id="449f5-550">Bridge Number Acquisition and Bridge Type</span></span></th>
<th align="left"><span data-ttu-id="449f5-551">Numéro du pont</span><span class="sxs-lookup"><span data-stu-id="449f5-551">Bridge Number</span></span></th>
<th align="left"><span data-ttu-id="449f5-552">Langue du pont</span><span class="sxs-lookup"><span data-stu-id="449f5-552">Bridge Language</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-553">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-553">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-554">Acquisition d'un nouveau numéro de pont dédié</span><span class="sxs-lookup"><span data-stu-id="449f5-554">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="449f5-555">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-555">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-556">Anglais (Australie)</span><span class="sxs-lookup"><span data-stu-id="449f5-556">English (Australia)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-557">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-557">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-558">Acquisition d'un nouveau numéro de pont partagé</span><span class="sxs-lookup"><span data-stu-id="449f5-558">Acquire new, shared</span></span></td>
<td align="left"><span data-ttu-id="449f5-559">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-559">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-560">Anglais (États-Unis), Chinois (simplifié, RPC)</span><span class="sxs-lookup"><span data-stu-id="449f5-560">English (United States), Chinese (Simplified, PRC)</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-561">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-561">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-562">Port existant, dédié</span><span class="sxs-lookup"><span data-stu-id="449f5-562">Port existing, dedicated</span></span></td>
<td align="left"><span data-ttu-id="449f5-563">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="449f5-563">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="449f5-564">Anglais (Royaume-Uni)</span><span class="sxs-lookup"><span data-stu-id="449f5-564">English (United Kingdom)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-565">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-565">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-566">Acquisition d'un nouveau numéro de pont dédié</span><span class="sxs-lookup"><span data-stu-id="449f5-566">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="449f5-567">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-567">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-568">Français (France), Anglais (Royaume-Uni)</span><span class="sxs-lookup"><span data-stu-id="449f5-568">French (France), English (United Kingdom)</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-569">_Tableau 10 - exemple de détails de pont de téléconférence_</span><span class="sxs-lookup"><span data-stu-id="449f5-569">_Table 10 Example of conference bridge details_</span></span>


> [!NOTE]
> <span data-ttu-id="449f5-570">Le tableau d’exemple ci-dessus et les tableaux suivants dans ce document sont utilisés comme modèle</span><span class="sxs-lookup"><span data-stu-id="449f5-570">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="449f5-571">« TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.</span><span class="sxs-lookup"><span data-stu-id="449f5-571">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

## <a name="conference-bridge-settings"></a><span data-ttu-id="449f5-572">Paramètres du pont de téléconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-572">Conference bridge settings</span></span>

<span data-ttu-id="449f5-573">Des options de configuration à l’échelle de l’organisation relatives à l’expérience de participation aux réunions en audioconférence (notification d’accès et de sortie de réunion et enregistrement du numéro de l’appelant), à la longueur du code PIN des organisateurs de réunion et à la notification par courrier électronique sont disponibles afin de personnaliser davantage l’expérience des utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="449f5-573">Organization-wide configuration options around Audio Conferencing meeting join experience (meeting entry and exit notification and caller name recording), meeting organizer’s PIN length, and email notification are available to further tailor the end-user experience.</span></span>

-   <span data-ttu-id="449f5-574">Les notifications d’accès et de sortie de réunion sont disponibles sous la forme de nom enregistré, de numéro de téléphone et de tonalités.</span><span class="sxs-lookup"><span data-stu-id="449f5-574">Meeting entry and exit notifications are available in the form of recorded name, phone number, and tones.</span></span>

-   <span data-ttu-id="449f5-575">La longueur du code PIN peut être configurée entre 4 et 12 chiffres, un code PIN de 5 chiffres étant configuré par défaut.</span><span class="sxs-lookup"><span data-stu-id="449f5-575">PIN length is configurable from 4 to 12 digits, with a 5-digit PIN as the default.</span></span>

-   <span data-ttu-id="449f5-576">Les notifications par courrier électronique lors de l’activation d'une licence d’audioconférence ou d’autres modifications effectuées par un administrateur sont activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="449f5-576">Notification emails upon enablement of Audio Conferencing license or any other admin-driven changes are enabled by default.</span></span> <span data-ttu-id="449f5-577">Vous pouvez désactiver cette fonction et contrôler les communications des utilisateurs finaux de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="449f5-577">You can disable this feature and take control of your organization’s end-user communications.</span></span>

<span data-ttu-id="449f5-578">Pour les utilisateurs à qui une licence d’audioconférence a été attribuée, les numéros payants/gratuits, présentés dans les coordonnées d’audioconférence, peuvent être configurés pour utiliser :</span><span class="sxs-lookup"><span data-stu-id="449f5-578">For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, are configurable to use:</span></span>

-   <span data-ttu-id="449f5-579">le numéro par défaut au niveau du client, ou</span><span class="sxs-lookup"><span data-stu-id="449f5-579">the tenant-level default, or</span></span>

-   <span data-ttu-id="449f5-580">les numéros de pont de téléconférence attribués automatiquement, ou</span><span class="sxs-lookup"><span data-stu-id="449f5-580">the automatically-assigned conference bridge phone numbers, or</span></span>

-   <span data-ttu-id="449f5-581">des numéros de pont de téléconférence définis manuellement pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="449f5-581">manually defined conference bridge phone numbers for each user.</span></span>

<span data-ttu-id="449f5-582">Des numéros de pont de téléconférence spécifiques aux utilisateurs sont généralement utiles dans les organisations mondiales ou à l'échelle du pays ou de la région où les utilisateurs sont distribués et doivent fournir des numéros locaux comme numéros de pont de téléconférence par défaut dans les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="449f5-582">User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in the meeting invites.</span></span>

<span data-ttu-id="449f5-583">Les participants qui rejoignent les réunions depuis des villes ou pays différents peuvent rechercher les numéros supplémentaires configurés au niveau du client, mais ces numéros n’apparaissent pas dans les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="449f5-583">Participants joining from different cities or overseas can look up additional numbers configured at the tenant-level, but these numbers do not appear directly in the meeting invites.</span></span> <span data-ttu-id="449f5-584">Les invitations aux réunions fournissent un lien qui dirige les participants vers la page des numéros à composer pour la conférence Teams afin qui leur permet de rechercher les numéros de pont de téléconférence les plus proches disponibles pour leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="449f5-584">The meeting invites provide a link that will take participants to the Teams Conference Dial-in Numbers page for them to lookup the closest conference bridge phone numbers available from their location.</span></span>

<span data-ttu-id="449f5-585">Vous pouvez également configurer comment les utilisateurs non authentifiés sont gérés par chaque organisateur de réunion individuel : exiger que l’organisateur de la réunion commence la réunion avant que les appelants non authentifiés soient admis ou autoriser les appelants non authentifiés à démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="449f5-585">You can also configure how unauthenticated callers are handled by each individual meeting organizer, whether to require meeting organizer to start the meeting before unauthenticated callers are admitted, or to allow unauthenticated callers to start a meeting.</span></span>

<span data-ttu-id="449f5-586">Des configurations supplémentaires pouvant être appliquées pour chaque utilisateur sont disponibles pour contrôler l’utilisation de numéros de pont de téléconférence gratuits et les appels depuis une conférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-586">Additional configurations that can be applied for each user are available to control the use of toll-free conference bridge phone numbers and dial-out from a conference.</span></span>

> [!NOTE]
> <span data-ttu-id="449f5-587">Ces contrôles liés au coût ne sont disponibles actuellement que pour les utilisateurs précoces.</span><span class="sxs-lookup"><span data-stu-id="449f5-587">These cost-related controls are currently available for preview customers only.</span></span> <span data-ttu-id="449f5-588">Vous pouvez inscrire votre organisation au programme d’évaluation depuis la page [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span><span class="sxs-lookup"><span data-stu-id="449f5-588">You can enroll your organization in the preview program from [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span></span>

<span data-ttu-id="449f5-589">Ces contrôles vous permettent de déterminer si les organisateurs de réunions peuvent fournir des numéros de pont de téléconférence gratuits pour les réunions qu’ils organisent, et de contrôler si les participants peuvent composer des numéros depuis les réunions qu'ils ont organisées.</span><span class="sxs-lookup"><span data-stu-id="449f5-589">With these controls, you can decide whether meeting organizers can provide toll-free conference bridge phone numbers for meetings organized by them, and to control whether participants can dial out from the meetings organized by them.</span></span> <span data-ttu-id="449f5-590">Les niveaux de contrôle sont les suivants : ne pas autoriser la composition de numéros, autoriser uniquement la composition de numéros nationaux, autoriser la composition de numéros nationaux et internationaux.</span><span class="sxs-lookup"><span data-stu-id="449f5-590">The level of dial-out control spans from disallowing dial out, only allowing dial out to domestic numbers, to allowing dial out to both domestic and international numbers.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="449f5-591">Points de décision</span><span class="sxs-lookup"><span data-stu-id="449f5-591">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-592">Déterminez si l’organisation requiert des notifications d’accès et de sortie de réunion et, le cas échéant, le type de notification à implémenter (tonalités, numéro de téléphone ou nom enregistré).</span><span class="sxs-lookup"><span data-stu-id="449f5-592">Decide whether the organization requires entry and exit notifications, and if yes, the type of notification to be implemented (tones, phone number, or recorded name).</span></span></li>
<li><span data-ttu-id="449f5-593">Déterminez la longueur du code PIN pour l’audioconférence qui correspond aux exigences de sécurité de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="449f5-593">Decide the Audio Conferencing PIN length that meets the organizational security requirements.</span></span></li>
<li><span data-ttu-id="449f5-594">Déterminez si l’organisation souhaite contrôler les communications des utilisateurs finaux liées au service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-594">Decide if the organization wants to take control of end-user communications related to Audio Conferencing service.</span></span></li>
<li><span data-ttu-id="449f5-595">Déterminez les numéros de pont de téléconférence à attribuer à chaque organisateur de réunions.</span><span class="sxs-lookup"><span data-stu-id="449f5-595">Decide the conference bridge phone numbers to be assigned to each meeting organizer.</span></span></li>
<li><span data-ttu-id="449f5-596">Déterminez si certains organisateurs de réunions doivent pouvoir utiliser des numéros de pont de téléconférence gratuits pour leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="449f5-596">Decide whether some meeting organizers require the ability to use toll-free conference bridge phone numbers for their meeings</span></span></li>
<li><span data-ttu-id="449f5-597">Déterminez si certains organisateurs de réunions doivent pouvoir autoriser les appelants non authentifiés à démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="449f5-597">Decide whether some meeting organizers require the ability to allow unauthenticated callers to start a meeting.</span></span></li>
<li><span data-ttu-id="449f5-598">Déterminez si la composition des numéros doit être contrôlée pour certains organisateurs de réunions.</span><span class="sxs-lookup"><span data-stu-id="449f5-598">Decide whether some meeting organizers require conference dial out to be controlled.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="449f5-599">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="449f5-599">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-600">Consignez les paramètres détaillés de pont de téléconférence (notifications d’accès et de sortie de réunion, longueur du code PIN, notification par courrier électronique des modifications de configuration).</span><span class="sxs-lookup"><span data-stu-id="449f5-600">Document the detailed conference bridge settings (entry and exit notifications, PIN length, configuration change email notification).</span></span></li>
<li><span data-ttu-id="449f5-601">Consignez les numéros de pont de téléconférence qui seront attribués à chaque organisateur de réunions et le paramètre correspondant de la stratégie de contrôle des appelants non authentifiés et pour les numéros gratuits et les appels.</span><span class="sxs-lookup"><span data-stu-id="449f5-601">Document the conference bridge phone numbers to be assinged to each meeting organizer and the corresponding setting to control unauthenticated caller’s policy, and toll-free and dial out controls.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="449f5-602"><strong>Activer les notifications d’accès et de sortie de réunion</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-602"><strong>Enable meeting entry and exit notifications</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-603">Activé</span><span class="sxs-lookup"><span data-stu-id="449f5-603">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="449f5-604"><strong>Type d’annonce d’accès/sortie</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-604"><strong>Entry/exit announcement type</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-605">Tonalités</span><span class="sxs-lookup"><span data-stu-id="449f5-605">Tones</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="449f5-606"><strong>Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-606"><strong>Ask callers to record their name before joining the meeting</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-607">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-607">Disabled</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="449f5-608"><strong>Longueur du code PIN</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-608"><strong>PIN length</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-609">5</span><span class="sxs-lookup"><span data-stu-id="449f5-609">5</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="449f5-610"><strong>Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de numérotation changent</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-610"><strong>Automatically send emails to users if their dial-in settings change</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-611">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-611">Disabled</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-612">_Tableau 11 - exemple de paramètres de pont de téléconférence_</span><span class="sxs-lookup"><span data-stu-id="449f5-612">_Table 11 Example of conference bridge settings_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-613">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="449f5-613">User</span></span></th>
<th align="left"><span data-ttu-id="449f5-614">Bureau</span><span class="sxs-lookup"><span data-stu-id="449f5-614">Office</span></span></th>
<th align="left"><span data-ttu-id="449f5-615">Numéro payant par défaut</span><span class="sxs-lookup"><span data-stu-id="449f5-615">Default toll number</span></span></th>
<th align="left"><span data-ttu-id="449f5-616">Numéro gratuit par défaut</span><span class="sxs-lookup"><span data-stu-id="449f5-616">Default toll-free number</span></span></th>
<th align="left"><span data-ttu-id="449f5-617">Autoriser le numéro gratuit</span><span class="sxs-lookup"><span data-stu-id="449f5-617">Allow toll-free</span></span></th>
<th align="left"><span data-ttu-id="449f5-618">Les appelants non authentifiés contournent la salle d’attente</span><span class="sxs-lookup"><span data-stu-id="449f5-618">Unauthenticated callers bypass lobby</span></span></th>
<th align="left"><span data-ttu-id="449f5-619">Composition de numéros depuis la conférence</span><span class="sxs-lookup"><span data-stu-id="449f5-619">Conference dial out</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-620">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="449f5-620">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="449f5-621">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-621">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-622">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-622">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-623">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-623">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-624">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-624">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-625">Activé</span><span class="sxs-lookup"><span data-stu-id="449f5-625">Enabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-626">Internationaux et nationaux</span><span class="sxs-lookup"><span data-stu-id="449f5-626">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-627">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="449f5-627">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="449f5-628">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-628">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-629">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-629">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-630">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-630">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-631">Non</span><span class="sxs-lookup"><span data-stu-id="449f5-631">No</span></span></td>
<td align="left"><span data-ttu-id="449f5-632">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-632">Disabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-633">Non autorisé</span><span class="sxs-lookup"><span data-stu-id="449f5-633">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-634">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="449f5-634">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="449f5-635">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-635">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-636">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-636">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-637">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-637">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-638">Non</span><span class="sxs-lookup"><span data-stu-id="449f5-638">No</span></span></td>
<td align="left"><span data-ttu-id="449f5-639">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-639">Disabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-640">Non autorisé</span><span class="sxs-lookup"><span data-stu-id="449f5-640">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-641">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="449f5-641">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="449f5-642">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-642">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-643">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-643">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-644">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-644">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-645">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-645">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-646">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-646">Disabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-647">Nationaux</span><span class="sxs-lookup"><span data-stu-id="449f5-647">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-648">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="449f5-648">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="449f5-649">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-649">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-650">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-650">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-651">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-651">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-652">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-652">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-653">Activé</span><span class="sxs-lookup"><span data-stu-id="449f5-653">Enabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-654">Nationaux</span><span class="sxs-lookup"><span data-stu-id="449f5-654">Domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-655">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="449f5-655">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="449f5-656">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-656">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-657">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-657">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-658">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-658">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-659">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-659">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-660">Activé</span><span class="sxs-lookup"><span data-stu-id="449f5-660">Enabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-661">Nationaux</span><span class="sxs-lookup"><span data-stu-id="449f5-661">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-662">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="449f5-662">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="449f5-663">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-663">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-664">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="449f5-664">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="449f5-665">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-665">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-666">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-666">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-667">Activé</span><span class="sxs-lookup"><span data-stu-id="449f5-667">Enabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-668">Non autorisé</span><span class="sxs-lookup"><span data-stu-id="449f5-668">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-669">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="449f5-669">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="449f5-670">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-670">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-671">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="449f5-671">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="449f5-672">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-672">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-673">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-673">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-674">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-674">Disabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-675">Non autorisé</span><span class="sxs-lookup"><span data-stu-id="449f5-675">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-676">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="449f5-676">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="449f5-677">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-677">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-678">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="449f5-678">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="449f5-679">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-679">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-680">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-680">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-681">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-681">Disabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-682">Non autorisé</span><span class="sxs-lookup"><span data-stu-id="449f5-682">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-683">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="449f5-683">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="449f5-684">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-684">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-685">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-685">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-686">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-686">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-687">Non</span><span class="sxs-lookup"><span data-stu-id="449f5-687">No</span></span></td>
<td align="left"><span data-ttu-id="449f5-688">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-688">Disabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-689">Nationaux</span><span class="sxs-lookup"><span data-stu-id="449f5-689">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-690">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="449f5-690">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="449f5-691">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-691">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-692">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-692">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-693">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-693">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-694">Oui</span><span class="sxs-lookup"><span data-stu-id="449f5-694">Yes</span></span></td>
<td align="left"><span data-ttu-id="449f5-695">Activé</span><span class="sxs-lookup"><span data-stu-id="449f5-695">Enabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-696">Internationaux et nationaux</span><span class="sxs-lookup"><span data-stu-id="449f5-696">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-697">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="449f5-697">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="449f5-698">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-698">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-699">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-699">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-700">TBA</span><span class="sxs-lookup"><span data-stu-id="449f5-700">TBA</span></span></td>
<td align="left"><span data-ttu-id="449f5-701">Non</span><span class="sxs-lookup"><span data-stu-id="449f5-701">No</span></span></td>
<td align="left"><span data-ttu-id="449f5-702">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-702">Disabled</span></span></td>
<td align="left"><span data-ttu-id="449f5-703">Nationaux</span><span class="sxs-lookup"><span data-stu-id="449f5-703">Domestic</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-704">_Tableau 12 - exemple d’affectations de paramètres de pont de téléconférence_</span><span class="sxs-lookup"><span data-stu-id="449f5-704">_Table 12 Example of conference bridge settings assignments_</span></span>


## <a name="dial-plans"></a><span data-ttu-id="449f5-705">Plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="449f5-705">Dial plans</span></span>

<span data-ttu-id="449f5-706">Un [Plan de numérotation](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), une fonctionnalité de système téléphonique d’Office 365, est un ensemble de règles de normalisation qui convertit les numéros de téléphone composés dans un autre format (généralement le format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) pour l’autorisation et le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="449f5-706">A [Dial Plan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), a Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically [E.164](https://go.microsoft.com/fwlink/?linkid=859014) format) for call authorization and call routing.</span></span> <span data-ttu-id="449f5-707">Le service d’audioconférence utilise les mêmes fonctionnalités que le système téléphonique pour convertir les numéros de téléphone en scénarios de numéros composés depuis la conférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-707">Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial out scenarios.</span></span>

<span data-ttu-id="449f5-708">Un plan de numérotation permet aux utilisateurs de composer des numéros de téléphone comme ils le font habituellement, par exemple en omettant l'indicatif régional pour les appels locaux, l'indicatif du pays ou de la région pour les appels nationaux ou même en composant un numéro court lorsqu'ils passent un appel depuis une conférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-708">A dial plan allows users to dial phone numbers the way they are accustomed to, such as omitting area code for local calls, omitting country code for domestic calls, or even using short digit dialing when performing conference dial out.</span></span>

<span data-ttu-id="449f5-709">La fonctionnalité de système téléphonique d’Office 365 comporte deux types de plans de numérotation :</span><span class="sxs-lookup"><span data-stu-id="449f5-709">Within the Phone System feature of Office 365, there are two types of dial plans:</span></span>

-   <span data-ttu-id="449f5-710">**Plan de numérotation de service**.</span><span class="sxs-lookup"><span data-stu-id="449f5-710">**Service dial plan**.</span></span> <span data-ttu-id="449f5-711">Il s’agit du plan de numérotation par défaut, qui est appliqué aux utilisateurs selon l’emplacement d’utilisation d’Office 365, et il ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="449f5-711">This is the default dial plan and applied to users based on Office 365 usage location, and it cannot be modified.</span></span>

<!-- -->

-   <span data-ttu-id="449f5-712">**Plan de numérotation de client**.</span><span class="sxs-lookup"><span data-stu-id="449f5-712">**Tenant dial plan**.</span></span> <span data-ttu-id="449f5-713">Ce plan de numérotation peut être personnalisé au sein d'un client, et divisé en deux types :</span><span class="sxs-lookup"><span data-stu-id="449f5-713">This is a customizable dial plan within a tenant, and further divided into two types:</span></span>

    -   <span data-ttu-id="449f5-714">**Plan de numérotation de client global** : ce plan de numérotation s’applique à tous les utilisateurs au sein du client.</span><span class="sxs-lookup"><span data-stu-id="449f5-714">**Tenant-global dial plan**—the dial plan applies to all users within the tenant.</span></span>

    -   <span data-ttu-id="449f5-715">**Plan de numérotation d’utilisateurs du client** : ce plan de numérotation s’applique uniquement à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="449f5-715">**Tenant-user dial plan**—the dial plan applies only to specific users.</span></span>


> [!NOTE]
> <span data-ttu-id="449f5-716">Pour des informations détaillées et des exemples, consultez la documentation [Plans de numérotation du forfait d’appels Office 365](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b).</span><span class="sxs-lookup"><span data-stu-id="449f5-716">Check out the [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) documentation for further details and examples.</span></span>

<span data-ttu-id="449f5-717">Le plan de numérotation efficace affecté aux utilisateurs est la combinaison du plan de numérotation de service (basé sur l’emplacement d’utilisation d’Office 365 des utilisateurs) et du plan de numérotation de client (il peut s’agir d’un plan de numérotation de client.global ou d'un plan de numérotation d’utilisateurs du client).</span><span class="sxs-lookup"><span data-stu-id="449f5-717">The effective dial plan assigned to users is the combination of service dial plan (based on user’s Office 365 usage location) and tenant dial plan (can be either tenant-global dial plan or tenant-user dial plan).</span></span>

![Le tableau présente trois combinaisons de plans de numérotation de client et de service.](media/audio_conferencing_image8.png)

<span data-ttu-id="449f5-719">Il existe 25 règles de normalisation au maximum dans chaque plan de numérotation de client, et le double emploi des règles de normalisation déjà disponibles dans le plan de numérotation de service doit donc être évité.</span><span class="sxs-lookup"><span data-stu-id="449f5-719">There is a maximum of 25 normalization rules in each tenant dial plan, and thus duplication with normalization rules already available as part of service dial plan needs to be avoided.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="449f5-720">Points de décision</span><span class="sxs-lookup"><span data-stu-id="449f5-720">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-721">Déterminez si votre organisation requiert des plans de numérotation personnalisés (besoins de l’entreprise, exigences en matière d’adoption, etc.).</span><span class="sxs-lookup"><span data-stu-id="449f5-721">Decide if your organization requires customized dial plans (business requirements, adoption requirements, etc.).</span></span></li>
<li><span data-ttu-id="449f5-722">Le cas échéant, déterminez la portée du plan de numérotation de client (global au sein du client ou utilisateurs du client) pour prendre en charge les exigences des plans de numérotation personnalisés.</span><span class="sxs-lookup"><span data-stu-id="449f5-722">If applicable, decide the scope of tenant dial plan (tenant-global or tenant-user) to support the requirements for customized dial plans.</span></span></li>
<li><span data-ttu-id="449f5-723">Le cas échéant, déterminez les plans de numérotation de client qui seront créés pour prendre en charge les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-723">If applicable, decide the tenant dial plans that will be created to support user locations or offices in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="449f5-724">Le cas échéant, déterminez le plan de numérotation personnalisé et le plan de numérotation de client.qui doit être affecté à chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="449f5-724">If applicable, decide which user require customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="449f5-725">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="449f5-725">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="449f5-726">Consignez les plans de numérotation personnalisés et les règles de normalisation associées à configurer dans le cadre de l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-726">Document the customized dial plans and the associated normalization rules to be configured as part of Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="449f5-727">Consignez les utilisateurs auxquels le plan de numérotation personnalisé sera affecté et le plan de numérotation de client.qui doit être affecté à chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="449f5-727">Document the users to be assigned with customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-728">Nom/description du plan de numérotation de client.</span><span class="sxs-lookup"><span data-stu-id="449f5-728">Tenant Dial Plan Name/Description</span></span></th>
<th align="left"><span data-ttu-id="449f5-729">Nom/description des règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="449f5-729">Normalization Rules Name/Description</span></span></th>
<th align="left"><span data-ttu-id="449f5-730">Modèle</span><span class="sxs-lookup"><span data-stu-id="449f5-730">Pattern</span></span></th>
<th align="left"><span data-ttu-id="449f5-731">Conversion</span><span class="sxs-lookup"><span data-stu-id="449f5-731">Translation</span></span></th>
<th align="left"><span data-ttu-id="449f5-732">IsInternalExtension</span><span class="sxs-lookup"><span data-stu-id="449f5-732">IsInternalExtension</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="449f5-733"><strong>AU-NSW-NorthRyde-OER</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-733"><strong>AU-NSW-NorthRyde-OER</strong></span></span></p>
<p><span data-ttu-id="449f5-734"><em>1 Epping Road North Ryde, NSW, plan de numérotation AU</em></span><span class="sxs-lookup"><span data-stu-id="449f5-734"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="449f5-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span></span></p>
<p><span data-ttu-id="449f5-736"><em>Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie</em></span><span class="sxs-lookup"><span data-stu-id="449f5-736"><em>Internal number (x7000 - x7999) for One Epping Road office, North Ryde, NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-737">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="449f5-737">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="449f5-738">+6125550$1</span><span class="sxs-lookup"><span data-stu-id="449f5-738">+6125550$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-739">True</span><span class="sxs-lookup"><span data-stu-id="449f5-739">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="449f5-740"><strong>AU-NSW-Local</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-740"><strong>AU-NSW-Local</strong></span></span></p>
<p><span data-ttu-id="449f5-741"><em>Normalisation du numéro local pour NSW, Australie</em></span><span class="sxs-lookup"><span data-stu-id="449f5-741"><em>Local number normalization for NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-742">^([2-9]\d{7})$</span><span class="sxs-lookup"><span data-stu-id="449f5-742">^([2-9]\d{7})$</span></span></td>
<td align="left"><span data-ttu-id="449f5-743">+612$1</span><span class="sxs-lookup"><span data-stu-id="449f5-743">+612$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-744">False</span><span class="sxs-lookup"><span data-stu-id="449f5-744">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="449f5-745"><strong>AU-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-745"><strong>AU-TollFree</strong></span></span></p>
<p><span data-ttu-id="449f5-746"><em>Normalisation du numéro gratuit pour l’Australie</em></span><span class="sxs-lookup"><span data-stu-id="449f5-746"><em>Toll Free number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-747">^(1[38]\d{4,8})\d*$</span><span class="sxs-lookup"><span data-stu-id="449f5-747">^(1[38]\d{4,8})\d*$</span></span></td>
<td align="left"><span data-ttu-id="449f5-748">+61$1</span><span class="sxs-lookup"><span data-stu-id="449f5-748">+61$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-749">False</span><span class="sxs-lookup"><span data-stu-id="449f5-749">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="449f5-750"><strong>AU-Service</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-750"><strong>AU-Service</strong></span></span></p>
<p><span data-ttu-id="449f5-751"><em>Normalisation du numéro de service pour l’Australie</em></span><span class="sxs-lookup"><span data-stu-id="449f5-751"><em>Service number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-752">^(000|1[0125]\d{1,8})$</span><span class="sxs-lookup"><span data-stu-id="449f5-752">^(000|1[0125]\d{1,8})$</span></span></td>
<td align="left"><span data-ttu-id="449f5-753">$1</span><span class="sxs-lookup"><span data-stu-id="449f5-753">$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-754">False</span><span class="sxs-lookup"><span data-stu-id="449f5-754">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="449f5-755"><strong>SG-Singapore-OMB</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-755"><strong>SG-Singapore-OMB</strong></span></span></p>
<p><span data-ttu-id="449f5-756"><em>OMB Singapour, plan de numérotation SG</em></span><span class="sxs-lookup"><span data-stu-id="449f5-756"><em>OMB Singapore, SG Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="449f5-757"><strong>SG-OMB-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-757"><strong>SG-OMB-Internal</strong></span></span></p>
<p><span data-ttu-id="449f5-758"><em>Numéro interne (x8000 – x8999) du bureau OMB, Singapour</em></span><span class="sxs-lookup"><span data-stu-id="449f5-758"><em>Internal number (x8000 – x8999) for OMB office, Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-759">^(8\d{3})$</span><span class="sxs-lookup"><span data-stu-id="449f5-759">^(8\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="449f5-760">+656888$1</span><span class="sxs-lookup"><span data-stu-id="449f5-760">+656888$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-761">True</span><span class="sxs-lookup"><span data-stu-id="449f5-761">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="449f5-762"><strong>SG-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-762"><strong>SG-TollFree</strong></span></span></p>
<p><span data-ttu-id="449f5-763"><em>Normalisation du numéro gratuit pour Singapour</em></span><span class="sxs-lookup"><span data-stu-id="449f5-763"><em>Toll Free number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-764">^(1?800\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="449f5-764">^(1?800\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="449f5-765">+65$1</span><span class="sxs-lookup"><span data-stu-id="449f5-765">+65$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-766">False</span><span class="sxs-lookup"><span data-stu-id="449f5-766">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="449f5-767"><strong>SG-Service</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-767"><strong>SG-Service</strong></span></span></p>
<p><span data-ttu-id="449f5-768"><em>Normalisation du numéro de service pour Singapour</em></span><span class="sxs-lookup"><span data-stu-id="449f5-768"><em>Service number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-769">^(1\d{3,4}|9\d{2})$</span><span class="sxs-lookup"><span data-stu-id="449f5-769">^(1\d{3,4}|9\d{2})$</span></span></td>
<td align="left"><span data-ttu-id="449f5-770">$1</span><span class="sxs-lookup"><span data-stu-id="449f5-770">$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-771">False</span><span class="sxs-lookup"><span data-stu-id="449f5-771">False</span></span></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="449f5-772"><strong>FR-Paris-Issy-39qdPR</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-772"><strong>FR-Paris-Issy-39qdPR</strong></span></span></p>
<p><span data-ttu-id="449f5-773"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France</em></span><span class="sxs-lookup"><span data-stu-id="449f5-773"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="449f5-774"><strong>FR-39qdPR-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-774"><strong>FR-39qdPR-Internal</strong></span></span></p>
<p><span data-ttu-id="449f5-775"><em>Numéro interne (x7000 – x7999) du bureau 39 quai du Président Roosevelt, Issy-les-Moulineaux, France</em></span><span class="sxs-lookup"><span data-stu-id="449f5-775"><em>Internal number (x7000 – x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-776">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="449f5-776">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="449f5-777">+3319999$1</span><span class="sxs-lookup"><span data-stu-id="449f5-777">+3319999$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-778">True</span><span class="sxs-lookup"><span data-stu-id="449f5-778">True</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="449f5-779"><strong>FR-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-779"><strong>FR-TollFree</strong></span></span></p>
<p><span data-ttu-id="449f5-780"><em>Normalisation du numéro gratuit pour la France</em></span><span class="sxs-lookup"><span data-stu-id="449f5-780"><em>Toll Free number normalization for France</em></span></span></p></td>
<td align="left"><span data-ttu-id="449f5-781">^0?(80\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="449f5-781">^0?(80\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="449f5-782">+33$1</span><span class="sxs-lookup"><span data-stu-id="449f5-782">+33$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-783">False</span><span class="sxs-lookup"><span data-stu-id="449f5-783">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="449f5-784"><strong>FR-Service</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-784"><strong>FR-Service</strong></span></span></p>
<p><span data-ttu-id="449f5-785"><em>Normalisation du numéro de service pour la France</em></span><span class="sxs-lookup"><span data-stu-id="449f5-785"><em>Service number normalization for France</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="449f5-786">^(1\d{1,2}|11[68]\d{3}|</span><span class="sxs-lookup"><span data-stu-id="449f5-786">^(1\d{1,2}|11[68]\d{3}|</span></span></p>
<p><span data-ttu-id="449f5-787">10\d{2}|3\d{3})$</span><span class="sxs-lookup"><span data-stu-id="449f5-787">10\d{2}|3\d{3})$</span></span></p></td>
<td align="left"><span data-ttu-id="449f5-788">$1</span><span class="sxs-lookup"><span data-stu-id="449f5-788">$1</span></span></td>
<td align="left"><span data-ttu-id="449f5-789">False</span><span class="sxs-lookup"><span data-stu-id="449f5-789">False</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-790">_Tableau 13 - exemple de plans de numérotation de client_</span><span class="sxs-lookup"><span data-stu-id="449f5-790">_Table 13 Example of tenant dial plans_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="449f5-791">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="449f5-791">User</span></span></th>
<th align="left"><span data-ttu-id="449f5-792">Bureau</span><span class="sxs-lookup"><span data-stu-id="449f5-792">Office</span></span></th>
<th align="left"><span data-ttu-id="449f5-793">Type de plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="449f5-793">Dial Plan Type</span></span></th>
<th align="left"><span data-ttu-id="449f5-794">Nom du plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="449f5-794">Dial Plan Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-795">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="449f5-795">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="449f5-796">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-796">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-797">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-797">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-798">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="449f5-798">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-799">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="449f5-799">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="449f5-800">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-800">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-801">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-801">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-802">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="449f5-802">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-803">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="449f5-803">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="449f5-804">1 Eppîng Road</span><span class="sxs-lookup"><span data-stu-id="449f5-804">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="449f5-805">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-805">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-806">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="449f5-806">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-807">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="449f5-807">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="449f5-808">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-808">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-809">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-809">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-810">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="449f5-810">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-811">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="449f5-811">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="449f5-812">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-812">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-813">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-813">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-814">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="449f5-814">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-815">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="449f5-815">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="449f5-816">1 Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="449f5-816">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="449f5-817">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-817">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-818">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="449f5-818">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-819">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="449f5-819">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="449f5-820">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-820">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-821">Plan de numérotation de service</span><span class="sxs-lookup"><span data-stu-id="449f5-821">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-822">N/A</span><span class="sxs-lookup"><span data-stu-id="449f5-822">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-823">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="449f5-823">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="449f5-824">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-824">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-825">Plan de numérotation de service</span><span class="sxs-lookup"><span data-stu-id="449f5-825">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-826">N/A</span><span class="sxs-lookup"><span data-stu-id="449f5-826">N/A</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-827">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="449f5-827">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="449f5-828">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="449f5-828">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="449f5-829">Plan de numérotation de service</span><span class="sxs-lookup"><span data-stu-id="449f5-829">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-830">N/A</span><span class="sxs-lookup"><span data-stu-id="449f5-830">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-831">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="449f5-831">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="449f5-832">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-832">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-833">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-833">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-834">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="449f5-834">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-835">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="449f5-835">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="449f5-836">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-836">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-837">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-837">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-838">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="449f5-838">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="449f5-839">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="449f5-839">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="449f5-840">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="449f5-840">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="449f5-841">Plan de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-841">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="449f5-842">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="449f5-842">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-843">_Tableau 14 - exemple d’affectations de plan de numérotation_</span><span class="sxs-lookup"><span data-stu-id="449f5-843">_Table 14 Example of dial plan assignments_</span></span>


## <a name="microsoft-teams-configurations"></a><span data-ttu-id="449f5-844">Configurations de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="449f5-844">Microsoft Teams configurations</span></span>

<span data-ttu-id="449f5-845">L’audioconférence n’étant disponible que pour les réunions planifiées, les configurations au niveau du client qui régissent la planification des réunions (réunions privées et de canal) doivent être activées.</span><span class="sxs-lookup"><span data-stu-id="449f5-845">Since Audio Conferencing is only available for scheduled meetings, tenant-level configurations that govern meeting scheduling (private and channel meetings) must be enabled.</span></span>


> [!NOTE]
> <span data-ttu-id="449f5-846">Actuellement, si votre organisation a des exigences de conformité exigeant que toutes les discussions en réunion puissent être découvertes, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres sur site Exchange.</span><span class="sxs-lookup"><span data-stu-id="449f5-846">Currently, if your organization has compliance requirements to ensure all meeting discussions are discoverable, you should disable private meetings if the organizer has an Exchange on-premises mailbox.</span></span><br><br>
> <span data-ttu-id="449f5-847">Dans un autre cas d’utilisation, si toutes les réunions dans l’organisation doivent être visibles <strong>pour les parties invitées</strong> uniquement, afin d’empêcher que les informations sur les réunions soient divulguées aux parties non invitées, nous vous recommandons de désactiver la possibilité de planifier des réunions dans les <strong>canaux</strong>.</span><span class="sxs-lookup"><span data-stu-id="449f5-847">In another use case, if all meetings in the organization must be visible <strong>to invited parties</strong> only, to avoid disclosing meeting information to uninvited parties, we recommend that you disable the ability to schedule meetings in <strong>channels</strong>.</span></span>

<span data-ttu-id="449f5-848">Les paramètres, disponibles en tant que configurations au niveau du client, s’appliquent à tous les utilisateurs dans l’organisation et auront une incidence sur toutes les planifications de réunions dans Teams, et non pas uniquement aux réunions Teams **avec** l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-848">The settings, available as tenant-level configurations, are applicable to all users in the organization, and will impact all meeting scheduling in Teams, not specific to Teams meetings **with** Audio Conferencing.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="449f5-849">Point de décision</span><span class="sxs-lookup"><span data-stu-id="449f5-849">Decision Point</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-850">Déterminez si l’organisation requiert que la planification de réunions privées soit activée ou désactivée.</span><span class="sxs-lookup"><span data-stu-id="449f5-850">Decide if the organization requires to enable or disable scheduling of private meetings.</span></span></p>
<p><span data-ttu-id="449f5-851">Déterminez si l’organisation requiert que la planification de réunions de canal soit activée ou désactivée.</span><span class="sxs-lookup"><span data-stu-id="449f5-851">Decide if the organization requires to enable or disable scheduling of channel meetings.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="449f5-852">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="449f5-852">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="449f5-853">Consignez les configurations de planification de réunions de Teams.</span><span class="sxs-lookup"><span data-stu-id="449f5-853">Document the meeting scheduling configurations for Teams.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="449f5-854"><strong>Autoriser la planification de réunions privées</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-854"><strong>Allow scheduling for private meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-855">Activé</span><span class="sxs-lookup"><span data-stu-id="449f5-855">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><span data-ttu-id="449f5-856"><strong>Autoriser la planification de réunions de canal</strong></span><span class="sxs-lookup"><span data-stu-id="449f5-856"><strong>Allow scheduling for channel meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="449f5-857">Désactivé</span><span class="sxs-lookup"><span data-stu-id="449f5-857">Disabled</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="449f5-858">_Tableau 15 - exemple de configurations de réunions Microsoft Teams_</span><span class="sxs-lookup"><span data-stu-id="449f5-858">_Table 15 Example of Microsoft Teams meetings configurations_</span></span>


## <a name="document-technical-implementation-plan"></a><span data-ttu-id="449f5-859">Documenter le plan d’implémentation technique</span><span class="sxs-lookup"><span data-stu-id="449f5-859">Document technical implementation plan</span></span>

<span data-ttu-id="449f5-860">Utilisez les points de décision ci-dessus pour documenter votre plan d’implémentation technique.</span><span class="sxs-lookup"><span data-stu-id="449f5-860">Use the decision points above to document your technical implementation plan.</span></span>

<span data-ttu-id="449f5-861">Ce plan d’implémentation technique fournira l’équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec les informations nécessaires pour exécuter l’intégration technique pour l’implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="449f5-861">This technical implementation plan will provide the project team, which can include FastTrack or a deployment partner, with the information required to execute the technical onboarding for the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="449f5-862">Généralement, un plan d’implémentation technique contiendra les sections principales suivantes :</span><span class="sxs-lookup"><span data-stu-id="449f5-862">In general, a technical implementation plan will contain the following main sections:</span></span>

-   <span data-ttu-id="449f5-863">Liste d’habilitations de sites pour le service d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-863">Audio Conferencing service site enablement list</span></span>

-   <span data-ttu-id="449f5-864">Liste d’attributions de licences pour les organisateurs de réunions en audioconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-864">License assignment list for Audio Conferencing meeting organizers</span></span>

-   <span data-ttu-id="449f5-865">Numéros de planification de crédits de communication</span><span class="sxs-lookup"><span data-stu-id="449f5-865">Communications Credits planning numbers</span></span>

-   <span data-ttu-id="449f5-866">Détails du pont de téléconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-866">Conference bridge details</span></span>

-   <span data-ttu-id="449f5-867">Paramètres du pont de téléconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-867">Conference bridge settings</span></span>

-   <span data-ttu-id="449f5-868">Affectations de paramètres de pont de téléconférence</span><span class="sxs-lookup"><span data-stu-id="449f5-868">Conference bridge settings assignments</span></span>

-   <span data-ttu-id="449f5-869">Plans de numérotation de client</span><span class="sxs-lookup"><span data-stu-id="449f5-869">Tenant dial plans</span></span>

-   <span data-ttu-id="449f5-870">Affectations du plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="449f5-870">Dial plan assignments</span></span>

-   <span data-ttu-id="449f5-871">Configurations des réunions Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="449f5-871">Microsoft Teams meetings configurations</span></span>

<span data-ttu-id="449f5-872">Une fois les plans de réussite et d’implémentation technique établis, vous êtes prêt à faire franchir à votre organisation les étapes suivantes du parcours du client d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="449f5-872">With the completion of success plan and technical implementation plan, you are now ready to take your organization to the next steps along the Office 365 customer journey.</span></span>

<a name="onboard"></a><span data-ttu-id="449f5-873">Intégrer</span><span class="sxs-lookup"><span data-stu-id="449f5-873">Onboard</span></span>
=======

<span data-ttu-id="449f5-874">*Bientôt disponible.*</span><span class="sxs-lookup"><span data-stu-id="449f5-874">*Coming soon.*</span></span>

<a name="drive-value"></a><span data-ttu-id="449f5-875">Générer une valeur ajoutée</span><span class="sxs-lookup"><span data-stu-id="449f5-875">Drive Value</span></span>
===========

<span data-ttu-id="449f5-876">*Bientôt disponible.*</span><span class="sxs-lookup"><span data-stu-id="449f5-876">*Coming soon.*</span></span>



### <a name="see-also"></a><span data-ttu-id="449f5-877">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="449f5-877">See also</span></span>
[<span data-ttu-id="449f5-878">Configurer la conférence rendez-vous ou PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="449f5-878">Set up dial-in or PSTN conferencing for Skype for Business</span></span>](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
