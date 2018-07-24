---
title: Skype Entreprise Server Management Shell
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration des serveurs. Il est basé sur Windows PowerShell et inclut un ensemble complet de la gestion et l’administration des applets de commande qui sont spécifiques à Skype et produits Lync server.
ms.openlocfilehash: 34bf761cfa6d9cfe648360319084b3a304d9f6e6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997355"
---
# <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell
 
Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration des serveurs. Il est basé sur Windows PowerShell et inclut un ensemble complet de la gestion et l’administration des applets de commande qui sont spécifiques à Skype et produits Lync server.
  
Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell a été initialement introduite comme une version téléchargeable pour le système d’exploitation Windows au plus tard en 2006 et ont été intégré à l’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007. Elle a été intégrée à la plupart des produits Microsoft Server, y compris les serveurs Lync et Skype commençant par Lync Server 2010. Plus de 700 Lync et Skype spécifiques des applets de commande sont disponibles dans le Skype pour Business Server Management Shell.
  
> [!NOTE]
> Skype pour la référence de l’entreprise a déplacé vers docs.microsoft.com. Cliquez sur les liens ci-dessous vous dirige vers la nouvelle page docs.microsoft.com. Le contenu est maintenant ouvrir Corée et disponibles pour des contributions par le biais de référentiels. Vous souhaitez contribuer au ? Extrayez le fichier README dans l’emprunteuses ici :[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype pour Business Server est fourni avec plus de 700 applets de commande qui permettent aux administrateurs de gérer Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell. Vous pouvez obtenir de l’aide sur une applet de commande directement à partir de la ligne de commande en tapant une commande similaire à la suivante :
  
```
Get-Help New-CsVoicePolicy -Full
```

La commande précédente récupère l’aide complète disponible pour l’applet de commande **New-CsVoicePolicy** . Pour afficher l’aide d’une applet de commande différents, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez accéder à l’aide.
  
Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype Entreprise Server, tapez les éléments suivants à l’invite de commandes shell : 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Choses à savoir sur Windows PowerShell dans Skype pour Business Server :
  
- Pour exécuter le Skype pour les applets de commande Business Server, ouvrez le Skype pour Business Server Management Shell.
    
    > [!CAUTION]
    > Si vous ouvrez une fenêtre Windows PowerShell, plutôt que la Skype pour Business Server Management Shell, par défaut vous ne pouvez pas être en mesure d’exécuter les applets de commande Skype. Pour exécuter Skype pour les applets de commande Business Server à partir de Windows PowerShell, tapez tout d’abord ce qui suit à l’invite de commandes Windows PowerShell : >`Import-Module SkypeforBusiness`
  
- Skype pour Business Server Management Shell est installé automatiquement sur chaque Skype pour Business Server Enterprise Edition serveur frontal ou Standard Edition server.
    
- Vous pouvez mettre à jour le Skype pour le contenu d’aide Business Server Management Shell en exécutant l’applet de commande [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . L’applet de commande Update-Help télécharge et installe les fichiers aide le plus récents disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour Skype pour les applets de commande Business.
    
    Par défaut, l’applet de commande **Update-Help** met à jour tous les modules installés sur votre Skype pour Business Server. Si vous souhaitez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre _Module_ pour limiter l’étendue de l’applet de commande. L’exemple suivant met à jour uniquement la Skype pour le module d’entreprise.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Si vous devez mettre à jour de l’aide sur les serveurs qui ne sont pas connectés à internet, vous pouvez utiliser l’applet de commande [Enregistrer-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) pour obtenir la dernière version de l’aide et enregistrez-le dans un emplacement que vous spécifiez. Vous pouvez ensuite utiliser l’applet de commande **Update-Help** avec le paramètre _- SourcePath_ sur les serveurs non connectés à internet pour obtenir de l’aide mis à jour à partir de l’emplacement que vous avez sélectionné. L’exemple suivant montre comment enregistrer les fichiers d’aide dans un partage de fichiers réseau, puis mettre à jour de l’aide de la Skype pour le module d’entreprise à partir du partage de fichier.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Pour plus d’informations, voir [à propos d’aide actualisable](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Si vous utilisez PowerShell à distance vous devrez peut-être autoriser les communications à travers un pare-feu. Pour en savoir plus sur les ports utilise de communication à distance PowerShell, voir [quel Port ne prend PowerShell à distance utiliser ?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

