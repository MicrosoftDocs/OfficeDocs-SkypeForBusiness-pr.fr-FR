---
title: 'Publier la topologie : page Sélectionner un CMS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Vous publiez la topologie que vous avez configurée à l’aide du générateur de topologie. Vous êtes invité à effectuer une sélection dans une liste avec le serveur frontal ou le pool frontal qui assumera le rôle de conservation du magasin central de gestion. Un seul serveur frontal ou pool frontal ne peut accueillir ce rôle qu’à un moment donné.
ms.openlocfilehash: e56597a1380f908c7abdb49b9b88edd7ad249870
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277880"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="9c0ec-105">Publier la topologie : page Sélectionner un CMS</span><span class="sxs-lookup"><span data-stu-id="9c0ec-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="9c0ec-106">Vous publiez la topologie que vous avez configurée à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="9c0ec-107">Vous êtes invité à effectuer une sélection dans une liste avec le serveur frontal ou le pool frontal qui assumera le rôle de conservation du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="9c0ec-108">Un seul serveur frontal ou pool frontal ne peut accueillir ce rôle qu’à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="9c0ec-109">À propos du serveur de gestion central</span><span class="sxs-lookup"><span data-stu-id="9c0ec-109">About the Central Management Server</span></span>
<span data-ttu-id="9c0ec-110">Le serveur de gestion central est un système de réplication maître/multiple unique, où la copie en lecture/écriture de la base de données est stockée par le serveur frontal qui contient le serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="9c0ec-111">Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion central, dispose d’une copie en lecture seule de la base de données centrale de gestion de la base de données SQL Server (nommée RTCLOCAL par défaut) installée sur l’ordinateur lors de l’installation et développement.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="9c0ec-112">La base de données locale reçoit les mises à jour de réplica par le biais de l’agent réplicateur de réplicas de Lync Server exécuté en tant que service sur tous les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="9c0ec-113">Le nom de la base de données réelle du serveur de gestion central et du réplica local est XDS, qui est constitué des fichiers XDS. mdf et XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="9c0ec-114">L’emplacement de la base de données maître est référencé par un point de contrôle de service (SCP) dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="9c0ec-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="9c0ec-115">Tous les outils qui utilisent le serveur de gestion central pour gérer et configurer Lync Server utilisent le SCP pour trouver le magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="9c0ec-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c0ec-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c0ec-116">See also</span></span>

[<span data-ttu-id="9c0ec-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="9c0ec-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
