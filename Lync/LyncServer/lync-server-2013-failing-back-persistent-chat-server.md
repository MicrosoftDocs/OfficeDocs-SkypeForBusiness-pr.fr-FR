---
title: 'Lync Server 2013 : restauration d’un serveur de conversation permanente'
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
ms.openlocfilehash: 6847f4002204c270b5978df2cab2851eeb912b20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="9f4ee-102">Restauration d’un serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f4ee-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f4ee-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="9f4ee-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="9f4ee-104">Cette procédure décrit les étapes nécessaires pour effectuer une récupération suite à une défaillance du serveur de conversation permanente, ainsi que pour rétablir les opérations à partir du centre de données principal.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="9f4ee-105">Lors d’une défaillance du serveur de conversation permanente, le centre de données principal subit une panne totale, et les bases de données principale et miroir deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="9f4ee-106">Le centre de données principal bascule vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="9f4ee-107">La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="9f4ee-108">La procédure suppose que le centre de données principal ait été récupéré après une panne totale et que la base de données MGC et la base de données mgccomp ont été recréées et réinstallées à l’aide du générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="9f4ee-109">La procédure suppose également qu’aucun nouveau serveur de miroir et de sauvegarde n’ait été déployé pendant la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, comme défini dans basculement du [serveur de conversation permanente dans Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="9f4ee-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="9f4ee-110">Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="9f4ee-111">Pour restaurer un serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="9f4ee-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="9f4ee-112">Effacez tous les serveurs de la liste serveur de conversation permanente Active Server `Set-CsPersistentChatActiveServer` à l’aide de l’applet de commande de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="9f4ee-113">Cela empêche tous les serveurs de conversation permanente de se connecter à la base de données MGC et à la base de données mgccomp pendant la restauration automatique.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9f4ee-114">L’agent SQL Server sur le serveur principal de serveur de conversation permanente secondaire doit être en cours d’exécution sous un compte privilégié.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="9f4ee-115">Plus précisément, le compte doit disposer des droits suivants :</span><span class="sxs-lookup"><span data-stu-id="9f4ee-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="9f4ee-116">Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</span><span class="sxs-lookup"><span data-stu-id="9f4ee-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9f4ee-117">Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</span><span class="sxs-lookup"><span data-stu-id="9f4ee-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="9f4ee-118">Désactivez la mise en miroir sur la base de données mgc de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="9f4ee-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="9f4ee-119">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de MGC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="9f4ee-120">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="9f4ee-121">Cliquez sur **Supprimer la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="9f4ee-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="9f4ee-123">Procédez de la même façon avec la base de données mgccomp.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="9f4ee-124">Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :</span><span class="sxs-lookup"><span data-stu-id="9f4ee-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="9f4ee-125">À l’aide de SQL Server Management Studio, connectez-vous à l’instance de MGC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="9f4ee-p105">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="9f4ee-128">Dans **Type de sauvegarde**, sélectionnez **Complète**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="9f4ee-129">Pour **Composant de sauvegarde**, cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="9f4ee-130">Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="9f4ee-131">\* \<Facultatif\> \* Dans **Description**, entrez une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="9f4ee-132">Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="9f4ee-p106">Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="9f4ee-135">Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="9f4ee-136">Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="9f4ee-137">À l’aide de SQL Server Management Studio, connectez-vous à l’instance MGC principale.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="9f4ee-p107">Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="9f4ee-140">Sélectionnez **À partir du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="9f4ee-p108">Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="9f4ee-144">Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="9f4ee-145">Dans le volet **Sélectionner une page**, cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="9f4ee-146">Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="9f4ee-147">Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="9f4ee-148">Cliquez sur **OK** pour lancer le processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="9f4ee-149">Configurez la copie des journaux de transaction SQL Server pour la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="9f4ee-150">Suivez les procédures décrites dans [configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) pour établir la copie des journaux de transaction pour la base de données MGC principale.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="9f4ee-151">Définissez les serveurs actifs du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="9f4ee-152">À partir de Lync Server Management Shell, utilisez l’applet de commande **Set-applet cspersistentchatactiveserver** pour définir la liste des serveurs actifs.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9f4ee-153">Tous les serveurs actifs doivent être situés dans le même centre de données que celui de la nouvelle base de données principale, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.</span><span class="sxs-lookup"><span data-stu-id="9f4ee-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="9f4ee-154">La restauration du pool à son état normal exécute la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="9f4ee-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="9f4ee-155">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) .</span><span class="sxs-lookup"><span data-stu-id="9f4ee-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

