---
title: Processus de migration - Détails
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="15cfe-102">Processus de migration - Détails</span><span class="sxs-lookup"><span data-stu-id="15cfe-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15cfe-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="15cfe-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="15cfe-104">Pour migrer vers Lync Server 2013, le serveur de chat permanent, vous devez disposer des éléments requis suivants et des étapes détaillées de migration de Lync Server 2010, de discussion de groupe ou d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="15cfe-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="15cfe-105">Conditions préalables à la migration</span><span class="sxs-lookup"><span data-stu-id="15cfe-105">Prerequisites for Migration</span></span>

<span data-ttu-id="15cfe-106">Assurez-vous que vous remplissez les conditions préalables suivantes avant de procéder à la migration de Lync Server 2010, d’une conversation de groupe ou d’une conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="15cfe-107">Déploiement d’au moins un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15cfe-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="15cfe-108">Si vous avez plusieurs pools Lync Server 2013, déterminez le pool Lync Server 2013, le pool Home pour le nouveau pool Lync Server 2013 Chat Server.</span><span class="sxs-lookup"><span data-stu-id="15cfe-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="15cfe-109">Installez Lync Server 2013, le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="15cfe-110">Il sera vide (aucune catégorie, salle ou complément).</span><span class="sxs-lookup"><span data-stu-id="15cfe-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="15cfe-111">Avant de migrer vos catégories, salles ou compléments hérités, vous pouvez créer des salles, des catégories ou des compléments dans votre Lync Server 2013, le déploiement permanent du serveur Chat.</span><span class="sxs-lookup"><span data-stu-id="15cfe-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="15cfe-112">Gardez à l’esprit que ces éléments nouvellement créés risquent de entrer en conflit avec des éléments hérités que vous migrez.</span><span class="sxs-lookup"><span data-stu-id="15cfe-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="15cfe-113">Éviter les conflits de noms ; Sinon, ils sont écrasés lors de la migration des données héritées.</span><span class="sxs-lookup"><span data-stu-id="15cfe-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="15cfe-114">Préparation des données sources pour la migration</span><span class="sxs-lookup"><span data-stu-id="15cfe-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="15cfe-115">Suivez les étapes ci-dessous pour préparer correctement vos données sources pour la migration.</span><span class="sxs-lookup"><span data-stu-id="15cfe-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="15cfe-116">Sauvegardez les bases de données sources pour Lync Server 2010, les discussions de groupe ou les discussions de groupe Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="15cfe-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="15cfe-117">Pour plus d’informations sur la façon de sauvegarder SQL Server, voir « vue d’ensemble de la <http://go.microsoft.com/fwlink/p/?linkid=254851>sauvegarde (SQL Server) ».</span><span class="sxs-lookup"><span data-stu-id="15cfe-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="15cfe-118">Les services de domaine Active Directory doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="15cfe-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="15cfe-119">Dans le cadre de la migration, vous ne pouvez pas effectuer de migration vers un pool dans un autre déploiement (plus précisément dans une autre forêt Active Directory).</span><span class="sxs-lookup"><span data-stu-id="15cfe-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="15cfe-120">Inspectez votre Lync Server 2010, vos discussions de groupe ou les salles de conversation de groupe et la configuration des catégories de Lync Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="15cfe-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="15cfe-121">Toute modification apportée à des catégories, des salles ou des compléments dans votre déploiement hérité actuel est réalisée par l’outil d’administration de discussion de groupe.</span><span class="sxs-lookup"><span data-stu-id="15cfe-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="15cfe-122">Toute modification apportée à des catégories, des salles ou des compléments dans votre Lync Server 2013, le déploiement de serveur de chat permanent est effectué par le panneau de configuration de Lync Server ou les applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15cfe-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="15cfe-123">Suivez ces étapes pour préparer votre système hérité à des fins de migration.</span><span class="sxs-lookup"><span data-stu-id="15cfe-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="15cfe-124">Le serveur Chat permanent prend en charge un seul niveau de catégories, contrairement à un ensemble hiérarchique de catégories.</span><span class="sxs-lookup"><span data-stu-id="15cfe-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="15cfe-125">Après la migration, les sous-catégories sont préfixées avec les noms de catégorie parents complets.</span><span class="sxs-lookup"><span data-stu-id="15cfe-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="15cfe-126">Vous voudrez peut-être simplifier et aplatir votre structure de catégorie existante pour que la structure qui en résulte réponde à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="15cfe-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="15cfe-127">Vérifiez les **responsables** de la catégorie racine.</span><span class="sxs-lookup"><span data-stu-id="15cfe-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="15cfe-128">S’il existe des gestionnaires à ce niveau, ces utilisateurs seront ajoutés comme **responsables à toutes les pièces** après la migration.</span><span class="sxs-lookup"><span data-stu-id="15cfe-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="15cfe-129">Si ce n’est pas une obligation pour votre organisation, vous devez supprimer ces responsables de la catégorie racine.</span><span class="sxs-lookup"><span data-stu-id="15cfe-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="15cfe-130">Vérifiez la longueur des noms de salle.</span><span class="sxs-lookup"><span data-stu-id="15cfe-130">Verify the length of room names.</span></span> <span data-ttu-id="15cfe-131">Après la migration, en raison de la présence de structures de catégories simplifiées, les noms de catégorie parent complet sont préfixés.</span><span class="sxs-lookup"><span data-stu-id="15cfe-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="15cfe-132">La limite d’appellation est de 256 caractères, y compris les noms de catégorie parent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="15cfe-133">Vous devez vérifier la longueur des noms de la salle et, éventuellement, réduire sa longueur, s’il est trop long.</span><span class="sxs-lookup"><span data-stu-id="15cfe-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="15cfe-134">Dans Lync Server 2013, si les paramètres d' **invitations** de catégorie sont définis sur true, vous pouvez choisir true ou false pour les invitations aux salles de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="15cfe-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="15cfe-135">Toutefois, si les paramètres d’invitations de la catégorie sont définis sur false, les invitations sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="15cfe-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="15cfe-136">Avant de procéder à la migration, vous devez réinitialiser les paramètres d’invitation dans votre version du serveur de conversation de groupe Lync Server héritée, si vous souhaitez que la salle (s) existe dans une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="15cfe-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="15cfe-137">Dans le cadre de la migration, Lync Server 2013 affiche les avertissements et définit les salles sur la valeur par défaut false.</span><span class="sxs-lookup"><span data-stu-id="15cfe-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="15cfe-138">Si vous avez utilisé des fichiers dans des salles de conversation, vous devez restaurer manuellement les fichiers dans le nouveau magasin de fichiers de chat permanent après la migration.</span><span class="sxs-lookup"><span data-stu-id="15cfe-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="15cfe-139">Ce n’est pas le cas pour les outils.</span><span class="sxs-lookup"><span data-stu-id="15cfe-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="15cfe-140">Si vous aviez des utilisateurs fédérés et des salles avec des utilisateurs fédérés, sachez que le serveur Chat permanent ne prend pas en charge la Fédération.</span><span class="sxs-lookup"><span data-stu-id="15cfe-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="15cfe-141">Les salles avec des utilisateurs fédérés seront migrées ; Toutefois, les utilisateurs ne seront pas en mesure d’accéder au contenu, car l’accès fédéré n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="15cfe-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="15cfe-142">Identifiez les salles que vous ne souhaitez pas migrer et marquez-les comme désactivées.</span><span class="sxs-lookup"><span data-stu-id="15cfe-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="15cfe-143">Déterminez la date au-delà de laquelle vous souhaitez migrer le contenu de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="15cfe-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="15cfe-144">Par exemple, il est possible que vous ne souhaitiez pas migrer des messages antérieurs au 1er janvier 2010, car ces messages risquent d’être obsolètes ou non pertinents pour la migration.</span><span class="sxs-lookup"><span data-stu-id="15cfe-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="15cfe-145">Exécution de la migration</span><span class="sxs-lookup"><span data-stu-id="15cfe-145">Performing the Migration</span></span>

<span data-ttu-id="15cfe-146">Suivez les étapes ci-dessous pour migrer votre serveur de discussion de groupe hérité.</span><span class="sxs-lookup"><span data-stu-id="15cfe-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="15cfe-147">Arrêtez le serveur Lync Server 2010, les discussions de groupe, les discussions de groupe Office Communications Server 2007 R2 ou Lync Server 2013, services de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="15cfe-148">Tous les services doivent être arrêtés, donc envisagez d’y parvenir à un moment où le temps d’arrêt est suffisant.</span><span class="sxs-lookup"><span data-stu-id="15cfe-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="15cfe-149">Comme décrit précédemment, assurez-vous de sauvegarder votre base de données de discussion de groupe actuelle.</span><span class="sxs-lookup"><span data-stu-id="15cfe-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="15cfe-150">Exécutez l’applet de la cmdlet Windows PowerShell **Export-CsPersistentChatData** en tant que membre du rôle RBAC administrateur de chat permanent (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="15cfe-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="15cfe-151">Pour plus d’informations sur les applets de connexion d’exportation et d’importation, voir [résolution des problèmes de configuration du serveur de chat permanent au moyen des cmdlets Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="15cfe-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="15cfe-152">Inspectez le contenu exporté.</span><span class="sxs-lookup"><span data-stu-id="15cfe-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="15cfe-153">Avant de pouvoir procéder à l’importation, fermez Lync Server 2013 et les services serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="15cfe-154">Tous les services doivent être arrêtés, donc envisagez d’y parvenir à un moment où le temps d’arrêt est suffisant.</span><span class="sxs-lookup"><span data-stu-id="15cfe-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="15cfe-155">Effectuez une sauvegarde de la base de données de chat permanent si vous avez créé des catégories, des salles ou des compléments dans votre déploiement Lync Server 2013 avant la migration.</span><span class="sxs-lookup"><span data-stu-id="15cfe-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="15cfe-156">Le processus d’exportation/importation est en mesure de fusionner les données héritées dans le déploiement de Lync Server 2013, mais il est préférable de sauvegarder la base de données au cas où le contenu serait involontairement écrasé (par exemple, en cas de conflit d’attribution de noms).</span><span class="sxs-lookup"><span data-stu-id="15cfe-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="15cfe-157">Exécutez l’applet de commande Windows PowerShell **Import-CsPersistentChatData** (outil d’importation), avec une commande **WhatIf** pour remplir le serveur principal du pool de serveurs de chat permanent avec les données déplacées.</span><span class="sxs-lookup"><span data-stu-id="15cfe-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="15cfe-158">Certaines conversions se produisent dans le processus pour s’adapter au modèle d’administration simplifié.</span><span class="sxs-lookup"><span data-stu-id="15cfe-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="15cfe-159">Corrigez les erreurs ou avertissements qui s’affichent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="15cfe-160">Exécutez l’applet de la cmdlet Windows PowerShell **Import-CsPersistentChatData** en tant que membre du rôle RBAC de l’administrateur de chat permanent (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="15cfe-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="15cfe-161">Pour plus d’informations sur les applets de connexion d’exportation et d’importation, voir [résolution des problèmes de configuration du serveur de chat permanent au moyen des cmdlets Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="15cfe-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="15cfe-162">Vous devez enregistrer tous les fichiers téléchargés (le dossier complet) sur le nouveau Lync Server 2013, magasin de fichiers de conversation permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="15cfe-163">Lync 2013 (client) ne prend pas en charge le chargement ou l’affichage de fichiers dans des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="15cfe-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="15cfe-164">Vous pouvez toujours utiliser le client hérité pour publier et afficher des fichiers dans la salle.</span><span class="sxs-lookup"><span data-stu-id="15cfe-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="15cfe-165">Sur le port de Lync Server 2010, de discussion de groupe ou d’Office Communications Server 2007 R2, le serveur de recherche de discussion de groupe sur Lync Server 2013, objet de contact du serveur de conversation permanent</span><span class="sxs-lookup"><span data-stu-id="15cfe-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="15cfe-166">Les étapes suivantes sont nécessaires si votre discussion de groupe Lync 2010 ou les clients de conversation de groupe Office Communicator 2007 R2 doivent se connecter à la dernière version de Lync 2013, de conversation permanente (client) après la migration sans modification de configuration côté client :</span><span class="sxs-lookup"><span data-stu-id="15cfe-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="15cfe-167">Supprimez le\<compte\>d’utilisateur du serveur de recherche OCSChat@ NomDomaine. com.</span><span class="sxs-lookup"><span data-stu-id="15cfe-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="15cfe-168">Il a été utilisé pour pointer vers le service de recherche dans Lync Server 2010, discussion de groupe.</span><span class="sxs-lookup"><span data-stu-id="15cfe-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="15cfe-169">Vous pouvez désinstaller le pool et supprimer les entrées approuvées ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="15cfe-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="15cfe-170">Créer un point de terminaison hérité (objet de contact de chat permanent) en exécutant l’applet de cmdlet Windows PowerShell, **New-CsPersistentChatEndpoint**, avec l’URI SIP identique de sorte que le client hérité puisse fonctionner efficacement au redémarrage du service.</span><span class="sxs-lookup"><span data-stu-id="15cfe-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="15cfe-171">Le processus de migration obligatoire est terminé à ce stade.</span><span class="sxs-lookup"><span data-stu-id="15cfe-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="15cfe-172">Les discussions de groupe Lync 2010 (clients) ou les discussions de groupe Office Communicator 2007 R2 (clients) peuvent se connecter au nouveau pool de serveurs de chat permanent désormais, de manière transparente.</span><span class="sxs-lookup"><span data-stu-id="15cfe-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="15cfe-173">Suivez ces étapes supplémentaires de désaffectation pour Lync Server 2010, les discussions de groupe ou la discussion de groupe Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="15cfe-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="15cfe-174">Démarrez les services serveur de chat permanent en activant tous les ordinateurs du nouveau pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="15cfe-175">Utilisez les applets de commande du panneau de configuration de Lync Server et de Windows PowerShell pour vérifier que les données ont bien été déplacées.</span><span class="sxs-lookup"><span data-stu-id="15cfe-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="15cfe-176">Désinstallez la discussion de groupe Lync 2010 ou la discussion de groupe Office Communicator 2007 R2 sur les ordinateurs du pool de serveurs de discussion de groupe.</span><span class="sxs-lookup"><span data-stu-id="15cfe-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="15cfe-177">Supprimez l’application approuvée et le pool d’applications approuvé à l’aide de cmdlets Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15cfe-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="15cfe-178">Cela supprime les éléments suivants du magasin de gestion central et des entrées de service de confiance associées dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="15cfe-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="15cfe-179">Par ailleurs, cette étape fonctionne à l’aide du générateur de topologie (les applications/pools approuvés disposent également d’un nœud dédié).</span><span class="sxs-lookup"><span data-stu-id="15cfe-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="15cfe-180">Vous pouvez à présent commencer à activer la fonctionnalité serveur de chat permanent par le biais des nouveaux clients.</span><span class="sxs-lookup"><span data-stu-id="15cfe-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="15cfe-181">Pour plus d’informations sur l’activation d’un serveur de chat permanent, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="15cfe-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="15cfe-182">Lync Server 2013 prend en charge plusieurs pools de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="15cfe-183">Néanmoins, nous prenons en charge la migration d’une conversation de groupe Lync 2010 ou&nbsp;d’une liste de discussion de groupe Office Communications Server 2007 R2 vers une seule Lync Server 2013, un pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="15cfe-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="15cfe-184">Vous pouvez ajouter des regroupements de serveurs de chat permanents supplémentaires dans votre déploiement pour répondre aux besoins en matière de réglementation (par exemple, conservation des données au sein d’une géographie donnée).</span><span class="sxs-lookup"><span data-stu-id="15cfe-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

