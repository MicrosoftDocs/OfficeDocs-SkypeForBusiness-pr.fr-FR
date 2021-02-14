---
title: Planifier le Gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques pour Skype Entreprise Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821824"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="5c628-103">Planifier le Gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5c628-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="5c628-104">**Résumé :** Lisez cette rubrique pour en savoir plus sur le Gestionnaire de statistiques pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5c628-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="5c628-105">Le Gestionnaire de statistiques pour Skype Entreprise Server est un outil puissant qui vous permet d’afficher les données d’état et de performances de Skype Entreprise Server en temps réel.</span><span class="sxs-lookup"><span data-stu-id="5c628-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="5c628-106">Vous pouvez sonder les données de performances sur des centaines de serveurs toutes les quelques secondes et afficher les résultats instantanément sur le site web du Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="5c628-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="5c628-107">Vous pouvez utiliser le Gestionnaire de statistiques pour identifier les problèmes de performances en cours, afficher les résultats d’une modification planifiée de votre environnement, suivre la résolution des pannes et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="5c628-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="5c628-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment’s unique needs.</span><span class="sxs-lookup"><span data-stu-id="5c628-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="5c628-109">Vous pouvez déployer le Gestionnaire de statistiques dans un déploiement local dans lequel un seul serveur héberge tous les composants du gestionnaire de statistiques côté serveur.</span><span class="sxs-lookup"><span data-stu-id="5c628-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="5c628-110">Pour plus d’informations sur le déploiement du Gestionnaire de statistiques, voir [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="5c628-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="5c628-111">Si vous avez déjà un déploiement existant du Gestionnaire de statistiques, mais que vous n’avez pas encore mis à niveau vers la version 2.0, consultez Les nouveautés de la version [2.0](plan.md#BKMK_WhatsNew) et le Gestionnaire de statistiques de mise à niveau pour [Skype Entreprise Server.](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="5c628-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="5c628-112">Cette rubrique comprend les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c628-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="5c628-113">Fonctionnalités et fonctions</span><span class="sxs-lookup"><span data-stu-id="5c628-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="5c628-114">Nouveautés de la version 2.0</span><span class="sxs-lookup"><span data-stu-id="5c628-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="5c628-115">Composants</span><span class="sxs-lookup"><span data-stu-id="5c628-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="5c628-116">Déploiement local</span><span class="sxs-lookup"><span data-stu-id="5c628-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="5c628-117">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="5c628-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="5c628-118">Considérations relatives à la sécurité</span><span class="sxs-lookup"><span data-stu-id="5c628-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="5c628-119">Fonctionnalités et fonctions</span><span class="sxs-lookup"><span data-stu-id="5c628-119">Features and capabilities</span></span>
<span data-ttu-id="5c628-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="5c628-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="5c628-121">Le Gestionnaire de statistiques vous permet de :</span><span class="sxs-lookup"><span data-stu-id="5c628-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="5c628-122">Afficher les données brutes de tous les serveurs en temps réel.</span><span class="sxs-lookup"><span data-stu-id="5c628-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="5c628-123">(Les données sont échantillon données à un taux très élevé et envoyées au site web en moins d’une seconde.)</span><span class="sxs-lookup"><span data-stu-id="5c628-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="5c628-124">Afficher les données agrégées pour un rôle spécifique ; par exemple, serveur frontal, serveur de médiation, serveur Edge, etc.</span><span class="sxs-lookup"><span data-stu-id="5c628-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="5c628-125">Descendre pour afficher les données pour des sites spécifiques, des pools spécifiques au sein du site, puis des serveurs spécifiques au sein du pool.</span><span class="sxs-lookup"><span data-stu-id="5c628-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="5c628-126">Créez des graphiques personnalisés afin que les compteurs choisis soient affichés par défaut.</span><span class="sxs-lookup"><span data-stu-id="5c628-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="5c628-127">Zoom et panoramique sur les axes x et y ou sur l’axe x uniquement.</span><span class="sxs-lookup"><span data-stu-id="5c628-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="5c628-128">Utilisez des plages de dates ou des points dans l’heure pour filtrer les données.</span><span class="sxs-lookup"><span data-stu-id="5c628-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="5c628-129">Afficher les performances du serveur en fonction des indicateurs d’état de santé clés établis.</span><span class="sxs-lookup"><span data-stu-id="5c628-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="5c628-130">Les khis représentent une collection de compteurs de performance avec une plage d’état d’santé définie.</span><span class="sxs-lookup"><span data-stu-id="5c628-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="5c628-131">Afficher des mesures détaillées pour chaque compteur.</span><span class="sxs-lookup"><span data-stu-id="5c628-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="5c628-132">Comparez les données entre plusieurs populations ou serveurs.</span><span class="sxs-lookup"><span data-stu-id="5c628-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="5c628-133">Afficher les rapports de compteur latents pour identifier les agents qui ne signalent pas les données actuelles au service de tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="5c628-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="5c628-134">Enregistrez une instance particulière de données de graphique dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="5c628-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="5c628-135">Afficher les KHIs en temps réel, y compris les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="5c628-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="5c628-136">Si l’affichage Historique est activé, seuls les nouveaux échecs sont affichés.</span><span class="sxs-lookup"><span data-stu-id="5c628-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="5c628-137">Afficher toutes les khis en même temps</span><span class="sxs-lookup"><span data-stu-id="5c628-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="5c628-138">Afficher les KHIs par serveur (mode Paysage)</span><span class="sxs-lookup"><span data-stu-id="5c628-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="5c628-139">Afficher les définitions KHI</span><span class="sxs-lookup"><span data-stu-id="5c628-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="5c628-140">Nouveautés de la version 2.0</span><span class="sxs-lookup"><span data-stu-id="5c628-140">What's new in Release 2.0</span></span>
<span data-ttu-id="5c628-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="5c628-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="5c628-142">Ce qui suit décrit les nouveautés de la version 2.0.</span><span class="sxs-lookup"><span data-stu-id="5c628-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="5c628-143">Si vous avez un déploiement existant du Gestionnaire de statistiques et que vous n’avez pas encore mis à niveau, voir [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="5c628-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="5c628-144">Des affichages de scénario ont été ajoutés pour les scénarios edge media, Fabric Health, Pool Failover et Registration.</span><span class="sxs-lookup"><span data-stu-id="5c628-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="5c628-145">De nombreux nouveaux compteurs ont été ajoutés pour SQL serveurs, d’autres compteurs d’utilisation de Skype Entreprise, etc.</span><span class="sxs-lookup"><span data-stu-id="5c628-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="5c628-146">Intégration du nœud de l’observeur pour l’agent du gestionnaire de statistiques : si l’agent est installé sur un nœud observeur, il signale les statistiques de transaction synthétique sous forme de compteurs au Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="5c628-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="5c628-147">De nombreuses améliorations en matière de fiabilité et de performances.</span><span class="sxs-lookup"><span data-stu-id="5c628-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="5c628-148">Pour vérifier la version du site web du Gestionnaire de statistiques que vous exécutez :</span><span class="sxs-lookup"><span data-stu-id="5c628-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="5c628-149">Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="5c628-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="5c628-150">Cliquez avec le bouton droit StatsManHubWebSite.dll et affichez ses propriétés</span><span class="sxs-lookup"><span data-stu-id="5c628-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="5c628-151">La version du produit s’affiche dans les détails de description.</span><span class="sxs-lookup"><span data-stu-id="5c628-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="5c628-152">Composants</span><span class="sxs-lookup"><span data-stu-id="5c628-152">Components</span></span>
<span data-ttu-id="5c628-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="5c628-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="5c628-154">Le Gestionnaire de statistiques se compose des composants suivants :</span><span class="sxs-lookup"><span data-stu-id="5c628-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="5c628-155">**Agent.**</span><span class="sxs-lookup"><span data-stu-id="5c628-155">**Agent.**</span></span> <span data-ttu-id="5c628-156">Agent léger qui s’exécute sur chaque serveur surveillé.</span><span class="sxs-lookup"><span data-stu-id="5c628-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="5c628-157">L’agent permet l’interrogation à taux élevé configurable des compteurs de performance avec l’agrégation locale.</span><span class="sxs-lookup"><span data-stu-id="5c628-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="5c628-158">**Listener.**</span><span class="sxs-lookup"><span data-stu-id="5c628-158">**Listener.**</span></span> <span data-ttu-id="5c628-159">API côté serveur qui reçoit des données de tous les agents et regroupe les données entre les populations.</span><span class="sxs-lookup"><span data-stu-id="5c628-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="5c628-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="5c628-160">**Hub.**</span></span> <span data-ttu-id="5c628-161">Sert d’API cliente pour le système, s’exécute sur les serveurs web et fournit des mises à jour de données en temps réel aux clients connectés via le site web.</span><span class="sxs-lookup"><span data-stu-id="5c628-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="5c628-162">(Le Hub est automatiquement installé dans le cadre du site web msi.)</span><span class="sxs-lookup"><span data-stu-id="5c628-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="5c628-163">**Site web.**</span><span class="sxs-lookup"><span data-stu-id="5c628-163">**Website.**</span></span> <span data-ttu-id="5c628-164">Interface utilisateur qui rassemble toutes les fonctionnalités disponibles dans le système.</span><span class="sxs-lookup"><span data-stu-id="5c628-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="5c628-165">En outre, le gestionnaire de statistiques requiert **Redis**, un serveur de structure de données open source pour la mise en cache en mémoire.</span><span class="sxs-lookup"><span data-stu-id="5c628-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="5c628-166">Pour plus d’informations sur le téléchargement de Redis, voir [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="5c628-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="5c628-167">Déploiement sur site</span><span class="sxs-lookup"><span data-stu-id="5c628-167">On-premises deployment</span></span>
<span data-ttu-id="5c628-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="5c628-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="5c628-169">Dans un déploiement local, un seul serveur héberge tous les composants du Gestionnaire de statistiques côté serveur.</span><span class="sxs-lookup"><span data-stu-id="5c628-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="5c628-170">Le diagramme suivant illustre un déploiement local, dans lequel le site web du gestionnaire de statistiques, le système de mise en cache Hub, Listener et Redis sont hébergés sur un seul ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5c628-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="5c628-171">Le Gestionnaire de statistiques surveille trois serveurs Skype Entreprise, chacun d’entre eux avec un seul agent transmettant des données à l’écoute.</span><span class="sxs-lookup"><span data-stu-id="5c628-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="5c628-172">Les utilisateurs se connectent à un site web unique pour afficher toutes les données agrégées par le Gestionnaire de statistiques :</span><span class="sxs-lookup"><span data-stu-id="5c628-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Déploiement local du gestionnaire des statistiques](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="5c628-174">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="5c628-174">Requirements</span></span>
<span data-ttu-id="5c628-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="5c628-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="5c628-176">Vous devez prendre en compte les configurations logicielle, réseau et matérielle suivantes avant de déployer le Gestionnaire de statistiques.</span><span class="sxs-lookup"><span data-stu-id="5c628-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="5c628-177">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="5c628-177">Software requirements</span></span>

- <span data-ttu-id="5c628-178">Windows Server 2016 et 2019</span><span class="sxs-lookup"><span data-stu-id="5c628-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="5c628-179">IIS (installé automatiquement)</span><span class="sxs-lookup"><span data-stu-id="5c628-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="5c628-180">Redis</span><span class="sxs-lookup"><span data-stu-id="5c628-180">Redis</span></span>

- <span data-ttu-id="5c628-181">Services du Gestionnaire de statistiques (installé automatiquement)</span><span class="sxs-lookup"><span data-stu-id="5c628-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="5c628-182">PSExec - Obligatoire pour le déploiement d’agent distant</span><span class="sxs-lookup"><span data-stu-id="5c628-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="5c628-183">.NET 4.5 (inclus avec 2012 R2) : requis pour les agents et les composants côté serveur</span><span class="sxs-lookup"><span data-stu-id="5c628-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="5c628-184">Télécharger [skype entreprise server, Real-Time statistiques (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="5c628-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="5c628-185">Configuration de réseau requise</span><span class="sxs-lookup"><span data-stu-id="5c628-185">Networking requirements</span></span>


|<span data-ttu-id="5c628-186">**Serveur d’hébergement**</span><span class="sxs-lookup"><span data-stu-id="5c628-186">**Hosting server**</span></span>|<span data-ttu-id="5c628-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="5c628-187">**Agents**</span></span>|<span data-ttu-id="5c628-188">**Listener**</span><span class="sxs-lookup"><span data-stu-id="5c628-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c628-189">Réseau duplex complet gigabit minimum.</span><span class="sxs-lookup"><span data-stu-id="5c628-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="5c628-190">Port TCP sortant 8443 (numéro de port personnalisable) pour communiquer avec l’port d’écoute.</span><span class="sxs-lookup"><span data-stu-id="5c628-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="5c628-191">Le port d’écoute doit être le même sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="5c628-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="5c628-192">Le port TCP entrant 80 ou 443 s’ouvre pour héberger le site web.</span><span class="sxs-lookup"><span data-stu-id="5c628-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="5c628-193">Port TCP entrant 8443 (numéro de port personnalisable) pour que les agents communiquent avec lui.</span><span class="sxs-lookup"><span data-stu-id="5c628-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="5c628-194">Pendant l’installation, les ports de pare-feu pour l’port d’écoute et le site web sont automatiquement créés.</span><span class="sxs-lookup"><span data-stu-id="5c628-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="5c628-195">Pour les agents, l’installation suppose que les connexions TCP sortantes sont autorisées par défaut.</span><span class="sxs-lookup"><span data-stu-id="5c628-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="5c628-196">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="5c628-196">Hardware requirements</span></span>

<span data-ttu-id="5c628-197">Dans un déploiement local, dans lequel un seul serveur héberge tous les composants du gestionnaire de statistiques côté serveur, un serveur avec 16 Go de RAM et 4 processeurs doit pouvoir prendre en charge environ 150 échantillons par seconde en moyenne.</span><span class="sxs-lookup"><span data-stu-id="5c628-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="5c628-198">Pour déterminer le nombre de compteurs/agents que vous pouvez prendre en charge, utilisez le calcul suivant :</span><span class="sxs-lookup"><span data-stu-id="5c628-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="5c628-199">100 serveurs 80 compteurs 1 échantillon par minute de chaque \* \* agent / 60 secondes = ~ 133 échantillons par seconde.</span><span class="sxs-lookup"><span data-stu-id="5c628-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="5c628-200">Considérations en matière de sécurité</span><span class="sxs-lookup"><span data-stu-id="5c628-200">Security considerations</span></span>
<span data-ttu-id="5c628-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="5c628-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="5c628-202">Tout le trafic entre les serveurs est chiffré.</span><span class="sxs-lookup"><span data-stu-id="5c628-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="5c628-203">Le trafic HTTPS chiffré sera envoyé sur le port 8443 (par défaut) de l’agent vers le serveur d’écoute.</span><span class="sxs-lookup"><span data-stu-id="5c628-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="5c628-204">L’agent vérifie l’empreinte SSL sur le serveur pour s’assurer que le serveur d’écoute est le destinataire attendu.</span><span class="sxs-lookup"><span data-stu-id="5c628-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="5c628-205">Notez que l’agent utilise la vérification de l’empreinte numérique du certificat (au lieu de la vérification de chaîne).</span><span class="sxs-lookup"><span data-stu-id="5c628-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="5c628-206">Il n’aura pas la validation complète du certificat, car il est possible d’utiliser des certificats auto-signés.</span><span class="sxs-lookup"><span data-stu-id="5c628-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="5c628-207">Une fois que l’agent est satisfait que l’écoute est authentifiée, un mot de passe est présenté par l’agent qui est ensuite vérifié par l’écoute.</span><span class="sxs-lookup"><span data-stu-id="5c628-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="5c628-208">L’agent commence à transmettre les données de performances sur la connexion à l’écoute.</span><span class="sxs-lookup"><span data-stu-id="5c628-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5c628-209">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="5c628-209">For more information</span></span>
<span data-ttu-id="5c628-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="5c628-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="5c628-211">Pour plus d'informations, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="5c628-211">For more information, see the following:</span></span>

- [<span data-ttu-id="5c628-212">Déploiement du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5c628-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="5c628-213">Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5c628-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="5c628-214">Dépannage du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5c628-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
