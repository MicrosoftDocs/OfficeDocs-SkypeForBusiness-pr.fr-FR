---
title: Suppression des serveurs d’archivage et de surveillance hérités
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si votre déploiement hérité contenait un serveur d’archivage ou un serveur de surveillance, après avoir effectué une migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, sous réserve que tous les utilisateurs aient été supprimés des autres pools hérités. Vous pouvez supprimer le serveur d’archivage ou le serveur de surveillance dans n’importe quel ordre. La principale condition est que tous les utilisateurs aient été supprimés de tous les pools hérités restants.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752166"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="bf235-105">Suppression des serveurs d’archivage et de surveillance hérités</span><span class="sxs-lookup"><span data-stu-id="bf235-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="bf235-106">Si votre déploiement hérité contient un serveur d’archivage ou un serveur de surveillance, après la migration vers Skype entreprise Server 2019, ces serveurs peuvent être supprimés de l’environnement hérité, à condition que tous les utilisateurs aient été supprimés de tous les autres pools hérités.</span><span class="sxs-lookup"><span data-stu-id="bf235-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="bf235-107">Vous pouvez supprimer le serveur d’archivage ou le serveur de surveillance dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="bf235-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="bf235-108">La principale condition est que tous les utilisateurs aient été supprimés de tous les pools hérités restants.</span><span class="sxs-lookup"><span data-stu-id="bf235-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="bf235-109">Vous pouvez déplacer des utilisateurs vers Skype entreprise Server 2019 en suivant les procédures décrites dans la [phase 4 : déplacer les utilisateurs test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="bf235-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="bf235-110">Une fois que vous avez vérifié que tous les utilisateurs ont été supprimés de tous les pools restants, decommision le serveur et supprimez les rôles.</span><span class="sxs-lookup"><span data-stu-id="bf235-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="bf235-111">Un exemple daté, mais pertinent, est le suivant : « désinstallation de Microsoft Lync Server et suppression des rôles serveur », qui peut être téléchargé à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .</span><span class="sxs-lookup"><span data-stu-id="bf235-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

