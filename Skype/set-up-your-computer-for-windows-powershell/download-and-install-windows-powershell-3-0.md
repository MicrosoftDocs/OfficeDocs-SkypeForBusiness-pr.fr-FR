---
title: "Téléchargez et installez Windows PowerShell 3.0"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: "Télécharger, installer et Windows PowerShell 3.0 permet de créer une session PowerShell distante qui se connecte à Skype pour entreprise en ligne."
ms.openlocfilehash: cdcabf75bbcdf53a1553f115af8f678d922a694b
ms.sourcegitcommit: 622dccfbcf2c7a13ac7400dcf9f3900c58ffd37d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2017
---
# <a name="download-and-install-windows-powershell-30"></a>Téléchargez et installez Windows PowerShell 3.0

Si vous utilisez Windows 8.1, Windows 8, Windows Server 2012 R2 ou Windows Server 2012, vous disposez déjà de Windows PowerShell 3.0. C’est parce que cette application est préinstallée sur les systèmes d’exploitation. 
  
Si vous exécutez Windows 7 ou Windows Server 2008 R2, vous pouvez également exécuter Windows PowerShell 3.0. Toutefois, il est également possible que vous utilisez peut-être version 2.0 à la place, la version initialement livrés avec ces systèmes d’exploitation. Pour déterminer la version de Microsoft PowerShelll que vous utilisez, procédez comme suit sur votre ordinateur Windows 7 ou Windows Server 2008 R2 :
  
1. Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez sur **Windows PowerShell**, puis cliquez sur **Windows PowerShell**.
    
2. Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :
    
    ```
   Get-Host | Select-Object Version
   ```

3. Informations semblables au suivant doivent ensuite être affichées dans la fenêtre de console :
    
    ```
    Version
    -------
    3.0
    ```

    Si le numéro de Version renvoyé est 3.0, Windows PowerShell 3.0 sont en cours d’exécution. Si le numéro de Version retourné n’est pas 3.0, vous devez installer Windows PowerShell 3.0. Vous pouvez télécharger Windows Management Framework 3.0, qui inclut Windows PowerShell 3.0, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Après avoir vérifié que Windows PowerShell 3.0 est installé, il se peut que vous devez vous assurer que PowerShell a été configuré pour exécuter des scripts à distance. Pour ce faire, démarrez PowerShell en tant qu’administrateur. Sur Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, effectuez les opérations suivantes :
  
1. Cliquez sur **Démarrer**sur **Tous les programmes**, sur **Accessoires**et cliquez sur **Windows PowerShell**, cliquez sur **Windows PowerShell**, puis cliquez sur **Exécuter en tant qu’administrateur**.
    
2. Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour vérifier que vous souhaitez exécuter PowerShell sous les informations d’identification de l’administrateur.
    
Si vous exécutez Windows 8, effectuez cette procédure à la place :
  
1. Accéder à la barre d’icônes et cliquez sur **Rechercher**, puis cliquez sur **Windows PowerShell**. Vous pouvez accéder rapidement à la barre d’icônes sur n’importe quel ordinateur Windows 8 (écran tactile ou écran tactile-non) en maintenant la touche Windows enfoncée et en appuyant sur la touche C.
    
2. Dans la barre d’outils en bas de l’écran, cliquez sur **Exécuter en tant qu’administrateur**.
    
3. Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour vérifier que vous souhaitez exécuter PowerShell sous les informations d’identification de l’administrateur.
    
Après l’exécution de PowerShell, vous devez modifier la stratégie d’exécution afin de permettre l’exécution de scripts à distance. Dans la console PowerShell, tapez la commande suivante et appuyez sur ENTRÉE :
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
Pour vérifier que la stratégie d’exécution a été configurée correctement, tapez la ligne suivante à l’invite de PowerShell et appuyez sur ENTRÉE :
  
```
Get-ExecutionPolicy
```

Si vous revenir la valeur suivante, puis tout ce qui a été configuré correctement :
  
```
RemoteSigned
```

Si vous n’exécutez pas actuellement Windows PowerShell 3.0, vous devez également télécharger et installer Windows Management Framework 3.0 à partir du Microsoft Download Center. Il s’agit d’un package d’installation qui inclut Windows PowerShell 3.0 et Windows Remote Management (WinRM) 3.0. Ce package d’installation peut être requis si vous exécutez Windows 7 et n’avez pas encore mis à jour pour Windows PowerShell 3.0. Si vous exécutez Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, il ne doit y avoir aucun nécessaire d’installer Windows PowerShell 3.0. Windows PowerShell 3.0 est préinstallé sur les systèmes d’exploitation.
  
Avant d’installer Windows Management Framework 3.0 :
  
- Assurez-vous que vous avez téléchargé la bonne version du package d’installation. Si vous exécutez la version 64 bits de Windows 7, téléchargez le fichier Windows6. 1-KB2506143-x 64.msu. Si vous exécutez la version 32 bits de Windows 7, téléchargez le fichier Windows6. 1-KB2506143-x 86.msu.
    
- Si vous exécutez Windows 7 sur votre ordinateur, assurez-vous que vous avez installé Windows 7 Service Pack 1.
    
Si vous ne savez pas quelle version de Windows vous exécutez, ou vous n’êtes pas sûr si vous avez installé Windows 7 Service Pack 1 et cliquez sur **Démarrer**, cliquez sur **ordinateur**, puis cliquez sur **Propriétés**. Ces informations seront signalées dans la boîte de dialogue.
  
Pour installer Windows Management Framework 3.0, procédez comme suit :
  
1. Double-cliquez sur le. Fichier d’installation MSU ( **package Windows6. 1-KB2506143-x 64.msu** ou **package Windows6. 1-KB2506143-x 86.msu**).
    
2. Dans l’Assistant de téléchargement et installer les mises à jour, dans la page **lire ces termes de la licence (1 / 1)** , cliquez sur **J’accepte**.
    
3. Lorsque l’installation est terminée, cliquez sur **Redémarrer maintenant** pour redémarrer votre ordinateur.
    
Une fois que l’ordinateur a redémarré, vérifiez que Windows PowerShell peut démarrer et que l’application peut être exécutée avec les informations d’identification d’administration. Pour ce faire :
  
1. Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez sur **Windows PowerShell**, avec le bouton droit de **Windows PowerShell** et puis cliquez sur **Exécuter en tant qu’administrateur**.
    
2. Si le contrôle de compte d’utilisateur s’affiche, cliquez sur **Oui** pour vérifier que vous souhaitez exécuter PowerShell sous les informations d’identification d’administrateur.
    
Lorsque la console PowerShell s’affiche, vous devez ensuite vérifier que le service WinRM est en cours d’exécution et qu’il a été configuré correctement. Pour vérifier que le service est en cours d’exécution, tapez la commande suivante à l’invite de PowerShell et appuyez sur ENTRÉE :
  
```
Get-Service winrm
```

Informations sur le service WinRM puis apparaîtra à l’écran :
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

Si le service d’état n’équivaut pas « Exécution », démarrez le service WinRM en tapant la commande suivante, puis appuyez sur ENTRÉE :
  
```
Start-Service winrm
```

Une fois que le service a démarré, exécutez la commande suivante afin de vous assurer que WinRM est l’authentification de base :
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Des informations semblables à ce qui suit seront affiche à l’écran :
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

Si l’authentification de base a été définie sur true, vous êtes prêt à utiliser PowerShell pour se connecter à Skype pour entreprise en ligne.
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 
