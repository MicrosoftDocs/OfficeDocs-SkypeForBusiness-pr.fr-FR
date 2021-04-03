---
title: Créer une file d’attente d’appels dans Microsoft Teams - Didacticiel petite entreprise
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
description: Découvrez comment configurer des files d’attente d’appels avec Microsoft 365 Business Voice.
ms.openlocfilehash: f60919dccd25231dbdb7e9c2991251bcb3f96700
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506641"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="c6107-103">Créer une file d’attente d’appels - Didacticiel pour les petites entreprises</span><span class="sxs-lookup"><span data-stu-id="c6107-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="c6107-104">Les files d’attente offrent une méthode de routage des appelants vers les personnes de votre organisation qui peuvent vous aider à répondre à un problème ou une question spécifique.</span><span class="sxs-lookup"><span data-stu-id="c6107-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="c6107-105">Les appels sont distribués un par un aux personnes dans la file d’attente (appelées *agents).*</span><span class="sxs-lookup"><span data-stu-id="c6107-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="c6107-106">Les files d’attente fournissent les services :</span><span class="sxs-lookup"><span data-stu-id="c6107-106">Call queues provide:</span></span>

- <span data-ttu-id="c6107-107">Message de salutation.</span><span class="sxs-lookup"><span data-stu-id="c6107-107">A greeting message.</span></span>

- <span data-ttu-id="c6107-108">Musique pendant que des personnes sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="c6107-109">Routage des appels *(dans l’ordre* Premier dans, Premier sorti (FIFO) - vers des agents.</span><span class="sxs-lookup"><span data-stu-id="c6107-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="c6107-110">Options de gestion pour le dépassement de capacité et le délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="c6107-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c6107-111">Before you begin</span></span>

<span data-ttu-id="c6107-112">Système [téléphonique : licences utilisateur virtuel si](../teams-add-on-licensing/virtual-user.md) vous ne les avez pas encore.</span><span class="sxs-lookup"><span data-stu-id="c6107-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="c6107-113">Obtenez une file d’attente pour chaque file d’attente d’appels et chaque personne de service automatique que vous prévoyez de configurer.</span><span class="sxs-lookup"><span data-stu-id="c6107-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="c6107-114">Ces licences sont gratuites. Nous vous suggérons donc d’en obtenir quelques supplémentaires si vous décidez de modifier votre installation ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="c6107-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="c6107-115">Étant donné que des agents dans une file d’attente d’appels peuvent appeler pour renvoyer un appel client, envisagez de définir l’ID d’appelant de vos agents d’appel sur votre numéro de téléphone principal ou le numéro d’un traitement automatique approprié.</span><span class="sxs-lookup"><span data-stu-id="c6107-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="c6107-116">Pour plus d’informations, voir Gérer les [stratégies d’ID](../caller-id-policies.md) d’appelant dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6107-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="c6107-117">Pour configurer votre file d’attente d’appels, suivez ces étapes</span><span class="sxs-lookup"><span data-stu-id="c6107-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="c6107-118">Étape 1 <br> Créer une équipe</span><span class="sxs-lookup"><span data-stu-id="c6107-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="c6107-119">Lorsque vous créez une file d’attente d’appels, vous pouvez ajouter des utilisateurs individuels à la file d’attente ou utiliser un groupe de sécurité existant, un groupe Microsoft 365 ou une équipe Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6107-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="c6107-120">Nous vous recommandons [d’utiliser un canal d’équipe.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)</span><span class="sxs-lookup"><span data-stu-id="c6107-120">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="c6107-121">Cela permet aux membres de la file d’attente de discuter entre eux, de partager des idées et de créer des documents ou d’autres ressources pour aider vos clients.</span><span class="sxs-lookup"><span data-stu-id="c6107-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="c6107-122">Une équipe fournit également une boîte vocale qui permet aux appelants de laisser un message après les heures d’ouverture ou si la file d’attente atteint sa capacité maximale.</span><span class="sxs-lookup"><span data-stu-id="c6107-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="c6107-123">Pour créer une équipe</span><span class="sxs-lookup"><span data-stu-id="c6107-123">To create a team</span></span>

1. <span data-ttu-id="c6107-124">Tout d’abord, cliquez **sur Teams** dans  la partie gauche de l’application, puis cliquez sur Rejoindre ou créer une équipe en bas de votre liste d’équipes.</span><span class="sxs-lookup"><span data-stu-id="c6107-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="c6107-125">Cliquez ensuite **sur Créer une équipe** (première carte, coin supérieur gauche).</span><span class="sxs-lookup"><span data-stu-id="c6107-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="c6107-126">Sélectionnez **Créer une équipe de toutes pièces.**</span><span class="sxs-lookup"><span data-stu-id="c6107-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="c6107-127">Choisissez ensuite si vous souhaitez une équipe publique ou privée.</span><span class="sxs-lookup"><span data-stu-id="c6107-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="c6107-128">Nous vous recommandons **de mettre votre** file d’attente d’appels privé pour éviter que des personnes ne se retrouvent involontairement dans la file d’attente en rejoignant l’équipe.</span><span class="sxs-lookup"><span data-stu-id="c6107-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="c6107-129">Nommez votre équipe et ajoutez une description facultative.</span><span class="sxs-lookup"><span data-stu-id="c6107-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="c6107-130">Lorsque vous avez terminé, cliquez sur **Créer.**</span><span class="sxs-lookup"><span data-stu-id="c6107-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="c6107-131">Tapez les noms des personnes que vous voulez avoir dans votre file d’attente d’appels, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="c6107-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="c6107-132">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c6107-132">Click **Close**.</span></span> <span data-ttu-id="c6107-133">Les personnes que vous ajoutez à une équipe recevront un e-mail leur faisant savoir qu’elles sont désormais membres de votre équipe et que l’équipe s’affichera dans leur liste d’équipes.</span><span class="sxs-lookup"><span data-stu-id="c6107-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="c6107-134">Nous allons ensuite ajouter un canal à utiliser avec la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c6107-134">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="c6107-135">Pour ajouter un canal</span><span class="sxs-lookup"><span data-stu-id="c6107-135">To add a channel</span></span>

1. <span data-ttu-id="c6107-136">Dans Teams, recherchez l’équipe que vous vient de créer, cliquez sur Autres **options** (...), puis sur **Ajouter un canal.**</span><span class="sxs-lookup"><span data-stu-id="c6107-136">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="c6107-137">Tapez un nom et une description pour le canal, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="c6107-137">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c6107-138">Étape 2 : gestion des comptes de ressources ></span><span class="sxs-lookup"><span data-stu-id="c6107-138">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="c6107-139">Étape 2 Comptes <br> de ressources</span><span class="sxs-lookup"><span data-stu-id="c6107-139">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="c6107-140">Chaque file d’attente d’appels que vous créez nécessite un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c6107-140">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="c6107-141">Ce compte est similaire à un compte d’utilisateur, sauf qu’il est associé à un service de attendant automatique ou à une file d’attente d’appels au lieu d’une personne.</span><span class="sxs-lookup"><span data-stu-id="c6107-141">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="c6107-142">Dans cette étape, nous allons créer le compte, lui attribuer une licence *Microsoft 365 Phone System - Utilisateur* virtuel, puis l’utiliser pour commencer à créer la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c6107-142">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="c6107-143">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="c6107-143">Create a resource account</span></span>

<span data-ttu-id="c6107-144">Vous pouvez créer un compte de ressource dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="c6107-144">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="c6107-145">Dans le Centre d’administration Teams, développez **les paramètres** à l’échelle de l’organisation, puis cliquez **sur Comptes de ressources.**</span><span class="sxs-lookup"><span data-stu-id="c6107-145">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="c6107-146">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c6107-146">Click **Add**.</span></span>

3. <span data-ttu-id="c6107-147">Dans le **volet Ajouter un compte de** ressource, remplissez Nom **d’affichage,** Nom d’utilisateur et sélectionnez **File** d’attente d’appels pour le type de compte de **ressource.** </span><span class="sxs-lookup"><span data-stu-id="c6107-147">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](../media/resource-account-add-cq.png)

4. <span data-ttu-id="c6107-149">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c6107-149">Click **Save**.</span></span>

<span data-ttu-id="c6107-150">Le nouveau compte apparaît dans la liste des comptes.</span><span class="sxs-lookup"><span data-stu-id="c6107-150">The new account will appear in the list of accounts.</span></span>

![Capture d’écran d’une liste des comptes de ressources](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="c6107-152">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="c6107-152">Assign a license</span></span>

<span data-ttu-id="c6107-153">Vous devez attribuer une *licence Microsoft 365 Phone System - Utilisateur* virtuel au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c6107-153">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="c6107-154">Dans le Centre d’administration Microsoft 365, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.</span><span class="sxs-lookup"><span data-stu-id="c6107-154">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="c6107-155">Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Phone System - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="c6107-155">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="c6107-156">Cliquez **sur Enregistrer les modifications.**</span><span class="sxs-lookup"><span data-stu-id="c6107-156">Click **Save changes**.</span></span>

    ![Capture d’écran de l’interface utilisateur d’attribution de licences dans le Centre d’administration Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="c6107-158">Créer une file d’attente d’appel</span><span class="sxs-lookup"><span data-stu-id="c6107-158">Create a call queue</span></span>

<span data-ttu-id="c6107-159">Nous allons ensuite commencer à créer une file d’attente d’appels et affecter le compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c6107-159">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="c6107-160">Dans le Centre d’administration Teams, **développez Voix,** cliquez **sur Files d’attente d’appels,** puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="c6107-160">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="c6107-161">Tapez un nom pour la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c6107-161">Type a name for the call queue.</span></span> <span data-ttu-id="c6107-162">Les agents voient ce nom lorsqu’ils reçoivent un appel entrant de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-162">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="c6107-163">Cliquez **sur Ajouter des comptes,** recherchez le compte de ressource à utiliser avec cette file d’attente d’appels, cliquez sur Ajouter, puis sur **Ajouter.** </span><span class="sxs-lookup"><span data-stu-id="c6107-163">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="c6107-164">Choisissez une langue.</span><span class="sxs-lookup"><span data-stu-id="c6107-164">Choose a language.</span></span> <span data-ttu-id="c6107-165">Cette langue sera utilisée pour les invites vocales générées par le système et la transcription des messages vocaux (si vous les activez).</span><span class="sxs-lookup"><span data-stu-id="c6107-165">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![Capture d’écran des paramètres de compte de ressource et de langue](../media/call-queue-name-language.png)

4. <span data-ttu-id="c6107-167">Indiquez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-167">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="c6107-168">Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil à lire.</span><span class="sxs-lookup"><span data-stu-id="c6107-168">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="c6107-169">Teams fournit de la musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-169">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="c6107-170">Si vous souhaitez lire un fichier audio spécifique, sélectionnez Lire un fichier **audio** et téléchargez un fichier MP3, WAV ou WMA.</span><span class="sxs-lookup"><span data-stu-id="c6107-170">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="c6107-171">L’enregistrement téléchargé ne peut pas avoir une taille supérieure à 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="c6107-171">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="c6107-172">La musique par défaut fournie dans les files d’attente d’appels de Teams est gratuite pour toutes les redevances payables par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c6107-172">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="c6107-173">Étape 3 : appeler des ></span><span class="sxs-lookup"><span data-stu-id="c6107-173">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="c6107-174">Étape 3 : appeler <br> les agents</span><span class="sxs-lookup"><span data-stu-id="c6107-174">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="c6107-175">Pour ajouter des agents à la file d’attente d’appels, nous les ajouterons à l’équipe et au canal que nous avons créés précédemment.</span><span class="sxs-lookup"><span data-stu-id="c6107-175">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span>

1. <span data-ttu-id="c6107-176">Sélectionnez **l’option Choisir une** équipe, puis cliquez sur Ajouter un **canal.**</span><span class="sxs-lookup"><span data-stu-id="c6107-176">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="c6107-177">Tapez le nom de l’équipe que vous avez créée, sélectionnez-la, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="c6107-177">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="c6107-178">Sélectionnez le canal que vous avez créé pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-178">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="c6107-179">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="c6107-179">Click **Apply**.</span></span>

    ![Capture d’écran des paramètres d’utilisateurs et de groupes pour les files d’attente d’appels](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="c6107-181">Lorsque de nouveaux utilisateurs sont ajoutés à l’équipe, jusqu’à huit heures peuvent être s’il s’agit de leur premier appel.</span><span class="sxs-lookup"><span data-stu-id="c6107-181">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c6107-182">Étape 4 : gestion des comptes de ></span><span class="sxs-lookup"><span data-stu-id="c6107-182">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="c6107-183">Étape 4 <br> Routage des appels</span><span class="sxs-lookup"><span data-stu-id="c6107-183">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="c6107-184">Choisissez la méthode de routage des appels que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="c6107-184">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="c6107-185">Définir **le mode Conférence** sur **Automatique.**</span><span class="sxs-lookup"><span data-stu-id="c6107-185">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="c6107-186">Choisissez la **méthode de routage** que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="c6107-186">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="c6107-187">Cela détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-187">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="c6107-188">Nous vous recommandons **de router en série** ou de **rais rond.**</span><span class="sxs-lookup"><span data-stu-id="c6107-188">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="c6107-189">Choisissez l’une des options ci-après :</span><span class="sxs-lookup"><span data-stu-id="c6107-189">Choose from these options:</span></span>

    - <span data-ttu-id="c6107-190">**Le routage d’Attendant** sonne tous les agents dans la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="c6107-190">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="c6107-191">Le premier appelant à prendre l’appel reçoit l’appel.</span><span class="sxs-lookup"><span data-stu-id="c6107-191">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="c6107-192">**Le routage en série** a pour but de faire sonner un par un tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="c6107-192">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="c6107-193">Si un agent le fait sans appel ou ne décroche pas, l’appel sonnera sur l’agent suivant et essaiera tous les agents jusqu’à ce qu’il soit choisi ou mis hors appel.</span><span class="sxs-lookup"><span data-stu-id="c6107-193">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="c6107-194">**L’arrondi balance** le routage des appels entrants de sorte que chaque agent d’appel reçoie le même nombre d’appels depuis la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-194">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="c6107-195">Cela pourrait être souhaitable dans un environnement de vente entrante afin d’assurer la même opportunité entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="c6107-195">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="c6107-196">**Les itinéraires inactifs** les plus longs à chaque appel à l’agent inactif la plus longue.</span><span class="sxs-lookup"><span data-stu-id="c6107-196">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="c6107-197">(Les agents dont l’état de présence est Absent depuis plus de 10 minutes ne sont pas inclus.)</span><span class="sxs-lookup"><span data-stu-id="c6107-197">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![Capture d’écran des paramètres du mode de conférence et de la méthode de routage](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="c6107-199">Activer **le routage en fonction des** présences</span><span class="sxs-lookup"><span data-stu-id="c6107-199">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="c6107-200">Cela a pour but d’appeler des agents dont le statut de présence **est disponible.**</span><span class="sxs-lookup"><span data-stu-id="c6107-200">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="c6107-201">Choisissez si vous voulez autoriser les agents à se désaisser des appels.</span><span class="sxs-lookup"><span data-stu-id="c6107-201">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="c6107-202">Définissez une **heure d’alerte** de l’agent pour spécifier combien de temps le téléphone d’un agent sonnera avant que la file d’attente redirige l’appel vers le prochain agent.</span><span class="sxs-lookup"><span data-stu-id="c6107-202">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![Capture d’écran des paramètres de routage, de désinspondage et d’heure d’alerte](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="c6107-204">Étape 5 : dépassement de capacité d'></span><span class="sxs-lookup"><span data-stu-id="c6107-204">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="c6107-205">Étape 5 - <br> Dépassement de capacité d’appel</span><span class="sxs-lookup"><span data-stu-id="c6107-205">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="c6107-206">Choisissez comment vous voulez gérer les appels dont le nombre d’appels dépasse le nombre maximal dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-206">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="c6107-207">Définir le **nombre maximal d’appels dans la file d’attente.**</span><span class="sxs-lookup"><span data-stu-id="c6107-207">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="c6107-208">Choisissez ce que vous voulez faire lorsque le nombre maximal d’appels est atteint.</span><span class="sxs-lookup"><span data-stu-id="c6107-208">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="c6107-209">Vous pouvez déconnecter l’appel ou le rediriger.</span><span class="sxs-lookup"><span data-stu-id="c6107-209">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="c6107-210">Nous vous recommandons de rediriger l’appel vers l’une des destinations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6107-210">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="c6107-211">**Personne dans l’organisation** - une personne de votre organisation qui peut recevoir des appels vocux</span><span class="sxs-lookup"><span data-stu-id="c6107-211">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="c6107-212">**Application vocale :** un attendant automatique ou une autre file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c6107-212">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="c6107-213">(Choisissez le compte de ressource associé au port automatique ou à la file d’attente d’appels lorsque vous choisissez cette destination.)</span><span class="sxs-lookup"><span data-stu-id="c6107-213">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="c6107-214">**Numéro de téléphone externe -** n’importe quel numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="c6107-214">**External phone number** - any phone number.</span></span> <span data-ttu-id="c6107-215">Utilisez ce format : +[code pays][code de zone][numéro de téléphone]</span><span class="sxs-lookup"><span data-stu-id="c6107-215">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="c6107-216">**Messagerie vocale** : vous pouvez utiliser la boîte aux lettres vocale de l’équipe que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="c6107-216">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Capture d’écran des paramètres de dépassement de capacité d’appel](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="c6107-218">Étape 6 : délai d'></span><span class="sxs-lookup"><span data-stu-id="c6107-218">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="c6107-219">Délai d’appel <br> d’étape 6</span><span class="sxs-lookup"><span data-stu-id="c6107-219">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="c6107-220">Choisissez ce que vous voulez faire lorsque les appels sont trop longs dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c6107-220">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="c6107-221">Définir le **délai d’attente des appels : temps d’attente maximal.**</span><span class="sxs-lookup"><span data-stu-id="c6107-221">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="c6107-222">Choisissez ce que vous voulez faire lorsqu’un appel arrive à la fin. Vous pouvez déconnecter l’appel ou le rediriger.</span><span class="sxs-lookup"><span data-stu-id="c6107-222">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="c6107-223">Nous vous recommandons de rediriger l’appel vers l’une des destinations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6107-223">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="c6107-224">**Personne dans l’organisation** - une personne de votre organisation qui peut recevoir des appels vocux</span><span class="sxs-lookup"><span data-stu-id="c6107-224">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="c6107-225">**Application vocale :** un attendant automatique ou une autre file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c6107-225">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="c6107-226">(Choisissez le compte de ressource associé au port automatique ou à la file d’attente d’appels lorsque vous choisissez cette destination.)</span><span class="sxs-lookup"><span data-stu-id="c6107-226">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="c6107-227">**Numéro de téléphone externe -** n’importe quel numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="c6107-227">**External phone number** - any phone number.</span></span> <span data-ttu-id="c6107-228">Utilisez ce format : +[code pays][code de zone][numéro de téléphone]</span><span class="sxs-lookup"><span data-stu-id="c6107-228">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="c6107-229">**Messagerie vocale** : vous pouvez utiliser la boîte aux lettres vocale de l’équipe que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="c6107-229">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![Capture d’écran des paramètres de délai d’appel](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="c6107-231">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c6107-231">Click **Save**.</span></span>

<span data-ttu-id="c6107-232">Cela termine la configuration de votre file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c6107-232">This completes the setup of your call queue.</span></span> <span data-ttu-id="c6107-233">Vous pouvez ensuite configurer [un attendant automatique.](create-a-phone-system-auto-attendant-smb.md)</span><span class="sxs-lookup"><span data-stu-id="c6107-233">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

