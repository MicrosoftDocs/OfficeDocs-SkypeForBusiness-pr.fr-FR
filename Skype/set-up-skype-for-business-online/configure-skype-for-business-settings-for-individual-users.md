---
title: "Administrateurs de configurer de Skype pour les paramètres d’entreprise pour les utilisateurs individuels"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: "Apprenez à modifier la Skype pour les paramètres d’entreprise pour les utilisateurs individuels tels que : conférence Audio et vidéo, des réunions et enregistrement des appels. "
ms.openlocfilehash: 0623c6dd913316584bd38e4076317c050c4a2812
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="c6d7f-103">Administrateurs : Configurer Skype pour les paramètres d’entreprise pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="c6d7f-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="c6d7f-104">Cet article explique comment les administrateurs configurer Skype pour l’entreprise pour un petit nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="c6d7f-105">Pour effectuer ces opérations en bloc, nous avons inclus des liens vers les applets de commande Windows PowerShell que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="c6d7f-106">Pour autoriser (ou bloquer) tout le monde dans votre entreprise pour communiquer avec des utilisateurs externes, voir :</span><span class="sxs-lookup"><span data-stu-id="c6d7f-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="c6d7f-107">[Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels](allow-users-to-contact-external-skype-for-business-users.md): vous pouvez permettent à votre organisation d’utiliser avancée Skype pour les fonctionnalités d’entreprise (partage de bureaux, recherchez qui est en ligne, etc.) pour communiquer avec des personnes spécifiques approuvés business (fédérées).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="c6d7f-108">L’article explique également comment bloquer les communications avec des domaines spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="c6d7f-109">[Laisser les Skype pour les utilisateurs professionnels ajouter les contacts Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="c6d7f-110">Vous pouvez laisser à votre organisation d’utiliser Skype pour les entreprises à rechercher et de messagerie instantanée utilisateurs de Skype, l’application gratuite.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="c6d7f-111">Configurer les paramètres généraux pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c6d7f-111">Configure general settings for one user</span></span>
<span data-ttu-id="c6d7f-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="c6d7f-112"></span></span>

<span data-ttu-id="c6d7f-113">Vous devez disposer [des autorisations d’administration](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="c6d7f-114">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c6d7f-115">Choisissez le **Centre d’administration** > **Skype pour les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c6d7f-116">Choisissez **les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-116">Choose **Users**.</span></span>
    
    ![Dans le Skype pour le centre d’administration Business, choisissez les utilisateurs.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="c6d7f-118">Choisir les utilisateurs auxquels vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="c6d7f-119">Dans le volet droit, cliquez **sur Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-119">In the right panel, choose **Edit**.</span></span>
    
    ![Cliquez sur l’icône Modifier.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="c6d7f-121">Dans la page options **générales** , sélectionnez ou désactivez la case à cocher près des fonctionnalités que vous souhaitez modifier et puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="c6d7f-122">**Option**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-122">**Option**</span></span>|<span data-ttu-id="c6d7f-123">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6d7f-124">Audio et vidéo HD</span><span class="sxs-lookup"><span data-stu-id="c6d7f-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="c6d7f-125">Autoriser cette personne à des réunions audio enregistrements, réunions audio et vidéo, ou ne leur permettre de planifier les meeetings (aucun).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="c6d7f-126">Les réunions et les conversations de l’enregistrements</span><span class="sxs-lookup"><span data-stu-id="c6d7f-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="c6d7f-127">Choisissez ce que cette personne est autorisée à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="c6d7f-128">Cette option n’est pas disponible avec Skype pour Business Basic.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="c6d7f-129">Pour la conformité, désactivez les fonctionnalités de non archivées</span><span class="sxs-lookup"><span data-stu-id="c6d7f-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="c6d7f-130">Choisissez cette option si vous êtes tenu de conserver des informations stockées par voie électronique.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="c6d7f-131">La sélection de cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous avez une [Place maintenez](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) paramétré dans le centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="c6d7f-132">Il désactive les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6d7f-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="c6d7f-133">transfert de fichier avec la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="c6d7f-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="c6d7f-134">Pages OneNote partagées</span><span class="sxs-lookup"><span data-stu-id="c6d7f-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="c6d7f-135">Annotations PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c6d7f-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="c6d7f-136">Pour configurer ces paramètres en vrac, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="c6d7f-137">Reportez-vous à la section [Gestion des stratégies dans Skype pour l’activité en ligne](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="c6d7f-138">Bloquer les communications externes</span><span class="sxs-lookup"><span data-stu-id="c6d7f-138">Block external communications</span></span>
<span data-ttu-id="c6d7f-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="c6d7f-139"></span></span>

<span data-ttu-id="c6d7f-140">Après vous [permettent de Skype pour les utilisateurs professionnels ajouter les contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre société, vous pouvez bloquer de façon sélective les communications externes pour des utilisateurs spécifiques à l’aide de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="c6d7f-141">Choisissez **les utilisateurs**et sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="c6d7f-142">Choisissez la **communication externe**et puis désactivez les options appropriées :</span><span class="sxs-lookup"><span data-stu-id="c6d7f-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="c6d7f-143">**Skype externe pour les utilisateurs professionnels**: désactivez cette case si vous ne souhaitez pas que l’utilisateur soit en mesure de communiquer avec Skype pour les utilisateurs de domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="c6d7f-144">**Les utilisateurs de Skype externe**: désactivez cette case si vous ne souhaitez pas que l’utilisateur soit en mesure de communiquer avec des personnes qui sont à l’aide de l’application freeSkype.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="c6d7f-145">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-145">Click **Save**.</span></span>
    
<span data-ttu-id="c6d7f-146">Pour configurer ces paramètres en vrac, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="c6d7f-147">Reportez-vous à la section [Gestion des communications dans Skype pour entreprise en ligne avec des utilisateurs et des organisations à l’extérieur](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="c6d7f-148">Modifier les paramètres de conférence audio d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c6d7f-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="c6d7f-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="c6d7f-149"></span></span>

1. <span data-ttu-id="c6d7f-150">Choisissez **les utilisateurs**, sélectionnez l’utilisateur dont vous voulez pour modifier, les paramètres de conférence audio, puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="c6d7f-151">Choisissez **audioconférence**Sélectionnez votre fournisseur de conférence audio, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="c6d7f-152">**Configuration de l'audioconférence**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="c6d7f-153">**Description**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6d7f-154">**Nom du fournisseur**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-154">**Provider name**</span></span> <br/> |<span data-ttu-id="c6d7f-155">Choisissez votre fournisseur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="c6d7f-156">**Numéro payant** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="c6d7f-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="c6d7f-157">Pour un tiers ACP, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="c6d7f-158">Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, il s’agit de nombres qui sont définies sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="c6d7f-159">Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion commerciale et Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="c6d7f-160">**Numéro gratuit**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="c6d7f-161">Pour un tiers ACP, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="c6d7f-162">Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, il s’agit de nombres qui sont définies sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="c6d7f-163">Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion commerciale et Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="c6d7f-164">**ID de conférence et code PIN** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="c6d7f-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="c6d7f-165">Le code PIN de participant, ou d’une conférence, utilisé pour participer à des conférences qui sont prévues par cet utilisateur et sont fournis à partir d’un fournisseur de conférence audio de tiers.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="c6d7f-166">Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, ce ne sera pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="c6d7f-167">Pour configurer ces paramètres en vrac, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="c6d7f-168">Voir [invite les inclure sur des numéros de téléphone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="c6d7f-169">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c6d7f-169">Related topics</span></span> 

[<span data-ttu-id="c6d7f-170">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c6d7f-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

<span data-ttu-id="c6d7f-171">Pour en savoir plus, reportez-vous à la rubrique [Conférence rendez-vous dans Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-171">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
