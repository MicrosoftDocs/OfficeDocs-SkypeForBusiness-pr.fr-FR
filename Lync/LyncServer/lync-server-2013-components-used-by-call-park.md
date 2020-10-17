---
title: 'Lync Server 2013 : composants utilisés par le parcage d’appel'
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
ms.openlocfilehash: 21335597f0910e18a5afe36898c7d0eff6c1a338
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502391"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="dc4e4-102">Composants utilisés par le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc4e4-102">Components used by Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc4e4-103">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="dc4e4-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="dc4e4-104">L’application de parcage d’appel est installée automatiquement lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="dc4e4-105">Vous activez le parcage d’appel en configurant la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="dc4e4-106">Les composants Lync Server 2013 suivants prennent en charge l’application de parcage d’appel :</span><span class="sxs-lookup"><span data-stu-id="dc4e4-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="dc4e4-107">**Service**     d’application Application service fournit une plateforme permettant de déployer, d’héberger et de gérer des applications de communications unifiées, telles que l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="dc4e4-108">Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="dc4e4-109">Application de parcage d' **appel**     L’application de parcage d’appel est l’une des applications de communications unifiées hébergées par le service d’application.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="dc4e4-110">Il est inclus automatiquement lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="dc4e4-111">Appeler des parcs de parcage et récupère les appels et gère les orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="dc4e4-112">Fichier de blocage **sur la musique**     Si la musique est activée, le fichier de musique est lu pendant le parcage d’un appel.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="dc4e4-113">Un fichier de musique par défaut est inclus lors de l’installation de l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="dc4e4-114">**Magasin**     de fichiers L’application de parcage d’appel utilise le magasin de fichiers pour contenir des fichiers audio personnalisés.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="dc4e4-115">**Panneau de configuration**     Lync Server Vous pouvez utiliser le panneau de configuration Lync Server pour configurer la table d’orbites de parcage d’appel et activer le parcage d’appel pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="dc4e4-116">**Lync Server Management Shell**     Toute la configuration de l’application parcage d’appel peut être effectuée à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dc4e4-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

