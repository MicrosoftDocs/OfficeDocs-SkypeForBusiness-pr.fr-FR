---
title: Télécharger et installer le module Skype entreprise Online Connector
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 'Téléchargez, installez, puis utilisez le connecteur Skype entreprise Online pour créer une session Windows PowerShell distante qui se connecte à Skype entreprise online. '
ms.openlocfilehash: 02c08d4172e2f42fb03c024fa2b0958a8e8b4637
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706259"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Télécharger et installer le module Skype entreprise Online Connector

Le module Skype entreprise Online Connector inclut l’applet **de commande New-CsOnlineSession** , qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online. Ce module, qui est pris en charge uniquement sur les ordinateurs 64 (pour plus d’informations, reportez-vous à la rubrique [configuration de votre ordinateur pour la gestion de Skype entreprise Online avec Windows PowerShell](set-up-your-computer-for-windows-powershell.md) pour plus d’informations) peut être téléchargé à partir du centre de téléchargement Microsoft [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366). Téléchargez le fichier SkypeOnlinePowershell. exe, puis procédez comme suit :
  
1. Double-cliquez sur le fichier **SkypeOnlinePowershell. exe** .
    
2. Dans l’Assistant Configuration de Skype entreprise Online et Windows PowerShell, dans la page termes du contrat de **licence logiciel Microsoft** , sélectionnez **J’accepte les conditions du contrat de licence**, puis cliquez sur **installer**. Si la boîte de dialogue **contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour continuer l’installation.
    
3. Dans la page de l’état **terminé de Skype entreprise Online,** cliquez sur **Terminer**.
    
Le programme d’installation copie le module Skype entreprise Online Connector (et l’applet **de nouvelle cmdlet New-CsOnlineSession** ) sur votre ordinateur. Pour accéder au module, démarrez une session Windows PowerShell sous informations d’identification d’administrateur, puis exécutez la commande suivante :
  
```PowerShell
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Si vous ne souhaitez pas entrer cette commande chaque fois que vous démarrez Windows PowerShell, vous pouvez ajouter la commande à votre profil Windows PowerShell. Pour ce faire, tapez la commande suivante à l’invite Windows PowerShell, puis appuyez sur entrée :
  
```PowerShell
notepad.exe $profile
```

 Lorsque le bloc-notes s’affiche, ajoutez la ligne suivante en bas des commandes déjà présentes dans le profil (le cas échéant) :
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Enregistrez le fichier. La prochaine fois que vous démarrez Windows PowerShell, le module connecteur Skype entreprise Online sera automatiquement importé. Sachez que vous recevrez un message d’erreur et que le module ne sera pas chargé, si vous n’exécutez pas Windows PowerShell sous informations d’identification d’administrateur.
  
En plus d’installer le module de connecteur Skype entreprise Online, SkypeOnlinePowershell. exe installe également trois composants supplémentaires : 1) la bibliothèque d’exécution du cliente de service d’identité (IDCRL), utilisée pour gérer l’authentification du client sur Skype entreprise Enchères 2) .NET Framework 4,5 ; et 3) le package Microsoft Visual C++ 2012 redistribuable (x64) (version 11.0.50727). .NET Framework 4,5 fournit l’infrastructure utilisée pour générer et exécuter des applications .NET, y compris Windows PowerShell. Le package redistribuable Visual C++ installe des composants runtime Visual C++ pour les ordinateurs sur lesquels Microsoft Visual Studio 2012 n’est pas installé.
  
Pour vérifier le numéro de version du module de connecteur actuellement installé sur votre ordinateur, ouvrez le panneau de configuration, ouvrez **programmes et fonctionnalités**, puis vérifiez le numéro de version du **module Skype entreprise Online, Windows PowerShell**.
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
