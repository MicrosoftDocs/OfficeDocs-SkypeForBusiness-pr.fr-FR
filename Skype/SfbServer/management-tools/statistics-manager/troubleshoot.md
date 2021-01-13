---
title: Résolution des problèmes du Gestionnaire de statistiques pour Skype Entreprise Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Résumé : Lisez cette rubrique pour résoudre les problèmes de déploiement du Gestionnaire de statistiques pour Skype Entreprise Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821774"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="2d41f-103">Résolution des problèmes du Gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2d41f-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="2d41f-104">**Résumé :** Lisez cette rubrique pour résoudre les problèmes de déploiement du Gestionnaire de statistiques pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="2d41f-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="2d41f-105">Cette rubrique décrit comment résoudre les problèmes de déploiement de votre gestionnaire de statistiques en décrivant les événements que vous pouvez voir dans le journal des événements d’application et les actions appropriées que vous pouvez prendre pour rectifier l’événement.</span><span class="sxs-lookup"><span data-stu-id="2d41f-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="2d41f-106">Cette rubrique comprend les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="2d41f-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="2d41f-107">Événements de l’agent</span><span class="sxs-lookup"><span data-stu-id="2d41f-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="2d41f-108">Événements d’écoute</span><span class="sxs-lookup"><span data-stu-id="2d41f-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="2d41f-109">Problèmes de site web</span><span class="sxs-lookup"><span data-stu-id="2d41f-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="2d41f-110">Événements de l’agent</span><span class="sxs-lookup"><span data-stu-id="2d41f-110">Agent events</span></span>
<span data-ttu-id="2d41f-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="2d41f-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="2d41f-112">**1000** — Impossible de configurer le limiteur de processeur (Objet travail) — Raison inconnue</span><span class="sxs-lookup"><span data-stu-id="2d41f-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="2d41f-113">**1001** — La limitation des processus n’est pas autorisée sur le processus (probablement déjà dans un objet Job)</span><span class="sxs-lookup"><span data-stu-id="2d41f-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="2d41f-114">L’agent s’exécute à l’intérieur d’un objet de travail Windows pour limiter automatiquement son encombrement mémoire.</span><span class="sxs-lookup"><span data-stu-id="2d41f-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="2d41f-115">Si l’agent ne démarre pas et que ces entrées d’événement sont présentes dans le journal des événements, l’objet de travail ne peut pas être inséré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d41f-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="2d41f-116">Pour contourner ce besoin, vous pouvez supprimer la limite de mémoire supérieure en modifiant une valeur dans le fichier de config :</span><span class="sxs-lookup"><span data-stu-id="2d41f-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="2d41f-117">Recherchez « MaxProcessMemoryMB » et modifiez la valeur sur « 0 », comme illustré :</span><span class="sxs-lookup"><span data-stu-id="2d41f-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="2d41f-118">Si cette modification est faite, l’agent consomme généralement toujours 100 Mo de mémoire, mais il ne sera pas forcément limité à 300 Mo comme c’est le cas par \< défaut.</span><span class="sxs-lookup"><span data-stu-id="2d41f-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="2d41f-119">Si cette modification est réalisée, nous vous recommandons de surveiller attentivement l’utilisation de la mémoire pour vous assurer que l’agent ne consomme pas une grande quantité de mémoire sur son ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="2d41f-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="2d41f-120">**2000** — Échec de l’initialisation du client</span><span class="sxs-lookup"><span data-stu-id="2d41f-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="2d41f-121">**2001**— Aucune connexion au service n’a pu être réalisée sur une adresse IP source</span><span class="sxs-lookup"><span data-stu-id="2d41f-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="2d41f-122">Si l’agent ne peut pas se connecter à l’ordinateur d’écoute, vérifiez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2d41f-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="2d41f-123">Assurez-vous que le service d’écoute est en cours d’exécution sur l’ordinateur d’écoute.</span><span class="sxs-lookup"><span data-stu-id="2d41f-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="2d41f-124">Si ce n’est pas le cas, assurez-vous que Redis est en cours d’exécution sur ce serveur, puis redémarrez le service d’écoute.</span><span class="sxs-lookup"><span data-stu-id="2d41f-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="2d41f-125">Consultez le journal des événements du Gestionnaire de statistiques sur l’ordinateur d’écoute pour vous assurer qu’il n’y a aucun problème avec le service d’écoute du gestionnaire de statistiques lui-même.</span><span class="sxs-lookup"><span data-stu-id="2d41f-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="2d41f-126">Utilisez un outil de connectivité tel que telnet pour vérifier la connectivité de l’ordinateur agent à l’écoute sur le port correct.</span><span class="sxs-lookup"><span data-stu-id="2d41f-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="2d41f-127">Si ce n’est pas le cas, assurez-vous que la règle de pare-feu entrant est activée sur l’ordinateur d’écoute pour le type de réseau à qui l’ordinateur d’écoute est connecté (privé/public/domaine).</span><span class="sxs-lookup"><span data-stu-id="2d41f-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="2d41f-128">Si l’ordinateur d’écoute n’est pas joint à un domaine, le réseau peut être répertorié comme public et, dans ce cas, les règles de pare-feu installées avec le Gestionnaire de statistiques ne s’appliqueront pas par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d41f-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="2d41f-129">**4000** : échec du téléchargement des informations sur le serveur à partir de l’écoute (raison inconnue)</span><span class="sxs-lookup"><span data-stu-id="2d41f-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="2d41f-130">**4001** — Serveur in trouvé dans la topologie d’écoute</span><span class="sxs-lookup"><span data-stu-id="2d41f-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="2d41f-131">Cette erreur se produit si le serveur se connecte avec succès à l’écoute, mais que le serveur n’a pas été ajouté à la topologie dans le cache de l’écoute.</span><span class="sxs-lookup"><span data-stu-id="2d41f-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="2d41f-132">Options de résolution :</span><span class="sxs-lookup"><span data-stu-id="2d41f-132">Resolution options:</span></span>
    
  - <span data-ttu-id="2d41f-133">Assurez-vous que vous avez suivi les instructions d’importation de la topologie.</span><span class="sxs-lookup"><span data-stu-id="2d41f-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="2d41f-134">Voir [Importer la topologie.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="2d41f-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="2d41f-135">Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, les nodes dans un [](deploy.md#BKMK_ImportTopology)cluster SQL AlwaysOn), vous devez ajouter l’agent manuellement en suivant les instructions de l’importation de la topologie.</span><span class="sxs-lookup"><span data-stu-id="2d41f-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="2d41f-136">**4002** — Mot de passe d’écoute non valide</span><span class="sxs-lookup"><span data-stu-id="2d41f-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="2d41f-137">Le mot de passe chiffré que l’agent tente d’utiliser ne correspond pas au mot de passe du service sur l’écoute proprement dite.</span><span class="sxs-lookup"><span data-stu-id="2d41f-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="2d41f-138">Désinstallez l’agent et réinstallez-le à l’aide du mot de passe de service correct.</span><span class="sxs-lookup"><span data-stu-id="2d41f-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="2d41f-139">**4003** — Non-matage de l’empreinte numérique du certificat</span><span class="sxs-lookup"><span data-stu-id="2d41f-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="2d41f-140">L’empreinte numérique de certificat donnée à l’agent au moment de l’installation ne correspond pas à l’empreinte du certificat que l’écoute utilise actuellement et par conséquent, la connexion sera refusée.</span><span class="sxs-lookup"><span data-stu-id="2d41f-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="2d41f-141">Désinstallez l’agent et réinstallez-le à l’aide de l’empreinte de certificat correcte.</span><span class="sxs-lookup"><span data-stu-id="2d41f-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="2d41f-142">**4004** — Réponse non valide ou HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="2d41f-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="2d41f-143">L’écoute ne répond pas avec un état attendu.</span><span class="sxs-lookup"><span data-stu-id="2d41f-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="2d41f-144">Si la connexion est proxy, vérifiez la configuration du proxy.</span><span class="sxs-lookup"><span data-stu-id="2d41f-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="2d41f-145">Vérifiez le journal StatsMan de l’ordinateur d’écoute pour les problèmes de configuration.</span><span class="sxs-lookup"><span data-stu-id="2d41f-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="2d41f-146">**4005** — Impossible de désérialiser le XML</span><span class="sxs-lookup"><span data-stu-id="2d41f-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="2d41f-147">Les informations du serveur sur le serveur d’écoute sont endommagées ou il se peut qu’il y a une insérialisation de version entre l’agent et les ordinateurs d’écoute.</span><span class="sxs-lookup"><span data-stu-id="2d41f-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="2d41f-148">Assurez-vous que les versions correspondent et vérifiez le journal des événements d’écoute pour les problèmes.</span><span class="sxs-lookup"><span data-stu-id="2d41f-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="2d41f-149">Événements d’écoute</span><span class="sxs-lookup"><span data-stu-id="2d41f-149">Listener events</span></span>
<span data-ttu-id="2d41f-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="2d41f-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="2d41f-151">**10000** — Échec du démarrage Pour une raison inconnue (ces erreurs sont irrécables et le service s’arrête/se crashe par conséquent)</span><span class="sxs-lookup"><span data-stu-id="2d41f-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="2d41f-152">**10001** — Problème de configuration</span><span class="sxs-lookup"><span data-stu-id="2d41f-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="2d41f-153">En règle générale, cela se produit lorsque le fichier [listener_install_location]\PerfAgentListener.exe.config a été modifié à la main et ne peut pas être lu par l’application.</span><span class="sxs-lookup"><span data-stu-id="2d41f-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="2d41f-154">**10002** — Erreur d’initialisation de l’écoute HTTP</span><span class="sxs-lookup"><span data-stu-id="2d41f-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="2d41f-155">Cet événement est généralement enregistré lorsque l’ACL de l’URL n’a pas été correctement définie lors de l’installation ou que le cert SSL n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="2d41f-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="2d41f-156">Assurez-vous que le certificat de votre configuration est valide.</span><span class="sxs-lookup"><span data-stu-id="2d41f-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="2d41f-157">Si c’est le cas, réinstallez l’écoute en suivant les instructions de [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="2d41f-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="2d41f-158">**10003** — Échec de Redis</span><span class="sxs-lookup"><span data-stu-id="2d41f-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="2d41f-159">**10004** : défaillance de l’infrastructure de mise en cache</span><span class="sxs-lookup"><span data-stu-id="2d41f-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="2d41f-160">**10007** — Paramètres (stockés dans redis)</span><span class="sxs-lookup"><span data-stu-id="2d41f-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="2d41f-161">L’écouteur n’a pas pu contacter Redis ou récupérer des données bien formées à partir du cache et n’a pas pu démarrer.</span><span class="sxs-lookup"><span data-stu-id="2d41f-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="2d41f-162">Assurez-vous que le service Redis est démarré et configuré correctement sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="2d41f-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="2d41f-163">**10005 —** Récupération/extraction/extraction des informations du serveur</span><span class="sxs-lookup"><span data-stu-id="2d41f-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="2d41f-164">Les informations de topologie dans le cache Redis ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="2d41f-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="2d41f-165">Tout d’abord, essayez de redémarrer Redis et l’écoute.</span><span class="sxs-lookup"><span data-stu-id="2d41f-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="2d41f-166">Si l’erreur persiste, voir [Importer la topologie](deploy.md#BKMK_ImportTopology) pour recréer les données de topologie.</span><span class="sxs-lookup"><span data-stu-id="2d41f-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="2d41f-167">**10100** — Panne PING Redis</span><span class="sxs-lookup"><span data-stu-id="2d41f-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="2d41f-168">**10101** — Panne continue de redis PING (toutes les 60 secondes)</span><span class="sxs-lookup"><span data-stu-id="2d41f-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="2d41f-169">**30100** — Restauration de la panne PING redis</span><span class="sxs-lookup"><span data-stu-id="2d41f-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="2d41f-170">Ceux-ci sont enregistrés lorsque l’écoute ne peut pas se connecter à Redis.</span><span class="sxs-lookup"><span data-stu-id="2d41f-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="2d41f-171">Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écoute et Redis est disponible.</span><span class="sxs-lookup"><span data-stu-id="2d41f-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="2d41f-172">**10200** — Panne d’écriture de Redis</span><span class="sxs-lookup"><span data-stu-id="2d41f-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="2d41f-173">**10201** — La panne d’écriture de Redis a continué (toutes les 60 secondes)</span><span class="sxs-lookup"><span data-stu-id="2d41f-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="2d41f-174">**30100** — Panne d’écriture De Redis résolue</span><span class="sxs-lookup"><span data-stu-id="2d41f-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="2d41f-175">Ceux-ci sont enregistrés lorsque l’écoute ne peut pas écrire dans le cache Redis.</span><span class="sxs-lookup"><span data-stu-id="2d41f-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="2d41f-176">Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écoute et Redis est disponible.</span><span class="sxs-lookup"><span data-stu-id="2d41f-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="2d41f-177">**30000** — Démarré avec succès</span><span class="sxs-lookup"><span data-stu-id="2d41f-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="2d41f-178">Journalisé chaque fois que l’écoute est démarrée.</span><span class="sxs-lookup"><span data-stu-id="2d41f-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="2d41f-179">**22000** : l’initialisation de l’agent du gestionnaire de statistiques a réussi.</span><span class="sxs-lookup"><span data-stu-id="2d41f-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="2d41f-180">**23000** — Initialisation de EventLogQueryManager réussi (première fois ou après un échec)</span><span class="sxs-lookup"><span data-stu-id="2d41f-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="2d41f-181">**24000** : l’initialisation de serverinfo a réussi (première fois ou après échec)</span><span class="sxs-lookup"><span data-stu-id="2d41f-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="2d41f-182">**25000 — L’écoute** est de nouveau en ligne après un échec de publication (ou une première publication réussie)</span><span class="sxs-lookup"><span data-stu-id="2d41f-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="2d41f-183">**5000** : début de l’écoute hors connexion pour la publication de données</span><span class="sxs-lookup"><span data-stu-id="2d41f-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="2d41f-184">**5001** — L’écoute est toujours hors connexion pendant une période prolongée</span><span class="sxs-lookup"><span data-stu-id="2d41f-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="2d41f-185">Ces événements peuvent être utiles pour surveiller/alerter/effacer les problèmes.</span><span class="sxs-lookup"><span data-stu-id="2d41f-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="2d41f-186">Problèmes de site web</span><span class="sxs-lookup"><span data-stu-id="2d41f-186">Website issues</span></span>
<span data-ttu-id="2d41f-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2d41f-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="2d41f-188">Invites de connexion répétitives dans Chrome : il s’agissait d’un bogue qui a été résolu dans la version 1.1.</span><span class="sxs-lookup"><span data-stu-id="2d41f-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="2d41f-189">Assurez-vous que vous avez mis à niveau vers la dernière version du Gestionnaire de statistiques si vous voyez des invites de connexion répétées dans le navigateur Chrome.</span><span class="sxs-lookup"><span data-stu-id="2d41f-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="2d41f-190">Pour vérifier la version du site web que vous exécutez :</span><span class="sxs-lookup"><span data-stu-id="2d41f-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="2d41f-191">Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut)</span><span class="sxs-lookup"><span data-stu-id="2d41f-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="2d41f-192">Cliquez avec le bouton droit StatsManHubWebSite.dll et affichez ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="2d41f-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="2d41f-193">Si vous ne pouvez pas trouver un ordinateur dans l’affichage Paysage KHI ou l’affichage Détails du compteur, assurez-vous qu’il est membre d’un site et d’un pool.</span><span class="sxs-lookup"><span data-stu-id="2d41f-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="2d41f-194">Si ce n’est pas le cas, il n’apparaîtra pas dans ces affichages.</span><span class="sxs-lookup"><span data-stu-id="2d41f-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="2d41f-195">Pour plus d’informations sur la définition d’un site et d’un pool pour un serveur dans la topologie, voir [Importer la topologie.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="2d41f-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="2d41f-196">La version du produit s’affiche dans les détails de description.</span><span class="sxs-lookup"><span data-stu-id="2d41f-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="2d41f-197">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="2d41f-197">For more information</span></span>
<span data-ttu-id="2d41f-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2d41f-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="2d41f-199">Pour plus d'informations, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="2d41f-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="2d41f-200">Planifier le gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2d41f-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="2d41f-201">Déploiement du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2d41f-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="2d41f-202">Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2d41f-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
