---
title: Supprimer les serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a6f24cd2cc176679f628bc54460a6c3c7a718
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="f6f96-102">Supprimer les serveurs d’archivage et de surveillance hérités</span><span class="sxs-lookup"><span data-stu-id="f6f96-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6f96-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="f6f96-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="f6f96-104">Si votre déploiement Office Communications Server 2007 R2 contenait un serveur d’archivage ou un serveur de surveillance, après la migration vers Lync Server 2013, ces serveurs peuvent être supprimés de l’environnement hérité, étant donné que tous les utilisateurs ont été supprimés des autres Pools Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f6f96-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="f6f96-105">Vous pouvez supprimer le serveur d’archivage ou le serveur de surveillance dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="f6f96-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="f6f96-106">La condition essentielle est que tous les utilisateurs ont été supprimés des pools Office Communications Server 2007 R2 restants.</span><span class="sxs-lookup"><span data-stu-id="f6f96-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="f6f96-107">Vous pouvez déplacer des utilisateurs d’Office Communications Server 2007 R2 vers Lync Server 2013 en suivant les procédures décrites à [la phase 6 : déplacer des utilisateurs vers le pool pilote](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f6f96-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="f6f96-108">Une fois que vous avez confirmé que tous les utilisateurs ont été supprimés des pools restants, suivez la procédure décrite dans la section [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)« suppression des serveurs et des rôles serveur » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f6f96-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

