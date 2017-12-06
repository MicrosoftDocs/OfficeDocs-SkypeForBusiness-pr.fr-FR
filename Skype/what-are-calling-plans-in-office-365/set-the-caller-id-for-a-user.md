---
title: "Définir l'ID d'appelant d'un utilisateur"
ms.author: tonysmit
author: tonysmit
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
description: "Le système téléphonique dans Office 365 fournit un ID de l'appelant par défaut est le numéro de téléphone affectées de l'utilisateur. Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé un ID de ligne de l'appel) pour un utilisateur. Vous pouvez en savoir plus sur l'utilisation des ID de l'appelant dans votre organisation en accédant Comment utiliser un ID d'appelant dans votre organisation."
---

# Définir l'ID d'appelant d'un utilisateur

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](c7323490-d9b7-421a-aa76-5bd485f80583.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/c7323490-d9b7-421a-aa76-5bd485f80583). 
  
Le système téléphonique dans Office 365 fournit un ID de l'appelant par défaut est le numéro de téléphone affectées de l'utilisateur. Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé un ID de ligne de l'appel) pour un utilisateur. Vous pouvez en savoir plus sur l'utilisation des ID de l'appelant dans votre organisation en accédant [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Vous ne pouvez pas bloquer les appels entrants actuellement dans Skype entreprise Online. 
  
Vous pouvez changer les paramètres suivants :
  
> [!NOTE]
> Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.
  
- **Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).
    
    > [!NOTE]
    > Si vous souhaitez utiliser le paramètre  _Service_, vous devez spécifier un numéro de service valide. 
  
- **Bloc de leur ID d'appelant sortant** Vous pouvez bloquer l'ID d'appelant sortant l'envoi aux appels sortants PSTN d'un utilisateur. Cette opération se bloque son numéro de téléphone ne soient pas affichées sur le téléphone d'une personne appelée.
    
- **Bloc de leur ID de l'appelant entrant** Vous pouvez empêcher un utilisateur reçoive les ID de l'appelant dans n'importe quel PSTN les appels entrants.
    
> [!IMPORTANT]
> Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur. 
  
Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.
  
Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## Définir vos paramètres de stratégie d'ID d'appelant

> [!NOTE]
> Pour tous les ID de l'appelant dans les paramètres du Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype centre d'administration entreprise**. 
  
### Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
1. Dans le **menu Démarrer**, recherchez **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

    Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
    
### Voir l'ensemble des paramètres de stratégie d'ID d'appelant de votre organisation

- Pour afficher tous les paramètres de stratégie de ID de l'appelant dans votre organisation, exécutez :
    
  - 
  ```
  Get-CsCallingLineIdentity |fl
  ```

    Voir obtenir des exemples et des détails pour [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).
    
### Créer une stratégie d'ID d'appelant pour votre organisation

- Pour créer une nouvelle stratégie de ID d'appelant qui définit l'ID d'appelant anonyme, exécutez :
    
  - 
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

    Voir obtenir des exemples et des détails pour [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
- Pour appliquer la nouvelle stratégie que vous avez créé à Amos marbre, exécutez :
    
  - 
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```

    En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l'applet de commande [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l'applet de commande[Grant CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### Définir la stratégie de manière à bloquer l'ID d'appelant

- Pour bloquer l'ID d'appelant entrants, exécutez :
    
  - 
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```

    Pour [Définir CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx), consultez obtenir des exemples et des détails.
    
- Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :
    
  - 
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```

    En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
### Stratégie de suppression dʼID dʼappelant

Pour supprimer une stratégie de votre organisation, exécutez :
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```

Pour supprimer une stratégie dʼun utilisateur, exécutez :
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```

## Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Rubriques connexes

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)
  
[Période de sortant gratuit de audio conférence](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

