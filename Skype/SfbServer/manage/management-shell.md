---
title: Skype Entreprise Server Management Shell
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration des serveurs. Il est basé sur Windows PowerShell et inclut un ensemble complet de la gestion et l’administration des applets de commande qui sont spécifiques à Skype et produits Lync server.
ms.openlocfilehash: 243ff7a684bb14f73ef9f4836ce00e8048fbb236
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199230"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="0a261-104">Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="0a261-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="0a261-105">Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration des serveurs.</span><span class="sxs-lookup"><span data-stu-id="0a261-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="0a261-106">Il est basé sur Windows PowerShell et inclut un ensemble complet de la gestion et l’administration des applets de commande qui sont spécifiques à Skype et produits Lync server.</span><span class="sxs-lookup"><span data-stu-id="0a261-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="0a261-107">Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="0a261-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="0a261-108">Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="0a261-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="0a261-109">Windows PowerShell a été initialement introduite comme une version téléchargeable pour le système d’exploitation Windows au plus tard en 2006 et ont été intégré à l’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="0a261-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="0a261-110">Elle a été intégrée à la plupart des produits Microsoft Server, y compris les serveurs Lync et Skype commençant par Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0a261-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="0a261-111">Plus de 700 Lync et Skype spécifiques des applets de commande sont disponibles dans le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0a261-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a261-112">Skype pour la référence de l’entreprise a déplacé vers docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0a261-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="0a261-113">Cliquez sur les liens ci-dessous vous dirige vers la nouvelle page docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0a261-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="0a261-114">Le contenu est maintenant ouvrir Corée et disponibles pour des contributions par le biais de référentiels.</span><span class="sxs-lookup"><span data-stu-id="0a261-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="0a261-115">Vous souhaitez contribuer au ?</span><span class="sxs-lookup"><span data-stu-id="0a261-115">Interested in contributing?</span></span> <span data-ttu-id="0a261-116">Extrayez le fichier README dans l’emprunteuses ici :[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="0a261-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="0a261-117">Skype pour Business Server est fourni avec plus de 700 applets de commande qui permettent aux administrateurs de gérer Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0a261-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0a261-118">Vous pouvez obtenir de l’aide sur une applet de commande directement à partir de la ligne de commande en tapant une commande similaire à la suivante :</span><span class="sxs-lookup"><span data-stu-id="0a261-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="0a261-119">La commande précédente permet d’obtenir de l’aide concernant l’applet de commande **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="0a261-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="0a261-120">Pour afficher l’aide d’une cmdlet différente, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="0a261-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="0a261-121">Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype Entreprise Server, tapez les éléments suivants à l’invite de commandes shell :</span><span class="sxs-lookup"><span data-stu-id="0a261-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="0a261-122">Choses à savoir sur Windows PowerShell dans Skype pour Business Server :</span><span class="sxs-lookup"><span data-stu-id="0a261-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="0a261-123">Pour exécuter le Skype pour les applets de commande Business Server, ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0a261-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0a261-124">Si vous ouvrez une fenêtre Windows PowerShell, plutôt que la Skype pour Business Server Management Shell, par défaut vous ne pouvez pas être en mesure d’exécuter les applets de commande Skype.</span><span class="sxs-lookup"><span data-stu-id="0a261-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="0a261-125">Pour exécuter Skype pour les applets de commande Business Server à partir de Windows PowerShell, tapez tout d’abord ce qui suit à l’invite de commandes Windows PowerShell : >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="0a261-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="0a261-126">Skype pour Business Server Management Shell est installé automatiquement sur chaque Skype pour Business Server Enterprise Edition serveur frontal ou Standard Edition server.</span><span class="sxs-lookup"><span data-stu-id="0a261-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="0a261-127">Vous pouvez mettre à jour le Skype pour le contenu d’aide Business Server Management Shell en exécutant l’applet de commande [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0a261-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="0a261-128">L’applet de commande Update-Help télécharge et installe les fichiers aide le plus récents disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour Skype pour les applets de commande Business.</span><span class="sxs-lookup"><span data-stu-id="0a261-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="0a261-129">Par défaut, l’applet de commande **Update-Help** met à jour tous les modules installés sur votre Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="0a261-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="0a261-130">Si vous voulez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre _Module_ pour limiter la portée de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="0a261-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="0a261-131">L’exemple suivant met à jour uniquement la Skype pour le module d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="0a261-131">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="0a261-132">Si vous devez mettre à jour de l’aide sur les serveurs qui ne sont pas connectés à internet, vous pouvez utiliser l’applet de commande [Enregistrer-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) pour obtenir la dernière version de l’aide et enregistrez-le dans un emplacement que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="0a261-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="0a261-133">Vous pouvez ensuite utiliser l’applet de commande **Update-Help** avec le paramètre _- SourcePath_ sur les serveurs non connectés à internet pour obtenir de l’aide mis à jour à partir de l’emplacement que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0a261-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="0a261-134">L’exemple suivant montre comment enregistrer les fichiers d’aide dans un partage de fichiers réseau, puis mettre à jour de l’aide de la Skype pour le module d’entreprise à partir du partage de fichier.</span><span class="sxs-lookup"><span data-stu-id="0a261-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="0a261-135">Pour plus d’informations, voir [à propos d’aide actualisable](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="0a261-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a261-136">Si vous utilisez PowerShell à distance vous devrez peut-être autoriser les communications à travers un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="0a261-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="0a261-137">Pour en savoir plus sur les ports utilise de communication à distance PowerShell, voir [quel Port ne prend PowerShell à distance utiliser ?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="0a261-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

