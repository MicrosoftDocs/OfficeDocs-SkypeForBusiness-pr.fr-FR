---
title: Suppression des serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4f149db04be75cec961478f4382b3e7a333e0a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="cacce-102">Suppression des serveurs d’archivage et de surveillance hérités</span><span class="sxs-lookup"><span data-stu-id="cacce-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cacce-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="cacce-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="cacce-104">Si votre déploiement Office Communications Server 2007 R2 contenait un serveur d’archivage ou un serveur de surveillance, après la migration vers Lync Server 2013, ces serveurs peuvent être supprimés de l’environnement hérité, sous réserve que tous les utilisateurs aient été supprimés des pools Office Communications Server 2007 R2 restants.</span><span class="sxs-lookup"><span data-stu-id="cacce-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="cacce-105">Vous pouvez supprimer le serveur d’archivage ou le serveur de surveillance dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="cacce-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="cacce-106">La condition essentielle est que tous les utilisateurs ont été supprimés des pools Office Communications Server 2007 R2 restants.</span><span class="sxs-lookup"><span data-stu-id="cacce-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="cacce-107">Vous pouvez déplacer des utilisateurs d’Office Communications Server 2007 R2 vers Lync Server 2013 en suivant les procédures décrites à [la phase 6 : déplacer des utilisateurs vers le pool pilote](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="cacce-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="cacce-108">Une fois que vous avez confirmé que tous les utilisateurs ont été supprimés des pools restants, suivez la procédure décrite dans la section « suppression des serveurs et des rôles serveur » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887) .</span><span class="sxs-lookup"><span data-stu-id="cacce-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

