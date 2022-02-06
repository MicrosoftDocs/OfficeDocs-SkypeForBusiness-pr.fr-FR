---
title: Créer ou modifier une file d’attente dans Skype Entreprise
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 'Créez ou modifiez une file d’attente Response Group, Skype Entreprise Server Voix Entreprise.'
---

# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Créer ou modifier une file d’attente dans Skype Entreprise
 
Créez ou modifiez une file d’attente Response Group, Skype Entreprise Server Voix Entreprise.
  
Les files d’attente placent les appelants en attente jusqu’à ce qu’un agent réponde à l’appel. Lorsque l’application Response Group recherche un agent disponible, elle recherche les groupes d’agents dans l’ordre dans le but de les lister. Vous pouvez sélectionner les groupes d’agents qui sont affectés à la file d’attente et spécifier le comportement de la file d’attente, par exemple en limitant le nombre d’appels que la file d’attente peut contenir et la période d’attente d’un appel jusqu’à ce qu’un agent réponde à l’appel.
  
Utilisez l’une des procédures suivantes pour créer ou modifier une file d’attente.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Pour utiliser Skype Entreprise Server panneau de commande pour créer ou modifier une file d’attente

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    > [!NOTE]
    > Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des files d’attente de groupes Response Group et les affecter aux flux de travail que vous gérez. 
  
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **File d’attente**.
    
4. Dans la page **File d’attente**, effectuez l’une des opérations suivantes :
    
   - Pour créer une file d’attente, cliquez sur **Nouveau**. Dans **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** où vous voulez ajouter la file d’attente dans le champ de recherche. Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.
    
   - Pour modifier une file d’attente existante, tapez entièrement ou partiellement le nom de la file d’attente dans le champ de recherche. Dans la liste des files d’attente obtenue, cliquez sur la file d’attente souhaitée, sur **Modifier**, puis sur click **Afficher les détails**.
    
5. Dans **Nom**, tapez un nom d’identification pour la file d’attente.
    
6. Dans **Description**, tapez une description pour la file d’attente.
    
7. Dans **Groupes**, spécifiez les groupes que vous voulez affecter à la file d’attente. Effectuez l’une des opérations suivantes : 
    
   - Pour ajouter un groupe à la fille d’attente, cliquez sur **Sélectionner**. Dans le champ de recherche **Sélectionner des groupes**, tapez entièrement ou partiellement le nom du groupe d’agents que vous voulez affecter à la file d’attente, cliquez sur le groupe d’agents souhaité, puis sur **OK**.
    
   - Pour supprimer un groupe de la file d’attente, dans la zone des groupes d’agents, cliquez sur le groupe que vous voulez supprimer, puis sur **Supprimer**.
    
   - Pour modifier l’ordre de recherche des agents, cliquez sur un groupe dans la liste des groupes d’agents, puis sur la flèche vers le haut ou vers le bas.
    
     > [!NOTE]
     > Lorsque le serveur recherche un agent disponible pour la file d’attente, il suit l’ordre des groupes. Autrement dit, la recherche s’effectue d’abord dans le premier groupe de la liste, puis dans le deuxième, et ainsi de suite. 
  
8. Pour spécifier une durée maximale pendant laquelle un appelant peut être mis en attente avant qu’un agent prenne l’appel, activez la case à cocher **Activer le délai d’expiration de la file d’attente**, puis procédez comme suit :
    
    a. Dans **Délai d’expiration (secondes)**, spécifiez la durée maximale en secondes pendant laquelle un appelant peut attendre qu’un agent prenne l’appel.
    
    b. Dans **Action d’appel**, sélectionnez l’action effectuée lorsqu’un appel arrive à expiration, comme suit :
    
   - Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.
    
   - Pour envoyer l’appel à la messagerie vocale, cliquez sur Forward **vers** la messagerie vocale, puis dans le champ d’adresse **SIP** , tapez une adresse de messagerie vocale au format sip: *\<username\>*@ *\<domainname\>* (par exemple, sip:bob@contoso.com).
    
   - Pour passer l’appel vers un autre numéro de téléphone, cliquez sur Forward **vers** le numéro de téléphone, puis dans le champ Adresse **SIP** , tapez le numéro de téléphone au format sip : *\<number\>*@ *\<domainname\>* (par exemple, sip:+14255550121@contoso.com).
    
   - Pour passer l’appel à un autre utilisateur, cliquez sur Forward vers l’adresse **SIP**, puis dans le champ d’adresse **SIP** , tapez l’URI de l’utilisateur au format sip: _\<username\>_@ _\<domainname\>_.
    
   - Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.
    
9. Pour spécifier un nombre maximal d’appels pouvant être stockés dans la file d’attente, activez la case à cocher **Activer le débordement de la file d’attente**, puis procédez comme suit :
    
    a. Dans **Nombre maximal d’appels** sélectionnez le nombre maximal d’appels que la file d’attente doit contenir. 
    
    b. Dans **Transférer l’appel**, sélectionnez l’appel à transférer lorsque la file d’attente est pleine : **Appel le plus récent** ou **Appel le plus ancien**.
    
    c. Dans **Action d’appel**, sélectionnez l’action à effectuer lorsque le seuil de saturation est atteint :
    
   - Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.
    
   - Pour envoyer l’appel à la messagerie vocale, cliquez sur Forward **vers** la messagerie vocale, puis dans le champ d’adresse **SIP** , tapez une adresse de messagerie vocale au format sip: *\<username\>*@ *\<domainname\>* (par exemple, sip:bob@contoso.com).
    
   - Pour passer l’appel vers un autre numéro de téléphone, cliquez sur Forward **vers** le numéro de téléphone, puis dans le champ Adresse **SIP** , tapez le numéro de téléphone au format sip : *\<number\>*@ *\<domainname\>* (par exemple, sip:+14255550121@contoso.com).
    
   - Pour passer l’appel à un autre utilisateur, cliquez sur Forward vers l’adresse **SIP**, puis dans le champ d’adresse **SIP** , tapez l’URI de l’utilisateur au format sip: _\<username\>_@ _\<domainname\>_.
    
   - Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.
    
10. Cliquez sur **Valider**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Pour utiliser Skype Entreprise Server Management Shell pour créer ou modifier une file d’attente

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.
    
    > [!NOTE]
    > Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des groupes d’agents et des files d’attente, puis affecter des groupes d’agents à des files d’attente. 
  
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Créez le message à lire lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Par exemple :
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Pour utiliser un fichier audio pour le message, utilisez l’applet de commande **Import-CsRgsAudioFile**. Pour plus d’informations, [voir Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Définissez l’action à exécuter lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Pour plus d’informations sur les actions possibles et leur syntaxe, voir [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Par exemple :
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Créez le message à lire lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Par exemple :
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Pour utiliser un fichier audio pour le message, utilisez l’applet de commande **Import-CsRgsAudioFile**. Pour plus d’informations, [voir Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Définissez l’action à exécuter lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Pour plus d’informations sur les actions possibles et leur syntaxe, voir [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Par exemple :
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Déterminez le nom du service Response Group et affectez-le à une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Obtenez l’identité du groupe d’agents à affecter à la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Pour plus d’informations sur la création du groupe d’agents, voir [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Créez la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Par exemple :
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Vérifiez que la file d’attente est créée. Exécutez la commande suivante :
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>Voir aussi

[New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)