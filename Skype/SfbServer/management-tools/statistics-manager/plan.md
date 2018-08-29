---
title: Planifier pour le Gestionnaire de statistiques de Skype Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques de Skype pour Business Server 2015.'
ms.openlocfilehash: de4f2bedcbd03191b852366504423ebb031cf5f1
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244005"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="1577a-103">Planifier pour le Gestionnaire de statistiques de Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1577a-103">Plan for Statistics Manager for Skype for Business Server 2015</span></span>

<span data-ttu-id="1577a-104">**Résumé :** Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1577a-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server 2015.</span></span>

 <span data-ttu-id="1577a-105">Gestionnaire de statistiques pour Skype pour Business Server est un outil puissant qui vous permet d’afficher Skype pour les données de performances et d’intégrité Business Server en temps réel.</span><span class="sxs-lookup"><span data-stu-id="1577a-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="1577a-106">Vous pouvez interroger les données de performance sur des centaines de serveurs après quelques secondes et afficher les résultats instantanément sur le site Web de gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="1577a-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="1577a-107">Vous pouvez utiliser le Gestionnaire de statistiques pour identifier les problèmes de performances en cours, afficher les résultats d’une modification planifiée dans votre environnement, effectuer le suivi de la résolution des pannes et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="1577a-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="1577a-108">L’emploi, Gestionnaire de statistiques est configuré avec les seuils d’indicateur de l’intégrité de clé (KHI) et peuvent être personnalisé en fonction des besoins de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1577a-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="1577a-109">Vous pouvez déployer le Gestionnaire de statistiques dans un déploiement sur site dans lequel un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur.</span><span class="sxs-lookup"><span data-stu-id="1577a-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="1577a-110">Pour plus d’informations sur le déploiement du Gestionnaire de statistiques, voir [Déployer des statistiques responsable Skype pour Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="1577a-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="1577a-111">Si vous disposez déjà d’un déploiement existant du Gestionnaire de statistiques, mais vous ne disposez pas encore mis à niveau vers version 1.1, voir [Nouveautés de version 1.1](plan.md#BKMK_WhatsNew) et [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="1577a-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 1.1, see [What's new in Release 1.1](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

<span data-ttu-id="1577a-112">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="1577a-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="1577a-113">Fonctions et fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="1577a-113">Features and capabilities</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)

- [<span data-ttu-id="1577a-114">Quelles sont les nouveautés dans la version 1.1</span><span class="sxs-lookup"><span data-stu-id="1577a-114">What's new in Release 1.1</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="1577a-115">Composants</span><span class="sxs-lookup"><span data-stu-id="1577a-115">Components</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)

- [<span data-ttu-id="1577a-116">Déploiement local</span><span class="sxs-lookup"><span data-stu-id="1577a-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="1577a-117">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="1577a-117">Requirements</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)

- [<span data-ttu-id="1577a-118">Considérations relatives à la sécurité</span><span class="sxs-lookup"><span data-stu-id="1577a-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="1577a-119">Fonctions et fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="1577a-119">Features and capabilities</span></span>
<span data-ttu-id="1577a-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="1577a-120"></span></span>

<span data-ttu-id="1577a-121">Gestionnaire de statistiques vous permet de :</span><span class="sxs-lookup"><span data-stu-id="1577a-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="1577a-122">Afficher les données brutes pour tous les serveurs en temps réel.</span><span class="sxs-lookup"><span data-stu-id="1577a-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="1577a-123">(Données sont l’objet d’un taux très élevé et envoyées au site Web en moins d’une seconde).</span><span class="sxs-lookup"><span data-stu-id="1577a-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="1577a-124">Afficher les données qui sont regroupées pour un rôle spécifique ; par exemple, serveur frontal, serveur de médiation, serveur Edge et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="1577a-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="1577a-125">Accéder à afficher les données pour des sites spécifiques, des pools spécifiques au sein du site et serveurs puis spécifiques au sein du pool.</span><span class="sxs-lookup"><span data-stu-id="1577a-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="1577a-126">Créer des graphiques personnalisés afin que choisi compteurs sont affichées par défaut.</span><span class="sxs-lookup"><span data-stu-id="1577a-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="1577a-127">Zoom et panoramique sur les deux - axes x et y- ou sur l’axe.</span><span class="sxs-lookup"><span data-stu-id="1577a-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="1577a-128">Utiliser des plages de dates ou de points dans le temps pour filtrer les données.</span><span class="sxs-lookup"><span data-stu-id="1577a-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="1577a-129">Afficher les performances du serveur en fonction des indicateurs d’intégrité de clé établie (KHIs).</span><span class="sxs-lookup"><span data-stu-id="1577a-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="1577a-130">KHIs représentent une collection de compteurs de performance avec une plage définie saine.</span><span class="sxs-lookup"><span data-stu-id="1577a-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="1577a-131">Visualiser les mesures détaillées pour chaque compteur.</span><span class="sxs-lookup"><span data-stu-id="1577a-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="1577a-132">Comparer les données entre plusieurs populations ou plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="1577a-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="1577a-133">Afficher les rapports de compteur latent pour identifier les agents qui sont reporting pas de données actuelles pour le service de tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="1577a-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="1577a-134">Enregistrer une instance spécifique de données de graphique dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="1577a-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="1577a-135">Affichage KHIs en temps réel, y compris les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="1577a-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="1577a-136">Si l’affichage de l’historique est activée, seuls les échecs nouveau sont affichés.</span><span class="sxs-lookup"><span data-stu-id="1577a-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="1577a-137">Afficher tous les KHIs en même temps</span><span class="sxs-lookup"><span data-stu-id="1577a-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="1577a-138">Vue KHIs par le serveur (mode paysage)</span><span class="sxs-lookup"><span data-stu-id="1577a-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="1577a-139">Définitions d’affichage KHI</span><span class="sxs-lookup"><span data-stu-id="1577a-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-11"></a><span data-ttu-id="1577a-140">Quelles sont les nouveautés dans la version 1.1</span><span class="sxs-lookup"><span data-stu-id="1577a-140">What's new in Release 1.1</span></span>
<span data-ttu-id="1577a-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="1577a-141"></span></span>

<span data-ttu-id="1577a-142">La section suivante décrit les nouveautés dans la version 1.1.</span><span class="sxs-lookup"><span data-stu-id="1577a-142">The following describes what's new in Release 1.1.</span></span> <span data-ttu-id="1577a-143">Si vous avez un déploiement existant de statistiques Manager et vous n’avez pas encore mis à niveau, voir [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="1577a-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

- <span data-ttu-id="1577a-144">Vues de scénario ont été ajoutées pour le média Edge, d’intégrité Fabric, le basculement et scénarios d’inscription.</span><span class="sxs-lookup"><span data-stu-id="1577a-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="1577a-145">Ligne de commande PerfAgentStorageManager.exe (installé avec le port d’écoute) peuvent désormais exporter des données de compteur en tant qu’un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="1577a-145">Command line PerfAgentStorageManager.exe (installed with the Listener) can now export counter data as a CSV.</span></span>

- <span data-ttu-id="1577a-146">Nombre de nouveaux compteurs ont été ajoutées pour les serveurs SQL, compteurs Windows Fabric, plus Skype pour des compteurs d’utilisation de Business et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="1577a-146">Many new counters have been added for SQL servers, more Windows Fabric counters, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="1577a-147">Intégration de nœud observateur pour l’Agent de gestionnaire de statistiques - si l’Agent est installé sur un nœud Observateur, il renverra un compte-rendu statistiques sur les transactions synthétiques en tant que compteurs au Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="1577a-147">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="1577a-148">Nombreuses améliorations de la fiabilité et les performances.</span><span class="sxs-lookup"><span data-stu-id="1577a-148">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="1577a-149">Pour vérifier la version du Gestionnaire de statistiques de site Web vous exécutez :</span><span class="sxs-lookup"><span data-stu-id="1577a-149">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="1577a-150">Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut) C:\Program Files\Skype pour Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="1577a-150">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="1577a-151">Cliquez avec le bouton droit sur StatsManHubWebSite.dll et afficher ses propriétés</span><span class="sxs-lookup"><span data-stu-id="1577a-151">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="1577a-152">La version du produit s’affiche dans les détails de la description.</span><span class="sxs-lookup"><span data-stu-id="1577a-152">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="1577a-153">Composants</span><span class="sxs-lookup"><span data-stu-id="1577a-153">Components</span></span>
<span data-ttu-id="1577a-154"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="1577a-154"></span></span>

<span data-ttu-id="1577a-155">Gestionnaire de statistiques comprend les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="1577a-155">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="1577a-156">**Agent.**</span><span class="sxs-lookup"><span data-stu-id="1577a-156">**Agent.**</span></span> <span data-ttu-id="1577a-157">Un agent léger qui s’exécute sur chaque serveur analysé.</span><span class="sxs-lookup"><span data-stu-id="1577a-157">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="1577a-158">L’Agent permet d’interrogation configurable taux élevé de compteurs de performances avec l’agrégation de locale.</span><span class="sxs-lookup"><span data-stu-id="1577a-158">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="1577a-159">**Port d’écoute.**</span><span class="sxs-lookup"><span data-stu-id="1577a-159">**Listener.**</span></span> <span data-ttu-id="1577a-160">L’API côté serveur qui reçoit les données de tous les Agents et regroupe les données entre les populations.</span><span class="sxs-lookup"><span data-stu-id="1577a-160">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="1577a-161">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="1577a-161">**Hub.**</span></span> <span data-ttu-id="1577a-162">Sert de l’API cliente pour le système, s’exécute sur l’ou les serveurs web et fournit des mises à jour des données en temps réel aux clients connectés via le site Web.</span><span class="sxs-lookup"><span data-stu-id="1577a-162">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="1577a-163">(Le Hub est installé automatiquement dans le cadre d’un site Web msi).</span><span class="sxs-lookup"><span data-stu-id="1577a-163">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="1577a-164">**Site Web.**</span><span class="sxs-lookup"><span data-stu-id="1577a-164">**Website.**</span></span> <span data-ttu-id="1577a-165">Une interface utilisateur qui regroupe toutes les fonctionnalités disponibles dans le système.</span><span class="sxs-lookup"><span data-stu-id="1577a-165">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="1577a-166">En outre, le Gestionnaire de statistiques nécessite **Redis**, un serveur de structure de données source ouverte pour la mise en cache en mémoire.</span><span class="sxs-lookup"><span data-stu-id="1577a-166">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="1577a-167">Pour plus d’informations sur le téléchargement Redis, voir [Déployer le gestionnaire statistiques](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="1577a-167">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="1577a-168">Déploiement local</span><span class="sxs-lookup"><span data-stu-id="1577a-168">On-premises deployment</span></span>
<span data-ttu-id="1577a-169"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="1577a-169"></span></span>

<span data-ttu-id="1577a-170">Dans un déploiement sur site, un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur.</span><span class="sxs-lookup"><span data-stu-id="1577a-170">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="1577a-171">Le diagramme suivant illustre un déploiement sur site, dans lequel le site Web du gestionnaire statistiques, Hub, port d’écoute et Redis mise en cache du système sont hébergés sur un seul ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1577a-171">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="1577a-172">Gestionnaire de statistiques de surveillance Skype trois serveurs d’entreprise, chacun d'entre eux ont un seul Agent de transmission de données vers le port d’écoute.</span><span class="sxs-lookup"><span data-stu-id="1577a-172">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="1577a-173">Utilisateurs se connectent à un site Web pour afficher toutes les données sont agrégées par le Gestionnaire de statistiques :</span><span class="sxs-lookup"><span data-stu-id="1577a-173">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Déploiement sur site du gestionnaire de statistiques](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="1577a-175">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="1577a-175">Requirements</span></span>
<span data-ttu-id="1577a-176"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="1577a-176"></span></span>

<span data-ttu-id="1577a-177">Vous devez prendre en compte la configuration requise matérielle, logicielle et réseau suivante avant de déployer le Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="1577a-177">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="1577a-178">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="1577a-178">Software requirements</span></span>

- <span data-ttu-id="1577a-179">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1577a-179">Windows Server 2012 R2</span></span>

- <span data-ttu-id="1577a-180">IIS (installé automatiquement)</span><span class="sxs-lookup"><span data-stu-id="1577a-180">IIS (automatically installed)</span></span>

- <span data-ttu-id="1577a-181">Redis</span><span class="sxs-lookup"><span data-stu-id="1577a-181">Redis</span></span>

- <span data-ttu-id="1577a-182">Services Gestionnaire de statistiques (installés automatiquement)</span><span class="sxs-lookup"><span data-stu-id="1577a-182">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="1577a-183">PSExec - nécessaire pour exécuter le déploiement de l’agent à distance</span><span class="sxs-lookup"><span data-stu-id="1577a-183">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="1577a-184">.NET 4.5 (inclus avec 2012 R2) - requis pour les composants côté serveur</span><span class="sxs-lookup"><span data-stu-id="1577a-184">.NET 4.5 (included with 2012 R2) - Required for server-side components</span></span>

- <span data-ttu-id="1577a-185">.NET 4.0 - requis pour les agents</span><span class="sxs-lookup"><span data-stu-id="1577a-185">.NET 4.0 - Required for agents</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="1577a-186">Exigences de mise en réseau</span><span class="sxs-lookup"><span data-stu-id="1577a-186">Networking requirements</span></span>


|<span data-ttu-id="1577a-187">**Serveur d’hébergement**</span><span class="sxs-lookup"><span data-stu-id="1577a-187">**Hosting server**</span></span>|<span data-ttu-id="1577a-188">**Agents**</span><span class="sxs-lookup"><span data-stu-id="1577a-188">**Agents**</span></span>|<span data-ttu-id="1577a-189">**Port d’écoute**</span><span class="sxs-lookup"><span data-stu-id="1577a-189">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1577a-190">Gestion de réseau gigabit minimale en duplex intégral.</span><span class="sxs-lookup"><span data-stu-id="1577a-190">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="1577a-191">Port TCP sortant 8443 (numéro de port personnalisable) pour communiquer avec le port d’écoute.</span><span class="sxs-lookup"><span data-stu-id="1577a-191">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="1577a-192">Le port d’écoute doit être identiques sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="1577a-192">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="1577a-193">Le port TCP 80 ou 443 ouvert pour héberger le site Web de trafic entrant.</span><span class="sxs-lookup"><span data-stu-id="1577a-193">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="1577a-194">Entrante 8443 (numéro de port personnalisables) le port TCP pour les agents de communiquer avec lui.</span><span class="sxs-lookup"><span data-stu-id="1577a-194">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="1577a-195">Pendant l’installation, les ports de pare-feu pour le port d’écoute et le site Web sont créés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="1577a-195">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="1577a-196">Pour les Agents, l’installation suppose que les connexions TCP sortantes sont autorisées par défaut.</span><span class="sxs-lookup"><span data-stu-id="1577a-196">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="1577a-197">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="1577a-197">Hardware requirements</span></span>

<span data-ttu-id="1577a-198">Dans un déploiement sur site, dans laquelle un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur, un serveur avec 16 Go de RAM et 4 processeurs doit pouvoir prendre en charge environ 150 échantillons par seconde en moyenne.</span><span class="sxs-lookup"><span data-stu-id="1577a-198">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="1577a-199">Pour déterminer combien compteurs/agents, vous pouvez prendre en charge, utilisez le calcul suivant :</span><span class="sxs-lookup"><span data-stu-id="1577a-199">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="1577a-200">100 serveurs \*80 compteurs \* 1 exemple par minute de chaque agent / 60 secondes = ~ 133 par seconde.</span><span class="sxs-lookup"><span data-stu-id="1577a-200">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="1577a-201">Considérations relatives à la sécurité</span><span class="sxs-lookup"><span data-stu-id="1577a-201">Security considerations</span></span>
<span data-ttu-id="1577a-202"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="1577a-202"></span></span>

<span data-ttu-id="1577a-203">Tout le trafic entre les serveurs est chiffré.</span><span class="sxs-lookup"><span data-stu-id="1577a-203">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="1577a-204">Le trafic HTTPS chiffré recevrez via le port 8443 (par défaut) à partir de l’Agent sur le serveur de port d’écoute.</span><span class="sxs-lookup"><span data-stu-id="1577a-204">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="1577a-205">L’Agent vérifie l’empreinte de SSL sur le serveur afin de garantir le serveur écoute le destinataire prévu.</span><span class="sxs-lookup"><span data-stu-id="1577a-205">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="1577a-206">Notez que l’agent utilise la vérification de l’empreinte de certificat (au lieu de la vérification de la chaîne).</span><span class="sxs-lookup"><span data-stu-id="1577a-206">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="1577a-207">Il n’effectue pas de validation de certificat complète, car il est possible d’utiliser des certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="1577a-207">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="1577a-208">Une fois que l’Agent est satisfait le port d’écoute est authentique, un mot de passe est présentée par l’Agent qui est ensuite vérifiée par le récepteur.</span><span class="sxs-lookup"><span data-stu-id="1577a-208">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="1577a-209">L’Agent commence la transmission de données de performances sur la connexion à l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="1577a-209">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1577a-210">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="1577a-210">For more information</span></span>
<span data-ttu-id="1577a-211"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="1577a-211"></span></span>

<span data-ttu-id="1577a-212">Pour plus d'informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="1577a-212">For more information, see the following:</span></span>

- [<span data-ttu-id="1577a-213">Déploiement du gestionnaire de statistiques pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="1577a-213">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)

- [<span data-ttu-id="1577a-214">Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="1577a-214">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)

- [<span data-ttu-id="1577a-215">Dépannage du gestionnaire de statistiques pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="1577a-215">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)

- [<span data-ttu-id="1577a-216">Skype pour Business Server Manager statistiques de blog</span><span class="sxs-lookup"><span data-stu-id="1577a-216">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)


