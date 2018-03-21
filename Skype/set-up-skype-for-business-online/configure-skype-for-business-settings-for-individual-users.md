---
title: "Administrateurs  Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: fbbd184af5eb39d78d221b9e5654322b2b6609ea
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="6058a-103">Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="6058a-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="6058a-104">Cet article explique comment les administrateurs configurent Skype Entreprise pour un petit nombre d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6058a-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="6058a-105">Pour effectuer ces opérations en bloc, nous avons inclus des liens vers les applets de commande Windows PowerShell que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="6058a-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="6058a-106">Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :</span><span class="sxs-lookup"><span data-stu-id="6058a-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="6058a-107">[Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels](allow-users-to-contact-external-skype-for-business-users.md): vous pouvez permettent à votre organisation d’utiliser avancée Skype pour les fonctionnalités d’entreprise (partage de bureaux, recherchez qui est en ligne, etc.) pour communiquer avec des personnes spécifiques approuvés business (fédérées).</span><span class="sxs-lookup"><span data-stu-id="6058a-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="6058a-108">L’article explique également comment bloquer les communications avec des domaines spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6058a-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="6058a-109">[Laisser les Skype pour les utilisateurs professionnels ajouter les contacts Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="6058a-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="6058a-110">Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.</span><span class="sxs-lookup"><span data-stu-id="6058a-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="6058a-111">Configurer les paramètres généraux pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6058a-111">Configure general settings for one user</span></span>
<span data-ttu-id="6058a-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="6058a-112"></span></span>

<span data-ttu-id="6058a-113">Vous devez disposer [des autorisations d’administration](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="6058a-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="6058a-114">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="6058a-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="6058a-115">Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="6058a-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="6058a-116">Sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6058a-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="6058a-118">Sélectionnez les utilisateurs que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="6058a-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="6058a-119">Dans le volet de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6058a-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="6058a-121">Dans la page d'options **Général**, cochez ou décochez les cases correspondant aux fonctionnalités que vous voulez modifier, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6058a-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="6058a-122">**Option**</span><span class="sxs-lookup"><span data-stu-id="6058a-122">**Option**</span></span>|<span data-ttu-id="6058a-123">**Détails**</span><span class="sxs-lookup"><span data-stu-id="6058a-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6058a-124">Appels audio et vidéo HD</span><span class="sxs-lookup"><span data-stu-id="6058a-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="6058a-125">Autorisez cette personne à enregistrer les réunions audio et les réunions audio et vidéo ou ne lʼautorisez pas à planifier des réunions (aucune).</span><span class="sxs-lookup"><span data-stu-id="6058a-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="6058a-126">Enregistrer les conversations et les réunions</span><span class="sxs-lookup"><span data-stu-id="6058a-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="6058a-127">Sélectionnez les éléments que cette personne est autorisée à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6058a-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="6058a-128">Cette option n’est pas disponible avec Skype pour Business Basic.</span><span class="sxs-lookup"><span data-stu-id="6058a-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="6058a-129">À des fins de conformité, désactivez les fonctions non archivées.</span><span class="sxs-lookup"><span data-stu-id="6058a-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="6058a-130">Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement.</span><span class="sxs-lookup"><span data-stu-id="6058a-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="6058a-131">La sélection de cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous avez une [Place maintenez](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) paramétré dans le centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="6058a-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="6058a-132">Elle désactive les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6058a-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="6058a-133">transfert de fichiers avec la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="6058a-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="6058a-134">Pages OneNote partagées</span><span class="sxs-lookup"><span data-stu-id="6058a-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="6058a-135">Annotations PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6058a-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="6058a-136">Pour configurer ces paramètres en vrac, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6058a-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="6058a-137">Reportez-vous à la section [Gestion des stratégies dans Skype pour l’activité en ligne](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6058a-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="6058a-138">Bloquer les communications externes</span><span class="sxs-lookup"><span data-stu-id="6058a-138">Block external communications</span></span>
<span data-ttu-id="6058a-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="6058a-139"></span></span>

<span data-ttu-id="6058a-140">Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6058a-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="6058a-141">Choisissez **les utilisateurs**et sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="6058a-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="6058a-142">Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :</span><span class="sxs-lookup"><span data-stu-id="6058a-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="6058a-143">**Utilisateurs Skype Entreprise externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des utilisateurs Skype Entreprise dans des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="6058a-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="6058a-144">**Utilisateurs Skype externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des personnes qui utilisent lʼapplication Skype gratuite.</span><span class="sxs-lookup"><span data-stu-id="6058a-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="6058a-145">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6058a-145">Click **Save**.</span></span>
    
<span data-ttu-id="6058a-146">Pour configurer ces paramètres en vrac, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6058a-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="6058a-147">Reportez-vous à la section [Gestion des communications dans Skype pour entreprise en ligne avec des utilisateurs et des organisations à l’extérieur](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6058a-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="6058a-148">Modifier les paramètres de conférence audio d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6058a-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="6058a-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="6058a-149"></span></span>

1. <span data-ttu-id="6058a-150">Choisissez **les utilisateurs**, sélectionnez l’utilisateur dont vous voulez pour modifier, les paramètres de conférence audio, puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="6058a-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="6058a-151">Choisissez **audioconférence**Sélectionnez votre fournisseur de conférence audio, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6058a-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="6058a-152">**Configuration de l'audioconférence**</span><span class="sxs-lookup"><span data-stu-id="6058a-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="6058a-153">**Description**</span><span class="sxs-lookup"><span data-stu-id="6058a-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6058a-154">**Nom du fournisseur**</span><span class="sxs-lookup"><span data-stu-id="6058a-154">**Provider name**</span></span> <br/> |<span data-ttu-id="6058a-155">Choisissez votre fournisseur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6058a-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="6058a-156">**Numéro payant** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="6058a-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="6058a-157">Pour un tiers ACP, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6058a-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="6058a-158">Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, il s’agit de nombres qui sont définies sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6058a-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="6058a-159">Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion commerciale et Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6058a-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="6058a-160">**Numéro gratuit**</span><span class="sxs-lookup"><span data-stu-id="6058a-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="6058a-161">Pour un tiers ACP, ces numéros de téléphone sont ceux que vous avez reçu à partir du fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6058a-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="6058a-162">Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, il s’agit de nombres qui sont définies sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6058a-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="6058a-163">Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion commerciale et Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6058a-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="6058a-164">**ID de conférence et code PIN** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="6058a-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="6058a-165">Le code PIN de participant, ou d’une conférence, utilisé pour participer à des conférences qui sont prévues par cet utilisateur et sont fournis à partir d’un fournisseur de conférence audio de tiers.</span><span class="sxs-lookup"><span data-stu-id="6058a-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="6058a-166">Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, ce ne sera pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="6058a-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="6058a-167">Pour configurer ces paramètres en vrac, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6058a-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="6058a-168">Voir [invite les inclure sur des numéros de téléphone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="6058a-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="6058a-169">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6058a-169">Related topics</span></span> 

[<span data-ttu-id="6058a-170">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6058a-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6058a-171">Licences de compléments pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6058a-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
