---
title: Skype Entreprise Server Management Shell
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype Entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion des serveurs. Il s’Windows PowerShell et inclut un ensemble complet d’cmdlets de gestion et d’administration spécifiques à Skype et aux produits serveur Lync hérités.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816534"
---
# <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell
 
Skype Entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion des serveurs. Il s’Windows PowerShell et inclut un ensemble complet d’cmdlets de gestion et d’administration spécifiques à Skype et aux produits serveur Lync hérités.
  
Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell a été introduite en tant que version téléchargeable pour le système d’exploitation Windows fin 2006 et a été incorporée en tant qu’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007. Il a été incorporé dans la plupart des produits Microsoft Server, y compris les serveurs Lync et Skype à partir de Lync Server 2010. Plus de 700 cmdlets spécifiques à Lync et Skype sont disponibles dans Skype Entreprise Server Management Shell.
  
> [!NOTE]
> La référence des cmdlet Skype Entreprise a été déplacée vers docs.microsoft.com. Cliquer sur les liens ci-dessous vous permettra d’docs.microsoft.com page. Le contenu est désormais open source et disponible pour les contributions de la communauté via GitHub. Vous souhaitez contribuer ? Consultez le readme dans le repo ici : [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype Entreprise Server est fourni avec plus de 700 cmdlets qui permettent aux administrateurs de gérer Skype Entreprise Server à l’aide de Skype Entreprise Server Management Shell. Vous pouvez récupérer l’aide d’une cmdlet directement à partir de la ligne de commande en tapant une commande semblable à la suivante :
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

La commande précédente permet d’obtenir de l’aide concernant l’applet de commande **New-CsVoicePolicy**. Pour afficher l’aide d’une applet de commande différente, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.
  
Pour récupérer la liste complète des cmdlets disponibles pour la gestion de Skype Entreprise Server, tapez ce qui suit à l’invite de commandes de l’shell : 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Ce qu’il faut savoir Windows PowerShell dans Skype Entreprise Server :
  
- Pour exécuter les cmdlets Skype Entreprise Server, ouvrez Skype Entreprise Server Management Shell.
    
    > [!CAUTION]
    > Si vous ouvrez une fenêtre Windows PowerShell plutôt que Skype Entreprise Server Management Shell, par défaut vous ne pourrez peut-être pas exécuter les cmdlets Skype. Pour exécuter les cmdlets Skype Entreprise Server à partir de Windows PowerShell, tapez d’abord ce qui suit à l’invite Windows PowerShell commande suivante : >  `Import-Module SkypeforBusiness`
  
- Skype Entreprise Server Management Shell est installé automatiquement sur chaque serveur frontal Skype Entreprise Server Enterprise Edition ou Standard Edition Server.
    
- Vous pouvez mettre à jour le contenu d’aide de Skype Entreprise Server Management Shell en exécutant la cmdlet [Update-Help.](https://technet.microsoft.com/library/hh849720.aspx) La cmdlet Update-Help télécharge et installe les derniers fichiers d’aide disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour des cmdlets Skype Entreprise.
    
    Par défaut, **l’cmdlet Update-Help** met à jour tous les modules installés sur votre serveur Skype Entreprise. Si vous souhaitez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre _Module_ pour limiter l’étendue de la cmdlet. L’exemple suivant met à jour uniquement le module Skype Entreprise.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Si vous devez mettre à jour l’aide sur les serveurs [](https://technet.microsoft.com/library/hh849724.aspx) qui ne sont pas connectés à Internet, vous pouvez utiliser la cmdlet Enregistrer l’aide pour obtenir la dernière version de l’aide et l’enregistrer à un emplacement que vous spécifiez. Vous pouvez ensuite utiliser la cmdlet **Update-Help** avec le paramètre _-SourcePath_ sur les serveurs non connectés à Internet pour obtenir l’aide mise à jour à partir de l’emplacement que vous avez sélectionné. L’exemple suivant montre comment enregistrer les fichiers d’aide dans un partage de fichiers réseau, puis mettre à jour l’aide pour le module Skype Entreprise à partir du partage de fichiers.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Pour plus d’informations, voir [à propos de l’aide updatable.](https://technet.microsoft.com/library/hh847735.aspx)
    
    > [!NOTE]
    > Si vous utilisez PowerShell à distance, vous devrez peut-être autoriser la communication via un pare-feu. Pour en savoir plus sur les ports utilisés par la technologie à remoting PowerShell, consultez l’utilisation de la technologie [à remoting PowerShell.](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)
    

