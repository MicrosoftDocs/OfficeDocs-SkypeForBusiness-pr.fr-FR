---
title: "Affecter un tiers que le fournisseur de conférence audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: 5ae513c754764933f08370139eeb557f0fb39211
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="4c28e-103">Affecter un tiers que le fournisseur de conférence audio</span><span class="sxs-lookup"><span data-stu-id="4c28e-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="4c28e-104">Un fournisseur de conférence audio fournit le *pont de conférence*.</span><span class="sxs-lookup"><span data-stu-id="4c28e-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="4c28e-105">Le pont de conférence fournit le numéro de téléphone d'accès, les codes PIN et le code de la conférence pour les réunions qui sont créées.</span><span class="sxs-lookup"><span data-stu-id="4c28e-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="4c28e-106">Vous devrez affecter un fournisseur de conférence audio pour les personnes qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c28e-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c28e-107">Pour les Teams de Microsoft, un utilisateur ne peut pas utiliser un fournisseur de conférence audio de tiers, ils doivent utiliser la conférence Audio dans Office 365, qui définit le fournisseur de conférence audio à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c28e-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="4c28e-108">Étapes à suivre avant de pouvoir affecter un fournisseur de conférence audio de tiers</span><span class="sxs-lookup"><span data-stu-id="4c28e-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="4c28e-109">En fonction de votre plan d’Office 365, vous devrez acheter des licences de module complémentaire **d’Audio conférence** pour les personnes de votre organisation qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft à l’aide d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="4c28e-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="4c28e-110">Pour plus d’informations, reportez-vous à la section [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4c28e-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="4c28e-111">Si vous avez acheté des licences de modules complémentaires **d’Audioconférence** , affectez-les aux personnes de votre organisation qui vont planifier ou de mener des réunions qui utilisent l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="4c28e-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="4c28e-112">Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4c28e-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c28e-113">Si vous attribuez une licence de **Conférence Audio** à un utilisateur **après** que vous les affecter un fournisseur de conférence audio de tiers, cette personne est automatiquement fixée à utiliser à la place de Microsoft comme leur fournisseur de conférence audio !</span><span class="sxs-lookup"><span data-stu-id="4c28e-113">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead!</span></span> <span data-ttu-id="4c28e-114">Dans ce cas, vous devez d’abord supprimer Microsoft comme le fournisseur de conférence audio avant de leur affecter un fournisseur de conférence audio de tiers.</span><span class="sxs-lookup"><span data-stu-id="4c28e-114">If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="4c28e-115">Rechercher un fournisseur de conférence audio de tierce partie dans [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="4c28e-115">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span> <span data-ttu-id="4c28e-116">Contactez les membres de ce réseau et découvrez comment configurer le service avec eux.</span><span class="sxs-lookup"><span data-stu-id="4c28e-116">Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="4c28e-117">Ils vous donneront :</span><span class="sxs-lookup"><span data-stu-id="4c28e-117">They will give you:</span></span>
    
  - <span data-ttu-id="4c28e-118">**Numéros d’accès à distance (numéro payant)** et les numéros verts, s’ils sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="4c28e-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="4c28e-p106">les **codes de la conférence** utilisés pour chaque personne qui planifie les réunions (certains fournisseurs d'audioconférences les appellent « mots de passe » de conférence).</span><span class="sxs-lookup"><span data-stu-id="4c28e-p106">**Conference IDs** that are used for each person who schedules meetings. Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c28e-121">Si vous avez fait l’initiale définie pour un ACP tiers mais vous devez maintenant apporter des modifications, au bas de la page **Microsoft Bridge** **Cliquez ici pour configurer un fournisseur de conférence audio de tiers**.</span><span class="sxs-lookup"><span data-stu-id="4c28e-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="4c28e-122">Lorsque vous permettre à une personne pour les conférences audio et les affectez à un fournisseur de conférence audio de tierce partie, les numéros de l’audio et de conférence (codes) sont automatiquement ajoutés à n’importe quel **Nouveau** Skype pour les réunions commerciales en ligne qu’ils créent.</span><span class="sxs-lookup"><span data-stu-id="4c28e-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="4c28e-123">L’affectation d’un fournisseur de conférence audio de tiers à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="4c28e-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="4c28e-p107">Dans le **Centre d'administration Skype Entreprise**, sélectionnez **Utilisateurs**. Sélectionnez l'utilisateur dans la liste et cliquez sur **Modifier** dans le volet d'actions.</span><span class="sxs-lookup"><span data-stu-id="4c28e-p107">In the **Skype for Business admin center**, choose **Users**. Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="4c28e-126">Sur la page de propriétés de l’utilisateur, cliquez sur **les conférences Audio** et entrer ces informations :</span><span class="sxs-lookup"><span data-stu-id="4c28e-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="4c28e-127">**Nom du fournisseur** Dans la liste, sélectionnez le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="4c28e-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="4c28e-128">**Numéro d’appel payant par défaut** Cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4c28e-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="4c28e-129">**Par défaut le numéro d’appel gratuit** Ce ne pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4c28e-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="4c28e-130">**ID de conférence** Ceci est fourni par votre fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="4c28e-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="4c28e-131">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4c28e-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="4c28e-132">Envoyer à chaque personne le code PIN que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="4c28e-132">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="4c28e-133">Le code confidentiel peut être requis pour appeler dans en tant que l’organisateur de la conférence téléphonique ou d’un leader.</span><span class="sxs-lookup"><span data-stu-id="4c28e-133">The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c28e-134">Lorsque vous utilisez un fournisseur de conférence audio de tierce partie, il n’est pas un moyen de vous voir ou de définir des broches pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="4c28e-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="4c28e-135">Comment affecter un fournisseur de conférence audio de tiers à plusieurs personnes en même temps</span><span class="sxs-lookup"><span data-stu-id="4c28e-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="4c28e-136">Dans le **Skype pour le centre d’administration Business**, choisissez **audioconférence** > **pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4c28e-136">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="4c28e-137">En bas de la page, cliquez sur le lien **que vous souhaitez configurer un fournisseur de conférence audio de tiers à la place, cliquez ici**.</span><span class="sxs-lookup"><span data-stu-id="4c28e-137">At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c28e-138">Si vous avez fait l’initiale définie pour un ACP tiers mais vous devez maintenant apporter des modifications, au bas de la page de **Pont de Microsoft** , **Cliquez ici pour configurer un fournisseur de conférence audio de tiers**.</span><span class="sxs-lookup"><span data-stu-id="4c28e-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="4c28e-139">Dans la page **configurer un fournisseur de conférence audio tiers** , sous **Importer et exporter des utilisateurs**, cliquez sur **Assistant Exportation**et puis suivez les étapes de l' **Assistant Exportation des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4c28e-139">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**.</span></span> <span data-ttu-id="4c28e-140">Lorsque vous avez terminé, vous aurez un fichier qui liste les personnes que vous souhaitez configurer pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="4c28e-140">When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="4c28e-141">Envoyer le fichier que vous avez créé à votre fournisseur de conférence audio de tiers.</span><span class="sxs-lookup"><span data-stu-id="4c28e-141">Send the file you created to your third-party audio conferencing provider.</span></span> <span data-ttu-id="4c28e-142">Ils seront ajouter les informations de conférence audio pour les personnes figurant dans le fichier et renvoie ensuite le fichier.</span><span class="sxs-lookup"><span data-stu-id="4c28e-142">They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="4c28e-p112">Vérifiez que le fichier qui vous a été renvoyé contient les bonnes informations. Nous avons été informés de cas où les renseignements avaient été mal transmis aux personnes répertoriées.</span><span class="sxs-lookup"><span data-stu-id="4c28e-p112">Double-check that the returned file has the right information in it. We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="4c28e-145">Dans la page **Configurer un fournisseur de services d'audioconférence tiers**, sous **Importer et exporter des utilisateurs**, cliquez **Assistant Importation**, puis suivez les étapes de l' **Assistant Importation d'utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="4c28e-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="4c28e-146">Envoyer à chaque personne le code PIN que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="4c28e-146">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="4c28e-147">Le code confidentiel peut être obligatoire pour effectuer l'appel en tant qu'organisateur ou leader de la téléconférence.</span><span class="sxs-lookup"><span data-stu-id="4c28e-147">The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c28e-148">Lorsque vous utilisez un fournisseur de conférence audio de tierce partie, il n’est pas un moyen de vous voir ou de définir des broches pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="4c28e-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="4c28e-149">Quand utiliser un fournisseur de conférence audio de tiers</span><span class="sxs-lookup"><span data-stu-id="4c28e-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="4c28e-150">Si vous êtes dans un pays ou une région où une conférence Audio dans Office 365 n’est pas disponible, la qualité de service n’est pas idéale en raison de son emplacement ou vous disposez d’un contrat existant avec un fournisseur de conférence audio de tiers, nous vous recommandons d’utiliser un audio tiers fournisseur de la conférence.</span><span class="sxs-lookup"><span data-stu-id="4c28e-150">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider.</span></span> <span data-ttu-id="4c28e-151">Dans le cas contraire, il est recommandé que votre fournisseur de conférence audio à l’aide de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c28e-151">Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="4c28e-152">Affecter automatiquement le fournisseur tiers d'audioconférences à l'aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c28e-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="4c28e-153">Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).</span><span class="sxs-lookup"><span data-stu-id="4c28e-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c28e-154">Pour modifier le fournisseur audio de Microsoft, à un fournisseur de conférence audio de tiers, vous devez supprimer Microsoft comme le fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="4c28e-154">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="4c28e-155">Pour ce faire, utilisez la cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ).</span><span class="sxs-lookup"><span data-stu-id="4c28e-155">To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="4c28e-156">Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="4c28e-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="4c28e-157">Que dois-je savoir également ?</span><span class="sxs-lookup"><span data-stu-id="4c28e-157">What else do I need to know?</span></span>

<span data-ttu-id="4c28e-158">Une personne de votre organisation ne pouvez utiliser qu’un seul fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="4c28e-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="4c28e-159">Pour modifier le fournisseur de conférence audio d’une personne à Microsoft, voir [déplacement du fournisseur de conférence audio d’un utilisateur à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) ou [Affecter de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4c28e-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4c28e-160">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4c28e-160">Related Topics</span></span>

[<span data-ttu-id="4c28e-161">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="4c28e-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="4c28e-162">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4c28e-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

