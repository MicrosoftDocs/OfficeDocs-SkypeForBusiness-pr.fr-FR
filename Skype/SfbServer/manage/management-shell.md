---
title: Skype Entreprise Server Management Shell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion des serveurs. Il est basé sur Windows PowerShell et inclut un ensemble complet d’applets de commande de gestion et d’administration qui sont propres à Skype et aux produits Lync Server hérités.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044256"
---
# <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell
 
Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion des serveurs. Il est basé sur Windows PowerShell et inclut un ensemble complet d’applets de commande de gestion et d’administration qui sont propres à Skype et aux produits Lync Server hérités.
  
Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell a été introduit pour la première fois en tant que version téléchargeable pour le système d’exploitation Windows en retard dans 2006, et a été incorporée comme interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007. Elle a été incorporée dans la plupart des produits serveur Microsoft, y compris les serveurs Lync et Skype commençant par Lync Server 2010. Il existe plus de 700 applets de commande spécifiques à Lync et Skype disponibles dans Skype entreprise Server Management Shell.
  
> [!NOTE]
> La référence de cmdlet Skype entreprise a été déplacée vers docs.microsoft.com. Cliquez sur les liens ci-dessous pour accéder à la nouvelle page docs.microsoft.com. Le contenu est désormais ouvert et disponible pour les contributions de la Communauté via GitHub. Vous souhaitez contribuer ? Consultez le fichier Lisez-moi dans le référentiel ici :[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype entreprise Server est fourni avec plus de 700 cmdlets qui permettent aux administrateurs de gérer Skype entreprise Server à l’aide de Skype entreprise Server Management Shell. Vous pouvez récupérer de l’aide pour une cmdlet directement à partir de la ligne de commande en tapant une commande semblable à la suivante :
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

La commande précédente permet d’obtenir de l’aide concernant l’applet de commande **New-CsVoicePolicy**. Pour afficher l’aide d’une applet de commande différente, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.
  
Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype entreprise Server, tapez ce qui suit à l’invite de commandes de l’environnement de ligne de commande : 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Éléments à connaître sur Windows PowerShell dans Skype entreprise Server :
  
- Pour exécuter les applets de commande Skype entreprise Server, ouvrez Skype entreprise Server Management Shell.
    
    > [!CAUTION]
    > Si vous ouvrez une fenêtre Windows PowerShell plutôt que Skype entreprise Server Management Shell, par défaut, il se peut que vous ne puissiez pas exécuter les applets de commande Skype. Pour exécuter les applets de commande Skype entreprise Server à partir de Windows PowerShell, tapez d’abord ce qui suit à l’invite de commandes Windows PowerShell : >`Import-Module SkypeforBusiness`
  
- Skype entreprise Server Management Shell est automatiquement installé sur chaque serveur frontal Skype entreprise Server Enterprise Edition ou serveur Standard Edition.
    
- Vous pouvez mettre à jour le contenu de l’aide de Skype entreprise Server Management Shell en exécutant l’applet de commande [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) . La cmdlet Update-Help télécharge et installe les derniers fichiers d’aide disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour des applets de commande Skype entreprise.
    
    Par défaut, l’applet de commande **Update-Help** met à jour tous les modules installés sur votre serveur Skype entreprise. Si vous souhaitez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre _module_ pour limiter l’étendue de l’applet de commande. L’exemple ci-dessous montre comment mettre à jour uniquement le module Skype entreprise.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Si vous devez mettre à jour l’aide sur les serveurs qui ne sont pas connectés à Internet, vous pouvez utiliser la cmdlet [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) pour obtenir la dernière version de l’aide et l’enregistrer à un emplacement que vous spécifiez. Vous pouvez ensuite utiliser l’applet de commande **Update-Help** avec le paramètre _-SourcePath_ sur les serveurs qui ne sont pas connectés à Internet pour obtenir l’aide mise à jour à partir de l’emplacement que vous avez sélectionné. L’exemple suivant montre comment enregistrer les fichiers d’aide sur un partage de fichiers réseau, puis mettre à jour l’aide pour le module Skype entreprise à partir du partage de fichiers.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Pour plus d’informations, consultez la rubrique [à propos de l’aide pouvant être mise à jour](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Si vous utilisez PowerShell à distance, vous devrez peut-être autoriser la communication via un pare-feu. Pour en savoir plus sur les ports utilisés par la communication à distance PowerShell, consultez la rubrique [quel port est utilisé par PowerShell Remoting ?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

