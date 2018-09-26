---
title: Supprimer l’archivage hérité et les serveurs de surveillance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si votre déploiement hérité contenue un serveur d’archivage ou un serveur de surveillance, après la migration vers Skype pour Business Server 2019, ces serveurs peuvent être retirées l’ancien environnement autant de tous les utilisateurs ont été supprimés des pools restants hérité. Vous pouvez supprimer le serveur d’archivage ou un serveur de surveillance dans n’importe quel ordre. L’essentiel est que tous les utilisateurs ont été supprimés des pools restants hérité.
ms.openlocfilehash: 4de6d9db5538864646f978e9fc33a79b39d4c2a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028613"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="e0ce7-105">Supprimer l’archivage hérité et les serveurs de surveillance</span><span class="sxs-lookup"><span data-stu-id="e0ce7-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="e0ce7-106">Si votre déploiement hérité contenue un serveur d’archivage ou un serveur de surveillance, après la migration vers Skype pour Business Server 2019, ces serveurs peut être supprimé de l’environnement hérité, que tous les utilisateurs ont été supprimés des pools restants hérité.</span><span class="sxs-lookup"><span data-stu-id="e0ce7-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="e0ce7-107">Vous pouvez supprimer le serveur d’archivage ou un serveur de surveillance dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="e0ce7-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="e0ce7-108">L’essentiel est que tous les utilisateurs ont été supprimés des pools restants hérité.</span><span class="sxs-lookup"><span data-stu-id="e0ce7-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="e0ce7-109">Vous pouvez déplacer des utilisateurs à Skype pour Business Server 2019 en suivant les procédures décrites dans [Phase 4 : test de déplacer les utilisateurs vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e0ce7-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="e0ce7-110">Après avoir vérifié que tous les utilisateurs ont été supprimés des pools restants, le serveur de désactivation et supprimer des rôles.</span><span class="sxs-lookup"><span data-stu-id="e0ce7-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="e0ce7-111">Une date, mais pertinents, exemple est « Désinstallation de Microsoft Lync Server et suppression de rôles de serveur, » qui peut être téléchargé à [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="e0ce7-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

