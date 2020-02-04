---
title: 'Lync Server 2013 : vue d’ensemble de la meilleure pratique Analyzer'
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
ms.openlocfilehash: 53e63bf6063803364a679a3cc0724ec1cbeae1a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="d1b52-102">Présentation de l’analyseur de meilleures pratiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1b52-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1b52-103">_**Dernière modification de la rubrique :** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="d1b52-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="d1b52-104">Vous pouvez utiliser Lync Server 2013, recommandée Analyzer pour identifier et résoudre les problèmes liés à votre déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b52-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="d1b52-105">L’analyseur de meilleures pratiques pour Lync Server 2013 recueille les informations de configuration des composants Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b52-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="d1b52-106">Avec l’accès au réseau approprié, le meilleur analyseur de recommandations peut examiner les serveurs exécutant les services de domaine Active Directory (AD DS), la messagerie unifiée Exchange Server (MU) et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b52-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="d1b52-107">Vous pouvez utiliser le BPA Analyzer pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1b52-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="d1b52-108">Effectuez des tests de manière proactive afin de vérifier que la configuration est définie conformément aux meilleures pratiques recommandées.</span><span class="sxs-lookup"><span data-stu-id="d1b52-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="d1b52-109">Détecter automatiquement les mises à jour requises pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b52-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="d1b52-110">Générer une liste des problèmes, tels que les paramètres de configuration de qualité optimale, les options non prises en charge, les mises à jour manquantes ou les pratiques que nous ne recommandons pas.</span><span class="sxs-lookup"><span data-stu-id="d1b52-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="d1b52-111">Aidez-vous à résoudre les problèmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d1b52-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="d1b52-112">Le Analyzer des recommandations fournit les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1b52-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="d1b52-113">Configuration minimale requise pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="d1b52-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="d1b52-114">Documentation en ligne sur les problèmes signalés, y compris des conseils de dépannage.</span><span class="sxs-lookup"><span data-stu-id="d1b52-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="d1b52-115">Informations de configuration que vous pouvez enregistrer pour révision ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d1b52-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="d1b52-116">Analyse du système de pointe.</span><span class="sxs-lookup"><span data-stu-id="d1b52-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="d1b52-117">Le vérificateur des recommandations utilise un ensemble de fichiers de configuration XML pour déterminer les informations à collecter dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b52-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="d1b52-118">En plus de vérifier les services de domaine Active Directory (AD DS), il vérifie les sources telles que le registre et les paramètres du système d’exploitation Windows Server dans WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="d1b52-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="d1b52-119">L’outil d’analyse des pratiques recommandées compare les données qu’il recueille avec un ensemble de règles prédéfinies pour les paramètres et configurations des déploiements de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b52-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="d1b52-120">Après avoir comparé les données collectées aux règles prédéfinies, l’outil signale des problèmes.</span><span class="sxs-lookup"><span data-stu-id="d1b52-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="d1b52-121">Pour chaque problème qu’il signale, le meilleur analyseur de recommandations fournit des informations sur les fonctionnalités qui ont été trouvées dans l’environnement Lync Server 2013 numérisé et la configuration recommandée.</span><span class="sxs-lookup"><span data-stu-id="d1b52-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="d1b52-122">Le Analyzer recommandations fournit également des liens vers des informations plus détaillées sur les problèmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d1b52-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1b52-123">L’analyseur de meilleures pratiques pour Lync Server 2013 recueille les informations de configuration uniquement à partir des composants Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b52-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="d1b52-124">Vous pouvez utiliser les versions précédentes de l’outil pour analyser d’anciens environnements.</span><span class="sxs-lookup"><span data-stu-id="d1b52-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="d1b52-125">Pour plus d’informations, voir <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Configuration requise pour l’exécution de l’analyseur de meilleures pratiques sur Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1b52-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

