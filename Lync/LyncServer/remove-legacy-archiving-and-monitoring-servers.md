---
title: Suppression des serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1df5ed76a0e0518120c9772b515b36c5f23bfd89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="edb55-102">Suppression des serveurs d’archivage et de surveillance hérités</span><span class="sxs-lookup"><span data-stu-id="edb55-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edb55-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="edb55-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="edb55-104">Si votre déploiement héritait d’un serveur d’archivage ou d’un serveur de surveillance après la migration vers Lync Server 2013, ces serveurs peuvent être supprimés de l’environnement hérité, à condition que tous les utilisateurs y aient été supprimés.</span><span class="sxs-lookup"><span data-stu-id="edb55-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="edb55-105">Vous pouvez supprimer le serveur d’archivage ou la surveillance du serveur dans n’importe quelle séquence.</span><span class="sxs-lookup"><span data-stu-id="edb55-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="edb55-106">La clé requise est que tous les utilisateurs ont été supprimés de tous les groupes hérités restants.</span><span class="sxs-lookup"><span data-stu-id="edb55-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="edb55-107">Vous pouvez déplacer des utilisateurs de Lync Server 2010 vers Lync Server 2013 en suivant les procédures décrites dans la [phase 4 : déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="edb55-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="edb55-108">Après avoir vérifié que tous les utilisateurs ont été supprimés de tous les pools restants, suivez la procédure décrite dans la section « désinstallation de Microsoft Lync Server 2010 et suppression des rôles [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)de serveur » qui peut être téléchargée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="edb55-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

