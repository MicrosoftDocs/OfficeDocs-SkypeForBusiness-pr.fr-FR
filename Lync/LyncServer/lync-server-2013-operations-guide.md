---
title: 'Guide des opérations de Lync Server 2013 :'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b4f3e0a9beaae9419b11bf7353319b3b3ad2b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="99e0f-102">Operations Guide for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99e0f-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="99e0f-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="99e0f-104">Ce document décrit les processus opérationnels, les tâches et les outils requis pour gérer un environnement logiciel de communication Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99e0f-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="99e0f-105">Cet article explique comment gérer Lync Server 2013 conformément au modèle MOF (Microsoft Operations Framework) et vous aidera à concevoir un environnement de gestion des opérations efficace, qui inclut l’implémentation de plannings, de processus et de procédures pour gérer une environnement de travail efficace.</span><span class="sxs-lookup"><span data-stu-id="99e0f-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99e0f-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="99e0f-106">In This Section</span></span>

<span data-ttu-id="99e0f-107">Les sections suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="99e0f-107">The following sections are included:</span></span>

  - [<span data-ttu-id="99e0f-108">Recommandations en matière d’environnements Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="99e0f-109">Tâches quotidiennes dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="99e0f-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="99e0f-110">Tâches hebdomadaires dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="99e0f-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="99e0f-111">Tâches mensuelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="99e0f-112">Tâches selon les besoins dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="99e0f-113">Listes de contrôle des opérations pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="99e0f-114">Surveiller Lync Server 2013 avec System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="99e0f-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="99e0f-115">Dépendances opérationnelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="99e0f-116">Résolution des problèmes et indicateurs d’intégrité clés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="99e0f-117">Il est supposé que votre déploiement de Microsoft Lync Server 2013 est terminé.</span><span class="sxs-lookup"><span data-stu-id="99e0f-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="99e0f-118">Si ce n’est pas le cas, reportez-vous à la planification et au contenu de déploiement pour Microsoft Lync Server 2013 avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="99e0f-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99e0f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99e0f-119">See Also</span></span>


[<span data-ttu-id="99e0f-120">Prise en main avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="99e0f-121">Planification de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="99e0f-122">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e0f-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="99e0f-123">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="99e0f-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

