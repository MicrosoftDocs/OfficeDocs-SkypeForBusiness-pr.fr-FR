---
title: Créer une file d'attente d'appels dans Microsoft Teams - Didacticiel petite entreprise
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Découvrez comment configurer des files d'attente d'appels avec Microsoft 365 Business Voice.
ms.openlocfilehash: ded780f0793a503e4f4089c7a201e659008e9eb7
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030124"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="07f0c-103">Créer une file d'attente d'appels - Didacticiel pour les petites entreprises</span><span class="sxs-lookup"><span data-stu-id="07f0c-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="07f0c-104">Les files d’attente des appels utilisent une méthode de routage des appelants, qui sont orientés vers les personnes de votre organisation qui pourront les aider à résoudre un problème ou répondre à une question.</span><span class="sxs-lookup"><span data-stu-id="07f0c-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="07f0c-105">Les appels sont distribués les uns après les autres aux personnes présentes dans la file d’attente (appelées *agents*).</span><span class="sxs-lookup"><span data-stu-id="07f0c-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="07f0c-106">Les files d’attente des appels fournissent :</span><span class="sxs-lookup"><span data-stu-id="07f0c-106">Call queues provide:</span></span>

- <span data-ttu-id="07f0c-107">un message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="07f0c-107">A greeting message.</span></span>

- <span data-ttu-id="07f0c-108">une musique pour les personnes en attente dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="07f0c-109">un routage des appels vers les agents, en utilisant la méthode *Premier entré, premier sorti* (PEPS).</span><span class="sxs-lookup"><span data-stu-id="07f0c-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="07f0c-110">Gestion des options pour le débordement et la temporisation des files d’attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="07f0c-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="07f0c-111">Before you begin</span></span>

<span data-ttu-id="07f0c-112">Système [téléphonique : licences utilisateur virtuel si](../teams-add-on-licensing/virtual-user.md) vous ne les avez pas encore.</span><span class="sxs-lookup"><span data-stu-id="07f0c-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="07f0c-113">Obtenez une file d'attente pour chaque file d'attente d'appels et chaque personne de service automatique que vous prévoyez de configurer.</span><span class="sxs-lookup"><span data-stu-id="07f0c-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="07f0c-114">Ces licences sont gratuites. Nous vous suggérons donc d'en obtenir quelques supplémentaires si vous décidez de modifier votre installation ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="07f0c-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="07f0c-115">Étant donné que des agents dans une file d'attente d'appels peuvent appeler pour renvoyer un appel client, envisagez de définir l'ID d'appelant de vos agents d'appel sur votre numéro de téléphone principal ou le numéro d'un traitement automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="07f0c-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="07f0c-116">Consultez l’article [Gérer les stratégies d’identification de l’appelant dans Microsoft Teams](../caller-id-policies.md) pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="07f0c-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="07f0c-117">Pour configurer votre file d'attente d'appels, suivez ces étapes</span><span class="sxs-lookup"><span data-stu-id="07f0c-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="07f0c-118">Étape 1 <br> Créer une équipe</span><span class="sxs-lookup"><span data-stu-id="07f0c-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="07f0c-119">Lorsque vous créez une file d'attente d'appels, vous pouvez ajouter des utilisateurs individuels à la file d'attente ou utiliser un groupe de sécurité existant, un groupe Microsoft 365 ou une équipe Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="07f0c-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="07f0c-120">Nous vous recommandons [d'utiliser un canal d'équipe.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="07f0c-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="07f0c-121">Cela permet aux membres de la file d'attente de discuter entre eux, de partager des idées et de créer des documents ou d'autres ressources pour aider vos clients.</span><span class="sxs-lookup"><span data-stu-id="07f0c-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="07f0c-122">Une équipe fournit également une boîte vocale qui permet aux appelants de laisser un message après les heures d'ouverture ou si la file d'attente atteint sa capacité maximale.</span><span class="sxs-lookup"><span data-stu-id="07f0c-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="07f0c-123">Pour créer une équipe</span><span class="sxs-lookup"><span data-stu-id="07f0c-123">To create a team</span></span>

1. <span data-ttu-id="07f0c-124">Tout d'abord, cliquez **sur Teams** dans  la partie gauche de l'application, puis cliquez sur Rejoindre ou créer une équipe en bas de votre liste d'équipes.</span><span class="sxs-lookup"><span data-stu-id="07f0c-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="07f0c-125">Cliquez ensuite **sur Créer une équipe** (première carte, coin supérieur gauche).</span><span class="sxs-lookup"><span data-stu-id="07f0c-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="07f0c-126">Sélectionnez **Créer une équipe de toutes pièces.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="07f0c-127">Choisissez ensuite si vous souhaitez une équipe publique ou privée.</span><span class="sxs-lookup"><span data-stu-id="07f0c-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="07f0c-128">Nous vous recommandons **de mettre votre** file d'attente d'appels privé pour éviter que des personnes ne se retrouvent involontairement dans la file d'attente en rejoignant l'équipe.</span><span class="sxs-lookup"><span data-stu-id="07f0c-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="07f0c-129">Nommez votre équipe et ajoutez une description facultative.</span><span class="sxs-lookup"><span data-stu-id="07f0c-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="07f0c-130">Lorsque vous avez terminé, cliquez sur **Créer.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="07f0c-131">Tapez les noms des personnes que vous voulez avoir dans votre file d'attente d'appels, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="07f0c-132">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="07f0c-132">Click **Close**.</span></span> <span data-ttu-id="07f0c-133">Les personnes que vous ajoutez à une équipe recevront un e-mail leur faisant savoir qu'elles sont désormais membres de votre équipe et que l'équipe s'affichera dans leur liste d'équipes.</span><span class="sxs-lookup"><span data-stu-id="07f0c-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="07f0c-134">Nous allons ensuite ajouter un canal à utiliser avec la file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="07f0c-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="07f0c-135">Pour ajouter un canal</span><span class="sxs-lookup"><span data-stu-id="07f0c-135">To add a channel</span></span>

1. <span data-ttu-id="07f0c-136">Dans Teams, recherchez l'équipe que vous vient de créer, cliquez sur Autres **options** (...), puis sur **Ajouter un canal.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="07f0c-137">Tapez un nom et une description pour le canal, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="07f0c-138">Étape 2 : gestion des comptes de ressources ></span><span class="sxs-lookup"><span data-stu-id="07f0c-138">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="07f0c-139">Étape 2 Comptes <br> de ressources</span><span class="sxs-lookup"><span data-stu-id="07f0c-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="07f0c-140">Chaque file d'attente d'appels que vous créez nécessite un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="07f0c-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="07f0c-141">Ce compte est similaire à un compte d'utilisateur, sauf qu'il est associé à un service de attendant automatique ou à une file d'attente d'appels au lieu d'une personne.</span><span class="sxs-lookup"><span data-stu-id="07f0c-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="07f0c-142">Dans cette étape, nous allons créer le compte, lui attribuer une licence *Microsoft 365 Phone System - Utilisateur* virtuel, puis l'utiliser pour commencer à créer la file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="07f0c-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="07f0c-143">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="07f0c-143">Create a resource account</span></span>

<span data-ttu-id="07f0c-144">Vous pouvez créer un compte de ressource dans le Centre d'administration Teams.</span><span class="sxs-lookup"><span data-stu-id="07f0c-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="07f0c-145">Dans le Centre d'administration Teams, développez **les paramètres** à l'échelle de l'organisation, puis cliquez sur **Comptes de ressources.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="07f0c-146">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="07f0c-146">Click **Add**.</span></span>

3. <span data-ttu-id="07f0c-147">Dans le **volet Ajouter un compte de** ressource, remplissez Nom **d'affichage,** Nom d'utilisateur et sélectionnez **File** d'attente d'appels pour le type de compte de **ressource.** </span><span class="sxs-lookup"><span data-stu-id="07f0c-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="07f0c-148">Les agents peuvent voir le nom complet lorsqu'ils reçoivent un appel entrant depuis la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-148">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![Capture d'écran de l'interface utilisateur Ajouter un compte de ressource](../media/resource-account-add-cq.png)

4. <span data-ttu-id="07f0c-150">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="07f0c-150">Click **Save**.</span></span>

   <span data-ttu-id="07f0c-151">Le nouveau compte apparaît dans la liste des comptes.</span><span class="sxs-lookup"><span data-stu-id="07f0c-151">The new account will appear in the list of accounts.</span></span>

   ![Capture d'écran d'une liste des comptes de ressources](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="07f0c-153">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="07f0c-153">Assign a license</span></span>

<span data-ttu-id="07f0c-154">Vous devez attribuer une *licence Microsoft 365 Phone System - Utilisateur* virtuel au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="07f0c-154">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="07f0c-155">Dans le Centre d'administration Microsoft 365, dans la liste **Utilisateurs** actifs, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.</span><span class="sxs-lookup"><span data-stu-id="07f0c-155">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="07f0c-156">Sous **l'onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Phone System - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-156">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="07f0c-157">Cliquez **sur Enregistrer les modifications.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-157">Click **Save changes**.</span></span>

    ![Capture d'écran de l'interface utilisateur d'attribution de licences dans le Centre d'administration Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="07f0c-159">Créer une file d’attente des appels</span><span class="sxs-lookup"><span data-stu-id="07f0c-159">Create a call queue</span></span>

<span data-ttu-id="07f0c-160">Nous allons ensuite commencer à créer une file d'attente d'appels et affecter le compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="07f0c-160">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="07f0c-161">Dans le Centre d'administration Teams, **développez Voix,** cliquez **sur Files d'attente d'appels,** puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-161">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="07f0c-162">Saisissez un nom pour la file d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="07f0c-162">Type a name for the call queue.</span></span>

2. <span data-ttu-id="07f0c-163">Cliquez sur **Ajouter des comptes**, recherchez le compte de ressource que vous souhaitez utiliser avec cette file d’attente des appels, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="07f0c-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="07f0c-164">Choisissez une langue.</span><span class="sxs-lookup"><span data-stu-id="07f0c-164">Choose a language.</span></span> <span data-ttu-id="07f0c-165">Nous utiliserons cette langue pour les invites vocales générées par le système et la transcription de la messagerie vocale (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="07f0c-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Capture d’écran du compte de ressource et des paramètres de langue](../media/call-queue-name-language.png)

4. <span data-ttu-id="07f0c-167">Indiquez si vous souhaitez diffuser un message d’accueil aux appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="07f0c-168">Vous devez télécharger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous souhaitez diffuser.</span><span class="sxs-lookup"><span data-stu-id="07f0c-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="07f0c-169">Teams fournit une musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="07f0c-170">Si vous souhaitez diffuser un fichier audio spécifique, choisissez **Lire un fichier audio** et téléchargez un fichier MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="07f0c-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="07f0c-171">La taille maximale de l’enregistrement téléchargé est de 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="07f0c-171">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="07f0c-172">La musique par défaut fournie dans les files d’attente des appels Teams est exempte de toute redevance payable par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="07f0c-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="07f0c-173">Étape 3 : appeler des ></span><span class="sxs-lookup"><span data-stu-id="07f0c-173">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="07f0c-174">Étape 3 : appeler <br> les agents</span><span class="sxs-lookup"><span data-stu-id="07f0c-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="07f0c-175">Pour ajouter des agents à la file d'attente d'appels, nous les ajouterons à l'équipe et au canal que nous avons créés précédemment.</span><span class="sxs-lookup"><span data-stu-id="07f0c-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="07f0c-176">Sélectionnez **l'option Choisir une** équipe, puis cliquez sur Ajouter un **canal.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="07f0c-177">Tapez le nom de l'équipe que vous avez créée, sélectionnez-la, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="07f0c-178">Sélectionnez le canal que vous avez créé pour la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="07f0c-179">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="07f0c-179">Click **Apply**.</span></span>

    ![Capture d’écran des paramètres des utilisateurs et des groupes pour les files d’attente des appels](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="07f0c-181">Lorsque de nouveaux utilisateurs sont ajoutés à l'équipe, jusqu'à huit heures peuvent être s'il s'agit de leur premier appel.</span><span class="sxs-lookup"><span data-stu-id="07f0c-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="07f0c-182">Étape 4 : gestion des comptes de ></span><span class="sxs-lookup"><span data-stu-id="07f0c-182">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="07f0c-183">Étape 4 <br> Routage des appels</span><span class="sxs-lookup"><span data-stu-id="07f0c-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="07f0c-184">Choisissez la méthode de routage des appels que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="07f0c-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="07f0c-185">Définir **le mode Conférence** sur **Automatique.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="07f0c-186">Choisissez la **méthode de routage** que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="07f0c-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="07f0c-187">Cela détermine l'ordre dans lequel les agents reçoivent les appels de la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="07f0c-188">Nous vous recommandons **de router en série** ou de **rais rond.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="07f0c-189">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="07f0c-189">Choose from these options:</span></span>

    - <span data-ttu-id="07f0c-190">Le **routage du standard** appelle tous les agents de la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="07f0c-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="07f0c-191">Le premier agent à prendre l’appel reçoit l’appel.</span><span class="sxs-lookup"><span data-stu-id="07f0c-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="07f0c-192">**Le routage en série** a pour but de faire sonner un par un tous les agents d'appel.</span><span class="sxs-lookup"><span data-stu-id="07f0c-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="07f0c-193">Si un agent rejette ou ne répond pas à un appel, l’appel sera transféré à l’agent suivant et à tous les agents jusqu’à ce que l’un deux réponde ou que le temps soit écoulé.</span><span class="sxs-lookup"><span data-stu-id="07f0c-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="07f0c-194">Le **tourniquet (round robin)** équilibre le routage des appels entrants afin que chaque agent d’appel reçoive le même nombre d’appels provenant de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="07f0c-195">Ceci peut être utile dans un environnement de ventes entrantes pour assurer l’égalité des chances entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="07f0c-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="07f0c-196">L’**inactivité la plus longue** achemine chaque appel vers l’agent qui a été inactif le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="07f0c-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="07f0c-197">(Les agents dont l'état de présence est Absent depuis plus de 10 minutes ne sont pas inclus.)</span><span class="sxs-lookup"><span data-stu-id="07f0c-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Capture d’écran des paramètres du mode conférence et de la méthode de routage](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="07f0c-199">Activer **le routage en fonction des** présences</span><span class="sxs-lookup"><span data-stu-id="07f0c-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="07f0c-200">Cela a pour but d'appeler des agents dont le statut de présence **est disponible.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="07f0c-201">Choisissez si vous voulez autoriser les agents à se désaisser des appels.</span><span class="sxs-lookup"><span data-stu-id="07f0c-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="07f0c-202">Définissez une **heure d'alerte** de l'agent pour spécifier combien de temps le téléphone d'un agent sonnera avant que la file d'attente redirige l'appel vers le prochain agent.</span><span class="sxs-lookup"><span data-stu-id="07f0c-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Capture d’écran des paramètres de routage, de désactivation et d’alerte](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="07f0c-204">Étape 5 : dépassement de capacité d'></span><span class="sxs-lookup"><span data-stu-id="07f0c-204">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="07f0c-205">Étape 5 - <br> Dépassement de capacité d'appel</span><span class="sxs-lookup"><span data-stu-id="07f0c-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="07f0c-206">Choisissez comment vous voulez gérer les appels dont le nombre d'appels dépasse le nombre maximal dans la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="07f0c-207">Définir le **nombre maximal d'appels dans la file d'attente.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="07f0c-208">Choisissez ce que vous voulez faire lorsque le nombre maximal d'appels est atteint.</span><span class="sxs-lookup"><span data-stu-id="07f0c-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="07f0c-209">Vous pouvez déconnecter l'appel ou le rediriger.</span><span class="sxs-lookup"><span data-stu-id="07f0c-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="07f0c-210">Nous vous recommandons de rediriger l'appel vers l'une des destinations suivantes :</span><span class="sxs-lookup"><span data-stu-id="07f0c-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="07f0c-211">**Personne dans l'organisation** - une personne de votre organisation qui peut recevoir des appels vocux</span><span class="sxs-lookup"><span data-stu-id="07f0c-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="07f0c-212">**Application vocale :** un attendant automatique ou une autre file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="07f0c-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="07f0c-213">(Choisissez le compte de ressource associé au port automatique ou à la file d'attente d'appels lorsque vous choisissez cette destination.)</span><span class="sxs-lookup"><span data-stu-id="07f0c-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="07f0c-214">**Numéro de téléphone externe -** n'importe quel numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="07f0c-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="07f0c-215">Utilisez ce format : +[code pays][code de zone][numéro de téléphone]</span><span class="sxs-lookup"><span data-stu-id="07f0c-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="07f0c-216">**Messagerie vocale** : vous pouvez utiliser la boîte aux lettres vocale de l'équipe que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="07f0c-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Capture d’écran des paramètres de débordement des appels](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="07f0c-218">Étape 6 : délai d'></span><span class="sxs-lookup"><span data-stu-id="07f0c-218">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="07f0c-219">Délai d'appel <br> d'étape 6</span><span class="sxs-lookup"><span data-stu-id="07f0c-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="07f0c-220">Choisissez ce que vous voulez faire lorsque les appels sont trop longs dans la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="07f0c-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="07f0c-221">Définissez le **temps d'attente maximal.**</span><span class="sxs-lookup"><span data-stu-id="07f0c-221">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="07f0c-222">Choisissez ce que vous voulez faire lorsqu'un appel arrive à la fin. Vous pouvez déconnecter l'appel ou le rediriger.</span><span class="sxs-lookup"><span data-stu-id="07f0c-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="07f0c-223">Nous vous recommandons de rediriger l'appel vers l'une des destinations suivantes :</span><span class="sxs-lookup"><span data-stu-id="07f0c-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="07f0c-224">**Personne dans l'organisation** - une personne de votre organisation qui peut recevoir des appels vocux</span><span class="sxs-lookup"><span data-stu-id="07f0c-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="07f0c-225">**Application vocale :** un attendant automatique ou une autre file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="07f0c-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="07f0c-226">(Choisissez le compte de ressource associé au port automatique ou à la file d'attente d'appels lorsque vous choisissez cette destination.)</span><span class="sxs-lookup"><span data-stu-id="07f0c-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="07f0c-227">**Numéro de téléphone externe -** n'importe quel numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="07f0c-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="07f0c-228">Utilisez ce format : +[code pays][code de zone][numéro de téléphone]</span><span class="sxs-lookup"><span data-stu-id="07f0c-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="07f0c-229">**Messagerie vocale** : vous pouvez utiliser la boîte aux lettres vocale de l'équipe que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="07f0c-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Capture d’écran des paramètres de temporisation des appels](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="07f0c-231">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="07f0c-231">Click **Save**.</span></span>

<span data-ttu-id="07f0c-232">Cela termine la configuration de votre file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="07f0c-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="07f0c-233">Vous pouvez ensuite configurer [un attendant automatique.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="07f0c-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

