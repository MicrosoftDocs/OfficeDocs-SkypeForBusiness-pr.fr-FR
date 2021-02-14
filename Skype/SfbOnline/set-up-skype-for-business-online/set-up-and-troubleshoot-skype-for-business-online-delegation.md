---
title: Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Cet article explique comment configurer et dépanner la délégation Skype Entreprise Online. Cet article fournit des conseils sur la configuration, les recommandations et les étapes de dépannage.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010797"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="0f3c6-104">Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0f3c6-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="0f3c6-105">Cet article explique comment configurer et dépanner la délégation Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="0f3c6-106">Cet article fournit des conseils sur la configuration, les recommandations et les étapes de dépannage.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="0f3c6-107">Instructions et exigences</span><span class="sxs-lookup"><span data-stu-id="0f3c6-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="0f3c6-108">Instructions relatives à la délégation</span><span class="sxs-lookup"><span data-stu-id="0f3c6-108">Guidelines for delegation</span></span>

<span data-ttu-id="0f3c6-109">La configuration et la configuration de la délégation pour qu’elle fonctionne correctement dépendent de vos recommandations :</span><span class="sxs-lookup"><span data-stu-id="0f3c6-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="0f3c6-110">Vous devez utiliser le client complet Skype Entreprise 2015 avec les dernières mises à jour ou le client Skype Entreprise 2016 complet.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="0f3c6-111">Vous devez utiliser le client Outlook 2013 avec les dernières mises à jour ou le client Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="0f3c6-112">Assurez-vous que le délégant et les ordinateurs délégués ont un profil de courrier Outlook principal ou le profil par défaut.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="0f3c6-113">Ce profil de messagerie ne doit contenir qu’un seul compte.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="0f3c6-114">Skype Entreprise pour le délégant et le délégué doivent être des utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="0f3c6-115">En outre, les Exchange Server de messagerie pour chaque compte doivent être soit en ligne, soit sur site.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="0f3c6-116">Le délégant et le délégué doivent utiliser la même version principale d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="0f3c6-117">La **valeur de l’attribut EnableExchangeDelegateSync** doit être définie sur **true** dans la stratégie client.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="0f3c6-118">Vous pouvez vérifier ce paramètre en exécutant l’cmdlet **Get-CSClientPolicy** dans le module PowerShell de Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="0f3c6-119">Le délégant et le délégué doivent être inscrits à Skype Entreprise et à Outlook en même temps sur différentes stations de travail.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="0f3c6-120">Les boîtes aux lettres partagées ne sont pas prise en charge pour la délégation Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="0f3c6-121">Cela est dû au fait que la boîte aux lettres partagée ne comprend pas de liste de contrôle d’accès (ACL) **de** la part de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="0f3c6-122">Prise en charge de la version du client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="0f3c6-122">Skype for Business client version support</span></span>

||<span data-ttu-id="0f3c6-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-123">**Outlook 2013**</span></span>|<span data-ttu-id="0f3c6-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f3c6-125">**Client Lync/Skype Entreprise Basic**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="0f3c6-126">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="0f3c6-126">Not supported</span></span> |<span data-ttu-id="0f3c6-127">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="0f3c6-127">Not supported</span></span>
|<span data-ttu-id="0f3c6-128">**Skype Entreprise 2015**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="0f3c6-129">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="0f3c6-129">Supported</span></span>| <span data-ttu-id="0f3c6-130">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="0f3c6-130">Supported</span></span>|
|<span data-ttu-id="0f3c6-131">**Skype Entreprise 2016**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="0f3c6-132">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="0f3c6-132">Supported</span></span>| <span data-ttu-id="0f3c6-133">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="0f3c6-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="0f3c6-134">Conditions de licence requises</span><span class="sxs-lookup"><span data-stu-id="0f3c6-134">Licensing requirements</span></span>

<span data-ttu-id="0f3c6-135">**Scénario de licence Entreprise E3**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="0f3c6-136">**Licence**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-136">**License**</span></span>|<span data-ttu-id="0f3c6-137">**Clients**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-137">**Clients**</span></span>|<span data-ttu-id="0f3c6-138">**Notes**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f3c6-139">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="0f3c6-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="0f3c6-140">Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="0f3c6-141">Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="0f3c6-142">Le client Skype Entreprise Basic ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="0f3c6-143">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="0f3c6-144">Entreprise E3 avec Office 365 Phone System + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="0f3c6-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="0f3c6-145">Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="0f3c6-146">Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="0f3c6-147">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="0f3c6-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="0f3c6-148">Le client Skype Entreprise Basic ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="0f3c6-149">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="0f3c6-150">**Scénario de licence Entreprise E5**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="0f3c6-151">**Licence**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-151">**License**</span></span>|<span data-ttu-id="0f3c6-152">**Clients**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-152">**Clients**</span></span>|<span data-ttu-id="0f3c6-153">**Notes**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f3c6-154">Entreprise E5</span><span class="sxs-lookup"><span data-stu-id="0f3c6-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="0f3c6-155">Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="0f3c6-156">Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="0f3c6-157">Le client Skype Entreprise Basic ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="0f3c6-158">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="0f3c6-159">Entreprise E5 + Plan d’appel Office 365</span><span class="sxs-lookup"><span data-stu-id="0f3c6-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="0f3c6-160">Skype Entreprise pour Mac 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="0f3c6-161">Lync 2013 (Skype Entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="0f3c6-162">Skype Entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f3c6-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="0f3c6-163">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="0f3c6-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="0f3c6-164">Le client Skype Entreprise Basic ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="0f3c6-165">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="0f3c6-166">Configurer et vérifier la délégation</span><span class="sxs-lookup"><span data-stu-id="0f3c6-166">Set up and verify delegation</span></span>

<span data-ttu-id="0f3c6-167">Pour configurer la délégation Skype Entreprise Online, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="0f3c6-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="0f3c6-168">Pour les clients Windows</span><span class="sxs-lookup"><span data-stu-id="0f3c6-168">For Windows clients</span></span>

 <span data-ttu-id="0f3c6-169">**Onglet De forwarding d’appel**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="0f3c6-170">Sélectionnez **Options**  >    >  **Outils Paramètres de forwardage d’appel.**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="0f3c6-171">Sélectionnez **Modifier mes membres délégués.**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="0f3c6-172">**Sélectionnez** Ajouter, sélectionnez le délégué que vous voulez ajouter, puis **OK.**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="0f3c6-173">**Aucun onglet De forwarding d’appel**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="0f3c6-174">Dans Outlook, sélectionnez  >  **Paramètres du compte de fichier**- Ajouter un  >  **accès**  >  **délégué.**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="0f3c6-175">Localisez et ajoutez le nom de la personne qui sera déléguée.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="0f3c6-176">Sélectionnez **le** menu Calendrier, puis Sélectionnez **Éditeur (peut lire, créer et modifier des éléments).**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="0f3c6-177">Pour les clients Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="0f3c6-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="0f3c6-178">**Onglet De forwarding d’appel**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="0f3c6-179">Si le client ne  dispose pas d’un  onglet Dedélément d’appel avec le lien Modifier mes membres délégués et que le délégant se trouve sur un ordinateur Mac, le délégant doit se connecter à un ordinateur Windows pour configurer la délégation.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="0f3c6-180">En effet, les clients Mac ne peuvent pas établir de connexions MAPI, et il s’agit d’une obligation d’établir la délégation Skype Entreprise à partir d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="0f3c6-181">Vérifier la réussite</span><span class="sxs-lookup"><span data-stu-id="0f3c6-181">Verify success</span></span>

<span data-ttu-id="0f3c6-182">Si la configuration réussit, le délégué doit voir que vous avez été ajouté en tant que délégué du message **< Name>** et que le groupe Personnes **que** je gère les appels est créé.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="0f3c6-183">Le délégant doit voir que le groupe **Délégués** est créé.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f3c6-184">Les autorisations de délégation apparaissent généralement dans les 30 minutes après le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="0f3c6-185">Toutefois, cette procédure peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="0f3c6-186">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="0f3c6-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="0f3c6-187">Problèmes courants</span><span class="sxs-lookup"><span data-stu-id="0f3c6-187">Common issues</span></span>

- > <span data-ttu-id="0f3c6-188">**Problème 1** L’entrée de délégué continue d’apparaître dans le groupe Personnes **je** gère les appels pour une fois que le délégant a supprimé le délégué du client Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="0f3c6-189">**Résolution 1** Dans le client Skype Entreprise, cliquez avec le bouton droit sur le délégué dans le groupe **Délégués,** puis sélectionnez Supprimer **du groupe.**</span><span class="sxs-lookup"><span data-stu-id="0f3c6-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="0f3c6-190">**Problème 2** Une fois l’accès délégué accordé par le biais du client Outlook, ni le message de confirmation ni le message « Personnes **que** je gère les appels pour le groupe » n’apparaissent pour le délégué.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="0f3c6-191">**Résolution 2** Supprimez la délégation du client Outlook, attendez environ 15 minutes pour la réplication, puis ajoutez de nouveau le délégué.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="0f3c6-192">Autres problèmes courants</span><span class="sxs-lookup"><span data-stu-id="0f3c6-192">Other common issues</span></span>

- <span data-ttu-id="0f3c6-193">La délégation ne fonctionne pas si le seuil de 25 délégations et 25 délégués est dépassé.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="0f3c6-194">Le client Skype Entreprise Basic n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f3c6-195">Si vous installez le client Skype Entreprise Basic, la délégation est supprimée.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="0f3c6-196">Si la **valeur État MAPI** n’est pas **CORRECTE,** assurez-vous que les valeurs **SIP** et **SMTP** correspondent.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f3c6-197">Après le premier démarrage de Skype Entreprise  et Outlook, l’affichage du statut MAPI peut prendre plusieurs minutes.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="0f3c6-198">La création d’un groupe de sécurité et l’ajout d’autorisations de délégation à ce groupe de sécurité ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="0f3c6-199">MAPI n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-199">MAPI is unavailable.</span></span> <span data-ttu-id="0f3c6-200">Consultez [l’erreur « MAPI non disponible » dans le client Skype Entreprise 2016.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="0f3c6-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="0f3c6-201">La boîte aux lettres Exchange Online n’est pas accessible via le client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="0f3c6-202">Si c’est le cas, exécutez le [test de connectivité d’Outlook](https://testconnectivity.microsoft.com/) pour vous assurer qu’il est exécuté.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0f3c6-203">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f3c6-203">Related topics</span></span>
[<span data-ttu-id="0f3c6-204">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0f3c6-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0f3c6-205">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="0f3c6-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
