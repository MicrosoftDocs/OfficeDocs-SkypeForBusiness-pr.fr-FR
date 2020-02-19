---
title: 'Lync Server 2013 : publication de la topologie mise à jour pour ajouter des bases de données d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f5d6e409682aaafd6e48966fa47797b870f90b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="65c40-102">Publication de la topologie mise à jour pour ajouter des bases de données d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65c40-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65c40-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="65c40-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="65c40-104">Après avoir mis à jour votre topologie dans le générateur de topologie, vous devez publier la topologie dans le magasin central de gestion avant de pouvoir configurer et utiliser l’archivage.</span><span class="sxs-lookup"><span data-stu-id="65c40-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="65c40-105">Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="65c40-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="65c40-106">Pour publier votre topologie mise à jour</span><span class="sxs-lookup"><span data-stu-id="65c40-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="65c40-107">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe utilisateurs local (ou d’un compte doté de droits d’utilisateur équivalents).</span><span class="sxs-lookup"><span data-stu-id="65c40-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c40-108">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour publier une topologie, qui est requise pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <STRONG>administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> et qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (de sorte que le générateur de topologies puisse configurer la liste de contrôle d’accès discrétionnaire requise ou un compte disposant de droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="65c40-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="65c40-109">Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="65c40-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="65c40-110">Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="65c40-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="65c40-111">Dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="65c40-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="65c40-112">Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="65c40-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="65c40-113">Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer.</span><span class="sxs-lookup"><span data-stu-id="65c40-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="65c40-114">Pour plus d’informations sur les droits et autorisations d’administrateur requis, reportez-vous à la rubrique <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="65c40-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="65c40-115">Seules les bases de données sur des serveurs SQL Server dédiés peuvent être installées à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="65c40-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="65c40-116">Les bases de données sur des serveurs SQL Server colocalisés avec d’autres composants serveur doivent être installées en exécutant le programme d’installation local sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="65c40-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="65c40-117">Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="65c40-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="65c40-118">Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu.</span><span class="sxs-lookup"><span data-stu-id="65c40-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="65c40-119">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-support-for-archiving.md">configuration de la prise en charge de l’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="65c40-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

