---
title: Installer le package de compatibilité descendante WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b8d474ff451a488124ebfbae0ff0872a6cca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="392da-102">Installer le package de compatibilité descendante WMI</span><span class="sxs-lookup"><span data-stu-id="392da-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="392da-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="392da-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="392da-104">Si vous essayez d’exécuter l’Assistant Fusion du générateur de topologie sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :</span><span class="sxs-lookup"><span data-stu-id="392da-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="392da-105">![Message d’erreur WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Message d’erreur WMI")</span><span class="sxs-lookup"><span data-stu-id="392da-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="392da-106">Si vous essayez d’exécuter l’applet **de commande Merge-CsLegacytopology** sans installer le package de compatibilité descendante WMI, le message d’erreur suivant s’affiche :</span><span class="sxs-lookup"><span data-stu-id="392da-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="392da-107">![Erreur du fournisseur WMI Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Erreur du fournisseur WMI Windows PowerShell")</span><span class="sxs-lookup"><span data-stu-id="392da-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="392da-108">Pour installer le package de compatibilité descendante WMI</span><span class="sxs-lookup"><span data-stu-id="392da-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="392da-109">À partir de votre support d’installation \\,\\accédez\\à\\configuration de configuration de OCSWMIBC. Portion.</span><span class="sxs-lookup"><span data-stu-id="392da-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="392da-110">Installez OCSWMIBC. Portion.</span><span class="sxs-lookup"><span data-stu-id="392da-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="392da-111">OCSWMIBC. msi doit être installé sur l’ordinateur sur lequel s’exécute l’Assistant Fusion du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="392da-111">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run.</span></span> <span data-ttu-id="392da-112">Toutefois, nous vous recommandons d’installer OCSWMIBC. msi sur tous les serveurs frontaux de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="392da-112">However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="392da-113">OCSWMIBC. msi peut être installé sur n’importe quel ordinateur du domaine sur lequel sont installés les composants principaux de Lync Server 2013 et Lync Server 2013 Management Shell et ayant accès à la topologie Office Communications Server 2007 R2 (fournisseur WMI sur le domaine Active Directory) Services (AD DS) et SQL Server).</span><span class="sxs-lookup"><span data-stu-id="392da-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

