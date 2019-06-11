---
title: Scénario de migration standard - Haut niveau
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="a0a6b-102">Scénario de migration standard - Haut niveau</span><span class="sxs-lookup"><span data-stu-id="a0a6b-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0a6b-103">_**Dernière modification de la rubrique:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a0a6b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a0a6b-104">Utilisez les éléments suivants comme point de départ lors de la migration de Lync Server 2010, d’une conversation de groupe ou d’une conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="a0a6b-105">Le chemin de migration standard de Lync Server 2013 est le suivant:</span><span class="sxs-lookup"><span data-stu-id="a0a6b-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="a0a6b-106">Votre organisation a déjà déployé Lync Server 2010, les discussions de groupe ou les discussions de groupe Office Communications Server 2007 R2 et vous voulez déployer Lync Server 2013, serveur de conversation permanent.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="a0a6b-107">Déploiement de Lync Server 2013, puis déploiement du ou des pools de serveurs de chat permanents.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="a0a6b-108">Préparez et planifiez la migration de vos salles de conversation permanente et déterminez un moment approprié pour arrêter le système à des fins de migration.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="a0a6b-109">Exécutez les cmdlets Windows PowerShell pour la migration (**Export-CsPersistentChatData** et **Import-CsPersistentChatData**) pour déplacer le contenu vers le serveur de conversation persistante.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="a0a6b-110">Vérifiez que la migration a réussi.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="a0a6b-111">Désaffectez votre déploiement hérité.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="a0a6b-112">Configurez le serveur de chat permanent de sorte que les clients hérités puissent se connecter à Lync Server 2013, serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="a0a6b-113">Cela est nécessaire, car cela prend du temps pour le déploiement de nouveaux clients, et vous voulez permettre aux utilisateurs existants d’avoir accès à leurs salles de conversation le plus rapidement possible.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="a0a6b-114">Déployez de nouveaux clients tout en continuant de garantir que les travailleurs disposant d’une discussion de groupe héritée (clients) pourront accéder à leurs salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="a0a6b-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

