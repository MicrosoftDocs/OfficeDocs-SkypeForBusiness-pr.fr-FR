---
title: Skype Entreprise Server 2015 Management Shell
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration du serveur. Il est basé sur Windows PowerShell et inclut un ensemble complet de gestion et administration applets de commande spécifiques à Skype et anciens produits de serveur Lync.
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a><span data-ttu-id="f9a1a-104">Skype Entreprise Server 2015 Management Shell</span><span class="sxs-lookup"><span data-stu-id="f9a1a-104">Skype for Business Server 2015 Management Shell</span></span>
 
<span data-ttu-id="f9a1a-105">Le Skype pour Business Server Management Shell fournit l’interface de ligne de commande pour la gestion et l’administration du serveur.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="f9a1a-106">Il est basé sur Windows PowerShell et inclut un ensemble complet de gestion et administration applets de commande spécifiques à Skype et anciens produits de serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="f9a1a-107">Windows PowerShell vous permet de gérer les applications de Microsoft à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="f9a1a-108">Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="f9a1a-109">Windows PowerShell a été introduite comme une version téléchargeable pour le système d’exploitation Windows plus tard en 2006 et ont été intégré à l’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="f9a1a-110">Il a été incorporé dans la plupart des produits Microsoft Server, y compris les serveurs Lync et Skype à partir de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="f9a1a-111">Il existe plus de 700 Lync Skype des applets de commande et dans le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9a1a-112">Skype pour référence d’applet de commande entreprise a déplacé vers docs.microsoft.com. En cliquant sur les liens ci-dessous vous amènera à la page docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-112">Skype for Business cmdlet reference has moved to docs.microsoft.com. Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="f9a1a-113">Le contenu est désormais ouvert Corée et disponible pour des contributions via GitHub.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-113">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="f9a1a-114">Vous souhaitez contribuer ?</span><span class="sxs-lookup"><span data-stu-id="f9a1a-114">Interested in contributing?</span></span> <span data-ttu-id="f9a1a-115">Consultez le fichier README dans le mis en pension ici :[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="f9a1a-115">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="f9a1a-116">Skype pour Business Server 2015 est livré avec plus de 700 applets de commande qui permettent aux administrateurs de gérer Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-116">Skype for Business Server 2015 ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f9a1a-117">Vous pouvez obtenir de l’aide sur une applet de commande directement à partir de la ligne de commande en tapant une commande similaire à la suivante :</span><span class="sxs-lookup"><span data-stu-id="f9a1a-117">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="f9a1a-118">La commande précédente extrait l’aide complète disponible pour l’applet de commande **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="f9a1a-118">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="f9a1a-119">Pour afficher l’aide pour une applet de commande différent, remplacez **New-CsVoicePolicy** avec le nom de l’applet de commande pour lequel vous souhaitez obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-119">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="f9a1a-120">Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Skype Entreprise Server, tapez les éléments suivants à l’invite de commandes shell :</span><span class="sxs-lookup"><span data-stu-id="f9a1a-120">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="f9a1a-121">Choses à savoir sur Windows PowerShell dans Skype pour Business Server :</span><span class="sxs-lookup"><span data-stu-id="f9a1a-121">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="f9a1a-122">Pour exécuter le Skype pour les applets de commande de serveur de l’entreprise, ouvrez la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-122">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f9a1a-123">Si vous ouvrez une fenêtre de Windows PowerShell, plutôt que le Skype pour Business Server Management Shell, par défaut vous ne peut-être pas être en mesure d’exécuter les applets de commande de Skype.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-123">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="f9a1a-124">Pour exécuter Skype pour les applets de commande Business Server à partir de Windows PowerShell, tapez ce qui suit à l’invite de commande Windows PowerShell : >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="f9a1a-124">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="f9a1a-125">Skype pour Business Server Management Shell est automatiquement installé sur chaque Skype pour serveur Business Server Enterprise Edition serveur frontal ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-125">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="f9a1a-126">Vous pouvez mettre à jour le Skype Business Server Management Shell contenu d’aide en exécutant la cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f9a1a-126">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="f9a1a-127">L’applet de commande Update-Help télécharge et installe les fichiers aide le plus récents disponibles pour tous les modules installés sur votre ordinateur, y compris les mises à jour Skype pour les cmdlets de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-127">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="f9a1a-128">Par défaut, l’applet de commande **Update-Help** met à jour tous les modules installés sur votre Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-128">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="f9a1a-129">Si vous souhaitez mettre à jour uniquement certains modules, vous pouvez utiliser le paramètre de _Module_ pour limiter l’étendue de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-129">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="f9a1a-130">L’exemple suivant met à jour uniquement le Skype pour le module d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-130">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="f9a1a-131">Si vous devez mettre à jour l’aide sur les serveurs qui ne sont pas connectés à internet, vous pouvez utiliser l’applet de commande [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) pour obtenir la dernière version de l’aide et l’enregistrer à un emplacement que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-131">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="f9a1a-132">Vous pouvez ensuite utiliser l’applet de commande **Update-Help** avec le paramètre _- SourcePath_ sur les serveurs non connectés à internet pour obtenir de l’aide mis à jour à partir de l’emplacement que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-132">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="f9a1a-133">L’exemple suivant montre comment enregistrer les fichiers d’aide pour un partage de fichiers réseau, puis mettre à jour de l’aide pour le Skype pour le module d’entreprise à partir du partage de fichier.</span><span class="sxs-lookup"><span data-stu-id="f9a1a-133">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="f9a1a-134">Pour plus d’informations, consultez [à propos d’aide mis à jour](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="f9a1a-134">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    

