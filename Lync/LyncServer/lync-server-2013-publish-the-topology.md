---
title: 'Lync Server 2013 : Publication de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="b1c5d-102">Publication de la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1c5d-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1c5d-103">_**Dernière modification de la rubrique :** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="b1c5d-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="b1c5d-104">Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="b1c5d-105">Il est également possible de déléguer les autorisations et les droits d’administrateur appropriés.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="b1c5d-106">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b1c5d-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="b1c5d-107">Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="b1c5d-108">Après avoir défini votre topologie dans le générateur de topologie, vous devez publier la topologie dans le centre de gestion central.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="b1c5d-109">Le centre de gestion central fournit un stockage fiable schematized des données nécessaires pour définir, configurer, gérer, gérer, décrire et utiliser un déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="b1c5d-110">Il valide également les données afin de garantir la cohérence de la configuration.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="b1c5d-111">Toutes les modifications apportées aux données de configuration ont lieu dans le magasin central de gestion, ce qui élimine les problèmes de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="b1c5d-112">Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie, y compris les serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1c5d-113">SQL Server a besoin d’un minimum de 20 Go d’espace disque libre pour la publication de la topologie initiale et la création du serveur de gestion central.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b1c5d-114">Pour Enterprise Edition uniquement : pour publier la topologie, le serveur principal SQL Server doit être connecté et accessible avec des exceptions de pare-feu.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="b1c5d-115">Pour plus d’informations sur la spécification des exceptions de pare-feu, voir <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Présentation de la configuration requise pour le pare-feu pour SQL Server avec Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="b1c5d-116">Pour plus d’informations sur la configuration de SQL Server, voir <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurer SQL Server pour Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="b1c5d-117">Pour publier une topologie</span><span class="sxs-lookup"><span data-stu-id="b1c5d-117">To publish a topology</span></span>

1.  <span data-ttu-id="b1c5d-118">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b1c5d-119">Sélectionnez cette option pour ouvrir la topologie à partir d’un fichier local.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="b1c5d-120">Si vous utilisez l’ordinateur sur lequel vous avez défini la topologie, il se trouve à l’emplacement où vous l’avez enregistrée aux étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="b1c5d-121">En règle générale, il s’agit du dossier Documents de l’utilisateur qui a configuré la topologie.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="b1c5d-122">Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="b1c5d-123">Dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="b1c5d-124">Dans la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez publier.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b1c5d-125">Si vous ne disposez pas des droits appropriés pour créer les bases de données, vous pouvez désactiver les cases à cocher en regard de celles-ci et demander à une personne dotée des droits appropriées de les créer plus tard.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="b1c5d-126">Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="b1c5d-127">Vous pouvez cliquer sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="b1c5d-128">Les options de placement des fichiers de données avancées SQL Server vous permettent de sélectionner les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b1c5d-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="b1c5d-129">**Déterminez automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur SQL Server en répartissant les fichiers journaux et de données vers le meilleur emplacement.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="b1c5d-p107">**Utiliser les valeurs par défaut de l’instance SQL Server** : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="b1c5d-133">Cliquez sur **OK**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="b1c5d-134">Dans la page **Sélectionner le serveur de gestion centrale** , sélectionnez un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="b1c5d-135">Vous pouvez cliquer sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="b1c5d-136">Les options de placement des fichiers de données avancées SQL Server vous permettent de sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b1c5d-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="b1c5d-137">**Déterminez automatiquement l’emplacement du fichier de base de données** : cette option détermine les meilleures performances opérationnelles en fonction de la configuration du disque sur votre serveur SQL Server en répartissant les fichiers journaux et de données vers le meilleur emplacement.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="b1c5d-p109">**Utiliser les valeurs par défaut de l’instance SQL Server** : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="b1c5d-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-141">Click **OK**.</span></span>

9.  <span data-ttu-id="b1c5d-142">Cliquez sur **Suivant** pour terminer le processus de publication.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="b1c5d-143">Lorsque le processus de publication est terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="b1c5d-144">Lorsque la topologie a été correctement publiée, vous pouvez commencer à installer une réplique locale du magasin de gestion central sur chaque serveur exécutant Lync Server 2013 dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="b1c5d-145">Il est recommandé de commencer par le premier pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b1c5d-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1c5d-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1c5d-146">See Also</span></span>


[<span data-ttu-id="b1c5d-147">Configuration des serveurs et des pools frontaux pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1c5d-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

