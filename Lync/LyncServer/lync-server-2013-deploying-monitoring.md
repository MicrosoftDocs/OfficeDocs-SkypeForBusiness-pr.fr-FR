---
title: 'Lync Server 2013 : déploiement d’une analyse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637897bce0a160a8cc3b199ec6aee3ffd7375852
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="ba035-102">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba035-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba035-103">_**Dernière modification de la rubrique :** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="ba035-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="ba035-104">Des modifications majeures ont été apportées à l’infrastructure de contrôle Microsoft Lync Server 2013, en commençant par le fait que le rôle du serveur de surveillance est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="ba035-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="ba035-105">Au lieu de surveiller les rôles de serveurs de surveillance individuels (en général, les organisations nécessaires pour configurer des ordinateurs dédiés comme serveurs d’analyse) sont désormais localisées sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="ba035-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="ba035-106">Vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba035-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="ba035-107">Réduisez le nombre de rôles de serveur requis lors de l’implémentation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba035-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="ba035-108">Dans ce cas, le fait de décrémenter le rôle serveur du serveur de surveillance permet également de réduire les coûts en éliminant la nécessité de conserver des serveurs dédiés à des fins de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ba035-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="ba035-109">Réduisez la complexité de la configuration et de l’administration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba035-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="ba035-110">Collocating automatiquement les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer et de gérer le rôle du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ba035-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba035-111">Le rôle du serveur d’archivage a également été déconseillé dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba035-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="ba035-112">Comme les services de surveillance, les services d’archivage de Lync Server 2013 sont désormais colocalisés sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="ba035-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="ba035-113">Il est important de noter qu’il est important de partager et d’archiver fréquemment la même instance de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba035-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="ba035-114">Comme vous le souhaitez, ces modifications ont un impact important sur la façon dont les services de surveillance sont installés et gérés.</span><span class="sxs-lookup"><span data-stu-id="ba035-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="ba035-115">Par exemple, dans la mesure où le rôle serveur de surveillance n’existe plus, le nœud du serveur de surveillance a été supprimé du générateur de topologie de Lync Server. en retour, cela signifie que vous n’utilisez plus l’Assistant Nouvelle analyse du serveur topologique pour ajouter un nouveau serveur de surveillance à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="ba035-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="ba035-116">(Cet Assistant n’existe plus.) Au lieu de cela, vous implémenterez généralement les services de surveillance dans votre topologie en effectuant les deux étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba035-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="ba035-117">Activation de l’analyse en même temps que vous configurez un nouveau pool de serveurs Lync.</span><span class="sxs-lookup"><span data-stu-id="ba035-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="ba035-118">(Dans Lync Server 2013, la surveillance est activée ou désactivée sur une base de pool par pool.) Notez que vous pouvez activer le contrôle pour un pool sans réellement collecter les données de surveillance, processus expliqué dans la section Configuration de l’enregistrement des détails des appels et de la qualité de l’enregistrement de cette documentation.</span><span class="sxs-lookup"><span data-stu-id="ba035-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="ba035-p107">Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.</span><span class="sxs-lookup"><span data-stu-id="ba035-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="ba035-123">Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance.</span><span class="sxs-lookup"><span data-stu-id="ba035-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="ba035-124">Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent.</span><span class="sxs-lookup"><span data-stu-id="ba035-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="ba035-125">Gardez à l’esprit que bien qu’il n’y ait plus de rôle serveur de surveillance, vous devrez tout de même créer un ou plusieurs magasins de surveillance : bases de données du serveur principal utilisées pour stocker les données collectées par le service de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ba035-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="ba035-126">Ces bases de données principales peuvent être créées à l’aide de Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="ba035-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba035-127">Si la surveillance a été activée pour un pool, vous pouvez désactiver le processus de collecte des données d’analyse sans avoir à modifier votre topologie : Lync Server Management Shell vous permet de désactiver (puis de réactiver ultérieurement) l’enregistrement des détails des appels (CDR) ou la qualité collecte de données de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ba035-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="ba035-128">Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.</span><span class="sxs-lookup"><span data-stu-id="ba035-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="ba035-129">Une autre amélioration importante apportée à l’analyse dans Lync Server 2013 est le fait que les rapports de surveillance de Lync Server prennent désormais en charge le protocole IPv6 : les rapports qui utilisent le champ IP address affichent des adresses IPv4 ou IPv6 en fonction de : 1) la requête SQL utilisée ; et 2) lorsque l’adresse IPv6 est stockée dans la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ba035-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba035-130">Assurez-vous que le type de démarrage du service d’agent SQL Server est Automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, de sorte que les tâches de maintenance de surveillance par défaut de SQL Server peuvent s’exécuter selon leur planification sous le contrôle du service d’agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba035-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="ba035-131">Cette documentation vous guide tout au long du processus d’installation et de configuration de rapports d’analyse et de surveillance de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba035-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="ba035-132">La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba035-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="ba035-133">activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;</span><span class="sxs-lookup"><span data-stu-id="ba035-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="ba035-134">Installez SQL Server Reporting Services et les rapports de surveillance de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba035-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="ba035-135">Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;</span><span class="sxs-lookup"><span data-stu-id="ba035-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="ba035-136">Configurez la collecte de données de l’enregistrement des détails des appels et de la qualité de l’appel.</span><span class="sxs-lookup"><span data-stu-id="ba035-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="ba035-137">L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités du serveur Lync telles que les appels téléphoniques VoIP (Voice over IP). messagerie instantanée ; transferts de fichiers ; conférences audio/vidéo (A/V); et des sessions de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="ba035-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="ba035-138">Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;</span><span class="sxs-lookup"><span data-stu-id="ba035-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="ba035-139">vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ba035-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

