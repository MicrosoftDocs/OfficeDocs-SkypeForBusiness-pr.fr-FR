---
title: 'Lync Server 2013: configuration d’un emplacement de sauvegarde'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6d8f91af650e68348a35e9f485f5ca5f54093fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="436b4-102">Configuration d’un emplacement de sauvegarde pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436b4-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="436b4-103">_**Dernière modification de la rubrique:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="436b4-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="436b4-104">Avant de procéder à la première sauvegarde de Lync Server, configurez le matériel et le logiciel dont vous avez besoin afin de stocker et de tenir à jour les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="436b4-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="436b4-105">Vous devez obtenir l’accès au contenu multimédia et au contenu, le cas échéant, et fournir une connectivité réseau entre chaque serveur à sauvegarder et le média de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="436b4-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="436b4-106">Le média et l’emplacement que vous utilisez doivent être définis dans votre stratégie de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="436b4-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="436b4-107">L’emplacement que vous utilisez pour les sauvegardes régulières peut être local ou distant, mais il doit être accessible pour la sauvegarde et la restauration.</span><span class="sxs-lookup"><span data-stu-id="436b4-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="436b4-108">Nous vous recommandons d’utiliser un lieu distant pour vous protéger contre un événement catastrophique sur votre site principal.</span><span class="sxs-lookup"><span data-stu-id="436b4-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="436b4-109">Après avoir configuré et testé les composants individuels, vérifiez l’accessibilité des sauvegardes sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="436b4-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

