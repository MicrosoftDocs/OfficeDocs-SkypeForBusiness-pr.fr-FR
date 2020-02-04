---
title: Notes de publication de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10961f0a8e59fe1d0dc0268b430f37fd294252b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="32d63-102">Notes de publication de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32d63-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32d63-103">_**Dernière modification de la rubrique :** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="32d63-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="32d63-104">Bienvenue dans les notes de publication de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="32d63-105">Pour plus d’informations sur les problèmes connus concernant Lync Server 2013, consultez ce fichier.</span><span class="sxs-lookup"><span data-stu-id="32d63-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="32d63-106">À propos de ce document</span><span class="sxs-lookup"><span data-stu-id="32d63-106">About this document</span></span>

<span data-ttu-id="32d63-107">Ce document contient des informations importantes à connaître avant de déployer et d’utiliser Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="32d63-108">Pour plus d’informations sur Lync Server 2013, voir la documentation [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="32d63-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="32d63-109">Ce document contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="32d63-110">Client 2013 Lync</span><span class="sxs-lookup"><span data-stu-id="32d63-110">Lync 2013 client</span></span>

  - <span data-ttu-id="32d63-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="32d63-111">Lync Server</span></span>

  - <span data-ttu-id="32d63-112">Installation</span><span class="sxs-lookup"><span data-stu-id="32d63-112">Installation</span></span>

  - <span data-ttu-id="32d63-113">Mobilité</span><span class="sxs-lookup"><span data-stu-id="32d63-113">Mobility</span></span>

  - <span data-ttu-id="32d63-114">Conférence</span><span class="sxs-lookup"><span data-stu-id="32d63-114">Conferencing</span></span>

  - <span data-ttu-id="32d63-115">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="32d63-115">Enterprise Voice</span></span>

  - <span data-ttu-id="32d63-116">Présence</span><span class="sxs-lookup"><span data-stu-id="32d63-116">Presence</span></span>

  - <span data-ttu-id="32d63-117">Application Response Group et application Parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="32d63-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="32d63-118">Panneau de configuration Lync Server, générateur de topologie et outil de planification</span><span class="sxs-lookup"><span data-stu-id="32d63-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="32d63-119">Localisation</span><span class="sxs-lookup"><span data-stu-id="32d63-119">Localization</span></span>

  - <span data-ttu-id="32d63-120">Reproduction</span><span class="sxs-lookup"><span data-stu-id="32d63-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="32d63-121">Client 2013 Lync</span><span class="sxs-lookup"><span data-stu-id="32d63-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="32d63-122">Échec du transfert d’un fichier dans un message instantané si le fichier est ouvert dans une autre application</span><span class="sxs-lookup"><span data-stu-id="32d63-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="32d63-123">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-123">**Issue:**</span></span>

<span data-ttu-id="32d63-124">Si vous essayez de transférer un fichier, tel qu’un document Word, en l’incluant dans un message instantané à un autre utilisateur Lync, le transfert semble aboutir, mais il se peut que le transfert du fichier échoue.</span><span class="sxs-lookup"><span data-stu-id="32d63-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="32d63-125">Une icône pour le type de fichier s’affichera dans le client Lync, mais le fichier ne peut pas être ouvert par le destinataire prévu.</span><span class="sxs-lookup"><span data-stu-id="32d63-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="32d63-126">Aucun message d’erreur ne s’affiche pour vous signaler que le transfert a échoué.</span><span class="sxs-lookup"><span data-stu-id="32d63-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="32d63-127">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-127">**Workaround:**</span></span>

<span data-ttu-id="32d63-128">Pour contourner ce problème, fermez l’application ou le fichier ouvert qui s’ouvre avant d’essayer de transférer le fichier dans un message instantané.</span><span class="sxs-lookup"><span data-stu-id="32d63-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="32d63-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="32d63-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="32d63-130">Si la réplication des données du service de stockage Lync Server échoue, les administrateurs doivent vérifier les compteurs de performance pour les éléments de la file d’attente du service de stockage obsolète</span><span class="sxs-lookup"><span data-stu-id="32d63-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="32d63-131">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-131">**Issue:**</span></span>

<span data-ttu-id="32d63-132">Le service de stockage Lync Server utilise Windows fabric pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="32d63-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="32d63-133">Si les données sont supprimées sur un serveur frontal principal, mais que la suppression d’un serveur frontal secondaire échoue (par exemple, en cas d’arrêt inattendu ou d’erreur sur le serveur frontal), les données peuvent être laissées au-dessus et « orphelines ».</span><span class="sxs-lookup"><span data-stu-id="32d63-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="32d63-134">Les données orphelines peuvent entraîner une dégradation des performances et gaspiller l’espace disque.</span><span class="sxs-lookup"><span data-stu-id="32d63-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="32d63-135">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-135">**Workaround:**</span></span>

<span data-ttu-id="32d63-136">Pour contourner ce problème, si les événements LYSS\_DB\_de\_la\_base de données (ID = 32058)\_et\_LYSS\_DB\_utilisés comme Critical (ID = 32059) sont générés dans le journal des événements, les administrateurs doivent vérifier le compteur de performance du serveur frontal sous **ls : LYSS-API du service** de stockage dont le nom est **LYSS**.</span><span class="sxs-lookup"><span data-stu-id="32d63-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="32d63-137">Si ce compteur de performance a une valeur élevée (par exemple, supérieure à 50 000), l’administrateur doit exécuter l’outil CleanuUpStorageServiceData. exe dans le kit de ressources de Lync Server 2013, qui supprimera toutes les données orphelines du pool.</span><span class="sxs-lookup"><span data-stu-id="32d63-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="32d63-138">Pour plus d’informations sur l’outil, voir la documentation du kit de ressources de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="32d63-139">Chaque fois que la configuration de l’adresse IP d’un serveur ou d’un pool est modifiée, vous devez redémarrer les services Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="32d63-140">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-140">**Issue:**</span></span>

<span data-ttu-id="32d63-141">Lorsque la configuration de l’adresse IP d’un déploiement de Lync Server 2013 est modifiée (par exemple, le passage d’une pile IPv4 à une pile double ou d’une pile passant à une pile IPv6), tous les composants serveur ne prennent pas en main la modification de la configuration tant qu’il n’est pas redémarré.</span><span class="sxs-lookup"><span data-stu-id="32d63-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="32d63-142">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-142">**Workaround:**</span></span>

<span data-ttu-id="32d63-143">Pour contourner ce problème, redémarrez les services Lync Server suite à la modification de la configuration d’adresse IP pour le déploiement.</span><span class="sxs-lookup"><span data-stu-id="32d63-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="32d63-144">Pour cela, exécutez les applets de commande suivantes dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="32d63-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="32d63-145">L’applet de connexion de transaction synthétique de conférence rendez-vous n’est plus disponible dans le pack d’administration 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="32d63-146">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-146">**Issue:**</span></span>

<span data-ttu-id="32d63-147">L’applet de **contrôle** de conférence rendez-vous de la Conférence rendez-vous n’est plus disponible dans le pack d’administration 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="32d63-148">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-148">**Workaround:**</span></span>

<span data-ttu-id="32d63-149">L’utilisation de l’applet de **contrôle** de conférence rendez-vous est prise en charge uniquement en interne pour une entreprise.</span><span class="sxs-lookup"><span data-stu-id="32d63-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="32d63-150">Les administrateurs peuvent continuer à utiliser l’applet de cmdlet dans Lync Server Management Shell à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="32d63-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="32d63-151">Le cas échéant, une entreprise peut également développer un pack d’administration privé pour exécuter l’applet de demande en interne.</span><span class="sxs-lookup"><span data-stu-id="32d63-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="32d63-152">Le service de journalisation centralisé s’arrête si le trafic réseau a été interrompu lors de la copie des fichiers journaux vers le partage réseau.</span><span class="sxs-lookup"><span data-stu-id="32d63-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="32d63-153">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-153">**Issue:**</span></span>

<span data-ttu-id="32d63-154">Lorsque le service de journalisation centralisé est configuré pour utiliser un chemin d’accès réseau (la valeur du paramètre CacheFileNetworkFolder de l’applet de connexion **Get-CsClsConfiguration** est un chemin UNC valide), les fichiers journaux mises en cache sont copiés sur le partage réseau.</span><span class="sxs-lookup"><span data-stu-id="32d63-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="32d63-155">S’il y a un problème de trafic réseau lors de la copie des fichiers, une exception se produit, ce qui entraîne l’arrêt du service de journalisation centralisé.</span><span class="sxs-lookup"><span data-stu-id="32d63-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="32d63-156">Le service est configuré pour un démarrage automatique à trois reprises, de sorte que le service récupère les trois premières exceptions.</span><span class="sxs-lookup"><span data-stu-id="32d63-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="32d63-157">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-157">**Workaround:**</span></span>

<span data-ttu-id="32d63-158">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-158">There is no workaround for this issue.</span></span> <span data-ttu-id="32d63-159">Pour identifier le problème, analysez le journal des événements pour l’ID d’événement 7031 à partir du « gestionnaire de contrôle de service » qui consigne le service « Lync Server central Logging agent » s’est arrêté de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="32d63-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="32d63-160">S’il s’agit de plus de trois fois, redémarrez manuellement le service à l’aide de l’applet de passe **Start-CsWindowService** .</span><span class="sxs-lookup"><span data-stu-id="32d63-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="32d63-161">Les éléments de la file d’attente du service de stockage doivent être importés manuellement</span><span class="sxs-lookup"><span data-stu-id="32d63-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="32d63-162">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-162">**Issue:**</span></span>

<span data-ttu-id="32d63-163">Lync Server 2013 stocke les données relatives aux conférences et à la messagerie instantanée, telles que les messages archivés et l’enregistrement des détails des appels, sur une base de données sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="32d63-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="32d63-164">Les données sont stockées dans la base de données pendant son traitement avant d’être remises à la destination prévue.</span><span class="sxs-lookup"><span data-stu-id="32d63-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="32d63-165">Pour améliorer les performances, Lync Server 2013 exporte périodiquement les éléments de la file d’attente à partir de la base de données locale qui ne sont pas traités pendant une période prolongée et les enregistre sur le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="32d63-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="32d63-166">Si le magasin de fichiers n’est pas disponible, les éléments sont stockés sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="32d63-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="32d63-167">La même opération se produit afin d’éviter les pertes de données pendant le basculement du pool.</span><span class="sxs-lookup"><span data-stu-id="32d63-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="32d63-168">Pendant l’opération d’exportation, le service de stockage du serveur Lync enregistre chaque étape du journal des événements avec les ID d’événement de 32075 (l’opération de vidage complète est lancée), 32076 (vidage complet est effectué), 32082 (le vidage du niveau de maintenance est démarré), 32083 (vidage de niveau de maintenance est terminé), 32089 (le vidage s’est produit en raison du remplissage de la base de données).</span><span class="sxs-lookup"><span data-stu-id="32d63-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="32d63-169">Ces données ne seront pas automatiquement importées sur le système pour être traitées et transmises à la destination finale (SQL Server ou Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="32d63-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="32d63-170">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-170">**Workaround:**</span></span>

<span data-ttu-id="32d63-171">Pour importer les données dans le système, les administrateurs doivent utiliser l’outil ImportStorageServiceData dans le kit de ressources de Lync Server, qui ajoute les données dans le système afin qu’elles soient traitées et transmises à la destination finale.</span><span class="sxs-lookup"><span data-stu-id="32d63-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="32d63-172">Les recherches dans le carnet d’adresses Web peuvent échouer si la valeur par défaut de UseNormalizationRules est remplacée par false.</span><span class="sxs-lookup"><span data-stu-id="32d63-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="32d63-173">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-173">**Issue:**</span></span>

<span data-ttu-id="32d63-174">Si la valeur par défaut de UseNormalizationRules est remplacée par false, les recherches de requête sur le Web du carnet d’adresses échouent.</span><span class="sxs-lookup"><span data-stu-id="32d63-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="32d63-175">Après la modification de la valeur par défaut, les utilisateurs du client Lync ne seront pas en mesure d’utiliser la requête Web du carnet d’adresses Lync pour rechercher des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="32d63-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="32d63-176">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-176">**Workaround:**</span></span>

<span data-ttu-id="32d63-177">Si la valeur par défaut de UseNormalizationRules est définie sur false, afin que les utilisateurs puissent utiliser des numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans Lync Server 2013 appliquant des règles de normalisation, contourner ce problème en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="32d63-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="32d63-178">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="32d63-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="32d63-179">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="32d63-180">Si votre déploiement inclut uniquement les serveurs Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de UseNormalizationRules et IgnoreGenericRules sur true :</span><span class="sxs-lookup"><span data-stu-id="32d63-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="32d63-181">Si votre déploiement inclut une combinaison de Lync Server 2013 et de Lync Server 2010 ou Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="32d63-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="32d63-182">Attendez la fin de la réplication CMS sur tous les pools.</span><span class="sxs-lookup"><span data-stu-id="32d63-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="32d63-183">Modifiez le fichier de règles de normalisation du téléphone pour votre déploiement pour effacer le contenu.</span><span class="sxs-lookup"><span data-stu-id="32d63-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="32d63-184">Le fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="32d63-185">Si le fichier n’est pas présent, créez-en un dans la section\_«\_\_règles\_de normalisation des numéros de téléphone de l’entreprise ».</span><span class="sxs-lookup"><span data-stu-id="32d63-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="32d63-186">Attendez quelques minutes pour que tous les pools du serveur principal lisent les nouveaux fichiers.</span><span class="sxs-lookup"><span data-stu-id="32d63-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="32d63-187">Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="32d63-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="32d63-188">Le message d’erreur de serveur du carnet d’adresses 21054 est généré quotidiennement pour chaque pool 2013 de Lync</span><span class="sxs-lookup"><span data-stu-id="32d63-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="32d63-189">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-189">**Issue:**</span></span>

<span data-ttu-id="32d63-190">Le serveur du carnet d’adresses Lync Server 2013 génère un événement d’erreur 21054 une fois tous les jours lors de la maintenance quotidienne.</span><span class="sxs-lookup"><span data-stu-id="32d63-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="32d63-191">Cette erreur est également générée chaque fois qu’un administrateur exécute l’applet de connexion **Update-csAddressBook** , même si la mise à jour est réussie.</span><span class="sxs-lookup"><span data-stu-id="32d63-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="32d63-192">Toutefois, l’événement d’erreur peut être ignoré en toute sécurité lorsque la mise à jour est réussie.</span><span class="sxs-lookup"><span data-stu-id="32d63-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="32d63-193">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-193">**Workaround:**</span></span>

<span data-ttu-id="32d63-194">Lorsque vous rencontrez cet événement d’erreur, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32d63-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="32d63-195">Si l’applet de passe signale qu’il n’y a aucun objet non indexé ou abandonné, l’événement d’erreur 21054 peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="32d63-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="32d63-196">Par ailleurs, le témoin d’intégrité principal (KHI) « les utilisateurs du carnet d’adresses correctement indexé » doit être désactivé dans System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="32d63-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="32d63-197">Les requêtes peuvent échouer lorsque le protocole IPv6 est configuré sur un pool de bords</span><span class="sxs-lookup"><span data-stu-id="32d63-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="32d63-198">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-198">**Issue:**</span></span>

<span data-ttu-id="32d63-199">Lorsque le protocole IPv6 est configuré sur un pool Edge, certaines requêtes vers le pool Edge peuvent échouer.</span><span class="sxs-lookup"><span data-stu-id="32d63-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="32d63-200">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-200">**Workaround:**</span></span>

<span data-ttu-id="32d63-201">Pour contourner ce problème, ne configurez pas de pool Edge avec IPv6.</span><span class="sxs-lookup"><span data-stu-id="32d63-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="32d63-202">L’applet de passe Invoke-csPoolFailback risque de ne pas fonctionner lors du retour automatique de la liste</span><span class="sxs-lookup"><span data-stu-id="32d63-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="32d63-203">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-203">**Issue:**</span></span>

<span data-ttu-id="32d63-204">Lorsque vous tentez de basculer sur un pool, l’applet de demande **Invoke-csPoolFailback** risque d’échouer en raison de l’erreur « Échec de l’accomplissement du processus d’hydratation après plusieurs tentatives ».</span><span class="sxs-lookup"><span data-stu-id="32d63-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="32d63-205">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-205">**Workaround:**</span></span>

<span data-ttu-id="32d63-206">Pour contourner ce problème, exécutez de nouveau l’applet de passe et attendez que l’applet de passe réussisse.</span><span class="sxs-lookup"><span data-stu-id="32d63-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="32d63-207">Notez que le processus de restauration automatique peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="32d63-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="32d63-208">Un délai de 60 minutes doit être nécessaire pour un pool avec des utilisateurs 20 000.</span><span class="sxs-lookup"><span data-stu-id="32d63-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="32d63-209">Une perte de données est susceptible de se produire lorsque vous ajoutez un serveur frontal à une réserve déjà établie-hybride, Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="32d63-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="32d63-210">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-210">**Issue:**</span></span>

<span data-ttu-id="32d63-211">Ce problème peut se produire dans un environnement dans lequel un pool a plusieurs serveurs frontaux et que vous redémarrez l’un des serveurs frontaux ou ajoutez un nouveau serveur frontal qui ne faisait pas partie de la liste.</span><span class="sxs-lookup"><span data-stu-id="32d63-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="32d63-212">Les utilisateurs dont les données sont archivées peuvent faire l’objet d’une perte de données jusqu’à ce qu’une distribution stable de l’archivage des données soit établie pour le pool.</span><span class="sxs-lookup"><span data-stu-id="32d63-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="32d63-213">Ce délai de perte de données potentiel est limité à 15 minutes pour les conversations de personne à personne et de 30 minutes pour les conférences.</span><span class="sxs-lookup"><span data-stu-id="32d63-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="32d63-214">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-214">**Workaround:**</span></span>

<span data-ttu-id="32d63-215">Lorsque vous effectuez une maintenance, au lieu de démarrer les serveurs frontaux dans le groupe, vous devez basculer le pool vers un autre, puis effectuer des tâches de maintenance sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="32d63-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="32d63-216">Vous pouvez également rendre le Service indisponible avant d’effectuer des tâches de maintenance, puis restaurer la disponibilité au terme de la maintenance.</span><span class="sxs-lookup"><span data-stu-id="32d63-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="32d63-217">Les administrateurs ne peuvent pas obtenir le nombre de licenciés à l’aide de l’applet de passe Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="32d63-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="32d63-218">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-218">**Issue:**</span></span>

<span data-ttu-id="32d63-219">Les administrateurs ne peuvent pas obtenir une utilisation précise des licences client en utilisant l’applet de commande **Get-CsClientAccessLicense** .</span><span class="sxs-lookup"><span data-stu-id="32d63-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="32d63-220">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-220">**Workaround:**</span></span>

<span data-ttu-id="32d63-221">Pour vérifier le type de licence serveur, vous pouvez exécuter l’applet de contrôle **Get-CsService** pour récupérer les noms de domaine complets (FDQNs) de toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="32d63-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="32d63-222">Si le nom de domaine complet du serveur principal est identique à celui de la base de données principale, la licence est une licence Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="32d63-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="32d63-223">Dans le cas contraire, la licence est une licence Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="32d63-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="32d63-224">Le nombre de licenciés du client n’est pas correctement signalé</span><span class="sxs-lookup"><span data-stu-id="32d63-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="32d63-225">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-225">**Issue:**</span></span>

<span data-ttu-id="32d63-226">Lorsque vous déterminez le nombre de licences clientes, vous pouvez observer les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="32d63-227">**Nombre de licences inexactes pour les utilisateurs mobiles**</span><span class="sxs-lookup"><span data-stu-id="32d63-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="32d63-228">Le nombre de licences est basé sur le nombre d’adresses IP uniques pour les utilisateurs de périphériques.</span><span class="sxs-lookup"><span data-stu-id="32d63-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="32d63-229">Le nombre de licences sera limité des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="32d63-230">Les licences seront surconsidérées si l’adresse IP de l’utilisateur change au cours des sessions Lync.</span><span class="sxs-lookup"><span data-stu-id="32d63-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="32d63-231">Cela peut se produire lorsqu’un utilisateur se connecte à Lync Server à partir de plusieurs emplacements auprès d’un client de bureau.</span><span class="sxs-lookup"><span data-stu-id="32d63-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="32d63-232">Les licences seront sous-comptabilisées si un utilisateur se connecte à un client mobile, car l’adresse IP de l’appareil ne peut pas être déterminée.</span><span class="sxs-lookup"><span data-stu-id="32d63-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="32d63-233">**Les licences sont comptabilisées à deux reprises pour les appels de réseau téléphonique commuté (PSTN) vers le client Lync, les appels client Lync vers les lignes RTC et les appels Lync renvoyés vers des lignes PSTN**</span><span class="sxs-lookup"><span data-stu-id="32d63-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="32d63-234">Dans les scénarios suivants, deux licences supplémentaires seront comptabilisées au lieu d’une telle sorte que le numéro de téléphone et l’utilisateur Lync soient pris en compte pour déterminer le nombre de licences utilisées.</span><span class="sxs-lookup"><span data-stu-id="32d63-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="32d63-235">Pour obtenir des informations précises sur la gestion des licences, supprimez manuellement les licences générées par un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="32d63-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="32d63-236">Appel téléphonique PSTN vers Lync</span><span class="sxs-lookup"><span data-stu-id="32d63-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="32d63-237">Appel Lync vers une ligne RTC</span><span class="sxs-lookup"><span data-stu-id="32d63-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="32d63-238">Un appel RTC sur Lync, puis Lync transfère l’appel vers une ligne PSTN.</span><span class="sxs-lookup"><span data-stu-id="32d63-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="32d63-239">Une des lignes RTC sera comptée.</span><span class="sxs-lookup"><span data-stu-id="32d63-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="32d63-240">**Une licence ne sera pas comptabilisée pour un téléphone Lync connecté**</span><span class="sxs-lookup"><span data-stu-id="32d63-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="32d63-241">Lorsqu’un utilisateur utilise un téléphone certifié Lync, si le téléphone se connecte et reste connecté, ce qui conserve son statut de connexion, le téléphone ne sera pas comptabilisé comme utilisant une licence si la requête de licences intervient après la connexion du téléphone.</span><span class="sxs-lookup"><span data-stu-id="32d63-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="32d63-242">**Licences comptabilisées pour les téléphones RTC qui se connectent à des conférences**</span><span class="sxs-lookup"><span data-stu-id="32d63-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="32d63-243">Lorsqu’un utilisateur rejoint une conférence à l’aide d’un téléphone RTC, une licence n’est pas correctement comptabilisée pour rejoindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="32d63-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="32d63-244">Toutefois, aucune licence n’est nécessaire pour participer à une conférence à l’aide d’un téléphone RTC.</span><span class="sxs-lookup"><span data-stu-id="32d63-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="32d63-245">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-245">**Workaround:**</span></span>

1.  <span data-ttu-id="32d63-246">**Nombre de licences inexactes pour les utilisateurs mobiles**</span><span class="sxs-lookup"><span data-stu-id="32d63-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="32d63-247">Vous pouvez identifier les adresses IP qui appartiennent au même appareil et en supprimer une dans le nombre de licences.</span><span class="sxs-lookup"><span data-stu-id="32d63-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="32d63-248">Il n’existe aucune solution de contournement pour ce problème avec les appareils mobiles qui se connectent avec le client Lync.</span><span class="sxs-lookup"><span data-stu-id="32d63-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="32d63-249">**Les licences sont comptabilisées deux fois pour les appels RTC vers le client Lync, les appels client Lync vers les lignes RTC et les appels Lync transférés vers les lignes RTC**</span><span class="sxs-lookup"><span data-stu-id="32d63-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="32d63-250">Vous devez identifier manuellement le numéro de téléphone RTC et supprimer le nombre de licences qui lui est généré.</span><span class="sxs-lookup"><span data-stu-id="32d63-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="32d63-251">**Une licence ne sera pas comptabilisée pour un téléphone Lync connecté**</span><span class="sxs-lookup"><span data-stu-id="32d63-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="32d63-252">Vous pouvez configurer le téléphone Lync pour vous déconnecter, puis vous reconnecter à un intervalle régulier, par exemple tous les 3 mois.</span><span class="sxs-lookup"><span data-stu-id="32d63-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="32d63-253">**Licences comptabilisées pour les téléphones RTC qui se connectent à des conférences**</span><span class="sxs-lookup"><span data-stu-id="32d63-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="32d63-254">Vous pouvez identifier manuellement le numéro de téléphone RTC qui est utilisé pour participer à la Conférence et supprimer la licence générée par le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="32d63-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="32d63-255">Le panneau de configuration de Lync Server cesse de fonctionner dans un environnement VMware après la mise à niveau vers Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="32d63-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="32d63-256">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-256">**Issue:**</span></span>

<span data-ttu-id="32d63-257">Si vous utilisez le panneau de configuration de Lync Server dans un environnement VMware, il est possible que le panneau de configuration de Lync Server cesse de fonctionner après la mise à niveau de Microsoft Silverlight vers la version 5.</span><span class="sxs-lookup"><span data-stu-id="32d63-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="32d63-258">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-258">**Workaround:**</span></span>

<span data-ttu-id="32d63-259">Pour contourner ce problème, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="32d63-260">Désinstaller Silverlight 5, puis installer Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)à partir de.</span><span class="sxs-lookup"><span data-stu-id="32d63-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="32d63-261">Accédez au panneau de configuration de Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.</span><span class="sxs-lookup"><span data-stu-id="32d63-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="32d63-262">Pour ce faire, vous pouvez démarrer le panneau de configuration de Lync Server à partir du menu **Démarrer** de Windows sur le serveur, si les outils d’administration de Lync Server sont installés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="32d63-263">Vous pouvez également accéder au panneau de configuration de Lync Server à l’aide d’un navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="32d63-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="32d63-264">L’URL sera similaire à celle du\<nom\_de\_domaine\>complet du pool https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="32d63-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="32d63-265">Les informations utilisateur du service de carnet d’adresses ne sont pas mises à jour lorsque le nom complet de l’utilisateur est modifié dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="32d63-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="32d63-266">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-266">**Issue:**</span></span>

<span data-ttu-id="32d63-267">Si le nom distinctif d’un utilisateur (également appelé DN) est modifié dans les services de domaine Active Directory (AD DS), les modifications supplémentaires ne seront pas mises à jour dans le service de carnet d’adresses (ABS).</span><span class="sxs-lookup"><span data-stu-id="32d63-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="32d63-268">Cela n’affecte pas la connexion ou la présence de l’utilisateur, mais empêche la communication de l’utilisateur si l’adresse SIP est également modifiée, car la recherche renverra une adresse SIP obsolète.</span><span class="sxs-lookup"><span data-stu-id="32d63-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="32d63-269">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-269">**Workaround:**</span></span>

<span data-ttu-id="32d63-270">Pour contourner ce problème, ne modifiez pas le nom d’utilisateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="32d63-271">Si vous rétablissez la valeur précédente pour l’utilisateur, les mises à jour sont reflétées dans le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="32d63-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="32d63-272">Installation</span><span class="sxs-lookup"><span data-stu-id="32d63-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="32d63-273">L’utilisation de caractères non ASCII risque de provoquer un échec du démarrage de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="32d63-274">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-274">**Issue:**</span></span>

<span data-ttu-id="32d63-275">Le programme d’installation ne fonctionnera pas si le nom du dossier de destination inclut des caractères non ASCII (par exemple, UNICODE, jeu de caractères codés sur deux octets (DBCS), UTF-8 et UTF-16).</span><span class="sxs-lookup"><span data-stu-id="32d63-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="32d63-276">De plus, le programme d’installation peut réussir, mais le serveur ne démarrera pas si des caractères non-ASCII sont contenus dans les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="32d63-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="32d63-277">Nom de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="32d63-277">Computer name</span></span>

  - <span data-ttu-id="32d63-278">Nom du domaine</span><span class="sxs-lookup"><span data-stu-id="32d63-278">Domain name</span></span>

  - <span data-ttu-id="32d63-279">Nom d'utilisateur</span><span class="sxs-lookup"><span data-stu-id="32d63-279">User name</span></span>

  - <span data-ttu-id="32d63-280">URI SIP de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="32d63-280">User SIP URI</span></span>

  - <span data-ttu-id="32d63-281">Nom du compte de service</span><span class="sxs-lookup"><span data-stu-id="32d63-281">Service account name</span></span>

<span data-ttu-id="32d63-282">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-282">**Workaround:**</span></span>

<span data-ttu-id="32d63-283">Utilisez uniquement des caractères ASCII dans le nom du dossier de destination, le nom de l’ordinateur, le nom de domaine, le nom d’utilisateur, l’URI SIP de l’utilisateur et les noms de compte de service.</span><span class="sxs-lookup"><span data-stu-id="32d63-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="32d63-284">Le correctif pour la corruption du tas se produit lorsqu’un module appelle la méthode InsertEntityBody dans IIS 7,5» doit être installé avant d’installer Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32d63-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="32d63-285">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-285">**Issue:**</span></span>

<span data-ttu-id="32d63-286">Le correctif pour la corruption du tas se produit lorsqu’un module appelle la méthode InsertEntityBody dans IIS 7,5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)"(), décrite dans l’article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)) de la base de connaissances Microsoft, doit être installé avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="32d63-287">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-287">**Workaround:**</span></span>

<span data-ttu-id="32d63-288">Téléchargez et installez le correctif à partir du centre de téléchargement [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="32d63-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="32d63-289">Lync Server 2013 ne peut pas être installé sur la version du système d’exploitation Windows Server 2012 du système d’exploitation ITA</span><span class="sxs-lookup"><span data-stu-id="32d63-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="32d63-290">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-290">**Issue:**</span></span>

<span data-ttu-id="32d63-291">Échec de l’installation de Lync Server 2013 sur le Windows Server 2012 en raison de l’échec de l’installation de Windows fabric.</span><span class="sxs-lookup"><span data-stu-id="32d63-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="32d63-292">Échec de l’installation de Windows fabric, car les traces de fabrique sont créées au format HH : MM : SS.</span><span class="sxs-lookup"><span data-stu-id="32d63-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="32d63-293">Toutefois, dans le Windows Server ITA, le format horaire est HH. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="32d63-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="32d63-294">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-294">**Workaround:**</span></span>

<span data-ttu-id="32d63-295">Pour contourner ce problème, mettez à jour le registre système avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="32d63-296">La clé de Registre qui doit être mise à jour est\_:\\utilisateurs de HKEY. Panneau\\\\de configuration par\\défaut sTimeFormat international.</span><span class="sxs-lookup"><span data-stu-id="32d63-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="32d63-297">Définissez la valeur de sTimeFormat sur HH : mm : SS en utilisant l’interface de ligne de commande Windows PowerShell comme suit :</span><span class="sxs-lookup"><span data-stu-id="32d63-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="32d63-298">Démarrez Windows PowerShell et exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="32d63-299">Pour afficher la valeur actuelle, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32d63-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="32d63-300">Notez la valeur actuelle de sTimeFormat afin qu’elle puisse être restaurée une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="32d63-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="32d63-301">Pour définir une nouvelle valeur, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32d63-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="32d63-302">Après l’installation de Lync Server 2013, restaurez la valeur d’origine pour sTimeFormat en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32d63-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="32d63-303">Set-ItemProperty $a-name sTimeFormat-value» <valeur notée à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="32d63-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="32d63-304">au-dessus de> "</span><span class="sxs-lookup"><span data-stu-id="32d63-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="32d63-305">Mobilité</span><span class="sxs-lookup"><span data-stu-id="32d63-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="32d63-306">Problèmes pour les clients mobiles au cours du processus de basculement du serveur</span><span class="sxs-lookup"><span data-stu-id="32d63-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="32d63-307">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-307">**Issue:**</span></span>

<span data-ttu-id="32d63-308">En cas d’échec du serveur Lync et du démarrage du processus de basculement, les problèmes suivants peuvent affecter les utilisateurs des clients mobiles :</span><span class="sxs-lookup"><span data-stu-id="32d63-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="32d63-309">Aucun appel ou signal entrant Lync n’est effectué pendant 10 minutes après le démarrage du basculement.</span><span class="sxs-lookup"><span data-stu-id="32d63-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="32d63-310">Impossible d’accepter les demandes de conversation entrantes</span><span class="sxs-lookup"><span data-stu-id="32d63-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="32d63-311">Impossible de rejoindre des réunions si le serveur en panne est le serveur de base pour l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="32d63-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="32d63-312">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-312">**Workaround:**</span></span>

<span data-ttu-id="32d63-313">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-313">There is no workaround for this issue.</span></span> <span data-ttu-id="32d63-314">Les fonctionnalités normales seront restaurées une fois le processus de basculement terminé.</span><span class="sxs-lookup"><span data-stu-id="32d63-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="32d63-315">Si un utilisateur mobile décline un appel entrant d’un autre point de terminaison Lync, l’appel est affiché en tant que conversion manquée sur les clients mobiles Lync</span><span class="sxs-lookup"><span data-stu-id="32d63-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="32d63-316">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-316">**Issue:**</span></span>

<span data-ttu-id="32d63-317">Si un utilisateur mobile décline un appel entrant et que l’appel provient d’un autre point de terminaison Lync, l’appel s’affiche sous la forme d’une conversation manquée dans le client mobile Lync au lieu d’un appel dans la liste d’appels d’appareil.</span><span class="sxs-lookup"><span data-stu-id="32d63-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="32d63-318">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-318">**Workaround:**</span></span>

<span data-ttu-id="32d63-319">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="32d63-320">Le client mobile ne peut pas afficher le nom complet d’un contact fédéré lors de la recherche de contacts</span><span class="sxs-lookup"><span data-stu-id="32d63-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="32d63-321">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-321">**Issue:**</span></span>

<span data-ttu-id="32d63-322">Dans certains cas, le nom d’affichage des contacts fédérés ne s’affiche pas, par exemple lors de la recherche d’un contact fédéré dans la liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="32d63-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="32d63-323">Cela peut se produire lorsqu’il n’y a aucun abonnement de présence actif pour le contact à partir du client mobile Lync.</span><span class="sxs-lookup"><span data-stu-id="32d63-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="32d63-324">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-324">**Workaround:**</span></span>

<span data-ttu-id="32d63-325">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="32d63-326">Dans le client mobile, les informations d’invité et d’horodatage sont manquantes dans une conversation manquée qui est une invitation à une conférence</span><span class="sxs-lookup"><span data-stu-id="32d63-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="32d63-327">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-327">**Issue:**</span></span>

<span data-ttu-id="32d63-328">Dans le client mobile, lorsqu’une conversation manquée est une invitation à une conférence, les informations invité et horodatage sont manquantes dans le message de conversation manqué.</span><span class="sxs-lookup"><span data-stu-id="32d63-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="32d63-329">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-329">**Workaround:**</span></span>

<span data-ttu-id="32d63-330">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="32d63-331">Les utilisateurs des clients mobiles effectuant des appels à l’aide de VoIP ne peuvent pas quitter la messagerie vocale pour les utilisateurs dont la messagerie vocale est configurée dans Exchange 2010 ou les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="32d63-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="32d63-332">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-332">**Issue:**</span></span>

<span data-ttu-id="32d63-333">Si un utilisateur du client mobile utilise le protocole VoIP pour passer des appels, l’utilisateur ne pourra pas quitter les messages vocaux pour les utilisateurs configurés pour utiliser la messagerie vocale dans Microsoft Exchange Server 2007 ou Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="32d63-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="32d63-334">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-334">**Workaround:**</span></span>

<span data-ttu-id="32d63-335">Pour contourner ce problème, utilisez Exchange 2010 avec SP1 ou une version plus récente de Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="32d63-336">Lors de l’utilisation de l’application bloc with URL pour la configuration de la version client sur des clients mobiles, un message d’erreur s’affiche</span><span class="sxs-lookup"><span data-stu-id="32d63-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="32d63-337">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-337">**Issue:**</span></span>

<span data-ttu-id="32d63-338">Lors de l’utilisation de l’application **bloc with URL** pour la configuration de la version client sur des clients mobiles, un message d’erreur incorrect peut s’afficher lorsque la version du client n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="32d63-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="32d63-339">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-339">**Workaround:**</span></span>

<span data-ttu-id="32d63-340">Pour contourner ce problème, configurez la configuration de version de client de façon à ce qu’elle utilise **bloc** au lieu de **bloquer avec une URL**.</span><span class="sxs-lookup"><span data-stu-id="32d63-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="32d63-341">Conférence</span><span class="sxs-lookup"><span data-stu-id="32d63-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="32d63-342">Un logiciel antivirus exécuté sur des serveurs frontaux Lync Server 2013 peut entraîner le recyclage du domaine d’application, ce qui interrompt temporairement le service pour Lync Web App 2013, Lync Mobile 2010 et les clients Lync mobile 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="32d63-343">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-343">**Issue:**</span></span>

<span data-ttu-id="32d63-344">Un logiciel antivirus peut déclencher les redémarrages de domaine d’application, ce qui peut entraîner l’exécution d’applications clientes d’API de mobilité Lync 2013 et de communications unifiées (UC) sur les applications clientes (Lync Web App 2013, Lync Mobile 2010 et Lync mobile 2013).</span><span class="sxs-lookup"><span data-stu-id="32d63-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="32d63-345">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-345">**Workaround:**</span></span>

<span data-ttu-id="32d63-346">Pour contourner ce problème, excluez les dossiers contenant des composants Web et .NET Framework de l’analyse antivirus.</span><span class="sxs-lookup"><span data-stu-id="32d63-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="32d63-347">Pour plus d’informations, reportez-vous à l’article 312592 de la base de connaissances Microsoft « problème : les redémarrages de l’application aléatoire avec [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)«l’application redémarre » dans ASP.net».</span><span class="sxs-lookup"><span data-stu-id="32d63-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="32d63-348">Les dossiers suivants doivent être exclus :</span><span class="sxs-lookup"><span data-stu-id="32d63-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="32d63-349">% ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components MCX\\ext</span><span class="sxs-lookup"><span data-stu-id="32d63-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="32d63-350">% ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components MCX\\ent</span><span class="sxs-lookup"><span data-stu-id="32d63-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="32d63-351">% ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components Ucwa\\ent</span><span class="sxs-lookup"><span data-stu-id="32d63-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="32d63-352">% ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components Ucwa\\ext</span><span class="sxs-lookup"><span data-stu-id="32d63-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="32d63-353">% Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="32d63-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="32d63-354">Les contrôles ActiveX ou la prise en charge native de XMLHTTP doivent être activés dans Windows Internet Explorer pour pouvoir participer à des conférences</span><span class="sxs-lookup"><span data-stu-id="32d63-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="32d63-355">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-355">**Issue:**</span></span>

<span data-ttu-id="32d63-356">Si un utilisateur a désactivé les contrôles ActiveX et la prise en charge du programme XMLHTTP natif dans Windows Internet Explorer, l’utilisateur ne pourra pas participer à une réunion si Internet Explorer est sélectionné comme navigateur par défaut.</span><span class="sxs-lookup"><span data-stu-id="32d63-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="32d63-357">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-357">**Workaround:**</span></span>

<span data-ttu-id="32d63-358">Activez les contrôles ActiveX ou le « support XMLHTTP natif » dans Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="32d63-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="32d63-359">Le service de conférence Web de Lync Server ne peut pas être récupéré à partir du mode critique</span><span class="sxs-lookup"><span data-stu-id="32d63-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="32d63-360">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-360">**Issue:**</span></span>

<span data-ttu-id="32d63-361">Si le mode critique est activé pour l’archivage, en cas de pannes système, le mode Critical démarre et les conférences ne fonctionneront plus pour les participants.</span><span class="sxs-lookup"><span data-stu-id="32d63-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="32d63-362">Une fois que l’administrateur a résolu les défaillances du système (par exemple, correction d’un problème de base de données), le service de conférence de données ne se restaure pas automatiquement, et l’administrateur doit redémarrer manuellement le service de conférence pour qu’il reprenne.</span><span class="sxs-lookup"><span data-stu-id="32d63-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="32d63-363">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-363">**Workaround:**</span></span>

<span data-ttu-id="32d63-364">Une fois le système résolu, un administrateur doit redémarrer manuellement le service de conférence.</span><span class="sxs-lookup"><span data-stu-id="32d63-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="32d63-365">Le service de conférence Web ignore le proxy HTTP pour les serveurs Office Web App externes</span><span class="sxs-lookup"><span data-stu-id="32d63-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="32d63-366">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-366">**Issue:**</span></span>

<span data-ttu-id="32d63-367">Si vous avez déployé un serveur Office Web Apps externe au service de conférence Web (autrement dit, un serveur qui n’est pas présent dans le réseau d’entreprise interne) sur Internet, le réseau de périmètre et le service de conférence Web nécessite un proxy HTTP pour se connecter à cette application, le La découverte d’Office Web Apps Server échoue.</span><span class="sxs-lookup"><span data-stu-id="32d63-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="32d63-368">Le service de conférence Web ignore le paramètre proxy HTTP, tel qu’il est défini dans générateur de topologie pour l’installation d’Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="32d63-369">Par conséquent, le client Lync ne sera pas en mesure d’effectuer le partage de 2010 Microsoft PowerPoint avec les autres participants à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="32d63-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="32d63-370">Si vous installez Lync Server en local et configurez également Office Web Apps Server en local sur le réseau interne, une configuration de proxy n’est pas requise.</span><span class="sxs-lookup"><span data-stu-id="32d63-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="32d63-371">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-371">**Workaround:**</span></span>

<span data-ttu-id="32d63-372">La seule solution de contournement consiste à ne pas avoir de configuration de déploiement qui nécessite l’utilisation du proxy HTTP pour communiquer avec un serveur Office Web Apps externe.</span><span class="sxs-lookup"><span data-stu-id="32d63-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="32d63-373">L’ajout de la vidéo à une conférence du fournisseur de services d’audioconférence n’est pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="32d63-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="32d63-374">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-374">**Issue:**</span></span>

<span data-ttu-id="32d63-375">L’ajout d’une vidéo n’est pas pris en charge si l’utilisateur est joint à une conférence de fournisseur de services d’audioconférence pour le son.</span><span class="sxs-lookup"><span data-stu-id="32d63-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="32d63-376">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-376">**Workaround:**</span></span>

<span data-ttu-id="32d63-377">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="32d63-378">Les topologies avec IPv6 activé forcent la mise à jour automatique du plug-in Lync Web App pour garantir le fonctionnement du partage d’écran à partir de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="32d63-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="32d63-379">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-379">**Issue:**</span></span>

<span data-ttu-id="32d63-380">Lorsqu’une topologie est configurée avec l’option IPv6 activée, les utilisateurs ne peuvent pas partager leur écran à partir du client Lync Web App si une version antérieure du plug-in de partage d’écran est déjà installée.</span><span class="sxs-lookup"><span data-stu-id="32d63-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="32d63-381">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-381">**Workaround:**</span></span>

<span data-ttu-id="32d63-382">Pour forcer une mise à jour vers la version la plus récente du plug-in de partage d’écran lors de la participation à une réunion via Lync Web App, remplacez la valeur de **MinSupportedBuildVersion** par « 4.0.7457.0 » par « 4.0.7577.380 » dans les deux fichiers suivants :</span><span class="sxs-lookup"><span data-stu-id="32d63-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="32d63-383">% ProgramFiles%\\Microsoft Lync Server 15\\composants\\Web ont\\atteint\\les\\plug\\-ins de clients ReachAppShPluginProperties. Xml</span><span class="sxs-lookup"><span data-stu-id="32d63-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="32d63-384">% ProgramFiles%\\Microsoft Lync Server 15\\composants\\Web sont\\accessibles\\à\\l'\\extension du client ReachAppShPluginProperties. Xml</span><span class="sxs-lookup"><span data-stu-id="32d63-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="32d63-385">Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="32d63-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="32d63-386">Dans certains cas, un client Lync exécuté sur un ordinateur configuré pour utiliser la pile double IPv4 et IPv6 peut ne pas prendre en charge les fonctionnalités qui dépendent du sous-réseau IP de l’ordinateur (par exemple, E911, dérivation multimédia, contrôle d’admission des appels et routage basé sur l’emplacement).</span><span class="sxs-lookup"><span data-stu-id="32d63-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="32d63-387">Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="32d63-388">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-388">**Issue:**</span></span>

<span data-ttu-id="32d63-389">Lorsqu’un client Lync est en cours d’exécution sur un ordinateur activé pour la pile IPv4 et IPv6 et en fonction de la résolution DNS du serveur proxy, le client peut utiliser l’adresse IPv6 de l’ordinateur pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="32d63-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="32d63-390">Après cela, le client Lync ne prend en charge que les fonctionnalités prises en charge pour IPv6, ce qui exclut E911, le contournement du média, le contrôle d’admission des appels et le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="32d63-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="32d63-391">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-391">**Workaround:**</span></span>

<span data-ttu-id="32d63-392">Pour contourner ce problème, désactivez la prise en charge du protocole IPv6 sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="32d63-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="32d63-393">Si voix entreprise n’est pas configurée pour un utilisateur, l’utilisateur doit utiliser le format E164 pour appeler à partir d’une conférence</span><span class="sxs-lookup"><span data-stu-id="32d63-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="32d63-394">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-394">**Issue:**</span></span>

<span data-ttu-id="32d63-395">Si voix entreprise n’est pas configurée pour un utilisateur, il doit utiliser le format E164 pour qu’il se connecte correctement à partir d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="32d63-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="32d63-396">Si le format E164 n’est pas utilisé, l’utilisateur ne pourra pas se connecter à partir de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="32d63-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="32d63-397">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-397">**Workaround:**</span></span>

<span data-ttu-id="32d63-398">Pour contourner ce problème, les utilisateurs qui ne sont pas activés pour voix entreprise doivent composer d’une conférence en utilisant des numéros au format E164.</span><span class="sxs-lookup"><span data-stu-id="32d63-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="32d63-399">Présence</span><span class="sxs-lookup"><span data-stu-id="32d63-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="32d63-400">Si un utilisateur a sélectionné « bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour l’utilisateur, le statut de présence n’est pas rejeté s’il devrait être</span><span class="sxs-lookup"><span data-stu-id="32d63-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="32d63-401">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-401">**Issue:**</span></span>

<span data-ttu-id="32d63-402">Si un utilisateur a sélectionné « bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour l’utilisateur, le statut de présence n’est pas rejeté le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="32d63-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="32d63-403">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-403">**Workaround:**</span></span>

<span data-ttu-id="32d63-404">Pour contourner ce problème, vous pouvez désactiver le magasin de contacts unifié pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="32d63-405">Pour cela, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="32d63-406">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="32d63-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="32d63-407">Les utilisateurs d’Office Communications Server 2007 R2 hébergés sur site ne peuvent pas voir le statut de présence des utilisateurs Skype entreprise Online dans des déploiements hybrides-hybrides</span><span class="sxs-lookup"><span data-stu-id="32d63-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="32d63-408">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-408">**Issue:**</span></span>

<span data-ttu-id="32d63-409">Le problème est susceptible de se produire dans un déploiement hybride lorsque vous utilisez un directeur 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="32d63-410">Le statut de présence des utilisateurs hébergés dans Skype entreprise Online est affiché en tant que présence inconnue pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="32d63-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="32d63-411">De plus, les utilisateurs hébergés sur Skype entreprise Online ne peuvent pas voir le statut de présence des utilisateurs Office Communications Server R2 locaux.</span><span class="sxs-lookup"><span data-stu-id="32d63-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="32d63-412">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-412">**Workaround:**</span></span>

<span data-ttu-id="32d63-413">Pour contourner ce problème, vous devez modifier le serveur principal (msRTCSIP-presencehomeserver) des utilisateurs de Skype entreprise Online pour qu’ils pointent vers un pool Lync Server 2013 local au lieu du Director Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="32d63-414">Vous pouvez modifier ce paramètre sur le serveur frontal local.</span><span class="sxs-lookup"><span data-stu-id="32d63-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="32d63-415">Cette solution de contournement affiche correctement le statut de présence des utilisateurs hébergés sur Office Communications Server 2007 R2 aux utilisateurs de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="32d63-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="32d63-416">Application de groupe de réponse, application de parc d’appels et capture d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="32d63-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="32d63-417">Un appelant peut entendre une seconde de la musique lors de l’établissement d’un appel avec la fête de l’extraction</span><span class="sxs-lookup"><span data-stu-id="32d63-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="32d63-418">Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="32d63-419">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-419">**Issue:**</span></span>

<span data-ttu-id="32d63-420">Lorsqu’un appel est récupéré par le biais d’un appel de groupe, l’appelant peut entendre une seconde de la musique lors de l’établissement de l’appel avec la partie du récupérateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="32d63-421">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-421">**Workaround:**</span></span>

<span data-ttu-id="32d63-422">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="32d63-423">Un agent Response Group peut se connecter et se déconnecter de la console de l’agent Lync Server 2010 aux groupes d’agents officiels Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="32d63-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="32d63-424">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-424">**Issue:**</span></span>

<span data-ttu-id="32d63-425">Un agent Response Group de Lync Server 2013 peut se connecter et se déconnecter par le biais d’une console de l’agent Lync Server 2010 aux groupes d’agents officiels Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="32d63-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="32d63-426">Dans la console de l’agent Lync Server 2010, les utilisateurs peuvent uniquement voir le groupe de réponse Lync Server 2010 auquel ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="32d63-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="32d63-427">Ils ne peuvent pas voir les groupes de réponse Lync Server 2013 auxquels ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="32d63-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="32d63-428">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-428">**Workaround:**</span></span>

<span data-ttu-id="32d63-429">Si l’agent Response Group est un utilisateur de Lync Server 2013 et fait partie d’un groupe d’agents officiels de Lync Server 2013, l’utilisateur doit accéder à la console de l’agent Lync Server 2013 directement via un lien Web dans un navigateur pour vous connecter et se déconnecter des groupes d’agents Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="32d63-430">Un agent Response Group de Lync Server 2010 ne peut pas passer d’appels pour le compte d’un groupe de réponse 2013 Server</span><span class="sxs-lookup"><span data-stu-id="32d63-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="32d63-431">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-431">**Issue:**</span></span>

<span data-ttu-id="32d63-432">Un utilisateur de Lync Server 2010 qui est un agent d’un groupe de réponse 2013 Server n’est pas en mesure de passer un appel au nom du groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="32d63-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="32d63-433">Le groupe de réponse Lync Server 2013 ne sera pas disponible dans le client Lync pour effectuer un appel.</span><span class="sxs-lookup"><span data-stu-id="32d63-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="32d63-434">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-434">**Workaround:**</span></span>

<span data-ttu-id="32d63-435">Pour contourner ce problème, vous devez déplacer l’utilisateur de Lync Server 2010 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="32d63-436">La suppression d’un groupe réponse de Lync Server 2010 après la migration vers Lync Server 2013 empêche le groupe de réponse d’accepter les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="32d63-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="32d63-437">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-437">**Issue:**</span></span>

<span data-ttu-id="32d63-438">Si un groupe Response migration de Lync Server 2010 vers Lync Server 2013 est supprimé de Lync Server 2010 par le biais du panneau de configuration de Lync Server ou de Lync Server Management Shell, le groupe réponse dans Lync Server 2013 cessera de recevoir des appels entrants.</span><span class="sxs-lookup"><span data-stu-id="32d63-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="32d63-439">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-439">**Workaround:**</span></span>

<span data-ttu-id="32d63-440">Pour contourner ce problème, ne supprimez pas les groupes de réponses de Lync Server 2010 qui ont été migrés de Lync Server 2010 vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="32d63-441">Si le groupe de réponse a déjà été supprimé, vous devez le redéployer dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="32d63-442">Lorsqu’un nouveau flux de travail géré est défini sur inactif lors de sa création, le déploiement du flux de travail échoue</span><span class="sxs-lookup"><span data-stu-id="32d63-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="32d63-443">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-443">**Issue:**</span></span>

<span data-ttu-id="32d63-444">Lorsqu’un nouveau flux de travail géré est défini sur inactif lors de sa création, le déploiement du flux de travail échoue.</span><span class="sxs-lookup"><span data-stu-id="32d63-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="32d63-445">Ce problème survient lorsque le flux de travail est défini sur inactif lors de sa création, mais n’affecte pas le flux de travail modifié pour le définir comme inactif après le déploiement de.</span><span class="sxs-lookup"><span data-stu-id="32d63-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="32d63-446">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-446">**Workaround:**</span></span>

<span data-ttu-id="32d63-447">Lorsque vous créez et déployez un flux de travail, définissez le flux de travail comme actif, puis déployez-le.</span><span class="sxs-lookup"><span data-stu-id="32d63-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="32d63-448">Après le déploiement réussi du flux de travail, le flux de travail peut être modifié et défini comme inactif.</span><span class="sxs-lookup"><span data-stu-id="32d63-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="32d63-449">Le fait de supprimer un groupe de réponses de la liste de propriétaires empêche le groupe de réponse du pool de sauvegarde d’accepter les appels entrants lors du basculement si le groupe de réponse a été importé dans le pool de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="32d63-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="32d63-450">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-450">**Issue:**</span></span>

<span data-ttu-id="32d63-451">Si un groupe de réponses possédé par le pool principal a été importé dans le pool de sauvegarde sans remplacer le propriétaire, et si le groupe de réponses est supprimé de la liste de propriétaires, le groupe réponse dans le pool de sauvegarde n’accepte aucun appel entrant lors du basculement.</span><span class="sxs-lookup"><span data-stu-id="32d63-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="32d63-452">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-452">**Workaround:**</span></span>

<span data-ttu-id="32d63-453">Vous devez redéployer le groupe Response dans le pool principal.</span><span class="sxs-lookup"><span data-stu-id="32d63-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="32d63-454">Vous devrez alors exporter la configuration de groupe de réponse à partir du pool principal et l’importer dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="32d63-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="32d63-455">Vous pouvez également recréer le groupe Response dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="32d63-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="32d63-456">Dans ce cas, le pool de sauvegarde sera le pool de propriétaires du groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="32d63-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="32d63-457">Un appel parqué ne peut pas être récupéré à partir de l’application de parc d’appels si la demande de récupération est exécutée au nom d’un groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="32d63-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="32d63-458">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-458">**Issue:**</span></span>

<span data-ttu-id="32d63-459">Lorsque les conditions suivantes sont vraies, une demande de récupération d’un appel en stationnement échoue :</span><span class="sxs-lookup"><span data-stu-id="32d63-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="32d63-460">Un agent fait partie d’un groupe de réponse anonyme</span><span class="sxs-lookup"><span data-stu-id="32d63-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="32d63-461">L’agent tente de récupérer un appel parqué à partir de l’application de parc d’appels via le groupe de réponse anonyme</span><span class="sxs-lookup"><span data-stu-id="32d63-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="32d63-462">L’agent tente de récupérer l’appel en composant le numéro orbite par le biais de l’option appeler de la part ou de la même option dans le client attendant Lync.</span><span class="sxs-lookup"><span data-stu-id="32d63-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="32d63-463">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-463">**Workaround:**</span></span>

<span data-ttu-id="32d63-464">Il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="32d63-465">L’appel parqué doit être récupéré sans action pour le compte d’un groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="32d63-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="32d63-466">Panneau de configuration Lync Server, générateur de topologie et outil de planification</span><span class="sxs-lookup"><span data-stu-id="32d63-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="32d63-467">Limitations de l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="32d63-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="32d63-468">Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="32d63-469">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-469">**Issue:**</span></span>

<span data-ttu-id="32d63-470">Lorsque vous planifiez votre déploiement, l’outil de planification présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="32d63-471">La prise en charge de 10 sites centraux est au maximum</span><span class="sxs-lookup"><span data-stu-id="32d63-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="32d63-472">Chaque site central peut comporter un maximum de 14 sites de succursales</span><span class="sxs-lookup"><span data-stu-id="32d63-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="32d63-473">Chaque site central peut avoir un maximum de 240 000 utilisateurs</span><span class="sxs-lookup"><span data-stu-id="32d63-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="32d63-474">Par ailleurs, l’outil de planification n’inclut pas de valeurs pour les éléments suivants lors du calcul de la topologie recommandée :</span><span class="sxs-lookup"><span data-stu-id="32d63-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="32d63-475">Le nombre d’utilisateurs hébergés en ligne</span><span class="sxs-lookup"><span data-stu-id="32d63-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="32d63-476">Pourcentage d’utilisateurs activés pour la Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="32d63-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="32d63-477">Pourcentage d’utilisateurs qui utilisent Lync Web App</span><span class="sxs-lookup"><span data-stu-id="32d63-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="32d63-478">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-478">**Workaround:**</span></span>

<span data-ttu-id="32d63-479">Il n’existe aucune solution de contournement pour ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="32d63-479">There is no workaround for these issues.</span></span> <span data-ttu-id="32d63-480">Pour plus d’informations sur l’outil de planification, voir [conception de la topologie pour Lync Server 2013 à l’aide de l’outil de planification](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="32d63-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="32d63-481">L’outil de planification n’utilise pas les adresses IP précédemment définies pour le réseau Edge lors de la mise à jour des options</span><span class="sxs-lookup"><span data-stu-id="32d63-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="32d63-482">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-482">**Issue:**</span></span>

<span data-ttu-id="32d63-483">Lorsque vous avez terminé de créer votre conception à l’aide de l’outil de planification, si vous apportez des modifications aux options du réseau Edge, des adresses IP supplémentaires pourront être ajoutées à la conception au lieu de mettre à jour les adresses IP existantes.</span><span class="sxs-lookup"><span data-stu-id="32d63-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="32d63-484">Cela peut se produire lorsque vous affichez les détails du réseau de tâches latérales, sélectionnez **cliquez ici pour mettre à jour vos options**, puis, dans la boîte de dialogue Options de configuration, sélectionnez réseau de bord, sélectionnez **l’option je souhaite utiliser les mêmes noms de domaine complets et adresses IP, mais des ports différents pour les services Edge sur le serveur Edge**.</span><span class="sxs-lookup"><span data-stu-id="32d63-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="32d63-485">L’application de toute modification entraîne l’ajout de nouvelles adresses IP et de serveurs de frontière à la conception.</span><span class="sxs-lookup"><span data-stu-id="32d63-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="32d63-486">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-486">**Workaround:**</span></span>

<span data-ttu-id="32d63-487">Pour le moment, il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="32d63-488">Dans le panneau de configuration de Lync Server, « déplacer tous les utilisateurs vers le pool » risque de ne pas fonctionner comme prévu</span><span class="sxs-lookup"><span data-stu-id="32d63-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="32d63-489">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-489">**Issue:**</span></span>

<span data-ttu-id="32d63-490">Lorsque vous utilisez le panneau de configuration de Lync Server pour déplacer tous les utilisateurs d’un pool vers un autre dans un environnement Active Directory complexe (par exemple, un avec plusieurs contrôleurs de domaine et domaines parent/enfant), un message d’erreur peut être retourné, car « l’utilisateur spécifié n’est pas un utilisateur hérité, utilisez l’applet de commande Move-CsUser à la place. »</span><span class="sxs-lookup"><span data-stu-id="32d63-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="32d63-491">Cela résulte de temps de réplication plus longs dans les environnements Active Directory complexes.</span><span class="sxs-lookup"><span data-stu-id="32d63-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="32d63-492">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-492">**Workaround:**</span></span>

<span data-ttu-id="32d63-493">Pour contourner ce problème, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="32d63-494">Utilisez les filtres du panneau de configuration de Lync Server pour rechercher des utilisateurs hérités, sélectionnez ces utilisateurs, puis utilisez la **commande déplacer les utilisateurs sélectionnés vers le pool** au lieu de **déplacer tous les utilisateurs vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="32d63-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="32d63-495">Utilisez Lync Server Management Shell pour déplacer des utilisateurs hérités par lot à l’aide d’applets de commande Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="32d63-496">Le panneau de configuration de Lync Server cesse de fonctionner dans un environnement VMware après la mise à jour du plug-in de navigateur Microsoft Silverlight vers la version 5</span><span class="sxs-lookup"><span data-stu-id="32d63-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="32d63-497">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-497">**Issue:**</span></span>

<span data-ttu-id="32d63-498">Si vous utilisez le panneau de configuration de Lync Server dans un environnement VMware, il est possible que le panneau de configuration de Lync Server cesse de fonctionner après la mise à niveau de Silverlight vers la version 5.</span><span class="sxs-lookup"><span data-stu-id="32d63-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="32d63-499">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-499">**Workaround:**</span></span>

<span data-ttu-id="32d63-500">Pour contourner ce problème, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="32d63-501">Désinstaller Silverlight 5, puis installer Silverlight 4 à [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)partir de.</span><span class="sxs-lookup"><span data-stu-id="32d63-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="32d63-502">Ouvrez le panneau de configuration de Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.</span><span class="sxs-lookup"><span data-stu-id="32d63-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="32d63-503">Pour ouvrir le panneau de configuration de Lync Server à partir d’un ordinateur distant, installez les outils d’administration de Lync Server sur votre ordinateur, puis démarrez le panneau de configuration de Lync Server à partir du menu **Démarrer** de Windows.</span><span class="sxs-lookup"><span data-stu-id="32d63-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="32d63-504">Vous pouvez également ouvrir le panneau de configuration de Lync Server en entrant l’URL dans un navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="32d63-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="32d63-505">L’URL sera similaire à celle du\<nom\_de\_domaine\>complet du pool https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="32d63-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="32d63-506">Un administrateur ne peut pas exécuter l’applet de création de désinstallation-csMirrorDB après la suppression de la base de données en miroir dans le générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="32d63-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="32d63-507">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-507">**Issue:**</span></span>

<span data-ttu-id="32d63-508">Lorsqu’un administrateur désactive une base de données en miroir dans le générateur de topologie, puis supprime la base de données en miroir dans le générateur de topologie, un message s’affiche dans la liste des tâches pour l’administrateur pour exécuter l’applet de l’applet de suppression **-csMirrorDatabase** et supprimer la mise en miroir de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="32d63-509">Lorsque l’administrateur tente d’exécuter l’applet de cmdlet, il échoue.</span><span class="sxs-lookup"><span data-stu-id="32d63-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="32d63-510">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-510">**Workaround:**</span></span>

<span data-ttu-id="32d63-511">Pour supprimer la mise en miroir SQL d’un pool dans le générateur de topologie, vous devez commencer par utiliser une applet de cmdlet pour supprimer le miroir dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32d63-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="32d63-512">Vous pouvez ensuite utiliser le générateur de topologie pour supprimer le miroir de la topologie.</span><span class="sxs-lookup"><span data-stu-id="32d63-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="32d63-513">Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="32d63-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="32d63-514">Par exemple, pour supprimer la mise en miroir et supprimer les bases de données pour les bases de données utilisateur, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="32d63-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="32d63-515">Le paramètre *DropExistingDatabasesOnMirror* vous permet de supprimer les bases de données affectées du miroir.</span><span class="sxs-lookup"><span data-stu-id="32d63-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="32d63-516">Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="32d63-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="32d63-517">Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="32d63-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="32d63-518">Désactivez l’option **activer la mise en miroir du magasin SQL** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="32d63-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="32d63-519">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="32d63-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="32d63-520">Lorsque vous modifiez une relation de mise en miroir de la base de données principale, vous devez redémarrer tous les serveurs frontaux de la liste.</span><span class="sxs-lookup"><span data-stu-id="32d63-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="32d63-521">Les erreurs de validation sont renvoyées dans le générateur de topologie lorsqu’un administrateur tente de supprimer un déploiement avec un pool frontal qui dispose d’un magasin témoin associé.</span><span class="sxs-lookup"><span data-stu-id="32d63-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="32d63-522">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-522">**Issue:**</span></span>

<span data-ttu-id="32d63-523">Si un administrateur tente d’utiliser la commande **supprimer le déploiement** dans le générateur de topologie pour supprimer un déploiement incluant un pool frontal avec un magasin témoin associé, une erreur de validation s’affiche dans le générateur de topologie et l’action ne se poursuit pas.</span><span class="sxs-lookup"><span data-stu-id="32d63-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="32d63-524">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-524">**Workaround:**</span></span>

<span data-ttu-id="32d63-525">Pour contourner ce problème, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="32d63-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="32d63-526">Supprimez le magasin témoin avant d’essayer de supprimer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="32d63-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="32d63-527">Ajoutez un magasin témoin pour le pool frontal, puis supprimez-le.</span><span class="sxs-lookup"><span data-stu-id="32d63-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="32d63-528">Les informations de déploiement permanent du serveur de conversation ne sont pas cohérentes entre l’outil de planification et le générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="32d63-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="32d63-529">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-529">**Issue:**</span></span>

<span data-ttu-id="32d63-530">Lorsque le serveur Lync Server 2013, l’outil de planification génère le diagramme de topologie de site pour un déploiement de serveur Chat permanent avec l’option de reprise après sinistre activée, le diagramme de topologie de site inclut plusieurs sites (physiques), avec des serveurs de chat permanent assignés Sitemap.</span><span class="sxs-lookup"><span data-stu-id="32d63-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="32d63-531">Dans le générateur de topologie, tous les serveurs de chat permanent sont représentés comme appartenant à un site unique (logique) et apparaissent sous le même nœud de pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="32d63-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="32d63-532">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-532">**Workaround:**</span></span>

<span data-ttu-id="32d63-533">Pour le moment, il n’existe aucune solution de contournement pour ce problème.</span><span class="sxs-lookup"><span data-stu-id="32d63-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="32d63-534">L’utilisateur doit analyser la sortie de l’outil de planification pour le déploiement de serveur Chat permanent et modifier le plan en fonction de ses besoins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="32d63-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="32d63-535">Localisation</span><span class="sxs-lookup"><span data-stu-id="32d63-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="32d63-536">Surveillance</span><span class="sxs-lookup"><span data-stu-id="32d63-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="32d63-537">L’Assistant Déploiement des rapports de surveillance affiche des caractères incorrects dans certaines circonstances lors de l’utilisation de la version d’Asie orientale de Lync Server</span><span class="sxs-lookup"><span data-stu-id="32d63-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="32d63-538">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-538">**Issue:**</span></span>

<span data-ttu-id="32d63-539">Lorsque vous utilisez une version d’Asie orientale de Lync Server 2013 (par exemple, chinois (simplifié), chinois (traditionnel), japonais ou coréen, sur un système d’exploitation dont les paramètres régionaux du système ne sont pas définis sur une langue d’Asie de l’est, l’Assistant Déploiement des rapports d’analyse Affichez des points d’interrogation ou d’autres caractères au lieu de messages localisés.</span><span class="sxs-lookup"><span data-stu-id="32d63-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="32d63-540">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-540">**Workaround:**</span></span>

<span data-ttu-id="32d63-541">Pour résoudre ce problème, définissez les paramètres régionaux pour le système d’exploitation et Lync Server 2013 dans la même langue, ce qui permet d’afficher tous les messages correctement.</span><span class="sxs-lookup"><span data-stu-id="32d63-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="32d63-542">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="32d63-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="32d63-543">Dans certains cas, le premier élément de la barre de navigation supérieure sur une page du panneau de configuration de Lync Server disparaît lorsque vous cliquez sur le dernier élément de la barre de navigation supérieure.</span><span class="sxs-lookup"><span data-stu-id="32d63-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="32d63-544">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-544">**Issue:**</span></span>

<span data-ttu-id="32d63-545">Il existe trois cas connus où cliquer sur le dernier élément de la barre de navigation supérieure sur une page du panneau de configuration de Lync Server entraîne la disparition du premier élément dans la barre de navigation supérieure :</span><span class="sxs-lookup"><span data-stu-id="32d63-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="32d63-546">Dans la version française, sur la page « Féderation et accès extern », l’élément « stratégie d’accès externe » disparaîtra lorsque vous cliquez sur « partenaires fédérés XMPP ».</span><span class="sxs-lookup"><span data-stu-id="32d63-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="32d63-547">Dans la version allemande, sur la page « clients », l’élément « Clientversionskonfiguration » disparaît lorsque vous cliquez sur « Pushbenachrichtigungskonfiguration ».</span><span class="sxs-lookup"><span data-stu-id="32d63-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="32d63-548">Dans la version russe, sur la page « Конфигурация сети », l’élément « Глобально » disparaît lorsque vous cliquez sur « Маршрут региона ».</span><span class="sxs-lookup"><span data-stu-id="32d63-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="32d63-549">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-549">**Workaround:**</span></span>

<span data-ttu-id="32d63-550">Pour contourner ce problème, actualisez la page du panneau de configuration de Lync Server dans votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="32d63-551">La page se charge dans le navigateur avec tous les éléments dans la barre de navigation supérieure affichée.</span><span class="sxs-lookup"><span data-stu-id="32d63-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="32d63-552">Carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="32d63-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="32d63-553">L’indexation dans le carnet d’adresses ne fonctionne pas comme prévu dans certaines langues</span><span class="sxs-lookup"><span data-stu-id="32d63-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="32d63-554">Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="32d63-555">Si les propriétés d’un utilisateur contiennent un champ indexé et que ce champ ne contient que des caractères qui ne peuvent pas être indexés, l’utilisateur n’apparaît pas dans les recherches effectuées dans le carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="32d63-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="32d63-556">Les caractères et valeurs locales suivants ne peuvent pas être indexés :</span><span class="sxs-lookup"><span data-stu-id="32d63-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="32d63-557">Caractères cyrilliques, grecs et arméniens en majuscules</span><span class="sxs-lookup"><span data-stu-id="32d63-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="32d63-558">Caractères en majuscules accentués</span><span class="sxs-lookup"><span data-stu-id="32d63-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="32d63-559">Thaï</span><span class="sxs-lookup"><span data-stu-id="32d63-559">Thai</span></span>

  - <span data-ttu-id="32d63-560">Laos</span><span class="sxs-lookup"><span data-stu-id="32d63-560">Lao</span></span>

  - <span data-ttu-id="32d63-561">Birmanie</span><span class="sxs-lookup"><span data-stu-id="32d63-561">Myanmar</span></span>

  - <span data-ttu-id="32d63-562">DÉVANÂGARÎ</span><span class="sxs-lookup"><span data-stu-id="32d63-562">Devanagari</span></span>

  - <span data-ttu-id="32d63-563">Éthiopienne</span><span class="sxs-lookup"><span data-stu-id="32d63-563">Ethiopic</span></span>

  - <span data-ttu-id="32d63-564">Voyelle</span><span class="sxs-lookup"><span data-stu-id="32d63-564">Tibetan</span></span>

  - <span data-ttu-id="32d63-565">Bengali</span><span class="sxs-lookup"><span data-stu-id="32d63-565">Bengali</span></span>

  - <span data-ttu-id="32d63-566">Gujarâtî</span><span class="sxs-lookup"><span data-stu-id="32d63-566">Gujarati</span></span>

  - <span data-ttu-id="32d63-567">Telugu</span><span class="sxs-lookup"><span data-stu-id="32d63-567">Telugu</span></span>

  - <span data-ttu-id="32d63-568">Tous les autres scripts Indiens</span><span class="sxs-lookup"><span data-stu-id="32d63-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="32d63-569">Lync Web App, Web Scheduler et composants Web</span><span class="sxs-lookup"><span data-stu-id="32d63-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="32d63-570">La langue de secours pour certaines langues dans Lync Web Scheduler, le lanceur de la Conférence rendez-vous, la gestion des salles de conversation permanente et OCTab peut ne pas fonctionner comme prévu</span><span class="sxs-lookup"><span data-stu-id="32d63-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="32d63-571">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-571">**Issue:**</span></span>

<span data-ttu-id="32d63-572">Lors de la sélection d’un paramètre régional neutre dans un navigateur Web (dans Internet Explorer, par exemple, le nom de la langue sans spécification \[supplémentaire\](par exemple, « norvégien no ») au lieu d’un paramètre régional spécifiant la langue, le script et les \[paramètres régionaux (\]par exemple, « norvégien, Bokmål (Norvège) NB-no ») peut entraîner un comportement inattendu pour certaines langues dans Lync Web Scheduler, le lanceur d’appels, la gestion des salles de conversation permanentes</span><span class="sxs-lookup"><span data-stu-id="32d63-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="32d63-573">Par exemple, les utilisateurs peuvent voir la page en anglais lorsque l’une des langues suivantes est sélectionnée :</span><span class="sxs-lookup"><span data-stu-id="32d63-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="32d63-574">Norvégien</span><span class="sxs-lookup"><span data-stu-id="32d63-574">Norwegian</span></span>

  - <span data-ttu-id="32d63-575">Portugais</span><span class="sxs-lookup"><span data-stu-id="32d63-575">Portuguese</span></span>

  - <span data-ttu-id="32d63-576">Serbe</span><span class="sxs-lookup"><span data-stu-id="32d63-576">Serbian</span></span>

<span data-ttu-id="32d63-577">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-577">**Workaround:**</span></span>

<span data-ttu-id="32d63-578">Si vous voulez sélectionner une langue à l’aide d’un paramètre régional neutre, assurez-vous également d’ajouter la langue avec des paramètres régionaux spécifiques (avec l’indicatif de script et/ou du pays) comme langue supplémentaire dans la liste des préférences linguistiques de votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="32d63-579">La prise en charge des paramètres régionaux azéri et ouzbek est limitée lors de l’utilisation de Lync Web Scheduler, de la Conférence rendez-vous, du lanceur de jointure, de la gestion des salles de conversation permanentes et de OCTab dans certains navigateurs Web</span><span class="sxs-lookup"><span data-stu-id="32d63-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="32d63-580">Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="32d63-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="32d63-581">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-581">**Issue:**</span></span>

<span data-ttu-id="32d63-582">Lorsque vous utilisez Internet Explorer 8 ou Internet Explorer 9 et que vous définissez la langue du navigateur sur azéri (latin) ou ouzbek (latin), les pages de lancement et de connexion sont affichées en anglais ou dans la langue par défaut définie dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="32d63-583">Lorsque vous utilisez les navigateurs Firefox ou chrome et que vous définissez la langue du navigateur sur azéri (latin) ou ouzbek (latin), les langues Lync Web App, Lync Web Scheduler et RGS OCTab apparaissent en anglais ou dans la langue par défaut du navigateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="32d63-584">Les paramètres régionaux ouzbek (latin) ne sont pas pris en charge dans le navigateur Safari.</span><span class="sxs-lookup"><span data-stu-id="32d63-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="32d63-585">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-585">**Workaround:**</span></span>

<span data-ttu-id="32d63-586">Il n’existe aucune solution de contournement pour ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="32d63-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="32d63-587">La flèche déroulante ne figure pas dans la liste « rejoindre la réunion de » dans la version roumaine de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="32d63-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="32d63-588">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-588">**Issue:**</span></span>

<span data-ttu-id="32d63-589">Lorsqu’un utilisateur qui utilise la version roumaine de Lync Web App effectue les étapes suivantes, la flèche déroulante ne s’affiche pas dans la liste déroulante **joindre la réunion** dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="32d63-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="32d63-590">Sélectionnez **Mémoriser mon adresse sur cet ordinateur** sous l’onglet **général** .</span><span class="sxs-lookup"><span data-stu-id="32d63-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="32d63-591">Sélectionnez l’onglet **téléphone** .</span><span class="sxs-lookup"><span data-stu-id="32d63-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="32d63-592">Cliquez sur la liste déroulante pour **participer à une réunion à partir de**.</span><span class="sxs-lookup"><span data-stu-id="32d63-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="32d63-593">Les utilisateurs ne verront pas une flèche indiquant qu’il existe d’autres options que la connexion par défaut de **Lync Web App**, par exemple : **ne pas participer** à la partie audio (en Roumanie, « nu se asociažae » et **nouveau numéro**» (en Roumanie, « număr Nou »).</span><span class="sxs-lookup"><span data-stu-id="32d63-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="32d63-594">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-594">**Workaround:**</span></span>

<span data-ttu-id="32d63-595">Même si la flèche de cette liste déroulante n’est pas affichée, les utilisateurs peuvent toujours sélectionner les paramètres supplémentaires dans la liste en cliquant sur la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="32d63-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="32d63-596">Lors de l’utilisation de la version turque de Lync Web Scheduler, une réunion ne peut pas être enregistrée lors de l’utilisation de l’option « personnes que je choisis » sous « qui est présentateur »</span><span class="sxs-lookup"><span data-stu-id="32d63-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="32d63-597">**Émet**</span><span class="sxs-lookup"><span data-stu-id="32d63-597">**Issue:**</span></span>

<span data-ttu-id="32d63-598">Lors de la création ou de la modification d’une réunion dans la version turque de Lync Web Scheduler, l’option « les personnes que je choisis » sous « qui est présentateur » n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="32d63-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="32d63-599">Lorsque cette option est sélectionnée, la réunion ne peut pas être enregistrée.</span><span class="sxs-lookup"><span data-stu-id="32d63-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="32d63-600">Au lieu de cela, un message d’erreur s’affiche, indiquant qu’une ou plusieurs personnes ne peuvent pas être transformées en présentateurs.</span><span class="sxs-lookup"><span data-stu-id="32d63-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="32d63-601">**Moyens**</span><span class="sxs-lookup"><span data-stu-id="32d63-601">**Workaround:**</span></span>

<span data-ttu-id="32d63-602">Pour contourner ce problème, les utilisateurs peuvent utiliser l’option par défaut « utilisateurs de ma société » ou tout autre choix, tels que « uniquement organisateur » ou « tout le monde, y compris les personnes externes à mon entreprise ».</span><span class="sxs-lookup"><span data-stu-id="32d63-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="32d63-603">L’organisateur peut rétrograder ou promouvoir les utilisateurs à leurs rôles appropriés ultérieurement, après avoir rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="32d63-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="32d63-604">Par ailleurs, les utilisateurs qui comprennent une autre langue peuvent modifier la sélection de la langue dans le navigateur pour l’une des autres langues prises en charge par 43 et tenter d’utiliser l’option « les personnes que je choisis ».</span><span class="sxs-lookup"><span data-stu-id="32d63-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="32d63-605">Reproduction</span><span class="sxs-lookup"><span data-stu-id="32d63-605">Copyright</span></span>

<span data-ttu-id="32d63-606">Ce document prend en charge une version préliminaire d’un produit logiciel dont le changement est susceptible d’être sensiblement antérieur à la version commerciale finale et qui est confidentiel et commercial.</span><span class="sxs-lookup"><span data-stu-id="32d63-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="32d63-607">Il est divulgué par le biais d’un accord de non-divulgation entre le destinataire et Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32d63-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="32d63-608">Ce document est fourni à titre indicatif uniquement et Microsoft ne fournit aucune garantie, expresse ou implicite, dans ce document.</span><span class="sxs-lookup"><span data-stu-id="32d63-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="32d63-609">Les informations contenues dans ce document, y compris les URL et autres références de site Web Internet, peuvent faire l’objet de modifications sans préavis.</span><span class="sxs-lookup"><span data-stu-id="32d63-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="32d63-610">Le risque qu’une utilisation ou des résultats de l’utilisation de ce document reste l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="32d63-611">Sauf mention contraire, les sociétés, organisations, produits, noms de domaines, adresses de messagerie, logos, personnes, lieux et événements décrits dans les exemples ci-dessous sont fictifs.</span><span class="sxs-lookup"><span data-stu-id="32d63-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="32d63-612">Il n’est pas possible d’associer une société, une organisation, un produit, un nom de domaine, une adresse de messagerie, un logo, une personne, un lieu ou un événement.</span><span class="sxs-lookup"><span data-stu-id="32d63-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="32d63-613">Conformément à toutes les lois applicables en matière de copyright, il incombe à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32d63-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="32d63-614">Sans limitation des droits découlant du droit d’auteur, aucune partie de ce document ne pourra être reproduite, stockée ou introduite dans un système de récupération, ni transmise à l’aide d’un moyen quelconque (électronique, mécanique, photocopie, enregistrement ou autre), ou à d’autres fins, sans l’autorisation expresse écrite de Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="32d63-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="32d63-615">Microsoft peut être doté d’un brevet, d’une demande de brevet, de marques commerciales, de droits d’auteur ou d’autres droits de propriété intellectuelle concernant le sujet figurant dans ce document.</span><span class="sxs-lookup"><span data-stu-id="32d63-615">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="32d63-616">À l’exception de ce que prévoit expressément un contrat de licence écrit de la part de Microsoft, la fourniture de ce document ne vous donne aucune licence pour ces brevets, marques commerciales, droits d’auteur ou toute autre propriété intellectuelle.</span><span class="sxs-lookup"><span data-stu-id="32d63-616">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="32d63-617">© 2012 de Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="32d63-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="32d63-618">Tous droits réservés.</span><span class="sxs-lookup"><span data-stu-id="32d63-618">All rights reserved.</span></span>

<span data-ttu-id="32d63-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook et SQL Server sont des marques commerciales ou des marques commerciales déposées de Microsoft Corporation aux États-Unis et/ou dans d’autres pays ou régions.</span><span class="sxs-lookup"><span data-stu-id="32d63-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="32d63-620">Toutes les autres marques déposées sont la propriété de leurs détenteurs respectifs.</span><span class="sxs-lookup"><span data-stu-id="32d63-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

