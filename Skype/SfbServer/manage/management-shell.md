---
title: Skype Entreprise Server Management Shell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion du serveur. Il repose sur Windows PowerShell et inclut un ensemble complet de cmdlets de gestion et d’administration qui sont spécifiques aux produits Lync Server traditionnels et Skype.
ms.openlocfilehash: 4890194824caaea771d31e008d4546d871d0da8a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991589"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="27413-104">Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="27413-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="27413-105">Skype entreprise Server Management Shell fournit l’interface de ligne de commande pour l’administration et la gestion du serveur.</span><span class="sxs-lookup"><span data-stu-id="27413-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="27413-106">Il repose sur Windows PowerShell et inclut un ensemble complet de cmdlets de gestion et d’administration qui sont spécifiques aux produits Lync Server traditionnels et Skype.</span><span class="sxs-lookup"><span data-stu-id="27413-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="27413-107">Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="27413-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="27413-108">Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="27413-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="27413-109">Windows PowerShell s’est d’abord présenté comme une version téléchargeable du système d’exploitation Windows en retard dans 2006, et il a été intégré en tant qu’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="27413-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="27413-110">Il a été incorporé à la plupart des produits serveur Microsoft, y compris Lync et les serveurs Skype commençant par Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="27413-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="27413-111">Il existe plus de 700 applets de contrôleurs spécifiques Lync et Skype disponibles dans Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="27413-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27413-112">Référence sur les applets de la cmdlet Skype entreprise a été déplacée vers docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="27413-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="27413-113">Cliquer sur les liens ci-dessous vous permet d’atteindre la nouvelle page docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="27413-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="27413-114">Le contenu est désormais ouvert et est disponible pour les contributions de la Communauté par le biais de GitHub.</span><span class="sxs-lookup"><span data-stu-id="27413-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="27413-115">Vous voulez participer ?</span><span class="sxs-lookup"><span data-stu-id="27413-115">Interested in contributing?</span></span> <span data-ttu-id="27413-116">Consultez le fichier README dans le référentiel Samples :[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="27413-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="27413-117">Skype entreprise Server est fourni avec plus de 700 cmdlets qui permettent aux administrateurs de gérer Skype entreprise Server à l’aide de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="27413-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="27413-118">Vous pouvez obtenir de l’aide sur une applet de commande directement à partir de la ligne de commande en tapant une commande similaire à la suivante :</span><span class="sxs-lookup"><span data-stu-id="27413-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="27413-119">La commande précédente permet d’obtenir de l’aide concernant l’applet de commande **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="27413-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="27413-120">Pour afficher l’aide d’une cmdlet différente, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="27413-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="27413-121">Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype Entreprise Server, tapez les éléments suivants à l’invite de commandes shell :</span><span class="sxs-lookup"><span data-stu-id="27413-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="27413-122">Éléments à connaître sur Windows PowerShell dans Skype entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="27413-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="27413-123">Pour exécuter les applets de cmdlet Skype entreprise Server, ouvrez le shell de gestion de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="27413-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="27413-124">Par défaut, si vous ouvrez une fenêtre Windows PowerShell plutôt que Skype entreprise Server Management Shell, vous risquez de ne pas pouvoir exécuter les applets de cmdlet Skype.</span><span class="sxs-lookup"><span data-stu-id="27413-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="27413-125">Pour exécuter les applets de commande Skype entreprise Server à partir de Windows PowerShell, commencez par taper la commande suivante à l’invite de commandes Windows PowerShell : >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="27413-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="27413-126">Skype entreprise Server Management Shell est automatiquement installé sur chaque serveur frontal Skype entreprise Server Enterprise Edition ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="27413-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="27413-127">Vous pouvez mettre à jour le contenu de l’aide de Skype entreprise Server Management Shell en exécutant la cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="27413-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="27413-128">La cmdlet Update-Help télécharge et installe les fichiers d’aide les plus récents disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour apportées aux cmdlets Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="27413-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="27413-129">Par défaut, la cmdlet **Update-Help** entraîne la mise à jour de tous les modules installés sur votre serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="27413-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="27413-130">Si vous voulez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre _Module_ pour limiter la portée de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="27413-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="27413-131">L’exemple suivant met à jour uniquement le module Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="27413-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="27413-132">Si vous avez besoin de mettre à jour l’aide sur des serveurs qui ne sont pas connectés à Internet, vous pouvez utiliser l’applet de contrôle [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) pour obtenir la dernière version de l’aide et l’enregistrer dans un emplacement que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="27413-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="27413-133">Vous pouvez ensuite utiliser l’applet de connexion **Update-Help** avec le paramètre _-CheminSource_ sur des serveurs qui ne sont pas connectés à Internet pour obtenir l’aide mise à jour à partir de l’emplacement que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="27413-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="27413-134">L’exemple suivant montre comment enregistrer les fichiers d’aide sur un partage de fichiers réseau, puis mettre à jour l’aide du module Skype entreprise à partir du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="27413-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="27413-135">Pour obtenir des informations plus détaillées, voir [à propos de l’aide à mettre à jour](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="27413-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="27413-136">Si vous utilisez PowerShell à distance, il est possible que vous deviez autoriser les communications par le biais d’un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="27413-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="27413-137">Pour en savoir plus sur les ports utilisés par les fonctionnalités d’accès distant PowerShell, voir [quel port utilise la communication à distance PowerShell ?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="27413-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

