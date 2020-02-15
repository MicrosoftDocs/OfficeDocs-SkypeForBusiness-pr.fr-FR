---
title: 'Lync Server 2013 : planification et déploiement d’une vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3938ca54278f71d8f51ecacfe3fdc3278ec59679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="1aa66-102">Planification et déploiement de la vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa66-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aa66-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1aa66-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1aa66-104">Lync Server 2013 présente les nouvelles fonctionnalités vidéo suivantes :</span><span class="sxs-lookup"><span data-stu-id="1aa66-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="1aa66-105">\*\*\*\*   Les utilisateurs de la vidéo HD peuvent bénéficier de résolutions jusqu’à la haute définition (HD) (1920 x 1080) dans les appels à deux et les conférences à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="1aa66-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="1aa66-106">**Vue**   de la galerie dans les conférences vidéo qui ont plus de deux personnes, les utilisateurs peuvent voir les vidéos des participants à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="1aa66-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="1aa66-107">Si la conférence inclut plus de cinq participants, seule la vidéo des participants les plus actifs apparaît dans la ligne supérieure, tandis qu’une photo apparaît pour les autres participants.</span><span class="sxs-lookup"><span data-stu-id="1aa66-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="1aa66-108">**Vidéo h. 264**   le codec vidéo h. 264 est maintenant la valeur par défaut pour le codage de vidéo sur les clients Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1aa66-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="1aa66-109">La vidéo H.264 prend en charge un éventail supérieur de résolutions et de fréquences d'images, et renforce l'évolutivité de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="1aa66-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1aa66-110">Lync Server 2013 prend toujours en charge le codec VC1 pour l’interopérabilité avec les versions précédentes de Lync.</span><span class="sxs-lookup"><span data-stu-id="1aa66-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="1aa66-111">Pour plus d’informations sur le nouveau codec vidéo, consultez l’article du blog de Jeff Schertz, « interopérabilité vidéo dans Lync 2013 », <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1aa66-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="1aa66-112">Cette section décrit comment gérer la bande passante pour la vidéo dans Lync Server 2013 et comment configurer les fonctionnalités vidéo.</span><span class="sxs-lookup"><span data-stu-id="1aa66-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1aa66-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1aa66-113">In This Section</span></span>

  - [<span data-ttu-id="1aa66-114">Configuration de la bande passante vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa66-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="1aa66-115">Configuration de la vue de la galerie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa66-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="1aa66-116">Configuration d’exemples de scénarios vidéo pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa66-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="1aa66-117">Considérations relatives à l’interopérabilité pour la conférence vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa66-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

