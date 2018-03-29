---
title: Création ou modification d’une file d’attente dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Créer ou modifier une file d’attente du groupe de réponse, dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: a5b76fd8003fcdd4152f57404b14271c4eaa8ef8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-queue-in-skype-for-business-2015"></a>Création ou modification d’une file d’attente dans Skype Entreprise 2015
 
Créer ou modifier une file d’attente du groupe de réponse, dans Skype pour Business Server Voix Entreprise.
  
Files d’attente contiennent des appelants jusqu'à ce qu’un agent répond à l’appel. Lorsque l’application de groupe de réponse recherche un agent disponible, il recherche les groupes de l’agent dans l’ordre que vous les placez. Vous pouvez sélectionner les groupes d’agents qui sont affectés à la file d’attente et de spécifient le comportement de la file d’attente, par exemple pour limiter le nombre d’appels de la file d’attente et de la période pendant laquelle un appel attend jusqu'à ce qu’une réponde d’agent l’appel.
  
Utilisez l’une des procédures suivantes pour créer ou modifier une file d’attente.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Utiliser Skype pour le panneau de configuration de Business Server pour créer ou modifier une file d’attente

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
    > [!NOTE]
    > Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des files d’attente de groupes Response Group et les affecter aux flux de travail que vous gérez. 
  
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **File d’attente**.
    
4. Dans la page **File d’attente**, effectuez l’une des opérations suivantes :
    
   - Pour créer une file d’attente, cliquez sur **Nouveau**. Dans la zone **Sélectionnez un Service**, tapez une partie ou l’intégralité du nom du service **ApplicationServer** où vous souhaitez ajouter la file d’attente dans le champ de recherche. Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.
    
   - Pour modifier une file d’attente existante, tapez entièrement ou partiellement le nom de la file d’attente dans le champ de recherche. Dans la liste des files d’attente obtenue, cliquez sur la file d’attente souhaitée, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Nom**, tapez un nom d’identification pour la file d’attente.
    
6. Dans **Description**, tapez une description pour la file d’attente.
    
7. Dans **Groupes**, spécifiez les groupes que vous voulez affecter à la file d’attente. Effectuez l’une des opérations suivantes : 
    
   - Pour ajouter un groupe à la file d’attente, cliquez sur **Sélectionner**. Dans le champ de recherche **Sélectionner des groupes**, tapez entièrement ou partiellement le nom du groupe d’agents que vous voulez affecter à la file d’attente, cliquez sur le groupe d’agents souhaité, puis sur **OK**.
    
   - Pour supprimer un groupe de la file d’attente, dans la zone des groupes d’agents, cliquez sur le groupe que vous voulez supprimer, puis sur **Supprimer**.
    
   - Pour modifier l’ordre de recherche des agents, cliquez sur un groupe dans la liste des groupes d’agents, puis sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]
    > Lorsque le serveur recherche un agent disponible pour la file d’attente, il suit l’ordre des groupes. Autrement dit, la recherche s’effectue d’abord dans le premier groupe de la liste, puis dans le deuxième, et ainsi de suite. 
  
8. Pour spécifier une durée maximale pendant laquelle un appelant peut être mis en attente avant qu’un agent prenne l’appel, activez la case à cocher **Activer le délai d’expiration de la file d’attente**, puis procédez comme suit :
    
    a. Dans **Délai d’expiration (secondes)**, spécifiez la durée maximale en secondes pendant laquelle un appelant peut attendre qu’un agent prenne l’appel.
    
    b. Dans **Action d’appel**, sélectionnez l’action effectuée lorsqu’un appel arrive à expiration, comme suit :
    
     - Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.
    
     - Pour transférer l’appel à la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**et puis, dans le champ **adresse de SIP** , tapez une adresse de messagerie vocale au format sip : _ \<nom d’utilisateur\>_@ _\<nom_domaine\> _ (pour exemple, sip:bob@contoso.com).
    
     - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Suivant pour le numéro de téléphone**et puis dans le champ **adresse de SIP** , tapez le numéro de téléphone au format sip : _ \<nombre\>_@ _\<nom_domaine\>_ (par exemple, sip:+14255550121@contoso.com).
    
     - Pour transférer l’appel à un autre utilisateur, cliquez sur **transfert à une adresse SIP**et puis, dans le champ **adresse de SIP** , tapez l’URI de l’utilisateur au format sip : _ \<nom d’utilisateur\>_@ _\<nom_domaine\>_.
    
     - Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.
    
9. Pour spécifier un nombre maximal d’appels pouvant être stockés dans la file d’attente, activez la case à cocher **Activer le débordement de la file d’attente**, puis procédez comme suit :
    
    a. Dans **Nombre maximal d’appels**, sélectionnez le nombre maximal d’appels que la file d’attente doit contenir. 
    
    b. Dans **Transférer l’appel**, sélectionnez l’appel à transférer lorsque la file d’attente est pleine : **Appel le plus récent** ou **Appel le plus ancien**.
    
    c. Dans **Action d’appel**, sélectionnez l’action à effectuer lorsque le seuil de saturation est atteint :
    
     - Pour déconnecter l’appel une fois le délai expiré, cliquez sur **Déconnecter**.
    
     - Pour transférer l’appel à la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**et puis, dans le champ **adresse de SIP** , tapez une adresse de messagerie vocale au format sip : _ \<nom d’utilisateur\>_@ _\<nom_domaine\> _ (pour exemple, sip:bob@contoso.com).
    
     - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Suivant pour le numéro de téléphone**et puis dans le champ **adresse de SIP** , tapez le numéro de téléphone au format sip : _ \<nombre\>_@ _\<nom_domaine\>_ (par exemple, sip:+14255550121@contoso.com).
    
     - Pour transférer l’appel à un autre utilisateur, cliquez sur **transfert à une adresse SIP**et puis, dans le champ **adresse de SIP** , tapez l’URI de l’utilisateur au format sip : _ \<nom d’utilisateur\>_@ _\<nom_domaine\>_.
    
     - Pour transférer l’appel vers une autre file d’attente, cliquez sur **Transférer vers une autre file d’attente**, puis accédez à la file d’attente que vous voulez utiliser.
    
10. Cliquez sur **Valider**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Utiliser Skype pour Business Server Management Shell pour créer ou modifier une file d’attente

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
    > [!NOTE]
    > Si vous êtes l’un des responsables des groupes Response Group délégués d’un flux de travail géré, vous pouvez créer ou modifier des groupes d’agents et des files d’attente, puis affecter des groupes d’agents à des files d’attente. 
  
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Créez le message à lire lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Exemple :
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Pour utiliser un fichier audio pour l’invite de commandes, utilisez la cmdlet **Import-CsRgsAudioFile** . Pour plus d’informations, reportez-vous à la section [Importation-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Définissez l’action à exécuter lorsque le seuil d’expiration de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Pour plus d’informations sur les actions possibles et leur syntaxe, consultez [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Exemple :
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Créez le message à lire lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
  ```

   Exemple :
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
  ```

      > [!NOTE]
      > Pour utiliser un fichier audio pour l’invite de commandes, utilisez la cmdlet **Import-CsRgsAudioFile** . Pour plus d’informations, reportez-vous à la section [Importation-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Définissez l’action à exécuter lorsque le seuil de saturation de la file d’attente est atteint, puis enregistrez-le dans une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
  ```
  $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
  ```

    > [!NOTE]
    > Pour plus d’informations sur les actions possibles et leur syntaxe, consultez [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Exemple :
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Récupérez le nom de service du service Response Group et affectez-le à une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Obtenez l’identité du groupe d’agents à affecter à la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Pour plus d’informations sur la création du groupe de l’agent, reportez-vous à la section [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Créez la file d’attente. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Exemple :
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Vérifiez que la file d’attente est créée. Exécutez la commande suivante :
    
   ```
   Get-CsRgsQueue -Name "Help Desk"
   ```

## <a name="see-also"></a>Voir aussi

#### 

[Nouvelle-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Ensemble-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[Nouvelle-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[Nouvelle-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Importation-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Supprimer-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)

