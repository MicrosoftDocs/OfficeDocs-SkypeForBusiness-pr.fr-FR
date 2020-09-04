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
description: Consultez cette rubrique pour découvrir comment surveiller votre déploiement de Cloud Connector version 2,1 et versions ultérieures à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359090"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="14512-103">Surveiller Cloud Connector avec Operations Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="14512-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="14512-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="14512-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="14512-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="14512-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="14512-106">Consultez cette rubrique pour découvrir comment surveiller votre déploiement de Cloud Connector version 2,1 et versions ultérieures à l’aide de Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="14512-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="14512-107">Vous pouvez maintenant surveiller votre déploiement de Cloud Connector version 2,1 et versions ultérieures à l’aide d’Operations Management Suite (OMS), une solution de gestion informatique en nuage Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14512-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="14512-108">L’analyse des journaux OMS vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, y compris les machines physiques et virtuelles.</span><span class="sxs-lookup"><span data-stu-id="14512-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="14512-109">Pour plus d’informations sur OMS et sur l’analyse des journaux, voir [qu’est-ce que Operations Management Suite (OMS) ?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="14512-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="14512-110">Cette rubrique comprend les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="14512-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="14512-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="14512-111">Prerequisites</span></span>

- <span data-ttu-id="14512-112">Configurer Cloud Connector pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="14512-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="14512-113">Configurer OMS</span><span class="sxs-lookup"><span data-stu-id="14512-113">Configure OMS</span></span>

- <span data-ttu-id="14512-114">Analyser les alertes dans votre référentiel d’analyse des journaux</span><span class="sxs-lookup"><span data-stu-id="14512-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="14512-115">Ensemble de surveillance recommandé</span><span class="sxs-lookup"><span data-stu-id="14512-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14512-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="14512-116">Prerequisites</span></span>

<span data-ttu-id="14512-117">Avant de pouvoir utiliser OMS pour surveiller votre déploiement de Cloud Connector, vous aurez besoin des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="14512-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="14512-118">**Un compte Azure et un espace de travail OMS.**</span><span class="sxs-lookup"><span data-stu-id="14512-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="14512-119">Si vous n’avez pas encore de compte Azure, vous devez en créer un pour utiliser l’analyse de journal OMS.</span><span class="sxs-lookup"><span data-stu-id="14512-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="14512-120">Pour plus d’informations sur la création d’un compte Azure et la configuration d’un espace de travail OMS, voir [Get Started with a log Analytics Workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="14512-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="14512-121">**Cloud Connector version 2,1 ou ultérieure**</span><span class="sxs-lookup"><span data-stu-id="14512-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="14512-122">**Log Analytics New log Search** est nécessaire pour la surveillance de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="14512-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="14512-123">Pour plus d’informations, consultez [la rubrique mettre à niveau votre espace de travail d’analyse Azure log Analytics vers une nouvelle recherche de journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="14512-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="14512-124">Configurer Cloud Connector pour utiliser OMS</span><span class="sxs-lookup"><span data-stu-id="14512-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="14512-125">Vous devez configurer votre environnement Cloud Connector sur site pour qu’il utilise OMS.</span><span class="sxs-lookup"><span data-stu-id="14512-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="14512-126">Pour ce faire, vous aurez besoin de votre ID d’espace de travail OMS et de votre clé, que vous pouvez trouver à l’aide du portail OMS comme suit : Settings-- \> sources connectées-- \> serveurs Windows :</span><span class="sxs-lookup"><span data-stu-id="14512-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Capture d’écran pour le Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="14512-128">La configuration de Cloud Connector pour l’utilisation d’OMS dépend de votre scénario :</span><span class="sxs-lookup"><span data-stu-id="14512-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="14512-129">**Si vous installez une nouvelle appliance Cloud Connector ou si vous souhaitez redéployer une appliance**, procédez comme suit avant d’exécuter Install-applet ccappliance :</span><span class="sxs-lookup"><span data-stu-id="14512-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="14512-130">Dans la section fichier de CloudConnector.ini [Common], définissez le paramètre OMSEnabled sur true.</span><span class="sxs-lookup"><span data-stu-id="14512-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="14512-131">Chaque fois que Cloud Connector est déployé ou mis à niveau, il essaiera d’installer l’agent OMS automatiquement sur les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="14512-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="14512-132">Activez cette fonctionnalité afin que l’agent OMS puisse survivre à la mise à jour automatique de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="14512-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="14512-133">Pour configurer l’ID et la clé OMS, exécutez Set-applet cccredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="14512-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="14512-134">**Si vous installez un agent OMS sur une appliance Cloud Connector existante**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="14512-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="14512-135">Dans la section fichier de CloudConnector.ini [Common], définissez OMSEnabled = true.</span><span class="sxs-lookup"><span data-stu-id="14512-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="14512-136">Exécutez Import-CcConfiguration.</span><span class="sxs-lookup"><span data-stu-id="14512-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="14512-137">Exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="14512-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="14512-138">Si les informations d’identification OMSWorkspace n’ont jamais été définies, vous êtes invité à entrer les informations d’identification lorsque vous exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="14512-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="14512-139">**Si vous souhaitez mettre à jour l’ID ou la clé d’espace de travail OMS dans une appliance Cloud Connector qui a déjà installé un agent OMS :**</span><span class="sxs-lookup"><span data-stu-id="14512-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="14512-140">Pour configurer l’ID et la clé OMS, exécutez Set-applet cccredential-AccountType OMSWorkspace.</span><span class="sxs-lookup"><span data-stu-id="14512-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="14512-141">Pour appliquer les mises à jour, exécutez Install-CcOMSAgent.</span><span class="sxs-lookup"><span data-stu-id="14512-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="14512-142">**Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**</span><span class="sxs-lookup"><span data-stu-id="14512-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="14512-143">Dans le portail OMS, accédez à paramètres- \> sources connectées- \> serveurs Windows.</span><span class="sxs-lookup"><span data-stu-id="14512-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="14512-144">La liste des ordinateurs connectés s’affiche.</span><span class="sxs-lookup"><span data-stu-id="14512-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="14512-145">Configurer OMS</span><span class="sxs-lookup"><span data-stu-id="14512-145">Configure OMS</span></span>

<span data-ttu-id="14512-146">Ensuite, vous devrez spécifier votre configuration OMS à l’aide du portail OMS.</span><span class="sxs-lookup"><span data-stu-id="14512-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="14512-147">Plus précisément, vous devez :</span><span class="sxs-lookup"><span data-stu-id="14512-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="14512-148">Spécifiez des informations sur les journaux des événements et les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="14512-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="14512-149">Créer des alertes</span><span class="sxs-lookup"><span data-stu-id="14512-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="14512-150">Spécifier des informations sur les journaux des événements et les compteurs de performance</span><span class="sxs-lookup"><span data-stu-id="14512-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="14512-151">Dans le portail OMS, vous devez spécifier des informations sur les journaux d’événements et les compteurs de performance comme suit :</span><span class="sxs-lookup"><span data-stu-id="14512-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="14512-152">Accédez à paramètres- \> données-données- \> journaux des événements Windows et ajoutez des journaux d’événements pour :</span><span class="sxs-lookup"><span data-stu-id="14512-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="14512-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="14512-153">Lync Server</span></span>

   - <span data-ttu-id="14512-154">Application</span><span class="sxs-lookup"><span data-stu-id="14512-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="14512-155">Vous devez entrer manuellement Lync Server dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="14512-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="14512-156">Elle n’apparaît pas sous la forme d’une option dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="14512-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="14512-157">Pour plus d’informations, consultez la rubrique [sources de données du journal des événements Windows dans analyse des journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="14512-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="14512-158">Accédez à paramètres- \> données-données- \> compteurs de performances Windows et ajoutez des compteurs de performance pour :</span><span class="sxs-lookup"><span data-stu-id="14512-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="14512-159">**Compteurs de niveau de système d’exploitation**.</span><span class="sxs-lookup"><span data-stu-id="14512-159">**OS level counters**.</span></span> <span data-ttu-id="14512-160">Vous pouvez ajouter des compteurs au niveau du système d’exploitation, tels que l’utilisation du processeur, l’utilisation de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes comme la capacité et les performances, l’analyseur de performances réseau sans ajouter de compteurs de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="14512-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="14512-161">Quelle que soit la façon dont vous décidez de les surveiller, Microsoft vous recommande de surveiller ces compteurs de système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="14512-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="14512-162">**Compteurs Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="14512-162">**Skype for Business counters**.</span></span> <span data-ttu-id="14512-163">Il existe de nombreux compteurs fournis par Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="14512-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="14512-164">Vous pouvez trouver ces compteurs en vous connectant à un serveur de médiation et en ouvrant l’analyseur de performances.</span><span class="sxs-lookup"><span data-stu-id="14512-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="14512-165">Ces compteurs commencent par « LS : ».</span><span class="sxs-lookup"><span data-stu-id="14512-165">These counters start with "LS:".</span></span> <span data-ttu-id="14512-166">Microsoft vous recommande de commencer avec les compteurs de capacité suivants au minimum et d’ajouter d’autres personnes intéressantes :</span><span class="sxs-lookup"><span data-stu-id="14512-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="14512-167">Nombre total d’appels actifs :</span><span class="sxs-lookup"><span data-stu-id="14512-167">Total active calls:</span></span>

       - <span data-ttu-id="14512-168">LS : MediationServer-appels entrants (_Total) \- en cours</span><span class="sxs-lookup"><span data-stu-id="14512-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="14512-169">LS : MediationServer-appels sortants (_Total) \- en cours</span><span class="sxs-lookup"><span data-stu-id="14512-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="14512-170">Nombre total d’appels de déviation du trafic multimédia actif :</span><span class="sxs-lookup"><span data-stu-id="14512-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="14512-171">LS : MediationServer-appels entrants (_Total) appels de déviation du trafic \- multimédia actifs</span><span class="sxs-lookup"><span data-stu-id="14512-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="14512-172">LS : MediationServer-appels sortants (_Total) \- appels de contournement de média actifs</span><span class="sxs-lookup"><span data-stu-id="14512-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="14512-173">Vous devez entrer manuellement les compteurs de performance dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="14512-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="14512-174">Elles n’apparaissent pas sous forme d’options dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="14512-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="14512-175">Pour plus d’informations, consultez la rubrique [sources de données de performances Windows et Linux dans analyse des journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="14512-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="14512-176">Créer des alertes</span><span class="sxs-lookup"><span data-stu-id="14512-176">Create alerts</span></span>

<span data-ttu-id="14512-177">Il existe deux types d’alertes dans OMS : nombre d’alertes de résultats et alertes de mesure métrique.</span><span class="sxs-lookup"><span data-stu-id="14512-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="14512-178">Pour plus d’informations sur la création d’alertes, voir [Working with Alert Rules in log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="14512-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="14512-179">Vous devez tenir compte des éléments suivants lors de la création d’alertes :</span><span class="sxs-lookup"><span data-stu-id="14512-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="14512-180">Assurez-vous que l’alerte est une alerte de nombre de résultats, qui est la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="14512-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="14512-181">Les requêtes de démonstration exigent que le paramètre « nombre de résultats » soit défini sur « supérieur à 0 ».</span><span class="sxs-lookup"><span data-stu-id="14512-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="14512-182">Il est recommandé de définir la fréquence des alertes et de la fenêtre de temps sur 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="14512-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="14512-183">Il est recommandé de ne pas activer la suppression des alertes pour les alertes de démonstration.</span><span class="sxs-lookup"><span data-stu-id="14512-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="14512-184">Pour les scénarios d’alerte classiques, Microsoft recommande de créer une paire d’alertes : une alerte d’erreur et une alerte de réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="14512-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="14512-185">Pour l’alerte d’erreur, sélectionnez niveau de gravité critique ; pour l’alerte réinitialiser, sélectionnez niveau de gravité information.</span><span class="sxs-lookup"><span data-stu-id="14512-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="14512-186">Les sections suivantes décrivent comment créer des alertes exemples.</span><span class="sxs-lookup"><span data-stu-id="14512-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="14512-187">**Créer une paire d’alertes : « RTCMEDSRV ne s’exécute pas dans les serveurs de médiation » et « RTCMEDSRV revient en cours d’exécution dans les serveurs de médiation »**</span><span class="sxs-lookup"><span data-stu-id="14512-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="14512-188">Pour créer cette paire d’alertes :</span><span class="sxs-lookup"><span data-stu-id="14512-188">To create this alert pair:</span></span>

- <span data-ttu-id="14512-189">La requête de l’alerte d’erreur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="14512-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="14512-190">La requête utilise le filtre de l’ordinateur  *où l’ordinateur contient « MediationServer »*  .</span><span class="sxs-lookup"><span data-stu-id="14512-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="14512-191">Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».</span><span class="sxs-lookup"><span data-stu-id="14512-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="14512-192">Vous devez remplacer le filtre par votre propre filtre d’ordinateur ou simplement le supprimer.</span><span class="sxs-lookup"><span data-stu-id="14512-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="14512-193">Vous pouvez créer des filtres de chaîne complexes sans expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="14512-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="14512-194">Pour plus d’informations, consultez la rubrique [opérateurs de chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="14512-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="14512-195">Vous pouvez également choisir d’utiliser des expressions régulières.</span><span class="sxs-lookup"><span data-stu-id="14512-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="14512-196">Par ailleurs, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche et en utilisant ce groupe comme filtre de votre ordinateur dans votre requête d’alerte.</span><span class="sxs-lookup"><span data-stu-id="14512-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="14512-197">Pour plus d’informations, consultez la rubrique [groupes d’ordinateurs dans les recherches du journal d’analyse des journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="14512-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="14512-198">Pour chaque ordinateur, la requête d’erreur obtiendra le dernier journal des événements pour le démarrage du service RTCMEDSRV et l’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="14512-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="14512-199">Elle renverra un journal si le dernier événement est l’événement d’arrêt de service ; elle renvoie la valeur Nothing si le dernier événement est l’événement de démarrage du service.</span><span class="sxs-lookup"><span data-stu-id="14512-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="14512-200">En bref, la requête renvoie une liste des serveurs dont la RTCMEDSRV est arrêtée dans la fenêtre de temps.</span><span class="sxs-lookup"><span data-stu-id="14512-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="14512-201">La requête pour l’alerte de réinitialisation est la suivante :</span><span class="sxs-lookup"><span data-stu-id="14512-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="14512-202">La requête de réinitialisation effectue exactement l’autre chose de la requête d’erreur.</span><span class="sxs-lookup"><span data-stu-id="14512-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="14512-203">Pour chaque ordinateur, il renvoie un si le dernier événement est l’événement de démarrage du service ; elle renvoie la valeur Nothing si le dernier événement est l’événement d’arrêt de service.</span><span class="sxs-lookup"><span data-stu-id="14512-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="14512-204">**Créer une paire d’alertes : « trop d’appels simultanés dans les serveurs de médiation » et « appels simultanés vers une charge normale »**</span><span class="sxs-lookup"><span data-stu-id="14512-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="14512-205">Pour créer cette alerte :</span><span class="sxs-lookup"><span data-stu-id="14512-205">To create this alert:</span></span>

- <span data-ttu-id="14512-206">La requête de l’alerte d’erreur est la suivante :</span><span class="sxs-lookup"><span data-stu-id="14512-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="14512-207">Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et totalisez ces deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="14512-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="14512-208">Elle renverra un journal si la valeur de la somme dépasse 500 ; elle renvoie la valeur Nothing si ce n’est pas le cas.</span><span class="sxs-lookup"><span data-stu-id="14512-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="14512-209">En bref, la requête renvoie une liste des serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.</span><span class="sxs-lookup"><span data-stu-id="14512-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="14512-210">La requête pour l’alerte de réinitialisation est la suivante :</span><span class="sxs-lookup"><span data-stu-id="14512-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="14512-211">La requête de réinitialisation effectue exactement l’autre chose de la requête d’erreur.</span><span class="sxs-lookup"><span data-stu-id="14512-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="14512-212">Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et totalisez ces deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="14512-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="14512-213">Elle renverra un journal si la valeur de la somme est inférieure à 500 ; il ne renvoie rien sinon.</span><span class="sxs-lookup"><span data-stu-id="14512-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="14512-214">**Créer une alerte : alerte utilisation de l’UC \> 90 ou RTCMEDIARELAY arrêtée dans les serveurs**</span><span class="sxs-lookup"><span data-stu-id="14512-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="14512-215">Pour créer cette alerte, la requête est la suivante :</span><span class="sxs-lookup"><span data-stu-id="14512-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="14512-216">La requête obtiendra tous les compteurs d’utilisation du processeur et l’événement d’arrêt de service à partir de tous les ordinateurs et renverra un journal si l’utilisation du processeur dépasse 90% ou que le service est toujours arrêté.</span><span class="sxs-lookup"><span data-stu-id="14512-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="14512-217">Analyser les alertes dans votre référentiel d’analyse des journaux</span><span class="sxs-lookup"><span data-stu-id="14512-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="14512-218">Pour analyser les alertes dans votre référentiel, utilisez la solution de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="14512-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="14512-219">Pour plus d’informations, consultez la rubrique [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .</span><span class="sxs-lookup"><span data-stu-id="14512-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="14512-220">Ensemble de surveillance minimal recommandé</span><span class="sxs-lookup"><span data-stu-id="14512-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="14512-221">Pour identifier les problèmes liés aux journaux des événements et aux compteurs de performance :</span><span class="sxs-lookup"><span data-stu-id="14512-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="14512-222">**Journaux des événements.**</span><span class="sxs-lookup"><span data-stu-id="14512-222">**Event logs.**</span></span> <span data-ttu-id="14512-223">Pour tout problème, il doit y avoir une paire Events, avec un ensemble d’événements pour indiquer un élément incorrect, tandis que l’autre indique que tout est bien.</span><span class="sxs-lookup"><span data-stu-id="14512-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="14512-224">Pour une période donnée, c’est le dernier événement enregistré qui indique si un point est amiss pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="14512-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="14512-225">**Compteurs de performance.**</span><span class="sxs-lookup"><span data-stu-id="14512-225">**Performance Counters.**</span></span> <span data-ttu-id="14512-226">Il doit y avoir un seuil pour les compteurs surveillés.</span><span class="sxs-lookup"><span data-stu-id="14512-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="14512-227">Le tableau suivant répertorie les services que Microsoft recommande de surveiller en indiquant les ID d’événement stop et Start :</span><span class="sxs-lookup"><span data-stu-id="14512-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="14512-228">Nom du service</span><span class="sxs-lookup"><span data-stu-id="14512-228">Service Name</span></span>  <br/> |<span data-ttu-id="14512-229">Rôle de serveur cible</span><span class="sxs-lookup"><span data-stu-id="14512-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="14512-230">Arrêter l’ID d’événement</span><span class="sxs-lookup"><span data-stu-id="14512-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="14512-231">ID d’événement de début</span><span class="sxs-lookup"><span data-stu-id="14512-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14512-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="14512-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="14512-233">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="14512-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="14512-234">25003</span><span class="sxs-lookup"><span data-stu-id="14512-234">25003</span></span>  <br/> |<span data-ttu-id="14512-235">25002</span><span class="sxs-lookup"><span data-stu-id="14512-235">25002</span></span>  <br/> |
|<span data-ttu-id="14512-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="14512-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="14512-237">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="14512-237">Edge Server</span></span>  <br/> |<span data-ttu-id="14512-238">12289</span><span class="sxs-lookup"><span data-stu-id="14512-238">12289</span></span>  <br/> |<span data-ttu-id="14512-239">12288</span><span class="sxs-lookup"><span data-stu-id="14512-239">12288</span></span>  <br/> |
|<span data-ttu-id="14512-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="14512-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="14512-241">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="14512-241">Edge Server</span></span>  <br/> |<span data-ttu-id="14512-242">19003</span><span class="sxs-lookup"><span data-stu-id="14512-242">19003</span></span>  <br/> |<span data-ttu-id="14512-243">19002</span><span class="sxs-lookup"><span data-stu-id="14512-243">19002</span></span>  <br/> |
|<span data-ttu-id="14512-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="14512-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="14512-245">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="14512-245">Edge Server</span></span>  <br/> |<span data-ttu-id="14512-246">22003</span><span class="sxs-lookup"><span data-stu-id="14512-246">22003</span></span>  <br/> |<span data-ttu-id="14512-247">22002</span><span class="sxs-lookup"><span data-stu-id="14512-247">22002</span></span>  <br/> |

<span data-ttu-id="14512-248">Le tableau suivant répertorie les problèmes réseau que Microsoft recommande de surveiller :</span><span class="sxs-lookup"><span data-stu-id="14512-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="14512-249">Nom du moniteur</span><span class="sxs-lookup"><span data-stu-id="14512-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="14512-250">Rôle de serveur cible</span><span class="sxs-lookup"><span data-stu-id="14512-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="14512-251">Expression d’ID d’événement de réussite</span><span class="sxs-lookup"><span data-stu-id="14512-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="14512-252">Expression d’ID d’événement d’erreur</span><span class="sxs-lookup"><span data-stu-id="14512-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="14512-253">Exemple d’échec</span><span class="sxs-lookup"><span data-stu-id="14512-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="14512-254">Échec de la connectivité du serveur de médiation à la passerelle</span><span class="sxs-lookup"><span data-stu-id="14512-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="14512-255">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="14512-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="14512-256">25062</span><span class="sxs-lookup"><span data-stu-id="14512-256">25062</span></span>                              |                                  | <span data-ttu-id="14512-257">25002</span><span class="sxs-lookup"><span data-stu-id="14512-257">25002</span></span>  <br/>           |
| <span data-ttu-id="14512-258">Échec de la fin de l’appel de passerelle de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="14512-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="14512-259">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="14512-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="14512-260">25064</span><span class="sxs-lookup"><span data-stu-id="14512-260">25064</span></span>                              |                                  | <span data-ttu-id="14512-261">25002</span><span class="sxs-lookup"><span data-stu-id="14512-261">25002</span></span>  <br/>           |
| <span data-ttu-id="14512-262">Problèmes réseau critiques</span><span class="sxs-lookup"><span data-stu-id="14512-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="14512-263">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="14512-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="14512-264">14353</span><span class="sxs-lookup"><span data-stu-id="14512-264">14353</span></span>                              |                                  | <span data-ttu-id="14512-265">12288</span><span class="sxs-lookup"><span data-stu-id="14512-265">12288</span></span>  <br/>           |

<span data-ttu-id="14512-266">La liste suivante répertorie les compteurs de capacité d’appel qui doivent être surveillés.</span><span class="sxs-lookup"><span data-stu-id="14512-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="14512-267">Ces chiffres doivent être inférieurs à 500 pour Cloud Connector Standard Edition ; inférieur à 50 pour la version minimale de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="14512-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="14512-268">LS : MediationServer-appels entrants (_Total) \- en cours</span><span class="sxs-lookup"><span data-stu-id="14512-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="14512-269">LS : MediationServer-appels sortants (_Total) \- en cours</span><span class="sxs-lookup"><span data-stu-id="14512-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="14512-270">LS : MediationServer-appels entrants (_Total) appels de déviation du trafic \- multimédia actifs</span><span class="sxs-lookup"><span data-stu-id="14512-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="14512-271">LS : MediationServer-appels sortants (_Total) \- appels de contournement de média actifs</span><span class="sxs-lookup"><span data-stu-id="14512-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="14512-272">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14512-272">See also</span></span>

<span data-ttu-id="14512-273">Pour plus d’informations sur l’utilisation d’OMS, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="14512-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="14512-274">Rechercher des données à l’aide de recherches de journal dans l’analyse de journal</span><span class="sxs-lookup"><span data-stu-id="14512-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="14512-275">Référence du langage d’analyse de journalisation Azure</span><span class="sxs-lookup"><span data-stu-id="14512-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="14512-276">Présentation des alertes dans les analyses de journal</span><span class="sxs-lookup"><span data-stu-id="14512-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="14512-277">Connecter des ordinateurs Windows au service Journal Analytics dans Azure</span><span class="sxs-lookup"><span data-stu-id="14512-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


