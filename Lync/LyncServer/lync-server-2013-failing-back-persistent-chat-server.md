---
title: 'Lync Server 2013 : Restauration d’un serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca00a71c88b917b9e59f2e9039e7960b51f64157
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="8fea6-102">Restauration d’un serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fea6-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fea6-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="8fea6-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8fea6-104">Cette procédure décrit les étapes nécessaires à la récupération d’une défaillance du serveur de chat permanent et à la restauration d’opérations à partir du centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="8fea6-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="8fea6-105">Lors de l’échec du serveur Chat permanent, le centre de données principal est en panne, et les bases de données principales et miroirs deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="8fea6-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="8fea6-106">Le centre de données principal bascule vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8fea6-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="8fea6-107">La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits.</span><span class="sxs-lookup"><span data-stu-id="8fea6-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="8fea6-108">Cette procédure part du principe que le centre de données principal a été restauré à partir d’une panne totale et que la base de données MGC et la base de données mgccomp ont été recréées puis réinstallées à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8fea6-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="8fea6-109">Cette procédure part du principe qu’aucun nouveau serveur miroir et de sauvegarde n’a été déployé pendant la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, comme cela a été défini dans [échec du serveur de conversation permanent dans Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="8fea6-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="8fea6-110">Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8fea6-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="8fea6-111">Pour restaurer le serveur de conversation persistante</span><span class="sxs-lookup"><span data-stu-id="8fea6-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="8fea6-112">Effacez tous les serveurs de la liste de serveurs actifs de chat permanent `Set-CsPersistentChatActiveServer` du serveur à l’aide de l’applet de contrôle de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8fea6-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="8fea6-113">Cela a pour fin la connexion à la base de données MGC et de la base de données mgccomp lors du retour arrière.</span><span class="sxs-lookup"><span data-stu-id="8fea6-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8fea6-114">L’agent SQL Server sur le serveur principal de chat permanent du serveur principal doit être en cours d’exécution sous un compte privilégié.</span><span class="sxs-lookup"><span data-stu-id="8fea6-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="8fea6-115">Plus précisément, le compte doit disposer des droits suivants :</span><span class="sxs-lookup"><span data-stu-id="8fea6-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="8fea6-116">Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</span><span class="sxs-lookup"><span data-stu-id="8fea6-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="8fea6-117">Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</span><span class="sxs-lookup"><span data-stu-id="8fea6-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="8fea6-118">Désactivez la mise en miroir sur la base de données mgc de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="8fea6-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="8fea6-119">À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.</span><span class="sxs-lookup"><span data-stu-id="8fea6-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="8fea6-120">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="8fea6-121">Cliquez sur **Supprimer la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="8fea6-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="8fea6-123">Procédez de la même façon avec la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="8fea6-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="8fea6-124">Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :</span><span class="sxs-lookup"><span data-stu-id="8fea6-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="8fea6-125">À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.</span><span class="sxs-lookup"><span data-stu-id="8fea6-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="8fea6-p105">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8fea6-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="8fea6-128">Dans **Type de sauvegarde**, sélectionnez **Complète**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="8fea6-129">Pour **Composant de sauvegarde**, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="8fea6-130">Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8fea6-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="8fea6-131">\* \<Facultatif\> \* Dans **Description**, entrez une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8fea6-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="8fea6-132">Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.</span><span class="sxs-lookup"><span data-stu-id="8fea6-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="8fea6-p106">Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8fea6-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="8fea6-135">Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8fea6-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="8fea6-136">Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="8fea6-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="8fea6-137">À l’aide de SQL Server Management Studio, connectez-vous à l’instance MGC principale.</span><span class="sxs-lookup"><span data-stu-id="8fea6-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="8fea6-p107">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8fea6-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="8fea6-140">Sélectionnez **À partir du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="8fea6-p108">Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="8fea6-144">Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="8fea6-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="8fea6-145">Dans le volet **Sélectionner une page**, cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="8fea6-146">Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="8fea6-147">Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.</span><span class="sxs-lookup"><span data-stu-id="8fea6-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="8fea6-148">Cliquez sur **OK** pour lancer le processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="8fea6-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="8fea6-149">Configurer l’envoi du journal SQL Server pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="8fea6-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="8fea6-150">Suivez les procédures de [configuration du serveur de chat permanent pour une haute disponibilité et une reprise après sinistre dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) pour établir l’envoi de journaux pour la base de données MGC principale.</span><span class="sxs-lookup"><span data-stu-id="8fea6-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="8fea6-151">Définissez les serveurs actifs de chat permanent serveur.</span><span class="sxs-lookup"><span data-stu-id="8fea6-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="8fea6-152">À partir de Lync Server Management Shell, utilisez l’applet de contrôle **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="8fea6-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8fea6-153">Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="8fea6-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="8fea6-154">Lorsque le pool est restauré à son état normal, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="8fea6-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="8fea6-155">Pour plus d’informations, consultez la rubrique d’aide sur l’applet de [CsPersistentChatState Set-](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) .</span><span class="sxs-lookup"><span data-stu-id="8fea6-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

