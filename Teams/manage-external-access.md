---
title: Gérer l’accès externe (fédération) dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: karvell
search.appverid: MET150
description: Votre administrateur informatique peut configurer l’accès externe pour d’autres domaines (fédération) permettre aux utilisateurs de ces domaines de participer à des équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56e4171421cc52ec1ca79895aba3c0f259d20201
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2019
ms.locfileid: "29708796"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="d0f49-103">Gérer l’accès externe (fédération) dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0f49-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="d0f49-104">Avec un accès externe Teams Microsoft, les utilisateurs d’autres domaines peuvent participer à vos conversations et les appels.</span><span class="sxs-lookup"><span data-stu-id="d0f49-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="d0f49-105">Vous pouvez également autoriser les utilisateurs externes qui sont toujours à l’aide Skype pour les entreprises à participer.</span><span class="sxs-lookup"><span data-stu-id="d0f49-105">You can also allow external users who are still using Skype for Business to participate.</span></span> 

<span data-ttu-id="d0f49-106">Accès externe (fédération) et l’accès invité sont différentes :</span><span class="sxs-lookup"><span data-stu-id="d0f49-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="d0f49-107">Accès invité donne l’autorisation d’accès à une seule personne.</span><span class="sxs-lookup"><span data-stu-id="d0f49-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="d0f49-108">Accès externe donne l’autorisation d’accès à la totalité d’un domaine.</span><span class="sxs-lookup"><span data-stu-id="d0f49-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="d0f49-109">Accès invité, une fois accordé par le propriétaire de l’équipe, autorise invité à [accéder aux ressources](guest-experience.md), telles que les discussions sur le canal et les fichiers, pour une équipe spécifique et conversation avec d’autres utilisateurs de l’équipe qu’ils ont été invités à.</span><span class="sxs-lookup"><span data-stu-id="d0f49-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="d0f49-110">Avec un accès externe (conversation fédérée), les participants à la conversation externes n’ont accès à des équipes ou des ressources de l’équipe de l’organisation à inviter.</span><span class="sxs-lookup"><span data-stu-id="d0f49-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="d0f49-111">Ils peuvent participer qu’à une conversation fédérée en tête-à-tête.</span><span class="sxs-lookup"><span data-stu-id="d0f49-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="d0f49-112">Administrateurs du client peut choisir entre les options de deux communication selon le niveau de la collaboration est souhaitable avec la partie externe.</span><span class="sxs-lookup"><span data-stu-id="d0f49-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="d0f49-113">Administrateurs peuvent choisir approches ou les deux, en fonction de leurs besoins en matière d’organisation, mais il est recommandé d’activation de l’accès invité pour une expérience d’équipes be, collaboration.</span><span class="sxs-lookup"><span data-stu-id="d0f49-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="d0f49-114">Consultez la table pour une comparaison d’externes et les invités d’accéder aux fonctionnalités suivantes.</span><span class="sxs-lookup"><span data-stu-id="d0f49-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="d0f49-115">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="d0f49-115">Feature</span></span> | <span data-ttu-id="d0f49-116">Utilisateurs de l’accès externe</span><span class="sxs-lookup"><span data-stu-id="d0f49-116">External access users</span></span> | <span data-ttu-id="d0f49-117">Utilisateurs de l’accès invité</span><span class="sxs-lookup"><span data-stu-id="d0f49-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="d0f49-118">Utilisateur peut converser avec une personne dans une autre société</span><span class="sxs-lookup"><span data-stu-id="d0f49-118">User can chat with someone in another company</span></span> | <span data-ttu-id="d0f49-119">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-119">Yes</span></span> |<span data-ttu-id="d0f49-120">Oui </span><span class="sxs-lookup"><span data-stu-id="d0f49-120">Yes</span></span> |
| <span data-ttu-id="d0f49-121">L’utilisateur peut appeler une personne dans une autre société</span><span class="sxs-lookup"><span data-stu-id="d0f49-121">User can call someone in another company</span></span> | <span data-ttu-id="d0f49-122">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-122">Yes</span></span> | <span data-ttu-id="d0f49-123">Oui </span><span class="sxs-lookup"><span data-stu-id="d0f49-123">Yes</span></span> |
| <span data-ttu-id="d0f49-124">Les utilisateurs peuvent afficher si une personne à partir d’une autre société est disponible pour un appel ou une conversation</span><span class="sxs-lookup"><span data-stu-id="d0f49-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="d0f49-125">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-125">Yes</span></span> | <span data-ttu-id="d0f49-126">Oui<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d0f49-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="d0f49-127">Utilisateur peut rechercher des utilisateurs dans les clients externes</span><span class="sxs-lookup"><span data-stu-id="d0f49-127">User can search for users across external tenants</span></span> | <span data-ttu-id="d0f49-128">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d0f49-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="d0f49-129">Non</span><span class="sxs-lookup"><span data-stu-id="d0f49-129">No</span></span> |
| <span data-ttu-id="d0f49-130">Utilisateur peut partager des fichiers</span><span class="sxs-lookup"><span data-stu-id="d0f49-130">User can share files</span></span> | <span data-ttu-id="d0f49-131">Non</span><span class="sxs-lookup"><span data-stu-id="d0f49-131">No</span></span> | <span data-ttu-id="d0f49-132">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-132">Yes</span></span> |
| <span data-ttu-id="d0f49-133">Utilisateur peut accéder aux ressources d’équipes</span><span class="sxs-lookup"><span data-stu-id="d0f49-133">User can access Teams resources</span></span> | <span data-ttu-id="d0f49-134">Non</span><span class="sxs-lookup"><span data-stu-id="d0f49-134">No</span></span> | <span data-ttu-id="d0f49-135">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-135">Yes</span></span> |
| <span data-ttu-id="d0f49-136">Utilisateur peut être ajouté à une conversation de groupe</span><span class="sxs-lookup"><span data-stu-id="d0f49-136">User can be added to a group chat</span></span> | <span data-ttu-id="d0f49-137">Non</span><span class="sxs-lookup"><span data-stu-id="d0f49-137">No</span></span> | <span data-ttu-id="d0f49-138">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-138">Yes</span></span> |
| <span data-ttu-id="d0f49-139">Utilisateur peut être ajouté à une réunion</span><span class="sxs-lookup"><span data-stu-id="d0f49-139">User can be added to a meeting</span></span> | <span data-ttu-id="d0f49-140">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-140">Yes</span></span> | <span data-ttu-id="d0f49-141">Oui </span><span class="sxs-lookup"><span data-stu-id="d0f49-141">Yes</span></span> |
| <span data-ttu-id="d0f49-142">Utilisateurs supplémentaires peuvent être ajoutés à une conversation avec un utilisateur externe</span><span class="sxs-lookup"><span data-stu-id="d0f49-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="d0f49-143">Aucun<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0f49-143">No<sup>3</sup></span></span> | <span data-ttu-id="d0f49-144">N/A</span><span class="sxs-lookup"><span data-stu-id="d0f49-144">N/A</span></span> |
| <span data-ttu-id="d0f49-145">Utilisateur est identifié comme une partie externe</span><span class="sxs-lookup"><span data-stu-id="d0f49-145">User is identified as an external party</span></span> | <span data-ttu-id="d0f49-146">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-146">Yes</span></span> | <span data-ttu-id="d0f49-147">Oui </span><span class="sxs-lookup"><span data-stu-id="d0f49-147">Yes</span></span> |
| <span data-ttu-id="d0f49-148">Affichage de la présence</span><span class="sxs-lookup"><span data-stu-id="d0f49-148">Presence is displayed</span></span> | <span data-ttu-id="d0f49-149">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-149">Yes</span></span> | <span data-ttu-id="d0f49-150">Oui </span><span class="sxs-lookup"><span data-stu-id="d0f49-150">Yes</span></span> |
| <span data-ttu-id="d0f49-151">Absent message s’affiche.</span><span class="sxs-lookup"><span data-stu-id="d0f49-151">Out of office message is shown</span></span> | <span data-ttu-id="d0f49-152">Non</span><span class="sxs-lookup"><span data-stu-id="d0f49-152">No</span></span> | <span data-ttu-id="d0f49-153">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-153">Yes</span></span> |
| <span data-ttu-id="d0f49-154">Les utilisateurs individuels peuvent être bloquées.</span><span class="sxs-lookup"><span data-stu-id="d0f49-154">Individual user can be blocked</span></span> | <span data-ttu-id="d0f49-155">Non</span><span class="sxs-lookup"><span data-stu-id="d0f49-155">No</span></span> | <span data-ttu-id="d0f49-156">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-156">Yes</span></span> |
| <span data-ttu-id="d0f49-157">@mentions sont pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0f49-157">@mentions are supported</span></span> | <span data-ttu-id="d0f49-158">Non</span><span class="sxs-lookup"><span data-stu-id="d0f49-158">No</span></span> | <span data-ttu-id="d0f49-159">Oui</span><span class="sxs-lookup"><span data-stu-id="d0f49-159">Yes</span></span> |
||||

<span data-ttu-id="d0f49-160"><sup>1</sup> à condition que l’utilisateur a été ajouté en tant qu’invité et est connecté en tant qu’invité au client d’invité.</span><span class="sxs-lookup"><span data-stu-id="d0f49-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="d0f49-161"><sup>2</sup> uniquement par courrier électronique ou l’adresse de protocole SIP (Session Initiation).</span><span class="sxs-lookup"><span data-stu-id="d0f49-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="d0f49-162"><sup>3</sup> conversation (fédérée) externe est 1:1.</span><span class="sxs-lookup"><span data-stu-id="d0f49-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access"></a><span data-ttu-id="d0f49-163">Activer ou désactiver l’accès externe</span><span class="sxs-lookup"><span data-stu-id="d0f49-163">Turn on or turn off external access</span></span>

<span data-ttu-id="d0f49-164">Vous pouvez utiliser la & Microsoft Teams Skype entreprise centre d’administration pour gérer l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="d0f49-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="d0f49-165">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **l’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="d0f49-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Capture d’écran de l’accès externe de paramètres à l’échelle de l’organisation](media/manage-external-access-1.png)<span data-ttu-id="d0f49-167">.</span><span class="sxs-lookup"><span data-stu-id="d0f49-167"></span></span>

2. <span data-ttu-id="d0f49-168">Activer \*\*ou \*\*désactiver\*\*\*\* l’utilisation de **l’accès externe** .</span><span class="sxs-lookup"><span data-stu-id="d0f49-168">Toggle the **External access** switch to **On** or **Off**.</span></span>

     ![Capture d’écran de l’option d’accès externe est activée](media/manage-external-access-2.png)<span data-ttu-id="d0f49-170">.</span><span class="sxs-lookup"><span data-stu-id="d0f49-170"></span></span>

3. <span data-ttu-id="d0f49-171">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d0f49-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="d0f49-172">Ajouter ou bloquer un domaine</span><span class="sxs-lookup"><span data-stu-id="d0f49-172">Add or block a domain</span></span>

<span data-ttu-id="d0f49-173">Suivez ces étapes pour ajouter un domaine ou de désactiver l’accès externe pour un domaine.</span><span class="sxs-lookup"><span data-stu-id="d0f49-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="d0f49-174">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **l’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="d0f49-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="d0f49-175">Sélectionnez **Ajouter un domaine**.</span><span class="sxs-lookup"><span data-stu-id="d0f49-175">Select **Add a domain**.</span></span> 
 
    ![Capture d’écran externe page d’accès aux ajouter un lien de domaine](media/manage-external-access-3.png)<span data-ttu-id="d0f49-177">.</span><span class="sxs-lookup"><span data-stu-id="d0f49-177"></span></span>

   <span data-ttu-id="d0f49-178">Le volet **Ajouter un domaine** apparaît.</span><span class="sxs-lookup"><span data-stu-id="d0f49-178">The **Add a domain** pane appears.</span></span>

    ![Capture d’écran d’ajouter un volet de domaine](media/manage-external-access-4.png)<span data-ttu-id="d0f49-180">.</span><span class="sxs-lookup"><span data-stu-id="d0f49-180"></span></span>


3. <span data-ttu-id="d0f49-181">Sous **Ajouter un domaine**, tapez le nom du domaine ; par exemple, tapez Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0f49-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="d0f49-182">Sélectionnez **autorisées** ou **bloquées**.</span><span class="sxs-lookup"><span data-stu-id="d0f49-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="d0f49-183">Vous pouvez modifier ce paramètre à tout moment.</span><span class="sxs-lookup"><span data-stu-id="d0f49-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="d0f49-184">Cliquez sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="d0f49-184">Select **Done**.</span></span>

<span data-ttu-id="d0f49-185">Après avoir ajouté un domaine, vous verrez le nom de domaine et l’état ajouté à la liste des domaines dans la page d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="d0f49-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="d0f49-186">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="d0f49-186">More information</span></span>

<span data-ttu-id="d0f49-187">Pour plus d’informations sur l’accès invité dans Microsoft Teams, voir [Gérer les accès invité dans les équipes Microsoft](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="d0f49-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>