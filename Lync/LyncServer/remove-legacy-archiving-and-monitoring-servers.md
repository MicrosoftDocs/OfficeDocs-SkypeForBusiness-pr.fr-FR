---
title: Suppression des serveurs d’archivage et de surveillance hérités
description: Supprimez les serveurs d’archivage et de surveillance hérités.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0155fb18e298d2538e3bad8dc4a5626bb1ce01d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545920"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="2b30f-103">Suppression des serveurs d’archivage et de surveillance hérités</span><span class="sxs-lookup"><span data-stu-id="2b30f-103">Remove legacy Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b30f-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2b30f-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2b30f-105">Si votre déploiement hérité contient un serveur d’archivage ou un serveur de surveillance, après la migration vers Lync Server 2013, ces serveurs peuvent être supprimés de l’environnement hérité, sous réserve que tous les utilisateurs aient été supprimés des pools hérités restants.</span><span class="sxs-lookup"><span data-stu-id="2b30f-105">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="2b30f-106">Vous pouvez supprimer le serveur d’archivage ou le serveur de surveillance dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="2b30f-106">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="2b30f-107">La principale condition est que tous les utilisateurs aient été supprimés de tous les pools hérités restants.</span><span class="sxs-lookup"><span data-stu-id="2b30f-107">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="2b30f-108">Vous pouvez déplacer des utilisateurs de Lync Server 2010 vers Lync Server 2013 en suivant les procédures décrites dans la [phase 4 : déplacer les utilisateurs de test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="2b30f-108">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="2b30f-109">Une fois que vous avez confirmé que tous les utilisateurs ont été supprimés des pools restants, suivez la procédure décrite dans la section « désinstallation de Microsoft Lync Server 2010 et suppression des rôles serveur », qui peut être téléchargée à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) .</span><span class="sxs-lookup"><span data-stu-id="2b30f-109">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

