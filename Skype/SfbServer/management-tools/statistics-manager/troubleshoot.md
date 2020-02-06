---
title: Dépannage du gestionnaire de statistiques pour Skype Entreprise Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Résumé : Lisez cette rubrique pour résoudre les problèmes liés à votre déploiement du gestionnaire de statistiques pour Skype entreprise Server.'
ms.openlocfilehash: a787297b25b983303e65f398dfb7b275ae044944
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816213"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="6eb1c-103">Dépannage du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6eb1c-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="6eb1c-104">**Résumé :** Consultez cette rubrique pour dépanner votre déploiement du gestionnaire de statistiques pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="6eb1c-105">Cette rubrique explique comment résoudre les problèmes de déploiement de votre gestionnaire de statistiques en décrivant des événements que vous pouvez rencontrer dans le journal des événements de l’application, ainsi que les actions appropriées pour corriger l’événement.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="6eb1c-106">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="6eb1c-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="6eb1c-107">Événements de l’agent</span><span class="sxs-lookup"><span data-stu-id="6eb1c-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="6eb1c-108">Événements de l’écouteur</span><span class="sxs-lookup"><span data-stu-id="6eb1c-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="6eb1c-109">Problèmes de site web</span><span class="sxs-lookup"><span data-stu-id="6eb1c-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="6eb1c-110">Événements de l’agent</span><span class="sxs-lookup"><span data-stu-id="6eb1c-110">Agent events</span></span>
<span data-ttu-id="6eb1c-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="6eb1c-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="6eb1c-112">**1000** : impossible de configurer le limiteur de processeur (objet de traitement) ; raison inconnue</span><span class="sxs-lookup"><span data-stu-id="6eb1c-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="6eb1c-113">**1001** : le processus de limitation de processus n’est pas autorisé sur le processus (probablement déjà dans un objet de travail).</span><span class="sxs-lookup"><span data-stu-id="6eb1c-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="6eb1c-114">L’agent s’exécute à l’intérieur d’un objet de traitement Windows pour limiter automatiquement son encombrement mémoire.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="6eb1c-115">Si l’agent ne démarre pas et si ces entrées d’événements apparaissent dans le journal d’événements, l’objet de traitement n’a pas pu être instancié sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="6eb1c-116">Pour contourner ce problème, la limite maximale de la mémoire peut être supprimée en modifiant une valeur dans le fichier de configuration :</span><span class="sxs-lookup"><span data-stu-id="6eb1c-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="6eb1c-117">Recherchez « MaxProcessMemoryMB » et attribuez la valeur « 0 » comme suit :</span><span class="sxs-lookup"><span data-stu-id="6eb1c-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```console
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="6eb1c-118">Si cette modification est apportée, l’agent utilisera \< généralement 100 Mo de mémoire, mais il ne sera pas limité de force à 300 Mo par défaut.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="6eb1c-119">Néanmoins, si vous effectuez cette modification, nous vous recommandons de surveiller attentivement l’utilisation de la mémoire, afin de vous assurer que l’agent ne consomme pas trop de mémoire sur son ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="6eb1c-120">**2000** : échec de l’initialisation du client</span><span class="sxs-lookup"><span data-stu-id="6eb1c-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="6eb1c-121">**2001** : impossible de se connecter au service sur n’importe quelle source IP</span><span class="sxs-lookup"><span data-stu-id="6eb1c-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="6eb1c-122">Si l’agent ne peut pas se connecter à l’ordinateur d’écoute, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="6eb1c-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="6eb1c-123">Vérifiez que le service d’écoute est en cours d’exécution sur l’ordinateur d’écoute.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="6eb1c-124">Si ce n’est pas le cas, assurez-vous que Redis est en cours d’exécution sur ce serveur, puis redémarrez le service d’écoute.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="6eb1c-125">Pour vérifier qu’il n’y a aucun problème avec le service d’écouteur de statistiques, consultez le journal des événements du gestionnaire de statistiques sur l’ordinateur de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="6eb1c-126">Utilisez un outil de connectivité tel que telnet pour vérifier la connectivité entre l’ordinateur de l’agent et l’écouteur sur le port approprié.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="6eb1c-127">Sinon, assurez-vous que la règle de pare-feu pour le trafic entrant est activée sur l’ordinateur d’écoute pour le type de réseau auquel l’ordinateur d’écoute est connecté (privé/public/domaine).</span><span class="sxs-lookup"><span data-stu-id="6eb1c-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="6eb1c-128">S’il n’est pas joint à un domaine, il est possible que le réseau soit répertorié comme public et, dans ce cas, les règles de pare-feu installées avec le gestionnaire de statistiques ne s’appliquent pas par défaut.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="6eb1c-129">**4000** : impossible de télécharger les informations du serveur depuis l’écouteur (raison inconnue)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="6eb1c-130">**4001** : serveur introuvable dans la topologie de l’écouteur</span><span class="sxs-lookup"><span data-stu-id="6eb1c-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="6eb1c-131">Cette erreur se produit si le serveur parvient à se connecter à l’écouteur, mais que le serveur n’a pas été ajouté à la topologie dans le cache de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="6eb1c-132">Options de résolution :</span><span class="sxs-lookup"><span data-stu-id="6eb1c-132">Resolution options:</span></span>
    
  - <span data-ttu-id="6eb1c-p107">	Assurez-vous que vous avez suivi les instructions pour importer la topologie. Consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="6eb1c-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="6eb1c-135">Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, nœuds dans un cluster SQL AlwaysOn), vous devrez ajouter l’agent manuellement en suivant les instructions de la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="6eb1c-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="6eb1c-136">**4002** : mot de passe d’écouteur non valide</span><span class="sxs-lookup"><span data-stu-id="6eb1c-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="6eb1c-137">Le mot de passe chiffré que l’agent essaie d’utiliser ne correspond pas au mot de passe du service sur l’écouteur lui-même.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="6eb1c-138">Désinstallez l’agent et réinstallez-le en utilisant le bon mot de passe du service.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="6eb1c-139">**4003** : incompatibilité de l’empreinte numérique du certificat</span><span class="sxs-lookup"><span data-stu-id="6eb1c-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="6eb1c-140">Le certificat d’empreinte numérique fourni pour l’agent au moment de l’installation ne correspond pas à l’empreinte digitale du certificat utilisé par l’écouteur et par conséquent, la connexion est refusée.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="6eb1c-141">Désinstallez et réinstallez-le à l’aide de l’empreinte numérique de certificat appropriée.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="6eb1c-142">**4004** : HttpStatusCode ou réponse non valide</span><span class="sxs-lookup"><span data-stu-id="6eb1c-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="6eb1c-143">L’écouteur ne répond pas avec le statut attendu.  </span><span class="sxs-lookup"><span data-stu-id="6eb1c-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="6eb1c-144">En cas de connexion par proxy, vérifiez la configuration du proxy.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="6eb1c-145">Pour plus d’informations sur les problèmes liés à la configuration, consultez le journal des statistiques de l’ordinateur de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="6eb1c-146">**4005** : impossible de désérialiser le XML</span><span class="sxs-lookup"><span data-stu-id="6eb1c-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="6eb1c-147">Les informations de serveur sur le serveur d’écoute sont corrompues ou les versions des ordinateurs d’écoute et de l’agent sont incompatibles.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="6eb1c-148">Vérifiez que ces versions sont compatibles et qu’aucun problème n’apparaît dans le journal d’événements de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="6eb1c-149">Événements de l’écouteur</span><span class="sxs-lookup"><span data-stu-id="6eb1c-149">Listener events</span></span>
<span data-ttu-id="6eb1c-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="6eb1c-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="6eb1c-151">**10000** : échec du démarrage pour une raison inconnue (erreur irrécupérable qui provoque l’arrêt ou le blocage du service)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="6eb1c-152">**10001** : problème de configuration</span><span class="sxs-lookup"><span data-stu-id="6eb1c-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="6eb1c-153">En général, ce problème survient lorsque le fichier [listener_install_location]\PerfAgentListener.exe.config a été modifié à la main et ne peut pas être lu par l’application.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="6eb1c-154">**10002** : erreur d’initialisation de l’écouteur HTTP</span><span class="sxs-lookup"><span data-stu-id="6eb1c-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="6eb1c-155">Cet événement est généralement enregistré lorsque l’ACL de l’URL n’a pas été définie correctement pendant l’installation ou lorsque le certificat SSL n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="6eb1c-156">Vérifiez que le certificat dans votre configuration est valide.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="6eb1c-157">Si c’est le cas, réinstallez l’écouteur en suivant les instructions de la rubrique [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="6eb1c-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="6eb1c-158">**10003** : échec de Redis</span><span class="sxs-lookup"><span data-stu-id="6eb1c-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="6eb1c-159">**10004** : échec de l’infrastructure de mise en cache</span><span class="sxs-lookup"><span data-stu-id="6eb1c-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="6eb1c-160">**10007** : paramètres (enregistrés dans redis)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="6eb1c-161">L’écouteur n’a pas pu entrer en contact avec Redis ou extraire des données bien formées à partir de la mémoire cache et n’a donc pas pu démarrer.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="6eb1c-162">Assurez-vous que le service Redis est démarré et correctement configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="6eb1c-163">**10005** : analyse/récupération des informations du serveur</span><span class="sxs-lookup"><span data-stu-id="6eb1c-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="6eb1c-164">Les informations de topologie dans la mémoire cache de Redis ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="6eb1c-165">Dans un premier temps, essayez de redémarrer Redis et l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="6eb1c-166">Si l’erreur persiste, consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology) pour recréer les données de topologie.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="6eb1c-167">**10100** : interruption du test ping de Redis</span><span class="sxs-lookup"><span data-stu-id="6eb1c-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="6eb1c-168">**10101** : interruption continue du test ping de Redis (toutes les 60 secondes)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="6eb1c-169">**30100** : interruption du test ping de Redis restaurée</span><span class="sxs-lookup"><span data-stu-id="6eb1c-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="6eb1c-170">Ces événements sont consignés lorsque l’écouteur ne peut pas se connecter à Redis.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="6eb1c-171">Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écouteur et Redis est disponible.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="6eb1c-172">**10200** : interruption de l’écriture de Redis</span><span class="sxs-lookup"><span data-stu-id="6eb1c-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="6eb1c-173">**10201** : interruption continue de l’écriture de Redis (toutes les 60 secondes)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="6eb1c-174">**30100** : interruption de l’écriture de Redis résolue</span><span class="sxs-lookup"><span data-stu-id="6eb1c-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="6eb1c-175">Ces événements sont consignés lorsque l’écouteur ne peut pas écrire sur la mémoire cache de Redis.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="6eb1c-176">Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écouteur et Redis est disponible.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="6eb1c-177">**30000** : démarrage réussi</span><span class="sxs-lookup"><span data-stu-id="6eb1c-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="6eb1c-178">Enregistré à chaque démarrage de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="6eb1c-179">**22000** -échec de l’initialisation de l’agent Statistics Manager.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="6eb1c-180">**23000** : initialisation de EventLogQueryManager réussie (la première fois ou après un échec)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="6eb1c-181">**24000** : initialisation des informations de serveur réussie (la première fois ou après un échec)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="6eb1c-182">**25000** : l’écouteur est à nouveau en ligne après un échec de publication (ou première publication réussie)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="6eb1c-183">**5000** : début de la mise hors connexion de l’écouteur pour la publication de données</span><span class="sxs-lookup"><span data-stu-id="6eb1c-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="6eb1c-184">**5001** : l’écouteur est toujours hors connexion pour une longue période</span><span class="sxs-lookup"><span data-stu-id="6eb1c-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="6eb1c-185">Ces événements peuvent servir à surveiller/détecter/résoudre des problèmes.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="6eb1c-186">Problèmes de site web</span><span class="sxs-lookup"><span data-stu-id="6eb1c-186">Website issues</span></span>
<span data-ttu-id="6eb1c-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="6eb1c-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="6eb1c-188">Invites de connexion répétitives dans Chrome-il s’agit d’un bogue résolu dans la version 1,1.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="6eb1c-189">Vérifiez que vous avez effectué la mise à niveau vers la dernière version de Statistic Manager si vous voyez des invites de connexion répétées dans le navigateur Chrome.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="6eb1c-190">Pour vérifier la version du site web que vous exécutez, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6eb1c-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="6eb1c-191">	Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut)</span><span class="sxs-lookup"><span data-stu-id="6eb1c-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="6eb1c-192">Cliquez avec le bouton droit de la souris sur StatsManHubWebSite.dll pour afficher ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="6eb1c-193">Si un ordinateur est introuvable dans l’affichage en mode Paysage ou en mode Détails des compteurs des KHI, assurez-vous qu’il est membre d’un site et d’un pool.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="6eb1c-194">Si ce n’est pas le cas, il n’apparaîtra pas dans ces affichages.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="6eb1c-195">Pour plus d’informations sur la définition dans la topologie d’un site et d’un pool pour un serveur, consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="6eb1c-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="6eb1c-196">La version du produit s’affiche dans les détails de la description.</span><span class="sxs-lookup"><span data-stu-id="6eb1c-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="6eb1c-197">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="6eb1c-197">For more information</span></span>
<span data-ttu-id="6eb1c-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="6eb1c-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="6eb1c-199">Pour plus d'informations, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="6eb1c-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="6eb1c-200">Planifier le gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6eb1c-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="6eb1c-201">Déploiement du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6eb1c-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="6eb1c-202">Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6eb1c-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
