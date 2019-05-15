---
title: Téléchargez et installez le Skype pour le module Business Connector en ligne
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 'Télécharger, installer et ensuite utiliser la Skype pour Business Connector en ligne pour créer une session Windows PowerShell à distance qui se connecte à Skype pour Business Online. '
ms.openlocfilehash: a93cf1d3d09910001f25619969b6d504e23ec36f
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036691"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Téléchargez et installez le Skype pour le module Business Connector en ligne

Le Skype pour le module Business Connector Online inclut l’applet de commande **New-CsOnlineSession** , qui vous permet de créer une session Windows PowerShell à distance qui se connecte à Skype pour Business Online. Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits (pour plus d’informations, voir [configurer votre ordinateur pour Skype pour la gestion de l’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), peut être téléchargé depuis le Center Download Microsoft à [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366). Téléchargez le fichier SkypeOnlinePowershell.exe et puis procédez comme suit :
  
1. Double-cliquez sur le fichier **SkypeOnlinePowershell.exe** .
    
2. Dans Skype pour Business Online, Assistant d’installation de Windows PowerShell, dans la page **Contrat de licence logiciel Microsoft** , sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **installer**. Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour poursuivre l’installation.
    
3. Dans la page **terminé le Skype pour Business Online, le Module Windows PowerShell** , cliquez sur **Terminer**.
    
Le programme d’installation copie la Skype pour module Business Connector en ligne (et l’applet de commande **New-CsOnlineSession** ) sur votre ordinateur. Pour accéder au module, démarrer une session Windows PowerShell sous les informations d’identification d’administrateur, puis exécutez la commande suivante :
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Si vous ne souhaitez pas tapez cette commande chaque fois que vous démarrez Windows PowerShell, vous pouvez ajouter la commande à votre profil Windows PowerShell. Pour cela, tapez la commande suivante à l’invite de Windows PowerShell et appuyez sur ENTRÉE :
  
```
notepad.exe $profile
```

 Lorsque le bloc-notes s’affiche, ajoutez la ligne suivante au bas des commandes qui se trouvent déjà dans le profil (le cas échéant) :
  
```
Import-Module SkypeOnlineConnector
```

Enregistrez le fichier. La prochaine fois que vous démarrez Windows PowerShell, la Skype pour le module Business Connector en ligne est automatiquement importé. N’oubliez pas que vous obtiendrez un message d’erreur et le module ne sera pas chargé, si vous n’exécutez pas Windows PowerShell sous les informations d’identification d’administrateur.
  
Outre l’installation du Skype pour le module Business Connector en ligne, SkypeOnlinePowershell.exe installe également trois composants supplémentaires : 1) l’identité Service Client Runtime Library (IDCRL), permet de gérer l’authentification client Skype pour les entreprises En ligne ; (2) .NET framework 4.5 ; et 3) le package redistribuable Microsoft Visual C++ 2012 (x64) (version 11.0.50727). .NET framework 4.5 fournit l’infrastructure utilisée pour générer et exécuter des applications .NET, notamment Windows PowerShell. Le package redistribuable Visual C++ installe les composants d’exécution Visual C++ pour les ordinateurs qui n’ont pas de Microsoft Visual Studio 2012.
  
Pour vérifier le numéro de version du module connecteur qui est actuellement installé sur votre ordinateur, ouvrez le panneau de configuration, ouvrez **programmes et fonctionnalités**, puis recherchez le numéro de version de la **Skype pour Business Online, le Module Windows PowerShell**.
  
## <a name="related-topics"></a>Voir aussi
[Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
