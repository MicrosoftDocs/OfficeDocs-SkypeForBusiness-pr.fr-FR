---
title: Utilisation de PowerShell pour gérer des équipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Apprenez à utiliser Windows PowerShell pour gérer l’ensemble des fonctionnalités disponibles dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c8eb0c37f71972bb20fac60706ff7a369d971d4
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678345"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="9ca39-103">Utilisation de PowerShell pour gérer des équipes</span><span class="sxs-lookup"><span data-stu-id="9ca39-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="9ca39-104">Fonctionnalités dans les équipes peuvent être gérées à l’aide de PowerShell ou Microsoft Teams et Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="9ca39-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="9ca39-105">! [Note] Toutes les fonctionnalités dans les équipes peuvent être gérés à l’aide du module de connecteur d’équipes.</span><span class="sxs-lookup"><span data-stu-id="9ca39-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="9ca39-106">Vous devrez peut-être utiliser la Skype pour Business connector.</span><span class="sxs-lookup"><span data-stu-id="9ca39-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="9ca39-107">Voir [télécharger et installer le Skype pour connecteur Business en ligne](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="9ca39-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="9ca39-108">Étape 1 : conditions préalables</span><span class="sxs-lookup"><span data-stu-id="9ca39-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="9ca39-109">Gestion à distance de Microsoft Teams à l’aide de PowerShell est pris en charge uniquement sur les ordinateurs 64 bits qui exécute un des systèmes d’exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="9ca39-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="9ca39-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ca39-110">Windows 10</span></span>
- <span data-ttu-id="9ca39-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9ca39-111">Windows 8.1</span></span>
- <span data-ttu-id="9ca39-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="9ca39-112">Windows 8</span></span> 
- <span data-ttu-id="9ca39-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9ca39-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="9ca39-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9ca39-114">Windows Server 2012</span></span>
- <span data-ttu-id="9ca39-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="9ca39-115">Windows Server 2008</span></span>
- <span data-ttu-id="9ca39-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="9ca39-116">Windows 7</span></span>
    
<span data-ttu-id="9ca39-117">En plus d’un système d’exploitation pris en charge, l’ordinateur doit également exécuter les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9ca39-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="9ca39-118">PowerShell version 3.0 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="9ca39-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="9ca39-119">Module de connecteur équipes PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca39-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="9ca39-120">Étape 2 : Installer PowerShell version 3.0 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="9ca39-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="9ca39-121">Utilisez cette rubrique pour une assistance</span><span class="sxs-lookup"><span data-stu-id="9ca39-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="9ca39-122">Étape 3 : Télécharger et installer le module de connecteur d’équipes</span><span class="sxs-lookup"><span data-stu-id="9ca39-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="9ca39-123">Utilisez cette rubrique pour une assistance</span><span class="sxs-lookup"><span data-stu-id="9ca39-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="9ca39-124">Installez le module le plus récent à partir de la galerie de PowerShell à l’aide :</span><span class="sxs-lookup"><span data-stu-id="9ca39-124">Install the latest module from the PowerShell Gallery using:</span></span> 
  
  <span data-ttu-id="9ca39-125">Install-Module MicrosoftTeams</span><span class="sxs-lookup"><span data-stu-id="9ca39-125">Install-Module MicrosoftTeams</span></span>

<span data-ttu-id="9ca39-126">Ou, pour plus d’informations, le package peut être trouvé :https://www.powershellgallery.com/packages/MicrosoftTeams/</span><span class="sxs-lookup"><span data-stu-id="9ca39-126">Or, for more information, the package can be found here: https://www.powershellgallery.com/packages/MicrosoftTeams/</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="9ca39-127">Étape 4 : Se connecter en utilisant le module de connecteur d’équipes</span><span class="sxs-lookup"><span data-stu-id="9ca39-127">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="9ca39-128">Utilisez cette rubrique pour une assistance</span><span class="sxs-lookup"><span data-stu-id="9ca39-128">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="9ca39-129">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9ca39-129">Related topics</span></span>
- [<span data-ttu-id="9ca39-130">Gérer les fonctionnalités des équipes avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca39-130">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)
