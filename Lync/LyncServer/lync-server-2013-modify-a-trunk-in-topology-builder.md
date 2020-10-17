---
title: 'Lync Server 2013 : modifier une jonction dans le générateur de topologies'
description: 'Lync Server 2013 : modifier une jonction dans le générateur de topologies.'
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
ms.openlocfilehash: 5f453997664dbe3048a7aa915732b4d95a932dd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550480"
---
# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="c2084-103">Modifier une jonction dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2084-103">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2084-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c2084-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c2084-105">Suivez ces étapes pour modifier l’adresse IP média de remplacement et l’identificateur de contournement de remplacement d’une jonction.</span><span class="sxs-lookup"><span data-stu-id="c2084-105">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="c2084-106">Pour modifier l’adresse IP média de remplacement d’une jonction</span><span class="sxs-lookup"><span data-stu-id="c2084-106">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="c2084-107">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c2084-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c2084-108">Exécutez l’applet de commande Set-CsPstnGateway et modifiez le champ AlternateBypassId dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c2084-108">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="c2084-109">Pour modifier le BypassID de remplacement d’une jonction</span><span class="sxs-lookup"><span data-stu-id="c2084-109">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="c2084-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c2084-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c2084-111">Exécutez l’applet de commande Set-CsPstnGateway et modifiez le champ AlternateBypassId dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c2084-111">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

