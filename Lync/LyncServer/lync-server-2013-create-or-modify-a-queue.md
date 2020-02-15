---
title: 'Lync Server 2013 : création ou modification d’une file d’attente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1db2211f174c18c160262c1f62c55a178b2cda4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="b2028-102">Création ou modification d’une file d’attente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2028-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2028-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b2028-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b2028-104">Utilisez l’une des procédures suivantes pour créer ou modifier une file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b2028-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="b2028-105">Pour créer ou modifier une file d’attente à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="b2028-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="b2028-106">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="b2028-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2028-107">Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des files d’attente de groupes Response Group et les affecter aux flux de travail que vous gérez.</span><span class="sxs-lookup"><span data-stu-id="b2028-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="b2028-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2028-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b2028-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b2028-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b2028-110">Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **File d’attente**.</span><span class="sxs-lookup"><span data-stu-id="b2028-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="b2028-111">Dans la page **File d’attente**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2028-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b2028-112">Pour créer une file d’attente, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b2028-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="b2028-113">Dans **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** où vous voulez ajouter la file d’attente dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="b2028-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="b2028-114">Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2028-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b2028-p103">Pour modifier une file d’attente existante, tapez entièrement ou partiellement le nom de la file d’attente dans le champ de recherche. Dans la liste des files d’attente obtenue, cliquez sur la file d’attente souhaitée, sur **Modifier**, puis sur click **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b2028-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b2028-117">Dans **Nom**, tapez un nom d’identification pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b2028-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="b2028-118">Dans **Description**, tapez une description pour la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b2028-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="b2028-p104">Dans **Groupes**, spécifiez les groupes que vous voulez affecter à la file d’attente. Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2028-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="b2028-p105">Pour ajouter un groupe à la fille d’attente, cliquez sur **Sélectionner**. Dans le champ de recherche **Sélectionner des groupes**, tapez entièrement ou partiellement le nom du groupe d’agents que vous voulez affecter à la file d’attente, cliquez sur le groupe d’agents souhaité, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2028-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b2028-123">Pour supprimer un groupe de la file d’attente, dans la zone des groupes d’agents, cliquez sur le groupe que vous voulez supprimer, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b2028-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="b2028-124">Pour modifier l’ordre de recherche des agents, cliquez sur un groupe dans la liste des groupes d’agents, puis sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="b2028-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b2028-p106">Lorsque le serveur recherche un agent disponible pour la file d’attente, il suit l’ordre des groupes. Autrement dit, la recherche s’effectue d’abord dans le premier groupe de la liste, puis dans le deuxième, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="b2028-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="b2028-127">Pour spécifier une durée maximale pendant laquelle un appelant peut être mis en attente avant qu’un agent prenne l’appel, activez la case à cocher **Activer le délai d’expiration de la file d’attente**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b2028-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="b2028-128">Dans **Délai d’expiration (secondes)**, spécifiez la durée maximale en secondes pendant laquelle un appelant peut attendre qu’un agent prenne l’appel.</span><span class="sxs-lookup"><span data-stu-id="b2028-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="b2028-129">Dans **Action d’appel**, sélectionnez l’action effectuée lorsqu’un appel arrive à expiration, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b2028-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="b2028-130">Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.</span><span class="sxs-lookup"><span data-stu-id="b2028-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="b2028-131">Pour transférer l’appel vers la messagerie vocale, cliquez sur **transférer à la messagerie vocale**, puis dans le champ **adresse SIP** , tapez une adresse de messagerie vocale au format\<SIP\>@\<:\> NomUtilisateur nom_domaine (par exemple, SIP :Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b2028-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="b2028-132">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **transférer au numéro de téléphone**, puis dans le champ **adresse SIP** , tapez le numéro de téléphone au\<format\>@\<SIP\> : numéro nomdomaine (par exemple, SIP :+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b2028-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="b2028-133">Pour transférer l’appel vers un autre utilisateur, cliquez sur **transférer à l’adresse SIP**, puis dans le champ **adresse SIP** , tapez l’URI de l’utilisateur au format SIP\<:\>@\<NomUtilisateur\>nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="b2028-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="b2028-134">Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="b2028-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="b2028-135">Pour spécifier un nombre maximal d’appels pouvant être stockés dans la file d’attente, activez la case à cocher **Activer le débordement de la file d’attente**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b2028-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="b2028-136">Dans **Nombre maximal d’appels** sélectionnez le nombre maximal d’appels que la file d’attente doit contenir.</span><span class="sxs-lookup"><span data-stu-id="b2028-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="b2028-137">Dans **Transférer l’appel**, sélectionnez l’appel à transférer lorsque la file d’attente est pleine : **Appel le plus récent** ou **Appel le plus ancien**.</span><span class="sxs-lookup"><span data-stu-id="b2028-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="b2028-138">Dans **Action d’appel**, sélectionnez l’action à effectuer lorsque le seuil de saturation est atteint :</span><span class="sxs-lookup"><span data-stu-id="b2028-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="b2028-139">Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.</span><span class="sxs-lookup"><span data-stu-id="b2028-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="b2028-140">Pour transférer l’appel vers la messagerie vocale, cliquez sur **transférer à la messagerie vocale**, puis dans le champ **adresse SIP** , tapez une adresse de messagerie vocale au format\<SIP\>@\<:\> NomUtilisateur nom_domaine (par exemple, SIP :Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b2028-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="b2028-141">Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **transférer au numéro de téléphone**, puis dans le champ **adresse SIP** , tapez le numéro de téléphone au\<format\>@\<SIP\> : numéro nomdomaine (par exemple, SIP :+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b2028-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="b2028-142">Pour transférer l’appel vers un autre utilisateur, cliquez sur **transférer à l’adresse SIP**, puis dans le champ **adresse SIP** , tapez l’URI de l’utilisateur au format SIP\<:\>@\<NomUtilisateur\>nom_domaine.</span><span class="sxs-lookup"><span data-stu-id="b2028-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="b2028-143">Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="b2028-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="b2028-144">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b2028-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="b2028-145">Pour utiliser Windows PowerShell pour créer ou modifier une file d’attente</span><span class="sxs-lookup"><span data-stu-id="b2028-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="b2028-146">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="b2028-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2028-147">Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des groupes d’agents et des files d’attente, puis affecter des groupes d’agents à des files d’attente.</span><span class="sxs-lookup"><span data-stu-id="b2028-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="b2028-148">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b2028-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b2028-p107">Créez le message à lire lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="b2028-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b2028-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2028-152">Pour utiliser un fichier audio pour le message, utilisez l’applet de commande <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b2028-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="b2028-153">Pour plus d’informations, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="b2028-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="b2028-p109">Définissez l’action à exécuter lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2028-156">Pour plus d’informations sur les actions possibles et leur syntaxe, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="b2028-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="b2028-157">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b2028-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="b2028-p110">Créez le message à lire lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="b2028-160">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b2028-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2028-161">Pour utiliser un fichier audio pour le message, utilisez l’applet de commande <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b2028-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="b2028-162">Pour plus d’informations, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="b2028-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="b2028-p112">Définissez l’action à exécuter lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2028-165">Pour plus d’informations sur les actions possibles et leur syntaxe, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="b2028-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="b2028-166">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b2028-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="b2028-167">Récupérez le nom du service Response Group et affectez-le à une variable.</span><span class="sxs-lookup"><span data-stu-id="b2028-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="b2028-168">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="b2028-169">Obtenez l’identité du groupe d’agents à affecter à la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b2028-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="b2028-170">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2028-171">Pour plus d’informations sur la création du groupe d’agents, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="b2028-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="b2028-p115">Créez la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="b2028-174">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b2028-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="b2028-p116">Vérifiez que la file d’attente est créée. Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2028-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2028-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2028-177">See Also</span></span>


[<span data-ttu-id="b2028-178">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b2028-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="b2028-179">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b2028-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="b2028-180">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="b2028-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="b2028-181">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="b2028-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="b2028-182">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b2028-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="b2028-183">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="b2028-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="b2028-184">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="b2028-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

