---
title: Vérification de la coexistence du pool pilote avec le pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="08343-102">Vérification de la coexistence du pool pilote avec le pool hérité</span><span class="sxs-lookup"><span data-stu-id="08343-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08343-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="08343-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="08343-104">Après avoir déployé le pool de pilotes, vous devez vérifier la coexistence des deux pools en utilisant les outils d’administration pour afficher les informations sur le pool.</span><span class="sxs-lookup"><span data-stu-id="08343-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="08343-105">Pour les pools Lync Server 2013 et les pools hérités, vous devez utiliser les outils de panneau de configuration et de générateur de topologie de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08343-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="08343-106">Vérifiez que les services Lync Server 2013 ont démarré</span><span class="sxs-lookup"><span data-stu-id="08343-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="08343-107">À partir du serveur frontal Lync Server 2013, accédez à l’applet\\services d’administration.</span><span class="sxs-lookup"><span data-stu-id="08343-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="08343-108">Vérifiez que les services suivants s’exécutent sur le serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="08343-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="08343-109">**Services Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="08343-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="08343-110">![Liste des services serveur Lync démarrés](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Liste des services serveur Lync démarrés")</span><span class="sxs-lookup"><span data-stu-id="08343-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="08343-111">Ouvrir le panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08343-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="08343-112">Sur le serveur frontal de votre déploiement Lync Server 2013, ouvrez le panneau de configuration de Lync Server 2013 et sélectionnez le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="08343-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="08343-113">Répétez cette procédure pour ouvrir le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08343-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="08343-114">**Ouvrir le panneau de configuration de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="08343-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="08343-115">![Boîte de dialogue Sélectionner une URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Boîte de dialogue Sélectionner une URL")</span><span class="sxs-lookup"><span data-stu-id="08343-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="08343-116">Sur Lync Server 2013, vous devez mettre à niveau Silverlight vers Silverlight version 5 avant d’utiliser le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08343-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="08343-117">Cette topologie inclut désormais les rôles serveur Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08343-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="08343-118">**Page Topology du panneau de configuration de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="08343-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="08343-119">![Panneau de configuration de Lync Server-page Topology](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Panneau de configuration de Lync Server-page Topology")</span><span class="sxs-lookup"><span data-stu-id="08343-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="08343-120">Ne pas essayer d’ouvrir la topologie dans Lync Server 2010-générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="08343-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="08343-121">Si vous essayez d’ouvrir la topologie à l’aide du générateur de topologie Lync Server 2010, le message d’erreur ci-dessous s’affiche.</span><span class="sxs-lookup"><span data-stu-id="08343-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="08343-122">Le module topologique peut uniquement être affiché à l’aide du générateur de topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08343-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="08343-123">Le générateur de topologie Lync Server 2013 doit être utilisé pour créer des pools pour Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="08343-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="08343-124">**Message d’erreur du générateur de topologie Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="08343-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="08343-125">![Erreur d’alignement de la console MMC du générateur de topologie Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Erreur d’alignement de la console MMC du générateur de topologie Lync Server")</span><span class="sxs-lookup"><span data-stu-id="08343-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

