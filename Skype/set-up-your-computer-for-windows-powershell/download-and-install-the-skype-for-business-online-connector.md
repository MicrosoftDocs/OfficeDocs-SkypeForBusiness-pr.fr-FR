---
title: "Téléchargez et installez le Skype pour module Business Connector en ligne"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
description: "Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
"
---

# Téléchargez et installez le Skype pour module Business Connector en ligne

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
La Module Skype Entreprise Online Connector inclut l'applet de commande **New-CsOnlineSession**, qui vous permet de créer une session distante Windows PowerShell qui se connecte à Skype Entreprise Online. Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits (pour plus d'informations, voir[Configurer votre ordinateur pour Skype pour la gestion de l'entreprise Online à l'aide de Windows PowerShell](set-up-your-computer-for-skype-for-business-online-management-using-windows-powe.md) ), peuvent être téléchargés à partir de la Centre de téléchargement Microsoft en[https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Téléchargez le fichier SkypeOnlinePowershell.exe et puis procédez comme suit :
  
1. Double-cliquez sur le fichier **SkypeOnlinePowershell.exe**.
    
2. Dans la Skype Entreprise Online, Assistant de configuration de Windows PowerShell, dans la page **Contrat de licence logiciel Microsoft**, sélectionnez **J'accepte les termes du contrat de licence**, puis cliquez sur **installer**. Si la boîte de dialogue **Contrôle de compte d'utilisateur** apparaît, cliquez sur **Oui** pour poursuivre l'installation.
    
3. Dans la page **terminé la Skype entreprise Online, Module Windows PowerShell**, cliquez sur **Terminer**.
    
Le programme d'installation copie la Module Skype Entreprise Online Connector (et l'applet de commande **New-CsOnlineSession** ) sur votre ordinateur. Pour accéder au module, démarrer une session de Windows PowerShell sous informations d'identification d'administrateur, puis exécutez la commande suivante :
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Si vous ne voulez pas tapez cette commande chaque fois que vous démarrez Windows PowerShell, vous pouvez ajouter la commande à votre profil Windows PowerShell. Pour cela, tapez la commande suivante à l'invite Windows PowerShell, puis appuyez sur ENTRÉE :
  
```
notepad.exe $profile
```

Lorsque le bloc-notes s'affiche, ajoutez la ligne suivante vers le bas des commandes qui se trouvent déjà dans le profil (le cas échéant) :
  
```
Import-Module SkypeOnlineConnector
```

Enregistrez le fichier. La prochaine fois que vous démarrez Windows PowerShell, la Module Skype Entreprise Online Connector seront automatiquement importés. N'oubliez pas que vous obtenez un message d'erreur, et le module ne sera pas chargé, si vous n'utilisez pas Windows PowerShell sous informations d'identification d'administrateur.
  
Outre l'installation de la Module Skype Entreprise Online Connector, SkypeOnlinePowershell.exe installe-t-il également les trois autres composants : 1) l'identité Service Client Runtime bibliothèque IDCRL (), permet de gérer l'authentification des clients à Skype Entreprise Online; 2) .NET framework 4.5 ; et, 3) le package redistribuable Microsoft Visual C++ 2012 (x64) (version 11.0.50727). .NET framework 4.5 fournit l'infrastructure utilisée pour créer et exécuter des applications .NET, y compris Windows PowerShell. Le package redistribuable Visual C++ installe des composants d'exécution VisualC pour les ordinateurs qui n'ont pas de Microsoft Visual Studio 2012 est installé.
  
Pour vérifier le numéro de version du module connecteur qui est installé sur votre ordinateur, ouvrez le panneau de configuration, ouvrez **programmes et fonctionnalités** et puis recherchez le numéro de version de **Skype entreprise Online, Module Windows PowerShell**.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

