---
title: 'Lync Server 2013 : utilisation du service de journalisation centralisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="90298-102">Utiliser le service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90298-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="90298-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="90298-104">Le service de journalisation centralisé est une nouvelle fonctionnalité de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90298-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="90298-105">Il s’agit d’un remplacement amélioré pour les outils **OCSLogger** et **OCSTracer** fournis dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="90298-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="90298-106">Vous pouvez utiliser le service de journalisation centralisé pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="90298-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="90298-107">Commencez à vous connecter sur un ou plusieurs ordinateurs et pools à partir d’un emplacement et d’une commande uniques.</span><span class="sxs-lookup"><span data-stu-id="90298-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="90298-108">Arrêtez la journalisation sur un ou plusieurs ordinateurs et pools à partir d’un emplacement et d’une commande uniques.</span><span class="sxs-lookup"><span data-stu-id="90298-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="90298-109">Recherchez les journaux sur un ou plusieurs ordinateurs et pools pour un emplacement et une commande uniques.</span><span class="sxs-lookup"><span data-stu-id="90298-109">Search logs on one or more computers and pools for a single location and command.</span></span> <span data-ttu-id="90298-110">Vous pouvez personnaliser la commande de recherche pour renvoyer l’ensemble d’agrégats de journaux qui ont été capturés et stockés sur tous les ordinateurs, ou renvoyer un résultat ajusté pour capturer des données spécifiques.</span><span class="sxs-lookup"><span data-stu-id="90298-110">You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="90298-111">Configurer les sessions de journalisation comme suit :</span><span class="sxs-lookup"><span data-stu-id="90298-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="90298-112">Définir un **Scenario** ou utiliser un scénario par défaut.</span><span class="sxs-lookup"><span data-stu-id="90298-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="90298-113">Dans le cadre du service de journalisation centralisé, un *scénario* est constitué d’une étendue (globale ou de site), d’un nom de scénario permettant d’identifier l’objet du scénario et d’un ou de plusieurs fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="90298-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="90298-114">Vous pouvez exécuter deux scénarios à tout moment sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="90298-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="90298-p104">Utiliser un *fournisseur* existant ou créer un nouveau fournisseur. Un *fournisseur* définit ce que la session de journalisation collecte, le niveau de détail, les composants à suivre et les indicateurs à appliquer.</span><span class="sxs-lookup"><span data-stu-id="90298-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="90298-117">Si vous connaissez lʼoutil OCSLogger, le terme <EM>fournisseurs</EM> fait référence à la collection de <STRONG>composants</STRONG> (par exemple, S4, SIPStack), à un <STRONG>type de journalisation</STRONG> (par exemple, WPP, EventLog ou fichier journal IIS), à un <STRONG>niveau de suivi</STRONG> (par exemple, All, verbose, debug) et aux <STRONG>indicateurs</STRONG> (par exemple, TF_COMPONENT, TF_DIAG).</span><span class="sxs-lookup"><span data-stu-id="90298-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="90298-118">Ces éléments sont définis dans le fournisseur (une variable Windows PowerShell) et transférés dans la commande service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="90298-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="90298-119">Configurez les ordinateurs et les pools à partir desquels vous voulez collecter les journaux.</span><span class="sxs-lookup"><span data-stu-id="90298-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="90298-120">Définissez l’étendue de la session de journalisation à partir du **site** d’options (exécuter les captures d’enregistrement sur les ordinateurs de ce site uniquement) ou **globale** (exécuter la capture de journalisation sur tous les ordinateurs du déploiement).</span><span class="sxs-lookup"><span data-stu-id="90298-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="90298-121">Le service de journalisation centralisé est extrêmement puissant et peut répondre à la plupart des besoins en matière de résolution des problèmes (grande ou petite).</span><span class="sxs-lookup"><span data-stu-id="90298-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="90298-122">D’une analyse de cause initiale aux problèmes de performances, le service de journalisation centralisé peut être un outil important pour tous les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="90298-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="90298-123">Tous les exemples sont affichés avec Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="90298-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="90298-124">Un composant de ligne de commande est associé au service de journalisation centralisé appelé **CLSController. exe**.</span><span class="sxs-lookup"><span data-stu-id="90298-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="90298-125">L’outil de ligne de commande est fourni à l’aide de l’outil proprement dit.</span><span class="sxs-lookup"><span data-stu-id="90298-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="90298-126">Néanmoins, il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="90298-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="90298-127">À l’aide de Lync Server Management Shell, vous avez accès à un ensemble de fonctionnalités plus volumineux et beaucoup plus configurable.</span><span class="sxs-lookup"><span data-stu-id="90298-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="90298-128">Il est recommandé de toujours considérer Lync Server Management Shell comme première et première méthode lors de l’utilisation du service de journalisation centralisé.</span><span class="sxs-lookup"><span data-stu-id="90298-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="90298-129">Les rubriques de cette section expliquent comment utiliser le service de journalisation centralisé et des exemples illustrant comment utiliser ses nombreuses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="90298-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="90298-130">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="90298-130">In This Section</span></span>

  - [<span data-ttu-id="90298-131">Présentation du service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="90298-132">Gestion des paramètres de configuration du service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="90298-133">Présentation des paramètres de configuration du service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="90298-134">Utiliser démarrer pour le service de journalisation centralisé pour capturer les journaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="90298-135">Utiliser le service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="90298-136">Utilisation de la recherche dans les journaux de capture créés par le service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="90298-137">Lecture de journaux de capture à partir du service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90298-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

