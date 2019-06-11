---
title: 'Lync Server 2013: recherche de virus et vérification des signatures de virus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 357c2c2053aca6b7b18a966756ece2768a8e71c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="ef138-102">Recherche de virus et vérification des définitions de virus dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef138-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef138-103">_**Dernière modification de la rubrique:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="ef138-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="ef138-104">Nous vous recommandons vivement d’installer un produit antivirus de niveau message instantané.</span><span class="sxs-lookup"><span data-stu-id="ef138-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="ef138-105">Le message instantané est une source connue pour la propagation rapide des virus et des logiciels malveillants au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="ef138-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="ef138-106">Microsoft Forefront® Security pour Lync Server fournit une analyse multimoteur avec un virus, un logiciel malveillant, une protection de filtre par fichier et mot clé ainsi qu’une intégration transparente avec Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="ef138-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="ef138-107">En plus de Forefront Security pour Lync Server, nous vous conseillons vivement d’installer une solution antivirus de niveau fichier pour protéger le système de fichiers du serveur.</span><span class="sxs-lookup"><span data-stu-id="ef138-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="ef138-108">Il est très important de maintenir les moteurs de scanneurs et les définitions de virus mis à jour.</span><span class="sxs-lookup"><span data-stu-id="ef138-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="ef138-109">La configuration et la surveillance de l’état des mises à jour permettent de s’assurer que les informations d’analyse les plus récentes sont utilisées pour protéger les fichiers et le système de fichiers Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="ef138-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ef138-110">Si vous utilisez un logiciel antivirus tiers, sur un serveur qui exécute Lync Server 2013 et Forefront Security pour Lync Server, assurez-vous que les dossiers dans lesquels Forefront Security pour Lync Server et le serveur Lync sont installés ne sont pas analysés, afin d’éviter leur corruption.</span><span class="sxs-lookup"><span data-stu-id="ef138-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="ef138-111">Pour obtenir la liste complète des exclusions, <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>reportez-vous à la section.</span><span class="sxs-lookup"><span data-stu-id="ef138-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

