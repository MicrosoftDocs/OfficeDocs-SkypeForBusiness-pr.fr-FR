---
title: Suppression des serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si votre déploiement héritait d’un serveur d’archivage ou d’un serveur de surveillance après la migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, à condition que tous les utilisateurs aient été supprimés de tous les pools hérités. Vous pouvez supprimer le serveur d’archivage ou la surveillance du serveur dans n’importe quelle séquence. La clé requise est que tous les utilisateurs ont été supprimés de tous les groupes hérités restants.
ms.openlocfilehash: 918e04bb42853f0203ae8a2a56db5e640985af99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301124"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="9a1a7-105">Suppression des serveurs d’archivage et de surveillance hérités</span><span class="sxs-lookup"><span data-stu-id="9a1a7-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="9a1a7-106">Si votre déploiement héritait d’un serveur d’archivage ou d’un serveur de surveillance après la migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, à condition que tous les utilisateurs aient été supprimés de tous les pools hérités.</span><span class="sxs-lookup"><span data-stu-id="9a1a7-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="9a1a7-107">Vous pouvez supprimer le serveur d’archivage ou la surveillance du serveur dans n’importe quelle séquence.</span><span class="sxs-lookup"><span data-stu-id="9a1a7-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="9a1a7-108">La clé requise est que tous les utilisateurs ont été supprimés de tous les groupes hérités restants.</span><span class="sxs-lookup"><span data-stu-id="9a1a7-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="9a1a7-109">Vous pouvez déplacer des utilisateurs vers Skype entreprise Server 2019 en suivant les procédures décrites dans la [phase 4: déplacer les utilisateurs de test vers le pool de pilotes](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="9a1a7-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="9a1a7-110">Après avoir vérifié que tous les utilisateurs ont été supprimés de tous les pools restants, decommision le serveur et supprimez les rôles.</span><span class="sxs-lookup"><span data-stu-id="9a1a7-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="9a1a7-111">Un exemple de date, mais pertinent, est «la désinstallation de Microsoft Lync Server et la suppression des rôles de serveur», [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)qui peut être téléchargé à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="9a1a7-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

