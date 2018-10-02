---
title: Gérer les stratégies d’événements en direct dans les équipes
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.liveevents.policies
description: Découvrez les stratégies d’événements en direct équipes et comment les utiliser pour gérer les paramètres pour les utilisateurs de votre organisation qui détiennent les événements en direct.
ms.openlocfilehash: b02f8de8accd0baff5f87af8682eab486866acb5
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354347"
---
# <a name="manage-live-events-policies-in-teams"></a><span data-ttu-id="c86cf-103">Gérer les stratégies d’événements en direct dans les équipes</span><span class="sxs-lookup"><span data-stu-id="c86cf-103">Manage live events policies in Teams</span></span>

<span data-ttu-id="c86cf-104">Stratégies d’événements en direct équipes permettent de contrôler les personnes de votre organisation peuvent contenir des événements en direct et les fonctionnalités qui sont disponibles dans les événements qu’ils créent.</span><span class="sxs-lookup"><span data-stu-id="c86cf-104">Teams live events policies are used to control who in your organization can hold live events and the features that are available in the events that they create.</span></span> <span data-ttu-id="c86cf-105">Après avoir créé une stratégie, l’affecter à un utilisateur ou groupes d’utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c86cf-105">After you create a policy, assign it to a user or groups of users in your organization.</span></span> 

- <span data-ttu-id="c86cf-106">**Nom** Il s’agit du nom de la stratégie qui s’affiche dans la page de stratégies d’événements en direct.</span><span class="sxs-lookup"><span data-stu-id="c86cf-106">**Name** This is the name of the policy that appears on the live events policies page.</span></span> <span data-ttu-id="c86cf-107">Il ne peut pas dépasser 64 caractères ou contient des caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="c86cf-107">It can't be longer than 64 characters or have any special characters.</span></span>  
- <span data-ttu-id="c86cf-108">**Description** Permet d’ajouter une description conviviale de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="c86cf-108">**Description** Use this to add a friendly description for the policy.</span></span> 
- <span data-ttu-id="c86cf-109">**Autoriser la planification** Activer cette fonctionnalité permet aux utilisateurs de votre organisation de créer et de planifier des événements en temps réel dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="c86cf-109">**Allow scheduling** Turning this on lets users in your organization create and schedule live events in Teams.</span></span>  
- <span data-ttu-id="c86cf-110">**Transcription autoriser des participants** Participants direct des légendes en temps réel et une traduction pendant l’événement permet d’activer cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="c86cf-110">**Allow transcription for attendees** Turning this on enables live event attendees to see real-time captions and translation during the event.</span></span> 
- <span data-ttu-id="c86cf-111">**Qui peut participer à des événements live planifiés**</span><span class="sxs-lookup"><span data-stu-id="c86cf-111">**Who can join scheduled live events**</span></span>
    - <span data-ttu-id="c86cf-112">**Tout le monde** Les utilisateurs peuvent créer des événements en direct tout le monde, y compris les personnes extérieures à votre organisation, peut participer.</span><span class="sxs-lookup"><span data-stu-id="c86cf-112">**Everyone** Users can create live events that everyone, including people outside your organization, can attend.</span></span>  
    - <span data-ttu-id="c86cf-113">**Tout le monde dans l’organisation** Les utilisateurs peuvent créer des événements en direct que seules les personnes de votre organisation peuvent participer.</span><span class="sxs-lookup"><span data-stu-id="c86cf-113">**Everyone in the organization** Users can create live events that only people in your organization can attend.</span></span> 
    - <span data-ttu-id="c86cf-114">**Utilisateurs ou groupes spécifiques** Les utilisateurs peuvent créer des événements en direct que seuls des utilisateurs spécifiques ou peuvent participer à des groupes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c86cf-114">**Specific users or groups** Users can create live events that only specific users or groups in your organization can attend.</span></span> 
- <span data-ttu-id="c86cf-115">**Paramètres d’enregistrement** Ce paramètre peut être appliqué uniquement pour les événements qui se sont produites à l’aide de réunions d’équipes, également connu sous les événements en direct de démarrage rapide en direct.</span><span class="sxs-lookup"><span data-stu-id="c86cf-115">**Recording setting** This setting can only be applied to live events that are produced using Teams meetings, also known as quick start live events.</span></span>  
    - <span data-ttu-id="c86cf-116">**Toujours enregistrer** Les événements live créés par les utilisateurs sont toujours enregistrées.</span><span class="sxs-lookup"><span data-stu-id="c86cf-116">**Always record** The live events created by users are always recorded.</span></span> <span data-ttu-id="c86cf-117">Après l’événement, membres de l’équipe événement peuvent télécharger l’enregistrement et les participants peuvent suivre l’événement.</span><span class="sxs-lookup"><span data-stu-id="c86cf-117">After the event is over, event team members can download the recording and attendees can watch the event.</span></span> 
    - <span data-ttu-id="c86cf-118">**Ne jamais faire enregistrer** Les événements live créés par les utilisateurs ne sont jamais enregistrées.</span><span class="sxs-lookup"><span data-stu-id="c86cf-118">**Never record** The live events created by users are never recorded.</span></span>
    - <span data-ttu-id="c86cf-119">**Organisateur peut enregistrer ou non** Les utilisateurs peuvent décider s’il faut enregistrer l’événement live.</span><span class="sxs-lookup"><span data-stu-id="c86cf-119">**Organizer can record or not** Users can decide whether to record the live event.</span></span> <span data-ttu-id="c86cf-120">S’il est enregistré, après l’événement, membres de l’équipe événement peuvent télécharger l’enregistrement et les participants peuvent suivre l’événement.</span><span class="sxs-lookup"><span data-stu-id="c86cf-120">If it is recorded, after the event is over, event team members can download the recording and attendees can watch the event.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="c86cf-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c86cf-121">Related topics</span></span>
- [<span data-ttu-id="c86cf-122">Quelles sont les équipes live événements ?</span><span class="sxs-lookup"><span data-stu-id="c86cf-122">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="c86cf-123">Planifier des équipes événements en direct</span><span class="sxs-lookup"><span data-stu-id="c86cf-123">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="c86cf-124">Configurer des équipes événements en direct</span><span class="sxs-lookup"><span data-stu-id="c86cf-124">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="c86cf-125">Configurer des événements en direct équipes</span><span class="sxs-lookup"><span data-stu-id="c86cf-125">Configure Teams live events</span></span>](configure-teams-live-events.md)
