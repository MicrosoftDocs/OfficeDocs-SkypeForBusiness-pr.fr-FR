---
title: Numéro de téléphone non attribué
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690389"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="461aa-104">Numéro de téléphone non attribué</span><span class="sxs-lookup"><span data-stu-id="461aa-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="461aa-105">La messagerie unifiée Exchange reste disponible dans Skype entreprise Server 2019 lorsque vous intégrez Skype entreprise 2019 avec Exchange 2013 ou Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="461aa-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="461aa-106">En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est mise en évidence dans les fonctionnalités de messagerie vocale et de standard automatique Cloud.</span><span class="sxs-lookup"><span data-stu-id="461aa-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="461aa-p103">Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="461aa-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="461aa-p104">La manière dont vous configurez la table des numéros non attribués dépend de l’utilisation envisagée. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéro. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle n’est appelée que lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.</span><span class="sxs-lookup"><span data-stu-id="461aa-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="461aa-115">Avant de configurer la table des numéros non attribués, vous devez avoir défini une ou plusieurs annonces ou configuré un standard automatique de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="461aa-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="461aa-116">La page **Numéro non attribué** affiche la liste des plages de numéros non attribués définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="461aa-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="461aa-117">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="461aa-117">Tasks you can perform</span></span>

<span data-ttu-id="461aa-118">Dans la page **Numéro non attribué**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="461aa-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="461aa-119">Création d’une plage de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="461aa-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="461aa-120">Modification d’une plage de numéros non attribués existante</span><span class="sxs-lookup"><span data-stu-id="461aa-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="461aa-121">Suppression d’une plage de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="461aa-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="461aa-122">Modification de l’ordre des plages de numéros non attribués pour déterminer la première action à appliquer à un appel entrant correspondant à un numéro non attribué.</span><span class="sxs-lookup"><span data-stu-id="461aa-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="461aa-123">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="461aa-123">UI Reference</span></span>

<span data-ttu-id="461aa-124">La liste ci-dessous décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="461aa-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="461aa-125">**Nouvelle** Commence une nouvelle plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="461aa-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="461aa-126">**Modifier** Ouvre la plage de numéros non attribués sélectionnée pour modification, sélectionne toutes les plages de nombres non attribués dans la liste, ou supprime la plage de numéros non attribués sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="461aa-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="461aa-127">**Monter** Déplace la plage de numéros non attribués sélectionnés vers le haut dans la liste de telle sorte que Skype entreprise Server le trouve plus tôt et applique l’action spécifiée avant d’appliquer des actions spécifiées pour d’autres plages dans la liste.</span><span class="sxs-lookup"><span data-stu-id="461aa-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="461aa-128">Skype entreprise Server effectue une recherche dans la table des numéros non attribués de haut en bas, et utilise la première plage qui correspond au numéro non attribué.</span><span class="sxs-lookup"><span data-stu-id="461aa-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="461aa-129">Par exemple, si une plage spécifie une action de dernier recours, assurez-vous qu’elle se trouve en bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="461aa-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="461aa-130">**Descendre** Déplace la plage de nombres non affectées sélectionnée de la liste vers le bas.</span><span class="sxs-lookup"><span data-stu-id="461aa-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="461aa-131">**Valider tout** Enregistre toutes les modifications que vous avez apportées aux plages de nombres non affectées.</span><span class="sxs-lookup"><span data-stu-id="461aa-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="461aa-132">Cette commande enregistre toutes les modifications apportées dans la page **Nouveau numéro non attribué** et dans la page **Modifier le numéro non attribué**.</span><span class="sxs-lookup"><span data-stu-id="461aa-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="461aa-133">**Actualiser** Actualise la liste des plages de nombres non affectées.</span><span class="sxs-lookup"><span data-stu-id="461aa-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="461aa-134">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="461aa-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="461aa-135">**Nom** Nom unique identifiant la plage de nombres non attribués.</span><span class="sxs-lookup"><span data-stu-id="461aa-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="461aa-136">**État** Indique les plages de nombres qui ont été enregistrées dans la base de données et celles qui ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="461aa-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="461aa-137">**Plage de début** Le numéro de début de la plage de nombres non attribués.</span><span class="sxs-lookup"><span data-stu-id="461aa-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="461aa-138">**Plage de fin** Le numéro de fin de la plage de nombres non attribués.</span><span class="sxs-lookup"><span data-stu-id="461aa-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="461aa-139">**Destination (destination** ) ID de service du service d’application qui héberge l’application d’annonce qui traitera les appels entrants de cette plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="461aa-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="461aa-140">**Annonce** Annonce qui sera lue pour cette série de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="461aa-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="461aa-141">Pour plus d’informations sur les fonctionnalités et les fonctionnalités d’annonce, voir [planifier l’application d’annonce dans Skype entreprise](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="461aa-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="461aa-142">Pour plus d’informations sur l’utilisation de plages de numéros non attribués, reportez-vous à la rubrique [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="461aa-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


