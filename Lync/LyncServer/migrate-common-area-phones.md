---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138068c73264ded3483d8d9f0902d403833a306d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="82777-102">Migration des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="82777-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82777-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="82777-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="82777-104">Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier.</span><span class="sxs-lookup"><span data-stu-id="82777-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="82777-105">Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir la fonctionnalité de communications unifiées Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82777-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="82777-106">Après avoir migré un déploiement Lync Server 2010 vers Lync Server 2013, vous devez également migrer les objets contact associés au téléphone de partie commune hérité.</span><span class="sxs-lookup"><span data-stu-id="82777-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="82777-107">À l’aide de Lync Server Management Shell, vous devez tout d’abord récupérer tous les objets contact associés aux téléphones de zone commune Lync Server 2010, puis déplacer ces objets vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82777-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="82777-108">**Migration des téléphones de partie commune**</span><span class="sxs-lookup"><span data-stu-id="82777-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="82777-109">À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="82777-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="82777-110">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="82777-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="82777-111">Pour vérifier que tous les objets contact ont été déplacés vers le pool Lync Server 2013, dans Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="82777-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="82777-112">Vérifiez que tous les objets contact sont maintenant associés au pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82777-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

