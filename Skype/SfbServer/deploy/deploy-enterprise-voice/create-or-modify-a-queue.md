---
title: Création ou modification d’une file d’attente dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Créez ou modifiez une file d’attente de Response Group dans Skype entreprise Server Voice.
ms.openlocfilehash: 8cd306e849eeddd8a11b76604826084c0eb9b41d
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767867"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="010b5-103">Création ou modification d’une file d’attente dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="010b5-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="010b5-104">Créez ou modifiez une file d’attente de Response Group dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="010b5-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="010b5-105">Les files d’attente contiennent les appelants tant qu’un agent ne répond pas à l’appel.</span><span class="sxs-lookup"><span data-stu-id="010b5-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="010b5-106">Lorsque l’application de Response Group recherche un agent disponible, elle effectue une recherche dans les groupes d’agents dans l’ordre de leur liste.</span><span class="sxs-lookup"><span data-stu-id="010b5-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="010b5-107">Vous pouvez sélectionner les groupes d’agents affectés à la file d’attente et spécifier le comportement de la file d’attente, par exemple pour limiter le nombre d’appels qui peuvent être maintenus par la file d’attente et la durée pendant laquelle l’agent attend la réponse à l’appel.</span><span class="sxs-lookup"><span data-stu-id="010b5-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="010b5-108">Utilisez l’une des procédures suivantes pour créer ou modifier une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="010b5-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="010b5-109">Utiliser le panneau de configuration Skype entreprise Server pour créer ou modifier une file d’attente</span><span class="sxs-lookup"><span data-stu-id="010b5-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="010b5-110">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="010b5-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="010b5-111">Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des files d’attente de groupes Response Group et les affecter aux flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="010b5-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="010b5-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="010b5-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="010b5-113">Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **File d’attente**.</span><span class="sxs-lookup"><span data-stu-id="010b5-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="010b5-114">Dans la page **File d’attente**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="010b5-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="010b5-115">Pour créer une file d’attente, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="010b5-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="010b5-116">Dans **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** où vous voulez ajouter la file d’attente dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="010b5-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="010b5-117">Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="010b5-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="010b5-p103">Pour modifier une file d’attente existante, tapez entièrement ou partiellement le nom de la file d’attente dans le champ de recherche. Dans la liste des files d’attente obtenue, cliquez sur la file d’attente souhaitée, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="010b5-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="010b5-120">Dans **Nom**, tapez un nom d’identification pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="010b5-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="010b5-121">Dans **Description**, tapez une description pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="010b5-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="010b5-p104">Dans **Groupes**, spécifiez les groupes que vous voulez affecter à la file d’attente. Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="010b5-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="010b5-p105">Pour ajouter un groupe à la file d’attente, cliquez sur **Sélectionner**. Dans le champ de recherche **Sélectionner des groupes**, tapez entièrement ou partiellement le nom du groupe d’agents que vous voulez affecter à la file d’attente, cliquez sur le groupe d’agents souhaité, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="010b5-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="010b5-126">Pour supprimer un groupe de la file d’attente, dans la zone des groupes d’agents, cliquez sur le groupe que vous voulez supprimer, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="010b5-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="010b5-127">Pour modifier l’ordre de recherche des agents, cliquez sur un groupe dans la liste des groupes d’agents, puis sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="010b5-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="010b5-p106">Lorsque le serveur recherche un agent disponible pour la file d’attente, il suit l’ordre des groupes. Autrement dit, la recherche s’effectue d’abord dans le premier groupe de la liste, puis dans le deuxième, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="010b5-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="010b5-130">Pour spécifier une durée maximale pendant laquelle un appelant peut être mis en attente avant qu’un agent prenne l’appel, activez la case à cocher **Activer le délai d’expiration de la file d’attente**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="010b5-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="010b5-131">a.</span><span class="sxs-lookup"><span data-stu-id="010b5-131">a.</span></span> <span data-ttu-id="010b5-132">Dans **Délai d’expiration (secondes)**, spécifiez la durée maximale en secondes pendant laquelle un appelant peut attendre qu’un agent prenne l’appel.</span><span class="sxs-lookup"><span data-stu-id="010b5-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="010b5-133">b.</span><span class="sxs-lookup"><span data-stu-id="010b5-133">b.</span></span> <span data-ttu-id="010b5-134">Dans **Action d’appel**, sélectionnez l’action effectuée lorsqu’un appel arrive à expiration, comme suit :</span><span class="sxs-lookup"><span data-stu-id="010b5-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="010b5-135">Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.</span><span class="sxs-lookup"><span data-stu-id="010b5-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="010b5-136">Pour transférer l’appel vers la messagerie vocale, cliquez sur **transférer vers la messagerie vocale**, puis dans le champ **adresse SIP** , tapez une adresse de messagerie vocale au format SIP : \* \<nom d'\>utilisateur\*@ \*\<nom_domaine\> \* (par exemple, SIP :Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="010b5-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="010b5-137">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **transférer vers le numéro de téléphone**, puis dans le champ **adresse SIP** , tapez le numéro de téléphone dans le format SIP : \* \<numéro\>\*@ \*\<nom_domaine\> \* (par exemple, SIP :+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="010b5-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="010b5-138">Pour transférer l’appel vers un autre utilisateur, cliquez sur **transférer vers l’adresse SIP**, puis dans le champ **adresse SIP** , tapez l’URI de l’utilisateur au format SIP _ \<:\>nom d'_@ _\<utilisateur NomDomaine\>_.</span><span class="sxs-lookup"><span data-stu-id="010b5-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="010b5-139">Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="010b5-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="010b5-140">Pour spécifier un nombre maximal d’appels pouvant être stockés dans la file d’attente, activez la case à cocher **Activer le débordement de la file d’attente**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="010b5-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="010b5-141">a.</span><span class="sxs-lookup"><span data-stu-id="010b5-141">a.</span></span> <span data-ttu-id="010b5-142">Dans **Nombre maximal d’appels**, sélectionnez le nombre maximal d’appels que la file d’attente doit contenir.</span><span class="sxs-lookup"><span data-stu-id="010b5-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="010b5-143">b.</span><span class="sxs-lookup"><span data-stu-id="010b5-143">b.</span></span> <span data-ttu-id="010b5-144">Dans **Transférer l’appel**, sélectionnez l’appel à transférer lorsque la file d’attente est pleine : **Appel le plus récent** ou **Appel le plus ancien**.</span><span class="sxs-lookup"><span data-stu-id="010b5-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="010b5-145">c.</span><span class="sxs-lookup"><span data-stu-id="010b5-145">c.</span></span> <span data-ttu-id="010b5-146">Dans **Action d’appel**, sélectionnez l’action à effectuer lorsque le seuil de saturation est atteint :</span><span class="sxs-lookup"><span data-stu-id="010b5-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="010b5-147">Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.</span><span class="sxs-lookup"><span data-stu-id="010b5-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="010b5-148">Pour transférer l’appel vers la messagerie vocale, cliquez sur **transférer vers la messagerie vocale**, puis dans le champ **adresse SIP** , tapez une adresse de messagerie vocale au format SIP : \* \<nom d'\>utilisateur\*@ \*\<nom_domaine\> \* (par exemple, SIP :Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="010b5-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="010b5-149">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **transférer vers le numéro de téléphone**, puis dans le champ **adresse SIP** , tapez le numéro de téléphone dans le format SIP : \* \<numéro\>\*@ \*\<nom_domaine\> \* (par exemple, SIP :+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="010b5-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="010b5-150">Pour transférer l’appel vers un autre utilisateur, cliquez sur **transférer vers l’adresse SIP**, puis dans le champ **adresse SIP** , tapez l’URI de l’utilisateur au format SIP _ \<:\>nom d'_@ _\<utilisateur NomDomaine\>_.</span><span class="sxs-lookup"><span data-stu-id="010b5-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="010b5-151">Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="010b5-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="010b5-152">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="010b5-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="010b5-153">Pour utiliser Skype entreprise Server Management Shell pour créer ou modifier une file d’attente</span><span class="sxs-lookup"><span data-stu-id="010b5-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="010b5-154">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="010b5-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="010b5-155">Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des groupes d’agents et des files d’attente, puis affecter des groupes d’agents à des files d’attente.</span><span class="sxs-lookup"><span data-stu-id="010b5-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="010b5-156">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="010b5-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="010b5-p112">Créez le message à lire lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="010b5-159">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="010b5-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="010b5-160">Pour utiliser un fichier audio pour l’invite, utilisez l’applet de commande **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="010b5-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="010b5-161">Pour plus d’informations, voir [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="010b5-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="010b5-p114">Définissez l’action à exécuter lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="010b5-164">Pour plus d’informations sur les actions possibles et leur syntaxe, voir [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="010b5-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="010b5-165">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="010b5-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="010b5-p115">Créez le message à lire lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="010b5-168">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="010b5-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="010b5-169">Pour utiliser un fichier audio pour l’invite, utilisez l’applet de commande **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="010b5-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="010b5-170">Pour plus d’informations, voir [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="010b5-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="010b5-p117">Définissez l’action à exécuter lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="010b5-173">Pour plus d’informations sur les actions possibles et leur syntaxe, voir [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="010b5-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="010b5-174">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="010b5-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="010b5-p118">Récupérez le nom de service du service Response Group et affectez-le à une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p118">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="010b5-p119">Obtenez l’identité du groupe d’agents à affecter à la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p119">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="010b5-179">Pour plus d’informations sur la création d’un groupe d’agents, voir [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="010b5-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="010b5-p120">Créez la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p120">Create the queue. At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="010b5-182">Exemple :</span><span class="sxs-lookup"><span data-stu-id="010b5-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="010b5-p121">Vérifiez que la file d’attente est créée. Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="010b5-p121">Confirm that the queue is created. Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="010b5-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="010b5-185">See also</span></span>

[<span data-ttu-id="010b5-186">Nouveau-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="010b5-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="010b5-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="010b5-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="010b5-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="010b5-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="010b5-189">Nouveau-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="010b5-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="010b5-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="010b5-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="010b5-191">Importation-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="010b5-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="010b5-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="010b5-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
