---
title: Skype Entreprise Server 2015 Management Shell
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration du serveur. Il est basé sur Windows PowerShell et inclut un ensemble complet de gestion et administration applets de commande spécifiques à Skype et anciens produits de serveur Lync.
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a>Skype Entreprise Server 2015 Management Shell
 
Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration du serveur. Il est basé sur Windows PowerShell et inclut un ensemble complet de gestion et administration applets de commande spécifiques à Skype et anciens produits de serveur Lync.
  
Windows PowerShell vous permet de gérer les applications de Microsoft à partir de la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell a été introduite comme une version téléchargeable pour le système d’exploitation Windows plus tard en 2006 et ont été intégré à l’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007. Il a été incorporé dans la plupart des produits Microsoft Server, y compris les serveurs Lync et Skype à partir de Lync Server 2010. Il existe plus de 700 Lync Skype des applets de commande et dans le Skype pour Business Server Management Shell.
  
> [!NOTE]
> Skype pour référence d’applet de commande entreprise a déplacé vers docs.microsoft.com. En cliquant sur les liens ci-dessous vous amènera à la page docs.microsoft.com. Le contenu est désormais ouvert Corée et disponible pour des contributions via GitHub. Vous souhaitez contribuer ? Consultez le fichier README dans le mis en pension ici :[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype pour Business Server 2015 est livré avec plus de 700 applets de commande qui permettent aux administrateurs de gérer Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell. Vous pouvez obtenir de l’aide sur une applet de commande directement à partir de la ligne de commande en tapant une commande similaire à la suivante :
  
```
Get-Help New-CsVoicePolicy -Full
```

La commande précédente extrait l’aide complète disponible pour l’applet de commande **New-CsVoicePolicy** . Pour afficher l’aide pour une applet de commande différent, remplacez **New-CsVoicePolicy** avec le nom de l’applet de commande pour lequel vous souhaitez obtenir de l’aide.
  
Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype Entreprise Server, tapez les éléments suivants à l’invite de commandes shell : 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Choses à savoir sur Windows PowerShell dans Skype pour Business Server :
  
- Pour exécuter le Skype pour les applets de commande de serveur de l’entreprise, ouvrez la Skype pour Business Server Management Shell.
    
    > [!CAUTION]
    > Si vous ouvrez une fenêtre de Windows PowerShell, plutôt que le Skype pour Business Server Management Shell, par défaut vous ne peut-être pas être en mesure d’exécuter les applets de commande de Skype. Pour exécuter Skype pour les applets de commande Business Server à partir de Windows PowerShell, tapez ce qui suit à l’invite de commande Windows PowerShell : >`Import-Module SkypeforBusiness`
  
- Skype pour Business Server Management Shell est automatiquement installé sur chaque Skype pour serveur Business Server Enterprise Edition serveur frontal ou Standard Edition.
    
- Vous pouvez mettre à jour le Skype Business Server Management Shell contenu d’aide en exécutant la cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . L’applet de commande Update-Help télécharge et installe les fichiers aide le plus récents disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour Skype pour les cmdlets de l’entreprise.
    
    Par défaut, l’applet de commande **Update-Help** met à jour tous les modules installés sur votre Skype pour Business Server. Si vous souhaitez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre de _Module_ pour limiter l’étendue de l’applet de commande. L’exemple suivant met à jour uniquement le Skype pour le module d’entreprise.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Si vous devez mettre à jour l’aide sur les serveurs qui ne sont pas connectés à internet, vous pouvez utiliser l’applet de commande [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) pour obtenir la dernière version de l’aide et l’enregistrer à un emplacement que vous spécifiez. Vous pouvez ensuite utiliser l’applet de commande **Update-Help** avec le paramètre _- SourcePath_ sur les serveurs non connectés à internet pour obtenir de l’aide mis à jour à partir de l’emplacement que vous avez sélectionné. L’exemple suivant montre comment enregistrer les fichiers d’aide pour un partage de fichiers réseau, puis mettre à jour de l’aide pour le Skype pour le module d’entreprise à partir du partage de fichier.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Pour plus d’informations, consultez [à propos d’aide mis à jour](https://technet.microsoft.com/library/hh847735.aspx).
    

