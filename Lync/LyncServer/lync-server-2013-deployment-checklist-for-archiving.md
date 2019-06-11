---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="ef84d-102">Liste de vérification du déploiement pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef84d-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef84d-103">_**Dernière modification de la rubrique:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ef84d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ef84d-104">L’archivage est automatiquement installé sur chaque serveur frontal de votre déploiement Lync Server 2013, mais vous devez le configurer pour pouvoir l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="ef84d-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="ef84d-105">Les étapes nécessaires pour les configurer, telles qu’elles sont résumées dans cette section, constituent le déploiement de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="ef84d-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="ef84d-106">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="ef84d-106">Deployment Sequence</span></span>

<span data-ttu-id="ef84d-107">La configuration de l’archivage dépend de l’option de stockage que vous choisissez:</span><span class="sxs-lookup"><span data-stu-id="ef84d-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="ef84d-108">Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer des stratégies d’archivage Lync Server 2013 pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ef84d-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="ef84d-109">Au lieu de cela, configurez vos stratégies de conservation inaltérable pour la prise en charge de l’archivage pour les utilisateurs hébergés sur Exchange 2013 et leurs boîtes aux lettres sont placées dans la conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="ef84d-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ef84d-110">Pour plus d’informations sur la configuration de ces stratégies, voir la documentation du produit Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ef84d-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="ef84d-111">Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs dans le cadre de votre déploiement, vous devez ajouter des bases de données d’archivage de Lync Server (bases de données SQL Server) à votre topologie, puis les publier, ainsi que configurer des stratégies et des paramètres pour vos utilisateurs, avant de pouvoir archiver des données pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ef84d-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="ef84d-112">Vous pouvez déployer des bases de données d’archivage en même temps que le déploiement de votre topologie initiale ou après le déploiement d’au moins un pool frontal ou d’un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="ef84d-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="ef84d-113">Ce document décrit le déploiement de bases de données d’archivage en les ajoutant à un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="ef84d-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="ef84d-114">Si vous activez l’archivage dans une liste frontale ou un serveur Standard Edition Server, vous devez l’activer pour tous les autres pools front-end et serveurs Standard Edition dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ef84d-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="ef84d-115">Cela afin de permettre aux utilisateurs dont les communications doivent être archivées d’être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool.</span><span class="sxs-lookup"><span data-stu-id="ef84d-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="ef84d-116">Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, la totalité de la session risque de ne pas être archivée.</span><span class="sxs-lookup"><span data-stu-id="ef84d-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="ef84d-117">Le cas échéant, il est toujours possible d’archiver les messages instantanés échangés avec des utilisateurs pour lesquels l’archivage est activé, mais pas les fichiers de contenu des conférences, ni les événements de participation ou d’arrêt de participation aux conférences.</span><span class="sxs-lookup"><span data-stu-id="ef84d-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ef84d-118">Si l’archivage est essentiel au sein de votre organisation pour des raisons de conformité, veillez à déployer l’archivage, à configurer les stratégies et autres options au niveau approprié, puis à l’activer pour tous les utilisateurs appropriés avant d’activer ces utilisateurs pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef84d-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="ef84d-119">Processus de déploiement d’archivage</span><span class="sxs-lookup"><span data-stu-id="ef84d-119">Archiving Deployment Process</span></span>

<span data-ttu-id="ef84d-120">Le tableau ci-dessous décrit les étapes nécessaires pour déployer l’archivage dans une topologie existante.</span><span class="sxs-lookup"><span data-stu-id="ef84d-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef84d-121">Phase</span><span class="sxs-lookup"><span data-stu-id="ef84d-121">Phase</span></span></th>
<th><span data-ttu-id="ef84d-122">Étapes</span><span class="sxs-lookup"><span data-stu-id="ef84d-122">Steps</span></span></th>
<th><span data-ttu-id="ef84d-123">Rôles et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="ef84d-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="ef84d-124">Documentation</span><span class="sxs-lookup"><span data-stu-id="ef84d-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef84d-125"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="ef84d-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ef84d-126">Pour utiliser l’intégration de Microsoft Exchange (à l’aide d’Exchange 2013 pour l’archivage du stockage pour certains ou pour tous les utilisateurs), vous avez besoin d’un déploiement Exchange 2013 existant.</span><span class="sxs-lookup"><span data-stu-id="ef84d-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="ef84d-127">Pour utiliser des bases de données d’archivage distinctes (à l’aide de bases de données SQL Server) pour l’archivage du stockage pour tout ou partie des utilisateurs, SQL Server sur le serveur qui stockera les données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ef84d-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="ef84d-128">L’archivage s’exécute sur les serveurs front-end d’un pool d’entreprise et de serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ef84d-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="ef84d-129">Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="ef84d-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="ef84d-130">Utilisateur du domaine membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="ef84d-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="ef84d-131"><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ef84d-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="ef84d-132">La <a href="lync-server-2013-server-software-and-infrastructure-support.md">prise en charge des logiciels et de l’infrastructure du serveur dans Lync Server 2013</a> dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ef84d-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="ef84d-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ef84d-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="ef84d-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configuration de systèmes et d’infrastructure pour l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ef84d-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="ef84d-135">La <a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">prise en charge de l’intégration d’Exchange Server et SharePoint dans Lync Server 2013</a> dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ef84d-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef84d-136"><strong>Créez la topologie interne appropriée pour la prise en charge de l’archivage (uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement).</strong></span><span class="sxs-lookup"><span data-stu-id="ef84d-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="ef84d-137">Exécutez le générateur de topologie pour ajouter des bases de données d’archivage Lync Server 2013 (bases de données SQL Server) à la topologie, puis publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="ef84d-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="ef84d-138">Pour définir une topologie afin d’incorporer des bases de données d’archivage, un compte membre du groupe utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="ef84d-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="ef84d-139">Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers 2013 Lync Server (de façon à ce que le générateur de topologie puisse Configurez les DACL requis).</span><span class="sxs-lookup"><span data-stu-id="ef84d-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="ef84d-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Ajouter des bases de données d’archivage à un déploiement 2013 Lync Server existant</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ef84d-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef84d-141"><strong>Configurer l’authentification de serveur à serveur (uniquement si vous utilisez l’intégration de Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="ef84d-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="ef84d-142">Configurer des serveurs pour activer l’authentification entre Lync Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ef84d-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="ef84d-143">Nous vous recommandons d’exécuter <strong>test-CsExchangeStorageConnectivity testuser_sipUri – benne de dossiers</strong> pour valider la connectivité de stockage d’archivage Exchange avant de procéder à l’archivage.</span><span class="sxs-lookup"><span data-stu-id="ef84d-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="ef84d-144">Un compte doté des autorisations appropriées pour gérer les certificats sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="ef84d-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="ef84d-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync server 2013</a> dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="ef84d-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef84d-146"><strong>Configurer les stratégies et configurations d’archivage</strong></span><span class="sxs-lookup"><span data-stu-id="ef84d-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="ef84d-147">Configuration de l’archivage, y compris l’utilisation de l’intégration de Microsoft Exchange, de la stratégie globale et des stratégies de site et d’utilisateur (si vous n’utilisez pas l’intégration de Microsoft Exchange pour tout le stockage des données) et des options d’archivage spécifiques, telles que le mode et les données critiques exportation et suppression définitive.</span><span class="sxs-lookup"><span data-stu-id="ef84d-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="ef84d-148">Dans le cadre de l’utilisation de l’intégration de Microsoft Exchange, configurez les stratégies de blocage sur place Exchange, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ef84d-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="ef84d-149">Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle CSArchivingAdministrator ou CSAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ef84d-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="ef84d-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuration de la prise en charge de l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ef84d-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="ef84d-151">Documentation du produit Exchange (si vous utilisez l’intégration de Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="ef84d-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="ef84d-152">Déploiement de Lync Server et Microsoft Exchange dans différentes forêts</span><span class="sxs-lookup"><span data-stu-id="ef84d-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="ef84d-153">Si Microsoft Exchange Server n’est pas déployé dans la même forêt que Lync Server, vous devez vous assurer que les attributs Active Directory suivants sont synchronisés avec la forêt sur laquelle Lync Server est déployé:</span><span class="sxs-lookup"><span data-stu-id="ef84d-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="ef84d-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ef84d-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="ef84d-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ef84d-155">proxyAddresses</span></span>

<span data-ttu-id="ef84d-p107">Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.</span><span class="sxs-lookup"><span data-stu-id="ef84d-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

