---
title: Télécharger et installer 5,1 PowerShell Windows
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Téléchargez, installez, puis utilisez Windows PowerShell 5,1 pour créer une session PowerShell distante qui se connecte à Skype entreprise online.
ms.openlocfilehash: 5afca0ef1fd5d7437c3974de1424a664c99ab1a1
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701553"
---
# <a name="download-and-install-windows-powershell-51"></a>Télécharger et installer 5,1 PowerShell Windows

Si vous utilisez la mise à jour anniversaire Windows 10 ou Windows Server 2016, vous devez déjà disposer de Windows PowerShell 5,1. Cette application est en effet pré-installée sur ces systèmes d'exploitation.
  
Pour déterminer la version de Microsoft PowerShell que vous utilisez, procédez comme suit sur votre ordinateur Windows 7 ou Windows Server 2008 R2 ou Windows Server 2012:
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell** et enfin sur **Windows PowerShell**.
    
2. Dans la console PowerShell, tapez la commande suivante, puis appuyez sur entrée:
    
   ```
   Get-Host | Select-Object Version
   ```

3. Des informations similaires à celles-présentées ci-dessous doivent s'afficher dans la fenêtre de console :
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Si le numéro de version retourné est 5,1, cela signifie que vous exécutez Windows PowerShell 5,1. Si le numéro de version retourné n’est pas 5,1, vous devez installer Windows PowerShell 5,1. Vous pouvez télécharger Windows Management Framework 5,1, qui inclut Windows PowerShell 5,1, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).
  
Une fois que vous avez vérifié que Windows PowerShell 5,1 est installé, vous devez vous assurer que PowerShell a été configuré pour exécuter des scripts distants. Pour cela, démarrez PowerShell en tant qu’administrateur. Sous Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, procédez comme suit :
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.
    
2. Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Si vous utilisez Windows 8, effectuer la procédure suivante à la place :
  
1. Accédez à la barre des talismans, cliquez sur **Rechercher** puis faites un clic droit sur **Windows PowerShell**. Vous pouvez accéder rapidement à la barre des talismans à partir de n'importe quel ordinateur Windows 8 (tactile ou non) en maintenant la touche Windows et en appuyant sur C.
    
2. Dans la barre d’outils située en bas de l’écran, cliquez sur **Exécuter en tant qu’administrateur**.
    
3. Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Après l'exécution de PowerShell, vous devez modifier la politique d'exécution pour permettre l'exécution de scripts distants. Dans la console PowerShell, tapez la commande suivante, puis appuyez sur entrée:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Lorsque vous exécutez la commande précédente, le message d'erreur suivant peut s'afficher : > *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* En règle générale, ce message d’erreur s'affiche si vous n’exécutez pas PowerShell en tant qu'administrateur. Fermez votre session PowerShell et démarrez une nouvelle session en tant qu’administrateur.
 
Pour vérifier que la politique d’exécution a été configurée correctement, saisissez l'expression suivante dans l’invite PowerShell et appuyez sur ENTRÉE :
  
```
Get-ExecutionPolicy
```

Si vous obtenez la valeur suivante, c'est que tout a été configuré correctement :
  
`RemoteSigned`

Si vous n’utilisez pas actuellement Windows PowerShell 5,1, vous devez également télécharger et installer l’infrastructure de gestion Windows 5,1 à partir du centre de téléchargement Microsoft. Il s’agit d’un package d’installation qui inclut Windows PowerShell 5,1 et Windows Remote Management (WinRM) 3,0. Ce package d’installation peut être requis si, par exemple, vous exécutez Windows 7 SP1 et que vous n’avez pas encore effectué la mise à jour vers Windows PowerShell 5,1. Si vous exécutez Windows Server 2016 ou la mise à jour anniversaire Windows 10, il est possible que vous n’ayez pas besoin d’installer Windows PowerShell 5,1. Windows PowerShell 5,1 est préinstallé sur ces systèmes d’exploitation.
  
Avant d’installer Windows Management Framework 5,1:
  
- Assurez-vous d'avoir téléchargé la bonne version du package d’installation. Si vous exécutez la version 64 bits de Windows 7 SP1, téléchargez le fichier Win7AndW2K8R2-KB3191566-x64. ZIP. Si vous exécutez la version 32 bits de Windows 7, téléchargez le fichier Win7-KB3191566-x86. ZIP.
    
- Si vous utilisez Windows 7 sur votre ordinateur, assurez-vous d'avoir installé Windows 7 Service Pack 1.

Si vous n'êtes pas certain de la version de Windows que vous utilisez, ou si vous n'êtes pas sûr d'avoir installé Windows 7 Service Pack 1, cliquez sur **Démarrer**, faites un clic droit sur **Ordinateur** puis cliquez sur **Propriétés**. Ces informations seront mentionnées dans la boîte de dialogue Système.
  
Pour installer Windows Management Framework 5,1, suivez la procédure décrite dans [installer et configurer une version WMF 5,1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).
  
Après que l'ordinateur a redémarré, vérifiez que Windows PowerShell démarre correctement et que l'application soit bien exécutée en tant qu'administrateur. Pour:
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.
    
2. Si la boîte de dialogue Contrôle de compte d'utilisateur apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Lorsque la console PowerShell s’affiche, vous devez vérifier que le service WinRM soit bien en cours d’exécution et qu’il ait été configuré correctement. Pour vérifier que le service est bien en cours d’exécution, saisissez la commande suivante dans l’invite PowerShell et appuyez sur ENTRÉE :
  
```
Get-Service winrm
```

Des informations sur le service WinRM s'affichent alors à l’écran :
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Si l'état du service n'est pas « En cours d'exécution », démarrez le service WinRM en saisissant la commande suivante, puis cliquez sur ENTRÉE :
  
```
Start-Service winrm
```

Une fois le service démarré, exécutez la commande suivante pour vous assurer que WinRM utilise une authentification de base :
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Des informations similaires aux éléments suivants s'affichent alors à l’écran :
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Si l’authentification de base a bien été définie sur true, vous êtes prêt à utiliser PowerShell pour une connexion à Skype Entreprise Online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Voir aussi
[Configurer votre ordinateur pour Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
