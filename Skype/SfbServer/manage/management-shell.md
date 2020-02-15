---
title: Skype Entreprise Server Management Shell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion des serveurs. Il est basé sur Windows PowerShell et inclut un ensemble complet d’applets de commande de gestion et d’administration qui sont propres à Skype et aux produits Lync Server hérités.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044256"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="0c760-104">Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="0c760-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="0c760-105">Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion des serveurs.</span><span class="sxs-lookup"><span data-stu-id="0c760-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="0c760-106">Il est basé sur Windows PowerShell et inclut un ensemble complet d’applets de commande de gestion et d’administration qui sont propres à Skype et aux produits Lync Server hérités.</span><span class="sxs-lookup"><span data-stu-id="0c760-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="0c760-107">Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="0c760-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="0c760-108">Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="0c760-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="0c760-109">Windows PowerShell a été introduit pour la première fois en tant que version téléchargeable pour le système d’exploitation Windows en retard dans 2006, et a été incorporée comme interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="0c760-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="0c760-110">Elle a été incorporée dans la plupart des produits serveur Microsoft, y compris les serveurs Lync et Skype commençant par Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0c760-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="0c760-111">Il existe plus de 700 applets de commande spécifiques à Lync et Skype disponibles dans Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0c760-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c760-112">La référence de cmdlet Skype entreprise a été déplacée vers docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0c760-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="0c760-113">Cliquez sur les liens ci-dessous pour accéder à la nouvelle page docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0c760-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="0c760-114">Le contenu est désormais ouvert et disponible pour les contributions de la Communauté via GitHub.</span><span class="sxs-lookup"><span data-stu-id="0c760-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="0c760-115">Vous souhaitez contribuer ?</span><span class="sxs-lookup"><span data-stu-id="0c760-115">Interested in contributing?</span></span> <span data-ttu-id="0c760-116">Consultez le fichier Lisez-moi dans le référentiel ici :[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="0c760-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="0c760-117">Skype entreprise Server est fourni avec plus de 700 cmdlets qui permettent aux administrateurs de gérer Skype entreprise Server à l’aide de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0c760-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0c760-118">Vous pouvez récupérer de l’aide pour une cmdlet directement à partir de la ligne de commande en tapant une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="0c760-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="0c760-119">La commande précédente permet d’obtenir de l’aide concernant l’applet de commande **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="0c760-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="0c760-120">Pour afficher l’aide d’une applet de commande différente, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="0c760-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="0c760-121">Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype entreprise Server, tapez ce qui suit à l’invite de commandes de l’environnement de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="0c760-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="0c760-122">Éléments à connaître sur Windows PowerShell dans Skype entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="0c760-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="0c760-123">Pour exécuter les applets de commande Skype entreprise Server, ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0c760-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0c760-124">Si vous ouvrez une fenêtre Windows PowerShell plutôt que Skype entreprise Server Management Shell, par défaut, il se peut que vous ne puissiez pas exécuter les applets de commande Skype.</span><span class="sxs-lookup"><span data-stu-id="0c760-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="0c760-125">Pour exécuter les applets de commande Skype entreprise Server à partir de Windows PowerShell, tapez d’abord ce qui suit à l’invite de commandes Windows PowerShell : >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="0c760-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="0c760-126">Skype entreprise Server Management Shell est automatiquement installé sur chaque serveur frontal Skype entreprise Server Enterprise Edition ou serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0c760-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="0c760-127">Vous pouvez mettre à jour le contenu de l’aide de Skype entreprise Server Management Shell en exécutant l’applet de commande [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0c760-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="0c760-128">La cmdlet Update-Help télécharge et installe les derniers fichiers d’aide disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour des applets de commande Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c760-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="0c760-129">Par défaut, l’applet de commande **Update-Help** met à jour tous les modules installés sur votre serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c760-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="0c760-130">Si vous souhaitez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre _module_ pour limiter l’étendue de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="0c760-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="0c760-131">L’exemple ci-dessous montre comment mettre à jour uniquement le module Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c760-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="0c760-132">Si vous devez mettre à jour l’aide sur les serveurs qui ne sont pas connectés à Internet, vous pouvez utiliser la cmdlet [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) pour obtenir la dernière version de l’aide et l’enregistrer à un emplacement que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="0c760-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="0c760-133">Vous pouvez ensuite utiliser l’applet de commande **Update-Help** avec le paramètre _-SourcePath_ sur les serveurs qui ne sont pas connectés à Internet pour obtenir l’aide mise à jour à partir de l’emplacement que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0c760-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="0c760-134">L’exemple suivant montre comment enregistrer les fichiers d’aide sur un partage de fichiers réseau, puis mettre à jour l’aide pour le module Skype entreprise à partir du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0c760-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="0c760-135">Pour plus d’informations, consultez la rubrique [à propos de l’aide pouvant être mise à jour](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c760-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0c760-136">Si vous utilisez PowerShell à distance, vous devrez peut-être autoriser la communication via un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="0c760-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="0c760-137">Pour en savoir plus sur les ports utilisés par la communication à distance PowerShell, consultez la rubrique [quel port est utilisé par PowerShell Remoting ?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="0c760-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

