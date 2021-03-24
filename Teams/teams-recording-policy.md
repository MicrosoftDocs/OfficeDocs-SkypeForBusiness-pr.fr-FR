---
title: Présentation de l’enregistrement de stratégie Teams pour les appels & réunions
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: En savoir plus sur l’enregistrement de stratégie Teams pour les appels & réunions
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd2b83c5b96ab9049783a774c56297b51179e68e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094034"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="9e01a-103">Présentation de l’enregistrement de stratégie Teams pour les appels et & réunions</span><span class="sxs-lookup"><span data-stu-id="9e01a-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="9e01a-104">L’enregistrement basé sur une stratégie permet aux organisations qui adoptent Microsoft Teams pour les appels et les réunions d’être en cours, à l’aide d’une stratégie d’administration, lorsque les appels et les réunions en ligne doivent être enregistrés et capturés automatiquement pour un traitement et une rétention ultérieurs, comme requis par la stratégie d’entreprise ou réglementaires pertinente.</span><span class="sxs-lookup"><span data-stu-id="9e01a-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="9e01a-105">Teams a été amélioré pour prendre en charge l’intégration de solutions d’enregistrement tierces, notamment les fonctionnalités de plateforme, les expériences utilisateur et les interfaces d’administration nécessaires pour fournir une solution de bout en bout pour la configuration, la gestion, l’enregistrement, le stockage et l’analyse des communications Teams.</span><span class="sxs-lookup"><span data-stu-id="9e01a-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="9e01a-106">Les améliorations ont été apportées aux API de plateforme de communication et aux événements pour l’enregistrement, qui offrent les possibilités suivantes :</span><span class="sxs-lookup"><span data-stu-id="9e01a-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="9e01a-107">Capture transparente et de haute qualité des médias sur tous les appareils et tous les points de terminaison pris en charge pour l’audio, la vidéo, le partage d’écran et la conversation.</span><span class="sxs-lookup"><span data-stu-id="9e01a-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="9e01a-108">Prise en charge de la capture d’interaction entre les utilisateurs de Teams et points de terminaison d’appel pris en charge (Teams, Teams Mobile, Skype Entreprise, PSTN)</span><span class="sxs-lookup"><span data-stu-id="9e01a-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="9e01a-109">Nouvelles stratégies d’administration pour l’enregistrement de la conformité, notamment l’intégration aux stratégies et outils d’appel d’administration et de réunion Teams existants</span><span class="sxs-lookup"><span data-stu-id="9e01a-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="9e01a-110">L’enregistrement de conformité peut être activé pour les utilisateurs de Microsoft 365 A3/A5/E3/E5/Business Premium et des utilisateurs d’Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="9e01a-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="9e01a-111">Les fonctionnalités d’intégration de la solution d’enregistrement de la conformité ont également été examinées dans Ignite 2019 dans l’enregistrement de [<span class="underline">conformité et la session Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)</span><span class="sxs-lookup"><span data-stu-id="9e01a-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="9e01a-112">Vue d’ensemble de l’enregistrement de l’interaction Teams</span><span class="sxs-lookup"><span data-stu-id="9e01a-112">Teams interaction recording overview</span></span>

<span data-ttu-id="9e01a-113">Les cas d’utilisation des enregistrements d’interaction peuvent être séparés en quatre catégories principales de fonctionnalités d’enregistrement : Commodité, Fonctionnel, Organisationnel et Origine légitime, comme illustré dans l’image :</span><span class="sxs-lookup"><span data-stu-id="9e01a-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="9e01a-114">![Capture d’écran montrant l’enregistrement de l’interaction.](media/recording-taxonomy.png "L’image affiche les catégories d’enregistrements.")</span><span class="sxs-lookup"><span data-stu-id="9e01a-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="9e01a-115">Chacune de ces catégories implique des exigences différentes en matière de procédure d’enregistrement, d’enregistrement, de stock des enregistrements, d’notification, de contrôle de l’accès et de gestion de la rétention.</span><span class="sxs-lookup"><span data-stu-id="9e01a-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="9e01a-116">Type</span><span class="sxs-lookup"><span data-stu-id="9e01a-116">Type</span></span>                   | <span data-ttu-id="9e01a-117">Commodité (enregistrement Teams normal)</span><span class="sxs-lookup"><span data-stu-id="9e01a-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="9e01a-118">Organisation - régulée (enregistrement de conformité)</span><span class="sxs-lookup"><span data-stu-id="9e01a-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="9e01a-119">Initiator</span><span class="sxs-lookup"><span data-stu-id="9e01a-119">Initiator</span></span>              | <span data-ttu-id="9e01a-120">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e01a-120">User</span></span>               | <span data-ttu-id="9e01a-121">Administrateur (système)</span><span class="sxs-lookup"><span data-stu-id="9e01a-121">Admin (system)</span></span>  |
| <span data-ttu-id="9e01a-122">Cible</span><span class="sxs-lookup"><span data-stu-id="9e01a-122">Target</span></span>                 | <span data-ttu-id="9e01a-123">Par appel/réunion</span><span class="sxs-lookup"><span data-stu-id="9e01a-123">Per-call / meeting</span></span> | <span data-ttu-id="9e01a-124">Par utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e01a-124">Per-user</span></span>        |
| <span data-ttu-id="9e01a-125">Propriétaire du stockage</span><span class="sxs-lookup"><span data-stu-id="9e01a-125">Storage owner</span></span>          | <span data-ttu-id="9e01a-126">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e01a-126">User</span></span>               | <span data-ttu-id="9e01a-127">Conformité</span><span class="sxs-lookup"><span data-stu-id="9e01a-127">Compliance</span></span>      |
| <span data-ttu-id="9e01a-128">Notification requise ?</span><span class="sxs-lookup"><span data-stu-id="9e01a-128">Notification required?</span></span> | <span data-ttu-id="9e01a-129">Oui</span><span class="sxs-lookup"><span data-stu-id="9e01a-129">Yes</span></span>                | <span data-ttu-id="9e01a-130">Oui</span><span class="sxs-lookup"><span data-stu-id="9e01a-130">Yes</span></span>             |
| <span data-ttu-id="9e01a-131">Propriétaire d’Access</span><span class="sxs-lookup"><span data-stu-id="9e01a-131">Access Owner</span></span>           | <span data-ttu-id="9e01a-132">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e01a-132">User</span></span>               | <span data-ttu-id="9e01a-133">Conformité</span><span class="sxs-lookup"><span data-stu-id="9e01a-133">Compliance</span></span>      |
| <span data-ttu-id="9e01a-134">Stratégie de rétention ?</span><span class="sxs-lookup"><span data-stu-id="9e01a-134">Retention Policy?</span></span>      | <span data-ttu-id="9e01a-135">Facultatif</span><span class="sxs-lookup"><span data-stu-id="9e01a-135">Optional</span></span>           | <span data-ttu-id="9e01a-136">Oui</span><span class="sxs-lookup"><span data-stu-id="9e01a-136">Yes</span></span>             |

<span data-ttu-id="9e01a-137">Teams offre différentes fonctionnalités pour l’enregistrement [<span class="underline">pratique</span>](./cloud-recording.md) et fonctionnel de réunions et d’événements en direct.</span><span class="sxs-lookup"><span data-stu-id="9e01a-137">Teams provides various capabilities for [<span class="underline">convenient</span>](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="9e01a-138">L’enregistrement organisationnel signifie permettre aux organisations qui adoptent Teams pour les appels et les réunions d’être en cours d’utilisation, par le moyen d’une stratégie administrative, lorsque les appels et les réunions en ligne doivent être enregistrés et capturés automatiquement à des fins de traitement et de rétention ultérieurs, comme requis par la stratégie d’entreprise ou réglementaires pertinente.</span><span class="sxs-lookup"><span data-stu-id="9e01a-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="9e01a-139">Les utilisateurs dans le cadre de cette stratégie se rendront compte que leurs interactions numériques avec Teams sont enregistrées, mais ne pourront pas désactiver l’enregistrement et n’auront pas accès à l’enregistrement une fois l’interaction terminée.</span><span class="sxs-lookup"><span data-stu-id="9e01a-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="9e01a-140">L’enregistrement devient partie intégrante de l’archive organisationnelle mise à la disposition du personnel juridique et de conformité pour la découverte électronique, la conservation légale et d’autres utilisations de la rétention d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9e01a-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="9e01a-141">Exemples de besoins de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e01a-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9e01a-142"><strong>Personnage</strong></span><span class="sxs-lookup"><span data-stu-id="9e01a-142"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="9e01a-143"><strong>Besoins</strong></span><span class="sxs-lookup"><span data-stu-id="9e01a-143"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9e01a-144">Utilisateurs enregistrés</span><span class="sxs-lookup"><span data-stu-id="9e01a-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9e01a-145">Soyez informé lorsque l’enregistrement est en cours.</span><span class="sxs-lookup"><span data-stu-id="9e01a-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="9e01a-146">Soyez informé lorsque l’erreur de stratégie et/ou d’enregistreur entraîne des modifications du comportement des appels.</span><span class="sxs-lookup"><span data-stu-id="9e01a-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e01a-147">Administrateur des communications</span><span class="sxs-lookup"><span data-stu-id="9e01a-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9e01a-148">Comprenez pourquoi et comment appliquer / appliquer des stratégies d’enregistrement aux utilisateurs/points de terminaison Teams.</span><span class="sxs-lookup"><span data-stu-id="9e01a-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="9e01a-149">Configurez et tenez à jour des stratégies d’enregistrement Teams pour l’organisation.</span><span class="sxs-lookup"><span data-stu-id="9e01a-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="9e01a-150">Surveillez et dépannage des problèmes liés à l’enregistrement des appels et réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="9e01a-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="9e01a-151">Responsable de la conformité interne au niveau de l’analyse opérationnelle de l’utilisation, de la qualité et de la fiabilité.</span><span class="sxs-lookup"><span data-stu-id="9e01a-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e01a-152">Responsable de la conformité</span><span class="sxs-lookup"><span data-stu-id="9e01a-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9e01a-153">Recueillez toutes les communications Teams de la manière requise pour respecter les obligations en matière de conformité dans les limites régionales appropriées.</span><span class="sxs-lookup"><span data-stu-id="9e01a-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="9e01a-154">Recherchez des interactions basées sur des métadonnées ou du contenu d’interaction liés à la communication.</span><span class="sxs-lookup"><span data-stu-id="9e01a-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="9e01a-155">Voici quelques exemples courants :</span><span class="sxs-lookup"><span data-stu-id="9e01a-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="9e01a-156"><strong>Métadonnées</strong> - Participants, heure, itinéraire, numéro composé, numéro de départ, données métiers personnalisées</span><span class="sxs-lookup"><span data-stu-id="9e01a-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="9e01a-157"><strong>Contenu</strong> – Transcription, sentiment, phonétique, interactions connexes</span><span class="sxs-lookup"><span data-stu-id="9e01a-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="9e01a-158">Analyser et interagir avec les communications collectées, notamment la possibilité de surveiller les interactions pendant qu’elles sont collectées.</span><span class="sxs-lookup"><span data-stu-id="9e01a-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="9e01a-159">Assurez la sécurité des communications collectées et empêchez les falsifications à toutes les étapes.</span><span class="sxs-lookup"><span data-stu-id="9e01a-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="9e01a-160">Vue d’ensemble de l’architecture de solution</span><span class="sxs-lookup"><span data-stu-id="9e01a-160">Solution architecture overview</span></span>

<span data-ttu-id="9e01a-161">Les solutions d’enregistrement de conformité sont intégrées à Teams, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="9e01a-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="9e01a-162">![Capture d’écran montrant le paramètre de l’application personnalisée d’équipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Les images illustrent le flux d’envoi et de réception d’une réunion ou d’un appel Teams.")</span><span class="sxs-lookup"><span data-stu-id="9e01a-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="9e01a-163">Enregistreur</span><span class="sxs-lookup"><span data-stu-id="9e01a-163">Recorder</span></span>

<span data-ttu-id="9e01a-164">Le composant principal de la solution d’enregistrement de conformité est l’enregistreur.</span><span class="sxs-lookup"><span data-stu-id="9e01a-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="9e01a-165">Les enregistreurs sont conçus sous la forme de services Azure évolutifs (bots) qui tirent parti de la plateforme de communication de Microsoft et s’inscrivent en tant [<span class="underline">qu’applications</span>](/graph/cloud-communications-concept-overview) auprès de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="9e01a-165">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="9e01a-166">L’enregistreur fournit l’interaction directe avec les appels et les api de [<span class="underline">communication</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) de la plateforme teams et fournit le point de terminaison pour l’ingestion multimédia.</span><span class="sxs-lookup"><span data-stu-id="9e01a-166">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="9e01a-167">Un [<span class="underline">exemple d’application</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) enregistreur de conformité est disponible pour vous aider à configurer le robot, à créer l’instance d’application et à attribuer les stratégies de conformité.</span><span class="sxs-lookup"><span data-stu-id="9e01a-167">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="9e01a-168">L’exemple présente également des exemples d’utilisation d’API pour enregistrer des interactions spécifiques telles que la gestion du [<span class="underline">routage</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) d’appel [<span class="underline">entrant,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)la modification des états d’enregistrement et la suppression de l’utilisateur en [<span class="underline">cours d’enregistrement.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)</span><span class="sxs-lookup"><span data-stu-id="9e01a-168">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="9e01a-169">Vous pouvez trouver de la documentation graphique sur les API spécifiques ici pour [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) et [<span class="underline">incomingContext.</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="9e01a-169">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [<span class="underline">incomingContext</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="9e01a-170">L’implémentation exacte du service d’enregistreur variera selon le partenaire, mais doit être conçue pour prendre en charge plusieurs enregistreurs afin d’obtenir une haute disponibilité et une distribution géographique du déploiement afin de réduire la latence entre Teams et l’enregistreur.</span><span class="sxs-lookup"><span data-stu-id="9e01a-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="9e01a-171">En outre, il est prévu que les enregistreurs eux-mêmes soient conçus avec une résilience et une redondance à l’esprit.</span><span class="sxs-lookup"><span data-stu-id="9e01a-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="9e01a-172">Les partenaires doivent confirmer la version de publication minimale requise des API et des SDK de Communications Microsoft Graph avec Microsoft avant de soumettre leur solution pour certification afin de s’assurer que toutes les exigences d’intégration de l’enregistrement de conformité sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9e01a-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="9e01a-173">Deux conditions spécifiques fondamentales pour le scénario d’enregistrement de conformité sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9e01a-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="9e01a-174">Le robot enregistreur doit être déployé dans Azure</span><span class="sxs-lookup"><span data-stu-id="9e01a-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="9e01a-175">Le robot enregistreur doit s’exécuter sur une VM Windows dans Azure</span><span class="sxs-lookup"><span data-stu-id="9e01a-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="9e01a-176">Les exigences relatives à la gestion des appareils VM Azure et Windows s’appliquent uniquement au composant Teams Bot, ce qui signifie qu’un partenaire peut implémenter le reste de la plateforme de son choix, à condition qu’il réponde aux exigences fonctionnelles et de performances pertinentes pour l’enregistrement de la conformité.</span><span class="sxs-lookup"><span data-stu-id="9e01a-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="9e01a-177">Affectation et mise en service des stratégies d’enregistrement de conformité</span><span class="sxs-lookup"><span data-stu-id="9e01a-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="9e01a-178">Les administrateurs informatiques peuvent déterminer les utilisateurs à enregistrer et l’enregistreur à utiliser pour chaque utilisateur, en créant et en attribuant des stratégies d’enregistrement de conformité.</span><span class="sxs-lookup"><span data-stu-id="9e01a-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="9e01a-179">Les enregistreurs sont invités automatiquement à participer à des conversations en fonction de la configuration de ces stratégies lors d’une interaction de communication.</span><span class="sxs-lookup"><span data-stu-id="9e01a-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="9e01a-180">Les stratégies d’enregistrement de conformité sont gérées à l’aide de [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) et peuvent être appliquées au niveau du client, par utilisateur et du groupe de sécurité pour chaque organisation.</span><span class="sxs-lookup"><span data-stu-id="9e01a-180">Compliance recording policies are managed using [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="9e01a-181">Vous trouverez davantage d’informations [<span class="underline"></span>](./meeting-policies-in-teams.md)sur les [<span class="underline"></span>](./teams-calling-policy.md) stratégies de réunion, les stratégies d’appel et les stratégies de groupe de Microsoft Docs pour [<span class="underline">les réunions.</span>](./assign-policies.md#assign-a-policy-to-a-group)</span><span class="sxs-lookup"><span data-stu-id="9e01a-181">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](./meeting-policies-in-teams.md), [<span class="underline">calling policies</span>](./teams-calling-policy.md) and  [<span class="underline">group policies</span>](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="9e01a-182">Créez une instance d’application dans votre client.</span><span class="sxs-lookup"><span data-stu-id="9e01a-182">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="9e01a-183">Créer une stratégie d’enregistrement de conformité.</span><span class="sxs-lookup"><span data-stu-id="9e01a-183">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span data-ttu-id="9e01a-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="9e01a-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="9e01a-185">Attribuez la stratégie d’enregistrement de conformité à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9e01a-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="9e01a-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="9e01a-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="9e01a-187">Expériences utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e01a-187">User experiences</span></span>

<span data-ttu-id="9e01a-188">La prise en charge des notifications est activée à l’aide de l’expérience client Teams.</span><span class="sxs-lookup"><span data-stu-id="9e01a-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="9e01a-189">Les expériences peuvent être visuelles ou audio.</span><span class="sxs-lookup"><span data-stu-id="9e01a-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="9e01a-190">**Clients Teams - remarque visuelle**</span><span class="sxs-lookup"><span data-stu-id="9e01a-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="9e01a-191">Bureau/Web</span><span class="sxs-lookup"><span data-stu-id="9e01a-191">Desktop/web</span></span>
- <span data-ttu-id="9e01a-192">Mobile (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="9e01a-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="9e01a-193">Téléphones Teams</span><span class="sxs-lookup"><span data-stu-id="9e01a-193">Teams phones</span></span>
- <span data-ttu-id="9e01a-194">Salles Teams</span><span class="sxs-lookup"><span data-stu-id="9e01a-194">Teams rooms</span></span>

<span data-ttu-id="9e01a-195">**Autres points de terminaison - Avis audio**</span><span class="sxs-lookup"><span data-stu-id="9e01a-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="9e01a-196">Téléphones SIP</span><span class="sxs-lookup"><span data-stu-id="9e01a-196">SIP phones</span></span>
- <span data-ttu-id="9e01a-197">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="9e01a-197">Skype for Business</span></span>
- <span data-ttu-id="9e01a-198">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="9e01a-198">Audio conferencing</span></span>
- <span data-ttu-id="9e01a-199">Appelants PSTN</span><span class="sxs-lookup"><span data-stu-id="9e01a-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="9e01a-200">Enregistrement de conformité pour les programmes de certification Teams</span><span class="sxs-lookup"><span data-stu-id="9e01a-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="9e01a-201">En plus de publier des API disponibles publiquement permettant aux partenaires de développer et d’intégrer des solutions CCaaS avec Teams, nous avons développé l’enregistrement de conformité pour le programme de certification de Microsoft Teams afin de fournir aux clients la assurance que la solution de chaque partenaire participant a été testée et vérifiée afin de fournir la qualité, la compatibilité et la fiabilité qu’ils attendent des solutions Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e01a-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="9e01a-202">Les partenaires suivants ont certifié leur solution pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9e01a-202">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="9e01a-203">Partenaire</span><span class="sxs-lookup"><span data-stu-id="9e01a-203">Partner</span></span>|<span data-ttu-id="9e01a-204">Site web de la solution</span><span class="sxs-lookup"><span data-stu-id="9e01a-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="9e01a-205">ASC Technologies</span><span class="sxs-lookup"><span data-stu-id="9e01a-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="9e01a-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="9e01a-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="9e01a-207">Dunker</span><span class="sxs-lookup"><span data-stu-id="9e01a-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="9e01a-208">NICE</span><span class="sxs-lookup"><span data-stu-id="9e01a-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="9e01a-209">Les partenaires suivants sont en train de certifier leur solution pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9e01a-209">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="9e01a-210">Partenaire</span><span class="sxs-lookup"><span data-stu-id="9e01a-210">Partner</span></span>|<span data-ttu-id="9e01a-211">Site web de la solution</span><span class="sxs-lookup"><span data-stu-id="9e01a-211">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="9e01a-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="9e01a-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="9e01a-213">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="9e01a-213">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="9e01a-214">Luware</span><span class="sxs-lookup"><span data-stu-id="9e01a-214">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="9e01a-215">Numonix</span><span class="sxs-lookup"><span data-stu-id="9e01a-215">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="9e01a-216">Innovations dans Le Monde</span><span class="sxs-lookup"><span data-stu-id="9e01a-216">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="9e01a-217">Red Box</span><span class="sxs-lookup"><span data-stu-id="9e01a-217">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="9e01a-218">Verint</span><span class="sxs-lookup"><span data-stu-id="9e01a-218">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="9e01a-219">Cette liste est mise à jour à mesure que de nouveaux partenaires rejoignent et répondent aux critères de certification.</span><span class="sxs-lookup"><span data-stu-id="9e01a-219">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e01a-220">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="9e01a-220">Next steps</span></span>

<span data-ttu-id="9e01a-221">Si vous êtes un fournisseur désireux de participer au programme de certification, veuillez envoyer un <a href= "mailto:Teamscategorypartner@microsoft.com">e-mail Teamscategorypartner@microsoft.com.</a></span><span class="sxs-lookup"><span data-stu-id="9e01a-221">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>