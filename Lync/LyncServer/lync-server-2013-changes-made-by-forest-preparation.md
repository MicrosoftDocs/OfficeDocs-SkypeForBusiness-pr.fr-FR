---
title: 'Lync Server 2013 : modifications apportées par la préparation de la forêt'
description: 'Lync Server 2013 : modifications apportées par la préparation de la forêt.'
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
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543650"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="b86d4-103">Modifications apportées par la préparation de la forêt dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b86d4-103">Changes made by forest preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b86d4-104">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b86d4-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b86d4-105">Cette section décrit les paramètres globaux, les objets et les groupes de services universels et d’administration créés pendant la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="b86d4-105">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="b86d4-106">Paramètres globaux et objets Active Directory</span><span class="sxs-lookup"><span data-stu-id="b86d4-106">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="b86d4-107">Si vous stockez des paramètres globaux dans le conteneur de configuration (comme c’est le cas pour tous les nouveaux déploiements Lync Server 2013), la préparation de la forêt utilise le conteneur services existants et ajoute un objet **RTC service** sous l' \\ objet Configuration Services.</span><span class="sxs-lookup"><span data-stu-id="b86d4-107">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="b86d4-108">Sous l’objet RTC Service, la préparation de la forêt ajoute un objet **Paramètres globaux** de type msRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="b86d4-108">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="b86d4-109">L’objet de paramètres globaux contient tous les paramètres qui s’appliquent au déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-109">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="b86d4-110">Si vous stockez des paramètres globaux dans le conteneur système, la préparation de la forêt utilise un conteneur Microsoft sous le conteneur système du domaine racine et un objet de service RTC sous l' \\ objet système Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b86d4-110">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="b86d4-111">La préparation de la forêt ajoute également un nouvel objet **msRTCSIP-Domain** pour le domaine racine dans lequel la procédure est exécutée.</span><span class="sxs-lookup"><span data-stu-id="b86d4-111">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="b86d4-112">Groupes de services universels et d’administration Active Directory</span><span class="sxs-lookup"><span data-stu-id="b86d4-112">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="b86d4-p102">La préparation de la forêt crée des groupes universels basés sur le domaine que vous spécifiez et ajoute des entrées de contrôle d’accès (ACE) pour ces groupes. Cette étape crée les groupes universels dans les conteneurs d’utilisateurs du domaine que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="b86d4-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="b86d4-p103">Les groupes universels permettent aux administrateurs d’accéder aux services et aux paramètres globaux et de les gérer. La préparation de la forêt ajoute les types de groupes universels suivants :</span><span class="sxs-lookup"><span data-stu-id="b86d4-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="b86d4-117">**Groupes**     d’administration Ces groupes définissent les rôles d’administrateur pour un réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-117">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="b86d4-118">**Groupes**     d’infrastructure Ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-118">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="b86d4-119">Ils fonctionnent comme composants des groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="b86d4-119">They function as components of administrative groups.</span></span> <span data-ttu-id="b86d4-120">Vous ne devez pas modifier ces groupes ni leur ajouter directement des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b86d4-120">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="b86d4-121">**Groupes**     de services Ces groupes sont des comptes de service qui sont requis pour accéder à différents services Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-121">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="b86d4-122">Le tableau suivant présente les groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="b86d4-122">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="b86d4-123">Groupes d’administration créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="b86d4-123">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86d4-124">Groupe d’administration</span><span class="sxs-lookup"><span data-stu-id="b86d4-124">Administrative group</span></span></th>
<th><span data-ttu-id="b86d4-125">Description</span><span class="sxs-lookup"><span data-stu-id="b86d4-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b86d4-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="b86d4-127">Permet à ses membres de gérer les paramètres de serveurs et de pools, notamment tous les rôles de serveurs, les paramètres globaux et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b86d4-127">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86d4-128">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b86d4-128">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b86d4-129">Permet à ses membres de gérer les paramètres utilisateur et de transférer des utilisateurs d’un serveur ou pool à un autre.</span><span class="sxs-lookup"><span data-stu-id="b86d4-129">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-130">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="b86d4-130">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="b86d4-131">Permet à ses membres d’accéder en lecture aux paramètres de serveur, de pool et d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b86d4-131">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b86d4-132">Le tableau suivant présente les groupes d’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="b86d4-132">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="b86d4-133">Groupes d’infrastructure créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="b86d4-133">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86d4-134">Groupe d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="b86d4-134">Infrastructure group</span></span></th>
<th><span data-ttu-id="b86d4-135">Description</span><span class="sxs-lookup"><span data-stu-id="b86d4-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-136">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="b86d4-136">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="b86d4-137">Octroie un accès en écriture aux objets de paramètre globaux pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-137">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86d4-138">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b86d4-138">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b86d4-139">Octroie un accès en lecture seule aux objets de paramètres globaux pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-139">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-140">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b86d4-140">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b86d4-141">Octroie un accès en lecture seule aux paramètres utilisateur de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-141">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86d4-142">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b86d4-142">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b86d4-143">Octroie un accès en lecture seule aux paramètres de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-143">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="b86d4-144">Ce groupe n’a pas accès aux paramètres de niveau pool, mais uniquement aux paramètres spécifiques à un serveur donné.</span><span class="sxs-lookup"><span data-stu-id="b86d4-144">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-145">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="b86d4-145">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="b86d4-146">Octroie un accès en lecture seule à la configuration de Lync Server et est placé dans le groupe Administrateurs local du Survivable Branch Appliances lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="b86d4-146">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b86d4-147">Le tableau suivant présente les groupes de services.</span><span class="sxs-lookup"><span data-stu-id="b86d4-147">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="b86d4-148">Groupes de services créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="b86d4-148">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86d4-149">Groupe de services</span><span class="sxs-lookup"><span data-stu-id="b86d4-149">Service group</span></span></th>
<th><span data-ttu-id="b86d4-150">Description</span><span class="sxs-lookup"><span data-stu-id="b86d4-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-151">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b86d4-151">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b86d4-152">Inclut les comptes de service utilisés pour exécuter les serveurs frontaux et Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-152">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="b86d4-153">Ce groupe permet aux serveurs d’accéder en lecture/écriture aux paramètres globaux et aux objets utilisateur Active Directory de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-153">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86d4-154">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b86d4-154">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b86d4-155">Inclut les comptes de service utilisés pour exécuter les serveurs de conférence A/V, les services Web, le serveur de médiation, le serveur d’archivage et le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b86d4-155">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-156">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b86d4-156">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b86d4-157">Inclut les comptes de service utilisés pour exécuter les serveurs Edge Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-157">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86d4-158">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="b86d4-158">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="b86d4-159">Inclut les serveurs qui peuvent participer à la réplication du magasin central de gestion Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-159">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-160">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b86d4-160">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b86d4-161">Octroie un accès en lecture seule aux paramètres de Lync Server, mais permet la configuration de l’installation d’un serveur Survivable Branch Server et du déploiement d’un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="b86d4-161">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b86d4-162">La préparation de la forêt ajoute ensuite des groupes de services et d’administration aux groupes d’infrastructure appropriés, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b86d4-162">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="b86d4-163">RTCUniversalServerAdmins est ajouté à RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="b86d4-163">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="b86d4-164">RTCUniversalUserAdmins est ajouté en tant que membre de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="b86d4-164">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="b86d4-165">RTCHSUniversalServices, RTCComponentUniversalServices et RTCUniversalReadOnlyAdmins sont ajoutés en tant que membres de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup et RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="b86d4-165">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="b86d4-166">La préparation de forêt crée également les groupes de rôles RBAC (Contrôle d’accès basé sur un rôle) suivants :</span><span class="sxs-lookup"><span data-stu-id="b86d4-166">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="b86d4-167">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-167">CSAdministrator</span></span>

  - <span data-ttu-id="b86d4-168">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-168">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="b86d4-169">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="b86d4-169">CSHelpDesk</span></span>

  - <span data-ttu-id="b86d4-170">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-170">CSLocationAdministrator</span></span>

  - <span data-ttu-id="b86d4-171">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-171">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="b86d4-172">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-172">CSServerAdministrator</span></span>

  - <span data-ttu-id="b86d4-173">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-173">CSUserAdministrator</span></span>

  - <span data-ttu-id="b86d4-174">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-174">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="b86d4-175">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b86d4-175">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="b86d4-176">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="b86d4-176">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="b86d4-177">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="b86d4-177">CsResponseGroupManager</span></span>

<span data-ttu-id="b86d4-178">Pour plus d’informations sur les rôles RBAC et les tâches qui leur sont accordées, voir [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b86d4-178">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="b86d4-179">La préparation de la forêt crée des entrées de clé publique et privées.</span><span class="sxs-lookup"><span data-stu-id="b86d4-179">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="b86d4-180">Il crée des ACE privées sur le conteneur de paramètres globaux utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b86d4-180">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="b86d4-181">Ce conteneur est utilisé uniquement par Lync Server et se trouve dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="b86d4-181">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="b86d4-182">Les ACE publiques créées par la préparation de la forêt sont répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="b86d4-182">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="b86d4-183">Entrées de contrôle d’accès publiques créées par la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="b86d4-183">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86d4-184">moteur ACE</span><span class="sxs-lookup"><span data-stu-id="b86d4-184">ACE</span></span></th>
<th><span data-ttu-id="b86d4-185">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b86d4-185">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86d4-186">Lire le conteneur système du domaine racine (non héritée)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="b86d4-186">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="b86d4-187">X</span><span class="sxs-lookup"><span data-stu-id="b86d4-187">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86d4-188">Lire le conteneur DisplaySpecifiers de la configuration (non héritée)</span><span class="sxs-lookup"><span data-stu-id="b86d4-188">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="b86d4-189">X</span><span class="sxs-lookup"><span data-stu-id="b86d4-189">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b86d4-190"><STRONG>\*</STRONG>Les ACE qui ne sont pas héritées n’accordent pas l’accès aux objets enfants sous ces conteneurs.</span><span class="sxs-lookup"><span data-stu-id="b86d4-190"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="b86d4-191">\*Les entrées de contrôle d’accès qui sont héritées permettent d’accéder aux objets enfants qui figurent dans ces conteneurs.</span><span class="sxs-lookup"><span data-stu-id="b86d4-191">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="b86d4-192">La préparation de la forêt exécute les tâches suivantes sur le conteneur de configuration, sous le contexte d’affectation de noms de la configuration :</span><span class="sxs-lookup"><span data-stu-id="b86d4-192">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="b86d4-193">Ajoute une entrée **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** pour la page **RTC property** sous les attributs adminContextMenu et adminPropertyPages du spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPersons (par exemple, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="b86d4-193">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="b86d4-194">Ajoute un objet **RTCPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User et Contact.</span><span class="sxs-lookup"><span data-stu-id="b86d4-194">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="b86d4-195">Ajoute un objet **RTCUserSearchPropertySet** de type **controlAccessRight** sous **Extended-Rights** qui s’applique aux classes User, Contact, OU et DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="b86d4-195">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="b86d4-196">Ajoute **msRTCSIP-PrimaryUserAddress** sous l’attribut **extraColumns** de chaque spécificateur d’affichage des unités d’organisation de la langue (CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers, par exemple) et copie des valeurs de l’attribut **extraColumns** de l’affichage par défaut (CN=default-Display, CN=409,CN=DisplaySpecifiers, par exemple).</span><span class="sxs-lookup"><span data-stu-id="b86d4-196">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="b86d4-197">Ajoute les attributs de filtrage **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** et **msRTCSIP-UserEnabled** sous l’attribut **attributeDisplayNames** de chaque spécificateur d’affichage de la langue pour les objets User, Contact et InetOrgPerson (par exemple, en anglais : CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="b86d4-197">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

