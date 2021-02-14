---
title: Télécharger et installer le module Skype Entreprise Online Connector
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
description: Téléchargez, installez et utilisez Skype Entreprise Online Connector pour créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814563"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Télécharger et installer le module Skype Entreprise Online Connector

> [!NOTE]
> La dernière version [publique de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un seul module pour la gestion de Teams PowerShell.

Le module Skype Entreprise Online Connector inclut la cmdlet **New-CsOnlineSession,** qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits (voir Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide de [Windows PowerShell](set-up-your-computer-for-windows-powershell.md) pour plus d’informations), peut être téléchargé à partir du Centre de téléchargement Microsoft à l’adresse [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . Téléchargez le SkypeOnlinePowershell.exe fichier, puis terminez la procédure suivante :
  
1. Double-cliquez sur **leSkypeOnlinePowershell.exe** fichier.
    
2. Dans l’Assistant configuration de Skype Entreprise Online Windows PowerShell, dans la page Termes du contrat de licence logiciel **Microsoft,** sélectionnez J’accepte les termes du contrat de **licence,** puis cliquez sur **Installer.** Si la boîte **de dialogue Contrôle de compte** d’utilisateur s’affiche, cliquez sur **Oui** pour poursuivre l’installation.
    
3. Sur la page **Skype Entreprise Online Terminée,** cliquez Windows PowerShell module final, cliquez **sur Terminer.**
    
Le programme d’installation copie le module Skype Entreprise Online Connector (et la cmdlet **New-CsOnlineSession)** sur votre ordinateur. Pour accéder au module, démarrez une session Windows PowerShell d’informations d’identification d’administrateur, puis exécutez la commande suivante :
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Si vous ne voulez pas taper cette commande chaque fois que vous démarrez une Windows PowerShell, vous pouvez l’ajouter à votre Windows PowerShell profil. Pour ce faire, à l’invite de commandes, tapez la commande Windows PowerShell suivante, puis appuyez sur Entrée :
  
```PowerShell
notepad.exe $profile
```

 Lorsque le Bloc-notes s’affiche, ajoutez la ligne suivante au bas des commandes déjà présentes dans le profil (le cas dessous) :
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Enregistrez le fichier. Au prochain démarrage d Windows PowerShell, le module Skype Entreprise Online Connector sera importé automatiquement. Notez qu’un message d’erreur s’agit d’un message d’erreur et que le module n’est pas chargé, si vous n’exécutez pas Windows PowerShell des informations d’identification d’administrateur.
  
Outre l’installation du module Skype Entreprise Online Connector, SkypeOnlinePowershell.exe installe également trois composants supplémentaires : 1) la bibliothèque IDCRL (Identity Service Client Runtime Library), qui permet de gérer l’authentification client à Skype Entreprise Online . 2) .NET Framework 4.5; et, 3) le package redistribuable Microsoft Visual C++ 2012 (x64) (version 11.0.50727). .NET Framework 4.5 fournit l’infrastructure utilisée pour la création et l’exécution d’applications .NET, dont Windows PowerShell. Le package redistribuable Visual C++ installe les composants Runtime Visual C++ pour les ordinateurs sur qui Microsoft Visual Studio 2012 n’est pas installé.
  
Pour vérifier le numéro de version du module Connector actuellement installé sur votre ordinateur, ouvrez le Panneau de commandes, ouvrez Programmes et fonctionnalités, puis vérifiez le numéro de version du Module Windows PowerShell Skype Entreprise **Online.**
  
## <a name="related-topics"></a>Sujets associés
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
