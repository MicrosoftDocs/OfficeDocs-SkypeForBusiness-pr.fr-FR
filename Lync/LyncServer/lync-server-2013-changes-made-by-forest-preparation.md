---
title: 'Lync Server 2013 : modifications apportées par la préparation de la forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 709263aeffe1a8681275d943da702242944868b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="27f81-102">Modifications apportées par la préparation de la forêt dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27f81-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27f81-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="27f81-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="27f81-104">Cette section décrit les paramètres globaux, les objets et les groupes de services universels et d’administration créés pendant la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="27f81-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="27f81-105">Paramètres globaux et objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="27f81-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="27f81-106">Si vous stockez des paramètres globaux dans le conteneur de configuration (comme c’est le cas pour tous les nouveaux déploiements Lync Server 2013), la préparation de la forêt utilise le conteneur services existants\\et ajoute un objet **RTC service** sous l’objet Configuration Services.</span><span class="sxs-lookup"><span data-stu-id="27f81-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="27f81-107">Sous l’objet RTC Service, la préparation de la forêt ajoute un objet **Paramètres globaux** de type msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="27f81-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="27f81-108">L’objet de paramètres globaux contient tous les paramètres qui s’appliquent au déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="27f81-109">Si vous stockez des paramètres globaux dans le conteneur système, la préparation de la forêt utilise un conteneur Microsoft sous le conteneur système du domaine racine et\\un objet de service RTC sous l’objet système Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27f81-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="27f81-110">La préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.</span><span class="sxs-lookup"><span data-stu-id="27f81-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="27f81-111">Groupes de services universels et d’administration Active Directory</span><span class="sxs-lookup"><span data-stu-id="27f81-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="27f81-p102">La préparation de la forêt crée des groupes universels basés sur le domaine que vous spécifiez et ajoute des entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape crée les groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="27f81-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="27f81-p103">Les groupes universels permettent aux administrateurs d’accéder aux services et aux paramètres globaux et de les gérer. La préparation de la forêt ajoute les types de groupes universels suivants :</span><span class="sxs-lookup"><span data-stu-id="27f81-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="27f81-116">**Groupes d’administration**   ces groupes définissent les rôles d’administrateur d’un réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="27f81-117">**Groupes d’infrastructure**   ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="27f81-118">Ils fonctionnent comme composants des groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="27f81-118">They function as components of administrative groups.</span></span> <span data-ttu-id="27f81-119">Vous ne devez pas modifier ces groupes ni leur ajouter directement des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="27f81-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="27f81-120">**Groupes de services**   ces groupes sont des comptes de service qui sont requis pour accéder à différents services Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="27f81-121">Le tableau suivant présente les groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="27f81-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="27f81-122">Groupes d’administration créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="27f81-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27f81-123">Groupe d’administration</span><span class="sxs-lookup"><span data-stu-id="27f81-123">Administrative group</span></span></th>
<th><span data-ttu-id="27f81-124">Description</span><span class="sxs-lookup"><span data-stu-id="27f81-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f81-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="27f81-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="27f81-126">Permet à ses membres de gérer les paramètres de serveurs et de pools, notamment tous les rôles de serveurs, les paramètres globaux et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="27f81-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f81-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="27f81-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="27f81-128">Permet à ses membres de gérer les paramètres utilisateur et de transférer des utilisateurs d’un serveur ou pool à un autre.</span><span class="sxs-lookup"><span data-stu-id="27f81-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f81-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="27f81-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="27f81-130">Permet à ses membres d’accéder en lecture aux paramètres de serveur, de pool et d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="27f81-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27f81-131">Le tableau suivant présente les groupes d’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="27f81-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="27f81-132">Groupes d’infrastructure créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="27f81-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27f81-133">Groupe d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="27f81-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="27f81-134">Description</span><span class="sxs-lookup"><span data-stu-id="27f81-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f81-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="27f81-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="27f81-136">Octroie un accès en écriture aux objets de paramètre globaux pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f81-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="27f81-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="27f81-138">Octroie un accès en lecture seule aux objets de paramètres globaux pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f81-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="27f81-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="27f81-140">Octroie un accès en lecture seule aux paramètres utilisateur de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f81-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="27f81-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="27f81-142">Octroie un accès en lecture seule aux paramètres de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="27f81-143">Ce groupe n’a pas accès aux paramètres de niveau pool, mais uniquement aux paramètres spécifiques à un serveur donné.</span><span class="sxs-lookup"><span data-stu-id="27f81-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f81-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="27f81-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="27f81-145">Octroie un accès en lecture seule à la configuration de Lync Server et est placé dans le groupe Administrateurs local du Survivable Branch Appliances lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="27f81-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27f81-146">Le tableau suivant présente les groupes de services.</span><span class="sxs-lookup"><span data-stu-id="27f81-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="27f81-147">Groupes de services créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="27f81-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27f81-148">Groupe de services</span><span class="sxs-lookup"><span data-stu-id="27f81-148">Service group</span></span></th>
<th><span data-ttu-id="27f81-149">Description</span><span class="sxs-lookup"><span data-stu-id="27f81-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f81-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="27f81-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="27f81-151">Inclut les comptes de service utilisés pour exécuter les serveurs frontaux et Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="27f81-152">Ce groupe permet aux serveurs d’accéder en lecture/écriture aux paramètres globaux et aux objets utilisateur Active Directory de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f81-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="27f81-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="27f81-154">Inclut les comptes de service utilisés pour exécuter les serveurs de conférence A/V, les services Web, le serveur de médiation, le serveur d’archivage et le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="27f81-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f81-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="27f81-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="27f81-156">Inclut les comptes de service utilisés pour exécuter les serveurs Edge Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f81-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="27f81-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="27f81-158">Inclut les serveurs qui peuvent participer à la réplication du magasin central de gestion Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f81-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="27f81-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="27f81-160">Octroie un accès en lecture seule aux paramètres de Lync Server, mais permet la configuration de l’installation d’un serveur Survivable Branch Server et du déploiement d’un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="27f81-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27f81-161">La préparation de la forêt ajoute ensuite des groupes de services et d’administration aux groupes d’infrastructure appropriés, comme suit :</span><span class="sxs-lookup"><span data-stu-id="27f81-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="27f81-162">RTCUniversalServerAdmins est ajouté à RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="27f81-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="27f81-163">RTCUniversalUserAdmins est ajouté en tant que membre de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="27f81-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="27f81-164">RTCHSUniversalServices, RTCComponentUniversalServices et RTCUniversalReadOnlyAdmins sont ajoutés en tant que membres de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="27f81-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="27f81-165">La préparation de forêt crée également les groupes de rôles RBAC (Contrôle d’accès basé sur un rôle) suivants :</span><span class="sxs-lookup"><span data-stu-id="27f81-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="27f81-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-166">CSAdministrator</span></span>

  - <span data-ttu-id="27f81-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="27f81-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="27f81-168">CSHelpDesk</span></span>

  - <span data-ttu-id="27f81-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="27f81-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="27f81-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="27f81-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="27f81-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="27f81-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="27f81-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="27f81-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="27f81-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="27f81-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="27f81-176">CsResponseGroupManager</span></span>

<span data-ttu-id="27f81-177">Pour plus d’informations sur les rôles RBAC et les tâches qui leur sont accordées, voir [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="27f81-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="27f81-178">La préparation de la forêt crée des entrées de clé publique et privées.</span><span class="sxs-lookup"><span data-stu-id="27f81-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="27f81-179">Il crée des ACE privées sur le conteneur de paramètres globaux utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f81-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="27f81-180">Ce conteneur est utilisé uniquement par Lync Server et se trouve dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="27f81-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="27f81-181">Les ACE publiques créées par la préparation de la forêt sont répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="27f81-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="27f81-182">Entrées de contrôle d’accès publiques créées par la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="27f81-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27f81-183">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="27f81-183">ACE</span></span></th>
<th><span data-ttu-id="27f81-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="27f81-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f81-185">Lire le conteneur système du domaine racine (non héritée)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="27f81-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="27f81-186">X</span><span class="sxs-lookup"><span data-stu-id="27f81-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f81-187">Lire le conteneur DisplaySpecifiers de la configuration (non héritée)</span><span class="sxs-lookup"><span data-stu-id="27f81-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="27f81-188">X</span><span class="sxs-lookup"><span data-stu-id="27f81-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="27f81-189"><STRONG>\*</STRONG>Les ACE qui ne sont pas héritées n’accordent pas l’accès aux objets enfants sous ces conteneurs.</span><span class="sxs-lookup"><span data-stu-id="27f81-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="27f81-190">\*Les entrées de contrôle d’accès qui sont héritées permettent d’accéder aux objets enfants qui figurent dans ces conteneurs.</span><span class="sxs-lookup"><span data-stu-id="27f81-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="27f81-191">La préparation de la forêt exécute les tâches suivantes sur le conteneur de configuration, sous le contexte d’affectation de noms de la configuration :</span><span class="sxs-lookup"><span data-stu-id="27f81-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="27f81-192">Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page **RTC property** sous les attributs adminContextMenu et adminPropertyPages du spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPersons (par exemple, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="27f81-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="27f81-193">Ajoute un objet **RTCPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User et Contact.</span><span class="sxs-lookup"><span data-stu-id="27f81-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="27f81-194">Ajoute un objet **RTCUserSearchPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User, Contact, OU et DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="27f81-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="27f81-195">Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage des unités d’organisation de la langue (CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers, par exemple) et copie des valeurs de l’attribut **extraColumns** de l’affichage par défaut (CN=default-Display, CN=409,CN=DisplaySpecifiers, par exemple).</span><span class="sxs-lookup"><span data-stu-id="27f81-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="27f81-196">Ajoute les attributs de filtrage **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** et **msRTCSIP-UserEnabled** sous l’attribut **attributeDisplayNames** de chaque spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPerson (par exemple, en anglais : CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="27f81-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

