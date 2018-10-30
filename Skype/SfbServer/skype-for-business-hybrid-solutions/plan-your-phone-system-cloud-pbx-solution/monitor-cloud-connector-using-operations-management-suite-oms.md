---
title: Surveiller le connecteur de nuage à l’aide de la Suite de gestion des opérations (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lisez cette rubrique pour savoir comment surveiller votre version de nuage connecteur 2.1 et de déploiement ultérieure à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 36d70a1504eab085d319e46d03c3c6f0bd9d14f3
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839822"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="51303-103">Surveiller le connecteur de nuage à l’aide de la Suite de gestion des opérations (OMS)</span><span class="sxs-lookup"><span data-stu-id="51303-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="51303-104">Lisez cette rubrique pour savoir comment surveiller votre version de nuage connecteur 2.1 et de déploiement ultérieure à l’aide de Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="51303-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="51303-105">Vous pouvez maintenant surveiller votre version de nuage connecteur 2.1 et de déploiement ultérieure à l’aide des opérations de gestion de Suite (OMS), un solution de gestion informatique en nuage de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51303-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="51303-106">OMS journal Analytique vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, y compris physiques et les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="51303-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="51303-107">Pour plus d’informations sur OMS et journal Analytique, voir [Quelle est la Suite de gestion des opérations (OMS) ?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="51303-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="51303-108">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="51303-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="51303-109">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="51303-109">Prerequisites</span></span>

- <span data-ttu-id="51303-110">Configurer le connecteur sur le nuage pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="51303-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="51303-111">Configurer OMS</span><span class="sxs-lookup"><span data-stu-id="51303-111">Configure OMS</span></span>

- <span data-ttu-id="51303-112">Analyser les alertes dans le référentiel de journal Analytique</span><span class="sxs-lookup"><span data-stu-id="51303-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="51303-113">Jeu de surveillance recommandé</span><span class="sxs-lookup"><span data-stu-id="51303-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51303-114">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="51303-114">Prerequisites</span></span>

<span data-ttu-id="51303-115">Avant de pouvoir utiliser OMS pour analyser votre déploiement en nuage connecteur, vous devez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="51303-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="51303-116">**Un compte Azure et un espace de travail OMS.**</span><span class="sxs-lookup"><span data-stu-id="51303-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="51303-117">Si vous ne disposez pas d’un compte Azure, vous devrez créer un pour utiliser OMS journal Analytique.</span><span class="sxs-lookup"><span data-stu-id="51303-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="51303-118">Pour plus d’informations sur la façon de créer un compte Azure et configurer un espace de travail OMS, voir [Démarrer avec un espace de travail journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="51303-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="51303-119">**Nuage connecteur 2.1 ou version ultérieure**</span><span class="sxs-lookup"><span data-stu-id="51303-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="51303-120">**Recherche de journal de journal Analytique** est requis pour la surveillance du connecteur sur le nuage.</span><span class="sxs-lookup"><span data-stu-id="51303-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="51303-121">Pour plus d’informations, voir [l’espace de travail Azure journal Analytique nouvelle recherche de journal de mise à niveau](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="51303-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="51303-122">Configurer le connecteur sur le nuage pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="51303-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="51303-123">Vous devez configurer votre environnement local de nuage connecteur pour utiliser OMS.</span><span class="sxs-lookup"><span data-stu-id="51303-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="51303-124">Pour ce faire, vous aurez besoin de votre ID d’espace de travail OMS et la clé, vous pouvez trouver en utilisant le portail OMS comme suit : paramètres--\>Sources connectées--\> serveurs Windows :</span><span class="sxs-lookup"><span data-stu-id="51303-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Capture d'écran pour Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="51303-126">Comment configurer le nuage connecteur pour utiliser OMS dépend de votre scénario :</span><span class="sxs-lookup"><span data-stu-id="51303-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="51303-127">**Si vous installez un nouveau matériel nuage connecteur ou vous souhaitez redéployer un matériel**, procédez comme suit avant d’exécuter Install-CcAppliance :</span><span class="sxs-lookup"><span data-stu-id="51303-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="51303-128">Dans le fichier CloudConnector.ini section [courantes], définissez le paramètre OMSEnabled sur True.</span><span class="sxs-lookup"><span data-stu-id="51303-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="51303-129">Chaque fois que le nuage connecteur est déployé ou mis à niveau, il essaiera d’installer l’agent d’OMS automatiquement sur les ordinateurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="51303-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="51303-130">Activer cette fonctionnalité afin que l’agent OMS puisse résister à la mise à jour automatique du nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="51303-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="51303-131">Pour configurer le OMS ID et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="51303-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="51303-132">**Si vous installez un agent OMS sur une appliance nuage connecteur existant**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="51303-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="51303-133">Dans le fichier CloudConnector.ini section [courantes], définissez OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="51303-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="51303-134">Exécutez Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="51303-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="51303-135">Exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="51303-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="51303-136">Si les informations d’identification OMSWorkspace n’a jamais été définie, vous êtes invité pour les informations d’identification lorsque vous exécutez install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="51303-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="51303-137">**Si vous souhaitez mettre à jour de l’ID d’espace de travail OMS ou clés dans une solution de nuage connecteur qui a déjà installé un agent OMS :**</span><span class="sxs-lookup"><span data-stu-id="51303-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="51303-138">Pour configurer le OMS ID et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="51303-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="51303-139">Pour appliquer les mises à jour, exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="51303-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="51303-140">**Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**</span><span class="sxs-lookup"><span data-stu-id="51303-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="51303-141">Dans le portail OMS, accédez à paramètres -\> Sources connectées -\> serveurs Windows.</span><span class="sxs-lookup"><span data-stu-id="51303-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="51303-142">Vous verrez une liste d’ordinateurs connectés.</span><span class="sxs-lookup"><span data-stu-id="51303-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="51303-143">Configurer OMS</span><span class="sxs-lookup"><span data-stu-id="51303-143">Configure OMS</span></span>

<span data-ttu-id="51303-144">Ensuite, vous devrez spécifier votre configuration OMS à l’aide du portail OMS.</span><span class="sxs-lookup"><span data-stu-id="51303-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="51303-145">Plus précisément, vous devez :</span><span class="sxs-lookup"><span data-stu-id="51303-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="51303-146">Spécifier des informations sur les compteurs de performance et les journaux des événements.</span><span class="sxs-lookup"><span data-stu-id="51303-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="51303-147">Créer des alertes.</span><span class="sxs-lookup"><span data-stu-id="51303-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="51303-148">Spécifier des informations sur les compteurs de performance et les journaux des événements</span><span class="sxs-lookup"><span data-stu-id="51303-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="51303-149">Dans le portail OMS, vous devez spécifier les informations sur les journaux des événements et les compteurs de performance comme suit :</span><span class="sxs-lookup"><span data-stu-id="51303-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="51303-150">Accédez à paramètres -\>données -\>journaux des événements Windows et ajoutez des journaux des événements :</span><span class="sxs-lookup"><span data-stu-id="51303-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="51303-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="51303-151">Lync Server</span></span>

   - <span data-ttu-id="51303-152">Application</span><span class="sxs-lookup"><span data-stu-id="51303-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="51303-153">Vous devez entrer manuellement Lync Server dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="51303-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="51303-154">Il n’apparaît pas en tant qu’option dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="51303-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="51303-155">Pour plus d’informations, voir [les sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="51303-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="51303-156">Accédez à paramètres -\>données -\> les compteurs de performances de Windows, et ajoutez des compteurs de performance pour :</span><span class="sxs-lookup"><span data-stu-id="51303-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="51303-157">**Compteurs de niveau du système d’exploitation**.</span><span class="sxs-lookup"><span data-stu-id="51303-157">**OS level counters**.</span></span> <span data-ttu-id="51303-158">Vous pouvez ajouter des compteurs au niveau du système d’exploitation, telles que l’utilisation du processeur, de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes telles que la capacité et les performances, l’Analyseur de performances réseau sans ajouter explicitement des compteurs.</span><span class="sxs-lookup"><span data-stu-id="51303-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="51303-159">Quelle que soit la façon dont vous décidez d’analyser les, Microsoft recommande que vous analysez ces compteurs de système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="51303-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="51303-160">**Skype pour les compteurs de l’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="51303-160">**Skype for Business counters**.</span></span> <span data-ttu-id="51303-161">Il existe de nombreux compteurs fournis par Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="51303-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="51303-162">Vous trouverez ces compteurs en vous connectant à n’importe quel serveur de médiation et l’ouverture de l’Analyseur de performances.</span><span class="sxs-lookup"><span data-stu-id="51303-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="51303-163">Ces compteurs commencent par « LS : ».</span><span class="sxs-lookup"><span data-stu-id="51303-163">These counters start with "LS:".</span></span> <span data-ttu-id="51303-164">Microsoft recommande que vous commencez par les compteurs suivants de la capacité au minimum et ajoutez d’autres personnes qui présentent un intérêt :</span><span class="sxs-lookup"><span data-stu-id="51303-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="51303-165">Nombre total d’appels actif :</span><span class="sxs-lookup"><span data-stu-id="51303-165">Total active calls:</span></span>

   - <span data-ttu-id="51303-166">LS:MediationServer - entrant Calls(_Total)\- en cours</span><span class="sxs-lookup"><span data-stu-id="51303-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="51303-167">LS:MediationServer - Calls(_Total) sortants\- en cours</span><span class="sxs-lookup"><span data-stu-id="51303-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="51303-168">Les appels déviés total multimédia active :</span><span class="sxs-lookup"><span data-stu-id="51303-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="51303-169">LS:MediationServer - entrant Calls(_Total)\- appels du contournement de média Active</span><span class="sxs-lookup"><span data-stu-id="51303-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="51303-170">LS:MediationServer - Calls(_Total) sortants\- appels du contournement de média Active</span><span class="sxs-lookup"><span data-stu-id="51303-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="51303-171">Vous devez entrer manuellement les compteurs de performance dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="51303-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="51303-172">Ils n’apparaissent pas en tant qu’options dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="51303-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="51303-173">Pour plus d’informations, voir les [sources de données de performances Windows et Linux dans journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="51303-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="51303-174">Créer des alertes</span><span class="sxs-lookup"><span data-stu-id="51303-174">Create alerts</span></span>

<span data-ttu-id="51303-175">Il existe deux types d’alertes dans OMS : nombre de résultats alertes et mesure métrique.</span><span class="sxs-lookup"><span data-stu-id="51303-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="51303-176">Pour plus d’informations sur la création des alertes, voir [utilisation des règles d’alerte dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="51303-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="51303-177">Lors de la création des alertes, tenez compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="51303-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="51303-178">Assurez-vous que l’alerte est une alerte nombre de résultats, qui est la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="51303-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="51303-179">Les requêtes de démo nécessitent que « Nombre de résultats » est défini sur « supérieur à 0 ».</span><span class="sxs-lookup"><span data-stu-id="51303-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="51303-180">Il est recommandé de définir la fenêtre délai et fréquence de l’alerte à 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="51303-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="51303-181">Il est recommandé que vous n’activez pas « supprimer « alertes pour les alertes de démonstration.</span><span class="sxs-lookup"><span data-stu-id="51303-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="51303-182">Pour les scénarios d’alerte par défaut, Microsoft recommande la création d’une paire d’alertes : alerte d’une erreur et une rétablir alerte.</span><span class="sxs-lookup"><span data-stu-id="51303-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="51303-183">Pour le message d’erreur, sélectionnez le niveau de gravité critique ; la mise en garde reset, sélectionnez le niveau de gravité information.</span><span class="sxs-lookup"><span data-stu-id="51303-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="51303-184">Les sections suivantes décrivent comment créer des alertes de l’échantillon.</span><span class="sxs-lookup"><span data-stu-id="51303-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="51303-185">**Créer une paire de l’alerte : « RTCMEDSRV ne fonctionne pas dans les serveurs de médiation » et « RTCMEDSRV est en cours d’exécution sur les serveurs de médiation dans »**</span><span class="sxs-lookup"><span data-stu-id="51303-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="51303-186">Pour créer cette paire de l’alerte :</span><span class="sxs-lookup"><span data-stu-id="51303-186">To create this alert pair:</span></span>

- <span data-ttu-id="51303-187">La requête pour le message d’erreur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="51303-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="51303-188">La requête utilise le filtre d’ordinateur *où ordinateur contient « MediationServer »* .</span><span class="sxs-lookup"><span data-stu-id="51303-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="51303-189">Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».</span><span class="sxs-lookup"><span data-stu-id="51303-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="51303-190">Vous souhaiteriez remplacer le filtre par le filtre de votre propre ordinateur ou simplement le supprimer.</span><span class="sxs-lookup"><span data-stu-id="51303-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="51303-191">Vous pouvez créer des filtres de chaîne complexe sans les expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="51303-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="51303-192">Pour plus d’informations, voir [opérateurs de chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="51303-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="51303-193">Vous pouvez également choisir d’utiliser des expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="51303-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="51303-194">En outre, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche à l’aide de ce groupe comme filtre de votre ordinateur dans votre requête de l’alerte.</span><span class="sxs-lookup"><span data-stu-id="51303-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="51303-195">Pour plus d’informations, voir [groupes d’ordinateurs dans le journal Analytique connecter des recherches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="51303-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="51303-196">Pour chaque ordinateur, l’erreur de la requête sera obtenir le dernier journal des événements pour les deux le démarrage du service RTCMEDSRV et arrêt de service.</span><span class="sxs-lookup"><span data-stu-id="51303-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="51303-197">Il renverra une session si le dernier événement est l’événement stop service ; Il ne renvoie rien si le dernier événement est l’événement de démarrage du service.</span><span class="sxs-lookup"><span data-stu-id="51303-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="51303-198">En résumé, la requête retourne une liste de serveurs dont RTCMEDSRV est arrêté dans la fenêtre de temps.</span><span class="sxs-lookup"><span data-stu-id="51303-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="51303-199">La requête de l’alerte de réinitialisation est la suivante :</span><span class="sxs-lookup"><span data-stu-id="51303-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="51303-200">La requête de réinitialisation effectue exactement la chose contraire à celui de la requête de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51303-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="51303-201">Pour chaque ordinateur, elle renvoie 1 si le dernier événement est le service démarre l’événement ; Il ne renvoie rien si le dernier événement est l’événement d’arrêt de service.</span><span class="sxs-lookup"><span data-stu-id="51303-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="51303-202">**Créer une paire de l’alerte : « trop grand nombre d’appels simultané sur les serveurs de médiation » et « appels simultanés rattachées à une charge normale »**</span><span class="sxs-lookup"><span data-stu-id="51303-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="51303-203">Pour créer cette alerte :</span><span class="sxs-lookup"><span data-stu-id="51303-203">To create this alert:</span></span>

- <span data-ttu-id="51303-204">La requête pour le message d’erreur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="51303-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="51303-205">Pour chaque ordinateur, la requête obtiendra dernières compteurs d’appels entrants et les appels sortants et somme ces deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="51303-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="51303-206">Il renverra une session si la valeur de la somme est supérieure à 500 ; Il ne renvoie rien si elle n’est pas.</span><span class="sxs-lookup"><span data-stu-id="51303-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="51303-207">En résumé, la requête retourne une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.</span><span class="sxs-lookup"><span data-stu-id="51303-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="51303-208">La requête de l’alerte de réinitialisation est la suivante :</span><span class="sxs-lookup"><span data-stu-id="51303-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="51303-209">La requête de réinitialisation effectue exactement la chose contraire à celui de la requête de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="51303-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="51303-210">Pour chaque ordinateur, la requête obtiendra dernières compteurs d’appels entrants et les appels sortants et somme ces deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="51303-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="51303-211">Renvoie un seul journal si la valeur de la somme est inférieur à 500 ; elle renvoie nothing dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="51303-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="51303-212">**Créer une alerte : « utilisation de l’UC \> 90 ou RTCMEDIARELAY arrêté dans les serveurs « alerte**</span><span class="sxs-lookup"><span data-stu-id="51303-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="51303-213">Pour créer cette alerte, la requête est la suivante :</span><span class="sxs-lookup"><span data-stu-id="51303-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="51303-214">La requête obtiendra tous les compteurs d’utilisation de processeur et événement arrêt du service de tous les ordinateurs et renvoyer un journal si l’utilisation du processeur est supérieure à 90 % ou le service est déjà arrêté.</span><span class="sxs-lookup"><span data-stu-id="51303-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="51303-215">Analyser les alertes dans le référentiel de journal Analytique</span><span class="sxs-lookup"><span data-stu-id="51303-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="51303-216">Pour analyser les alertes dans le référentiel, utilisez la solution de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="51303-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="51303-217">Pour plus d’informations, voir la [solution de gestion de l’alerte dans la Suite Gestion des opérations (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="51303-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="51303-218">Jeu de surveillance minimum recommandé</span><span class="sxs-lookup"><span data-stu-id="51303-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="51303-219">Pour identifier des problèmes avec les compteurs de performance et les journaux des événements :</span><span class="sxs-lookup"><span data-stu-id="51303-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="51303-220">**Journaux des événements.**</span><span class="sxs-lookup"><span data-stu-id="51303-220">**Event logs.**</span></span> <span data-ttu-id="51303-221">Pour résoudre un problème, il doit être une paire d’événements, avec un ensemble d’événements pour indiquer qu'un élément est incorrect, tandis que l’autre indique que tout est bien.</span><span class="sxs-lookup"><span data-stu-id="51303-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="51303-222">Pour une période donnée, il est le dernier événement enregistré qui indique si un élément est explosion pour cette période.</span><span class="sxs-lookup"><span data-stu-id="51303-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="51303-223">**Compteurs de performance.**</span><span class="sxs-lookup"><span data-stu-id="51303-223">**Performance Counters.**</span></span> <span data-ttu-id="51303-224">Il doit exister un seuil pour les compteurs surveillés.</span><span class="sxs-lookup"><span data-stu-id="51303-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="51303-225">Le tableau suivant répertorie les services que Microsoft vous recommande de surveillance en répertoriant les ID d’événement arrêt et démarrage :</span><span class="sxs-lookup"><span data-stu-id="51303-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="51303-226">Nom de service</span><span class="sxs-lookup"><span data-stu-id="51303-226">Service Name</span></span>  <br/> |<span data-ttu-id="51303-227">Rôle de serveur cible</span><span class="sxs-lookup"><span data-stu-id="51303-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="51303-228">Arrêter l’ID d’événement</span><span class="sxs-lookup"><span data-stu-id="51303-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="51303-229">ID d’événement Démarrer</span><span class="sxs-lookup"><span data-stu-id="51303-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="51303-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="51303-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="51303-231">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="51303-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="51303-232">25003</span><span class="sxs-lookup"><span data-stu-id="51303-232">25003</span></span>  <br/> |<span data-ttu-id="51303-233">25002</span><span class="sxs-lookup"><span data-stu-id="51303-233">25002</span></span>  <br/> |
|<span data-ttu-id="51303-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="51303-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="51303-235">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="51303-235">Edge Server</span></span>  <br/> |<span data-ttu-id="51303-236">12289</span><span class="sxs-lookup"><span data-stu-id="51303-236">12289</span></span>  <br/> |<span data-ttu-id="51303-237">12288</span><span class="sxs-lookup"><span data-stu-id="51303-237">12288</span></span>  <br/> |
|<span data-ttu-id="51303-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="51303-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="51303-239">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="51303-239">Edge Server</span></span>  <br/> |<span data-ttu-id="51303-240">19003</span><span class="sxs-lookup"><span data-stu-id="51303-240">19003</span></span>  <br/> |<span data-ttu-id="51303-241">19002</span><span class="sxs-lookup"><span data-stu-id="51303-241">19002</span></span>  <br/> |
|<span data-ttu-id="51303-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="51303-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="51303-243">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="51303-243">Edge Server</span></span>  <br/> |<span data-ttu-id="51303-244">22003</span><span class="sxs-lookup"><span data-stu-id="51303-244">22003</span></span>  <br/> |<span data-ttu-id="51303-245">22002</span><span class="sxs-lookup"><span data-stu-id="51303-245">22002</span></span>  <br/> |

<span data-ttu-id="51303-246">Le tableau suivant répertorie les problèmes de réseau Microsoft vous recommande de surveillance :</span><span class="sxs-lookup"><span data-stu-id="51303-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="51303-247">Nom de l’analyseur</span><span class="sxs-lookup"><span data-stu-id="51303-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="51303-248">Rôle de serveur cible</span><span class="sxs-lookup"><span data-stu-id="51303-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="51303-249">Expression d’ID d’événement de réussite</span><span class="sxs-lookup"><span data-stu-id="51303-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="51303-250">Expression de l’ID d’événement d’erreur</span><span class="sxs-lookup"><span data-stu-id="51303-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="51303-251">Exemple de défaillance</span><span class="sxs-lookup"><span data-stu-id="51303-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="51303-252">Échec de connectivité de passerelle du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="51303-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="51303-253">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="51303-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="51303-254">25062</span><span class="sxs-lookup"><span data-stu-id="51303-254">25062</span></span>                              |                                  | <span data-ttu-id="51303-255">25002</span><span class="sxs-lookup"><span data-stu-id="51303-255">25002</span></span>  <br/>           |
| <span data-ttu-id="51303-256">Serveur de médiation vers passerelle Échec de fin d’appel</span><span class="sxs-lookup"><span data-stu-id="51303-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="51303-257">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="51303-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="51303-258">25064</span><span class="sxs-lookup"><span data-stu-id="51303-258">25064</span></span>                              |                                  | <span data-ttu-id="51303-259">25002</span><span class="sxs-lookup"><span data-stu-id="51303-259">25002</span></span>  <br/>           |
| <span data-ttu-id="51303-260">Problèmes de réseau</span><span class="sxs-lookup"><span data-stu-id="51303-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="51303-261">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="51303-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="51303-262">14353</span><span class="sxs-lookup"><span data-stu-id="51303-262">14353</span></span>                              |                                  | <span data-ttu-id="51303-263">12288</span><span class="sxs-lookup"><span data-stu-id="51303-263">12288</span></span>  <br/>           |

<span data-ttu-id="51303-264">Voici les compteurs de la capacité d’appel qui doivent être surveillées.</span><span class="sxs-lookup"><span data-stu-id="51303-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="51303-265">Ces numéros doit être inférieure 500 pour standard edition de nuage connecteur ; inférieur à 50 pour édition minimale nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="51303-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="51303-266">LS:MediationServer - entrant Calls(_Total)\- en cours</span><span class="sxs-lookup"><span data-stu-id="51303-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="51303-267">LS:MediationServer - Calls(_Total) sortants\- en cours</span><span class="sxs-lookup"><span data-stu-id="51303-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="51303-268">LS:MediationServer - entrant Calls(_Total)\- appels du contournement de média Active</span><span class="sxs-lookup"><span data-stu-id="51303-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="51303-269">LS:MediationServer - Calls(_Total) sortants\- appels du contournement de média Active</span><span class="sxs-lookup"><span data-stu-id="51303-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="51303-270">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51303-270">See also</span></span>

<span data-ttu-id="51303-271">Pour plus d’informations sur l’utilisation des OMS, voir :</span><span class="sxs-lookup"><span data-stu-id="51303-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="51303-272">Rechercher des données à l’aide de recherches de journal dans le journal Analytique</span><span class="sxs-lookup"><span data-stu-id="51303-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="51303-273">Référence du langage Analytique journal Azure</span><span class="sxs-lookup"><span data-stu-id="51303-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="51303-274">Présentation des alertes dans le journal Analytique</span><span class="sxs-lookup"><span data-stu-id="51303-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="51303-275">Connecter des ordinateurs Windows au service journal Analytique dans Azure</span><span class="sxs-lookup"><span data-stu-id="51303-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


