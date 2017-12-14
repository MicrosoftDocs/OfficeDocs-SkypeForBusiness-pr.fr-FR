---
title: "Télécharger et installer Windows PowerShell 3.0"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: LIL_Placement
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4

description: "Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online."
---

# Télécharger et installer Windows PowerShell 3.0

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](d739cd71-3c18-42ea-879f-b408bf53b1f4.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/d739cd71-3c18-42ea-879f-b408bf53b1f4). 
  
Si vous utilisez Windows 8.1, Windows 8, Windows Server 2012 R2 ou Windows Server 2012, vous disposez déjà de Windows PowerShell 3.0. C'est parce que cette application est préinstallée avec les systèmes d'exploitation.
  
Si vous exécutez Windows 7 ou Windows Server 2008 R2, vous pouvez également exécuter Windows PowerShell 3.0. Toutefois, il est également possible que vous utilisez peut-être version 2.0 à la place, la version fournis avec les systèmes d'exploitation. Pour déterminer la version de Microsoft PowerShell l que vous utilisez, procédez comme suit sur votre ordinateur Windows 7 ou Windows Server 2008 R2:
  
1. Cliquez sur **Démarrer**, cliquez sur **Tous les programmes**, sur **Accessoires**, cliquez sur **Windows PowerShell**, puis cliquez sur **Windows PowerShell**.
    
2. Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :
    
  ```
  Get-Host | Select-Object Version
  ```

3. Informations semblables à ce qui suit puis doivent être affichées dans la fenêtre de la console :
    
  ```
  Version
-------
3.0
  ```

Si le numéro de Version retourné est 3.0, vous exécutez Windows PowerShell 3.0. Si le numéro de Version retourné n'est pas 3.0, vous devez installer Windows PowerShell 3.0. Vous pouvez télécharger Windows Management Framework 3.0, qui inclut Windows PowerShell 3.0, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Une fois que vous avez vérifié que Windows PowerShell 3.0 est installé, vous devez vous assurer que PowerShell a été configuré pour exécuter des scripts à distance. Pour ce faire, démarrez PowerShell en tant qu'administrateur. Dans Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, procédez comme suit :
  
1. Cliquez sur **Démarrer** et cliquez sur **Tous les programmes**, sur **Accessoires**, cliquez sur **Windows PowerShell**, avec le bouton droit de **Windows PowerShell**, puis cliquez sur **Exécuter en tant qu'administrateur**.
    
2. Si la boîte de dialogue **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous souhaitez exécuter PowerShell sous informations d'identification d'administrateur.
    
Si vous exécutez Windows 8, effectuer cette procédure à la place :
  
1. Accéder à la barre d'icônes et cliquez sur **Rechercher**, puis cliquez sur **Windows PowerShell**. Vous pouvez accéder rapidement à la barre d'icônes sur n'importe quel ordinateur Windows 8 (écran tactile ou non tactiles écran) en maintenant la touche Windows enfoncée et en appuyant sur C.
    
2. Dans la barre d'outils en bas de l'écran, cliquez sur **Exécuter en tant qu'administrateur**.
    
3. Si la boîte de dialogue **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous souhaitez exécuter PowerShell sous informations d'identification d'administrateur.
    
Une fois que PowerShell est en cours d'exécution, vous devez modifier la stratégie d'exécution pour autoriser l'exécution de scripts à distance. Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :
  
```
Set-ExecutionPolicy RemoteSigned -Force
```

> [!NOTE]
> Lorsque vous exécutez la commande précédente, vous pouvez recevoir le message d'erreur suivant : > Set-ExecutionPolicy : Accéder à la key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell du Registre » est refusé. > En règle générale, ce message d'erreur se produit si vous exécutez pas PowerShell sous informations d'identification d'administrateur. Fermez votre session de PowerShell et démarrer une nouvelle session en tant qu'administrateur. 
  
Pour vérifier que la stratégie d'exécution a été configurée correctement, tapez ce qui suit à l'invite PowerShell et appuyez sur ENTRÉE :
  
```
Get-ExecutionPolicy
```

Si vous revenir la valeur suivante, puis tout a été correctement configuré :
  
```
RemoteSigned
```

Si vous exécutez pas actuellement Windows PowerShell 3.0, vous devez également télécharger et installer Windows Management Framework 3.0 à partir du Microsoft Download Center. Il s'agit d'un package d'installation qui inclut Windows PowerShell 3.0 et gestion à distance Windows (WinRM) 3.0. Le package d'installation peut être nécessaire si vous exécutez Windows 7 et n'avez pas encore mis à jour à Windows PowerShell 3.0. Si vous exécutez Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, il convient inutile d'installer Windows PowerShell 3.0. Windows PowerShell 3.0 est préinstallé sur les systèmes d'exploitation.
  
Avant d'installer Windows Management Framework 3.0 :
  
- Vérifiez que vous avez téléchargé la version correcte du package d'installation. Si vous exécutez la version 64 bits de Windows 7, téléchargez le fichier Windows6. 1-KB2506143-x 64.msu. Si vous exécutez la version 32 bits de Windows 7, téléchargez le fichier Windows6. 1-KB2506143-x 86.
    
- Si vous exécutez Windows 7 sur votre ordinateur, vérifiez que vous avez installé Windows 7 Service Pack 1.
    
Si vous ne savez pas quelle version de Windows que vous exécutez, ou vous ne savez pas si vous avez installé Windows 7 Service Pack 1, cliquez sur **Démarrer**, cliquez sur **ordinateur** et puis cliquez sur **Propriétés**. Ces informations seront signalées dans la boîte de dialogue système.
  
Pour installer Windows Management Framework 3.0, procédez comme suit :
  
1. Double-cliquez sur la. Fichier d'installation MSU ( **Windows6. 1-KB2506143-x 64.msu** ou **Windows6. 1-KB2506143-x 86** ).
    
2. Dans l'Assistant télécharger et installer les mises à jour, dans la page **lire ces termes de licence (1 / 1)**, cliquez sur **J'accepte**.
    
3. Une fois l'installation terminée, cliquez sur **Redémarrer maintenant** pour redémarrer votre ordinateur.
    
Une fois que l'ordinateur a redémarré, vérifiez que Windows PowerShell peut démarrer et que l'application peut être exécutée sous informations d'identification d'administration. Pour cela :
  
1. Cliquez sur **Démarrer**, **Tous les** programmes, sur **Accessoires**, cliquez sur **Windows PowerShell**, avec le bouton droit de **Windows PowerShell**, puis sur **Exécuter en tant qu'administrateur**.
    
2. Si la boîte de dialogue contrôle de compte d'utilisateur apparaît, cliquez sur **Oui** pour confirmer que vous souhaitez exécuter PowerShell sous informations d'identification d'administrateur.
    
Lorsque la console PowerShell s'affiche, vous devez ensuite vérifier que le service WinRM est en cours d'exécution et qu'il a été configuré correctement. Pour vérifier que le service est en cours d'exécution, tapez la commande suivante à l'invite PowerShell et appuyez sur ENTRÉE :
  
```
Get-Service winrm
```

Informations sur le service WinRM puis apparaîtra sur écran :
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

Si le service d'état est différent de « En cours d'exécution », démarrez le service WinRM en appuyant sur la commande suivante et appuyez sur ENTRÉE :
  
```
Start-Service winrm
```

Une fois que le service a démarré, exécutez la commande suivante pour vous assurer que WinRM utilise l'authentification de base :
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Informations semblables au suivant seront affiche à l'écran :
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

Si l'authentification de base a été définie sur true, puis que vous êtes prêt à utiliser PowerShell pour vous connecter à Skype Entreprise Online.
  
||
|:-----|
|![Petit icône de LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Vous débutez dans Office 365 ?**         Découvrez les cours vidéo gratuits destinés aux administrateurs **Office 365 et aux professionnels de l'informatique**, proposés par LinkedIn Learning. |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

