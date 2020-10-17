---
title: 'Lync Server 2013 : vue d’ensemble de Best Practices Analyzer'
description: 'Lync Server 2013 : vue d’ensemble de Best Practices Analyzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ea48e88b26fa1081e5770fef2ac24efc21b74cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559280"
---
# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="48b63-103">Vue d’ensemble de Best Practices Analyzer dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b63-103">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48b63-104">_**Dernière modification de la rubrique :** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="48b63-104">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="48b63-105">Vous pouvez utiliser Lync Server 2013, Best Practices Analyzer pour identifier et résoudre les problèmes liés à votre déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b63-105">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="48b63-106">Lync Server 2013, Best Practices Analyzer recueille des informations de configuration à partir des composants Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b63-106">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="48b63-107">Avec l’accès réseau approprié, Best Practices Analyzer peut examiner les serveurs exécutant les services de domaine Active Directory, la messagerie unifiée Exchange Server et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b63-107">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="48b63-108">Vous pouvez utiliser Best Practices Analyzer pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="48b63-108">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="48b63-109">Effectuer des vérifications de manière proactive, en vérifiant que la configuration est définie conformément aux meilleures pratiques recommandées.</span><span class="sxs-lookup"><span data-stu-id="48b63-109">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="48b63-110">Détecter automatiquement les mises à jour requises pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b63-110">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="48b63-111">Générez une liste de problèmes, tels que des paramètres de configuration sous-optimaux, des options non prises en charge, des mises à jour manquantes ou des pratiques non recommandées.</span><span class="sxs-lookup"><span data-stu-id="48b63-111">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="48b63-112">Vous aider à résoudre des problèmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="48b63-112">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="48b63-113">Best Practices Analyzer offre les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="48b63-113">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="48b63-114">Conditions préalables d’installation minimales.</span><span class="sxs-lookup"><span data-stu-id="48b63-114">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="48b63-115">Documentation en ligne sur les problèmes signalés, y compris des conseils de dépannage.</span><span class="sxs-lookup"><span data-stu-id="48b63-115">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="48b63-116">Informations de configuration que vous pouvez enregistrer pour une révision ultérieure.</span><span class="sxs-lookup"><span data-stu-id="48b63-116">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="48b63-117">Analyse du système de pointe.</span><span class="sxs-lookup"><span data-stu-id="48b63-117">State-of-the-art system analysis.</span></span>

<span data-ttu-id="48b63-118">Best Practices Analyzer utilise un ensemble de fichiers de configuration XML pour déterminer les informations à collecter à partir de votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b63-118">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="48b63-119">En plus de vérifier les services de domaine Active Directory, il vérifie les sources telles que le Registre du système d’exploitation Windows Server et les paramètres dans WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="48b63-119">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="48b63-120">Best Practices Analyzer compare les données qu’il recueille avec un ensemble de règles prédéfinies pour les paramètres et les configurations des déploiements Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b63-120">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="48b63-121">Après avoir comparé les données collectées aux règles prédéfinies, l’outil signale les problèmes.</span><span class="sxs-lookup"><span data-stu-id="48b63-121">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="48b63-122">Pour chaque problème signalé par le service informatique, Best Practices Analyzer fournit des informations sur ce qui a été trouvé dans l’environnement Lync Server 2013 analysé et la configuration recommandée.</span><span class="sxs-lookup"><span data-stu-id="48b63-122">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="48b63-123">Best Practices Analyzer fournit également des liens vers des informations plus détaillées sur les problèmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="48b63-123">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48b63-124">Lync Server 2013, Best Practices Analyzer recueille des informations de configuration uniquement à partir des composants Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b63-124">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="48b63-125">Vous pouvez utiliser les versions précédentes de l’outil pour analyser les environnements précédents.</span><span class="sxs-lookup"><span data-stu-id="48b63-125">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="48b63-126">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Configuration requise pour l’exécution de Best Practices Analyzer dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48b63-126">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

