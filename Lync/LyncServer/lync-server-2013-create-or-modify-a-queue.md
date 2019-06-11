---
title: 'Lync Server 2013: création ou modification d’une file d’attente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Créer ou modifier une file d’attente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Utilisez l’une des procédures suivantes pour créer ou modifier une file d’attente.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Pour utiliser le panneau de configuration de Lync Server pour créer ou modifier une file d’attente

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    <div>
    

    > [!NOTE]  
    > Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des files d’attente de groupes Response Group et les affecter aux flux de travail que vous gérez.

    
    </div>

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **File d’attente**.

4.  Dans la page **File d’attente**, effectuez l’une des opérations suivantes :
    
      - Pour créer une file d’attente, cliquez sur **Nouveau**. Dans **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** où vous voulez ajouter la file d’attente dans le champ de recherche. Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.
    
      - Pour modifier une file d’attente existante, tapez entièrement ou partiellement le nom de la file d’attente dans le champ de recherche. Dans la liste des files d’attente obtenue, cliquez sur la file d’attente souhaitée, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Nom**, tapez un nom d’identification pour la file d’attente.

6.  Dans **Description**, tapez une description pour la file d’attente.

7.  Dans **Groupes**, spécifiez les groupes que vous voulez affecter à la file d’attente. Effectuez l’une des opérations suivantes :
    
      - Pour ajouter un groupe à la file d’attente, cliquez sur **Sélectionner**. Dans le champ de recherche **Sélectionner des groupes**, tapez entièrement ou partiellement le nom du groupe d’agents que vous voulez affecter à la file d’attente, cliquez sur le groupe d’agents souhaité, puis sur **OK**.
    
      - Pour supprimer un groupe de la file d’attente, dans la zone des groupes d’agents, cliquez sur le groupe que vous voulez supprimer, puis sur **Supprimer**.
    
      - Pour modifier l’ordre de recherche des agents, cliquez sur un groupe dans la liste des groupes d’agents, puis sur la flèche vers le haut ou vers le bas.
        
        <div>
        

        > [!NOTE]  
        > Lorsque le serveur recherche un agent disponible pour la file d’attente, il suit l’ordre des groupes. Autrement dit, la recherche s’effectue d’abord dans le premier groupe de la liste, puis dans le deuxième, et ainsi de suite.

        
        </div>

8.  Pour spécifier une durée maximale pendant laquelle un appelant peut être mis en attente avant qu’un agent prenne l’appel, activez la case à cocher **Activer le délai d’expiration de la file d’attente**, puis procédez comme suit :
    
    1.  Dans **Délai d’expiration (secondes)**, spécifiez la durée maximale en secondes pendant laquelle un appelant peut attendre qu’un agent prenne l’appel.
    
    2.  Dans **Action d’appel**, sélectionnez l’action effectuée lorsqu’un appel arrive à expiration, comme suit :
    
    <!-- end list -->
    
      - Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.
    
      - Pour transférer l’appel vers la messagerie vocale, cliquez sur **transférer vers la messagerie vocale**, puis dans le champ **adresse SIP** , tapez une adresse de messagerie vocale au format\<SIP\>@\<:\> nom d’utilisateur nom_domaine (par exemple, SIP: bob@contoso.com).
    
      - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **transférer vers le numéro de téléphone**, puis dans le champ **adresse SIP** , tapez le numéro de téléphone\<dans\>@\<le\> format SIP: numéro nom_domaine (par par exemple, sip:+14255550121@contoso.com).
    
      - Pour transférer l’appel vers un autre utilisateur, cliquez sur **transférer vers l’adresse SIP**, puis dans le champ **adresse SIP** , tapez l’URI de l’utilisateur au format SIP\<:\>@\<nom\>d’utilisateur NomDomaine.
    
      - Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.

9.  Pour spécifier un nombre maximal d’appels pouvant être stockés dans la file d’attente, activez la case à cocher **Activer le débordement de la file d’attente**, puis procédez comme suit :
    
    1.  Dans **Nombre maximal d’appels**, sélectionnez le nombre maximal d’appels que la file d’attente doit contenir.
    
    2.  Dans **Transférer l’appel**, sélectionnez l’appel à transférer lorsque la file d’attente est pleine : **Appel le plus récent** ou **Appel le plus ancien**.
    
    3.  Dans **Action d’appel**, sélectionnez l’action à effectuer lorsque le seuil de saturation est atteint :
    
    <!-- end list -->
    
      - Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.
    
      - Pour transférer l’appel vers la messagerie vocale, cliquez sur **transférer vers la messagerie vocale**, puis dans le champ **adresse SIP** , tapez une adresse de messagerie vocale au format\<SIP\>@\<:\> nom d’utilisateur nom_domaine (par exemple, SIP: bob@contoso.com).
    
      - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **transférer vers le numéro de téléphone**, puis dans le champ **adresse SIP** , tapez le numéro de téléphone\<dans\>@\<le\> format SIP: numéro nom_domaine (par par exemple, sip:+14255550121@contoso.com).
    
      - Pour transférer l’appel vers un autre utilisateur, cliquez sur **transférer vers l’adresse SIP**, puis dans le champ **adresse SIP** , tapez l’URI de l’utilisateur au format SIP\<:\>@\<nom\>d’utilisateur NomDomaine.
    
      - Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.

10. Cliquez sur **Valider**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Pour utiliser Windows PowerShell pour la création ou la modification d’une file d’attente

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    <div>
    

    > [!NOTE]  
    > Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des groupes d’agents et des files d’attente, puis affecter des groupes d’agents à des files d’attente.

    
    </div>

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Créez le message à lire lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Par exemple :
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Pour utiliser un fichier audio pour l’invite, utilisez l’applet de commande <STRONG>Import-CsRgsAudioFile</STRONG>. Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Définissez l’action à exécuter lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur les actions possibles et leur syntaxe, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Par exemple :
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Créez le message à lire lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Par exemple :
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Pour utiliser un fichier audio pour l’invite, utilisez l’applet de commande <STRONG>Import-CsRgsAudioFile</STRONG>. Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

6.  Définissez l’action à exécuter lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur les actions possibles et leur syntaxe, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Par exemple :
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Récupérez le nom de service du service Response Group et affectez-le à une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Obtenez l’identité du groupe d’agents à affecter à la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur la création d’un groupe d’agents, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A>

    
    </div>

9.  Créez la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Exemple :
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Vérifiez que la file d’attente est créée. Exécutez la commande suivante :
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Nouveau-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[Nouveau-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Importation-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

