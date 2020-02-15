---
title: 'Lync Server 2013 : tâches en fonction des besoins'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67a0355d32e5e704d6609335c82f8cfe1fe7aa86
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="97210-102">Tâches nécessaires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97210-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97210-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="97210-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="97210-104">Effectuez les tâches suivantes si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="97210-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="97210-105">Ils sont souvent également couverts par les procédures standard :</span><span class="sxs-lookup"><span data-stu-id="97210-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="97210-106">**Audit de sécurité complet   ** Vous pouvez effectuer cet audit régulièrement, en réponse à une mise à niveau ou à une nouvelle conception du système de messagerie, ou en réponse à une violation de sécurité.</span><span class="sxs-lookup"><span data-stu-id="97210-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="97210-107">La procédure peut impliquer des analyses de ports sur les serveurs et pare-feu, des audits de correctifs de sécurité et des tests de pénétration tiers.</span><span class="sxs-lookup"><span data-stu-id="97210-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="97210-108">**Remplacer les certificats sur le terme de l’expiration**   de la vérification les certificats Lync Server sont l’une des tâches hebdomadaires normales et, dans le cadre de la procédure, un administrateur doit disposer d’un enregistrement de la date d’expiration de tous les certificats.</span><span class="sxs-lookup"><span data-stu-id="97210-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="97210-109">Cet enregistrement permet à un administrateur de créer une notification lorsqu’un certificat particulier est sur le sujet de la date d’expiration et remplacé si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="97210-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="97210-110">\*\*\*\*   Mise à jour des lignes de base des performances mettez à jour les lignes de base des performances après une modification ou une modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="97210-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="97210-111">Votre organisation peut utiliser des lignes de base pour mesurer les changements de performances et détecter les problèmes qui affectent les performances du système.</span><span class="sxs-lookup"><span data-stu-id="97210-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="97210-112">**La gestion**   de la configuration initiale des pools d’entreprise des pools d’entreprise, des serveurs Standard Edition et de tous les autres serveurs de l’environnement de votre organisation a été réalisée lors du déploiement des serveurs individuels.</span><span class="sxs-lookup"><span data-stu-id="97210-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="97210-113">La gestion post-déploiement des serveurs et des pools pour les serveurs Standard Edition et les pools d’entreprise comprend les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="97210-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="97210-114">Gestion de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="97210-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="97210-115">Gestion des conférences Web</span><span class="sxs-lookup"><span data-stu-id="97210-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="97210-116">Gestion des conférences</span><span class="sxs-lookup"><span data-stu-id="97210-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="97210-117">Modification des informations d’identification du compte de service</span><span class="sxs-lookup"><span data-stu-id="97210-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="97210-118">Gestion des bases de données</span><span class="sxs-lookup"><span data-stu-id="97210-118">Managing Databases</span></span>
    
      - <span data-ttu-id="97210-119">Démarrage et arrêt des services et désactivation des rôles serveur</span><span class="sxs-lookup"><span data-stu-id="97210-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="97210-120">Suppression des serveurs et des rôles serveur, suppression des pools et mise hors service des serveurs et pools</span><span class="sxs-lookup"><span data-stu-id="97210-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="97210-121">**Gestion de l’utilisation**   vous pouvez configurer Lync Server 2013 pour fournir les fonctionnalités les plus appropriées pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="97210-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="97210-122">Les voici :</span><span class="sxs-lookup"><span data-stu-id="97210-122">This includes the following:</span></span>
    
      - <span data-ttu-id="97210-123">Gestion de la prise en charge des réunions de conférence Web sur site</span><span class="sxs-lookup"><span data-stu-id="97210-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="97210-124">Gestion de l’utilisation des groupes de distribution pour envoyer des messages instantanés</span><span class="sxs-lookup"><span data-stu-id="97210-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="97210-125">Gestion des contacts, de la présence et des requêtes</span><span class="sxs-lookup"><span data-stu-id="97210-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="97210-126">Configuration du filtrage de version du client</span><span class="sxs-lookup"><span data-stu-id="97210-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="97210-127">Configuration du filtrage de messagerie instantanée intelligent</span><span class="sxs-lookup"><span data-stu-id="97210-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="97210-128">Configuration de l’archivage, de l’enregistrement des détails des appels et de la conformité aux réunions</span><span class="sxs-lookup"><span data-stu-id="97210-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="97210-129">**Gestion**   de la connectivité de serveur Edge la gestion continue des serveurs et des paramètres requis pour fournir la connectivité externe inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="97210-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="97210-130">Gestion de la connectivité entre les serveurs internes et les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="97210-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="97210-131">Configuration des interfaces internes et externes et des certificats pour les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="97210-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="97210-132">Gestion de l’accès des partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="97210-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="97210-133">**Administrer le carnet d'**   adresses les serveurs de carnets d’adresses incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="97210-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="97210-134">Configuration de la normalisation des téléphones du serveur de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="97210-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="97210-135">Gestion du serveur de carnet d’adresses à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="97210-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="97210-136">\*\*\*\*   La gestion des comptes d’utilisateur pour la gestion des comptes d’utilisateurs comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="97210-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="97210-137">Activation des comptes d’utilisateur pour Lync Server</span><span class="sxs-lookup"><span data-stu-id="97210-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="97210-138">Configuration des utilisateurs de Lync Server à l’aide de l’Assistant</span><span class="sxs-lookup"><span data-stu-id="97210-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="97210-139">Configuration des propriétés de compte d’utilisateur Lync Server individuelles</span><span class="sxs-lookup"><span data-stu-id="97210-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="97210-140">Recherche d’utilisateurs Lync Server</span><span class="sxs-lookup"><span data-stu-id="97210-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="97210-141">Migration des utilisateurs de Lync Server</span><span class="sxs-lookup"><span data-stu-id="97210-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="97210-142">Suppression d’utilisateurs Lync Server</span><span class="sxs-lookup"><span data-stu-id="97210-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="97210-143">**Analyse des fichiers**   journaux Lync Server 2013 un outil très utile, généralement utilisé pour la résolution des problèmes, est l’outil de journalisation Lync Server 2013 décrit en détail dans [utilisation de l’outil de journalisation Lync Server 2013](http://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="97210-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="97210-144">Étant donné que l’outil de journalisation génère des fichiers journaux (par serveur), ces fichiers journaux peuvent être affichés et analysés à l’aide de l’outil Snooper, si les outils du kit de ressources Microsoft Office Server 12 sont installés sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="97210-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="97210-145">Dans le cas contraire, les journaux peuvent également être analysés à l’aide d’un éditeur de texte, ce qui est bien moins transparent et plus complexe que l’utilisation de l’utilitaire de surveillance.</span><span class="sxs-lookup"><span data-stu-id="97210-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="97210-146">Pour afficher et analyser les messages de protocole</span><span class="sxs-lookup"><span data-stu-id="97210-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="97210-147">Dans l’outil de journalisation, lorsque vous avez terminé la session de débogage, cliquez sur analyser les fichiers journaux pour afficher les fichiers journaux à l’aide de l’outil Snooper.</span><span class="sxs-lookup"><span data-stu-id="97210-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="97210-148">Vous pouvez analyser les journaux de protocole pour les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="97210-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="97210-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="97210-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="97210-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="97210-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="97210-151">Trafic de signalisation de conférence Lync Server (C3P), y compris le trafic MCU C3P et le focus C3P</span><span class="sxs-lookup"><span data-stu-id="97210-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="97210-152">Trafic de conférence Web Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="97210-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="97210-153">Client de plateforme de communications unifiées Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="97210-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="97210-154">Rapports d’erreur de la base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="97210-154">Error reports from the archiving database</span></span>

<span data-ttu-id="97210-155">Pour vous aider à organiser les performances des tâches selon vos besoins, voir liste de vérification des opérations selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="97210-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97210-156">Pour plus d’informations sur les procédures d’administration et de gestion, consultez le Guide d’administration de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97210-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="97210-157">Stratégies de sauvegarde (et restauration) ou paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="97210-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="97210-158">Lync Server 2013 permet de sauvegarder et de restaurer l’ensemble du système.</span><span class="sxs-lookup"><span data-stu-id="97210-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="97210-159">IIF que vous souhaitez sauvegarder (et éventuellement effectuer une restauration à un jour) une seule stratégie ou une seule collection de paramètres de configuration, récupérez la stratégie appropriée, puis dirigez cet objet vers la cmdlet Export-Clixml, qui enregistre les informations de stratégie sous la forme d’un fichier XML :</span><span class="sxs-lookup"><span data-stu-id="97210-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="97210-160">Vous pouvez maintenant expérimenter RedmondClientPolicy et modifier un grand nombre de paramètres.</span><span class="sxs-lookup"><span data-stu-id="97210-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="97210-161">Si, au lieu de cela, vous décidez de restaurer l’ancienne stratégie, entrez :</span><span class="sxs-lookup"><span data-stu-id="97210-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="97210-162">Notez que cette approche fonctionnera pour la plupart des stratégies et des paramètres, mais elle ne fonctionnera pas avec certains des éléments plus complexes : les éléments qui contiennent plusieurs sous-objets (par exemple, les paramètres de configuration de routage, qui contiennent un grand nombre d’itinéraires vocaux distincts).</span><span class="sxs-lookup"><span data-stu-id="97210-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

