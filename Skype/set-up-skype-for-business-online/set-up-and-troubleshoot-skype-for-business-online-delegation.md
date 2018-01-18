---
title: "Configurer et dépanner Skype pour la délégation d’entreprise en ligne"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Cet article explique comment configurer et dépanner Skype pour la délégation d’activité en ligne. Cet article vous donne des conseils pour des recommandations sur le paramétrage, les meilleures pratiques et les étapes de dépannage."
ms.openlocfilehash: bf3bf61a633366408e2584a89dfee9ad771ce78e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="2032c-104">Configurer et dépanner Skype pour la délégation d’entreprise en ligne</span><span class="sxs-lookup"><span data-stu-id="2032c-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="2032c-105">Cet article explique comment configurer et dépanner Skype pour la délégation d’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="2032c-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="2032c-106">Cet article vous donne des conseils pour des recommandations sur le paramétrage, les meilleures pratiques et les étapes de dépannage.</span><span class="sxs-lookup"><span data-stu-id="2032c-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="2032c-107">Instructions et conditions</span><span class="sxs-lookup"><span data-stu-id="2032c-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="2032c-108">Instructions pour la délégation</span><span class="sxs-lookup"><span data-stu-id="2032c-108">Guidelines for delegation</span></span>

<span data-ttu-id="2032c-109">Paramétrage et mise en route de la délégation fonctionne correctement dépendant de vous les recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2032c-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="2032c-110">Vous devez utiliser le Skype pour client complet d’entreprise 2015 avec les dernières mises à jour ou le Skype pour le client complet de 2016 de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2032c-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="2032c-111">Vous devez utiliser le client Outlook 2013 avec les dernières mises à jour ou le client Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="2032c-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="2032c-112">Assurez-vous que la personne qui a délégué et délégué ordinateurs ont un profil de messagerie Outlook est le principal ou le profil par défaut.</span><span class="sxs-lookup"><span data-stu-id="2032c-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="2032c-113">Ce profil de messagerie doit contenir qu’un seul compte.</span><span class="sxs-lookup"><span data-stu-id="2032c-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="2032c-114">Skype pour les entreprises de la personne qui a délégué et du délégué doit être des utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="2032c-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="2032c-115">En outre, les boîtes aux lettres Exchange Server pour chaque compte doit soit tous les deux être en ligne ou sur site.</span><span class="sxs-lookup"><span data-stu-id="2032c-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="2032c-116">La personne qui a délégué et le délégué doivent utiliser la même version principale de Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="2032c-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="2032c-117">La valeur de l’attribut **EnableExchangeDelegateSync** doit être définie à **true** dans la stratégie du client.</span><span class="sxs-lookup"><span data-stu-id="2032c-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="2032c-118">Vous pouvez vérifier ce paramètre en exécutant l’applet de commande **Get-CSClientPolicy** dans le Skype pour module de Business Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2032c-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="2032c-119">La personne qui a délégué et le délégué doivent être connectés à Skype pour les entreprises et Outlook en même temps sur les stations de travail différentes.</span><span class="sxs-lookup"><span data-stu-id="2032c-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="2032c-120">Boîtes aux lettres partagées ne sont pas pris en charge pour Skype pour la délégation d’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="2032c-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="2032c-121">C’est parce que la boîte aux lettres partagée n’a pas la liste de contrôle d’accès (ACL) **sendonbehalf** .</span><span class="sxs-lookup"><span data-stu-id="2032c-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="2032c-122">Skype pour la prise en charge de la version Business client</span><span class="sxs-lookup"><span data-stu-id="2032c-122">Skype for Business client version support</span></span>

||<span data-ttu-id="2032c-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="2032c-123">**Outlook 2013**</span></span>|<span data-ttu-id="2032c-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="2032c-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2032c-125">**Lync/Skype pour Client de base d’entreprise**</span><span class="sxs-lookup"><span data-stu-id="2032c-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="2032c-126">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2032c-126">Not supported</span></span> |<span data-ttu-id="2032c-127">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2032c-127">Not supported</span></span>
|<span data-ttu-id="2032c-128">**Skype pour entreprise 2015**</span><span class="sxs-lookup"><span data-stu-id="2032c-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="2032c-129">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="2032c-129">Supported</span></span>| <span data-ttu-id="2032c-130">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="2032c-130">Supported</span></span>|
|<span data-ttu-id="2032c-131">**Skype pour entreprise 2016**</span><span class="sxs-lookup"><span data-stu-id="2032c-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="2032c-132">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="2032c-132">Supported</span></span>| <span data-ttu-id="2032c-133">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="2032c-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="2032c-134">Conditions de licence</span><span class="sxs-lookup"><span data-stu-id="2032c-134">Licensing requirements</span></span>

<span data-ttu-id="2032c-135">**Scénario de licence entreprise E3**</span><span class="sxs-lookup"><span data-stu-id="2032c-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="2032c-136">**Licence**</span><span class="sxs-lookup"><span data-stu-id="2032c-136">**License**</span></span>|<span data-ttu-id="2032c-137">**Clients**</span><span class="sxs-lookup"><span data-stu-id="2032c-137">**Clients**</span></span>|<span data-ttu-id="2032c-138">**Remarques**</span><span class="sxs-lookup"><span data-stu-id="2032c-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2032c-139">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="2032c-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="2032c-140">Lync 2013 (Skype pour entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="2032c-141">Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="2032c-142">Skype pour client de base d’entreprise ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="2032c-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="2032c-143">Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="2032c-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="2032c-144">E3 Enterprise avec Office 365 téléphone système + d’Office 365, xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="2032c-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="2032c-145">Lync 2013 (Skype pour entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="2032c-146">Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="2032c-147">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2032c-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="2032c-148">Skype pour client de base d’entreprise ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="2032c-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="2032c-149">Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="2032c-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="2032c-150">**Scénario de licence entreprise E5**</span><span class="sxs-lookup"><span data-stu-id="2032c-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="2032c-151">**Licence**</span><span class="sxs-lookup"><span data-stu-id="2032c-151">**License**</span></span>|<span data-ttu-id="2032c-152">**Clients**</span><span class="sxs-lookup"><span data-stu-id="2032c-152">**Clients**</span></span>|<span data-ttu-id="2032c-153">**Remarques**</span><span class="sxs-lookup"><span data-stu-id="2032c-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2032c-154">E5 de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="2032c-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="2032c-155">Lync 2013 (Skype pour entreprise 2015) utilisé avec 2016 d’Outlook ou d’Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="2032c-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="2032c-156">Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="2032c-157">Skype pour client de base d’entreprise ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="2032c-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="2032c-158">Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="2032c-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="2032c-159">E5 de l’entreprise plus de Plan d’appel de Office 365</span><span class="sxs-lookup"><span data-stu-id="2032c-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="2032c-160">Skype pour entreprise pour Mac 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="2032c-161">Lync 2013 (Skype pour entreprise 2015) utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="2032c-162">Skype pour 2016 Business utilisé avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2032c-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="2032c-163">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2032c-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="2032c-164">Skype pour client de base d’entreprise ne prend pas en charge la délégation.</span><span class="sxs-lookup"><span data-stu-id="2032c-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="2032c-165">Pour les clients Mac, vous pouvez déléguer des appels mais pas des réunions.</span><span class="sxs-lookup"><span data-stu-id="2032c-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="2032c-166">Permet de paramétrer et de vérifier la délégation</span><span class="sxs-lookup"><span data-stu-id="2032c-166">Set up and verify delegation</span></span>

<span data-ttu-id="2032c-167">Pour paramétrer Skype pour la délégation d’entreprise en ligne, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2032c-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="2032c-168">Pour les clients Windows</span><span class="sxs-lookup"><span data-stu-id="2032c-168">For Windows clients</span></span>

 <span data-ttu-id="2032c-169">**Onglet de transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="2032c-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="2032c-170">Sélectionnez **Outils** > **Options** > **appeler le transfert des paramètres**.</span><span class="sxs-lookup"><span data-stu-id="2032c-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="2032c-171">Sélectionnez **Modifier les membres de mon délégué**.</span><span class="sxs-lookup"><span data-stu-id="2032c-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="2032c-172">Sélectionnez **Ajouter**et sélectionnez le délégué que vous souhaitez ajouter puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="2032c-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="2032c-173">**Aucun onglet transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="2032c-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="2032c-174">Dans Outlook, sélectionnez le **fichier** > **Les paramètres du compte** > **Accès délégué** > **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2032c-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="2032c-175">Recherchez, puis ajoutez le nom de la personne qui va être le délégué.</span><span class="sxs-lookup"><span data-stu-id="2032c-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="2032c-176">Sélectionnez le menu **calendrier** , puis sélectionnez **éditeur (peut lire, créer et modifier des éléments)**.</span><span class="sxs-lookup"><span data-stu-id="2032c-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="2032c-177">Pour les clients Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="2032c-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="2032c-178">**Onglet de transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="2032c-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="2032c-179">Si le client n’a pas un onglet **Transfert d’appel** qui a le lien **Modifier les membres de mon délégué** et que la personne se trouve sur un ordinateur Mac, la personne doit vous connecter à un ordinateur fonctionnant sous Windows pour configurer la délégation.</span><span class="sxs-lookup"><span data-stu-id="2032c-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="2032c-180">C’est parce que les clients Mac ne peut pas effectuer de connexions MAPI, et il s’agit d’une exigence pour établir Skype pour la délégation d’entreprise à partir d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="2032c-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="2032c-181">Vérifiez le succès</span><span class="sxs-lookup"><span data-stu-id="2032c-181">Verify success</span></span>

<span data-ttu-id="2032c-182">Si l’installation est réussie, le délégué doit s’afficher **que vous avez été ajouté en tant que délégué pour < nom >** message et que le groupe de **personnes je gérer les appels pour** est créé.</span><span class="sxs-lookup"><span data-stu-id="2032c-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="2032c-183">La personne qui a délégué doit voir que le groupe de **délégués** est créé.</span><span class="sxs-lookup"><span data-stu-id="2032c-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2032c-184">Autorisations de délégation apparaissent généralement dans les 30 minutes au processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="2032c-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="2032c-185">Toutefois, ce processus peut prendre jusqu'à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="2032c-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="2032c-186">Identification et résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="2032c-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="2032c-187">Problèmes courants</span><span class="sxs-lookup"><span data-stu-id="2032c-187">Common issues</span></span>

- > <span data-ttu-id="2032c-188">**Problème 1** L’entrée de délégué continue d’apparaître dans le groupe **I gérer les appels pour les personnes** après que la personne a retiré le délégué du client Outlook.</span><span class="sxs-lookup"><span data-stu-id="2032c-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="2032c-189">**Résolution 1** Sur le Skype pour client d’entreprise, droit le délégué dans le groupe de **délégués** et sélectionnez **Supprimer du groupe**.</span><span class="sxs-lookup"><span data-stu-id="2032c-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="2032c-190">**Problème 2** Une fois l’accès délégué est accordé via le client Outlook, le message de confirmation, ni le groupe **I gérer les appels pour les personnes** s’affichent pour le délégué.</span><span class="sxs-lookup"><span data-stu-id="2032c-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="2032c-191">**Résolution 2** Supprimer la délégation à partir du client Outlook, et attendre environ 15 minutes pour la réplication, puis ajoutez de nouveau le délégué.</span><span class="sxs-lookup"><span data-stu-id="2032c-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="2032c-192">Autres problèmes courants</span><span class="sxs-lookup"><span data-stu-id="2032c-192">Other common issues</span></span>

- <span data-ttu-id="2032c-193">Délégation ne fonctionne pas si le seuil de personnes qui 25 délèguent et 25 délégués est dépassé.</span><span class="sxs-lookup"><span data-stu-id="2032c-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="2032c-194">Le Skype pour client de base d’entreprise n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2032c-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2032c-195">Si vous installez le Skype pour client de base d’entreprise, il supprime et rompre la délégation.</span><span class="sxs-lookup"><span data-stu-id="2032c-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="2032c-196">Si la valeur **d’État de MAPI** n’est pas **OK**, assurez-vous que les valeurs de **SIP** et **SMTP** correspondent.</span><span class="sxs-lookup"><span data-stu-id="2032c-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2032c-197">Elle peut prendre plusieurs minutes pour que le statut MAPI à afficher comme **OK** une fois que vous démarrez pour la première fois Skype pour les entreprises et Outlook.</span><span class="sxs-lookup"><span data-stu-id="2032c-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="2032c-198">Création d’un groupe de sécurité et d’ajout des autorisations de délégation pour ce groupe de sécurité n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2032c-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="2032c-199">MAPI n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="2032c-199">MAPI is unavailable.</span></span> <span data-ttu-id="2032c-200">Voir [l’Erreur « MAPI non disponible » dans Skype pour client d’entreprise 2016](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="2032c-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="2032c-201">La boîte aux lettres Exchange Online n’est pas accessible via le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2032c-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="2032c-202">Si cela se produit, exécuter le [test de connectivité Outlook](https://testconnectivity.microsoft.com/) afin de vous assurer qu’il passe.</span><span class="sxs-lookup"><span data-stu-id="2032c-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="2032c-203">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2032c-203">Related topics</span></span>
[<span data-ttu-id="2032c-204">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2032c-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="2032c-205">Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels</span><span class="sxs-lookup"><span data-stu-id="2032c-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
