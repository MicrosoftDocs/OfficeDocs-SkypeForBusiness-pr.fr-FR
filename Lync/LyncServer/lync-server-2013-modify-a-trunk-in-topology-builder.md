---
title: 'Lync Server 2013 : modification d’un Trunk dans le générateur de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1c603aa24a0d31ea87178f740f824ae77f20f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="01e3e-102">Modifier un Trunk dans le générateur de topologies de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e3e-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01e3e-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="01e3e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="01e3e-104">Suivez ces étapes pour modifier l’adresse IP de remplacement et l’identificateur de contournement du Trunk.</span><span class="sxs-lookup"><span data-stu-id="01e3e-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="01e3e-105">Pour modifier l’adresse IP du média de remplacement d’un Trunk</span><span class="sxs-lookup"><span data-stu-id="01e3e-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="01e3e-106">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01e3e-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="01e3e-107">Exécutez l’applet de cmdlet Set-CsPstnGateway et modifiez le champ AlternateBypassId dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="01e3e-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="01e3e-108">Pour modifier l’autre BypassID d’un Trunk</span><span class="sxs-lookup"><span data-stu-id="01e3e-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="01e3e-109">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01e3e-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="01e3e-110">Exécutez l’applet de cmdlet Set-CsPstnGateway et modifiez le champ AlternateBypassId dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="01e3e-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

