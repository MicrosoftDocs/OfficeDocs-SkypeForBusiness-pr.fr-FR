---
title: 'Lync Server 2013 : Configuration de la table d’orbites de parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="6366d-102">Configuration de la table d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6366d-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6366d-103">_**Dernière modification de la rubrique:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="6366d-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="6366d-104">Le parc d’appels utilise des orbites pour les appels en stationnement.</span><span class="sxs-lookup"><span data-stu-id="6366d-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="6366d-105">Pour que les utilisateurs puissent parcer et récupérer des appels, vous devez configurer la table d’orbite du parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="6366d-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="6366d-106">Vous devez spécifier les plages de numéros d’extension (orbites) que votre organisation va réserver pour les appels de parking et définir le routage de ces plages en spécifiant le pool de parc d’appels qui gère chaque plage.</span><span class="sxs-lookup"><span data-stu-id="6366d-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="6366d-107">Lorsque vous définissez des plages d’orbites, l’objectif est de disposer de suffisamment d’orbites pour ne pas avoir à réutiliser trop rapidement une orbite, mais sans que leur nombre soit trop élevé afin de pouvoir limiter le nombre de postes disponibles pour les utilisateurs ou d’autres services.</span><span class="sxs-lookup"><span data-stu-id="6366d-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="6366d-108">Vous pouvez créer plusieurs plages d’orbite de parking pour chaque pool de serveurs Lync dans lequel l’application de parc d’appels est déployée.</span><span class="sxs-lookup"><span data-stu-id="6366d-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="6366d-109">Chaque gamme de parking d’appel doit avoir un nom globalement unique et un ensemble unique d’extensions.</span><span class="sxs-lookup"><span data-stu-id="6366d-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6366d-p102">Une plage d’orbites comprend généralement au moins 100 orbites. Chaque plage peut être plus importante à condition qu’elle contienne moins de 10 000 orbites et que chaque pool comporte moins de 50 000 orbites. Si une plage est trop petite, les orbites sont réutilisées plus rapidement.</span><span class="sxs-lookup"><span data-stu-id="6366d-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="6366d-113">Utilisez des blocs de postes virtuels (postes attribués à aucun utilisateur ni téléphone) pour vos plages d’orbites.</span><span class="sxs-lookup"><span data-stu-id="6366d-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6366d-114">L’attribution de numéros de numérotation directe à l’intérieur de la table du parking d’appel n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="6366d-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6366d-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6366d-115">In This Section</span></span>

[<span data-ttu-id="6366d-116">Créer ou modifier une gamme de parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6366d-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

