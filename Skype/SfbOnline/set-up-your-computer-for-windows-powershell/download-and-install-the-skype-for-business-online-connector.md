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
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="55f67-103">Télécharger et installer le module Skype Entreprise Online Connector</span><span class="sxs-lookup"><span data-stu-id="55f67-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="55f67-104">La dernière version [publique de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un seul module pour la gestion de Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55f67-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="55f67-105">Le module Skype Entreprise Online Connector inclut la cmdlet **New-CsOnlineSession,** qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="55f67-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="55f67-106">Ce module, pris en charge uniquement sur les ordinateurs 64 bits (voir Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide de [Windows PowerShell](set-up-your-computer-for-windows-powershell.md) pour plus d’informations), peut être téléchargé à partir du Centre de téléchargement Microsoft à l’adresse [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="55f67-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="55f67-107">Téléchargez le SkypeOnlinePowershell.exe fichier, puis terminez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="55f67-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="55f67-108">Double-cliquez sur **leSkypeOnlinePowershell.exe** fichier.</span><span class="sxs-lookup"><span data-stu-id="55f67-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="55f67-109">Dans l’Assistant configuration de Skype Entreprise Online Windows PowerShell, dans la page Termes du contrat de licence logiciel **Microsoft,** sélectionnez J’accepte les termes du contrat de **licence,** puis cliquez sur **Installer.**</span><span class="sxs-lookup"><span data-stu-id="55f67-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="55f67-110">Si la boîte **de dialogue Contrôle de compte** d’utilisateur s’affiche, cliquez sur **Oui** pour poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="55f67-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="55f67-111">Sur la page **Skype Entreprise Online Terminée,** cliquez Windows PowerShell module final, cliquez **sur Terminer.**</span><span class="sxs-lookup"><span data-stu-id="55f67-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="55f67-112">Le programme d’installation copie le module Skype Entreprise Online Connector (et la cmdlet **New-CsOnlineSession)** sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="55f67-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="55f67-113">Pour accéder au module, démarrez une session Windows PowerShell d’informations d’identification d’administrateur, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="55f67-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="55f67-114">Si vous ne voulez pas taper cette commande chaque fois que vous démarrez une Windows PowerShell, vous pouvez l’ajouter à votre Windows PowerShell profil.</span><span class="sxs-lookup"><span data-stu-id="55f67-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="55f67-115">Pour ce faire, à l’invite de commandes, tapez la commande Windows PowerShell suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="55f67-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="55f67-116">Lorsque le Bloc-notes s’affiche, ajoutez la ligne suivante au bas des commandes déjà présentes dans le profil (le cas dessous) :</span><span class="sxs-lookup"><span data-stu-id="55f67-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="55f67-117">Enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="55f67-117">Save the file.</span></span> <span data-ttu-id="55f67-118">Au prochain démarrage d Windows PowerShell, le module Skype Entreprise Online Connector sera importé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="55f67-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="55f67-119">Notez qu’un message d’erreur s’agit d’un message d’erreur et que le module n’est pas chargé, si vous n’exécutez pas Windows PowerShell des informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="55f67-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="55f67-120">Outre l’installation du module Skype Entreprise Online Connector, SkypeOnlinePowershell.exe installe également trois composants supplémentaires : 1) la bibliothèque IDCRL (Identity Service Client Runtime Library), qui permet de gérer l’authentification client à Skype Entreprise Online . 2) .NET Framework 4.5; et, 3) le package redistribuable Microsoft Visual C++ 2012 (x64) (version 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="55f67-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="55f67-121">.NET Framework 4.5 fournit l’infrastructure utilisée pour la création et l’exécution d’applications .NET, dont Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55f67-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="55f67-122">Le package redistribuable Visual C++ installe les composants Runtime Visual C++ pour les ordinateurs sur qui Microsoft Visual Studio 2012 n’est pas installé.</span><span class="sxs-lookup"><span data-stu-id="55f67-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="55f67-123">Pour vérifier le numéro de version du module Connector actuellement installé sur votre ordinateur, ouvrez le Panneau de commandes, ouvrez Programmes et fonctionnalités, puis vérifiez le numéro de version du Module Windows PowerShell Skype Entreprise **Online.**</span><span class="sxs-lookup"><span data-stu-id="55f67-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="55f67-124">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="55f67-124">Related topics</span></span>
[<span data-ttu-id="55f67-125">Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55f67-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
