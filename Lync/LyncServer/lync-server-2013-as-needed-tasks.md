---
title: 'Lync Server 2013 : tâches au besoin'
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
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="52806-102">Tâches selon les besoins dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52806-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52806-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="52806-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="52806-104">Effectuez les tâches suivantes si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="52806-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="52806-105">Ils sont souvent couverts par des procédures standard :</span><span class="sxs-lookup"><span data-stu-id="52806-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="52806-106">**Contrôle total   ** de la sécurité Vous pouvez effectuer ce contrôle régulièrement, en réponse à une mise à niveau ou une nouvelle conception du système de messagerie, ou en réponse à une faille de sécurité lancée (ou réussie).</span><span class="sxs-lookup"><span data-stu-id="52806-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="52806-107">Cette procédure est susceptible de nécessiter des analyses de port sur les serveurs et les pare-feu, d’audit des correctifs de sécurité et de tests de pénétration de tiers.</span><span class="sxs-lookup"><span data-stu-id="52806-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="52806-108">**Remplacer les certificats concernant pour expirer**   vérification le certificat de serveur Lync est l’une des tâches hebdomadaires normales et dans le cadre de la procédure qu’un administrateur doit avoir un enregistrement de la date d’expiration de tous les certificats.</span><span class="sxs-lookup"><span data-stu-id="52806-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="52806-109">Cet enregistrement permet à un administrateur de créer une notification lorsqu’un certificat particulier est sur le lieu d’avoir expiré et remplacé selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="52806-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="52806-110">\*\*\*\*   Mise à jour des résultats de performance mettez à jour les références de performance suite à une mise à niveau ou modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="52806-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="52806-111">Votre organisation peut utiliser des plannings de référence pour mesurer les changements de performances et détecter les problèmes qui affectent les performances du système.</span><span class="sxs-lookup"><span data-stu-id="52806-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="52806-112">**La gestion**   de la configuration initiale du pool d’entreprise, des serveurs Standard Edition et de tout autre serveur dans l’environnement de votre organisation, s’est effectuée lors du déploiement de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="52806-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="52806-113">La gestion après le déploiement de serveurs et de pools pour les serveurs Standard Edition et les pools d’entreprise inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="52806-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="52806-114">Gestion des serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="52806-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="52806-115">Gestion des conférences Web</span><span class="sxs-lookup"><span data-stu-id="52806-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="52806-116">Gestion des conférences</span><span class="sxs-lookup"><span data-stu-id="52806-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="52806-117">Modification des informations d’identification d’un compte de service</span><span class="sxs-lookup"><span data-stu-id="52806-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="52806-118">Gestion des bases de données</span><span class="sxs-lookup"><span data-stu-id="52806-118">Managing Databases</span></span>
    
      - <span data-ttu-id="52806-119">Démarrage et arrêt des services et désactivation des rôles de serveur</span><span class="sxs-lookup"><span data-stu-id="52806-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="52806-120">Suppression de serveurs et de rôles de serveur, suppression de pools et désaffectation de serveurs et de pools</span><span class="sxs-lookup"><span data-stu-id="52806-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="52806-121">**Gestion de l’utilisation**   vous pouvez configurer Lync Server 2013 pour proposer les fonctionnalités et fonctionnalités qui conviennent le mieux à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="52806-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="52806-122">Il s’agit notamment de ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="52806-122">This includes the following:</span></span>
    
      - <span data-ttu-id="52806-123">Gestion de la prise en charge des réunions locales de conférences sur le Web</span><span class="sxs-lookup"><span data-stu-id="52806-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="52806-124">Gestion de l’utilisation des groupes de distribution pour envoyer des messages instantanés</span><span class="sxs-lookup"><span data-stu-id="52806-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="52806-125">Gestion des contacts, de la présence et des requêtes</span><span class="sxs-lookup"><span data-stu-id="52806-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="52806-126">Configuration du filtrage des versions du client</span><span class="sxs-lookup"><span data-stu-id="52806-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="52806-127">Configuration du filtrage du message instantané intelligent</span><span class="sxs-lookup"><span data-stu-id="52806-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="52806-128">Configuration de l’archivage, de l’enregistrement des détails des appels et de la conformité aux réunions</span><span class="sxs-lookup"><span data-stu-id="52806-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="52806-129">\*\*\*\*   Gestion en continu de la connectivité Edge Server les serveurs et les paramètres requis pour fournir une connectivité externe incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="52806-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="52806-130">Gestion de la connectivité entre les serveurs internes et les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="52806-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="52806-131">Configuration d’interfaces et de certificats internes et externes pour les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="52806-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="52806-132">Gestion de l’accès des partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="52806-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="52806-133">**L’administration du carnet d'**   adresses qui administre les serveurs du carnet d’adresses inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="52806-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="52806-134">Configuration de la normalisation du téléphone du serveur du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="52806-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="52806-135">Gestion du serveur du carnet d’adresses à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="52806-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="52806-136">\*\*\*\*   La gestion des comptes d’utilisateur pour la gestion des comptes d’utilisateurs comprend les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="52806-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="52806-137">Activation de comptes d’utilisateur pour Lync Server</span><span class="sxs-lookup"><span data-stu-id="52806-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="52806-138">Configuration des utilisateurs de Lync Server à l’aide de l’Assistant</span><span class="sxs-lookup"><span data-stu-id="52806-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="52806-139">Configuration de propriétés de compte d’utilisateur Lync Server individuelles</span><span class="sxs-lookup"><span data-stu-id="52806-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="52806-140">Rechercher des utilisateurs de Lync Server</span><span class="sxs-lookup"><span data-stu-id="52806-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="52806-141">Déplacement des utilisateurs de Lync Server</span><span class="sxs-lookup"><span data-stu-id="52806-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="52806-142">Supprimer des utilisateurs de Lync Server</span><span class="sxs-lookup"><span data-stu-id="52806-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="52806-143">\*\*\*\*   Pour résoudre les problèmes, l’outil de journalisation de Lync Server 2013 est décrit en détail dans [l’article utilisation de l’outil journal](http://technet.microsoft.com/en-us/library/gg558599.aspx)de Lync Server 2013.2013</span><span class="sxs-lookup"><span data-stu-id="52806-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span></span>

<span data-ttu-id="52806-144">Dans la mesure où l’outil journalisation génère des fichiers journaux (sur la base du serveur), ces fichiers journaux peuvent être affichés et analysés à l’aide de l’outil Snoop, si les outils du kit de ressources Microsoft Office Server 12 sont installés sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="52806-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="52806-145">Dans le cas contraire, les journaux peuvent également être analysés à l’aide d’un éditeur de texte, qui est beaucoup moins transparent et plus complexe que l’utilisation de l’utilitaire Snoop.</span><span class="sxs-lookup"><span data-stu-id="52806-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="52806-146">Pour afficher et analyser les messages de protocole</span><span class="sxs-lookup"><span data-stu-id="52806-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="52806-147">Dans l’outil journalisation, une fois que vous avez terminé la session de débogage, cliquez sur analyse des fichiers journaux pour afficher les fichiers journaux à l’aide de l’outil de vérification de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="52806-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="52806-148">Vous pouvez analyser les journaux de protocole pour les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="52806-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="52806-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="52806-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="52806-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="52806-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="52806-151">Trafic de signalisation des conférences Lync Server (C3P), y compris MCU infra C3P et Focus C3P</span><span class="sxs-lookup"><span data-stu-id="52806-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="52806-152">Trafic de conférence Web Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="52806-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="52806-153">Client de plate-forme client de communications unifiées Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="52806-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="52806-154">Rapports d’erreur de la base de données d’archivage</span><span class="sxs-lookup"><span data-stu-id="52806-154">Error reports from the archiving database</span></span>

<span data-ttu-id="52806-155">Pour vous aider à organiser les performances des tâches au besoin, voir liste de contrôle des opérations selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="52806-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52806-156">Pour obtenir des instructions d’administration et de gestion détaillées, voir le Guide d’administration de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52806-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="52806-157">Backup (and Restore) ou paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="52806-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="52806-158">Lync Server 2013 vous permet de sauvegarder et de restaurer tout le système.</span><span class="sxs-lookup"><span data-stu-id="52806-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="52806-159">IIF vous voulez sauvegarder (et peut-être restaurer une seule action) une seule stratégie ou une collection unique de paramètres de configuration, récupérer la stratégie appropriée, puis canalr cet objet vers l’applet de passe Export-Clixml, qui enregistre les informations de stratégie sous forme de fichier XML :</span><span class="sxs-lookup"><span data-stu-id="52806-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="52806-160">Vous pouvez maintenant tester RedmondClientPolicy et modifier de nombreux paramètres.</span><span class="sxs-lookup"><span data-stu-id="52806-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="52806-161">Si vous préférez procéder à la restauration de l’ancienne stratégie, entrez :</span><span class="sxs-lookup"><span data-stu-id="52806-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="52806-162">Notez que cette approche fonctionne pour la plupart des stratégies et des paramètres, mais qu’elle ne fonctionne pas avec certains éléments plus complexes, c’est-à-dire des éléments contenant plusieurs sous-objets (par exemple, les paramètres de configuration de routage, qui contiennent de nombreux itinéraires vocaux différents).</span><span class="sxs-lookup"><span data-stu-id="52806-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

