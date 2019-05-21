---
title: Skype Entreprise Server Management Shell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion du serveur. Il repose sur Windows PowerShell et inclut un ensemble complet de cmdlets de gestion et d’administration qui sont spécifiques aux produits Lync Server traditionnels et Skype.
ms.openlocfilehash: ce031b15e2146036d77c7336aa9c2b73f000fe4a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279591"
---
# <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell
 
Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion du serveur. Il repose sur Windows PowerShell et inclut un ensemble complet de cmdlets de gestion et d’administration qui sont spécifiques aux produits Lync Server traditionnels et Skype.
  
Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell s’est d’abord présenté comme une version téléchargeable du système d’exploitation Windows en retard dans 2006, et il a été intégré en tant qu’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007. Il a été incorporé à la plupart des produits serveur Microsoft, y compris Lync et les serveurs Skype commençant par Lync Server 2010. Il existe plus de 700 applets de contrôleurs spécifiques Lync et Skype disponibles dans Skype entreprise Server Management Shell.
  
> [!NOTE]
> Référence sur les applets de la cmdlet Skype entreprise a été déplacée vers docs.microsoft.com. Cliquer sur les liens ci-dessous vous permet d’atteindre la nouvelle page docs.microsoft.com. Le contenu est désormais ouvert et est disponible pour les contributions de la Communauté par le biais de GitHub. Vous voulez participer? Consultez le fichier README dans le référentiel Samples:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype entreprise Server est fourni avec plus de 700 cmdlets qui permettent aux administrateurs de gérer Skype entreprise Server à l’aide de Skype entreprise Server Management Shell. Vous pouvez obtenir de l’aide sur une applet de commande directement à partir de la ligne de commande en tapant une commande similaire à la suivante :
  
```
Get-Help New-CsVoicePolicy -Full
```

La commande précédente permet d’obtenir de l’aide concernant l’applet de commande **New-CsVoicePolicy**. Pour afficher l’aide d’une cmdlet différente, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.
  
Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype Entreprise Server, tapez les éléments suivants à l’invite de commandes shell : 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Éléments à connaître sur Windows PowerShell dans Skype entreprise Server:
  
- Pour exécuter les applets de cmdlet Skype entreprise Server, ouvrez le shell de gestion de Skype entreprise Server.
    
    > [!CAUTION]
    > Par défaut, si vous ouvrez une fenêtre Windows PowerShell plutôt que Skype entreprise Server Management Shell, vous risquez de ne pas pouvoir exécuter les applets de cmdlet Skype. Pour exécuter les applets de commande Skype entreprise Server à partir de Windows PowerShell, commencez par taper la commande suivante à l’invite de commandes Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype entreprise Server Management Shell est automatiquement installé sur chaque serveur frontal Skype entreprise Server Enterprise Edition ou Standard Edition Server.
    
- Vous pouvez mettre à jour le contenu de l’aide de Skype entreprise Server Management Shell en exécutant la cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . La cmdlet Update-Help télécharge et installe les fichiers d’aide les plus récents disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour apportées aux cmdlets Skype entreprise.
    
    Par défaut, la cmdlet **Update-Help** entraîne la mise à jour de tous les modules installés sur votre serveur Skype entreprise. Si vous voulez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre _Module_ pour limiter la portée de l’applet de commande. L’exemple suivant met à jour uniquement le module Skype entreprise.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Si vous avez besoin de mettre à jour l’aide sur des serveurs qui ne sont pas connectés à Internet, vous pouvez utiliser l’applet de contrôle [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) pour obtenir la dernière version de l’aide et l’enregistrer dans un emplacement que vous spécifiez. Vous pouvez ensuite utiliser l’applet de connexion **Update-Help** avec le paramètre _-CheminSource_ sur des serveurs qui ne sont pas connectés à Internet pour obtenir l’aide mise à jour à partir de l’emplacement que vous avez sélectionné. L’exemple suivant montre comment enregistrer les fichiers d’aide sur un partage de fichiers réseau, puis mettre à jour l’aide du module Skype entreprise à partir du partage de fichiers.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Pour obtenir des informations plus détaillées, voir [à propos de l’aide à mettre à jour](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Si vous utilisez PowerShell à distance, il est possible que vous deviez autoriser les communications par le biais d’un pare-feu. Pour en savoir plus sur les ports utilisés par les fonctionnalités d’accès distant PowerShell, voir [quel port utilise la communication à distance PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

