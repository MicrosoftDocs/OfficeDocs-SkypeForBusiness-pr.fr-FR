---
title: 'Lync Server 2013 : Configuration logicielle requise pour les outils d’administration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95dfed4d6cf69950a0e17ab6826d79ee7e7a68cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="faa21-102">Configuration logicielle requise pour les outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faa21-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faa21-103">_**Dernière modification de la rubrique:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="faa21-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="faa21-104">Cette rubrique décrit les logiciels requis pour installer et utiliser les outils d’administration de Lync Server 2013 en plus de la configuration requise du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="faa21-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="faa21-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="faa21-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="faa21-106">L’édition 64 bits de Microsoft .NET Framework 4,5 est requise pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="faa21-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="faa21-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="faa21-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="faa21-108">Windows PowerShell 3,0 est requis pour l’exécution de tous les composants de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="faa21-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="faa21-109">Pour plus d’informations, voir [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="faa21-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="faa21-110">Windows Installer version 4,5</span><span class="sxs-lookup"><span data-stu-id="faa21-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="faa21-111">Lync Server 2013 utilise la technologie Windows Installer pour installer, désinstaller et gérer divers rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="faa21-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="faa21-112">La version 4,5 de Windows Installer est disponible en tant que composant redistribuable pour le système d’exploitation Windows Server.</span><span class="sxs-lookup"><span data-stu-id="faa21-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="faa21-113">Windows Installer 4,5 est fourni avec Windows Server 2012 R2, Windows Server 2012 et Windows Server 2008 R2, ce qui signifie que vous n’avez pas besoin de télécharger l’utilitaire pour les ordinateurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="faa21-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="faa21-114">(Lync Server 2013 ne peut être installé que sur les ordinateurs exécutant Windows Server 2012 R2, Windows Server 2012 ou Windows Server 2008 R2.)</span><span class="sxs-lookup"><span data-stu-id="faa21-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="faa21-115">Toutefois, si vous voulez installer Lync Server Management Shell ou le générateur de topologie de Lync Server sur une station de travail administrateur, vous devrez peut-être télécharger le programme d’installation 4,5.</span><span class="sxs-lookup"><span data-stu-id="faa21-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="faa21-116">Cet utilitaire est fourni avec Windows 7 et Windows 2008 R2, mais pas pour les versions antérieures du système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="faa21-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="faa21-117">Vous pouvez télécharger Windows Installer 4,5 à partir du centre de téléchargement <http://go.microsoft.com/fwlink/p/?linkid=197395>Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="faa21-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <http://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="faa21-118">Plug-in de navigateur Microsoft Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="faa21-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="faa21-119">Le panneau de configuration de Lync Server 2013 est un outil Web qui nécessite l’installation de la dernière version du plug-in de navigateur Microsoft Silverlight 5.</span><span class="sxs-lookup"><span data-stu-id="faa21-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="faa21-120">Lorsque vous démarrez le panneau de configuration de Lync Server 2013, si ce logiciel n’est pas installé ou si vous avez installé une version antérieure, le panneau de configuration de Lync Server 2013 vous invite à installer la version requise.</span><span class="sxs-lookup"><span data-stu-id="faa21-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="faa21-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="faa21-121">See Also</span></span>


[<span data-ttu-id="faa21-122">Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faa21-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="faa21-123">Exigences d’infrastructure des outils d’administration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faa21-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="faa21-124">Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faa21-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

