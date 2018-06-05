---
title: Administrateurs  Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels
ms.author: tonysmit
author: tonysmit
manager: serdars
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
ms.openlocfilehash: f9b6db08c87e46326d6e9de7c82d6e1c89cffce0
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500818"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="f97a4-103">Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="f97a4-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="f97a4-104">Cet article explique comment les administrateurs configurent Skype Entreprise pour un petit nombre d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f97a4-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="f97a4-105">Pour effectuer ces étapes en bloc, nous avons inclus des liens vers les applets de commande Windows PowerShell que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="f97a4-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="f97a4-106">Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :</span><span class="sxs-lookup"><span data-stu-id="f97a4-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="f97a4-107">[Autoriser les utilisateurs à contacts Skype externe pour les utilisateurs professionnels](allow-users-to-contact-external-skype-for-business-users.md): vous pouvez permettent à votre organisation d’utiliser avancée Skype pour les fonctionnalités d’entreprise (partage de postes de travail, recherchez qui est en ligne, etc.) pour communiquer avec des personnes dans une spécifique (fédérés) business approuvés.</span><span class="sxs-lookup"><span data-stu-id="f97a4-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="f97a4-108">Cet article explique comment empêcher la communication avec des domaines spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f97a4-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="f97a4-109">[Laisser les Skype pour les utilisateurs professionnels Ajouter contacts Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="f97a4-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="f97a4-110">Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.</span><span class="sxs-lookup"><span data-stu-id="f97a4-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="f97a4-111">Configurer les paramètres généraux pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f97a4-111">Configure general settings for one user</span></span>
<span data-ttu-id="f97a4-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="f97a4-112"></span></span>

<span data-ttu-id="f97a4-113">Vous devez disposer des [autorisations d’administrateur](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="f97a4-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="f97a4-114">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="f97a4-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="f97a4-115">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="f97a4-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f97a4-116">Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="f97a4-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f97a4-117">Sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f97a4-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="f97a4-119">Sélectionnez les utilisateurs que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="f97a4-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="f97a4-120">Dans le volet de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f97a4-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="f97a4-122">Dans la page d'options **Général**, cochez ou décochez les cases correspondant aux fonctionnalités que vous voulez modifier, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f97a4-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="f97a4-123">**Option**</span><span class="sxs-lookup"><span data-stu-id="f97a4-123">**Option**</span></span>|<span data-ttu-id="f97a4-124">**Détails**</span><span class="sxs-lookup"><span data-stu-id="f97a4-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f97a4-125">Appels audio et vidéo HD</span><span class="sxs-lookup"><span data-stu-id="f97a4-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="f97a4-126">Autorisez cette personne à enregistrer les réunions audio et les réunions audio et vidéo ou ne lʼautorisez pas à planifier des réunions (aucune).</span><span class="sxs-lookup"><span data-stu-id="f97a4-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="f97a4-127">Enregistrer les conversations et les réunions</span><span class="sxs-lookup"><span data-stu-id="f97a4-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="f97a4-128">Sélectionnez les éléments que cette personne est autorisée à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f97a4-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="f97a4-129">Cette option n’est pas disponible avec Skype pour Business Basic.</span><span class="sxs-lookup"><span data-stu-id="f97a4-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="f97a4-130">À des fins de conformité, désactivez les fonctions non archivées.</span><span class="sxs-lookup"><span data-stu-id="f97a4-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="f97a4-131">Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement.</span><span class="sxs-lookup"><span data-stu-id="f97a4-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="f97a4-132">Cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous avez un [Blocage sur Place](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configuré le centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="f97a4-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="f97a4-133">Elle désactive les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f97a4-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="f97a4-134">transfert de fichiers avec la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="f97a4-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="f97a4-135">Pages OneNote partagées</span><span class="sxs-lookup"><span data-stu-id="f97a4-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="f97a4-136">Annotations PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f97a4-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="f97a4-137">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f97a4-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="f97a4-138">Voir [Gestion des stratégies dans Skype pour Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f97a4-138">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="f97a4-139">Bloquer les communications externes</span><span class="sxs-lookup"><span data-stu-id="f97a4-139">Block external communications</span></span>
<span data-ttu-id="f97a4-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="f97a4-140"></span></span>

<span data-ttu-id="f97a4-141">Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f97a4-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="f97a4-142">Sélectionnez **les utilisateurs**, sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres, puis **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="f97a4-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="f97a4-143">Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :</span><span class="sxs-lookup"><span data-stu-id="f97a4-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="f97a4-144">**Utilisateurs Skype Entreprise externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des utilisateurs Skype Entreprise dans des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="f97a4-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="f97a4-145">**Utilisateurs Skype externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des personnes qui utilisent lʼapplication Skype gratuite.</span><span class="sxs-lookup"><span data-stu-id="f97a4-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="f97a4-146">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f97a4-146">Click **Save**.</span></span>
    
<span data-ttu-id="f97a4-147">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f97a4-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="f97a4-148">Voir [Gestion des communications dans Skype pour Business Online avec des organisations et des utilisateurs externes](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f97a4-148">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="f97a4-149">Modifier les paramètres de conférence audio pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f97a4-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="f97a4-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="f97a4-150"></span></span>

1. <span data-ttu-id="f97a4-151">**Les utilisateurs**, sélectionnez l’utilisateur dont vous voulez pour modifier, les paramètres de conférence audio, puis choisissez **Modifier** ![modifier](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="f97a4-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="f97a4-152">Choisissez **l’audioconférence**, sélectionnez votre fournisseur de services d’audioconférence, tapez ou modifier les informations demandées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f97a4-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="f97a4-153">**Configuration de l'audioconférence**</span><span class="sxs-lookup"><span data-stu-id="f97a4-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="f97a4-154">**Description**</span><span class="sxs-lookup"><span data-stu-id="f97a4-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f97a4-155">**Nom du fournisseur**</span><span class="sxs-lookup"><span data-stu-id="f97a4-155">**Provider name**</span></span> <br/> |<span data-ttu-id="f97a4-156">Choisissez votre fournisseur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f97a4-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="f97a4-157">**Numéro payant** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="f97a4-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="f97a4-158">Pour un fournisseur tiers, ces numéros de téléphone sont celles que vous avez reçus du fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="f97a4-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="f97a4-159">Si l’utilisateur est à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence, il sera numéros qui sont définies sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="f97a4-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="f97a4-160">Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f97a4-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="f97a4-161">**Numéro gratuit**</span><span class="sxs-lookup"><span data-stu-id="f97a4-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="f97a4-162">Pour un fournisseur tiers, ces numéros de téléphone sont celles que vous avez reçus du fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="f97a4-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="f97a4-163">Si l’utilisateur est à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence, il sera numéros qui sont définies sur le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="f97a4-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="f97a4-164">Mettre en forme les numéros que vous le souhaitez les voir apparaître dans Skype pour les demandes de réunion Business et Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f97a4-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="f97a4-165">**Code confidentiel et ID de conférence** (requis)</span><span class="sxs-lookup"><span data-stu-id="f97a4-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="f97a4-166">Le code participant code confidentiel, ou une conférence, utilisé pour participer à des réunions sont planifiées par cet utilisateur et sont fournies à partir d’un fournisseur de services d’audioconférence tiers.</span><span class="sxs-lookup"><span data-stu-id="f97a4-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="f97a4-167">Si l’utilisateur est à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence, il sera requis.</span><span class="sxs-lookup"><span data-stu-id="f97a4-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="f97a4-168">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f97a4-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="f97a4-169">Voir [l’invite inclus sur les numéros de téléphone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="f97a4-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="f97a4-170">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f97a4-170">Related topics</span></span> 

[<span data-ttu-id="f97a4-171">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f97a4-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f97a4-172">Licences de compléments pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f97a4-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 