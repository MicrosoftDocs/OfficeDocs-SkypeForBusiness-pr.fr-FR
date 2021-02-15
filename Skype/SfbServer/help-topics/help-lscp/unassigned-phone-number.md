---
title: Numéro de téléphone non attribué
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826884"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="637c9-104">Numéro de téléphone non attribué</span><span class="sxs-lookup"><span data-stu-id="637c9-104">Unassigned Phone Number</span></span>

<span data-ttu-id="637c9-p102">Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="637c9-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="637c9-p103">La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Vous pouvez configurer la table avec tous les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.</span><span class="sxs-lookup"><span data-stu-id="637c9-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="637c9-113">Avant de configurer la table des numéros non attribués, vous devez avoir défini une ou plusieurs annonces ou configuré un standard automatique de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="637c9-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="637c9-114">La page **Numéro non attribué** affiche la liste des plages de numéros non attribués définies pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="637c9-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="637c9-115">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="637c9-115">Tasks you can perform</span></span>

<span data-ttu-id="637c9-116">Vous pouvez effectuer les tâches suivantes dans la page **Numéro non attribué** :</span><span class="sxs-lookup"><span data-stu-id="637c9-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="637c9-117">Créer une nouvelle plage de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="637c9-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="637c9-118">Modifier une plage de numéros non attribués existante</span><span class="sxs-lookup"><span data-stu-id="637c9-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="637c9-119">Supprimer une plage de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="637c9-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="637c9-120">Modifier l’ordre des plages de numéros non attribués pour déterminer la première action qui doit être appliquée à un appel entrant correspondant à un numéro non attribué.</span><span class="sxs-lookup"><span data-stu-id="637c9-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="637c9-121">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="637c9-121">UI Reference</span></span>

<span data-ttu-id="637c9-122">La liste suivante décrit les commandes de la page.</span><span class="sxs-lookup"><span data-stu-id="637c9-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="637c9-123">**Nouveau** Démarre une nouvelle plage de numéro non assignés.</span><span class="sxs-lookup"><span data-stu-id="637c9-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="637c9-124">**Modifier** Ouvre la plage de numéro non assignées sélectionnée pour modification, sélectionne toutes les plages de numéro non assignées dans la liste ou supprime la plage de numéro non assignées sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="637c9-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="637c9-125">**Monter** Déplace la plage de numéros non signés sélectionnée vers le haut dans la liste afin que Skype Entreprise Server la trouve plus tôt et applique l’action spécifiée avant d’appliquer les actions spécifiées pour les autres plages de la liste.</span><span class="sxs-lookup"><span data-stu-id="637c9-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="637c9-126">Skype Entreprise Server recherche la table des numéros non assignés de haut en bas et utilise la première plage qui correspond au numéro non assigné.</span><span class="sxs-lookup"><span data-stu-id="637c9-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="637c9-127">Par exemple, si une plage spécifie une action de dernier recours, assurez-vous qu’elle se trouve en bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="637c9-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="637c9-128">**Déplacer vers le bas** Déplace la plage de numéro non assignés sélectionnée vers le bas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="637c9-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="637c9-129">**Valider tout** Enregistre toutes les modifications que vous avez apportées aux plages de numéro non assignés.</span><span class="sxs-lookup"><span data-stu-id="637c9-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="637c9-130">Cette commande enregistre toutes les modifications que vous avez effectuées dans la page **Nouveau numéro non attribué** et dans la page **Modifier le numéro non attribué**.</span><span class="sxs-lookup"><span data-stu-id="637c9-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="637c9-131">**Actualiser** Actualise la liste des plages de nombres non résignés.</span><span class="sxs-lookup"><span data-stu-id="637c9-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="637c9-132">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="637c9-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="637c9-133">**Nom** Nom unique qui identifie la plage de numéro non assignés.</span><span class="sxs-lookup"><span data-stu-id="637c9-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="637c9-134">**État** Indique les plages de nombres qui ont été enregistrées dans la base de données et qui n’ont pas été enregistrées.</span><span class="sxs-lookup"><span data-stu-id="637c9-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="637c9-135">**Plage de début** Numéro de début de la plage de numéro non signés.</span><span class="sxs-lookup"><span data-stu-id="637c9-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="637c9-136">**Plage de fin** Numéro de fin de la plage de numéro non assignés.</span><span class="sxs-lookup"><span data-stu-id="637c9-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="637c9-137">**Destination** ID de service du service d’application qui héberge l’application d’annonce qui gérera les appels entrants vers cette plage de numéros non assignés.</span><span class="sxs-lookup"><span data-stu-id="637c9-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="637c9-138">**Annonce** Annonce à lire pour cette plage de numéros non signés.</span><span class="sxs-lookup"><span data-stu-id="637c9-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="637c9-139">Pour plus d’informations sur les fonctionnalités d’annonce, voir [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="637c9-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="637c9-140">Pour plus d’informations sur l’utilisation de plages de numéros non attribués, voir [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="637c9-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


