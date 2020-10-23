---
title: Administrateurs  Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 546e693dd1fb6e9becf7119c35d7b00875eda99a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739172"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="a3aa5-103">Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="a3aa5-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3aa5-104">Le centre d’administration Microsoft teams a remplacé le centre d’administration Skype entreprise (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="a3aa5-105">Tous les paramètres de gestion de Skype entreprise se trouvent désormais dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="a3aa5-106">Pour en savoir plus, voir [gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="a3aa5-107">Cet article explique comment les administrateurs configurent Skype Entreprise pour un petit nombre d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-107">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="a3aa5-108">Pour effectuer ces étapes en bloc, nous avons inclus des liens vers les cmdlets Windows PowerShell que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-108">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="a3aa5-109">Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :</span><span class="sxs-lookup"><span data-stu-id="a3aa5-109">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="a3aa5-110">[Autorisez les utilisateurs à contacter des utilisateurs Skype entreprise externes](allow-users-to-contact-external-skype-for-business-users.md): vous pouvez faire en sorte que votre organisation utilise les fonctionnalités avancées de Skype entreprise (partage de bureaux, recherchez qui est en ligne, etc.).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-110">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="a3aa5-111">Cet article explique également comment bloquer des communications avec des domaines spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-111">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="a3aa5-112">[Autorisez les utilisateurs Skype entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-112">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="a3aa5-113">Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-113">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="a3aa5-114">Configurer les paramètres généraux pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a3aa5-114">Configure general settings for one user</span></span>
<span data-ttu-id="a3aa5-115"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="a3aa5-115"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="a3aa5-116">Vous devez disposer des [autorisations d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-116">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="a3aa5-117">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="a3aa5-117">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a3aa5-118">Connectez-vous à l’aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-118">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="a3aa5-119">Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-119">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a3aa5-120">Sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-120">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="a3aa5-122">Sélectionnez les utilisateurs que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-122">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="a3aa5-123">Dans le volet de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-123">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="a3aa5-125">Dans la page d'options **Général**, cochez ou décochez les cases correspondant aux fonctionnalités que vous voulez modifier, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-125">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="a3aa5-126">**Option**</span><span class="sxs-lookup"><span data-stu-id="a3aa5-126">**Option**</span></span>|<span data-ttu-id="a3aa5-127">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a3aa5-127">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3aa5-128">Appels audio et vidéo HD</span><span class="sxs-lookup"><span data-stu-id="a3aa5-128">Audio and HD video</span></span>  <br/> |<span data-ttu-id="a3aa5-129">Autorisez cette personne à enregistrer les réunions audio et les réunions audio et vidéo ou ne l’autorisez pas à planifier des réunions (aucune).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-129">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="a3aa5-130">Enregistrer les conversations et les réunions</span><span class="sxs-lookup"><span data-stu-id="a3aa5-130">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="a3aa5-131">Sélectionnez les éléments que cette personne est autorisée à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-131">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="a3aa5-132">Cette option n’est pas disponible dans Skype entreprise Basic.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-132">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="a3aa5-133">À des fins de conformité, désactivez les fonctions non archivées.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-133">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="a3aa5-134">Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-134">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="a3aa5-135">La sélection de cette option désactive les fonctionnalités qui ne sont pas capturées lorsque vous disposez d’une [conservation inaltérable](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) dans le centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-135">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="a3aa5-136">Elle désactive les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3aa5-136">It turns off the following features:</span></span> <br/>  <span data-ttu-id="a3aa5-137">transfert de fichiers avec la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="a3aa5-137">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="a3aa5-138">Pages OneNote partagées</span><span class="sxs-lookup"><span data-stu-id="a3aa5-138">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="a3aa5-139">Annotations PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a3aa5-139">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="a3aa5-140">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-140">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="a3aa5-141">Voir [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-141">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="a3aa5-142">Bloquer les communications externes</span><span class="sxs-lookup"><span data-stu-id="a3aa5-142">Block external communications</span></span>
<span data-ttu-id="a3aa5-143"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="a3aa5-143"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="a3aa5-144">Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-144">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="a3aa5-145">Sélectionnez **utilisateurs**, sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres, puis sélectionnez **modifier** la ![ modification ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="a3aa5-145">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="a3aa5-146">Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :</span><span class="sxs-lookup"><span data-stu-id="a3aa5-146">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="a3aa5-147">**Utilisateurs Skype Entreprise externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des utilisateurs Skype Entreprise dans des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-147">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="a3aa5-148">**Utilisateurs Skype externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des personnes qui utilisent lʼapplication Skype gratuite.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-148">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="a3aa5-149">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-149">Click **Save**.</span></span>
    
<span data-ttu-id="a3aa5-150">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-150">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="a3aa5-151">Voir [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-151">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="a3aa5-152">Modifier les paramètres de l’audioconférence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="a3aa5-152">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="a3aa5-153"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="a3aa5-153"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="a3aa5-154">Sélectionnez **utilisateurs**, sélectionnez l’utilisateur dont vous souhaitez modifier les paramètres de conférence rendez-vous, puis sélectionnez **modifier** la ![ modification ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="a3aa5-154">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="a3aa5-155">Sélectionnez **audioconférence**, sélectionnez votre fournisseur de services d’audioconférence, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-155">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="a3aa5-156">**Configuration de l'audioconférence**</span><span class="sxs-lookup"><span data-stu-id="a3aa5-156">**Audio conferencing setting**</span></span>|<span data-ttu-id="a3aa5-157">**Description**</span><span class="sxs-lookup"><span data-stu-id="a3aa5-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3aa5-158">**Nom du fournisseur**</span><span class="sxs-lookup"><span data-stu-id="a3aa5-158">**Provider name**</span></span> <br/> |<span data-ttu-id="a3aa5-159">Dans la liste, choisissez votre fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-159">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="a3aa5-160">**Numéro payant** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="a3aa5-160">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="a3aa5-161">Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="a3aa5-162">Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="a3aa5-163">Mettez en forme les numéros comme vous voulez qu’ils apparaissent dans les demandes de réunion Skype entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="a3aa5-164">**Numéro gratuit**</span><span class="sxs-lookup"><span data-stu-id="a3aa5-164">**Toll-free number**</span></span> <br/> |<span data-ttu-id="a3aa5-165">Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-165">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="a3aa5-166">Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-166">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="a3aa5-167">Mettez en forme les numéros comme vous voulez qu’ils apparaissent dans les demandes de réunion Skype entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-167">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="a3aa5-168">**ID de conférence et code confidentiel** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="a3aa5-168">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="a3aa5-169">Code confidentiel du participant, ou code de conférence, utilisé pour participer aux réunions planifiées par cet utilisateur et fourni par un fournisseur de services d’audioconférence tiers.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-169">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="a3aa5-170">Si l’utilisateur utilise Microsoft en tant que fournisseur de services d’audioconférence, ce n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-170">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="a3aa5-171">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3aa5-171">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="a3aa5-172">Reportez-vous [à la rubrique définition des numéros de téléphone inclus dans les invitations](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a3aa5-172">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="a3aa5-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3aa5-173">Related topics</span></span> 

[<span data-ttu-id="a3aa5-174">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a3aa5-174">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a3aa5-175">Licences de compléments pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3aa5-175">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
