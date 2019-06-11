---
title: 'Lync Server 2013: considérations d’interopérabilité pour les conférences vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880b2e41a1ea92b3d6da9cd29153695b474e88f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="83ce1-102">Considérations en matière d’interopérabilité pour les conférences vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83ce1-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83ce1-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="83ce1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="83ce1-104">Cette section décrit l’utilisation de l’application par l’utilisateur lors de la phase de coexistence de la migration, en cas d’interopérabilité entre les clients hérités et un pool Lync Server 2013 ou un serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83ce1-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="83ce1-105">Pools Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83ce1-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="83ce1-106">Les utilisateurs peuvent observer le comportement suivant lorsqu’un client hérité est utilisé dans un pool Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="83ce1-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="83ce1-107">Pour les appels à deux participants, la résolution vidéo est identique à celle du pool hérité.</span><span class="sxs-lookup"><span data-stu-id="83ce1-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="83ce1-108">Dans le cadre de conférences multiparties, les fonctionnalités de résolution vidéo et de visioconférence sont les mêmes que dans le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="83ce1-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="83ce1-109">Le mode Galerie et la haute résolution ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="83ce1-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="83ce1-110">Pools hérités</span><span class="sxs-lookup"><span data-stu-id="83ce1-110">Legacy Pools</span></span>

<span data-ttu-id="83ce1-111">Les utilisateurs peuvent découvrir le comportement suivant lorsqu’un client Lync Server 2013 est utilisé dans un pool hérité:</span><span class="sxs-lookup"><span data-stu-id="83ce1-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="83ce1-112">Pour les appels à deux parties, les clients Lync Server 2013 peuvent utiliser les nouvelles fonctionnalités comme suit:</span><span class="sxs-lookup"><span data-stu-id="83ce1-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="83ce1-113">H. 264 est disponible si les deux participants utilisent les clients Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83ce1-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="83ce1-114">Le client Lync Server 2013 utilise la valeur par défaut pour TotalReceiveVideoBitRateKb, car le serveur hérité n’envoie pas ces informations avec la mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="83ce1-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="83ce1-115">Dans le cadre de conférences multipièces, les fonctionnalités de résolution vidéo et de visioconférence sont les mêmes que celles d’un client hérité dans le pool hérité.</span><span class="sxs-lookup"><span data-stu-id="83ce1-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83ce1-116">Lorsqu’un serveur hérité héberge un client Lync Server 2013, il est possible de configurer une bande passante de conférence vidéo de sorte que tous les utilisateurs du pool reçoivent uniquement de la vidéo basse résolution, mais qu’ils envoient une vidéo haute résolution.</span><span class="sxs-lookup"><span data-stu-id="83ce1-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="83ce1-117">C’est le cas, par exemple, lorsque MaxVideoRateAllowed est défini sur CAF-250K dans la configuration multimédia et VideoBitRateKb est défini sur 2000 KB/s dans la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="83ce1-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="83ce1-118">Dans cette situation, l’effet net n’est pas possible pour les utilisateurs du pool.</span><span class="sxs-lookup"><span data-stu-id="83ce1-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="83ce1-119">Étant donné que MaxVideoRateAllowed n’est plus utilisé pour les clients Lync Server 2013, il n’est pas possible d’empêcher les clients Lync Server 2013 de demander une vidéo haute résolution.</span><span class="sxs-lookup"><span data-stu-id="83ce1-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="83ce1-120">Au lieu de cela, définissez VideoBitRateKb dans la stratégie de conférence pour que tous les utilisateurs du pool aient la même valeur que MaxVideoRateAllowed (c’est-à-dire que la valeur CAF est définie sur 250 kb/s, 600 ou la valeur HD est définie sur 1500 kb/s).</span><span class="sxs-lookup"><span data-stu-id="83ce1-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

