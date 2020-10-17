---
title: 'Lync Server 2013 : liste de vérification du déploiement pour le serveur de conversation permanente'
description: 'Lync Server 2013 : liste de vérification du déploiement pour le serveur de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d96da5e2961634e6a81450796e5d1ae3426819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568290"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f7039-103">Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7039-103">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7039-104">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f7039-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f7039-105">Le déploiement de Lync Server 2013, le serveur de conversation permanente nécessite que vous le déployiez dans l’ordre correct et que vous terminiez toutes les étapes de déploiement requises.</span><span class="sxs-lookup"><span data-stu-id="f7039-105">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="f7039-106">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="f7039-106">Deployment Sequence</span></span>

<span data-ttu-id="f7039-107">Vous pouvez déployer le serveur de conversation permanente après avoir déployé votre topologie initiale, notamment au moins un serveur Lync Server 2013, un pool frontal ou un serveur Lync Server 2013, Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f7039-107">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="f7039-108">Cette rubrique décrit comment déployer le serveur de conversation permanente en l’ajoutant à un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="f7039-108">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="f7039-109">Processus de déploiement</span><span class="sxs-lookup"><span data-stu-id="f7039-109">Deployment Process</span></span>

<span data-ttu-id="f7039-110">Le tableau suivant répertorie les étapes de base pour déployer le serveur de conversation permanente et fournit des liens pour obtenir plus de détails.</span><span class="sxs-lookup"><span data-stu-id="f7039-110">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="f7039-111">Processus de déploiement du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f7039-111">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7039-112">Tâche</span><span class="sxs-lookup"><span data-stu-id="f7039-112">Task</span></span></th>
<th><span data-ttu-id="f7039-113">Étapes</span><span class="sxs-lookup"><span data-stu-id="f7039-113">Steps</span></span></th>
<th><span data-ttu-id="f7039-114">Rôles et appartenance aux groupes nécessaires</span><span class="sxs-lookup"><span data-stu-id="f7039-114">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="f7039-115">Rubriques associées</span><span class="sxs-lookup"><span data-stu-id="f7039-115">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7039-116"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="f7039-116"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="f7039-117">Sur le matériel conforme à la configuration système requise, installez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f7039-117">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7039-118">Sur les serveurs frontaux du serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="f7039-118">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="f7039-119">Un système d’exploitation conforme à la configuration système requise</span><span class="sxs-lookup"><span data-stu-id="f7039-119">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="f7039-120">Conditions préalables logicielles pour les ordinateurs exécutant Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7039-120">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="f7039-121">SQL Server sur le serveur qui hébergera la base de données du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f7039-121">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="f7039-122">Si la conformité du serveur de conversation permanente est requise :</span><span class="sxs-lookup"><span data-stu-id="f7039-122">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7039-123">SQL Server sur le serveur qui hébergera la base de données de conformité du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f7039-123">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f7039-124">Un utilisateur membre du groupe Administrateurs local</span><span class="sxs-lookup"><span data-stu-id="f7039-124">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="f7039-125"><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="f7039-125"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="f7039-126"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="f7039-126"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="f7039-127"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f7039-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f7039-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f7039-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7039-129"><strong>Créer la topologie interne appropriée pour prendre en charge le serveur de conversation permanente (et éventuellement la conformité de la conversation permanente)</strong></span><span class="sxs-lookup"><span data-stu-id="f7039-129"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="f7039-130">Exécutez le générateur de topologie pour ajouter un pool de serveurs de conversation permanente à votre topologie :</span><span class="sxs-lookup"><span data-stu-id="f7039-130">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7039-131">Ajouter des composants de serveur de conversation permanente à la topologie</span><span class="sxs-lookup"><span data-stu-id="f7039-131">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="f7039-132">Créer une base de données SQL Server pour le magasin de serveurs de conversation permanente (et un serveur SQL Server de sauvegarde pour la récupération d’urgence)</span><span class="sxs-lookup"><span data-stu-id="f7039-132">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="f7039-133">Définir un nouveau magasin de fichiers Lync ou utiliser un magasin de fichiers Lync existant pour les fichiers du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f7039-133">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="f7039-134">Associer le pool Lync Server 2013 qui peut acheminer les demandes à ce pool de serveurs de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f7039-134">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="f7039-135">Si la conformité de la conversation permanente est requise :</span><span class="sxs-lookup"><span data-stu-id="f7039-135">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7039-136">Ajouter un magasin de conformité de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f7039-136">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="f7039-137">Cliquez sur la case à cocher définition de pool de serveurs de conversation permanente pour activer la conformité.</span><span class="sxs-lookup"><span data-stu-id="f7039-137">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="f7039-138">Publier la topologie</span><span class="sxs-lookup"><span data-stu-id="f7039-138">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="f7039-139">Si vous installez le serveur de conversation permanente sur Standard Edition, le nom de domaine complet (FQDN) du pool de serveurs de conversation permanente doit correspondre au serveur Standard Edition et les bases de données SQL Server sont colocalisées sur l’instance SQL Server Express sur le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="f7039-139">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="f7039-140">Pour définir une topologie, un compte membre du groupe Utilisateurs local</span><span class="sxs-lookup"><span data-stu-id="f7039-140">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="f7039-141">Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins, ainsi que l’utilisateur doivent également disposer d’autorisations de contrôle complètes (lecture/écriture/modification) sur le magasin de fichiers Lync pour les fichiers du serveur de conversation permanente (afin que le générateur de topologie puisse configurer les DACL requises).</span><span class="sxs-lookup"><span data-stu-id="f7039-141">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="f7039-142"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="f7039-142"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7039-143"><strong>Déployer un serveur de conversation permanente</strong></span><span class="sxs-lookup"><span data-stu-id="f7039-143"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="f7039-144">Exécutez le programme d’installation de Lync Server sur tous les ordinateurs exécutant le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="f7039-144">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="f7039-145">Le programme d’installation du serveur de conversation permanente est intégré à l’Assistant Déploiement de Lync Server 2013, qui fournit les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7039-145">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7039-146">Déployer le magasin de gestion local</span><span class="sxs-lookup"><span data-stu-id="f7039-146">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="f7039-147">Installer les services de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f7039-147">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="f7039-148">Demander et assigner des certificats</span><span class="sxs-lookup"><span data-stu-id="f7039-148">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="f7039-149">Exécuter et démarrer les services</span><span class="sxs-lookup"><span data-stu-id="f7039-149">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f7039-150">Un utilisateur membre du groupe Administrateurs local</span><span class="sxs-lookup"><span data-stu-id="f7039-150">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="f7039-151"><a href="lync-server-2013-deploying-persistent-chat-server.md">Déploiement du serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="f7039-151"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7039-152"><strong>Créer un administrateur de conversation permanente</strong></span><span class="sxs-lookup"><span data-stu-id="f7039-152"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="f7039-153">Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f7039-153">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="f7039-154">Un utilisateur membre des administrateurs de domaines.</span><span class="sxs-lookup"><span data-stu-id="f7039-154">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="f7039-155"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Ajout d’un administrateur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="f7039-155"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7039-156"><strong>Configuration du serveur de conversation permanente</strong></span><span class="sxs-lookup"><span data-stu-id="f7039-156"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="f7039-157">Configurez les utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="f7039-157">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7039-158">La stratégie d’accès à un serveur de conversation permanente doit être activée pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f7039-158">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="f7039-159">Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f7039-159">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="f7039-160">Configurer les paramètres</span><span class="sxs-lookup"><span data-stu-id="f7039-160">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f7039-p104">L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f7039-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="f7039-163"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuration du serveur de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="f7039-163"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="f7039-164">Vous pouvez déployer un ou plusieurs pools de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="f7039-164">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="f7039-165">Nous prenons en charge plusieurs pools de serveurs de conversation permanente pour des raisons réglementaires selon lesquelles les données générées dans une région donnée doivent rester dans cette région.</span><span class="sxs-lookup"><span data-stu-id="f7039-165">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="f7039-166">Par exemple, si vous déployez un pool de serveurs de conversation permanente à Chicago et un autre à Zurich pour vous conformer aux réglementations relatives aux données en Suisse, les utilisateurs peuvent se connecter à des salles dans les pools de serveurs de conversation permanente, à condition qu’ils disposent d’un accès.</span><span class="sxs-lookup"><span data-stu-id="f7039-166">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

