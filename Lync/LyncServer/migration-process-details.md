---
title: Processus de migration-détails
description: Processus de migration-détails.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569580"
---
# <a name="migration-process---details"></a><span data-ttu-id="06fbe-103">Processus de migration-détails</span><span class="sxs-lookup"><span data-stu-id="06fbe-103">Migration process - details</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06fbe-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="06fbe-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="06fbe-105">Utilisez les conditions préalables et les étapes détaillées suivantes pour migrer Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat vers Lync Server 2013, serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="06fbe-105">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="06fbe-106">Conditions préalables pour la migration</span><span class="sxs-lookup"><span data-stu-id="06fbe-106">Prerequisites for Migration</span></span>

<span data-ttu-id="06fbe-107">Veillez à respecter les conditions préalables suivantes avant de migrer Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat vers Lync Server 2013, serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="06fbe-107">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="06fbe-108">Déployez au moins un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06fbe-108">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="06fbe-109">Si vous avez plusieurs pools Lync Server 2013, déterminez quel pool Lync Server 2013 sera le pool d’accueil pour le nouveau pool de serveurs Lync Server 2013 persistent chat.</span><span class="sxs-lookup"><span data-stu-id="06fbe-109">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="06fbe-110">Installez le pool de serveurs Lync Server 2013, persistent chat.</span><span class="sxs-lookup"><span data-stu-id="06fbe-110">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="06fbe-111">Il sera vide (pas de catégorie, de salle et de complément).</span><span class="sxs-lookup"><span data-stu-id="06fbe-111">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="06fbe-112">Avant de migrer vos catégories, salles ou compléments hérités, vous pouvez créer des salles, des catégories ou des compléments dans votre déploiement de serveur de conversation permanente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06fbe-112">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="06fbe-p103">Notez que ces éléments nouvellement créés peuvent entrer en conflit avec les éléments hérités que vous migrez. Évitez tout conflit de nom, sans quoi ils seront remplacés à la migration des données héritées.</span><span class="sxs-lookup"><span data-stu-id="06fbe-p103">Be aware that these newly created items may conflict with legacy items that you migrate. Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="06fbe-115">Préparation des données sources pour la migration</span><span class="sxs-lookup"><span data-stu-id="06fbe-115">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="06fbe-116">Pour préparer correctement vos données sources pour la migration, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="06fbe-116">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="06fbe-117">Sauvegardez les bases de données sources pour Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat.</span><span class="sxs-lookup"><span data-stu-id="06fbe-117">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="06fbe-118">Pour plus d’informations sur la sauvegarde de SQL Server, voir « vue d’ensemble de la sauvegarde (SQL Server) » à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=254851> .</span><span class="sxs-lookup"><span data-stu-id="06fbe-118">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="06fbe-119">Les services de domaine Active Directory doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="06fbe-119">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="06fbe-120">En guise de condition de migration, vous ne pouvez pas migrer vers un pool dans un autre déploiement (en particulier dans une forêt Active Directory différente).</span><span class="sxs-lookup"><span data-stu-id="06fbe-120">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="06fbe-121">Inspectez votre configuration de catégorie Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat.</span><span class="sxs-lookup"><span data-stu-id="06fbe-121">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="06fbe-122">Toute modification apportée à des catégories, des salles ou des compléments dans votre déploiement hérité existant sera réalisée par l’outil d’administration de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="06fbe-122">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="06fbe-123">Toute modification apportée à des catégories, des salles ou des compléments dans votre déploiement de serveur de conversation permanente Lync Server 2013 est effectuée par le panneau de configuration ou les applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06fbe-123">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="06fbe-124">Pour préparer votre système hérité pour la migration, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="06fbe-124">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="06fbe-125">Le serveur de conversation permanente prend en charge un seul niveau de catégories, contrairement à un ensemble hiérarchique profond de catégories.</span><span class="sxs-lookup"><span data-stu-id="06fbe-125">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="06fbe-126">Après la migration, les sous-catégories sont précédées du nom complet de la catégorie parent.</span><span class="sxs-lookup"><span data-stu-id="06fbe-126">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="06fbe-127">Vous pouvez simplifier votre structure de catégories existante afin que la structure qui en résulte satisfasse vos conditions.</span><span class="sxs-lookup"><span data-stu-id="06fbe-127">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="06fbe-p108">Vérifiez les **responsables** dans la catégorie racine. Si des responsables existent à ce niveau, ces utilisateurs seront ajoutés en tant que **responsables de toutes les salles** après la migration. S’il ne s’agit pas d’un impératif pour votre organisation, vous devez supprimer ces responsables de la catégorie racine.</span><span class="sxs-lookup"><span data-stu-id="06fbe-p108">Verify the **Managers** at the root Category. If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration. If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="06fbe-p109">Vérifiez la longueur des noms de salle. Après la migration, en raison des structures de catégories simplifiées, si les salles existent sous une catégorie enfant, elles sont précédées du nom complet de la catégorie parent. Les noms peuvent inclure jusqu’à 256 caractères (nom de la catégorie parent inclus). Vous devez vérifier la longueur des noms de salle et éventuellement les raccourcir s’ils sont trop longs.</span><span class="sxs-lookup"><span data-stu-id="06fbe-p109">Verify the length of room names. After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names. The naming limit is 256 characters, including parent category names. You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="06fbe-135">Dans Lync Server 2013, si les paramètres des **invitations** aux catégories sont définis sur true, vous pouvez choisir true ou false pour les invitations à des salles sous cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="06fbe-135">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="06fbe-136">Cependant, si les paramètres des invitations de catégorie sont définis sur false, les invitations des salles sous cette catégorie sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="06fbe-136">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="06fbe-137">Avant la migration, vous devez réinitialiser les paramètres d’invitation dans votre version héritée du serveur de conversation de groupe Lync Server si vous voulez que des salles soient présentes dans une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="06fbe-137">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="06fbe-138">Dans le cas contraire, lors de la migration, Lync Server 2013 affiche des avertissements et définit les salles sur la valeur par défaut false.</span><span class="sxs-lookup"><span data-stu-id="06fbe-138">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="06fbe-139">Si vous avez utilisé des fichiers dans des salles de conversation, vous devez restaurer manuellement les fichiers dans le nouveau magasin de fichiers de conversation permanente après la migration.</span><span class="sxs-lookup"><span data-stu-id="06fbe-139">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="06fbe-140">Les outils ne le font pas.</span><span class="sxs-lookup"><span data-stu-id="06fbe-140">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="06fbe-141">Si vous aviez des utilisateurs fédérés et des salles avec des utilisateurs fédérés, sachez que le serveur de conversation permanente ne prend pas en charge la Fédération.</span><span class="sxs-lookup"><span data-stu-id="06fbe-141">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="06fbe-142">Les salles avec des utilisateurs fédérés seront migrées ; Toutefois, les utilisateurs eux-mêmes ne pourront pas accéder au contenu, car l’accès fédéré n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="06fbe-142">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="06fbe-143">Identifiez les salles que vous ne voulez pas migrer, et marquez-les comme désactivées.</span><span class="sxs-lookup"><span data-stu-id="06fbe-143">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="06fbe-p113">Spécifiez la date après laquelle vous voulez migrer le contenu des salles de conversation. Par exemple, vous pouvez exclure les messages antérieurs au 1er janvier 2010 de la migration, car ceux-ci sont obsolètes ou non appropriés pour la migration.</span><span class="sxs-lookup"><span data-stu-id="06fbe-p113">Identify the date beyond which you want to migrate the chat room content. For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="06fbe-146">Exécution de la migration</span><span class="sxs-lookup"><span data-stu-id="06fbe-146">Performing the Migration</span></span>

<span data-ttu-id="06fbe-147">Effectuez les étapes suivantes pour migrer votre serveur de conversation de groupe hérité.</span><span class="sxs-lookup"><span data-stu-id="06fbe-147">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="06fbe-148">Arrêtez les services Lync Server 2010, conversation de groupe, conversation de groupe Office Communications Server 2007 R2 ou Lync Server 2013, serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="06fbe-148">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="06fbe-149">Tous les services doivent être arrêtés, aussi, devez-vous planifier cette opération à un moment opportun.</span><span class="sxs-lookup"><span data-stu-id="06fbe-149">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="06fbe-150">Comme décrit précédemment, veillez à sauvegarder votre base de données de conversation de groupe actuelle.</span><span class="sxs-lookup"><span data-stu-id="06fbe-150">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="06fbe-151">Exécutez la cmdlet Windows PowerShell **Export-applet cspersistentchatdata** en tant que membre du rôle RBAC de l’administrateur de conversation permanente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="06fbe-151">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="06fbe-152">Pour plus d’informations sur les applets de commande d’exportation/importation, voir [Troubleshooting persistent Chat Server Configuration Using Windows PowerShell Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="06fbe-152">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="06fbe-153">Inspectez le contenu exporté.</span><span class="sxs-lookup"><span data-stu-id="06fbe-153">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="06fbe-154">Avant d’être prêt à importer, arrêtez Lync Server 2013 et les services de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="06fbe-154">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="06fbe-155">Tous les services doivent être arrêtés, aussi, devez-vous planifier cette opération à un moment opportun.</span><span class="sxs-lookup"><span data-stu-id="06fbe-155">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="06fbe-156">Effectuez une sauvegarde de la base de données de conversation permanente si vous avez créé des catégories, des salles ou des compléments dans votre déploiement Lync Server 2013 avant la migration.</span><span class="sxs-lookup"><span data-stu-id="06fbe-156">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="06fbe-157">Le processus d’exportation/importation sera en mesure de fusionner les données héritées dans le déploiement Lync Server 2013, mais vous souhaiterez sauvegarder la base de données si le contenu est remplacé par inadvertance (par exemple, en cas de conflits d’affectation de noms).</span><span class="sxs-lookup"><span data-stu-id="06fbe-157">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="06fbe-158">Exécutez l’applet de commande **Import-applet cspersistentchatdata** Windows PowerShell (outil d’importation), avec une commande **WhatIf** pour remplir le serveur principal du pool de serveurs de conversation permanente avec les données migrées.</span><span class="sxs-lookup"><span data-stu-id="06fbe-158">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="06fbe-159">Certaines conversions surviennent dans le processus pour prendre en charge le modèle d’administration simplifié.</span><span class="sxs-lookup"><span data-stu-id="06fbe-159">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="06fbe-160">Corrigez les erreurs et avertissements qui apparaissent.</span><span class="sxs-lookup"><span data-stu-id="06fbe-160">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="06fbe-161">Exécutez la cmdlet Windows PowerShell **Import-applet cspersistentchatdata** du serveur de conversation permanente en tant que membre du rôle RBAC de l’administrateur de conversation permanente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="06fbe-161">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="06fbe-162">Pour plus d’informations sur les applets de commande d’exportation/importation, voir [Troubleshooting persistent Chat Server Configuration Using Windows PowerShell Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="06fbe-162">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="06fbe-163">Vous devez XCOPY tous les fichiers téléchargés (tout le dossier) vers le nouveau magasin de fichiers de conversation permanente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06fbe-163">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="06fbe-164">Le Lync 2013 (client) ne prend pas en charge le téléchargement ou l’affichage de fichiers dans les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="06fbe-164">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="06fbe-165">Vous pouvez toujours utiliser le client hérité pour publier et afficher les fichiers dans la salle.</span><span class="sxs-lookup"><span data-stu-id="06fbe-165">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="06fbe-166">Transférez l’URI du serveur de recherche de conversation de groupe Lync Server 2010, Group chat ou Office Communications Server 2007 R2 vers l’objet contact de serveur de conversation permanente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06fbe-166">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="06fbe-167">Les étapes suivantes sont requises si votre client Lync 2010 Group chat ou Office Communicator 2007 R2 Group chat doit se connecter à la dernière version de Lync 2013, persistent chat (client) après la migration sans modification de configuration côté client :</span><span class="sxs-lookup"><span data-stu-id="06fbe-167">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="06fbe-168">Supprimez le \<domainName\> compte d’utilisateur du serveur de recherche OCSChat@. com.</span><span class="sxs-lookup"><span data-stu-id="06fbe-168">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="06fbe-169">Il a été utilisé pour pointer vers le service de recherche dans Lync Server 2010, Group chat.</span><span class="sxs-lookup"><span data-stu-id="06fbe-169">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="06fbe-170">Vous pouvez désinstaller le pool et supprimer les entrées approuvées plus tard.</span><span class="sxs-lookup"><span data-stu-id="06fbe-170">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="06fbe-171">Créez un point de terminaison hérité (objet contact de serveur de conversation permanente) en exécutant l’applet de commande Windows PowerShell, **New-CsPersistentChatEndpoint**, avec l’URI SIP identique afin que le client hérité fonctionne correctement lors du redémarrage du service.</span><span class="sxs-lookup"><span data-stu-id="06fbe-171">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="06fbe-172">Le processus de migration obligatoire est terminé à ce point.</span><span class="sxs-lookup"><span data-stu-id="06fbe-172">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="06fbe-173">Lync 2010 Group chat (clients) ou Office Communicator 2007 R2 Group chat (clients) peuvent se connecter au nouveau pool de serveurs de conversation permanente maintenant, de façon transparente.</span><span class="sxs-lookup"><span data-stu-id="06fbe-173">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="06fbe-174">Suivez ces étapes de désaffectation supplémentaires pour Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat.</span><span class="sxs-lookup"><span data-stu-id="06fbe-174">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="06fbe-175">Démarrez les services du serveur de conversation permanente en activant tous les ordinateurs dans le nouveau pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="06fbe-175">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="06fbe-176">Utilisez le panneau de configuration Lync Server et les applets de commande Windows PowerShell pour vérifier que les données ont été correctement migrées.</span><span class="sxs-lookup"><span data-stu-id="06fbe-176">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="06fbe-177">Désinstallez Lync 2010 Group chat ou Office Communicator 2007 R2 Group chat des ordinateurs du pool de serveurs de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="06fbe-177">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="06fbe-178">Supprimez l’application approuvée et le pool d’applications approuvées à l’aide des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06fbe-178">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="06fbe-179">Ces éléments sont supprimés du magasin central de gestion et des entrées de service approuvé associées (est) à partir d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06fbe-179">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="06fbe-180">Cette étape peut également être utilisée à l’aide du générateur de topologie (les pools et les applications approuvées ont un nœud dédié, également).</span><span class="sxs-lookup"><span data-stu-id="06fbe-180">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="06fbe-181">Vous pouvez maintenant commencer à activer la fonctionnalité de serveur de conversation permanente via les nouveaux clients.</span><span class="sxs-lookup"><span data-stu-id="06fbe-181">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="06fbe-182">Pour plus d’informations sur l’activation du serveur de conversation permanente, voir [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="06fbe-182">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="06fbe-183">Lync Server 2013 prend en charge plusieurs pools de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="06fbe-183">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="06fbe-184">Toutefois, nous prenons en charge la migration d’un pool Lync 2010 Group chat ou Office Communications Server 2007 R2 &nbsp; Group chat vers un pool de serveurs de conversation permanente et Lync server 2013.</span><span class="sxs-lookup"><span data-stu-id="06fbe-184">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="06fbe-185">Vous pouvez ajouter des pools de serveurs de conversation permanente dans votre déploiement pour répondre aux besoins de réglementation (par exemple, conserver des données au sein d’une géographie donnée).</span><span class="sxs-lookup"><span data-stu-id="06fbe-185">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

