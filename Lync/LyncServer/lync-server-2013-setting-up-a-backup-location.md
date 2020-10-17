---
title: 'Lync Server 2013 : configuration d’un emplacement de sauvegarde'
description: 'Lync Server 2013 : configuration d’un emplacement de sauvegarde.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344baea1b7e51454bb28d31d88451d29fd6aa3a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550450"
---
# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="2546d-103">Configuration d’un emplacement de sauvegarde pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2546d-103">Setting up a backup location for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2546d-104">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="2546d-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="2546d-105">Avant d’effectuer votre première sauvegarde de Lync Server, configurez le matériel et les logiciels dont vous avez besoin afin de stocker et de maintenir les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="2546d-105">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="2546d-106">Vous devez avoir accès aux supports et aux contenus, selon le cas, et fournir une connectivité réseau entre chaque serveur à sauvegarder et les supports de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2546d-106">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="2546d-107">Le média et l’emplacement que vous utilisez doivent être définis dans votre stratégie de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="2546d-107">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="2546d-108">L’emplacement que vous utilisez pour les sauvegardes régulières peut être local ou distant, mais il doit être sécurisé, et doit être accessible à la fois pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="2546d-108">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="2546d-109">Nous vous recommandons d’utiliser un emplacement distant pour vous protéger contre un événement catastrophique sur votre site principal.</span><span class="sxs-lookup"><span data-stu-id="2546d-109">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="2546d-110">Une fois que vous avez installé et testé les composants individuels, vérifiez l’accessibilité des sauvegardes à partir de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="2546d-110">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

