---
title: "Téléchargez et installez le Skype pour module de Business Connector d’en ligne"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Télécharger, installer et puis utiliser le Skype pour Business Connector d’en ligne pour créer une session à distance de Windows PowerShell qui se connecte à Skype pour entreprise en ligne. "
ms.openlocfilehash: b95b41937fea2ec87cb484cf557d85dcb3a77a8e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="6fe07-103">Téléchargez et installez le Skype pour module de Business Connector d’en ligne</span><span class="sxs-lookup"><span data-stu-id="6fe07-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="6fe07-104">Le Skype pour module de Business Connector d’en ligne comprend l’applet de commande **New-CsOnlineSession** , ce qui vous permet de créer une session à distance de Windows PowerShell qui se connecte à Skype pour entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="6fe07-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="6fe07-105">Ce module est pris en charge uniquement sur les ordinateurs 64 bits (pour plus d’informations, voir [configurer votre ordinateur pour Skype pour la gestion de l’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), peut être téléchargé à partir de Microsoft Download Center au [https:// www.Microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="6fe07-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="6fe07-106">Téléchargez le fichier SkypeOnlinePowershell.exe et puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6fe07-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="6fe07-107">Double-cliquez sur le fichier **SkypeOnlinePowershell.exe** .</span><span class="sxs-lookup"><span data-stu-id="6fe07-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="6fe07-108">Dans le Skype pour Business Online, Assistant d’installation de Windows PowerShell, dans la page **Contrat de licence logiciel Microsoft** , sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="6fe07-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="6fe07-109">Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="6fe07-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="6fe07-110">Dans la page **terminé le Skype pour Business Online, Module de Windows PowerShell** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6fe07-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="6fe07-111">Le programme d’installation copie le Skype pour module de Business en ligne Connector (et l’applet de commande **New-CsOnlineSession** ) sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6fe07-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="6fe07-112">Pour accéder au module et démarrer une session Windows PowerShell sous les informations d’identification de l’administrateur, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6fe07-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="6fe07-113">Si vous ne souhaitez pas tapez cette commande chaque fois que vous démarrez Windows PowerShell, vous pouvez ajouter la commande à votre profil Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fe07-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="6fe07-114">Pour cela, tapez la commande suivante à l’invite de Windows PowerShell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="6fe07-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="6fe07-115">Lorsque le bloc-notes s’affiche, ajoutez la ligne suivante à la fin des commandes qui se trouvent déjà dans le profil (le cas échéant) :</span><span class="sxs-lookup"><span data-stu-id="6fe07-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="6fe07-116">Enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="6fe07-116">Save the file.</span></span> <span data-ttu-id="6fe07-117">La prochaine fois que vous démarrez Windows PowerShell, le Skype pour module de Business Connector d’en ligne est automatiquement importé.</span><span class="sxs-lookup"><span data-stu-id="6fe07-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="6fe07-118">Sachez que vous obtenez un message d’erreur, et le module ne sera pas chargé, si vous n’exécutez pas Windows PowerShell sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6fe07-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="6fe07-119">En plus d’installer le Skype pour module de Business Connector d’en ligne, SkypeOnlinePowershell.exe installe également les trois autres composants : 1) l’identité Service Client Runtime Library IDCRL (), permet de gérer l’authentification d’un client Skype pour entreprise En ligne ; 2).NET Framework 4.5 ; et 3) du package redistribuable Microsoft Visual C++ 2012 (x64) (version 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="6fe07-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="6fe07-120">.NET Framework 4.5 fournit l’infrastructure utilisée pour générer et exécuter des applications .NET, y compris Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fe07-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="6fe07-121">Le package redistribuable Visual C++ installe les composants d’exécution de Visual C++ pour les ordinateurs qui ne disposent pas de Microsoft Visual Studio 2012 est installé.</span><span class="sxs-lookup"><span data-stu-id="6fe07-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="6fe07-122">Pour vérifier le numéro de version du module connecteur qui est actuellement installé sur votre ordinateur, ouvrez le panneau de configuration, ouvrez **programmes et fonctionnalités**et puis vérifiez le numéro de version pour le **Skype pour Business Online, Module de Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6fe07-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6fe07-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6fe07-123">Related topics</span></span>
[<span data-ttu-id="6fe07-124">Configurer votre ordinateur pour Skype pour la gestion d’entreprise en ligne à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fe07-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
