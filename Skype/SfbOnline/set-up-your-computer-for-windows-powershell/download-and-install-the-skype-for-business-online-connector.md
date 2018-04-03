---
title: Téléchargez et installez le Skype pour module de Business Connector d’en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: 'Télécharger, installer et puis utiliser le Skype pour Business Connector d’en ligne pour créer une session à distance de Windows PowerShell qui se connecte à Skype pour entreprise en ligne. '
ms.openlocfilehash: e4aea93e8c14f172b8fd19420d8a02f584a18dde
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Téléchargez et installez le Skype pour module de Business Connector d’en ligne

Le Skype pour module de Business Connector d’en ligne comprend l’applet de commande **New-CsOnlineSession** , ce qui vous permet de créer une session à distance de Windows PowerShell qui se connecte à Skype pour entreprise en ligne. Ce module est pris en charge uniquement sur les ordinateurs 64 bits (pour plus d’informations, voir [configurer votre ordinateur pour Skype pour la gestion de l’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), peut être téléchargé à partir de Microsoft Download Center au [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Téléchargez le fichier SkypeOnlinePowershell.exe et puis procédez comme suit :
  
1. Double-cliquez sur le fichier **SkypeOnlinePowershell.exe** .
    
2. Dans le Skype pour Business Online, Assistant d’installation de Windows PowerShell, dans la page **Contrat de licence logiciel Microsoft** , sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **installer**. Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour poursuivre l’installation.
    
3. Dans la page **terminé le Skype pour Business Online, Module de Windows PowerShell** , cliquez sur **Terminer**.
    
Le programme d’installation copie le Skype pour module de Business en ligne Connector (et l’applet de commande **New-CsOnlineSession** ) sur votre ordinateur. Pour accéder au module et démarrer une session Windows PowerShell sous les informations d’identification de l’administrateur, puis exécutez la commande suivante :
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Si vous ne souhaitez pas tapez cette commande chaque fois que vous démarrez Windows PowerShell, vous pouvez ajouter la commande à votre profil Windows PowerShell. Pour cela, tapez la commande suivante à l’invite de Windows PowerShell, puis appuyez sur ENTRÉE :
  
```
notepad.exe $profile
```

 Lorsque le bloc-notes s’affiche, ajoutez la ligne suivante à la fin des commandes qui se trouvent déjà dans le profil (le cas échéant) :
  
```
Import-Module SkypeOnlineConnector
```

Enregistrez le fichier. La prochaine fois que vous démarrez Windows PowerShell, le Skype pour module de Business Connector d’en ligne est automatiquement importé. Sachez que vous obtenez un message d’erreur, et le module ne sera pas chargé, si vous n’exécutez pas Windows PowerShell sous les informations d’identification d’administrateur.
  
En plus d’installer le Skype pour module de Business Connector d’en ligne, SkypeOnlinePowershell.exe installe également les trois autres composants : 1) l’identité Service Client Runtime Library IDCRL (), permet de gérer l’authentification d’un client Skype pour entreprise En ligne ; 2).NET Framework 4.5 ; et 3) du package redistribuable Microsoft Visual C++ 2012 (x64) (version 11.0.50727). .NET Framework 4.5 fournit l’infrastructure utilisée pour générer et exécuter des applications .NET, y compris Windows PowerShell. Le package redistribuable Visual C++ installe les composants d’exécution de Visual C++ pour les ordinateurs qui ne disposent pas de Microsoft Visual Studio 2012 est installé.
  
Pour vérifier le numéro de version du module connecteur qui est actuellement installé sur votre ordinateur, ouvrez le panneau de configuration, ouvrez **programmes et fonctionnalités**et puis vérifiez le numéro de version pour le **Skype pour Business Online, Module de Windows PowerShell**.
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion d’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 