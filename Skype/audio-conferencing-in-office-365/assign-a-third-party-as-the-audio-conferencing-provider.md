---
title: "Affecter un tiers que le fournisseur de conférence audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Apprenez à configurer un tiers en tant que votre fournisseur de conférence à distance avec Skype pour les entreprises. "
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="0322a-103">Affecter un tiers que le fournisseur de conférence audio</span><span class="sxs-lookup"><span data-stu-id="0322a-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="0322a-104">Un fournisseur de conférence audio fournit le *pont de conférence*.</span><span class="sxs-lookup"><span data-stu-id="0322a-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="0322a-105">Le pont de conférence fournit le numéro de téléphone d’accès à distance, les broches et les ID de conférence pour les réunions qui sont créés.</span><span class="sxs-lookup"><span data-stu-id="0322a-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="0322a-106">Vous devrez affecter un fournisseur de conférence audio pour les personnes qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0322a-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0322a-107">Pour les Teams de Microsoft, un utilisateur ne peut pas utiliser un fournisseur de conférence audio de tiers, ils doivent utiliser la conférence Audio dans Office 365, qui définit le fournisseur de conférence audio à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0322a-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="0322a-108">Étapes à suivre avant de pouvoir affecter un fournisseur de conférence audio de tiers</span><span class="sxs-lookup"><span data-stu-id="0322a-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="0322a-109">En fonction de votre plan d’Office 365, vous devrez acheter des licences de module complémentaire **d’Audio conférence** pour les personnes de votre organisation qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft à l’aide d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="0322a-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="0322a-110">Pour plus d’informations, reportez-vous à la section [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0322a-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="0322a-111">Si vous avez acheté des licences de modules complémentaires **d’Audioconférence** , affectez-les aux personnes de votre organisation qui vont planifier ou de mener des réunions qui utilisent l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="0322a-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="0322a-112">Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="0322a-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0322a-113">Si vous attribuez une licence de **Conférence Audio** à un utilisateur **après** que vous les affecter un fournisseur de conférence audio de tiers, cette personne est automatiquement fixée à utiliser à la place de Microsoft comme leur fournisseur de conférence audio !</span><span class="sxs-lookup"><span data-stu-id="0322a-113">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead!</span></span> <span data-ttu-id="0322a-114">Dans ce cas, vous devez d’abord supprimer Microsoft comme le fournisseur de conférence audio avant de leur affecter un fournisseur de conférence audio de tiers.</span><span class="sxs-lookup"><span data-stu-id="0322a-114">If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="0322a-115">Rechercher un fournisseur de conférence audio de tierce partie dans [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="0322a-115">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span> <span data-ttu-id="0322a-116">Les contacter pour en savoir plus pour vous aider à configurer avec eux.</span><span class="sxs-lookup"><span data-stu-id="0322a-116">Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="0322a-117">Ils présentent :</span><span class="sxs-lookup"><span data-stu-id="0322a-117">They will give you:</span></span>
    
  - <span data-ttu-id="0322a-118">**Numéros d’accès à distance (numéro payant)** et les numéros verts, s’ils sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="0322a-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="0322a-119">**ID de conférence** qui sont utilisés pour chaque personne qui planifie les réunions.</span><span class="sxs-lookup"><span data-stu-id="0322a-119">**Conference IDs** that are used for each person who schedules meetings.</span></span> <span data-ttu-id="0322a-120">Certains ACPs appellent ces codes secrets de conférence.</span><span class="sxs-lookup"><span data-stu-id="0322a-120">Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0322a-121">Si vous avez fait l’initiale définie pour un ACP tiers mais vous devez maintenant apporter des modifications, au bas de la page **Microsoft Bridge** **Cliquez ici pour configurer un fournisseur de conférence audio de tiers**.</span><span class="sxs-lookup"><span data-stu-id="0322a-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="0322a-122">Lorsque vous permettre à une personne pour les conférences audio et les affectez à un fournisseur de conférence audio de tierce partie, les numéros de l’audio et de conférence (codes) sont automatiquement ajoutés à n’importe quel **Nouveau** Skype pour les réunions commerciales en ligne qu’ils créent.</span><span class="sxs-lookup"><span data-stu-id="0322a-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="0322a-123">L’affectation d’un fournisseur de conférence audio de tiers à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="0322a-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="0322a-124">Dans le **Skype pour le centre d’administration Business**, choisissez **les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="0322a-124">In the **Skype for Business admin center**, choose **Users**.</span></span> <span data-ttu-id="0322a-125">Sélectionnez l’utilisateur dans la liste et cliquez sur **Modifier** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0322a-125">Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="0322a-126">Sur la page de propriétés de l’utilisateur, cliquez sur **les conférences Audio** et entrer ces informations :</span><span class="sxs-lookup"><span data-stu-id="0322a-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="0322a-127">**Nom du fournisseur** Dans la liste, sélectionnez le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="0322a-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="0322a-128">**Numéro d’appel payant par défaut** Cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0322a-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="0322a-129">**Par défaut le numéro d’appel gratuit** Ce ne pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0322a-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="0322a-130">**ID de conférence** Ceci est fourni par votre fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="0322a-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="0322a-131">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0322a-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="0322a-132">Envoyer à chaque personne le code PIN que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="0322a-132">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="0322a-133">Le code confidentiel peut être requis pour appeler dans en tant que l’organisateur de la conférence téléphonique ou d’un leader.</span><span class="sxs-lookup"><span data-stu-id="0322a-133">The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0322a-134">Lorsque vous utilisez un fournisseur de conférence audio de tierce partie, il n’est pas un moyen de vous voir ou de définir des broches pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="0322a-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="0322a-135">Comment affecter un fournisseur de conférence audio de tiers à plusieurs personnes en même temps</span><span class="sxs-lookup"><span data-stu-id="0322a-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="0322a-136">Dans le **Skype pour le centre d’administration Business**, choisissez **audioconférence** > **pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0322a-136">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="0322a-137">En bas de la page, cliquez sur le lien **que vous souhaitez configurer un fournisseur de conférence audio de tiers à la place, cliquez ici**.</span><span class="sxs-lookup"><span data-stu-id="0322a-137">At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0322a-138">Si vous avez fait l’initiale définie pour un ACP tiers mais vous devez maintenant apporter des modifications, au bas de la page de **Pont de Microsoft** , **Cliquez ici pour configurer un fournisseur de conférence audio de tiers**.</span><span class="sxs-lookup"><span data-stu-id="0322a-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="0322a-139">Dans la page **configurer un fournisseur de conférence audio tiers** , sous **Importer et exporter des utilisateurs**, cliquez sur **Assistant Exportation**et puis suivez les étapes de l' **Assistant Exportation des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="0322a-139">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**.</span></span> <span data-ttu-id="0322a-140">Lorsque vous avez terminé, vous aurez un fichier qui liste les personnes que vous souhaitez configurer pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="0322a-140">When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="0322a-141">Envoyer le fichier que vous avez créé à votre fournisseur de conférence audio de tiers.</span><span class="sxs-lookup"><span data-stu-id="0322a-141">Send the file you created to your third-party audio conferencing provider.</span></span> <span data-ttu-id="0322a-142">Ils seront ajouter les informations de conférence audio pour les personnes figurant dans le fichier et renvoie ensuite le fichier.</span><span class="sxs-lookup"><span data-stu-id="0322a-142">They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="0322a-143">Vérifiez que le fichier retourné comporte les bonnes informations.</span><span class="sxs-lookup"><span data-stu-id="0322a-143">Double-check that the returned file has the right information in it.</span></span> <span data-ttu-id="0322a-144">Nous avons entendu des instances où tous les utilisateurs non répertoriés dans le fichier obtenu les bonnes informations.</span><span class="sxs-lookup"><span data-stu-id="0322a-144">We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="0322a-145">Sur la **page Configurer une conférence audio du tiers fournisseur**, sous **Importer et exporter des utilisateurs**, cliquez sur **Assistant Importation**, puis suivez les étapes de l' **Assistant d’importation d’utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="0322a-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="0322a-146">Envoyer à chaque personne le code PIN que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="0322a-146">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="0322a-147">Le code confidentiel peut être requis pour appeler dans en tant que l’organisateur de la conférence téléphonique, ou le leader.</span><span class="sxs-lookup"><span data-stu-id="0322a-147">The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0322a-148">Lorsque vous utilisez un fournisseur de conférence audio de tierce partie, il n’est pas un moyen de vous voir ou de définir des broches pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="0322a-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="0322a-149">Quand utiliser un fournisseur de conférence audio de tiers</span><span class="sxs-lookup"><span data-stu-id="0322a-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="0322a-150">Si vous êtes dans un pays ou une région où une conférence Audio dans Office 365 n’est pas disponible, la qualité de service n’est pas idéale en raison de son emplacement ou vous disposez d’un contrat existant avec un fournisseur de conférence audio de tiers, nous vous recommandons d’utiliser un audio tiers fournisseur de la conférence.</span><span class="sxs-lookup"><span data-stu-id="0322a-150">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider.</span></span> <span data-ttu-id="0322a-151">Dans le cas contraire, il est recommandé que votre fournisseur de conférence audio à l’aide de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0322a-151">Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="0322a-152">Automatiser l’affectation du fournisseur de conférence audio de tiers à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0322a-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="0322a-153">Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser l’applet de commande [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) .</span><span class="sxs-lookup"><span data-stu-id="0322a-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0322a-154">Pour modifier le fournisseur audio de Microsoft, à un fournisseur de conférence audio de tiers, vous devez supprimer Microsoft comme le fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="0322a-154">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="0322a-155">Pour ce faire, utilisez l’applet de commande [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .</span><span class="sxs-lookup"><span data-stu-id="0322a-155">To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="0322a-156">Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="0322a-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="0322a-157">Qu’est-ce que je dois savoir d’autre ?</span><span class="sxs-lookup"><span data-stu-id="0322a-157">What else do I need to know?</span></span>

<span data-ttu-id="0322a-158">Une personne de votre organisation ne pouvez utiliser qu’un seul fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="0322a-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="0322a-159">Pour modifier le fournisseur de conférence audio d’une personne à Microsoft, voir [déplacement du fournisseur de conférence audio d’un utilisateur à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) ou [Affecter de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0322a-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0322a-160">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0322a-160">Related Topics</span></span>

[<span data-ttu-id="0322a-161">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="0322a-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="0322a-162">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0322a-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

