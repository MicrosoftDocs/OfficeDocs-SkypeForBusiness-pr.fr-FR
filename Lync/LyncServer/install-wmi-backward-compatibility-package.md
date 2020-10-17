---
title: Installer le package de compatibilité descendante WMI
description: Installez le package de compatibilité descendante WMI.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9062e209981fd180b8772801960bd94d2256513a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568990"
---
# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="fa482-103">Installer le package de compatibilité descendante WMI</span><span class="sxs-lookup"><span data-stu-id="fa482-103">Install WMI Backward Compatibility package</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa482-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fa482-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fa482-105">Si vous essayez d’exécuter l’Assistant Fusion du Générateur de topologie sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :</span><span class="sxs-lookup"><span data-stu-id="fa482-105">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="fa482-106">![Message d’erreur WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Message d’erreur WMI")</span><span class="sxs-lookup"><span data-stu-id="fa482-106">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="fa482-107">Si vous essayez d’exécuter l’applet de commande **Merge-CsLegacytopology** sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :</span><span class="sxs-lookup"><span data-stu-id="fa482-107">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="fa482-108">![Erreur du fournisseur WMI Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Erreur du fournisseur WMI Windows PowerShell")</span><span class="sxs-lookup"><span data-stu-id="fa482-108">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="fa482-109">Pour installer le package de compatibilité descendante WMI</span><span class="sxs-lookup"><span data-stu-id="fa482-109">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="fa482-110">À partir de votre support d’installation, naviguez jusqu’à \\ Setup \\ AMD64 \\ Setup \\OCSWMIBC.MSI.</span><span class="sxs-lookup"><span data-stu-id="fa482-110">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="fa482-111">Installez OCSWMIBC.MSI.</span><span class="sxs-lookup"><span data-stu-id="fa482-111">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fa482-p101">OCSWMIBC.msi doit être installé sur l’ordinateur sur lequel l’Assistant Fusion du Générateur de topologie s’exécute. Toutefois, nous recommandons d’installer OCSWMIBC.msi sur tous les serveurs frontaux de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="fa482-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fa482-114">OCSWMIBC.msi peut être installé sur tout ordinateur du domaine sur lequel les composants principaux de Lync Server 2013 et Lync Server 2013 Management Shell sont installés, et ayant accès à la topologie Office Communications Server 2007 R2 (fournisseur WMI aux services de domaine Active Directory (AD DS) et SQL Server).</span><span class="sxs-lookup"><span data-stu-id="fa482-114">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

