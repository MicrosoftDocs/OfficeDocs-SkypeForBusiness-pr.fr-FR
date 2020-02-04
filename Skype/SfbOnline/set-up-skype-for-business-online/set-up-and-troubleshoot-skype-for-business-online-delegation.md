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
description: Cet article explique comment configurer et résoudre les problèmes de délégation Skype entreprise online. Cet article fournit des conseils pour la configuration des recommandations, meilleures pratiques et étapes de résolution des problèmes.
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706479"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="7723f-104">Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7723f-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="7723f-105">Cet article explique comment configurer et résoudre les problèmes de délégation Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="7723f-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="7723f-106">Cet article fournit des conseils pour la configuration des recommandations, meilleures pratiques et étapes de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="7723f-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="7723f-107">Recommandations et configuration requise</span><span class="sxs-lookup"><span data-stu-id="7723f-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="7723f-108">Recommandations en matière de délégation</span><span class="sxs-lookup"><span data-stu-id="7723f-108">Guidelines for delegation</span></span>

<span data-ttu-id="7723f-109">La configuration et l’activation de la délégation fonctionneront correctement en fonction des recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7723f-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="7723f-110">Vous devez utiliser le client complet Skype entreprise 2015 avec les mises à jour les plus récentes ou le client complet Skype entreprise 2016.</span><span class="sxs-lookup"><span data-stu-id="7723f-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="7723f-111">Vous devez utiliser le client Outlook 2013 avec les mises à jour les plus récentes ou le client 2016 Outlook.</span><span class="sxs-lookup"><span data-stu-id="7723f-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="7723f-112">Assurez-vous que la personne qui est déléguée et déléguée ont un profil de courrier Outlook principal ou le profil par défaut.</span><span class="sxs-lookup"><span data-stu-id="7723f-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="7723f-113">Ce profil de messagerie ne doit contenir qu’un seul compte.</span><span class="sxs-lookup"><span data-stu-id="7723f-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="7723f-114">Skype entreprise pour le déléguer et le délégué doivent être des utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="7723f-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="7723f-115">Par ailleurs, les boîtes aux lettres Exchange Server pour chaque compte doivent être soit en ligne soit en local.</span><span class="sxs-lookup"><span data-stu-id="7723f-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="7723f-116">Le délégué et le délégué doivent utiliser la même version majeure d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="7723f-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="7723f-117">La valeur de l’attribut **EnableExchangeDelegateSync** doit être définie sur **true** dans la stratégie client.</span><span class="sxs-lookup"><span data-stu-id="7723f-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="7723f-118">Vous pouvez vérifier ce paramètre en exécutant l’applet de contrôle **Get-CSClientPolicy** dans le module PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="7723f-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="7723f-119">Le délégué et le délégué doivent être connectés à Skype entreprise et à Outlook en même temps sur différentes stations de travail.</span><span class="sxs-lookup"><span data-stu-id="7723f-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="7723f-120">Les boîtes aux lettres partagées ne sont pas prises en charge pour la délégation Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="7723f-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="7723f-121">En effet, la boîte aux lettres partagée ne dispose pas de la liste de contrôle d’accès **SendOnBehalf** (ACL).</span><span class="sxs-lookup"><span data-stu-id="7723f-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="7723f-122">Prise en charge du client Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="7723f-122">Skype for Business client version support</span></span>

||<span data-ttu-id="7723f-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="7723f-123">**Outlook 2013**</span></span>|<span data-ttu-id="7723f-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="7723f-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7723f-125">**Client de base Lync/Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="7723f-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="7723f-126">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="7723f-126">Not supported</span></span> |<span data-ttu-id="7723f-127">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="7723f-127">Not supported</span></span>
|<span data-ttu-id="7723f-128">**Skype Entreprise 2015**</span><span class="sxs-lookup"><span data-stu-id="7723f-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="7723f-129">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="7723f-129">Supported</span></span>| <span data-ttu-id="7723f-130">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="7723f-130">Supported</span></span>|
|<span data-ttu-id="7723f-131">**Skype entreprise 2016**</span><span class="sxs-lookup"><span data-stu-id="7723f-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="7723f-132">Pris en charge </span><span class="sxs-lookup"><span data-stu-id="7723f-132">Supported</span></span>| <span data-ttu-id="7723f-133">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="7723f-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="7723f-134">Conditions de licence</span><span class="sxs-lookup"><span data-stu-id="7723f-134">Licensing requirements</span></span>

<span data-ttu-id="7723f-135">**Scénario de gestion des licences entreprise E3**</span><span class="sxs-lookup"><span data-stu-id="7723f-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="7723f-136">**Licence**</span><span class="sxs-lookup"><span data-stu-id="7723f-136">**License**</span></span>|<span data-ttu-id="7723f-137">**Clients**</span><span class="sxs-lookup"><span data-stu-id="7723f-137">**Clients**</span></span>|<span data-ttu-id="7723f-138">**Remarques**</span><span class="sxs-lookup"><span data-stu-id="7723f-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7723f-139">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="7723f-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="7723f-140">Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7723f-141">Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="7723f-142">Le client Skype entreprise basique ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="7723f-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7723f-143">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="7723f-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="7723f-144">Entreprise E3 avec le système téléphonique d’Office 365 + plan Office 365 xCalling</span><span class="sxs-lookup"><span data-stu-id="7723f-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="7723f-145">Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7723f-146">Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7723f-147">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="7723f-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="7723f-148">Le client Skype entreprise basique ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="7723f-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7723f-149">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="7723f-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="7723f-150">**Scénario de gestion des licences entreprise E5**</span><span class="sxs-lookup"><span data-stu-id="7723f-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="7723f-151">**Licence**</span><span class="sxs-lookup"><span data-stu-id="7723f-151">**License**</span></span>|<span data-ttu-id="7723f-152">**Clients**</span><span class="sxs-lookup"><span data-stu-id="7723f-152">**Clients**</span></span>|<span data-ttu-id="7723f-153">**Remarques**</span><span class="sxs-lookup"><span data-stu-id="7723f-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7723f-154">Entreprise E5</span><span class="sxs-lookup"><span data-stu-id="7723f-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="7723f-155">Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="7723f-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="7723f-156">Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="7723f-157">Le client Skype entreprise basique ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="7723f-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7723f-158">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="7723f-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="7723f-159">Plan d’appel d’entreprise E5 et Office 365</span><span class="sxs-lookup"><span data-stu-id="7723f-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="7723f-160">Skype entreprise pour Mac 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="7723f-161">Lync 2013 (Skype entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7723f-162">Skype entreprise 2016 utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7723f-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7723f-163">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="7723f-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="7723f-164">Le client Skype entreprise basique ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="7723f-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7723f-165">Pour les clients Mac, vous pouvez déléguer des appels, mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="7723f-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="7723f-166">Configurer et vérifier la délégation</span><span class="sxs-lookup"><span data-stu-id="7723f-166">Set up and verify delegation</span></span>

<span data-ttu-id="7723f-167">Pour configurer la délégation de Skype entreprise Online, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7723f-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="7723f-168">Pour les clients Windows</span><span class="sxs-lookup"><span data-stu-id="7723f-168">For Windows clients</span></span>

 <span data-ttu-id="7723f-169">**Onglet renvoi d’appel**</span><span class="sxs-lookup"><span data-stu-id="7723f-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="7723f-170">Sélectionnez **Outils** > **options** > **paramètres de transfert d’appel**.</span><span class="sxs-lookup"><span data-stu-id="7723f-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="7723f-171">Cliquez sur **Modifier mes membres délégués**.</span><span class="sxs-lookup"><span data-stu-id="7723f-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="7723f-172">Cliquez sur **Ajouter**, sélectionnez le délégué que vous voulez ajouter, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="7723f-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="7723f-173">**Aucun onglet renvoi d’appel**</span><span class="sxs-lookup"><span data-stu-id="7723f-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="7723f-174">Dans Outlook, sélectionnez \*\*\*\* > **paramètres** > du compte de fichier > **Ajouter\*\*\*\*l’accès délégué**.</span><span class="sxs-lookup"><span data-stu-id="7723f-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="7723f-175">Recherchez et ajoutez le nom de la personne qui va agir en tant que délégué.</span><span class="sxs-lookup"><span data-stu-id="7723f-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="7723f-176">Sélectionnez le menu **calendrier** , puis **éditeur (peut lire, créer et modifier des éléments)**.</span><span class="sxs-lookup"><span data-stu-id="7723f-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="7723f-177">Pour les clients Mac-Lync</span><span class="sxs-lookup"><span data-stu-id="7723f-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="7723f-178">**Onglet renvoi d’appel**</span><span class="sxs-lookup"><span data-stu-id="7723f-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="7723f-179">Si le client ne possède pas d’onglet **renvoi d’appel** avec le lien **Modifier mes membres délégués** et si la personne disposant se trouve sur un ordinateur Mac, la personne disposant doit se connecter à un ordinateur exécutant Windows pour configurer la délégation.</span><span class="sxs-lookup"><span data-stu-id="7723f-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="7723f-180">En effet, les clients Mac ne peuvent pas créer de connexions MAPI et c’est une condition requise pour établir une délégation Skype entreprise à partir d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="7723f-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="7723f-181">Vérifier le succès</span><span class="sxs-lookup"><span data-stu-id="7723f-181">Verify success</span></span>

<span data-ttu-id="7723f-182">Si la configuration est réussie, le délégué doit voir le message **vous avez été ajouté en tant que délégué pour < nom>** message et les **personnes avec lesquelles je gère les appels pour** le groupe sont créées.</span><span class="sxs-lookup"><span data-stu-id="7723f-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="7723f-183">La personne disposant doit voir que le groupe **délégués** est créé.</span><span class="sxs-lookup"><span data-stu-id="7723f-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7723f-184">Les autorisations de délégation apparaissent généralement dans les 30 minutes du processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="7723f-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="7723f-185">Toutefois, ce processus peut prendre jusqu’à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="7723f-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="7723f-186">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="7723f-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="7723f-187">Problèmes courants</span><span class="sxs-lookup"><span data-stu-id="7723f-187">Common issues</span></span>

- > <span data-ttu-id="7723f-188">**Problème 1** L’entrée de délégué continue à apparaître dans le groupe **personnes que je gère** , une fois que le délégué a supprimé le délégué du client Outlook.</span><span class="sxs-lookup"><span data-stu-id="7723f-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="7723f-189">**Résolution 1** Sur le client Skype entreprise, cliquez avec le bouton droit sur le délégué dans le groupe **délégués** , puis sélectionnez **supprimer du groupe**.</span><span class="sxs-lookup"><span data-stu-id="7723f-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="7723f-190">**Problème 2** Lorsque l’accès délégué est accordé par le biais du client Outlook, ni le message de confirmation, ni le message **je gère les appels pour** le délégué apparaissent.</span><span class="sxs-lookup"><span data-stu-id="7723f-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="7723f-191">**Résolution 2** Supprimez la délégation du client Outlook, attendez environ 15 minutes pour la réplication, puis rajoutez le délégué.</span><span class="sxs-lookup"><span data-stu-id="7723f-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="7723f-192">Autres problèmes courants</span><span class="sxs-lookup"><span data-stu-id="7723f-192">Other common issues</span></span>

- <span data-ttu-id="7723f-193">La délégation ne fonctionne pas si le seuil de 25 délégations et 25 délégués est dépassé.</span><span class="sxs-lookup"><span data-stu-id="7723f-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="7723f-194">Le client Skype entreprise basique n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="7723f-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7723f-195">Si vous installez le client Skype entreprise Basic, il est supprimé et interrompu la délégation.</span><span class="sxs-lookup"><span data-stu-id="7723f-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="7723f-196">Si la valeur de **statut MAPI** n’est pas **OK**, assurez-vous que les valeurs **SIP** et **SMTP** correspondent.</span><span class="sxs-lookup"><span data-stu-id="7723f-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7723f-197">Quelques minutes peuvent s’écouler avant que l’État MAPI affiche le message **OK** une fois que vous avez démarré Skype entreprise et Outlook.</span><span class="sxs-lookup"><span data-stu-id="7723f-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="7723f-198">La création d’un groupe de sécurité et l’ajout d’autorisations de délégation pour ce groupe de sécurité ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="7723f-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="7723f-199">MAPI n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="7723f-199">MAPI is unavailable.</span></span> <span data-ttu-id="7723f-200">Voir [erreur « MAPI non disponible » dans le client Skype entreprise 2016](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="7723f-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="7723f-201">La boîte aux lettres Exchange Online n’est pas accessible via le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="7723f-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="7723f-202">Le cas échéant, exécutez le [test de connectivité Outlook](https://testconnectivity.microsoft.com/) pour vérifier qu’il est transmis.</span><span class="sxs-lookup"><span data-stu-id="7723f-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7723f-203">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7723f-203">Related topics</span></span>
[<span data-ttu-id="7723f-204">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7723f-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7723f-205">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="7723f-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
