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
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093388"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="334e9-103">Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="334e9-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="334e9-104">Le Centre d’administration Microsoft Teams a remplacé le Centre d’administration Skype Entreprise (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="334e9-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="334e9-105">Tous les paramètres de gestion de Skype Entreprise sont désormais dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="334e9-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="334e9-106">Pour gérer les fonctionnalités de Skype Entreprise dans le Centre d’administration Teams, vous devez avoir le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) d’administrateur global ou d’administrateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="334e9-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="334e9-107">Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="334e9-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="334e9-108">Cet article explique comment les administrateurs configurent Skype Entreprise pour un petit nombre d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="334e9-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="334e9-109">Pour suivre ces étapes en bloc, nous avons inclus des liens vers les Windows PowerShell cmdlets que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="334e9-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="334e9-110">Pour autoriser (ou bloquer) toutes les personnes de votre entreprise à communiquer avec des personnes externes, voir :</span><span class="sxs-lookup"><span data-stu-id="334e9-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="334e9-111">Autoriser les utilisateurs à contacter des utilisateurs [Skype](allow-users-to-contact-external-skype-for-business-users.md)Entreprise externes : Vous pouvez permettre à votre organisation d’utiliser les fonctionnalités avancées de Skype Entreprise (partager des bureaux, rechercher qui est en ligne, etc.) pour communiquer avec des personnes dans une entreprise de confiance (fédérée) spécifique.</span><span class="sxs-lookup"><span data-stu-id="334e9-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="334e9-112">Cet article explique également comment bloquer les communications avec des domaines spécifiques.</span><span class="sxs-lookup"><span data-stu-id="334e9-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="334e9-113">[Permettez aux utilisateurs de Skype Entreprise d’ajouter des contacts Skype.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="334e9-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="334e9-114">Vous pouvez permettre à votre organisation dʼutiliser Skype Entreprise pour rechercher et communiquer par messagerie instantanée avec des personnes qui utilisent Skype, lʼapplication gratuite.</span><span class="sxs-lookup"><span data-stu-id="334e9-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="334e9-115">Configurer les paramètres généraux pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="334e9-115">Configure general settings for one user</span></span>
<span data-ttu-id="334e9-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="334e9-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="334e9-117">Vous devez avoir des [autorisations d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="334e9-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="334e9-118">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="334e9-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="334e9-119">Connectez-vous avec votre compte scolaire ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="334e9-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="334e9-120">Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="334e9-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="334e9-121">Sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="334e9-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="334e9-123">Sélectionnez les utilisateurs que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="334e9-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="334e9-124">Dans le volet de droite, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="334e9-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="334e9-126">Dans la page d'options **Général**, cochez ou décochez les cases correspondant aux fonctionnalités que vous voulez modifier, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="334e9-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="334e9-127">**Option**</span><span class="sxs-lookup"><span data-stu-id="334e9-127">**Option**</span></span>|<span data-ttu-id="334e9-128">**Détails**</span><span class="sxs-lookup"><span data-stu-id="334e9-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="334e9-129">Appels audio et vidéo HD</span><span class="sxs-lookup"><span data-stu-id="334e9-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="334e9-130">Autorisez cette personne à enregistrer des réunions audio, audio et vidéo, ou ne l’autorisez pas à planifier des réunions (aucune).</span><span class="sxs-lookup"><span data-stu-id="334e9-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="334e9-131">Enregistrer les conversations et les réunions</span><span class="sxs-lookup"><span data-stu-id="334e9-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="334e9-132">Sélectionnez les éléments que cette personne est autorisée à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="334e9-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="334e9-133">Cette option n’est pas disponible avec Skype Entreprise Basic.</span><span class="sxs-lookup"><span data-stu-id="334e9-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="334e9-134">À des fins de conformité, désactivez les fonctions non archivées.</span><span class="sxs-lookup"><span data-stu-id="334e9-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="334e9-135">Sélectionnez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement.</span><span class="sxs-lookup"><span data-stu-id="334e9-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="334e9-136">La sélection de cette option permet de sélectionner [](/exchange/security-and-compliance/in-place-and-litigation-holds) des fonctionnalités qui ne sont pas capturées lors de la mise en place d’une attente sur place dans le Centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="334e9-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="334e9-137">Elle désactive les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="334e9-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="334e9-138">transfert de fichiers avec la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="334e9-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="334e9-139">Pages OneNote partagées</span><span class="sxs-lookup"><span data-stu-id="334e9-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="334e9-140">Annotations PowerPoint</span><span class="sxs-lookup"><span data-stu-id="334e9-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="334e9-141">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="334e9-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="334e9-142">Consultez [Configurer votre ordinateur pour Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="334e9-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="334e9-143">Bloquer les communications externes</span><span class="sxs-lookup"><span data-stu-id="334e9-143">Block external communications</span></span>
<span data-ttu-id="334e9-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="334e9-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="334e9-145">Après avoir [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) pour tout le monde dans votre entreprise, vous pouvez bloquer les communications externes pour des personnes spécifiques en suivant cette procédure.</span><span class="sxs-lookup"><span data-stu-id="334e9-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="334e9-146">**Sélectionnez** Utilisateurs, sélectionnez les utilisateurs dont vous souhaitez désactiver les paramètres, puis **sélectionnez** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Modifier.</span><span class="sxs-lookup"><span data-stu-id="334e9-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="334e9-147">Cliquez sur **Communications externes**, puis cochez ou décochez les options de votre choix :</span><span class="sxs-lookup"><span data-stu-id="334e9-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="334e9-148">**Utilisateurs Skype Entreprise externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des utilisateurs Skype Entreprise dans des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="334e9-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="334e9-149">**Utilisateurs Skype externes**: décochez cette case si vous ne voulez pas que lʼutilisateur puisse communiquer avec des personnes qui utilisent lʼapplication Skype gratuite.</span><span class="sxs-lookup"><span data-stu-id="334e9-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="334e9-150">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="334e9-150">Click **Save**.</span></span>
    
<span data-ttu-id="334e9-151">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="334e9-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="334e9-152">Consultez [Configurer votre ordinateur pour Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="334e9-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="334e9-153">Modifier les paramètres d’audioconférence pour un utilisateur</span><span class="sxs-lookup"><span data-stu-id="334e9-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="334e9-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="334e9-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="334e9-155">**Sélectionnez** Utilisateurs, sélectionnez l’utilisateur dont vous souhaitez modifier les paramètres d’audioconférence, puis **sélectionnez** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Modifier.</span><span class="sxs-lookup"><span data-stu-id="334e9-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="334e9-156">Sélectionnez **Audioconférence,** sélectionnez votre fournisseur de services d’audioconférence, tapez ou modifiez les informations demandées, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="334e9-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="334e9-157">**Configuration de l'audioconférence**</span><span class="sxs-lookup"><span data-stu-id="334e9-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="334e9-158">**Description**</span><span class="sxs-lookup"><span data-stu-id="334e9-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="334e9-159">**Nom du fournisseur**</span><span class="sxs-lookup"><span data-stu-id="334e9-159">**Provider name**</span></span> <br/> |<span data-ttu-id="334e9-160">Choisissez votre fournisseur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="334e9-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="334e9-161">**Numéro payant** (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="334e9-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="334e9-162">Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334e9-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="334e9-163">Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334e9-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="334e9-164">Affichez les numéros de la même forme que vous voulez qu’ils apparaissent dans les demandes de réunion Skype Entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="334e9-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="334e9-165">**Numéro gratuit**</span><span class="sxs-lookup"><span data-stu-id="334e9-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="334e9-166">Pour un fournisseur de services d’audioconférence tiers, ces numéros de téléphone sont ceux que vous avez reçus du fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334e9-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="334e9-167">Si l’utilisateur utilise Microsoft en tant que fournisseur d’audioconférence, ce seront des numéros définis sur le pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334e9-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="334e9-168">Affichez les numéros de la même forme que vous voulez qu’ils apparaissent dans les demandes de réunion Skype Entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="334e9-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="334e9-169">**ID et code confidentiel** de conférence (obligatoire)</span><span class="sxs-lookup"><span data-stu-id="334e9-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="334e9-170">Code confidentiel du participant, ou code de conférence, utilisé pour participer à des réunions organisées par cet utilisateur et fournies par un fournisseur de services d’audioconférence tiers.</span><span class="sxs-lookup"><span data-stu-id="334e9-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="334e9-171">Si l’utilisateur utilise Microsoft comme fournisseur de services d’audioconférence, cela ne sera pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="334e9-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="334e9-172">Pour configurer ces paramètres en bloc, utilisez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="334e9-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="334e9-173">Consultez [Définir les numéros de téléphone inclus dans les invitations](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurer votre ordinateur pour [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="334e9-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="334e9-174">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="334e9-174">Related topics</span></span> 

[<span data-ttu-id="334e9-175">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="334e9-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="334e9-176">Licences de compléments pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="334e9-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
