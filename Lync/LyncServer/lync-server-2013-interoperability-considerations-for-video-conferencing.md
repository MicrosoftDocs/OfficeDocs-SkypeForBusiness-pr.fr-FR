---
title: 'Lync Server 2013 : considérations relatives à l’interopérabilité pour la conférence vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 885768cc461b7b59c37cf83b0b422bfca6c950a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="a9756-102">Considérations relatives à l’interopérabilité pour la conférence vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9756-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9756-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a9756-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a9756-104">Cette section décrit l’expérience utilisateur pendant la phase de coexistence de la migration, lorsqu’il existe une interopérabilité entre les clients hérités et un pool Lync Server 2013 ou Lync Server 2013 et un pool hérité.</span><span class="sxs-lookup"><span data-stu-id="a9756-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="a9756-105">Pools Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9756-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="a9756-106">Les utilisateurs subissent les comportements suivants lorsqu’un client hérité est utilisé dans un pool Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="a9756-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="a9756-107">Pour les appels à deux, la résolution vidéo est la même que dans le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="a9756-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="a9756-p101">Pour les conférences à plusieurs, la résolution vidéo et les fonctionnalités de vidéoconférence sont les mêmes que celles du pool hérité. La vue Galerie et la haute résolution ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="a9756-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="a9756-110">Pools hérités</span><span class="sxs-lookup"><span data-stu-id="a9756-110">Legacy Pools</span></span>

<span data-ttu-id="a9756-111">Les utilisateurs subissent le comportement suivant lorsqu’un client Lync Server 2013 est utilisé dans un pool hérité :</span><span class="sxs-lookup"><span data-stu-id="a9756-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="a9756-112">Pour les appels à deux, les clients Lync Server 2013 peuvent utiliser les nouvelles fonctionnalités comme suit :</span><span class="sxs-lookup"><span data-stu-id="a9756-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="a9756-113">H. 264 est disponible si les deux participants utilisent les clients Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9756-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="a9756-114">Le client Lync Server 2013 utilise la valeur par défaut pour TotalReceiveVideoBitRateKb, car le serveur hérité n’envoie pas ces informations avec la mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="a9756-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="a9756-115">Pour les conférences à plusieurs, la résolution vidéo et les fonctionnalités de vidéoconférence sont les mêmes que celles d’un client hérité dans le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="a9756-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9756-116">Lorsqu’un serveur hérité héberge un client Lync Server 2013, il est possible de configurer la bande passante de la vidéoconférence de sorte que tous les utilisateurs du pool reçoivent uniquement la vidéo basse résolution, mais envoient une vidéo haute résolution.</span><span class="sxs-lookup"><span data-stu-id="a9756-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="a9756-117">Par exemple, lorsque MaxVideoRateAllowed est défini sur CAF-250K dans la configuration des médias et que VideoBitRateKb est défini sur 2000 kbits/s dans la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="a9756-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="a9756-118">Dans ce cas, l’effet net est que la résolution élevée n’est pas possible pour les utilisateurs du pool.</span><span class="sxs-lookup"><span data-stu-id="a9756-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="a9756-119">Comme MaxVideoRateAllowed n’est plus utilisé pour les clients Lync Server 2013, il ne peut pas empêcher les clients Lync Server 2013 de demander une vidéo à haute résolution.</span><span class="sxs-lookup"><span data-stu-id="a9756-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="a9756-120">En revanche, vous pouvez affecter pour tous les utilisateurs du pool la même valeur à VideoBitRateKb et à MaxVideoRateAllowed (c’est-à-dire, CIF est défini sur 250 Kbits/s ou VGA est défini sur 600 Kbits/s ou HD est défini sur 1 500 Kbits/s).</span><span class="sxs-lookup"><span data-stu-id="a9756-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

