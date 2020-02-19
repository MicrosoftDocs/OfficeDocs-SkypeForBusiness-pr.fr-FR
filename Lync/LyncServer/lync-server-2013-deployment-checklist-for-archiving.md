---
title: 'Lync Server 2013 : liste de vérification du déploiement pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f7c8184862993500d09819de912bccf4310aa73
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="0d294-102">Liste de vérification du déploiement pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d294-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d294-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0d294-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0d294-104">L’archivage est automatiquement installé sur chaque serveur frontal de votre déploiement Lync Server 2013, mais vous devez toujours le configurer pour pouvoir l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="0d294-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="0d294-105">Les étapes de configuration requises, comme indiqué dans cette section, constituent le déploiement de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="0d294-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="0d294-106">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="0d294-106">Deployment Sequence</span></span>

<span data-ttu-id="0d294-107">La manière de configurer l’archivage dépend de l’option de stockage choisie :</span><span class="sxs-lookup"><span data-stu-id="0d294-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="0d294-108">Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer les stratégies d’archivage Lync Server 2013 pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0d294-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="0d294-109">Au lieu de cela, configurez vos stratégies de conservation inaltérable Exchange pour prendre en charge l’archivage pour les utilisateurs hébergés sur Exchange 2013, avec leurs boîtes aux lettres placées en conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="0d294-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0d294-110">Pour plus d’informations sur la configuration de ces stratégies, voir la documentation du produit Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0d294-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="0d294-111">Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez ajouter les bases de données d’archivage Lync Server (bases de données SQL Server) à votre topologie, puis la publier, ainsi que configurer des stratégies et des paramètres pour vos utilisateurs, avant de pouvoir archivez les données de ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0d294-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="0d294-112">Vous pouvez déployer les bases de données d’archivage en même temps que la topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0d294-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="0d294-113">Ce document indique la marche à suivre pour déployer des bases de données d’archivage en les ajoutant à un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="0d294-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="0d294-p104">Si vous activez l’archivage sur un pool frontal ou un serveur Standard Edition, vous devez l’activer pour tous les pools frontaux et serveurs Standard Edition dans le déploiement. Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée. Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.</span><span class="sxs-lookup"><span data-stu-id="0d294-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d294-118">Si l’archivage est essentiel au sein de votre organisation pour des raisons de conformité, veillez à déployer l’archivage, à configurer les stratégies et les autres options au niveau approprié, et à l’activer pour tous les utilisateurs appropriés, avant d’activer ces utilisateurs pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d294-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="0d294-119">Processus de déploiement de l’archivage</span><span class="sxs-lookup"><span data-stu-id="0d294-119">Archiving Deployment Process</span></span>

<span data-ttu-id="0d294-120">Le tableau suivant décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.</span><span class="sxs-lookup"><span data-stu-id="0d294-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d294-121">Phase</span><span class="sxs-lookup"><span data-stu-id="0d294-121">Phase</span></span></th>
<th><span data-ttu-id="0d294-122">Étapes</span><span class="sxs-lookup"><span data-stu-id="0d294-122">Steps</span></span></th>
<th><span data-ttu-id="0d294-123">Rôles et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="0d294-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="0d294-124">Documentation</span><span class="sxs-lookup"><span data-stu-id="0d294-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d294-125"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="0d294-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0d294-126">Pour utiliser l’intégration de Microsoft Exchange (à l’aide d’Exchange 2013 pour l’archivage de stockage pour tout ou partie des utilisateurs), vous avez besoin d’un déploiement Exchange 2013 existant.</span><span class="sxs-lookup"><span data-stu-id="0d294-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="0d294-127">Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour le stockage d’archives d’une partie ou de la totalité des utilisateurs, vous avez besoin de SQL Server sur le serveur qui va stocker les données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="0d294-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="0d294-p105">L’archivage s’exécute sur les serveurs frontaux d’un pool Enterprise et des serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="0d294-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="0d294-130">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="0d294-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="0d294-131"><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0d294-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="0d294-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure de serveur dans Lync Server 2013</a> dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0d294-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="0d294-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0d294-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="0d294-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configuration des systèmes et de l’infrastructure pour l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0d294-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="0d294-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013</a> dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0d294-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d294-136"><strong>Créez la topologie interne appropriée pour prendre en charge l’archivage (uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement).</strong></span><span class="sxs-lookup"><span data-stu-id="0d294-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="0d294-137">Exécutez le générateur de topologie pour ajouter des bases de données d’archivage Lync Server 2013 (bases de données SQL Server) à la topologie, puis publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="0d294-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="0d294-138">Pour définir une topologie afin qu’elle intègre des bases de données d’archivage, un compte membre du groupe Utilisateurs local est requis.</span><span class="sxs-lookup"><span data-stu-id="0d294-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="0d294-139">Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Lync Server 2013 (afin que le générateur de topologies puisse configurer les DACL requises).</span><span class="sxs-lookup"><span data-stu-id="0d294-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="0d294-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Ajout de bases de données d’archivage à un déploiement Lync Server 2013 existant</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0d294-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d294-141"><strong>Configurer l’authentification de serveur à serveur (uniquement en cas d’utilisation de l’intégration de Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="0d294-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="0d294-142">Configurez les serveurs pour activer l’authentification entre Lync Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0d294-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="0d294-143">Nous vous recommandons d’exécuter <strong>le test-CsExchangeStorageConnectivity testuser_sipUri – benne de dossier</strong> pour valider la connectivité de stockage d’archivage Exchange avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="0d294-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="0d294-144">Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="0d294-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="0d294-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing Server-to-Server Authentication (OAuth) and Partner applications dans Lync server 2013</a> dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="0d294-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d294-146"><strong>Configurer les stratégies et les paramètres de l’archivage</strong></span><span class="sxs-lookup"><span data-stu-id="0d294-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="0d294-147">Configurez l’archivage, y compris s’il faut utiliser l’intégration de Microsoft Exchange, la stratégie globale et les stratégies de site et d’utilisateur (lorsque vous n’utilisez pas l’intégration de Microsoft Exchange pour tout le stockage de données) et des options d’archivage spécifiques, telles que le mode critique et les données exportation et vidage.</span><span class="sxs-lookup"><span data-stu-id="0d294-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="0d294-148">Si vous utilisez l’intégration de Microsoft Exchange, configurez les stratégies de conservation inaltérable d’Exchange comme il convient.</span><span class="sxs-lookup"><span data-stu-id="0d294-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="0d294-149">Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0d294-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="0d294-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuration de la prise en charge de l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0d294-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="0d294-151">Documentation du produit Exchange (si vous utilisez l’intégration de Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="0d294-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="0d294-152">Déploiement de Lync Server et Microsoft Exchange dans des forêts différentes</span><span class="sxs-lookup"><span data-stu-id="0d294-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="0d294-153">Si Microsoft Exchange Server n’est pas déployé dans la même forêt que Lync Server, vous devez vous assurer que les attributs Active Directory d’Exchange suivants sont synchronisés avec la forêt où Lync Server est déployé :</span><span class="sxs-lookup"><span data-stu-id="0d294-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="0d294-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0d294-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="0d294-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0d294-155">proxyAddresses</span></span>

<span data-ttu-id="0d294-p107">Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.</span><span class="sxs-lookup"><span data-stu-id="0d294-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

