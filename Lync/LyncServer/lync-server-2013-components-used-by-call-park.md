---
title: 'Lync Server 2013 : composants utilisés par le parcage d’appel'
description: 'Lync Server 2013 : composants utilisés par le parcage d’appel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576770"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="e6a7c-103">Composants utilisés par le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a7c-103">Components used by Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6a7c-104">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="e6a7c-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="e6a7c-105">L’application de parcage d’appel est installée automatiquement lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-105">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e6a7c-106">Vous activez le parcage d’appel en configurant la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-106">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="e6a7c-107">Les composants Lync Server 2013 suivants prennent en charge l’application de parcage d’appel :</span><span class="sxs-lookup"><span data-stu-id="e6a7c-107">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="e6a7c-108">**Service**     d’application Application service fournit une plateforme permettant de déployer, d’héberger et de gérer des applications de communications unifiées, telles que l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="e6a7c-109">Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-109">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="e6a7c-110">Application de parcage d' **appel**     L’application de parcage d’appel est l’une des applications de communications unifiées hébergées par le service d’application.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-110">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="e6a7c-111">Il est inclus automatiquement lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-111">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e6a7c-112">Appeler des parcs de parcage et récupère les appels et gère les orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-112">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="e6a7c-113">Fichier de blocage **sur la musique**     Si la musique est activée, le fichier de musique est lu pendant le parcage d’un appel.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-113">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="e6a7c-114">Un fichier de musique par défaut est inclus lors de l’installation de l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-114">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="e6a7c-115">**Magasin**     de fichiers L’application de parcage d’appel utilise le magasin de fichiers pour contenir des fichiers audio personnalisés.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-115">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="e6a7c-116">**Panneau de configuration**     Lync Server Vous pouvez utiliser le panneau de configuration Lync Server pour configurer la table d’orbites de parcage d’appel et activer le parcage d’appel pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="e6a7c-117">**Lync Server Management Shell**     Toute la configuration de l’application parcage d’appel peut être effectuée à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e6a7c-117">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

