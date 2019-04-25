---
title: Suppression des serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si votre déploiement hérité contenue un serveur d’archivage ou un serveur de surveillance, après la migration vers Skype pour Business Server 2019, ces serveurs peuvent être retirées l’ancien environnement autant de tous les utilisateurs ont été supprimés des pools restants hérité. Vous pouvez supprimer le serveur d’archivage ou un serveur de surveillance dans n’importe quel ordre. L’essentiel est que tous les utilisateurs ont été supprimés des pools restants hérité.
ms.openlocfilehash: 5a3a691c8f2e8a4ad3610ccf1ea947ce23b74111
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231422"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="bf74c-105">Suppression des serveurs d’archivage et de surveillance hérités</span><span class="sxs-lookup"><span data-stu-id="bf74c-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="bf74c-106">Si votre déploiement hérité contenue un serveur d’archivage ou un serveur de surveillance, après la migration vers Skype pour Business Server 2019, ces serveurs peut être supprimé de l’environnement hérité, que tous les utilisateurs ont été supprimés des pools restants hérité.</span><span class="sxs-lookup"><span data-stu-id="bf74c-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="bf74c-107">Vous pouvez supprimer le serveur d’archivage ou un serveur de surveillance dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="bf74c-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="bf74c-108">L’essentiel est que tous les utilisateurs ont été supprimés des pools restants hérité.</span><span class="sxs-lookup"><span data-stu-id="bf74c-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="bf74c-109">Vous pouvez déplacer des utilisateurs à Skype pour Business Server 2019 en suivant les procédures décrites dans [Phase 4 : test de déplacer les utilisateurs vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="bf74c-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="bf74c-110">Après avoir vérifié que tous les utilisateurs ont été supprimés des pools restants, le serveur de désactivation et supprimer des rôles.</span><span class="sxs-lookup"><span data-stu-id="bf74c-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="bf74c-111">Une date, mais pertinents, exemple est « Désinstallation de Microsoft Lync Server et suppression de rôles de serveur, » qui peut être téléchargé à [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="bf74c-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

