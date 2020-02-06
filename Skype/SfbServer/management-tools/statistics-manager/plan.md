---
title: Planifier le gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Résumé : cette rubrique vous explique en savoir plus sur le gestionnaire de statistiques pour Skype entreprise Server.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816233"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="6f6b1-103">Planifier le gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f6b1-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="6f6b1-104">**Résumé :** Consultez cette rubrique pour en savoir plus sur le gestionnaire de statistiques pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="6f6b1-105">Le Gestionnaire de statistiques pour Skype Entreprise Server est un outil puissant qui permet de consulter Skype pour l’état et les performances des données entreprise Server en temps réel.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="6f6b1-106">Vous pouvez interroger les données de performances sur des centaines de serveurs à des intervalles de quelques secondes et afficher les résultats instantanément sur le site Web de Gestionnaire de Statistiques.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="6f6b1-107">Vous pouvez utiliser le gestionnaire de statistiques pour identifier les problèmes de performances en cours, afficher les résultats d’un changement planifié pour votre environnement, suivre la résolution des pannes et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="6f6b1-108">Le gestionnaire de statistiques est configuré à l’aide des seuils d’indicateur d’intégrité clé (KHI) et peut être personnalisé pour répondre aux besoins uniques de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="6f6b1-109">Vous pouvez déployer le gestionnaire de statistiques dans un déploiement local dans lequel un serveur unique héberge tous les composants gestionnaires de statistiques côté serveur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="6f6b1-110">Pour plus d’informations sur le déploiement du gestionnaire de statistiques, voir [déploiement de statistiques pour Skype entreprise Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="6f6b1-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="6f6b1-111">Si vous disposez déjà d’un déploiement de Statistics Manager, mais que vous n’avez pas encore effectué la mise à niveau vers la version 2,0, voir [Nouveautés de la version 2,0](plan.md#BKMK_WhatsNew) et [mise à niveau du gestionnaire de statistiques pour Skype entreprise Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="6f6b1-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="6f6b1-112">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f6b1-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="6f6b1-113">Fonctionnalités et fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="6f6b1-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="6f6b1-114">Nouveautés de la version 2,0</span><span class="sxs-lookup"><span data-stu-id="6f6b1-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="6f6b1-115">Composants</span><span class="sxs-lookup"><span data-stu-id="6f6b1-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="6f6b1-116">Déploiement local</span><span class="sxs-lookup"><span data-stu-id="6f6b1-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="6f6b1-117">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f6b1-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="6f6b1-118">Considérations en matière de sécurité</span><span class="sxs-lookup"><span data-stu-id="6f6b1-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="6f6b1-119">Fonctionnalités et fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="6f6b1-119">Features and capabilities</span></span>
<span data-ttu-id="6f6b1-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="6f6b1-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="6f6b1-121">Le gestionnaire de statistiques vous permet d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f6b1-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="6f6b1-122">Affichez des données brutes pour tous les serveurs en temps réel.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="6f6b1-123">(Les données sont échantillonnées à un tarif très élevé et envoyées au site Web en moins d’une seconde.)</span><span class="sxs-lookup"><span data-stu-id="6f6b1-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="6f6b1-124">Afficher des données agrégées pour un rôle spécifique ; par exemple, serveur frontal, serveur de médiation, serveur Edge, etc.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="6f6b1-125">Explorez les données vers le bas pour afficher les données de sites spécifiques, des pools spécifiques au sein du site, puis des serveurs spécifiques au sein de la liste.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="6f6b1-126">Créez des graphiques personnalisés de telle sorte que les compteurs sélectionnés apparaissent par défaut.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="6f6b1-127">Effectuer un zoom et un panoramique sur les axes x et y ou sur l’axe x uniquement.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="6f6b1-128">Utiliser des plages de dates ou des points dans le temps pour filtrer des données.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="6f6b1-129">Affichez les performances du serveur sur la base des indicateurs d’État clés (KHIs).</span><span class="sxs-lookup"><span data-stu-id="6f6b1-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="6f6b1-130">KHIs représenter une collection de compteurs de performance avec une plage correcte définie.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="6f6b1-131">Affichez des mesures détaillées pour chaque compteur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="6f6b1-132">Comparer les données entre plusieurs populations ou serveurs.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="6f6b1-133">Afficher les rapports de compteurs latent pour identifier les agents qui ne signalent pas de données actuelles au service de tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="6f6b1-134">Enregistrez une instance particulière de données de graphique dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="6f6b1-135">Affichez KHIs en temps réel, y compris les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="6f6b1-136">Si la vue historique est activée, seules les nouvelles erreurs sont affichées.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="6f6b1-137">Afficher tous les KHIs en une seule fois</span><span class="sxs-lookup"><span data-stu-id="6f6b1-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="6f6b1-138">Afficher KHIs par serveur (vue paysage)</span><span class="sxs-lookup"><span data-stu-id="6f6b1-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="6f6b1-139">Afficher les définitions KHI</span><span class="sxs-lookup"><span data-stu-id="6f6b1-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="6f6b1-140">Nouveautés de la version 2,0</span><span class="sxs-lookup"><span data-stu-id="6f6b1-140">What's new in Release 2.0</span></span>
<span data-ttu-id="6f6b1-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="6f6b1-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="6f6b1-142">Les rubriques suivantes décrivent les nouveautés de la version 2,0.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="6f6b1-143">Si vous avez un déploiement de Statistics Manager et que vous n’avez pas encore effectué la mise à niveau, reportez-vous à la rubrique [mise à niveau du gestionnaire de statistiques pour Skype entreprise Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="6f6b1-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="6f6b1-144">Des affichages de scénario ont été ajoutés pour des scénarios de média, d’intégrité de fabrique et de basculement de pool.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="6f6b1-145">De nombreux nouveaux compteurs ont été ajoutés pour les serveurs SQL Server, d’autres compteurs d’utilisation Skype entreprise, etc.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="6f6b1-146">Intégration de nœud d’observateur pour l’agent gestionnaire de statistiques-si l’agent est installé sur un nœud de l’observateur, il signalera les statistiques de transaction synthétique en tant que compteurs aux statistiques Manager.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="6f6b1-147">De nombreuses améliorations liées à la fiabilité et aux performances.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="6f6b1-148">Pour vérifier la version du site Web du gestionnaire de statistiques que vous exécutez :</span><span class="sxs-lookup"><span data-stu-id="6f6b1-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="6f6b1-149">Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut) C:\Program Files\Skype entreprise Server Stats WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="6f6b1-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="6f6b1-150">Cliquer avec le bouton droit sur StatsManHubWebSite. dll et afficher ses propriétés</span><span class="sxs-lookup"><span data-stu-id="6f6b1-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="6f6b1-151">La version du produit s’affiche dans les détails de la description.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="6f6b1-152">Composants</span><span class="sxs-lookup"><span data-stu-id="6f6b1-152">Components</span></span>
<span data-ttu-id="6f6b1-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="6f6b1-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="6f6b1-154">Le gestionnaire de statistiques comprend les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="6f6b1-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="6f6b1-155">**Représentant.**</span><span class="sxs-lookup"><span data-stu-id="6f6b1-155">**Agent.**</span></span> <span data-ttu-id="6f6b1-156">Un agent léger qui s’exécute sur chaque serveur surveillé.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="6f6b1-157">L’agent autorise une interrogation de haut débit configurable des compteurs de performance avec une agrégation locale.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="6f6b1-158">**Écouteur.**</span><span class="sxs-lookup"><span data-stu-id="6f6b1-158">**Listener.**</span></span> <span data-ttu-id="6f6b1-159">API côté serveur qui reçoit les données de tous les agents et agrège les données entre les populations.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="6f6b1-160">**Raccord.**</span><span class="sxs-lookup"><span data-stu-id="6f6b1-160">**Hub.**</span></span> <span data-ttu-id="6f6b1-161">Sert d’API client pour le système, s’exécute sur le ou des serveurs Web et fournit des mises à jour de données en temps réel aux clients connectés via le site Web.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="6f6b1-162">(Le concentrateur est automatiquement installé en même temps que le site Web msi.)</span><span class="sxs-lookup"><span data-stu-id="6f6b1-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="6f6b1-163">**Associates.**</span><span class="sxs-lookup"><span data-stu-id="6f6b1-163">**Website.**</span></span> <span data-ttu-id="6f6b1-164">Une interface utilisateur qui rassemble toutes les fonctionnalités disponibles dans le système.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="6f6b1-165">De plus, le gestionnaire de statistiques nécessite des **ReDim**, un serveur de structure de données en source d’ouverture pour la mise en cache en mémoire.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="6f6b1-166">Pour plus d’informations sur le téléchargement de ReDim, voir [déploiement de statistiques](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="6f6b1-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="6f6b1-167">Déploiement local</span><span class="sxs-lookup"><span data-stu-id="6f6b1-167">On-premises deployment</span></span>
<span data-ttu-id="6f6b1-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="6f6b1-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="6f6b1-169">Dans un déploiement local, un serveur unique héberge tous les composants du gestionnaire de statistiques côté serveur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="6f6b1-170">Le diagramme suivant illustre un déploiement local, dans lequel le site Web du gestionnaire de statistiques, le concentrateur, l’écouteur et le système de mise en cache de ReDim sont hébergés sur un seul ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="6f6b1-171">Le gestionnaire de statistiques analyse trois serveurs Skype entreprise, chacun d’eux disposant d’un seul agent pour transmettre des données à l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="6f6b1-172">Les utilisateurs se connectent à un site Web unique pour afficher toutes les données agrégées par le gestionnaire de statistiques :</span><span class="sxs-lookup"><span data-stu-id="6f6b1-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Déploiement sur site du gestionnaire de statistiques](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="6f6b1-174">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6f6b1-174">Requirements</span></span>
<span data-ttu-id="6f6b1-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="6f6b1-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="6f6b1-176">Avant de déployer Statistics Manager, vous devez tenir compte des éléments suivants concernant le logiciel, la mise en réseau et la configuration matérielle requise.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="6f6b1-177">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="6f6b1-177">Software requirements</span></span>

- <span data-ttu-id="6f6b1-178">Windows Server 2016 et 2019</span><span class="sxs-lookup"><span data-stu-id="6f6b1-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="6f6b1-179">IIS (installé automatiquement)</span><span class="sxs-lookup"><span data-stu-id="6f6b1-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="6f6b1-180">Redis géré</span><span class="sxs-lookup"><span data-stu-id="6f6b1-180">Redis</span></span>

- <span data-ttu-id="6f6b1-181">Services du gestionnaire de statistiques (installés automatiquement)</span><span class="sxs-lookup"><span data-stu-id="6f6b1-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="6f6b1-182">PSExec-requis pour le déploiement d’agent distant</span><span class="sxs-lookup"><span data-stu-id="6f6b1-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="6f6b1-183">.NET 4,5 (inclus avec 2012 R2)-requis pour les agents et les composants côté serveur</span><span class="sxs-lookup"><span data-stu-id="6f6b1-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="6f6b1-184">Télécharger [Skype entreprise Server, gestionnaire de statistiques en temps réel (64)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="6f6b1-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="6f6b1-185">Configuration réseau requise</span><span class="sxs-lookup"><span data-stu-id="6f6b1-185">Networking requirements</span></span>


|<span data-ttu-id="6f6b1-186">**Serveur d’hébergement**</span><span class="sxs-lookup"><span data-stu-id="6f6b1-186">**Hosting server**</span></span>|<span data-ttu-id="6f6b1-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="6f6b1-187">**Agents**</span></span>|<span data-ttu-id="6f6b1-188">**Écouteur**</span><span class="sxs-lookup"><span data-stu-id="6f6b1-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f6b1-189">Mise en réseau Gigabit duplex intégral minimum.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="6f6b1-190">Port TCP sortant 8443 (numéro de Port personnalisable) pour communiquer avec l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="6f6b1-191">Le port d’écoute doit être le même sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="6f6b1-192">Port TCP entrant 80 ou 443 ouvert pour héberger le site Web.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="6f6b1-193">Port TCP entrant 8443 (numéro de Port personnalisable) pour que les agents puissent communiquer avec lui.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="6f6b1-194">Lors de l’installation, les ports de pare-feu pour l’écouteur et le site Web sont automatiquement créés.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="6f6b1-195">Pour les agents, l’installation part du principe que les connexions TCP sortantes sont autorisées par défaut.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="6f6b1-196">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="6f6b1-196">Hardware requirements</span></span>

<span data-ttu-id="6f6b1-197">Dans un déploiement local, dans lequel un serveur unique héberge tous les composants gestionnaires de statistiques côté serveur, un serveur doté de 16 Go de mémoire vive (RAM) et de 4 UC doit être en mesure de prendre en charge des exemples de 150 par seconde en moyenne.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="6f6b1-198">Pour déterminer le nombre de compteurs/agents pris en charge, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f6b1-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="6f6b1-199">100 serveurs \*80 compteurs \* 1 exemple par minute de chaque agent/60 secondes = ~ 133 exemples par seconde.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="6f6b1-200">Considérations en matière de sécurité</span><span class="sxs-lookup"><span data-stu-id="6f6b1-200">Security considerations</span></span>
<span data-ttu-id="6f6b1-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="6f6b1-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="6f6b1-202">Tout le trafic entre les serveurs est crypté.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="6f6b1-203">Le trafic HTTPs chiffré sera envoyé via le port 8443 (par défaut) de l’agent au serveur d’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="6f6b1-204">L’agent vérifie l’empreinte SSL du serveur pour vérifier que le serveur de l’écouteur est le destinataire attendu.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="6f6b1-205">Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne).</span><span class="sxs-lookup"><span data-stu-id="6f6b1-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="6f6b1-206">Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="6f6b1-207">Dès lors que l’agent est satisfait, l’écouteur est authentifié et un mot de passe est présenté par l’agent qui est ensuite vérifié par l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="6f6b1-208">L’agent commence à transmettre les données de performances par le biais de la connexion à l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="6f6b1-209">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="6f6b1-209">For more information</span></span>
<span data-ttu-id="6f6b1-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="6f6b1-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="6f6b1-211">Pour plus d'informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="6f6b1-211">For more information, see the following:</span></span>

- [<span data-ttu-id="6f6b1-212">Déploiement du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f6b1-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="6f6b1-213">Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f6b1-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="6f6b1-214">Dépannage du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6f6b1-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
