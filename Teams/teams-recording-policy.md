---
title: Présentation des enregistrements basés sur les stratégies d’équipes pour les appels & des réunions
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
description: Apprenez-en davantage sur l’enregistrement basé sur les stratégies d’équipe pour appeler & réunions
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
ms.openlocfilehash: a63aee051467d07a5eef9063538d740b07e6eadf
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584083"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="49bad-103">Présentation des enregistrements basés sur les stratégies d’équipe pour les appels & des réunions</span><span class="sxs-lookup"><span data-stu-id="49bad-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="49bad-104">L’enregistrement basé sur une stratégie permet aux organisations adoptant Microsoft teams d’appeler et de réunions de stipuler, à l’aide d’une stratégie d’administration, si les appels et les réunions en ligne doivent être enregistrés automatiquement et capturés en cas de traitement et de rétention ultérieurs requis par une politique d’entreprise ou de réglementation appropriée.</span><span class="sxs-lookup"><span data-stu-id="49bad-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="49bad-105">Teams a été amélioré pour prendre en charge l’intégration de solutions d’enregistrement tiers, notamment les fonctionnalités de plateforme, les expériences utilisateur et les interfaces d’administration nécessaires pour fournir une solution de bout en bout pour la configuration, la gestion, l’enregistrement, le stockage et l’analyse des communications entre les équipes.</span><span class="sxs-lookup"><span data-stu-id="49bad-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="49bad-106">Cela inclut les API et événements de la plateforme de communication pour l’enregistrement, qui fournit les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="49bad-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="49bad-107">Capture multimédia transparente et de grande qualité sur les appareils et tous les points de terminaison pris en charge pour l’audio, la vidéo, le partage d’écran et la discussion.</span><span class="sxs-lookup"><span data-stu-id="49bad-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="49bad-108">Prise en charge de la capture d’interactions entre les utilisateurs de teams et les points de terminaison d’appel pris en charge (Teams, équipes mobiles, Skype entreprise, RTC)</span><span class="sxs-lookup"><span data-stu-id="49bad-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="49bad-109">Nouvelles politiques d’administration pour l’enregistrement de la conformité, y compris l’intégration aux équipes existantes d’appels administratifs et aux politiques et aux outils de réunion</span><span class="sxs-lookup"><span data-stu-id="49bad-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

- <span data-ttu-id="49bad-110">Nécessite une [licence de communications avancée](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="49bad-110">Requires an [Advanced Communications license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/advanced-communications)</span></span>

<span data-ttu-id="49bad-111">Les fonctionnalités d’intégration de la solution enregistrement de la conformité ont également été examinées lors de l’enflamme 2019 de la [<span class="underline">session enregistrement de la conformité et Microsoft teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="49bad-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="49bad-112">Présentation de l’enregistrement d’interactions dans teams</span><span class="sxs-lookup"><span data-stu-id="49bad-112">Teams interaction recording overview</span></span>

<span data-ttu-id="49bad-113">Les cas d’utilisation de l’enregistrement d’interactions peuvent être divisées en quatre catégories principales de fonctionnalité d’enregistrement (commodité, fonctionnelle, d’organisation et d’interception licite, comme illustré dans l’image :</span><span class="sxs-lookup"><span data-stu-id="49bad-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="49bad-114">![Capture d’écran montrant les interactions enregistrement et pourquoi.](media/recording-taxonomy.png "L’image montre les catégories d’enregistrements.")</span><span class="sxs-lookup"><span data-stu-id="49bad-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="49bad-115">Chacune des catégories implique différentes exigences relatives à la manière dont les enregistrements sont initiés, les enregistrements enregistrés, les enregistrements stockés, les personnes qui contrôlent l’accès et la manière dont la rétention est gérée.</span><span class="sxs-lookup"><span data-stu-id="49bad-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="49bad-116">Avantage</span><span class="sxs-lookup"><span data-stu-id="49bad-116">Convenience</span></span>        | <span data-ttu-id="49bad-117">Fonction</span><span class="sxs-lookup"><span data-stu-id="49bad-117">Functional</span></span>         | <span data-ttu-id="49bad-118">Org-général</span><span class="sxs-lookup"><span data-stu-id="49bad-118">Org - General</span></span>      | <span data-ttu-id="49bad-119">Réglementé par l’Organisation</span><span class="sxs-lookup"><span data-stu-id="49bad-119">Org - Regulated</span></span> | <span data-ttu-id="49bad-120">Interception licite</span><span class="sxs-lookup"><span data-stu-id="49bad-120">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="49bad-121">Initiateur</span><span class="sxs-lookup"><span data-stu-id="49bad-121">Initiator</span></span>              | <span data-ttu-id="49bad-122">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="49bad-122">User</span></span>               | <span data-ttu-id="49bad-123">Application/solution</span><span class="sxs-lookup"><span data-stu-id="49bad-123">App/Solution</span></span>       | <span data-ttu-id="49bad-124">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="49bad-124">Admin (system)</span></span>     | <span data-ttu-id="49bad-125">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="49bad-125">Admin (system)</span></span>  | <span data-ttu-id="49bad-126">LEA</span><span class="sxs-lookup"><span data-stu-id="49bad-126">LEA</span></span>                |
| <span data-ttu-id="49bad-127">Cible</span><span class="sxs-lookup"><span data-stu-id="49bad-127">Target</span></span>                 | <span data-ttu-id="49bad-128">Par appel/réunion</span><span class="sxs-lookup"><span data-stu-id="49bad-128">Per-call / meeting</span></span> | <span data-ttu-id="49bad-129">Par appel/réunion</span><span class="sxs-lookup"><span data-stu-id="49bad-129">Per-call / meeting</span></span> | <span data-ttu-id="49bad-130">Par appel/réunion</span><span class="sxs-lookup"><span data-stu-id="49bad-130">Per-call / meeting</span></span> | <span data-ttu-id="49bad-131">Par utilisateur</span><span class="sxs-lookup"><span data-stu-id="49bad-131">Per-user</span></span>        | <span data-ttu-id="49bad-132">Par point de terminaison/DID</span><span class="sxs-lookup"><span data-stu-id="49bad-132">Per-endpoint / DID</span></span> |
| <span data-ttu-id="49bad-133">Propriétaire de stockage</span><span class="sxs-lookup"><span data-stu-id="49bad-133">Storage owner</span></span>          | <span data-ttu-id="49bad-134">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="49bad-134">User</span></span>               | <span data-ttu-id="49bad-135">Appli</span><span class="sxs-lookup"><span data-stu-id="49bad-135">App</span></span>                | <span data-ttu-id="49bad-136">Administrateur</span><span class="sxs-lookup"><span data-stu-id="49bad-136">Admin</span></span>              | <span data-ttu-id="49bad-137">Conformité</span><span class="sxs-lookup"><span data-stu-id="49bad-137">Compliance</span></span>      | <span data-ttu-id="49bad-138">LEA</span><span class="sxs-lookup"><span data-stu-id="49bad-138">LEA</span></span>                |
| <span data-ttu-id="49bad-139">Notification requise ?</span><span class="sxs-lookup"><span data-stu-id="49bad-139">Notification required?</span></span> | <span data-ttu-id="49bad-140">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-140">Yes</span></span>                | <span data-ttu-id="49bad-141">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-141">Yes</span></span>                | <span data-ttu-id="49bad-142">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-142">Yes</span></span>                | <span data-ttu-id="49bad-143">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-143">Yes</span></span>             | <span data-ttu-id="49bad-144">Non</span><span class="sxs-lookup"><span data-stu-id="49bad-144">No</span></span>                 |
| <span data-ttu-id="49bad-145">Propriétaire de l’accès</span><span class="sxs-lookup"><span data-stu-id="49bad-145">Access Owner</span></span>           | <span data-ttu-id="49bad-146">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="49bad-146">User</span></span>               | <span data-ttu-id="49bad-147">Appli</span><span class="sxs-lookup"><span data-stu-id="49bad-147">App</span></span>                | <span data-ttu-id="49bad-148">Administrateur</span><span class="sxs-lookup"><span data-stu-id="49bad-148">Admin</span></span>              | <span data-ttu-id="49bad-149">Conformité</span><span class="sxs-lookup"><span data-stu-id="49bad-149">Compliance</span></span>      | <span data-ttu-id="49bad-150">LEA</span><span class="sxs-lookup"><span data-stu-id="49bad-150">LEA</span></span>                |
| <span data-ttu-id="49bad-151">Stratégie de rétention</span><span class="sxs-lookup"><span data-stu-id="49bad-151">Retention Policy?</span></span>      | <span data-ttu-id="49bad-152">Facultatif</span><span class="sxs-lookup"><span data-stu-id="49bad-152">Optional</span></span>           | <span data-ttu-id="49bad-153">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-153">Yes</span></span>                | <span data-ttu-id="49bad-154">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-154">Yes</span></span>                | <span data-ttu-id="49bad-155">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-155">Yes</span></span>             | <span data-ttu-id="49bad-156">Oui</span><span class="sxs-lookup"><span data-stu-id="49bad-156">Yes</span></span>                |

<span data-ttu-id="49bad-157">Teams fournit différentes fonctionnalités pour un enregistrement [<span class="underline">pratique</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) et opérationnel pour les réunions et les événements en direct.</span><span class="sxs-lookup"><span data-stu-id="49bad-157">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="49bad-158">L’enregistrement d’organisation implique la possibilité pour les organisations d’adopter des équipes aux fins d’appel et de réunions pour stipuler, par le biais d’une politique d’administration, l’enregistrement et la conservation automatiques des appels et des réunions en ligne conformément aux exigences d’entreprise ou de réglementation pertinentes.</span><span class="sxs-lookup"><span data-stu-id="49bad-158">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="49bad-159">Les utilisateurs qui se trouvent dans le cadre de cette stratégie seront avertis que leurs interactions numériques avec Teams, mais ne seront pas en mesure de désactiver l’enregistrement et ne pourront pas accéder à l’enregistrement une fois que l’interaction se termine.</span><span class="sxs-lookup"><span data-stu-id="49bad-159">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="49bad-160">L’enregistrement fait partie de l’archive d’organisation disponible pour la conformité et le personnel légal pour la découverte électronique, la conservation légale et les autres usages de rétention de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="49bad-160">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="49bad-161">Exemple d’utilisation requise</span><span class="sxs-lookup"><span data-stu-id="49bad-161">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="49bad-162"><strong>Personnage</strong></span><span class="sxs-lookup"><span data-stu-id="49bad-162"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="49bad-163"><strong>Nécessit</strong></span><span class="sxs-lookup"><span data-stu-id="49bad-163"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="49bad-164">Utilisateurs enregistrés</span><span class="sxs-lookup"><span data-stu-id="49bad-164">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="49bad-165">Recevoir une notification lorsque l’enregistrement est en cours.</span><span class="sxs-lookup"><span data-stu-id="49bad-165">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="49bad-166">Soyez informé en cas d’erreur de stratégie et/ou d’enregistreur entraînant des modifications du comportement d’appel.</span><span class="sxs-lookup"><span data-stu-id="49bad-166">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49bad-167">Administration des communications</span><span class="sxs-lookup"><span data-stu-id="49bad-167">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="49bad-168">Comprenez pourquoi et comment appliquer/mettre en œuvre des stratégies d’enregistrement aux utilisateurs/points de terminaison Teams.</span><span class="sxs-lookup"><span data-stu-id="49bad-168">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="49bad-169">Configurer et tenir à jour des stratégies d’enregistrement d’équipes pour l’organisation.</span><span class="sxs-lookup"><span data-stu-id="49bad-169">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="49bad-170">Surveiller et résoudre les problèmes liés à l’enregistrement liés aux conférences et aux appels aux équipes.</span><span class="sxs-lookup"><span data-stu-id="49bad-170">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="49bad-171">Prise en charge de l’officier de conformité interne avec les analyses opérationnelles concernant l’utilisation, la qualité et la fiabilité.</span><span class="sxs-lookup"><span data-stu-id="49bad-171">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49bad-172">Officier de conformité</span><span class="sxs-lookup"><span data-stu-id="49bad-172">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="49bad-173">Rassemblez toutes les communications de l’équipe conformément aux exigences en matière de conformité aux frontières locales appropriées.</span><span class="sxs-lookup"><span data-stu-id="49bad-173">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="49bad-174">Recherchez des interactions basées sur les métadonnées ou le contenu d’interaction liés aux communications.</span><span class="sxs-lookup"><span data-stu-id="49bad-174">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="49bad-175">Voici quelques exemples courants :</span><span class="sxs-lookup"><span data-stu-id="49bad-175">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="49bad-176"><strong>Metadata</strong> - Participants, heure, direction, numéro composé, numéro d’origine, données métiers personnalisées</span><span class="sxs-lookup"><span data-stu-id="49bad-176"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="49bad-177"><strong>Contenu</strong> – transcription, sentiment, phonétique, interactions associées</span><span class="sxs-lookup"><span data-stu-id="49bad-177"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="49bad-178">Analysez et interagissez avec les communications collectées, y compris la possibilité de surveiller les interactions lors de leur collecte.</span><span class="sxs-lookup"><span data-stu-id="49bad-178">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="49bad-179">Assurez la sécurité des communications collectées et empêchez les étapes de falsification.</span><span class="sxs-lookup"><span data-stu-id="49bad-179">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="49bad-180">Vue d’ensemble de l’architecture de solution</span><span class="sxs-lookup"><span data-stu-id="49bad-180">Solution architecture overview</span></span>

<span data-ttu-id="49bad-181">Les solutions d’enregistrement de la conformité sont intégrées aux équipes, comme indiqué dans le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="49bad-181">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="49bad-182">![Capture d’écran montrant le paramètre de l’application personnalisée d’équipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Les images montrent le flux d’envoi et de réception d’une réunion ou d’un appel Teams.")</span><span class="sxs-lookup"><span data-stu-id="49bad-182">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="49bad-183">Magnétoscope</span><span class="sxs-lookup"><span data-stu-id="49bad-183">Recorder</span></span>

<span data-ttu-id="49bad-184">Le composant principal de la solution d’enregistrement de la conformité est l’enregistreur.</span><span class="sxs-lookup"><span data-stu-id="49bad-184">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="49bad-185">Les enregistreurs sont basés sur des services basés sur la fonction Azure (robots) qui [<span class="underline">tirent parti de la plateforme de communication de Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) et sont enregistrés en tant qu’applications avec Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="49bad-185">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="49bad-186">L’enregistreur d’enregistrements fournit une interaction directe avec les API d’appel et de réunion de la [<span class="underline">plateforme de communication</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) et fournit le point de terminaison d’acquisition multimédia.</span><span class="sxs-lookup"><span data-stu-id="49bad-186">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="49bad-187">Un [<span class="underline">exemple d’application d’enregistrement de conformité est disponible</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , qui montre comment configurer le bot, créer l’instance d’application et affecter les stratégies de conformité.</span><span class="sxs-lookup"><span data-stu-id="49bad-187">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="49bad-188">Cet exemple inclut également des exemples d’utilisation d’API pour l’enregistrement d’interactions spécifiques telles que le traitement de l’acheminement des [<span class="underline">appels entrants</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , le [<span class="underline">changement d’état d’enregistrement</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)et [<span class="underline">la suppression de l’utilisateur enregistré</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="49bad-188">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="49bad-189">La documentation Graph sur les API spécifiques est disponible ici pour [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) et [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="49bad-189">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="49bad-190">L’implémentation exacte du service d’enregistreur d’enregistrements varie en fonction du partenaire, mais doit être conçue pour prendre en charge plusieurs enregistreurs afin de garantir une disponibilité élevée et une distribution géographique du déploiement afin de réduire la latence entre teams et l’enregistreur.</span><span class="sxs-lookup"><span data-stu-id="49bad-190">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="49bad-191">De plus, il est probable que les enregistreurs eux-mêmes soient conçus en fonction de la résilience et de la redondance à l’esprit.</span><span class="sxs-lookup"><span data-stu-id="49bad-191">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="49bad-192">Les partenaires doivent confirmer la version minimale requise des API et SDK Microsoft Graph avec Microsoft avant de soumettre leur solution de certification pour s’assurer que toutes les exigences en matière d’intégration de l’enregistrement de la conformité sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="49bad-192">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="49bad-193">Deux exigences spécifiques qui sont fondamentales pour le scénario d’enregistrement de la conformité sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="49bad-193">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="49bad-194">Le robot de magnétoscope doit être déployé dans Azure</span><span class="sxs-lookup"><span data-stu-id="49bad-194">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="49bad-195">Le robot de magnétoscope doit s’exécuter sur un ordinateur virtuel Windows dans Azure</span><span class="sxs-lookup"><span data-stu-id="49bad-195">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="49bad-196">La configuration requise pour Azure et Windows VM s’applique uniquement au composant bot Teams, ce qui signifie qu’un partenaire peut mettre en œuvre le reste de la plate-forme de son choix pour répondre aux exigences de performances et de fonctionnement pertinentes pour l’enregistrement de la conformité.</span><span class="sxs-lookup"><span data-stu-id="49bad-196">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="49bad-197">Attribution de stratégie d’enregistrement de la conformité et approvisionnement</span><span class="sxs-lookup"><span data-stu-id="49bad-197">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="49bad-198">Les administrateurs informatiques peuvent déterminer quels utilisateurs seront enregistrés et quel enregistreur sera utilisé pour chaque utilisateur, en créant et en assignant des stratégies d’enregistrement de la conformité.</span><span class="sxs-lookup"><span data-stu-id="49bad-198">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="49bad-199">Les enregistreurs sont automatiquement invités à participer à des conversations en fonction de la configuration de celles-ci lorsqu’une interaction de communication a lieu.</span><span class="sxs-lookup"><span data-stu-id="49bad-199">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="49bad-200">Les stratégies d’enregistrement de la conformité sont gérées à l’aide de [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) et peuvent être appliquées au niveau du client, de la sécurité et du groupe de sécurité pour chaque organisation.</span><span class="sxs-lookup"><span data-stu-id="49bad-200">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="49bad-201">Vous trouverez des informations supplémentaires sur les stratégies de [<span class="underline">réunion</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), les stratégies d' [<span class="underline">appel</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) et les stratégies de [<span class="underline">groupe</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)dans Microsoft documents.</span><span class="sxs-lookup"><span data-stu-id="49bad-201">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="49bad-202">Créez une instance d’application dans votre client.</span><span class="sxs-lookup"><span data-stu-id="49bad-202">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="49bad-203">Créer une stratégie d’enregistrement de conformité.</span><span class="sxs-lookup"><span data-stu-id="49bad-203">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="49bad-204"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="49bad-204"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="49bad-205">Affectez la stratégie d’enregistrement de conformité à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="49bad-205">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="49bad-206"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="49bad-206"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="49bad-207">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="49bad-207">User experiences</span></span>

<span data-ttu-id="49bad-208">La prise en charge des notifications est activée à l’aide de l’expérience client d’équipes.</span><span class="sxs-lookup"><span data-stu-id="49bad-208">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="49bad-209">Les expériences peuvent être visuelles ou audio.</span><span class="sxs-lookup"><span data-stu-id="49bad-209">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="49bad-210">**Clients teams-avis visuel**</span><span class="sxs-lookup"><span data-stu-id="49bad-210">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="49bad-211">Bureau et Web</span><span class="sxs-lookup"><span data-stu-id="49bad-211">Desktop/web</span></span>
- <span data-ttu-id="49bad-212">Mobile (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="49bad-212">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="49bad-213">Téléphones teams</span><span class="sxs-lookup"><span data-stu-id="49bad-213">Teams phones</span></span>
- <span data-ttu-id="49bad-214">Salles d’équipe</span><span class="sxs-lookup"><span data-stu-id="49bad-214">Teams rooms</span></span>

<span data-ttu-id="49bad-215">**Autres points de terminaison-avis audio**</span><span class="sxs-lookup"><span data-stu-id="49bad-215">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="49bad-216">Téléphones SIP</span><span class="sxs-lookup"><span data-stu-id="49bad-216">SIP phones</span></span>
- <span data-ttu-id="49bad-217">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="49bad-217">Skype for Business</span></span>
- <span data-ttu-id="49bad-218">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="49bad-218">Audio conferencing</span></span>
- <span data-ttu-id="49bad-219">Appelants PSTN</span><span class="sxs-lookup"><span data-stu-id="49bad-219">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="49bad-220">Enregistrement de la conformité pour les programmes de certification d’équipes</span><span class="sxs-lookup"><span data-stu-id="49bad-220">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="49bad-221">Outre la publication d’API disponibles à des fins publiques permettant aux partenaires de développer et d’intégrer des solutions CCaaSes avec Teams, nous avons mis en garde l’enregistrement de la conformité pour le programme de certification de Microsoft Teams, afin de fournir aux clients l’assurance que les solutions de chaque partenaire participant ont été testées et vérifiées pour fournir la qualité, la compatibilité et la fiabilité de leurs solutions</span><span class="sxs-lookup"><span data-stu-id="49bad-221">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="49bad-222">Les partenaires suivants sont en train de certifier leur solution pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49bad-222">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>  

|<span data-ttu-id="49bad-223">Partenaire</span><span class="sxs-lookup"><span data-stu-id="49bad-223">Partner</span></span>|<span data-ttu-id="49bad-224">Site Web de solution</span><span class="sxs-lookup"><span data-stu-id="49bad-224">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="49bad-225">Technologies ASC</span><span class="sxs-lookup"><span data-stu-id="49bad-225">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="49bad-226">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="49bad-226">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="49bad-227">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="49bad-227">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="49bad-228">BELLE</span><span class="sxs-lookup"><span data-stu-id="49bad-228">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="49bad-229">Numonix</span><span class="sxs-lookup"><span data-stu-id="49bad-229">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="49bad-230">Zone rouge</span><span class="sxs-lookup"><span data-stu-id="49bad-230">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="49bad-231">Verint</span><span class="sxs-lookup"><span data-stu-id="49bad-231">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="49bad-232">Cette liste sera mise à jour sous la forme d’autres partenaires et répondez aux critères de certification.</span><span class="sxs-lookup"><span data-stu-id="49bad-232">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="49bad-233">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="49bad-233">Next steps</span></span>

<span data-ttu-id="49bad-234">Si vous êtes un fournisseur qui cherche à rejoindre le programme de certification, envoyez-le à <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="49bad-234">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
