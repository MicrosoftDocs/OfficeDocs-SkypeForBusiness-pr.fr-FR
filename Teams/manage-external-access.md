---
title: Gérez l’accès externe (fédération) dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Votre administrateur informatique peut configurer l’accès externe pour d’autres domaines (fédération) permettre aux utilisateurs de ces domaines de participer à des équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b04b125f5cb998c71f161bf31809a39097accf6c
ms.sourcegitcommit: 188c57e6b6c707edb694bb922556dea1c4724846
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955021"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="a557f-103">Gérez l’accès externe (fédération) dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a557f-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="a557f-104">Avec un accès externe Teams Microsoft, les utilisateurs d’autres domaines peuvent participer à vos conversations et les appels.</span><span class="sxs-lookup"><span data-stu-id="a557f-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="a557f-105">Vous pouvez également autoriser les utilisateurs externes qui sont toujours à l’aide Skype pour les entreprises à participer.</span><span class="sxs-lookup"><span data-stu-id="a557f-105">You can also allow external users who are still using Skype for Business to participate.</span></span> 

<span data-ttu-id="a557f-106">Accès externe (fédération) et l’accès invité sont différentes :</span><span class="sxs-lookup"><span data-stu-id="a557f-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="a557f-107">Accès invité donne l’autorisation d’accès à une seule personne.</span><span class="sxs-lookup"><span data-stu-id="a557f-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="a557f-108">Accès externe donne l’autorisation d’accès à la totalité d’un domaine.</span><span class="sxs-lookup"><span data-stu-id="a557f-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="a557f-109">Accès invité, une fois accordé par le propriétaire de l’équipe, autorise invité à [accéder aux ressources](guest-experience.md), telles que les discussions sur le canal et les fichiers, pour une équipe spécifique et conversation avec d’autres utilisateurs de l’équipe qu’ils ont été invités à.</span><span class="sxs-lookup"><span data-stu-id="a557f-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="a557f-110">Avec un accès externe (conversation fédérée), les participants à la conversation externes n’ont accès à des équipes ou des ressources de l’équipe de l’organisation à inviter.</span><span class="sxs-lookup"><span data-stu-id="a557f-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="a557f-111">Ils peuvent participer qu’à une conversation fédérée en tête-à-tête.</span><span class="sxs-lookup"><span data-stu-id="a557f-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="a557f-112">Administrateurs du client peut choisir entre les options de deux communication selon le niveau de la collaboration est souhaitable avec la partie externe.</span><span class="sxs-lookup"><span data-stu-id="a557f-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="a557f-113">Administrateurs peuvent choisir approches ou les deux, en fonction de leurs besoins en matière d’organisation, mais il est recommandé d’activation de l’accès invité pour une expérience d’équipes be, collaboration.</span><span class="sxs-lookup"><span data-stu-id="a557f-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="a557f-114">Consultez la table pour une comparaison d’externes et les invités d’accéder aux fonctionnalités suivantes.</span><span class="sxs-lookup"><span data-stu-id="a557f-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="a557f-115">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="a557f-115">Feature</span></span> | <span data-ttu-id="a557f-116">Utilisateurs de l’accès externe</span><span class="sxs-lookup"><span data-stu-id="a557f-116">External access users</span></span> | <span data-ttu-id="a557f-117">Utilisateurs de l’accès invité</span><span class="sxs-lookup"><span data-stu-id="a557f-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="a557f-118">Utilisateur peut converser avec une personne dans une autre société</span><span class="sxs-lookup"><span data-stu-id="a557f-118">User can chat with someone in another company</span></span> | <span data-ttu-id="a557f-119">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-119">Yes</span></span> |<span data-ttu-id="a557f-120">Oui </span><span class="sxs-lookup"><span data-stu-id="a557f-120">Yes</span></span> |
| <span data-ttu-id="a557f-121">L’utilisateur peut appeler une personne dans une autre société</span><span class="sxs-lookup"><span data-stu-id="a557f-121">User can call someone in another company</span></span> | <span data-ttu-id="a557f-122">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-122">Yes</span></span> | <span data-ttu-id="a557f-123">Oui </span><span class="sxs-lookup"><span data-stu-id="a557f-123">Yes</span></span> |
| <span data-ttu-id="a557f-124">Les utilisateurs peuvent afficher si une personne à partir d’une autre société est disponible pour un appel ou une conversation</span><span class="sxs-lookup"><span data-stu-id="a557f-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="a557f-125">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-125">Yes</span></span> | <span data-ttu-id="a557f-126">Oui<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a557f-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="a557f-127">Utilisateur peut rechercher des utilisateurs dans les clients externes</span><span class="sxs-lookup"><span data-stu-id="a557f-127">User can search for users across external tenants</span></span> | <span data-ttu-id="a557f-128">Oui<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a557f-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="a557f-129">Non</span><span class="sxs-lookup"><span data-stu-id="a557f-129">No</span></span> |
| <span data-ttu-id="a557f-130">Utilisateur peut partager des fichiers</span><span class="sxs-lookup"><span data-stu-id="a557f-130">User can share files</span></span> | <span data-ttu-id="a557f-131">Non</span><span class="sxs-lookup"><span data-stu-id="a557f-131">No</span></span> | <span data-ttu-id="a557f-132">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-132">Yes</span></span> |
| <span data-ttu-id="a557f-133">Utilisateur peut accéder aux ressources d’équipes</span><span class="sxs-lookup"><span data-stu-id="a557f-133">User can access Teams resources</span></span> | <span data-ttu-id="a557f-134">Non</span><span class="sxs-lookup"><span data-stu-id="a557f-134">No</span></span> | <span data-ttu-id="a557f-135">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-135">Yes</span></span> |
| <span data-ttu-id="a557f-136">Utilisateur peut être ajouté à une conversation de groupe</span><span class="sxs-lookup"><span data-stu-id="a557f-136">User can be added to a group chat</span></span> | <span data-ttu-id="a557f-137">Non</span><span class="sxs-lookup"><span data-stu-id="a557f-137">No</span></span> | <span data-ttu-id="a557f-138">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-138">Yes</span></span> |
| <span data-ttu-id="a557f-139">Utilisateur peut être ajouté à une réunion</span><span class="sxs-lookup"><span data-stu-id="a557f-139">User can be added to a meeting</span></span> | <span data-ttu-id="a557f-140">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-140">Yes</span></span> | <span data-ttu-id="a557f-141">Oui </span><span class="sxs-lookup"><span data-stu-id="a557f-141">Yes</span></span> |
| <span data-ttu-id="a557f-142">Utilisateurs supplémentaires peuvent être ajoutés à une conversation avec un utilisateur externe</span><span class="sxs-lookup"><span data-stu-id="a557f-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="a557f-143">Aucun<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a557f-143">No<sup>3</sup></span></span> | <span data-ttu-id="a557f-144">N/A</span><span class="sxs-lookup"><span data-stu-id="a557f-144">N/A</span></span> |
| <span data-ttu-id="a557f-145">Utilisateur est identifié comme une partie externe</span><span class="sxs-lookup"><span data-stu-id="a557f-145">User is identified as an external party</span></span> | <span data-ttu-id="a557f-146">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-146">Yes</span></span> | <span data-ttu-id="a557f-147">Oui </span><span class="sxs-lookup"><span data-stu-id="a557f-147">Yes</span></span> |
| <span data-ttu-id="a557f-148">Affichage de la présence</span><span class="sxs-lookup"><span data-stu-id="a557f-148">Presence is displayed</span></span> | <span data-ttu-id="a557f-149">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-149">Yes</span></span> | <span data-ttu-id="a557f-150">Oui </span><span class="sxs-lookup"><span data-stu-id="a557f-150">Yes</span></span> |
| <span data-ttu-id="a557f-151">Absent message s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a557f-151">Out of office message is shown</span></span> | <span data-ttu-id="a557f-152">Non</span><span class="sxs-lookup"><span data-stu-id="a557f-152">No</span></span> | <span data-ttu-id="a557f-153">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-153">Yes</span></span> |
| <span data-ttu-id="a557f-154">Les utilisateurs individuels peuvent être bloquées.</span><span class="sxs-lookup"><span data-stu-id="a557f-154">Individual user can be blocked</span></span> | <span data-ttu-id="a557f-155">Non</span><span class="sxs-lookup"><span data-stu-id="a557f-155">No</span></span> | <span data-ttu-id="a557f-156">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-156">Yes</span></span> |
| <span data-ttu-id="a557f-157">@mentions sont pris en charge</span><span class="sxs-lookup"><span data-stu-id="a557f-157">@mentions are supported</span></span> | <span data-ttu-id="a557f-158">Non</span><span class="sxs-lookup"><span data-stu-id="a557f-158">No</span></span> | <span data-ttu-id="a557f-159">Oui</span><span class="sxs-lookup"><span data-stu-id="a557f-159">Yes</span></span> |
||||

<span data-ttu-id="a557f-160"><sup>1</sup> à condition que l’utilisateur a été ajouté en tant qu’invité et est connecté en tant qu’invité au client d’invité.</span><span class="sxs-lookup"><span data-stu-id="a557f-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="a557f-161"><sup>2</sup> uniquement par courrier électronique ou l’adresse de protocole SIP (Session Initiation).</span><span class="sxs-lookup"><span data-stu-id="a557f-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="a557f-162"><sup>3</sup> conversation (fédérée) externe est 1:1.</span><span class="sxs-lookup"><span data-stu-id="a557f-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="a557f-163">Activer ou désactiver l’accès externe (les utilisateurs peuvent communiquer avec Skype pour les utilisateurs professionnels et les équipes)</span><span class="sxs-lookup"><span data-stu-id="a557f-163">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="a557f-164">Vous pouvez utiliser la & Microsoft Teams Skype entreprise centre d’administration pour gérer l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="a557f-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="a557f-165">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **l’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="a557f-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Capture d’écran de l’accès externe de paramètres à l’échelle de l’organisation](media/manage-external-access-1.png)<span data-ttu-id="a557f-167">.</span><span class="sxs-lookup"><span data-stu-id="a557f-167"></span></span>

2. <span data-ttu-id="a557f-168">Basculez **les utilisateurs peuvent communiquer avec Skype pour les utilisateurs professionnels et les équipes** **activé** ou **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="a557f-168">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![Capture d’écran de l’option d’accès externe est activée](media/manage-external-access-2.png)<span data-ttu-id="a557f-170">.</span><span class="sxs-lookup"><span data-stu-id="a557f-170"></span></span>

3. <span data-ttu-id="a557f-171">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a557f-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="a557f-172">Ajouter ou bloquer un domaine</span><span class="sxs-lookup"><span data-stu-id="a557f-172">Add or block a domain</span></span>

<span data-ttu-id="a557f-173">Suivez ces étapes pour ajouter un domaine ou de désactiver l’accès externe pour un domaine.</span><span class="sxs-lookup"><span data-stu-id="a557f-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="a557f-174">Dans le Microsoft Teams & Skype entreprise centre d’administration, sélectionnez **paramètres à l’échelle de la société** > **l’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="a557f-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="a557f-175">Sélectionnez **Ajouter un domaine**.</span><span class="sxs-lookup"><span data-stu-id="a557f-175">Select **Add a domain**.</span></span> 
 
    ![Capture d’écran externe page d’accès aux ajouter un lien de domaine](media/manage-external-access-3.png)<span data-ttu-id="a557f-177">.</span><span class="sxs-lookup"><span data-stu-id="a557f-177"></span></span>

   <span data-ttu-id="a557f-178">Le volet **Ajouter un domaine** apparaît.</span><span class="sxs-lookup"><span data-stu-id="a557f-178">The **Add a domain** pane appears.</span></span>

    ![Capture d’écran d’ajouter un volet de domaine](media/manage-external-access-4.png)<span data-ttu-id="a557f-180">.</span><span class="sxs-lookup"><span data-stu-id="a557f-180"></span></span>


3. <span data-ttu-id="a557f-181">Sous **Ajouter un domaine**, tapez le nom du domaine ; par exemple, tapez Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a557f-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="a557f-182">Sélectionnez **autorisées** ou **bloquées**.</span><span class="sxs-lookup"><span data-stu-id="a557f-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="a557f-183">Vous pouvez modifier ce paramètre à tout moment.</span><span class="sxs-lookup"><span data-stu-id="a557f-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="a557f-184">Cliquez sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="a557f-184">Select **Done**.</span></span>

<span data-ttu-id="a557f-185">Après avoir ajouté un domaine, vous verrez le nom de domaine et l’état ajouté à la liste des domaines dans la page d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="a557f-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="a557f-186">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="a557f-186">More information</span></span>

<span data-ttu-id="a557f-187">Pour plus d’informations sur l’accès invité dans Microsoft Teams, voir [Gérer les accès invité dans les équipes Microsoft](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="a557f-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>