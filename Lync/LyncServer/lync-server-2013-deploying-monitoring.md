---
title: 'Lync Server 2013 : déploiement de la surveillance'
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
ms.openlocfilehash: 49d62537f91145803f60f51c18b86816a0af657f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="1219f-102">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1219f-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1219f-103">_**Dernière modification de la rubrique :** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="1219f-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="1219f-104">Des modifications majeures ont été apportées à l’infrastructure de surveillance de Microsoft Lync Server 2013, en commençant par le fait que le rôle serveur de surveillance a été déconseillé.</span><span class="sxs-lookup"><span data-stu-id="1219f-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="1219f-105">À la place des rôles Serveur de surveillance distincts (qui nécessitaient généralement que les organisations configurent des ordinateurs dédiés agissant comme serveurs de surveillance), les services de surveillance sont maintenant colocalisés sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1219f-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="1219f-106">Cette modification permet, entre autres, d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1219f-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="1219f-107">Réduisez le nombre de rôles serveur requis lors de l’implémentation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1219f-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="1219f-108">Dans ce cas, la réduction du nombre de rôles serveur Serveur de surveillance permet également de diminuer les coûts en rendant inutile la gestion de serveurs dédiés à la surveillance ;</span><span class="sxs-lookup"><span data-stu-id="1219f-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="1219f-109">Réduisez la complexité de l’installation et de l’administration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1219f-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="1219f-110">En colocalisant automatiquement les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer ni de gérer le rôle Serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1219f-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1219f-111">Le rôle de serveur d’archivage a également été déconseillé dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1219f-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="1219f-112">À l’instar des services de surveillance, les services d’archivage Lync Server 2013 sont colocalisés sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1219f-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="1219f-113">Il est important de le noter, car la surveillance et l’archivage partagent souvent la même instance de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1219f-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="1219f-114">Comme vous pouvez vous y attendre, ces modifications ont un impact majeur sur l’installation et la gestion des services de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1219f-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="1219f-115">Par exemple, étant donné que le rôle serveur de surveillance n’existe plus, le nœud du serveur de surveillance a été supprimé du générateur de topologie Lync Server ; Cela signifie que vous ne pouvez plus utiliser l’Assistant Nouveau serveur de surveillance du générateur de topologie pour ajouter un nouveau serveur de surveillance à votre topologie.</span><span class="sxs-lookup"><span data-stu-id="1219f-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="1219f-116">(Cet Assistant n’existe plus.) Au lieu de cela, vous implémenterez généralement des services de surveillance dans votre topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="1219f-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="1219f-117">Activation de l’analyse en même temps vous configurez un nouveau pool Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1219f-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="1219f-118">(Dans Lync Server 2013, la surveillance est activée ou désactivée sur un pool par pool.) Notez que vous pouvez activer la surveillance pour un pool sans collecter réellement les données de surveillance, un processus expliqué dans la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de cette documentation.</span><span class="sxs-lookup"><span data-stu-id="1219f-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="1219f-p107">Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.</span><span class="sxs-lookup"><span data-stu-id="1219f-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="1219f-p108">Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. N’oubliez pas que même si le rôle Serveur de surveillance n’existe plus, vous devez toujours créer un ou plusieurs magasins d’analyse : des bases de données principales utilisées pour stocker les données collectées par le service de surveillance. Ces bases de données principales peuvent être créées avec Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="1219f-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1219f-127">Si la surveillance a été activée pour un pool, vous pouvez désactiver le processus de collecte des données de surveillance sans avoir à modifier votre topologie : Lync Server Management Shell vous permet de désactiver (puis réactiver ultérieurement) l’enregistrement des détails des appels (CDR) ou la qualité collecte de données de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="1219f-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="1219f-128">Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.</span><span class="sxs-lookup"><span data-stu-id="1219f-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="1219f-129">Une autre amélioration importante de la surveillance dans Lync Server 2013 est le fait que les rapports de surveillance de Lync Server prennent désormais en charge IPv6 : les rapports qui utilisent le champ adresse IP affichent des adresses IPv4 ou IPv6 en fonction de : 1) requête SQL utilisée ; et, 2) où l’adresse IPv6 est stockée dans la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1219f-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1219f-130">Assurez-vous que le type de démarrage du service de l’agent SQL Server est automatique et que le service de l’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, afin que les travaux de maintenance SQL Server par défaut puissent s’exécuter sur leur base planifiée. sous le contrôle du service SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="1219f-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="1219f-131">Cette documentation vous guide tout au long du processus d’installation et de configuration des rapports de surveillance et de surveillance pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1219f-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="1219f-132">La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1219f-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="1219f-133">activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;</span><span class="sxs-lookup"><span data-stu-id="1219f-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="1219f-134">Installez SQL Server Reporting Services et les rapports de surveillance Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1219f-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="1219f-135">Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;</span><span class="sxs-lookup"><span data-stu-id="1219f-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="1219f-136">configurer la collecte des données de l’enregistrement des détails des appels ou de la qualité de l’expérience (QoE) de données.</span><span class="sxs-lookup"><span data-stu-id="1219f-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="1219f-137">L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités de Lync Server, telles que les appels téléphoniques VoIP (Voice over IP); messagerie instantanée (IM); transferts de fichiers ; conférence audio/vidéo (A/V); et les sessions de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="1219f-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="1219f-138">Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;</span><span class="sxs-lookup"><span data-stu-id="1219f-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="1219f-139">vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1219f-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

