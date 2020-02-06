---
title: Surveiller Cloud Connector avec Operations Management Suite (OMS)
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Pour plus d’informations sur la façon de surveiller la version 2,1 du Cloud Connector et le déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS), consultez cette rubrique.
ms.openlocfilehash: 1dcac3519624cef898622f915b08b24363453b84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799624"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="f6650-103">Surveiller Cloud Connector avec Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="f6650-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="f6650-104">Pour plus d’informations sur la façon de surveiller la version 2,1 du Cloud Connector et le déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS), consultez cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f6650-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="f6650-105">Vous pouvez désormais surveiller la version 2,1 du Cloud Connector et le déploiement ultérieur à l’aide de Operations Management Suite (OMS), une solution de gestion informatique du Cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f6650-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="f6650-106">L’analyse du journal OMS vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, notamment les machines physiques et virtuelles.</span><span class="sxs-lookup"><span data-stu-id="f6650-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="f6650-107">Pour plus d’informations sur OMS et sur l’analyse du journal, voir [qu’est-ce que la suite de gestion des opérations ?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="f6650-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="f6650-108">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6650-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="f6650-109">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="f6650-109">Prerequisites</span></span>

- <span data-ttu-id="f6650-110">Configurer le Cloud Connector pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="f6650-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="f6650-111">Configurer OMS</span><span class="sxs-lookup"><span data-stu-id="f6650-111">Configure OMS</span></span>

- <span data-ttu-id="f6650-112">Analyser les alertes dans votre référentiel d’analyse du journal</span><span class="sxs-lookup"><span data-stu-id="f6650-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="f6650-113">Ensemble de contrôles recommandés</span><span class="sxs-lookup"><span data-stu-id="f6650-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6650-114">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="f6650-114">Prerequisites</span></span>

<span data-ttu-id="f6650-115">Pour que vous puissiez utiliser OMS pour surveiller le déploiement de votre Cloud Connector, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f6650-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="f6650-116">**Un compte Azure et un espace de travail OMS.**</span><span class="sxs-lookup"><span data-stu-id="f6650-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="f6650-117">Si vous n’avez pas encore de compte Azure, vous devez en créer un pour utiliser l’analyse du journal OMS.</span><span class="sxs-lookup"><span data-stu-id="f6650-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="f6650-118">Pour plus d’informations sur la création d’un compte Azure et la configuration d’un espace de travail OMS, voir [commencer à utiliser un espace de travail d’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="f6650-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="f6650-119">**Cloud Connector version 2,1 ou ultérieure**</span><span class="sxs-lookup"><span data-stu-id="f6650-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="f6650-120">Le **nouveau journal de recherche du journal d’analyse** est requis pour la surveillance du connecteur Cloud.</span><span class="sxs-lookup"><span data-stu-id="f6650-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="f6650-121">Pour plus d’informations, reportez-vous à [mettre à niveau votre espace de travail analyse du journal Azure vers une nouvelle recherche de journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="f6650-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="f6650-122">Configurer le Cloud Connector pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="f6650-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="f6650-123">Vous devez configurer votre environnement sur site Cloud Connector pour qu’il utilise OMS.</span><span class="sxs-lookup"><span data-stu-id="f6650-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="f6650-124">Pour ce faire, vous avez besoin de votre ID d’espace de travail OMS et de votre clé, que vous pouvez trouver en utilisant le portail OMS\>comme suit : Settings--sources connectées-serveurs\> Windows :</span><span class="sxs-lookup"><span data-stu-id="f6650-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Capture d'écran pour Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="f6650-126">La configuration de Cloud Connector pour utiliser OMS dépend de votre scénario :</span><span class="sxs-lookup"><span data-stu-id="f6650-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="f6650-127">**Si vous installez un nouveau matériel de connecteur Cloud ou que vous voulez redéployer un appareil**, procédez comme suit avant d’exécuter l’installation-CcAppliance :</span><span class="sxs-lookup"><span data-stu-id="f6650-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="f6650-128">Dans la section [Common] du fichier CloudConnector. ini, définissez le paramètre OMSEnabled sur true.</span><span class="sxs-lookup"><span data-stu-id="f6650-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="f6650-129">Chaque fois que le Cloud Connector est déployé ou mis à niveau, il essaiera d’installer automatiquement l’agent OMS sur les ordinateurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="f6650-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="f6650-130">Activez cette fonctionnalité pour que l’agent OMS puisse survivre à la mise à jour automatique du Cloud Cloud.</span><span class="sxs-lookup"><span data-stu-id="f6650-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="f6650-131">Pour configurer l’ID et la clé OMS, exécutez Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="f6650-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="f6650-132">**Si vous installez un agent OMS sur un appareil de connecteur Cloud existant**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f6650-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="f6650-133">Dans la section [Common] du fichier CloudConnector. ini, définissez OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="f6650-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="f6650-134">Exécutez Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6650-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="f6650-135">Exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="f6650-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f6650-136">Si les informations d’identification OMSWorkspace n’ont jamais été définies, vous êtes invité à entrer les informations d’identification lorsque vous exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="f6650-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="f6650-137">**Si vous voulez mettre à jour l’ID d’espace de travail OMS ou la clé dans un appareil Cloud sur lequel est déjà installé un agent OMS :**</span><span class="sxs-lookup"><span data-stu-id="f6650-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="f6650-138">Pour configurer l’ID et la clé OMS, exécutez Set-CcCredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="f6650-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="f6650-139">Pour appliquer les mises à jour, exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="f6650-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="f6650-140">**Dans tous les cas, vérifiez que les agents sont connectés comme suit :**</span><span class="sxs-lookup"><span data-stu-id="f6650-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="f6650-141">Dans le portail OMS, accédez à paramètres-\> sources connectées\> -serveurs Windows.</span><span class="sxs-lookup"><span data-stu-id="f6650-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="f6650-142">Une liste des ordinateurs connectés s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f6650-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="f6650-143">Configurer OMS</span><span class="sxs-lookup"><span data-stu-id="f6650-143">Configure OMS</span></span>

<span data-ttu-id="f6650-144">Vous devrez ensuite spécifier votre configuration OMS à l’aide du portail OMS.</span><span class="sxs-lookup"><span data-stu-id="f6650-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="f6650-145">En particulier, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6650-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="f6650-146">Spécifiez les informations relatives aux journaux des événements et aux compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="f6650-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="f6650-147">Créer des alertes.</span><span class="sxs-lookup"><span data-stu-id="f6650-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="f6650-148">Spécifier des informations sur les journaux d’événements et les compteurs de performance</span><span class="sxs-lookup"><span data-stu-id="f6650-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="f6650-149">Dans le portail OMS, vous devez spécifier les informations relatives aux journaux d’événements et aux compteurs de performance comme suit :</span><span class="sxs-lookup"><span data-stu-id="f6650-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="f6650-150">Accédez à paramètres-\>données-\>journaux des événements Windows et ajoutez les journaux des événements pour :</span><span class="sxs-lookup"><span data-stu-id="f6650-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="f6650-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="f6650-151">Lync Server</span></span>

   - <span data-ttu-id="f6650-152">Application</span><span class="sxs-lookup"><span data-stu-id="f6650-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="f6650-153">Vous devez entrer manuellement Lync Server dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f6650-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="f6650-154">Il n’apparaît pas sous la forme d’une option dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f6650-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="f6650-155">Pour plus d’informations, voir [sources de données du journal des événements Windows dans analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="f6650-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="f6650-156">Accédez à paramètres-\>données-\> compteurs de performance Windows et ajouter des compteurs de performance pour :</span><span class="sxs-lookup"><span data-stu-id="f6650-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="f6650-157">**Compteurs de niveau de système d’exploitation**.</span><span class="sxs-lookup"><span data-stu-id="f6650-157">**OS level counters**.</span></span> <span data-ttu-id="f6650-158">Vous pouvez ajouter des compteurs de niveau de système d’exploitation, par exemple une utilisation du processeur, de la mémoire, une utilisation du réseau, ou vous pouvez utiliser des solutions existantes comme la capacité et les performances, le moniteur des performances du réseau sans ajouter de compteurs explicitement.</span><span class="sxs-lookup"><span data-stu-id="f6650-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="f6650-159">Quelle que soit la façon dont vous décidez de les surveiller, Microsoft vous recommande de surveiller ces compteurs du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="f6650-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="f6650-160">**Des compteurs Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="f6650-160">**Skype for Business counters**.</span></span> <span data-ttu-id="f6650-161">Il existe de nombreux compteurs proposés par Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f6650-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="f6650-162">Vous pouvez trouver ces compteurs en vous connectant à un serveur de médiation et en ouvrant le moniteur de performance.</span><span class="sxs-lookup"><span data-stu-id="f6650-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="f6650-163">Ces compteurs commencent par « LS : ».</span><span class="sxs-lookup"><span data-stu-id="f6650-163">These counters start with "LS:".</span></span> <span data-ttu-id="f6650-164">Microsoft vous recommande de commencer avec les compteurs de capacité suivants au minimum et d’ajouter d’autres personnes qui vous intéressent :</span><span class="sxs-lookup"><span data-stu-id="f6650-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="f6650-165">Nombre total d’appels actifs :</span><span class="sxs-lookup"><span data-stu-id="f6650-165">Total active calls:</span></span>

   - <span data-ttu-id="f6650-166">LS : MediationServer-appels entrants (_Total)\- actuels</span><span class="sxs-lookup"><span data-stu-id="f6650-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="f6650-167">LS : MediationServer-les appels sortants (_Total\- ) actuels</span><span class="sxs-lookup"><span data-stu-id="f6650-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="f6650-168">Nombre total d’appels multimédias actifs :</span><span class="sxs-lookup"><span data-stu-id="f6650-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="f6650-169">LS : appels entrants et MediationServer (_Total)\-</span><span class="sxs-lookup"><span data-stu-id="f6650-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="f6650-170">LS : MediationServer-appels sortants (_Total)\- appels multimédias actifs</span><span class="sxs-lookup"><span data-stu-id="f6650-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="f6650-171">Vous devez entrer manuellement les compteurs de performance dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f6650-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="f6650-172">Elles n’apparaissent pas sous la forme d’options dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f6650-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="f6650-173">Pour plus d’informations, voir [sources de données de performances Windows et Linux dans l’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="f6650-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="f6650-174">Créer des alertes</span><span class="sxs-lookup"><span data-stu-id="f6650-174">Create alerts</span></span>

<span data-ttu-id="f6650-175">Il existe deux types d’alertes dans OMS : le nombre d’alertes de résultats et d’alertes de mesure métrique.</span><span class="sxs-lookup"><span data-stu-id="f6650-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="f6650-176">Pour plus d’informations sur la création d’alertes, voir [utilisation des règles d’alerte dans l’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="f6650-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="f6650-177">Lorsque vous créez des alertes, vous devez tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f6650-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="f6650-178">Assurez-vous que l’alerte est une alerte de type nombre de résultats (sélection par défaut).</span><span class="sxs-lookup"><span data-stu-id="f6650-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="f6650-179">Les requêtes de démonstration requièrent que « nombre de résultats » soit défini sur « supérieur à 0 ».</span><span class="sxs-lookup"><span data-stu-id="f6650-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="f6650-180">Nous vous conseillons de définir la fenêtre temps et la fréquence d’alerte sur 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="f6650-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="f6650-181">Nous vous recommandons de ne pas activer « supprimer les alertes » pour les alertes de démonstration.</span><span class="sxs-lookup"><span data-stu-id="f6650-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="f6650-182">Pour des scénarios d’alerte standard, Microsoft recommande la création d’une paire d’alertes : une alerte d’erreur et une alerte de réinitialisation unique.</span><span class="sxs-lookup"><span data-stu-id="f6650-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="f6650-183">Pour l’alerte d’erreur, sélectionnez niveau de gravité critique ; pour l’alerte de réinitialisation, sélectionnez information sur le niveau de gravité.</span><span class="sxs-lookup"><span data-stu-id="f6650-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="f6650-184">Les sections suivantes décrivent comment créer des exemples d’alertes.</span><span class="sxs-lookup"><span data-stu-id="f6650-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="f6650-185">**Créer une paire d’alertes : « RTCMEDSRV ne s’exécute pas sur les serveurs de médiation » et « RTCMEDSRV fonctionne de nouveau sur les serveurs de médiation »**</span><span class="sxs-lookup"><span data-stu-id="f6650-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="f6650-186">Pour créer cette paire d’alertes :</span><span class="sxs-lookup"><span data-stu-id="f6650-186">To create this alert pair:</span></span>

- <span data-ttu-id="f6650-187">La requête d’erreur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="f6650-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="f6650-188">La requête utilise le filtre d’ordinateur sur *lequel ordinateur contient « MediationServer »* .</span><span class="sxs-lookup"><span data-stu-id="f6650-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="f6650-189">Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».</span><span class="sxs-lookup"><span data-stu-id="f6650-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="f6650-190">Vous devez remplacer le filtre par votre propre filtre d’ordinateur ou simplement le supprimer.</span><span class="sxs-lookup"><span data-stu-id="f6650-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="f6650-191">Vous pouvez créer des filtres de chaîne complexes sans expression régulière.</span><span class="sxs-lookup"><span data-stu-id="f6650-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="f6650-192">Pour plus d’informations, consultez la section [opérateurs de chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="f6650-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="f6650-193">Vous pouvez également choisir d’utiliser des expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="f6650-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="f6650-194">Par ailleurs, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche et en utilisant ce groupe comme filtre d’ordinateur dans votre requête d’alerte.</span><span class="sxs-lookup"><span data-stu-id="f6650-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="f6650-195">Pour plus d’informations, voir [groupes d’ordinateurs dans les recherches dans le journal d’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="f6650-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="f6650-196">Pour chaque ordinateur, la requête d’erreur reçoit le dernier journal des événements pour le démarrage et le service du service RTCMEDSRV.</span><span class="sxs-lookup"><span data-stu-id="f6650-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="f6650-197">Il renverra un journal si le dernier événement est l’événement d’arrêt du service ; elle ne renvoie aucune valeur si le dernier événement est l’événement de début de service.</span><span class="sxs-lookup"><span data-stu-id="f6650-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="f6650-198">En résumé, la requête renvoie une liste de serveurs pour lesquels RTCMEDSRV est arrêté dans la fenêtre délai.</span><span class="sxs-lookup"><span data-stu-id="f6650-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="f6650-199">La requête de réinitialisation est la suivante :</span><span class="sxs-lookup"><span data-stu-id="f6650-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="f6650-200">La requête Reset effectue exactement l’opération inverse de la requête d’erreur.</span><span class="sxs-lookup"><span data-stu-id="f6650-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="f6650-201">S’il s’agit d’un ordinateur, l’événement de début de service sera renvoyé. elle ne renvoie aucune valeur si le dernier événement est l’événement d’arrêt de service.</span><span class="sxs-lookup"><span data-stu-id="f6650-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="f6650-202">**Créer une paire d’alertes : « un trop grand nombre d’appels simultanés dans les serveurs de médiation » et « les appels simultanés sont ramenés au chargement normal »**</span><span class="sxs-lookup"><span data-stu-id="f6650-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="f6650-203">Pour créer cette alerte :</span><span class="sxs-lookup"><span data-stu-id="f6650-203">To create this alert:</span></span>

- <span data-ttu-id="f6650-204">La requête d’erreur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="f6650-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="f6650-205">Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et additionner ces deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="f6650-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="f6650-206">Il renverra un journal si la valeur de somme dépasse 500 ; Si ce n’est pas le cas, elle renvoie la valeur Nothing.</span><span class="sxs-lookup"><span data-stu-id="f6650-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="f6650-207">En résumé, la requête renvoie une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre délai.</span><span class="sxs-lookup"><span data-stu-id="f6650-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="f6650-208">La requête de réinitialisation est la suivante :</span><span class="sxs-lookup"><span data-stu-id="f6650-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="f6650-209">La requête Reset effectue exactement l’opération inverse de la requête d’erreur.</span><span class="sxs-lookup"><span data-stu-id="f6650-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="f6650-210">Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et additionner ces deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="f6650-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="f6650-211">Il renverra un journal si la valeur somme est inférieure à 500 ; elle ne renvoie aucun résultat.</span><span class="sxs-lookup"><span data-stu-id="f6650-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="f6650-212">**Créer une alerte : « utilisation \> processeur 90 ou RTCMEDIARELAY arrêtées dans les serveurs »**</span><span class="sxs-lookup"><span data-stu-id="f6650-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="f6650-213">Pour créer cette alerte, la requête est la suivante :</span><span class="sxs-lookup"><span data-stu-id="f6650-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="f6650-214">La requête obtiendra tous les compteurs d’utilisation du processeur et un événement d’arrêt de service de tous les ordinateurs et renverra un journal si l’utilisation du processeur dépasse 90% ou si le service est arrêté.</span><span class="sxs-lookup"><span data-stu-id="f6650-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="f6650-215">Analyser les alertes dans votre référentiel d’analyse du journal</span><span class="sxs-lookup"><span data-stu-id="f6650-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="f6650-216">Pour analyser les alertes dans votre référentiel, utilisez la solution de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="f6650-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="f6650-217">Pour plus d’informations, reportez-vous [à solution de gestion des alertes dans Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="f6650-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="f6650-218">Ensemble de contrôles minimaux recommandés</span><span class="sxs-lookup"><span data-stu-id="f6650-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="f6650-219">Pour identifier les problèmes liés aux journaux d’événements et aux compteurs de performance :</span><span class="sxs-lookup"><span data-stu-id="f6650-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="f6650-220">**Journaux des événements.**</span><span class="sxs-lookup"><span data-stu-id="f6650-220">**Event logs.**</span></span> <span data-ttu-id="f6650-221">En cas de problème, il devrait y avoir une paire d’événements, avec un ensemble d’événements indiquant qu’un problème survient, tandis que l’autre indique que tout est bien.</span><span class="sxs-lookup"><span data-stu-id="f6650-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="f6650-222">Pour une période donnée, il s’agit du dernier événement enregistré qui indique s’il s’agit d’amiss pour cette période.</span><span class="sxs-lookup"><span data-stu-id="f6650-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="f6650-223">**Compteurs de performance.**</span><span class="sxs-lookup"><span data-stu-id="f6650-223">**Performance Counters.**</span></span> <span data-ttu-id="f6650-224">Le seuil doit être défini pour les compteurs surveillés.</span><span class="sxs-lookup"><span data-stu-id="f6650-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="f6650-225">Le tableau suivant répertorie les services que Microsoft recommande de surveiller en répertoriant les ID d’événement stop et Start :</span><span class="sxs-lookup"><span data-stu-id="f6650-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="f6650-226">Nom du service</span><span class="sxs-lookup"><span data-stu-id="f6650-226">Service Name</span></span>  <br/> |<span data-ttu-id="f6650-227">Rôle du serveur cible</span><span class="sxs-lookup"><span data-stu-id="f6650-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="f6650-228">Arrêter l’ID d’événement</span><span class="sxs-lookup"><span data-stu-id="f6650-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="f6650-229">ID d’événement de début</span><span class="sxs-lookup"><span data-stu-id="f6650-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6650-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="f6650-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="f6650-231">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f6650-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="f6650-232">25003</span><span class="sxs-lookup"><span data-stu-id="f6650-232">25003</span></span>  <br/> |<span data-ttu-id="f6650-233">25002</span><span class="sxs-lookup"><span data-stu-id="f6650-233">25002</span></span>  <br/> |
|<span data-ttu-id="f6650-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="f6650-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="f6650-235">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="f6650-235">Edge Server</span></span>  <br/> |<span data-ttu-id="f6650-236">12289</span><span class="sxs-lookup"><span data-stu-id="f6650-236">12289</span></span>  <br/> |<span data-ttu-id="f6650-237">12288</span><span class="sxs-lookup"><span data-stu-id="f6650-237">12288</span></span>  <br/> |
|<span data-ttu-id="f6650-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="f6650-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="f6650-239">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="f6650-239">Edge Server</span></span>  <br/> |<span data-ttu-id="f6650-240">19003</span><span class="sxs-lookup"><span data-stu-id="f6650-240">19003</span></span>  <br/> |<span data-ttu-id="f6650-241">19002</span><span class="sxs-lookup"><span data-stu-id="f6650-241">19002</span></span>  <br/> |
|<span data-ttu-id="f6650-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="f6650-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="f6650-243">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="f6650-243">Edge Server</span></span>  <br/> |<span data-ttu-id="f6650-244">22003</span><span class="sxs-lookup"><span data-stu-id="f6650-244">22003</span></span>  <br/> |<span data-ttu-id="f6650-245">22002</span><span class="sxs-lookup"><span data-stu-id="f6650-245">22002</span></span>  <br/> |

<span data-ttu-id="f6650-246">Le tableau suivant répertorie les problèmes de réseau que Microsoft recommande de surveiller :</span><span class="sxs-lookup"><span data-stu-id="f6650-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="f6650-247">Nom du moniteur</span><span class="sxs-lookup"><span data-stu-id="f6650-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="f6650-248">Rôle du serveur cible</span><span class="sxs-lookup"><span data-stu-id="f6650-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="f6650-249">Expression d’ID d’événement Success</span><span class="sxs-lookup"><span data-stu-id="f6650-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="f6650-250">Expression d’ID d’événement d’erreur</span><span class="sxs-lookup"><span data-stu-id="f6650-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="f6650-251">Exemple d’échec</span><span class="sxs-lookup"><span data-stu-id="f6650-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="f6650-252">Échec de la connectivité du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f6650-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="f6650-253">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f6650-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="f6650-254">25062</span><span class="sxs-lookup"><span data-stu-id="f6650-254">25062</span></span>                              |                                  | <span data-ttu-id="f6650-255">25002</span><span class="sxs-lookup"><span data-stu-id="f6650-255">25002</span></span>  <br/>           |
| <span data-ttu-id="f6650-256">Serveur de médiation-échec de la fin de l’appel de la passerelle</span><span class="sxs-lookup"><span data-stu-id="f6650-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="f6650-257">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f6650-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="f6650-258">25064</span><span class="sxs-lookup"><span data-stu-id="f6650-258">25064</span></span>                              |                                  | <span data-ttu-id="f6650-259">25002</span><span class="sxs-lookup"><span data-stu-id="f6650-259">25002</span></span>  <br/>           |
| <span data-ttu-id="f6650-260">Problèmes réseau critiques</span><span class="sxs-lookup"><span data-stu-id="f6650-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="f6650-261">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="f6650-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="f6650-262">14353</span><span class="sxs-lookup"><span data-stu-id="f6650-262">14353</span></span>                              |                                  | <span data-ttu-id="f6650-263">12288</span><span class="sxs-lookup"><span data-stu-id="f6650-263">12288</span></span>  <br/>           |

<span data-ttu-id="f6650-264">La liste suivante répertorie les compteurs de capacités d’appel qui doivent être analysés.</span><span class="sxs-lookup"><span data-stu-id="f6650-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="f6650-265">Ces nombres doivent avoir moins de 500 pour le Cloud Connector Standard Edition ; inférieur à 50 pour le Cloud Connector édition minimum.</span><span class="sxs-lookup"><span data-stu-id="f6650-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="f6650-266">LS : MediationServer-appels entrants (_Total)\- actuels</span><span class="sxs-lookup"><span data-stu-id="f6650-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="f6650-267">LS : MediationServer-les appels sortants (_Total\- ) actuels</span><span class="sxs-lookup"><span data-stu-id="f6650-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="f6650-268">LS : appels entrants et MediationServer (_Total)\-</span><span class="sxs-lookup"><span data-stu-id="f6650-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="f6650-269">LS : MediationServer-appels sortants (_Total)\- appels multimédias actifs</span><span class="sxs-lookup"><span data-stu-id="f6650-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="f6650-270">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6650-270">See also</span></span>

<span data-ttu-id="f6650-271">Pour plus d’informations sur l’utilisation d’OMS, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6650-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="f6650-272">Rechercher des données à l’aide de recherches de journaux dans l’analyse du journal</span><span class="sxs-lookup"><span data-stu-id="f6650-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="f6650-273">Informations de référence sur le langage d’analyse du journal Azure</span><span class="sxs-lookup"><span data-stu-id="f6650-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="f6650-274">Présentation des alertes dans l’analyse du journal</span><span class="sxs-lookup"><span data-stu-id="f6650-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="f6650-275">Connecter des ordinateurs Windows au service d’analyse du journal dans Azure</span><span class="sxs-lookup"><span data-stu-id="f6650-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


