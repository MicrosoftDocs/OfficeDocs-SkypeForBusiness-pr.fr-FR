---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="87f0e-102">Migration des téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="87f0e-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87f0e-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="87f0e-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="87f0e-104">Les téléphones portables courants sont les téléphones IP qui se trouvent le plus souvent dans un espace de travail partagé ou une zone commune (par exemple, salle d’attente, cuisine ou étage d’usine).</span><span class="sxs-lookup"><span data-stu-id="87f0e-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="87f0e-105">Il n’est pas nécessaire de connecter des téléphones communs à un ordinateur pour fournir une fonctionnalité de communications unifiées Lync Server.</span><span class="sxs-lookup"><span data-stu-id="87f0e-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="87f0e-106">Après avoir migré un déploiement de Lync Server 2010 vers Lync Server 2013, vous devez également migrer les objets de contact associés au téléphone de zone commune hérité.</span><span class="sxs-lookup"><span data-stu-id="87f0e-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="87f0e-107">À l’aide de Lync Server Management Shell, vous devez d’abord récupérer tous les objets de contact associés aux téléphones de zone commune de Lync Server 2010, puis déplacer ces objets vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87f0e-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="87f0e-108">**Migration des téléphones de partie commune**</span><span class="sxs-lookup"><span data-stu-id="87f0e-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="87f0e-109">À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="87f0e-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="87f0e-110">À partir de la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="87f0e-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="87f0e-111">Pour vérifier que tous les objets de contact ont été déplacés vers le pool Lync Server 2013, à partir de Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="87f0e-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="87f0e-112">Vérifiez que tous les objets de contact sont désormais associés au pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87f0e-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

