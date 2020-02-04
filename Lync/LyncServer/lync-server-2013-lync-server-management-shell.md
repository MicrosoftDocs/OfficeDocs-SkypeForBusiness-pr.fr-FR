---
title: 'Lync Server 2013 : Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="75fbf-102">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="75fbf-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75fbf-103">_**Dernière modification de la rubrique :** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="75fbf-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75fbf-104">Référence sur les applets de la cmdlet Skype entreprise a été déplacée vers docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="75fbf-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="75fbf-105">Cliquer sur les liens ci-dessous vous permet d’atteindre la nouvelle page docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="75fbf-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="75fbf-106">Le contenu est désormais ouvert et est disponible pour les contributions de la Communauté par le biais de GitHub.</span><span class="sxs-lookup"><span data-stu-id="75fbf-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="75fbf-107">Vous voulez participer ?</span><span class="sxs-lookup"><span data-stu-id="75fbf-107">Interested in contributing?</span></span> <span data-ttu-id="75fbf-108">Consultez le fichier README dans le référentiel Samples :<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="75fbf-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="75fbf-109">Microsoft Lync Server 2010 a introduit un grand nombre de fonctionnalités nouvelles et améliorées par rapport à ce qui était disponible dans Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="75fbf-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="75fbf-110">L’une des améliorations est le mode de gestion de votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="75fbf-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="75fbf-111">Par exemple, il existe une nouvelle interface utilisateur, appelée panneau de configuration de Lync Server, qui représente un important changement de l’utilisation de la plupart des personnes avec la console de gestion Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75fbf-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="75fbf-112">L’autre amélioration majeure de la gestion est l’inclusion de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75fbf-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="75fbf-113">Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="75fbf-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="75fbf-114">Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="75fbf-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="75fbf-115">Windows PowerShell s’est d’abord présenté comme une version téléchargeable du système d’exploitation Windows en retard dans 2006, et il a été intégré en tant qu’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="75fbf-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="75fbf-116">À partir de ce point, il a continué de grandir et il a été intégré à la plupart des produits Microsoft Server, les plus récents d’eux étant Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75fbf-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="75fbf-117">Lync Server 2010 a présenté des applets de passe spécifiques à 550, que vous pouvez utiliser pour gérer chaque aspect de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="75fbf-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="75fbf-118">Les sections suivantes contiennent une liste des applets de commande et leurs descriptions.</span><span class="sxs-lookup"><span data-stu-id="75fbf-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="75fbf-119">Ces informations sont aussi disponibles directement à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="75fbf-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="75fbf-120">Tapez simplement ce qui suit dans l’invite de commandes de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="75fbf-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="75fbf-121">Par exemple, pour accéder à l’aide depuis l’invite de commande de l’applet de commande **New-CsVoicePolicy** tapez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="75fbf-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="75fbf-122">Éléments à connaître sur Windows PowerShell dans Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="75fbf-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="75fbf-123">Pour exécuter les applets de cmdlet Lync Server, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75fbf-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="75fbf-124">Par défaut, si vous ouvrez une fenêtre Windows PowerShell plutôt que Lync Server Management Shell, vous ne serez pas en mesure d’exécuter les applets de cmdlet de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75fbf-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="75fbf-125">Pour exécuter les applets de commande Lync Server à partir de Windows PowerShell, commencez par taper la commande suivante à l’invite de commandes Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="75fbf-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="75fbf-126">Importer-module Lync</span><span class="sxs-lookup"><span data-stu-id="75fbf-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="75fbf-127">Lync Server Management Shell est automatiquement installé sur chaque serveur frontal Lync Server Enterprise Edition ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="75fbf-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="75fbf-128">Des informations nouvelles et mises à jour, des exemples de scripts et de l’aide pour la mise en route et en savoir plus sur les applets de cmdlet Windows PowerShell et Microsoft [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)Lync Server 2013 sont disponibles sur le blog Windows PowerShell de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75fbf-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

