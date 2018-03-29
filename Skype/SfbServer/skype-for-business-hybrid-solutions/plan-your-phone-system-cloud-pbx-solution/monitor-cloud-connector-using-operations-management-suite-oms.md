---
title: Surveiller le connecteur Cloud à l’aide de la Suite de gestion des opérations (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lisez cette rubrique pour savoir comment surveiller votre version de connecteur de nuage 2.1 et d’un déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 5e03504f27eadbb235c1b5c84e8c7a19d66aea7d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="546ec-103">Surveiller le connecteur Cloud à l’aide de la Suite de gestion des opérations (OMS)</span><span class="sxs-lookup"><span data-stu-id="546ec-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>
 
<span data-ttu-id="546ec-104">Lisez cette rubrique pour savoir comment surveiller votre version de connecteur de nuage 2.1 et d’un déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="546ec-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>
  
<span data-ttu-id="546ec-105">Vous pouvez maintenant surveiller votre version de connecteur de nuage 2.1 et d’un déploiement ultérieur en utilisant la Suite de gestion des opérations (OMS), un solution de gestion informatique de Microsoft cloud.</span><span class="sxs-lookup"><span data-stu-id="546ec-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="546ec-106">OMS journal Analytique vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, y compris physiques et les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="546ec-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="546ec-107">Pour plus d’informations sur l’OMS et Analytique du journal, reportez-vous à la section [Quelle est la Suite de gestion des opérations (OMS) ?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="546ec-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>
  
<span data-ttu-id="546ec-108">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="546ec-108">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="546ec-109">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="546ec-109">Prerequisites</span></span>
    
- <span data-ttu-id="546ec-110">Configuration du connecteur de nuage pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="546ec-110">Configure Cloud Connector to use OMS</span></span>
    
- <span data-ttu-id="546ec-111">Configurer l’OMS</span><span class="sxs-lookup"><span data-stu-id="546ec-111">Configure OMS</span></span>
    
- <span data-ttu-id="546ec-112">Analyser les alertes dans votre référentiel Analytique du journal</span><span class="sxs-lookup"><span data-stu-id="546ec-112">Analyze the alerts in your Log Analytics repository</span></span>
    
- <span data-ttu-id="546ec-113">Jeu de surveillance recommandé</span><span class="sxs-lookup"><span data-stu-id="546ec-113">Recommended monitoring set</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="546ec-114">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="546ec-114">Prerequisites</span></span>

<span data-ttu-id="546ec-115">Avant de pouvoir utiliser OMS de déploiement de Cloud connecteur, vous devez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="546ec-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>
  
- <span data-ttu-id="546ec-116">**Un compte Azure et un espace de travail de l’OMS.**</span><span class="sxs-lookup"><span data-stu-id="546ec-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="546ec-117">Si vous ne disposez pas d’un compte Azure, vous devez en créer un pour utiliser OMS journal Analytique.</span><span class="sxs-lookup"><span data-stu-id="546ec-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="546ec-118">Pour plus d’informations sur la façon de créer un compte Azure et de configurer un espace de travail de l’OMS, consultez [mise en route de journal Analytique d’un espace de travail](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="546ec-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>
    
- <span data-ttu-id="546ec-119">**Connecteur de nuage version 2.1 ou ultérieure**</span><span class="sxs-lookup"><span data-stu-id="546ec-119">**Cloud Connector version 2.1 or later**</span></span>
    
- <span data-ttu-id="546ec-120">**Nouvelle recherche de journal de journal Analytique** est nécessaire pour la surveillance de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="546ec-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="546ec-121">Pour plus d’informations, consultez [mise à niveau de votre espace de travail Azure journal Analytique à la recherche des journaux de nouveau](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="546ec-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>
    
## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="546ec-122">Configuration du connecteur de nuage pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="546ec-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="546ec-123">Vous devez configurer votre environnement local de connecteur de nuage pour utiliser OMS.</span><span class="sxs-lookup"><span data-stu-id="546ec-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="546ec-124">Pour ce faire, vous aurez besoin de votre ID d’espace de travail OMS et de la clé, que vous pouvez trouver en utilisant le portail OMS comme suit : paramètres--\>Sources connectées--\> serveurs Windows :</span><span class="sxs-lookup"><span data-stu-id="546ec-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>
  
![Capture d'écran pour Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
<span data-ttu-id="546ec-126">La configuration de connecteur de nuage pour utiliser OMS dépend de votre scénario :</span><span class="sxs-lookup"><span data-stu-id="546ec-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>
  
- <span data-ttu-id="546ec-127">**Si vous installez un nouveau matériel de connecteur de nuage ou vous souhaitez redéployer une solution matérielle-logicielle**, procédez comme suit avant d’exécuter Install-CcAppliance :</span><span class="sxs-lookup"><span data-stu-id="546ec-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>
    
1. <span data-ttu-id="546ec-128">Dans le section [Common] du fichier CloudConnector.ini, définissez le paramètre OMSEnabled sur True.</span><span class="sxs-lookup"><span data-stu-id="546ec-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>
    
    <span data-ttu-id="546ec-129">Chaque fois que connecteur de nuage est déployé ou mis à niveau, il va tenter d’installer l’agent OMS automatiquement sur les ordinateurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="546ec-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="546ec-130">Activez cette fonction afin que l’agent de l’OMS peut survivre à la mise à jour automatique de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="546ec-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>
    
2. <span data-ttu-id="546ec-131">Pour configurer l’ID de l’OMS et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="546ec-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
- <span data-ttu-id="546ec-132">**Si vous installez un agent de l’OMS sur une appliance de connecteur de nuage existante**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="546ec-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>
    
1. <span data-ttu-id="546ec-133">Dans le fichier CloudConnector.ini de section [Common], définissez OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="546ec-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 
    
2. <span data-ttu-id="546ec-134">Exécutez CcConfiguration à l’importation.</span><span class="sxs-lookup"><span data-stu-id="546ec-134">Run Import-CcConfiguration.</span></span> 
    
3. <span data-ttu-id="546ec-135">Exécutez CcOMSAgent à l’installation.</span><span class="sxs-lookup"><span data-stu-id="546ec-135">Run Install-CcOMSAgent.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="546ec-136">Si les informations d’identification de OMSWorkspace n’a jamais été définie, vous êtes invité pour les informations d’identification lorsque vous exécutez l’installation-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="546ec-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 
  
- <span data-ttu-id="546ec-137">**Si vous souhaitez mettre à jour de l’ID d’espace de travail OMS ou clé dans un appareil de connecteur de nuage qui a déjà installé un agent d’OMS :**</span><span class="sxs-lookup"><span data-stu-id="546ec-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>
    
1. <span data-ttu-id="546ec-138">Pour configurer l’ID de l’OMS et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="546ec-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
2. <span data-ttu-id="546ec-139">Pour appliquer les mises à jour, exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="546ec-139">To apply the updates, run Install-CcOMSAgent.</span></span> 
    
- <span data-ttu-id="546ec-140">**Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**</span><span class="sxs-lookup"><span data-stu-id="546ec-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>
    
    <span data-ttu-id="546ec-141">Dans le portail de l’OMS, cliquez sur paramètres -\> Sources connectées -\> serveurs de Windows.</span><span class="sxs-lookup"><span data-stu-id="546ec-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="546ec-142">Vous verrez une liste d’ordinateurs connectés.</span><span class="sxs-lookup"><span data-stu-id="546ec-142">You will see a list of connected machines.</span></span> 
    
## <a name="configure-oms"></a><span data-ttu-id="546ec-143">Configurer l’OMS</span><span class="sxs-lookup"><span data-stu-id="546ec-143">Configure OMS</span></span>

<span data-ttu-id="546ec-144">Ensuite, vous devez spécifier votre configuration OMS via le portail de l’OMS.</span><span class="sxs-lookup"><span data-stu-id="546ec-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="546ec-145">Plus précisément, vous devez :</span><span class="sxs-lookup"><span data-stu-id="546ec-145">Specifically, you will need to:</span></span>
  
- <span data-ttu-id="546ec-146">Permet de spécifier des informations sur les journaux des événements et des compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="546ec-146">Specify information about event logs and performance counters.</span></span>
    
- <span data-ttu-id="546ec-147">Créer des alertes.</span><span class="sxs-lookup"><span data-stu-id="546ec-147">Create alerts.</span></span> 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="546ec-148">Spécifier des informations sur les journaux des événements et des compteurs de performance</span><span class="sxs-lookup"><span data-stu-id="546ec-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="546ec-149">Dans le portail de l’OMS, vous devez spécifier des informations sur les journaux des événements et des compteurs de performance comme suit :</span><span class="sxs-lookup"><span data-stu-id="546ec-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>
  
1. <span data-ttu-id="546ec-150">Accédez à paramètres -\>de données -\>les journaux d’événements Windows et ajoutez des journaux d’événements :</span><span class="sxs-lookup"><span data-stu-id="546ec-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 
    
  - <span data-ttu-id="546ec-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="546ec-151">Lync Server</span></span>
    
  - <span data-ttu-id="546ec-152">Application</span><span class="sxs-lookup"><span data-stu-id="546ec-152">Application</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="546ec-153">Vous devez entrer manuellement Lync Server dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="546ec-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="546ec-154">Il n’apparaît pas comme option dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="546ec-154">It does not appear as an option in the drop-down list.</span></span> 
  
    <span data-ttu-id="546ec-155">Pour plus d’informations, consultez [les sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="546ec-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>
    
2. <span data-ttu-id="546ec-156">Accédez à paramètres -\>de données -\> les compteurs de performances de Windows, et ajoutez des compteurs de performances pour :</span><span class="sxs-lookup"><span data-stu-id="546ec-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 
    
  - <span data-ttu-id="546ec-157">**Compteurs de niveau système d’exploitation**.</span><span class="sxs-lookup"><span data-stu-id="546ec-157">**OS level counters**.</span></span> <span data-ttu-id="546ec-158">Vous pouvez ajouter des compteurs au niveau du système d’exploitation, telles que l’utilisation du processeur, utilisation de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes telles que la capacité et de performances, sans ajouter explicitement les compteurs de l’Analyseur de performances réseau.</span><span class="sxs-lookup"><span data-stu-id="546ec-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="546ec-159">Peu importe comment vous décidez de les contrôler, Microsoft recommande que vous surveillez ces compteurs du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="546ec-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>
    
  - <span data-ttu-id="546ec-160">**Skype pour les compteurs de l’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="546ec-160">**Skype for Business counters**.</span></span> <span data-ttu-id="546ec-161">Il existe de nombreux compteurs fournis par Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="546ec-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="546ec-162">Vous trouverez ces compteurs en vous connectant à n’importe quel serveur de médiation et d’ouverture de l’Analyseur de performances.</span><span class="sxs-lookup"><span data-stu-id="546ec-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="546ec-163">Ces compteurs commencent par « LS : ».</span><span class="sxs-lookup"><span data-stu-id="546ec-163">These counters start with "LS:".</span></span> <span data-ttu-id="546ec-164">Microsoft vous recommande de commencer par les compteurs suivants de capacité au minimum et ajouter d’autres qui sont d’intérêt :</span><span class="sxs-lookup"><span data-stu-id="546ec-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>
    
    <span data-ttu-id="546ec-165">Nombre total d’appels actif :</span><span class="sxs-lookup"><span data-stu-id="546ec-165">Total active calls:</span></span>
    
  - <span data-ttu-id="546ec-166">LS:MediationServer - entrant Calls(_Total)\- en cours</span><span class="sxs-lookup"><span data-stu-id="546ec-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
  - <span data-ttu-id="546ec-167">LS:MediationServer - Calls(_Total) sortants\- en cours</span><span class="sxs-lookup"><span data-stu-id="546ec-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
    <span data-ttu-id="546ec-168">Support active totale de contourner les appels :</span><span class="sxs-lookup"><span data-stu-id="546ec-168">Total active media bypass calls:</span></span>
    
  - <span data-ttu-id="546ec-169">LS:MediationServer - entrant Calls(_Total)\- support Active ignore les appels</span><span class="sxs-lookup"><span data-stu-id="546ec-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 
    
  - <span data-ttu-id="546ec-170">LS:MediationServer - Calls(_Total) sortants\- media Active ignore les appels</span><span class="sxs-lookup"><span data-stu-id="546ec-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="546ec-171">Vous devez entrer manuellement les compteurs de performance dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="546ec-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="546ec-172">Ils n’apparaissent pas en tant qu’options dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="546ec-172">They do not appear as options in the drop-down list.</span></span> 
  
    <span data-ttu-id="546ec-173">Pour plus d’informations, voir les [sources de données de performance Windows et Linux dans journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="546ec-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>
    
### <a name="create-alerts"></a><span data-ttu-id="546ec-174">Créer des alertes</span><span class="sxs-lookup"><span data-stu-id="546ec-174">Create alerts</span></span>

<span data-ttu-id="546ec-175">Il existe deux types d’alertes dans OMS : nombre de résultats alertes et mesure métrique.</span><span class="sxs-lookup"><span data-stu-id="546ec-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="546ec-176">Pour plus d’informations sur la création d’alertes, reportez-vous à la section [utilisation des règles d’alerte dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="546ec-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>
  
<span data-ttu-id="546ec-177">Lors de la création d’alertes, tenez compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="546ec-177">You should consider the following when creating alerts:</span></span>
  
- <span data-ttu-id="546ec-178">Vérifiez que l’alerte est une alerte nombre de résultats, qui est la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="546ec-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 
    
- <span data-ttu-id="546ec-179">Les requêtes de démonstration nécessitent que « Nombre de résultats » est définie à « supérieur à 0 ».</span><span class="sxs-lookup"><span data-stu-id="546ec-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 
    
- <span data-ttu-id="546ec-180">Il est recommandé de définir la fenêtre de temps et de fréquence de l’alerte à 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="546ec-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 
    
- <span data-ttu-id="546ec-181">Il est recommandé de ne pas activer « Supprimer des alertes » pour les alertes de démonstration.</span><span class="sxs-lookup"><span data-stu-id="546ec-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 
    
- <span data-ttu-id="546ec-182">Pour les scénarios d’alerte par défaut, Microsoft recommande la création d’une paire d’alertes : d’une erreur et la réinitialisation d’une alerte.</span><span class="sxs-lookup"><span data-stu-id="546ec-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="546ec-183">Pour le message d’erreur, sélectionnez le niveau de gravité critique ; l’alerte de réinitialisation, sélectionnez le niveau de gravité information.</span><span class="sxs-lookup"><span data-stu-id="546ec-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>
    
<span data-ttu-id="546ec-184">Les sections suivantes décrivent comment créer des alertes de l’échantillon.</span><span class="sxs-lookup"><span data-stu-id="546ec-184">The following sections describe how to create sample alerts.</span></span>
  
 <span data-ttu-id="546ec-185">**Créer une paire d’alerte : « RTCMEDSRV ne fonctionne pas dans les serveurs de médiation » et « RTCMEDSRV est en cours d’exécution sur les serveurs de médiation dans »**</span><span class="sxs-lookup"><span data-stu-id="546ec-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>
  
<span data-ttu-id="546ec-186">Pour créer cette paire d’alerte :</span><span class="sxs-lookup"><span data-stu-id="546ec-186">To create this alert pair:</span></span>
  
- <span data-ttu-id="546ec-187">La requête pour le message d’erreur est :</span><span class="sxs-lookup"><span data-stu-id="546ec-187">The query for the error alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="546ec-188">La requête utilise le filtre d’ordinateur *où ordinateur contient « MediationServer »* .</span><span class="sxs-lookup"><span data-stu-id="546ec-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="546ec-189">Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».</span><span class="sxs-lookup"><span data-stu-id="546ec-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>
    
     <span data-ttu-id="546ec-190">Vous souhaitez remplacer le filtre par le filtre de votre propre ordinateur ou simplement le supprimer.</span><span class="sxs-lookup"><span data-stu-id="546ec-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="546ec-191">Vous pouvez créer des filtres de chaîne complexe sans les expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="546ec-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="546ec-192">Pour plus d’informations, consultez [opérateurs de type chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="546ec-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="546ec-193">Vous pouvez également choisir d’utiliser des expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="546ec-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="546ec-194">En outre, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche à l’aide de ce groupe comme filtre de votre ordinateur dans votre requête d’alerte.</span><span class="sxs-lookup"><span data-stu-id="546ec-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="546ec-195">Pour plus d’informations, consultez [groupes d’ordinateurs dans le journal Analytique journal des recherches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="546ec-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>
    
    <span data-ttu-id="546ec-196">Pour chaque ordinateur, l’erreur de la requête obtient le dernier journal des événements pour les deux le démarrage du service RTCMEDSRV et arrêt de service.</span><span class="sxs-lookup"><span data-stu-id="546ec-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="546ec-197">Il retournera un journal si le dernier événement est l’événement d’arrêt de service ; Il ne renvoie rien si le dernier événement est l’événement de démarrage du service.</span><span class="sxs-lookup"><span data-stu-id="546ec-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="546ec-198">En bref, la requête renvoie une liste de serveurs dont RTCMEDSRV est arrêté dans la fenêtre de temps.</span><span class="sxs-lookup"><span data-stu-id="546ec-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 
    
- <span data-ttu-id="546ec-199">La requête de l’alerte de réinitialisation est :</span><span class="sxs-lookup"><span data-stu-id="546ec-199">The query for the reset alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="546ec-200">La requête de réinitialisation ne la chose opposée de la requête de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="546ec-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="546ec-201">Pour chaque ordinateur, il retournera un si le dernier événement est que le service démarre l’événement ; Il ne renvoie rien si le dernier événement est l’événement d’arrêt de service.</span><span class="sxs-lookup"><span data-stu-id="546ec-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>
    
 <span data-ttu-id="546ec-202">**Créer une paire d’alerte : "trop grand nombre d’appels simultané dans les serveurs de médiation » et « appels simultanés retomber à une charge normale »**</span><span class="sxs-lookup"><span data-stu-id="546ec-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>
  
<span data-ttu-id="546ec-203">Pour créer cette alerte :</span><span class="sxs-lookup"><span data-stu-id="546ec-203">To create this alert:</span></span>
  
- <span data-ttu-id="546ec-204">La requête pour le message d’erreur est :</span><span class="sxs-lookup"><span data-stu-id="546ec-204">The query for the error alert is:</span></span>
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="546ec-205">Pour chaque ordinateur, la requête obtiendra les dernières compteurs pour les appels entrants et les appels sortants et somme des deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="546ec-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="546ec-206">Il retournera une session si la valeur de la somme est supérieure à 500 ; Il ne renvoie rien si elle n’est pas.</span><span class="sxs-lookup"><span data-stu-id="546ec-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="546ec-207">En bref, la requête renvoie une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.</span><span class="sxs-lookup"><span data-stu-id="546ec-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>
    
- <span data-ttu-id="546ec-208">La requête de l’alerte de réinitialisation est :</span><span class="sxs-lookup"><span data-stu-id="546ec-208">The query for the reset alert is:</span></span>
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    <span data-ttu-id="546ec-209">La requête de réinitialisation ne la chose opposée de la requête de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="546ec-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="546ec-210">Pour chaque ordinateur, la requête obtiendra les dernières compteurs pour les appels entrants et les appels sortants et somme des deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="546ec-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="546ec-211">Il retournera un journal si la valeur de la somme est inférieure à 500 ; elle retourne nothing dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="546ec-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>
    
 <span data-ttu-id="546ec-212">**Créer une alerte : « utilisation de l’UC \> 90 ou RTCMEDIARELAY s’est arrêté dans les serveurs « alerte**</span><span class="sxs-lookup"><span data-stu-id="546ec-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>
  
<span data-ttu-id="546ec-213">Pour créer cette alerte, la requête est la suivante :</span><span class="sxs-lookup"><span data-stu-id="546ec-213">To create this alert, the query is:</span></span>
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="546ec-214">La requête obtiendra tous les compteurs d’utilisation de processeur et événement d’arrêt de service à partir de tous les ordinateurs et retour un journal si l’utilisation du processeur dépasse 90 % ou un service est déjà arrêté.</span><span class="sxs-lookup"><span data-stu-id="546ec-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="546ec-215">Analyser les alertes dans votre référentiel Analytique du journal</span><span class="sxs-lookup"><span data-stu-id="546ec-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="546ec-216">Pour analyser les alertes dans votre référentiel, utiliser la solution de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="546ec-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="546ec-217">Pour plus d’informations, consultez la [solution de gestion des alertes dans la Suite Gestion des opérations (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="546ec-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>
  
## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="546ec-218">Ensemble de surveillance minimal recommandé</span><span class="sxs-lookup"><span data-stu-id="546ec-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="546ec-219">Pour identifier les problèmes avec les journaux des événements et des compteurs de performance :</span><span class="sxs-lookup"><span data-stu-id="546ec-219">To identify issues with event logs and performance counters:</span></span> 
  
- <span data-ttu-id="546ec-220">**Journaux des événements.**</span><span class="sxs-lookup"><span data-stu-id="546ec-220">**Event logs.**</span></span> <span data-ttu-id="546ec-221">Pour tout problème, il doit être une paire d’événements, avec un ensemble d’événements pour indiquer que quelque chose est incorrect, tandis que l’autre indique que tout est bien.</span><span class="sxs-lookup"><span data-stu-id="546ec-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="546ec-222">Pour une période donnée, il est le dernier événement enregistré qui indique si un élément est explosion pour cette période.</span><span class="sxs-lookup"><span data-stu-id="546ec-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>
    
- <span data-ttu-id="546ec-223">**Compteurs de performance.**</span><span class="sxs-lookup"><span data-stu-id="546ec-223">**Performance Counters.**</span></span> <span data-ttu-id="546ec-224">Il doit exister un seuil pour les compteurs surveillés.</span><span class="sxs-lookup"><span data-stu-id="546ec-224">There should be a threshold for the monitored counters.</span></span>
    
<span data-ttu-id="546ec-225">Le tableau suivant répertorie les services que Microsoft vous recommande de surveillance en répertoriant les ID d’événement arrêter et démarrer :</span><span class="sxs-lookup"><span data-stu-id="546ec-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="546ec-226">Nom du service</span><span class="sxs-lookup"><span data-stu-id="546ec-226">Service Name</span></span>  <br/> |<span data-ttu-id="546ec-227">Rôle du serveur cible</span><span class="sxs-lookup"><span data-stu-id="546ec-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="546ec-228">Arrêter l’ID d’événement</span><span class="sxs-lookup"><span data-stu-id="546ec-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="546ec-229">ID de l’événement de début</span><span class="sxs-lookup"><span data-stu-id="546ec-229">Start Event ID</span></span>  <br/> |
|<span data-ttu-id="546ec-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="546ec-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="546ec-231">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="546ec-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="546ec-232">25003</span><span class="sxs-lookup"><span data-stu-id="546ec-232">25003</span></span>  <br/> |<span data-ttu-id="546ec-233">25002</span><span class="sxs-lookup"><span data-stu-id="546ec-233">25002</span></span>  <br/> |
|<span data-ttu-id="546ec-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="546ec-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="546ec-235">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="546ec-235">Edge Server</span></span>  <br/> |<span data-ttu-id="546ec-236">12289</span><span class="sxs-lookup"><span data-stu-id="546ec-236">12289</span></span>  <br/> |<span data-ttu-id="546ec-237">12288</span><span class="sxs-lookup"><span data-stu-id="546ec-237">12288</span></span>  <br/> |
|<span data-ttu-id="546ec-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="546ec-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="546ec-239">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="546ec-239">Edge Server</span></span>  <br/> |<span data-ttu-id="546ec-240">19003</span><span class="sxs-lookup"><span data-stu-id="546ec-240">19003</span></span>  <br/> |<span data-ttu-id="546ec-241">19002</span><span class="sxs-lookup"><span data-stu-id="546ec-241">19002</span></span>  <br/> |
|<span data-ttu-id="546ec-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="546ec-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="546ec-243">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="546ec-243">Edge Server</span></span>  <br/> |<span data-ttu-id="546ec-244">22003</span><span class="sxs-lookup"><span data-stu-id="546ec-244">22003</span></span>  <br/> |<span data-ttu-id="546ec-245">22002</span><span class="sxs-lookup"><span data-stu-id="546ec-245">22002</span></span>  <br/> |
   
<span data-ttu-id="546ec-246">Le tableau suivant répertorie les problèmes de réseau, Microsoft vous recommande de surveillance :</span><span class="sxs-lookup"><span data-stu-id="546ec-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="546ec-247">Nom du moniteur</span><span class="sxs-lookup"><span data-stu-id="546ec-247">Monitor Name</span></span>  <br/> |<span data-ttu-id="546ec-248">Rôle du serveur cible</span><span class="sxs-lookup"><span data-stu-id="546ec-248">Target Server Role</span></span>  <br/> |<span data-ttu-id="546ec-249">Expression de l’ID d’événement de réussite</span><span class="sxs-lookup"><span data-stu-id="546ec-249">Success Event ID expression</span></span>  <br/> |<span data-ttu-id="546ec-250">Expression de l’ID d’événement d’erreur</span><span class="sxs-lookup"><span data-stu-id="546ec-250">Error Event ID expression</span></span>  <br/> |<span data-ttu-id="546ec-251">Exemple de défaillance</span><span class="sxs-lookup"><span data-stu-id="546ec-251">Failure example</span></span>  <br/> |
|<span data-ttu-id="546ec-252">Serveur de médiation pour Échec de connectivité de passerelle</span><span class="sxs-lookup"><span data-stu-id="546ec-252">Mediation Server to gateway connectivity failure</span></span>  <br/> |<span data-ttu-id="546ec-253">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="546ec-253">Mediation Server</span></span>  <br/> |<span data-ttu-id="546ec-254">25062</span><span class="sxs-lookup"><span data-stu-id="546ec-254">25062</span></span> || <span data-ttu-id="546ec-255">25002</span><span class="sxs-lookup"><span data-stu-id="546ec-255">25002</span></span>  <br/> |<span data-ttu-id="546ec-256">25061</span><span class="sxs-lookup"><span data-stu-id="546ec-256">25061</span></span>  <br/> |<span data-ttu-id="546ec-257">Échec de MS PING (option) passerelle</span><span class="sxs-lookup"><span data-stu-id="546ec-257">MS PING (option) Gateway failed</span></span>  <br/> |
|<span data-ttu-id="546ec-258">Serveur de médiation pour passerelle appeler Échec d’achèvement</span><span class="sxs-lookup"><span data-stu-id="546ec-258">Mediation Server to gateway call completion failure</span></span>  <br/> |<span data-ttu-id="546ec-259">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="546ec-259">Mediation Server</span></span>  <br/> |<span data-ttu-id="546ec-260">25064</span><span class="sxs-lookup"><span data-stu-id="546ec-260">25064</span></span> || <span data-ttu-id="546ec-261">25002</span><span class="sxs-lookup"><span data-stu-id="546ec-261">25002</span></span>  <br/> |<span data-ttu-id="546ec-262">25063</span><span class="sxs-lookup"><span data-stu-id="546ec-262">25063</span></span>  <br/> |<span data-ttu-id="546ec-263">Échec de MS, essayez de faire appel à la passerelle</span><span class="sxs-lookup"><span data-stu-id="546ec-263">MS trying to make call to Gateway failed</span></span>  <br/> |
|<span data-ttu-id="546ec-264">Problèmes réseau critiques.</span><span class="sxs-lookup"><span data-stu-id="546ec-264">Critical network problems</span></span>  <br/> |<span data-ttu-id="546ec-265">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="546ec-265">Edge Server</span></span>  <br/> |<span data-ttu-id="546ec-266">14353</span><span class="sxs-lookup"><span data-stu-id="546ec-266">14353</span></span> || <span data-ttu-id="546ec-267">12288</span><span class="sxs-lookup"><span data-stu-id="546ec-267">12288</span></span>  <br/> |<span data-ttu-id="546ec-268">14624</span><span class="sxs-lookup"><span data-stu-id="546ec-268">14624</span></span>  <br/> |<span data-ttu-id="546ec-269">Le transport TLS n’a pas pu démarrer sur l’adresse IP locale 192.168.231.14 sur le port 5061</span><span class="sxs-lookup"><span data-stu-id="546ec-269">Transport TLS has failed to start on local IP address 192.168.231.14 at port 5061</span></span>  <br/> |
   
<span data-ttu-id="546ec-270">Voici les compteurs de capacité d’appel qui doivent être contrôlés.</span><span class="sxs-lookup"><span data-stu-id="546ec-270">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="546ec-271">Ces numéros doivent être moins que 500 pour l’édition standard de nuage connecteur ; moins de 50 pour édition minimale de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="546ec-271">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>
  
- <span data-ttu-id="546ec-272">LS:MediationServer - entrant Calls(_Total)\- en cours</span><span class="sxs-lookup"><span data-stu-id="546ec-272">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="546ec-273">LS:MediationServer - Calls(_Total) sortants\- en cours</span><span class="sxs-lookup"><span data-stu-id="546ec-273">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="546ec-274">LS:MediationServer - entrant Calls(_Total)\- support Active ignore les appels</span><span class="sxs-lookup"><span data-stu-id="546ec-274">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>
    
- <span data-ttu-id="546ec-275">LS:MediationServer - Calls(_Total) sortants\- media Active ignore les appels</span><span class="sxs-lookup"><span data-stu-id="546ec-275">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>
    
## <a name="see-also"></a><span data-ttu-id="546ec-276">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="546ec-276">See also</span></span>

<span data-ttu-id="546ec-277">Pour plus d’informations sur l’utilisation de l’OMS, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="546ec-277">For more information about working with OMS, see the following:</span></span>
  
- [<span data-ttu-id="546ec-278">Rechercher des données à l’aide de la recherche de journal de journal Analytique</span><span class="sxs-lookup"><span data-stu-id="546ec-278">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [<span data-ttu-id="546ec-279">Journal Azure Analytique de référence du langage</span><span class="sxs-lookup"><span data-stu-id="546ec-279">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)
    
- [<span data-ttu-id="546ec-280">Présentation des alertes dans le journal Analytique</span><span class="sxs-lookup"><span data-stu-id="546ec-280">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [<span data-ttu-id="546ec-281">Connecter des ordinateurs Windows au service journal Analytique dans Azure</span><span class="sxs-lookup"><span data-stu-id="546ec-281">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

