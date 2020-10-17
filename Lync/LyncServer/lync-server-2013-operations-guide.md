---
title: 'Lync Server 2013 : Guide des opérations'
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
ms.openlocfilehash: 212a640577d55e80225a597c9263b7a2573d257f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524531"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="f5991-102">Guide des opérations pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-102">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5991-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="f5991-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="f5991-104">Ce document décrit les processus, les tâches et les outils opérationnels nécessaires pour gérer un environnement logiciel de communications Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5991-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="f5991-105">Elle explique comment gérer Lync Server 2013 conformément au modèle MOF (Microsoft Operations Framework) et il vous permettra de concevoir un environnement de gestion des opérations efficace, qui inclut la mise en œuvre de planifications, de processus et de procédures pour maintenir un environnement de travail efficace.</span><span class="sxs-lookup"><span data-stu-id="f5991-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5991-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f5991-106">In This Section</span></span>

<span data-ttu-id="f5991-107">Les sections suivantes sont incluses :</span><span class="sxs-lookup"><span data-stu-id="f5991-107">The following sections are included:</span></span>

  - [<span data-ttu-id="f5991-108">Meilleures pratiques pour les environnements Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="f5991-109">Tâches quotidiennes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="f5991-110">Tâches hebdomadaires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="f5991-111">Tâches mensuelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="f5991-112">Tâches nécessaires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="f5991-113">Listes de vérification des opérations pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="f5991-114">Surveillance de Lync Server 2013 avec System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="f5991-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="f5991-115">Dépendances opérationnelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="f5991-116">Résolution des problèmes et indicateurs d’intégrité clés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="f5991-117">Le déploiement de Microsoft Lync Server 2013 est supposé se terminer.</span><span class="sxs-lookup"><span data-stu-id="f5991-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="f5991-118">Si ce n’est pas le cas, reportez-vous à la rubrique planification et déploiement du contenu pour Microsoft Lync Server 2013 avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="f5991-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5991-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5991-119">See Also</span></span>


[<span data-ttu-id="f5991-120">Prise en main de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="f5991-121">Planification de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="f5991-122">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5991-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="f5991-123">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="f5991-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

