---
title: 'Publier la topologie : page Sélectionner un CMS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Vous publiez la topologie que vous avez configurées à l’aide du Générateur de topologie. Vous êtes invité à sélectionner à partir d’une liste pool frontal ou serveur frontal assumeront le rôle de contenir le magasin Central de gestion. Qu’un seul pool frontal ou serveur frontal peut contenir ce rôle à un moment donné.
ms.openlocfilehash: e649629650bfa1fe168698984e3e8b0aaa5d2df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888757"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="e1aaa-105">Publier la topologie : page Sélectionner un CMS</span><span class="sxs-lookup"><span data-stu-id="e1aaa-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="e1aaa-106">Vous publiez la topologie que vous avez configurées à l’aide du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="e1aaa-107">Vous êtes invité à sélectionner à partir d’une liste pool frontal ou serveur frontal assumeront le rôle de contenir le magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="e1aaa-108">Qu’un seul pool frontal ou serveur frontal peut contenir ce rôle à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="e1aaa-109">Sur le serveur d’administration centrale</span><span class="sxs-lookup"><span data-stu-id="e1aaa-109">About the Central Management Server</span></span>
<span data-ttu-id="e1aaa-110">Le serveur de gestion centrale est un système maître/plusieurs réplicas, où la copie en lecture/écriture de la base de données est détenue par le serveur frontal qui contient le serveur d’administration centrale.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="e1aaa-111">Chaque ordinateur de la topologie, y compris le serveur frontal qui contient le serveur de gestion centralisée, dispose d’une copie en lecture seule des données du magasin Central de gestion de la base de SQL Server (appelée RTCLOCAL par défaut) installée sur l’ordinateur pendant l’installation et déploiement.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="e1aaa-112">La base de données local reçoit des mises à jour du réplica par l’Agent réplicateur d’utilisateurs Lync Server réplica qui s’exécute en tant que service sur tous les ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="e1aaa-113">Le nom de la base de données sur le serveur de gestion centrale et du réplica local est XDS, qui est composée des fichiers xds.mdf et xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="e1aaa-114">L’emplacement de la base de données master est référencé par un point de contrôle de service (SCP) dans les Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="e1aaa-115">Tous les outils qui utilisent le serveur d’administration centrale pour gérer et configurer Lync Server utilisent le SCP pour localiser le magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="e1aaa-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1aaa-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1aaa-116">See also</span></span>

[<span data-ttu-id="e1aaa-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="e1aaa-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
