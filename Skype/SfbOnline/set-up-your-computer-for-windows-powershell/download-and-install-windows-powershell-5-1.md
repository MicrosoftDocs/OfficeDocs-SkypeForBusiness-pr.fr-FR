---
title: Télécharger et installer Windows PowerShell 5.1
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Télécharger, installer et utiliser Windows PowerShell 5.1 pour créer une session PowerShell distante se connectant à Skype Entreprise Online.
ms.openlocfilehash: 2cbfa65f3170dd516e8bb46365ef663fd237d542
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612833"
---
# <a name="download-and-install-windows-powershell-51"></a>Télécharger et installer Windows PowerShell 5.1

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Si vous utilisez la mise à jour anniversaire Windows 10 ou Windows Server 2016, vous utilisez déjà Windows PowerShell 5.1. En effet, cette application est préinstallée avec ces systèmes d’exploitation.
  
Pour déterminer la version de Microsoft PowerShell que vous utilisez, effectuez les opérations suivante sur votre ordinateur Windows 7 ou Windows Server 2008 R2 ou Windows Server 2012 :
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell** et enfin sur **Windows PowerShell**.
    
2. Dans la console PowerShell, tapez la commande suivante, puis appuyez sur Entrée :
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. Des informations semblables à ce qui suit doivent être affichées dans la fenêtre de la console :
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Si le numéro de version renvoyé est 5.1, c'est que vous utilisez Windows PowerShell 5.1. Si le numéro de version renvoyé n'est pas 5.1, vous devez installer Windows PowerShell 5.1. Vous pouvez télécharger Windows Management Framework 5.1, qui inclut Windows PowerShell 5.1, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=54616).
  
Une fois que vous avez vérifié que Windows PowerShell 5.1 est bien installé, vous devez vous assurer que PowerShell a bien été configuré pour l'exécution de scripts distants. Pour cela, démarrez PowerShell en tant qu’administrateur. Sous Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, procédez comme suit :
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.
    
2. Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Si vous utilisez Windows 8, procédez comme suit :
  
1. Accédez à la barre des icônes, cliquez sur **Rechercher** puis faites un clic droit sur **Windows PowerShell**. Vous pouvez accéder rapidement à la barre des icônes sur un ordinateur Windows 8 (écran tactile ou normal) en maintenant la touche Windows enfoncée, puis en appuyant sur C.
    
2. Dans la barre d’outils située en bas de l’écran, cliquez sur **Exécuter en tant qu’administrateur**.
    
3. Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Après l'exécution de PowerShell, vous devez modifier la politique d'exécution pour permettre l'exécution de scripts distants. Dans la console PowerShell, tapez la commande suivante, puis appuyez sur Entrée :
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Lorsque vous exécutez la commande précédente, le message d'erreur suivant peut s'afficher : > *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* En règle générale, ce message d’erreur s'affiche si vous n’exécutez pas PowerShell en tant qu'administrateur. Fermez votre session PowerShell et démarrez une nouvelle session en tant qu’administrateur.
 
Pour vérifier que la politique d’exécution a été configurée correctement, saisissez l'expression suivante dans l’invite PowerShell et appuyez sur ENTRÉE :
  
```PowerShell
Get-ExecutionPolicy
```

Si vous obtenez la valeur suivante, tout est correctement configuré :
  
`RemoteSigned`

Si vous n'utilisez pas Windows PowerShell 5.1, vous allez également devoir télécharger et installer Windows Management Framework 5.1 à partir du Centre de téléchargement Microsoft. Il s’agit d’un package d’installation qui inclut Windows PowerShell 5.1 et Windows Remote Management (WinRM) 3.0. Ce package d’installation peut être nécessaire si, par exemple, vous utilisez Windows 7 SP1 et n’avez pas encore effectué la mise à jour vers Windows PowerShell 5.1. Si vous utilisez Windows Server 2016 ou la mise à jour anniversaire Windows 10, il n’est pas nécessaire d’installer Windows PowerShell 5.1. Windows PowerShell 5.1 est en effet préinstallé sur ces systèmes d’exploitation.
  
Avant d’installer Windows Management Framework 5.1 :
  
- Vérifiez que vous avez téléchargé la version correcte du package d’installation. Si vous utilisez la version 64 bits de Windows 7 SP1, téléchargez le fichier Win7AndW2K8R2-KB3191566-x64.ZIP. Si vous utilisez la version 32 bits de Windows 7, téléchargez le fichier Win7-KB3191566-x86.ZIP.
    
- Si vous exécutez Windows 7 sur votre ordinateur, vérifiez que vous avez installé Windows 7 Service Pack 1.

Si vous n'êtes pas certain de la version de Windows que vous utilisez, ou si vous n'êtes pas sûr d'avoir installé Windows 7 Service Pack 1, cliquez sur **Démarrer**, faites un clic droit sur **Ordinateur** puis cliquez sur **Propriétés**. Ces informations seront mentionnées dans la boîte de dialogue Système.
  
Pour installer Windows Management Framework 5.1, suivez la procédure décrite dans [Installer et configurer WMF 5.1](/powershell/scripting/wmf/setup/install-configure).
  
Après que l'ordinateur a redémarré, vérifiez que Windows PowerShell démarre correctement et que l'application soit bien exécutée en tant qu'administrateur. Pour ce faire :
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.
    
2. Si la boîte de dialogue Contrôle de compte d'utilisateur apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Lorsque la console PowerShell s’affiche, vous devez vérifier que le service WinRM soit bien en cours d’exécution et qu’il ait été configuré correctement. Pour vérifier que le service est bien en cours d’exécution, saisissez la commande suivante dans l’invite PowerShell et appuyez sur ENTRÉE :
  
```PowerShell
Get-Service winrm
```

Des informations sur le service WinRM sont affichées à l’écran :
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Si l'état du service n'est pas « En cours d'exécution », démarrez le service WinRM en saisissant la commande suivante, puis cliquez sur ENTRÉE :
  
```PowerShell
Start-Service winrm
```

Une fois le service démarré, exécutez la commande suivante pour vérifier que WinRM utilise l’authentification de base :
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Des informations semblables à ce qui suit sont affichées à l’écran :
  
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
   
## <a name="related-topics"></a>Sujets associés
[Configurer votre ordinateur pour Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
