---
title: 'Lync Server 2013 : analyse antivirus et vérification des définitions de virus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bc6704329dbc124bb61f779bf773a1f55bd72d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="55247-102">Recherche de virus et vérification des définitions de virus dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55247-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55247-103">_**Dernière modification de la rubrique :** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="55247-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="55247-104">Nous vous recommandons vivement d’installer un produit antivirus de niveau messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="55247-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="55247-105">La messagerie instantanée est une source connue pour diffuser rapidement les virus et les logiciels malveillants au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="55247-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="55247-106">Microsoft Forefront® Security for Lync Server fournit une analyse multimoteur avec des virus, des logiciels malveillants, une protection contre le filtrage des fichiers et des mots clés et une intégration transparente avec Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="55247-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="55247-107">En plus de Forefront Security pour Lync Server, nous vous recommandons également d’installer une solution antivirus au niveau du fichier pour protéger le système de fichiers du serveur.</span><span class="sxs-lookup"><span data-stu-id="55247-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="55247-108">La mise à jour des moteurs de scanneurs et des définitions de virus est très importante.</span><span class="sxs-lookup"><span data-stu-id="55247-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="55247-109">La configuration et la surveillance de l’intégrité des mises à jour permettent de s’assurer que les informations d’analyse les plus récentes sont utilisées pour protéger à la fois Office Communications Server et le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="55247-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55247-110">Lors de l’utilisation d’un logiciel antivirus de niveau fichier tiers sur un serveur qui exécute Lync Server 2013 et Forefront Security pour Lync Server, assurez-vous que les dossiers dans lesquels Forefront Security pour Lync Server et Lync Server sont installés ne sont pas analysés, afin d’empêcher leur corruption.</span><span class="sxs-lookup"><span data-stu-id="55247-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="55247-111">Pour obtenir la liste complète des exclusions, <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="55247-111">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

