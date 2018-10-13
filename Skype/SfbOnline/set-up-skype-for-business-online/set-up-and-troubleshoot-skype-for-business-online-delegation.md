---
title: Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Cet article explique comment configurer et dépanner Skype pour la délégation d’entreprise en ligne. Cet article vous donne des conseils pour les étapes de dépannage, meilleures pratiques et recommandations pour le programme d’installation.
ms.openlocfilehash: e3131b28be1ad01e0965b2739dc152a627826d5e
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546674"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="4279e-104">Configurer et résoudre les problèmes de délégation pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4279e-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="4279e-105">Cet article explique comment configurer et dépanner Skype pour la délégation d’entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="4279e-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="4279e-106">Cet article vous donne des conseils pour les étapes de dépannage, meilleures pratiques et recommandations pour le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="4279e-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="4279e-107">Instructions et conditions requises</span><span class="sxs-lookup"><span data-stu-id="4279e-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="4279e-108">Instructions pour la délégation</span><span class="sxs-lookup"><span data-stu-id="4279e-108">Guidelines for delegation</span></span>

<span data-ttu-id="4279e-109">Configuration et l’obtention de la délégation fonctionne correctement dépendent de vous les recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4279e-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="4279e-110">Vous devez utiliser le Skype pour client complète 2015 métier avec les dernières mises à jour ou le Skype pour client complète 2016 Business.</span><span class="sxs-lookup"><span data-stu-id="4279e-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="4279e-111">Vous devez utiliser le client Outlook 2013 avec les dernières mises à jour ou le client Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="4279e-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="4279e-112">Assurez-vous que la personne et des ordinateurs délégués ont un profil de messagerie Outlook est le principal ou le profil par défaut.</span><span class="sxs-lookup"><span data-stu-id="4279e-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="4279e-113">Ce profil de messagerie doit contenir qu’un seul compte.</span><span class="sxs-lookup"><span data-stu-id="4279e-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="4279e-114">Skype pour les entreprises pour la personne qui a délégué et le délégué doit être des utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="4279e-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="4279e-115">En outre, les boîtes aux lettres Exchange Server pour chaque compte doit soit les deux être en ligne ou locale.</span><span class="sxs-lookup"><span data-stu-id="4279e-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="4279e-116">La personne qui a délégué et le délégué doivent être à l’aide de la même version principale de Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="4279e-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="4279e-117">La valeur d’attribut **EnableExchangeDelegateSync** doit être définie sur **true** dans la stratégie du client.</span><span class="sxs-lookup"><span data-stu-id="4279e-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="4279e-118">Vous pouvez vérifier ce paramètre en exécutant l’applet de commande **Get-CSClientPolicy** dans la Skype pour le module Business Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4279e-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="4279e-119">La personne qui a délégué et le délégué doivent être connectés à Skype pour les entreprises et Outlook en même temps sur des stations de travail.</span><span class="sxs-lookup"><span data-stu-id="4279e-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="4279e-120">Boîtes aux lettres partagées ne sont pas pris en charge pour Skype pour la délégation d’entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="4279e-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="4279e-121">Il s’agit, car la liste de contrôle d’accès (ACL) **sendonbehalf** ne possède pas de la boîte aux lettres partagée.</span><span class="sxs-lookup"><span data-stu-id="4279e-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="4279e-122">Skype pour la prise en charge de la version entreprise client</span><span class="sxs-lookup"><span data-stu-id="4279e-122">Skype for Business client version support</span></span>

||<span data-ttu-id="4279e-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="4279e-123">**Outlook 2013**</span></span>|<span data-ttu-id="4279e-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="4279e-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4279e-125">**Lync/Skype pour le Client de base Business**</span><span class="sxs-lookup"><span data-stu-id="4279e-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="4279e-126">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="4279e-126">Not supported</span></span> |<span data-ttu-id="4279e-127">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="4279e-127">Not supported</span></span>
|<span data-ttu-id="4279e-128">**Skype Entreprise 2015**</span><span class="sxs-lookup"><span data-stu-id="4279e-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="4279e-129">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="4279e-129">Supported</span></span>| <span data-ttu-id="4279e-130">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="4279e-130">Supported</span></span>|
|<span data-ttu-id="4279e-131">**Skype pour Business 2016**</span><span class="sxs-lookup"><span data-stu-id="4279e-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="4279e-132">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="4279e-132">Supported</span></span>| <span data-ttu-id="4279e-133">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="4279e-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="4279e-134">Conditions de licence</span><span class="sxs-lookup"><span data-stu-id="4279e-134">Licensing requirements</span></span>

<span data-ttu-id="4279e-135">**Scénario de licence entreprise E3**</span><span class="sxs-lookup"><span data-stu-id="4279e-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="4279e-136">**Licence**</span><span class="sxs-lookup"><span data-stu-id="4279e-136">**License**</span></span>|<span data-ttu-id="4279e-137">**Clients**</span><span class="sxs-lookup"><span data-stu-id="4279e-137">**Clients**</span></span>|<span data-ttu-id="4279e-138">**Remarques**</span><span class="sxs-lookup"><span data-stu-id="4279e-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4279e-139">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="4279e-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="4279e-140">Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4279e-141">Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="4279e-142">Skype pour le client Business base ne gère pas la délégation.</span><span class="sxs-lookup"><span data-stu-id="4279e-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4279e-143">Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.</span><span class="sxs-lookup"><span data-stu-id="4279e-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="4279e-144">Entreprise E3 avec Office 365 Phone System + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="4279e-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="4279e-145">Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4279e-146">Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4279e-147">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="4279e-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="4279e-148">Skype pour le client Business base ne gère pas la délégation.</span><span class="sxs-lookup"><span data-stu-id="4279e-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4279e-149">Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.</span><span class="sxs-lookup"><span data-stu-id="4279e-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="4279e-150">**Scénario de licence entreprise E5**</span><span class="sxs-lookup"><span data-stu-id="4279e-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="4279e-151">**Licence**</span><span class="sxs-lookup"><span data-stu-id="4279e-151">**License**</span></span>|<span data-ttu-id="4279e-152">**Clients**</span><span class="sxs-lookup"><span data-stu-id="4279e-152">**Clients**</span></span>|<span data-ttu-id="4279e-153">**Remarques**</span><span class="sxs-lookup"><span data-stu-id="4279e-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4279e-154">E5 d’entreprise</span><span class="sxs-lookup"><span data-stu-id="4279e-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="4279e-155">Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou 2016 Outlook.</span><span class="sxs-lookup"><span data-stu-id="4279e-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="4279e-156">Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="4279e-157">Skype pour le client Business base ne gère pas la délégation.</span><span class="sxs-lookup"><span data-stu-id="4279e-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4279e-158">Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.</span><span class="sxs-lookup"><span data-stu-id="4279e-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="4279e-159">E5 Enterprise plus Plan d’appel Office 365</span><span class="sxs-lookup"><span data-stu-id="4279e-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="4279e-160">Skype pour les entreprises pour Mac 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="4279e-161">Lync 2013 (Skype pour Business 2015) utilisés avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4279e-162">Skype pour 2016 Business utilisés avec Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4279e-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4279e-163">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="4279e-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="4279e-164">Skype pour le client Business base ne gère pas la délégation.</span><span class="sxs-lookup"><span data-stu-id="4279e-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4279e-165">Pour les clients Mac, vous pouvez déléguer des appels, mais pas de réunions.</span><span class="sxs-lookup"><span data-stu-id="4279e-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="4279e-166">Configurer et vérifier la délégation</span><span class="sxs-lookup"><span data-stu-id="4279e-166">Set up and verify delegation</span></span>

<span data-ttu-id="4279e-167">Pour configurer Skype pour la délégation d’entreprise en ligne, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4279e-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="4279e-168">Pour les clients Windows</span><span class="sxs-lookup"><span data-stu-id="4279e-168">For Windows clients</span></span>

 <span data-ttu-id="4279e-169">**Onglet de transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="4279e-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="4279e-170">Sélectionnez **Outils** > **Options** > **paramètres de transfert d’appel**.</span><span class="sxs-lookup"><span data-stu-id="4279e-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="4279e-171">Sélectionnez **Modifier mes membres délégués**.</span><span class="sxs-lookup"><span data-stu-id="4279e-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="4279e-172">Sélectionnez **Ajouter**, sélectionnez le délégué que vous souhaitez ajouter, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="4279e-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="4279e-173">**Aucun onglet transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="4279e-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="4279e-174">Dans Outlook, sélectionnez le **fichier** > **Paramètres du compte** > **Accès délégué** > **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4279e-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="4279e-175">Recherchez, puis ajoutez le nom de la personne qui doit être le délégué.</span><span class="sxs-lookup"><span data-stu-id="4279e-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="4279e-176">Sélectionnez le menu **calendrier** , puis sélectionnez **éditeur (peut lire, créer et modifier des éléments)**.</span><span class="sxs-lookup"><span data-stu-id="4279e-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="4279e-177">Pour les clients Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="4279e-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="4279e-178">**Onglet de transfert d’appel**</span><span class="sxs-lookup"><span data-stu-id="4279e-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="4279e-179">Si le client ne possède pas un onglet **Transfert d’appel** qui contient le lien **Modifier mes membres délégués** , et la personne qui se trouve sur un ordinateur Mac, la personne doit se connecter à un ordinateur fonctionnant sous Windows afin de configurer la délégation.</span><span class="sxs-lookup"><span data-stu-id="4279e-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="4279e-180">Il s’agit, car les clients Mac ne peut pas établir des connexions de MAPI, et il s’agit d’une condition requise pour établir une relation Skype pour la délégation d’entreprise à partir d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="4279e-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="4279e-181">Vérifier la réussite</span><span class="sxs-lookup"><span data-stu-id="4279e-181">Verify success</span></span>

<span data-ttu-id="4279e-182">Si le programme d’installation se déroule correctement, le délégué doit voir **que vous avez été ajouté en tant que délégué pour < nom >** message et que le groupe de **personnes dont je gérer les appels pour** est créé.</span><span class="sxs-lookup"><span data-stu-id="4279e-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="4279e-183">La personne qui a délégué doit voir que le groupe de **délégués** est créé.</span><span class="sxs-lookup"><span data-stu-id="4279e-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4279e-184">Autorisations de délégation apparaissent généralement dans les 30 minutes au processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="4279e-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="4279e-185">Toutefois, ce processus peut prendre jusqu'à 24 heures.</span><span class="sxs-lookup"><span data-stu-id="4279e-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="4279e-186">Identification et résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="4279e-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="4279e-187">Problèmes courants</span><span class="sxs-lookup"><span data-stu-id="4279e-187">Common issues</span></span>

- > <span data-ttu-id="4279e-188">**Problème 1** L’entrée de délégué continue d’apparaître dans le groupe de **personnes dont je gérer les appels pour** une fois que la personne a supprimé le délégué à partir du client Outlook.</span><span class="sxs-lookup"><span data-stu-id="4279e-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="4279e-189">**Résolution 1** Sur Skype pour client d’entreprise, le délégué dans le groupe **délégués** d’avec le bouton droit et sélectionnez **Supprimer du groupe**.</span><span class="sxs-lookup"><span data-stu-id="4279e-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="4279e-190">**Problème 2** Une fois que l’accès délégué est accordé via le client Outlook, le message de confirmation, ni le groupe de **personnes dont je gérer les appels pour** s’affichent pour le délégué.</span><span class="sxs-lookup"><span data-stu-id="4279e-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="4279e-191">**Résolution 2** Supprimer la délégation à partir du client Outlook, attendez environ 15 minutes pour la réplication, puis ajoutez de nouveau le délégué.</span><span class="sxs-lookup"><span data-stu-id="4279e-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="4279e-192">Autres problèmes courants</span><span class="sxs-lookup"><span data-stu-id="4279e-192">Other common issues</span></span>

- <span data-ttu-id="4279e-193">Délégation ne fonctionne pas si le seuil de 25 délégués et les personnes qui 25 délèguent est dépassé.</span><span class="sxs-lookup"><span data-stu-id="4279e-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="4279e-194">Le Skype pour le client Business base n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4279e-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4279e-195">Si vous installez le Skype pour le client Business base, supprime et rompre la délégation.</span><span class="sxs-lookup"><span data-stu-id="4279e-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="4279e-196">Si la valeur **d’État MAPI** n’est pas **OK**, assurez-vous que les valeurs **SIP** et **SMTP** correspondent.</span><span class="sxs-lookup"><span data-stu-id="4279e-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4279e-197">Il peut prendre quelques minutes pour que le statut MAPI à afficher en tant que **OK** une fois que vous commencez Skype pour les entreprises et Outlook.</span><span class="sxs-lookup"><span data-stu-id="4279e-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="4279e-198">Création d’un groupe de sécurité et ajout d’autorisations de délégation pour ce groupe de sécurité n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4279e-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="4279e-199">MAPI n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="4279e-199">MAPI is unavailable.</span></span> <span data-ttu-id="4279e-200">Voir [l’Erreur « MAPI non disponible » dans Skype pour 2016 Business client](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="4279e-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="4279e-201">La boîte aux lettres Exchange Online n’est pas accessible via le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4279e-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="4279e-202">Si cela se produit, exécutez le [test de connectivité Outlook](https://testconnectivity.microsoft.com/) pour vous assurer qu’il passe.</span><span class="sxs-lookup"><span data-stu-id="4279e-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4279e-203">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4279e-203">Related topics</span></span>
[<span data-ttu-id="4279e-204">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4279e-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4279e-205">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="4279e-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
