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
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="b2185-103">Télécharger et installer le module Skype entreprise Online Connector</span><span class="sxs-lookup"><span data-stu-id="b2185-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="b2185-104">Le module Skype entreprise Online Connector inclut l’applet **de commande New-CsOnlineSession** , qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="b2185-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="b2185-105">Ce module, qui est pris en charge uniquement sur les ordinateurs 64 (pour plus d’informations, reportez-vous à la rubrique [configuration de votre ordinateur pour la gestion de Skype entreprise Online avec Windows PowerShell](set-up-your-computer-for-windows-powershell.md) pour plus d’informations) peut être téléchargé à partir du centre de téléchargement Microsoft [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="b2185-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="b2185-106">Téléchargez le fichier SkypeOnlinePowershell. exe, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b2185-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="b2185-107">Double-cliquez sur le fichier **SkypeOnlinePowershell. exe** .</span><span class="sxs-lookup"><span data-stu-id="b2185-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="b2185-108">Dans l’Assistant Configuration de Skype entreprise Online et Windows PowerShell, dans la page termes du contrat de **licence logiciel Microsoft** , sélectionnez **J’accepte les conditions du contrat de licence**, puis cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="b2185-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="b2185-109">Si la boîte de dialogue **contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui** pour continuer l’installation.</span><span class="sxs-lookup"><span data-stu-id="b2185-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="b2185-110">Dans la page de l’état **terminé de Skype entreprise Online,** cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b2185-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="b2185-111">Le programme d’installation copie le module Skype entreprise Online Connector (et l’applet **de nouvelle cmdlet New-CsOnlineSession** ) sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b2185-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="b2185-112">Pour accéder au module, démarrez une session Windows PowerShell sous informations d’identification d’administrateur, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2185-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="b2185-113">Si vous ne souhaitez pas entrer cette commande chaque fois que vous démarrez Windows PowerShell, vous pouvez ajouter la commande à votre profil Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2185-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="b2185-114">Pour ce faire, tapez la commande suivante à l’invite Windows PowerShell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="b2185-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="b2185-115">Lorsque le bloc-notes s’affiche, ajoutez la ligne suivante en bas des commandes déjà présentes dans le profil (le cas échéant) :</span><span class="sxs-lookup"><span data-stu-id="b2185-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="b2185-116">Enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="b2185-116">Save the file.</span></span> <span data-ttu-id="b2185-117">La prochaine fois que vous démarrez Windows PowerShell, le module connecteur Skype entreprise Online sera automatiquement importé.</span><span class="sxs-lookup"><span data-stu-id="b2185-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="b2185-118">Sachez que vous recevrez un message d’erreur et que le module ne sera pas chargé, si vous n’exécutez pas Windows PowerShell sous informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="b2185-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="b2185-119">En plus d’installer le module de connecteur Skype entreprise Online, SkypeOnlinePowershell. exe installe également trois composants supplémentaires : 1) la bibliothèque d’exécution du cliente de service d’identité (IDCRL), utilisée pour gérer l’authentification du client sur Skype entreprise Enchères 2) .NET Framework 4,5 ; et 3) le package Microsoft Visual C++ 2012 redistribuable (x64) (version 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="b2185-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="b2185-120">.NET Framework 4,5 fournit l’infrastructure utilisée pour générer et exécuter des applications .NET, y compris Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2185-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="b2185-121">Le package redistribuable Visual C++ installe des composants runtime Visual C++ pour les ordinateurs sur lesquels Microsoft Visual Studio 2012 n’est pas installé.</span><span class="sxs-lookup"><span data-stu-id="b2185-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="b2185-122">Pour vérifier le numéro de version du module de connecteur actuellement installé sur votre ordinateur, ouvrez le panneau de configuration, ouvrez **programmes et fonctionnalités**, puis vérifiez le numéro de version du **module Skype entreprise Online, Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b2185-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b2185-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b2185-123">Related topics</span></span>
[<span data-ttu-id="b2185-124">Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2185-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
