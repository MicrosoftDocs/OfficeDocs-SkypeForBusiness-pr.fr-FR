---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour le serveur de conversation permanente'
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
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="9c1f0-102">Liste de vérification du déploiement pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c1f0-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c1f0-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="9c1f0-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="9c1f0-104">Le déploiement de Lync Server 2013, de chat permanent serveur nécessite que vous le déployiez dans l’ordre approprié et que vous ayez effectué toutes les étapes de déploiement requises.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="9c1f0-105">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="9c1f0-105">Deployment Sequence</span></span>

<span data-ttu-id="9c1f0-106">Vous pouvez déployer le serveur de chat permanent après le déploiement de votre topologie initiale, y compris au moins un serveur Lync Server 2013, un pool frontal ou un serveur Lync Server 2013, Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="9c1f0-107">Cette rubrique décrit la procédure de déploiement d’un serveur de chat permanent en l’ajoutant à un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="9c1f0-108">Processus de déploiement</span><span class="sxs-lookup"><span data-stu-id="9c1f0-108">Deployment Process</span></span>

<span data-ttu-id="9c1f0-109">Le tableau suivant répertorie les étapes de base de déploiement d’un serveur de conversation permanent et fournit des liens pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="9c1f0-110">Processus de déploiement d’un serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="9c1f0-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c1f0-111">Tâche</span><span class="sxs-lookup"><span data-stu-id="9c1f0-111">Task</span></span></th>
<th><span data-ttu-id="9c1f0-112">Étapes</span><span class="sxs-lookup"><span data-stu-id="9c1f0-112">Steps</span></span></th>
<th><span data-ttu-id="9c1f0-113">Rôles et appartenance aux groupes nécessaires</span><span class="sxs-lookup"><span data-stu-id="9c1f0-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="9c1f0-114">Rubriques associées</span><span class="sxs-lookup"><span data-stu-id="9c1f0-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c1f0-115"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="9c1f0-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="9c1f0-116">Sur le matériel conforme à la configuration système requise, installez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="9c1f0-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c1f0-117">Sur les serveurs front-end serveur Chat permanent :</span><span class="sxs-lookup"><span data-stu-id="9c1f0-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="9c1f0-118">Un système d’exploitation conforme à la configuration système requise</span><span class="sxs-lookup"><span data-stu-id="9c1f0-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-119">Configuration logicielle requise pour les ordinateurs exécutant Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c1f0-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-120">Serveur SQL Server sur le serveur qui héberge la base de données de serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="9c1f0-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="9c1f0-121">Si la conformité du serveur Chat permanent est requise :</span><span class="sxs-lookup"><span data-stu-id="9c1f0-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c1f0-122">Serveur SQL Server sur le serveur qui héberge la base de données de compatibilité serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="9c1f0-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c1f0-123">Un utilisateur membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="9c1f0-124"><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="9c1f0-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="9c1f0-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Support du logiciel serveur et de l’infrastructure dans Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="9c1f0-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="9c1f0-126"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9c1f0-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="9c1f0-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Configuration requise pour le serveur de chat permanent dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9c1f0-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c1f0-128"><strong>Créer la topologie interne appropriée pour prendre en charge le serveur de chat permanent (et éventuellement la conformité avec la conversation permanente)</strong></span><span class="sxs-lookup"><span data-stu-id="9c1f0-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="9c1f0-129">Exécutez le générateur de topologie pour ajouter un pool de serveurs de chat permanent à votre topologie :</span><span class="sxs-lookup"><span data-stu-id="9c1f0-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c1f0-130">Ajouter des composants serveur de chat permanent à la topologie</span><span class="sxs-lookup"><span data-stu-id="9c1f0-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-131">Créer une base de données SQL Server pour le magasin serveur Chat permanent (et un serveur SQL de sauvegarde pour la récupération d’urgence)</span><span class="sxs-lookup"><span data-stu-id="9c1f0-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-132">Définir un nouveau magasin de fichiers Lync ou utiliser un magasin de fichiers Lync existant pour les fichiers du serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="9c1f0-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-133">Associez le pool Lync Server 2013 qui peut acheminer les demandes vers ce pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="9c1f0-134">Si la conformité de conversation permanente est requise :</span><span class="sxs-lookup"><span data-stu-id="9c1f0-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c1f0-135">Ajouter un magasin de conformité des conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="9c1f0-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-136">Cliquez sur la case à cocher de la définition de pool de serveurs de conversation permanente pour activer la conformité</span><span class="sxs-lookup"><span data-stu-id="9c1f0-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-137">Publication de la topologie</span><span class="sxs-lookup"><span data-stu-id="9c1f0-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="9c1f0-138">Si vous installez le serveur Chat permanent sur l’édition standard, le nom de domaine complet (FQDN) du pool de serveurs de chat permanent doit correspondre au serveur Standard Edition Server, et les bases de données SQL Server sont colocalisées sur l’instance SQL Server Express sur le standard. Serveur édition</span><span class="sxs-lookup"><span data-stu-id="9c1f0-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="9c1f0-139">Pour définir une topologie, un compte membre du groupe Utilisateurs local</span><span class="sxs-lookup"><span data-stu-id="9c1f0-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="9c1f0-140">Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et l’utilisateur doit également disposer des autorisations de contrôle total (lecture/écriture/modification) sur le magasin de fichiers Lync pour les fichiers du serveur de chat permanent (de sorte que le générateur de topologie puisse configurer les DACL requis).</span><span class="sxs-lookup"><span data-stu-id="9c1f0-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="9c1f0-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur de chat permanent à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="9c1f0-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c1f0-142"><strong>Déployer un serveur de conversation permanente</strong></span><span class="sxs-lookup"><span data-stu-id="9c1f0-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="9c1f0-143">Exécutez le programme d’installation de Lync Server sur tous les ordinateurs exécutant la fonction de chat permanent serveur.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="9c1f0-144">La configuration du serveur de chat permanent est intégrée à l’Assistant Déploiement de Lync Server 2013, qui fournit les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c1f0-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c1f0-145">Déployer le magasin de gestion local</span><span class="sxs-lookup"><span data-stu-id="9c1f0-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-146">Installer les services serveur de chat permanent</span><span class="sxs-lookup"><span data-stu-id="9c1f0-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-147">Demander et affecter des certificats</span><span class="sxs-lookup"><span data-stu-id="9c1f0-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-148">Exécuter et démarrer les services</span><span class="sxs-lookup"><span data-stu-id="9c1f0-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c1f0-149">Un utilisateur membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="9c1f0-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Déploiement d’un serveur de chat permanent dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="9c1f0-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c1f0-151"><strong>Créer un administrateur de conversation permanente</strong></span><span class="sxs-lookup"><span data-stu-id="9c1f0-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="9c1f0-152">Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="9c1f0-153">Un utilisateur membre des administrateurs de domaines.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="9c1f0-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Ajouter un administrateur de chat permanent dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="9c1f0-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c1f0-155"><strong>Configuration du serveur de conversation permanente</strong></span><span class="sxs-lookup"><span data-stu-id="9c1f0-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="9c1f0-156">Configurez les utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="9c1f0-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="9c1f0-157">La stratégie doit être activée pour permettre à l’utilisateur d’accéder au serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="9c1f0-158">Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="9c1f0-159">Configurer les paramètres</span><span class="sxs-lookup"><span data-stu-id="9c1f0-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c1f0-p104">L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="9c1f0-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuration du serveur de chat permanent dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="9c1f0-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="9c1f0-163">Vous pouvez déployer un ou plusieurs pools de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="9c1f0-164">Nous prenons en charge plusieurs pools de serveurs de chat permanent pour des raisons réglementaires dans lesquelles les données générées dans une région donnée doivent rester dans cette région.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="9c1f0-165">Par exemple, si vous déployez un pool de serveurs de chat permanent à Chicago et un autre sur Zurich pour se conformer aux réglementations relatives aux données en Suisse, les utilisateurs peuvent se connecter aux salles dans les pools de serveurs de chat permanent, à condition qu’ils y aient accès.</span><span class="sxs-lookup"><span data-stu-id="9c1f0-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

