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
ms.openlocfilehash: f7b7fa418b31a7b826319fc75c943819193161ea
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225812"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="d581b-103">Téléchargez et installez le Skype pour le module Business Connector en ligne</span><span class="sxs-lookup"><span data-stu-id="d581b-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="d581b-104">Le Skype pour le module Business Connector Online inclut l’applet de commande **New-CsOnlineSession** , qui vous permet de créer une session Windows PowerShell à distance qui se connecte à Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="d581b-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="d581b-105">Ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits (pour plus d’informations, voir [configurer votre ordinateur pour Skype pour la gestion de l’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), peut être téléchargé depuis le Center Download Microsoft à [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="d581b-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="d581b-106">Téléchargez le fichier SkypeOnlinePowershell.exe et puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d581b-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="d581b-107">Double-cliquez sur le fichier **SkypeOnlinePowershell.exe** .</span><span class="sxs-lookup"><span data-stu-id="d581b-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="d581b-108">Dans Skype pour Business Online, Assistant d’installation de Windows PowerShell, dans la page **Contrat de licence logiciel Microsoft** , sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="d581b-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="d581b-109">Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="d581b-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="d581b-110">Dans la page **terminé le Skype pour Business Online, le Module Windows PowerShell** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d581b-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="d581b-111">Le programme d’installation copie la Skype pour module Business Connector en ligne (et l’applet de commande **New-CsOnlineSession** ) sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d581b-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="d581b-112">Pour accéder au module, démarrer une session Windows PowerShell sous les informations d’identification d’administrateur, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d581b-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="d581b-113">Si vous ne souhaitez pas tapez cette commande chaque fois que vous démarrez Windows PowerShell, vous pouvez ajouter la commande à votre profil Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d581b-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="d581b-114">Pour cela, tapez la commande suivante à l’invite de Windows PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="d581b-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="d581b-115">Lorsque le bloc-notes s’affiche, ajoutez la ligne suivante au bas des commandes qui se trouvent déjà dans le profil (le cas échéant) :</span><span class="sxs-lookup"><span data-stu-id="d581b-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="d581b-116">Enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="d581b-116">Save the file.</span></span> <span data-ttu-id="d581b-117">La prochaine fois que vous démarrez Windows PowerShell, la Skype pour le module Business Connector en ligne est automatiquement importé.</span><span class="sxs-lookup"><span data-stu-id="d581b-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="d581b-118">N’oubliez pas que vous obtiendrez un message d’erreur et le module ne sera pas chargé, si vous n’exécutez pas Windows PowerShell sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d581b-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="d581b-119">Outre l’installation du Skype pour le module Business Connector en ligne, SkypeOnlinePowershell.exe installe également trois composants supplémentaires : 1) l’identité Service Client Runtime Library (IDCRL), permet de gérer l’authentification client Skype pour les entreprises En ligne ; (2) .NET framework 4.5 ; et 3) le package redistribuable Microsoft Visual C++ 2012 (x64) (version 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="d581b-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="d581b-120">.NET framework 4.5 fournit l’infrastructure utilisée pour générer et exécuter des applications .NET, notamment Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d581b-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="d581b-121">Le package redistribuable Visual C++ installe les composants d’exécution Visual C++ pour les ordinateurs qui n’ont pas de Microsoft Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="d581b-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="d581b-122">Pour vérifier le numéro de version du module connecteur qui est actuellement installé sur votre ordinateur, ouvrez le panneau de configuration, ouvrez **programmes et fonctionnalités**, puis recherchez le numéro de version de la **Skype pour Business Online, le Module Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d581b-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d581b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d581b-123">Related topics</span></span>
[<span data-ttu-id="d581b-124">Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d581b-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
