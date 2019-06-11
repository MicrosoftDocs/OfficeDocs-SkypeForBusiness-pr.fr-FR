---
title: 'Lync Server 2013: modifications apportées par la préparation de la forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="83120-102">Modifications apportées par la préparation de la forêt dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83120-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83120-103">_**Dernière modification de la rubrique:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="83120-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="83120-104">Cette section décrit les paramètres globaux et les objets, ainsi que les groupes de services et d’administration universels créés par l’étape de préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="83120-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="83120-105">Paramètres globaux et objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="83120-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="83120-106">Si vous stockez des paramètres globaux dans le conteneur de configuration (comme pour tous les nouveaux déploiements de Lync Server 2013), la préparation de la forêt utilise le conteneur services existants et ajoute un\\objet **Service RTC** sous les services de configuration. objet.</span><span class="sxs-lookup"><span data-stu-id="83120-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="83120-107">Sous l’objet RTC service, la préparation de la forêt ajoute un objet de **paramètres globaux** de type MsRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="83120-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="83120-108">L’objet paramètres globaux contient tous les paramètres qui s’appliquent au déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="83120-109">Si vous stockez des paramètres globaux dans le conteneur système, la préparation de la forêt utilise un conteneur Microsoft sous le conteneur système du domaine racine et\\un objet service RTC sous l’objet Microsoft système.</span><span class="sxs-lookup"><span data-stu-id="83120-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="83120-110">La préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.</span><span class="sxs-lookup"><span data-stu-id="83120-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="83120-111">Service universel et groupes d’administration Active Directory</span><span class="sxs-lookup"><span data-stu-id="83120-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="83120-112">La préparation de la forêt crée des groupes universels en fonction du domaine que vous spécifiez et ajoute des entrées de contrôle d’accès (ACE) pour ces groupes.</span><span class="sxs-lookup"><span data-stu-id="83120-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="83120-113">Cette étape permet de créer des groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="83120-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="83120-114">Les groupes universels permettent aux administrateurs d’accéder aux paramètres globaux et de gérer ces derniers.</span><span class="sxs-lookup"><span data-stu-id="83120-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="83120-115">La préparation de la forêt ajoute les types suivants de groupes universels:</span><span class="sxs-lookup"><span data-stu-id="83120-115">Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="83120-116">**Groupes d’administration**   ces groupes définissent des rôles d’administrateur pour un réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="83120-117">**Groupes d’infrastructure**   ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="83120-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="83120-118">Ils fonctionnent en tant que composants de groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="83120-118">They function as components of administrative groups.</span></span> <span data-ttu-id="83120-119">Vous ne devez pas modifier ces groupes ni y ajouter des utilisateurs directement.</span><span class="sxs-lookup"><span data-stu-id="83120-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="83120-120">**Services les groupes**   sont des comptes de service nécessaires pour accéder à différents services Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="83120-121">Le tableau suivant décrit les groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="83120-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="83120-122">Groupes d’administration créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="83120-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83120-123">Groupe d’administration</span><span class="sxs-lookup"><span data-stu-id="83120-123">Administrative group</span></span></th>
<th><span data-ttu-id="83120-124">Description</span><span class="sxs-lookup"><span data-stu-id="83120-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83120-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83120-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="83120-126">Permet aux membres de gérer les paramètres du serveur et du pool, y compris tous les rôles de serveur, les paramètres globaux et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="83120-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83120-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="83120-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="83120-128">Permet aux membres de gérer les paramètres utilisateur et de déplacer les utilisateurs d’un serveur ou d’un pool vers un autre.</span><span class="sxs-lookup"><span data-stu-id="83120-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83120-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="83120-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="83120-130">Permet aux membres de lire les paramètres du serveur, du pool et de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="83120-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83120-131">Le tableau suivant décrit les groupes d’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="83120-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="83120-132">Groupes d’infrastructure créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="83120-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83120-133">Groupe d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="83120-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="83120-134">Description</span><span class="sxs-lookup"><span data-stu-id="83120-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83120-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="83120-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="83120-136">Accorde l’accès en écriture aux objets de paramètres globaux de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83120-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="83120-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="83120-138">Octroie un accès en lecture seule aux objets de paramètres globaux pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83120-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="83120-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="83120-140">Octroie un accès en lecture seule aux paramètres utilisateur de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83120-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="83120-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="83120-142">Octroie un accès en lecture seule aux paramètres du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="83120-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="83120-143">Ce groupe n’a pas accès aux paramètres de niveau de regroupement, uniquement aux paramètres spécifiques à un serveur individuel.</span><span class="sxs-lookup"><span data-stu-id="83120-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83120-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="83120-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="83120-145">Octroie un accès en lecture seule à la configuration du serveur Lync et est placé dans le groupe administrateurs locaux des appareils de succursales survivables au cours de l’installation.</span><span class="sxs-lookup"><span data-stu-id="83120-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83120-146">Le tableau suivant décrit les groupes de services.</span><span class="sxs-lookup"><span data-stu-id="83120-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="83120-147">Groupes de services créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="83120-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83120-148">Groupe de services</span><span class="sxs-lookup"><span data-stu-id="83120-148">Service group</span></span></th>
<th><span data-ttu-id="83120-149">Description</span><span class="sxs-lookup"><span data-stu-id="83120-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83120-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83120-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="83120-151">Inclut les comptes de service utilisés pour exécuter les serveurs front-end Server et Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="83120-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="83120-152">Ce groupe permet à un serveur en lecture/écriture de l’accès en lecture/écriture aux paramètres globaux et aux objets utilisateurs Active Directory de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83120-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83120-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="83120-154">Inclut les comptes de service utilisés pour exécuter des serveurs de conférence A/V, des services Web, un serveur de médiation, un serveur d’archivage et un serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="83120-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83120-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83120-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="83120-156">Inclut les comptes de service utilisés pour exécuter les serveurs Edge de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83120-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="83120-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="83120-158">Inclut les serveurs qui peuvent participer à la réplication du magasin de gestion central de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83120-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83120-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="83120-160">Octroie un accès en lecture seule aux paramètres du serveur Lync, mais permet une configuration pour l’installation d’un serveur de succursales survivant et du déploiement d’une unité de branchement plus survivant.</span><span class="sxs-lookup"><span data-stu-id="83120-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="83120-161">La préparation de la forêt ajoute ensuite des groupes de services et d’administration aux groupes d’infrastructure appropriés, comme suit:</span><span class="sxs-lookup"><span data-stu-id="83120-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="83120-162">RTCUniversalServerAdmins est ajouté à RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="83120-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="83120-163">RTCUniversalUserAdmins est ajouté en tant que membre de RTCUniversalGlobalReadOnlyGroup, de RTCUniversalServerReadOnlyGroup et d’RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="83120-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="83120-164">RTCHSUniversalServices, RTCComponentUniversalServices et RTCUniversalReadOnlyAdmins sont ajoutés en tant que membres de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="83120-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="83120-165">La préparation de la forêt crée également les groupes de contrôle d’accès basés sur les rôles suivants:</span><span class="sxs-lookup"><span data-stu-id="83120-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="83120-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-166">CSAdministrator</span></span>

  - <span data-ttu-id="83120-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="83120-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="83120-168">CSHelpDesk</span></span>

  - <span data-ttu-id="83120-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="83120-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="83120-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="83120-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="83120-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="83120-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="83120-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="83120-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="83120-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="83120-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="83120-176">CsResponseGroupManager</span></span>

<span data-ttu-id="83120-177">Pour plus d’informations sur les rôles RBAC et les tâches autorisées pour chacun, voir [planification du contrôle d’accès basé sur les rôles dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="83120-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="83120-178">La préparation de la forêt crée des entrées ACE privées et publiques.</span><span class="sxs-lookup"><span data-stu-id="83120-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="83120-179">Il crée des ACE privées sur le conteneur de paramètres globaux utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83120-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="83120-180">Ce conteneur est utilisé uniquement par Lync Server et réside dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="83120-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="83120-181">Les ACE publiques créées par une préparation de forêt sont répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="83120-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="83120-182">ACE publiques créées par une préparation de forêt</span><span class="sxs-lookup"><span data-stu-id="83120-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83120-183">MAILLOTS</span><span class="sxs-lookup"><span data-stu-id="83120-183">ACE</span></span></th>
<th><span data-ttu-id="83120-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="83120-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83120-185">Lire le conteneur système du domaine racine (non hérité)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="83120-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="83120-186">X</span><span class="sxs-lookup"><span data-stu-id="83120-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83120-187">Lecture du conteneur de configuration de DisplaySpecifiers (non hérité)</span><span class="sxs-lookup"><span data-stu-id="83120-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="83120-188">X</span><span class="sxs-lookup"><span data-stu-id="83120-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="83120-189"><STRONG>\*</STRONG>Les ACE qui ne sont pas héritées n’accordent pas l’accès aux objets enfants sous ces conteneurs.</span><span class="sxs-lookup"><span data-stu-id="83120-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="83120-190">Les As héritent d’octroyer l’accès à des objets enfants sous ces conteneurs.</span><span class="sxs-lookup"><span data-stu-id="83120-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="83120-191">Dans le conteneur Configuration, sous le contexte d’appellation de configuration, la préparation de la forêt effectue les tâches suivantes:</span><span class="sxs-lookup"><span data-stu-id="83120-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="83120-192">Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page de **Propriétés RTC** sous les attributs adminContextMenu et adminPropertyPages du spécificateur d’affichage de langue pour les utilisateurs, les contacts et les inetOrgPersons (par exemple, CN = user-Display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="83120-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="83120-193">Ajoute un objet **RTCPropertySet** de type **ControlAccessRight** sous **droits étendus** qui s’appliquent aux classes d’utilisateur et de contact.</span><span class="sxs-lookup"><span data-stu-id="83120-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="83120-194">Ajoute un objet **RTCUserSearchPropertySet** de type **ControlAccessRight** sous **privilèges étendus** qui s’applique aux classes utilisateur, contact, UO et domainDNS.</span><span class="sxs-lookup"><span data-stu-id="83120-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="83120-195">Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage de l’unité d’organisation (UO) Language (par exemple, CN = ORGANIZATIONALUNIT-Display, CN = 409, CN = DisplaySpecifiers) et copie les valeurs du **extraColumnsx** xxxxxxxxx XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX</span><span class="sxs-lookup"><span data-stu-id="83120-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="83120-196">Ajoute les attributs de filtre **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**et **msRTCSIP-UserEnabled** sous l’attribut **attributeDisplayNames** de chaque spécificateur d’affichage de langue pour les utilisateurs, les contacts, et les objets InetOrgPerson (par exemple, en anglais: CN = user-Display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="83120-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

