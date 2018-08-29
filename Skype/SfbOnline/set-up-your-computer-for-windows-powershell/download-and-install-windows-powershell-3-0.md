---
title: Télécharger et installer Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Télécharger, installer et utiliser Windows PowerShell 3.0 pour créer une session PowerShell distante se connectant à Skype Entreprise Online.
ms.openlocfilehash: 9c2b0f02d9da7e44cdb5585314c13a6bafbe58c6
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568321"
---
# <a name="download-and-install-windows-powershell-30"></a>Télécharger et installer Windows PowerShell 3.0

Si vous utilisez Windows 8.1, Windows 8 Windows Server 2012 R2 ou Windows erver 2012, vous disposez normalement déjà de Windows PowerShell 3.0. Cette application est en effet pré-installée sur ces systèmes d'exploitation. 
  
Si vous utilisez Windows 7 ou Windows Server 2008 R2, il est également possible que vous utilisiez déjà Windows PowerShell 3.0. La possibilité existe cependant que vous utilisiez la version 2.0 – laquelle était initialement livrée avec ces systèmes d'exploitation. Pour déterminer la version de Microsoft PowerShell que vous utilisez, effectuez les opérations suivante sur votre ordinateur Windows 7 ou Windows Server 2008 R2 :
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell** et enfin sur **Windows PowerShell**.
    
2. Dans la console PowerShell, saisissez la commande suivante puis appuyez sur Entrée :
    
   ```
   Get-Host | Select-Object Version
   ```

3. Des informations similaires à celles-présentées ci-dessous doivent s'afficher dans la fenêtre de console :
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    Si le numéro de version renvoyé est 3.0, c'est que vous utilisez Windows PowerShell 3.0. Si le numéro de version renvoyé n'est pas 3.0, vous devez installer Windows PowerShell 3.0. Vous pouvez télécharger Windows Management Frameworks 3.0, qui inclut Windows PowerShell 3.0, à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Une fois que vous avez vérifié que Windows PowerShell 3.0 est bien installé, vous devez vous assurer que PowerShell ait bien été configuré pour l'exécution de scripts distants. Pour cela, démarrez PowerShell en tant qu’administrateur. Sous Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, procédez comme suit :
  
1. Cliquez sur **Démarrer**, **Tous les programmes**, **Accessoires**, **Windows PowerShell**, faites un clic droit sur **Windows PowerShell** et cliquez sur **Exécuter en tant qu'administrateur**.
    
2. Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Si vous utilisez Windows 8, effectuer la procédure suivante à la place :
  
1. Accédez à la barre des talismans, cliquez sur **Rechercher** puis faites un clic droit sur **Windows PowerShell**. Vous pouvez accéder rapidement à la barre des talismans à partir de n'importe quel ordinateur Windows 8 (tactile ou non) en maintenant la touche Windows et en appuyant sur C.
    
2. Dans la barre d’outils située en bas de l’écran, cliquez sur **Exécuter en tant qu’administrateur**.
    
3. Si la boîte de dialoguqe **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour confirmer que vous désirer exécuter PowerShell en utilisant les informations du compte administrateur.
    
Après l'exécution de PowerShell, vous devez modifier la politique d'exécution pour permettre l'exécution de scripts distants. Dans la console PowerShell, saisissez la commande suivante puis appuyez sur Entrée :
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

Si vous n'utilisez pas Windows PowerShell 3.0, vous allez également devoir télécharger et installer Windows Management Frameworks 3.0 à partir du Centre de téléchargement Microsoft. Il s’agit d’un package d’installation qui inclut Windows PowerShell 3.0 et Windows Remote Management (WinRM) 3.0. Ce package d’installation peut être nécessaire si vous utilisez Windows 7 et n’avez pas encore effectué la mise à jour vers Windows PowerShell 3.0. Si vous utilisez Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, aucune installation de Windows PowerShell 3.0 ne devrait être nécessaire. Windows PowerShell 3.0 est en effet préinstallé sur ces systèmes d’exploitation.
  
Avant d’installer Windows Management Framework 3.0 :
  
- Assurez-vous d'avoir téléchargé la bonne version du package d’installation. Si vous utilisez la version 64 bits de Windows 7, téléchargez le fichier Windows6.1-KB2506143-x64.msu. Si vous utilisez la version 32 bits de Windows 7, téléchargez le fichier Windows6.1-KB2506143-x86.
    
- Si vous utilisez Windows 7 sur votre ordinateur, assurez-vous d'avoir installé Windows 7 Service Pack 1.
    
Si vous n'êtes pas certain de la version de Windows que vous utilisez, ou si vous n'êtes pas sûr d'avoir installé Windows 7 Service Pack 1, cliquez sur **Démarrer**, faites un clic droit sur **Ordinateur** puis cliquez sur **Propriétés**. Ces informations seront mentionnées dans la boîte de dialogue Système.
  
Pour installer Windows Management Framework 3.0, procédez comme suit :
  
1. Double-cliquez sur le fichier d’installation .MSU ( **Windows6.1-KB2506143-x64.msu** ou **Windows6.1-KB2506143-x86**).
    
2. Dans l'assistant Télécharger et installer des mises à jour, sur la page **Lire les termes du contrat de licence (1 sur 1)**, cliquez sur **J'accepte**.
    
3. Une fois le processus d'installation terminé, cliquez sur **Redémarrer maintenant** pour redémarrer votre ordinateur.
    
Après que l'ordinateur a redémarré, vérifiez que Windows PowerShell démarre correctement et que l'application soit bien exécutée en tant qu'administrateur. Pour cela :
  
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
   
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 