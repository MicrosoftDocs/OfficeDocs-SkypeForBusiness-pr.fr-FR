---
title: 'Lync Server 2013 : planification du contrôle d’accès basé sur un rôle'
description: 'Lync Server 2013 : planification du contrôle d’accès basé sur un rôle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971b3353694a1cdd53d88452717e6a9a360c6870
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549240"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="571d9-103">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="571d9-103">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="571d9-104">_**Dernière modification de la rubrique :** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="571d9-104">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="571d9-105">Pour vous permettre de déléguer des tâches administratives tout en conservant des normes de sécurité élevées, Lync Server 2013 offre un contrôle d’accès basé sur un rôle (RBAC).</span><span class="sxs-lookup"><span data-stu-id="571d9-105">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="571d9-106">Avec le contrôle d’accès basé sur un rôle, le privilège administratif est accordé en affectant des rôles d’administrateur aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="571d9-106">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="571d9-107">Lync Server 2013 inclut un ensemble complet de rôles administratifs intégrés, et vous permet également de créer de nouveaux rôles et de spécifier une liste personnalisée d’applets de commande pour chaque nouveau rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-107">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="571d9-108">Vous pouvez aussi ajouter des scripts d’applets de commande aux tâches autorisées des rôles RBAC prédéfinis et personnalisés.</span><span class="sxs-lookup"><span data-stu-id="571d9-108">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="571d9-109">Centralisation et sécurité du serveur améliorées</span><span class="sxs-lookup"><span data-stu-id="571d9-109">Better Server Security and Centralization</span></span>

<span data-ttu-id="571d9-110">Avec RBAC, l’accès et l’autorisation sont basés précisément sur le rôle Lync Server d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="571d9-110">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="571d9-111">Cela permet la mise en œuvre de la pratique de sécurité du « privilège minimum », qui accorde aux administrateurs et aux utilisateurs uniquement les droits nécessaires à la réalisation de leur travail.</span><span class="sxs-lookup"><span data-stu-id="571d9-111">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="571d9-112">Les restrictions RBAC fonctionnent uniquement sur les administrateurs travaillant à distance, à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="571d9-112">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="571d9-113">Un utilisateur se trouvant sur un serveur exécutant Lync Server n’est pas limité par RBAC.</span><span class="sxs-lookup"><span data-stu-id="571d9-113">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="571d9-114">Par conséquent, la sécurité physique de votre serveur Lync Server est importante pour conserver les restrictions RBAC.</span><span class="sxs-lookup"><span data-stu-id="571d9-114">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="571d9-115">Rôles et étendue</span><span class="sxs-lookup"><span data-stu-id="571d9-115">Roles and Scope</span></span>

<span data-ttu-id="571d9-p104">Dans le cadre de RBAC, un *rôle* est autorisé à utiliser une liste d’applets de commande conçues pour rendre service à un certain type d’administrateur ou de technicien. Une *étendue* est l’ensemble d’objets que peuvent exploiter les applets de commande définies dans un rôle. Les objets couverts par l’étendue peuvent être des comptes d’utilisateurs (regroupés par unité d’organisation) ou des serveurs (regroupés par site).</span><span class="sxs-lookup"><span data-stu-id="571d9-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="571d9-119">Le tableau suivant répertorie les rôles prédéfinis dans Lync Server et offre une vue d’ensemble des types de tâches que chaque peut effectuer.</span><span class="sxs-lookup"><span data-stu-id="571d9-119">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="571d9-120">La quatrième colonne indique le rôle Microsoft Exchange Server similaire pour chaque rôle Lync Server, s’il en existe un.</span><span class="sxs-lookup"><span data-stu-id="571d9-120">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="571d9-121">Rôles d’administration prédéfinis</span><span class="sxs-lookup"><span data-stu-id="571d9-121">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="571d9-122">Role</span><span class="sxs-lookup"><span data-stu-id="571d9-122">Role</span></span></th>
<th><span data-ttu-id="571d9-123">Tâches autorisées</span><span class="sxs-lookup"><span data-stu-id="571d9-123">Tasks allowed</span></span></th>
<th><span data-ttu-id="571d9-124">Groupe Active Directory sous-jacent</span><span class="sxs-lookup"><span data-stu-id="571d9-124">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="571d9-125">Équivalent Exchange</span><span class="sxs-lookup"><span data-stu-id="571d9-125">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="571d9-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-p106">Permet d’effectuer toutes les tâches d’administration et de modifier tous les paramètres, y compris la création de rôles et l’affectation d’utilisateurs aux rôles. Permet de développer un déploiement en ajoutant de nouveaux sites, pools et services.</span><span class="sxs-lookup"><span data-stu-id="571d9-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="571d9-129">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-129">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-130">Organization Management</span><span class="sxs-lookup"><span data-stu-id="571d9-130">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="571d9-131">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-131">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-132">Peut activer et désactiver des utilisateurs pour Lync Server, déplacer des utilisateurs et affecter des stratégies existantes aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="571d9-132">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="571d9-133">Ne permet pas de modifier des stratégies.</span><span class="sxs-lookup"><span data-stu-id="571d9-133">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="571d9-134">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-134">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-135">Mail Recipients</span><span class="sxs-lookup"><span data-stu-id="571d9-135">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="571d9-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-136">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-137">Permet de créer, configurer et gérer les stratégies et les paramètres liés à la voix.</span><span class="sxs-lookup"><span data-stu-id="571d9-137">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="571d9-138">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-138">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-139">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="571d9-139">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="571d9-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-140">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-p108">Permet de gérer, surveiller et dépanner des serveurs et des services. Permet d’empêcher de nouvelles connexions aux serveurs, d’arrêter et de démarrer des services, et d’appliquer des mises à jour logicielles. Ne permet pas d’effectuer des modifications ayant un impact de configuration global.</span><span class="sxs-lookup"><span data-stu-id="571d9-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="571d9-144">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-144">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-145">Server Management</span><span class="sxs-lookup"><span data-stu-id="571d9-145">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="571d9-146">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-146">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-147">Permet de visualiser le déploiement, notamment les informations d’utilisateur et de serveur, afin de surveiller l’état du déploiement.</span><span class="sxs-lookup"><span data-stu-id="571d9-147">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="571d9-148">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-148">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-149">View-Only Organization Management</span><span class="sxs-lookup"><span data-stu-id="571d9-149">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="571d9-150">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="571d9-150">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="571d9-p109">Permet d’afficher le déploiement, notamment les stratégies et les propriétés d’utilisateurs. Permet d’exécuter des tâches de dépannage spécifiques. Ne permet pas de modifier les stratégies et les propriétés d’utilisateurs, la configuration du serveur ou les services.</span><span class="sxs-lookup"><span data-stu-id="571d9-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="571d9-154">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="571d9-154">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="571d9-155">Centre</span><span class="sxs-lookup"><span data-stu-id="571d9-155">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="571d9-156">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-156">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-157">Permet de modifier les stratégies et la configuration de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="571d9-157">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="571d9-158">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-158">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-159">Retention Management, Legal Hold</span><span class="sxs-lookup"><span data-stu-id="571d9-159">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="571d9-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-160">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-161">Permet de gérer la configuration de l’application Response Group dans un site.</span><span class="sxs-lookup"><span data-stu-id="571d9-161">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="571d9-162">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-162">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-163">Non applicable</span><span class="sxs-lookup"><span data-stu-id="571d9-163">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="571d9-164">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-164">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-p110">Niveau de droits le plus bas pour la gestion Enhanced 9-1-1 (E9-1-1), y compris la création d’identificateurs réseau et d’emplacements E9-1-1, ainsi que leur association entre eux. Ce rôle est toujours affecté avec une étendue globale.</span><span class="sxs-lookup"><span data-stu-id="571d9-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="571d9-167">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-167">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-168">Non applicable</span><span class="sxs-lookup"><span data-stu-id="571d9-168">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="571d9-169">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="571d9-169">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="571d9-170">Permet de gérer des groupes Response Group spécifiques.</span><span class="sxs-lookup"><span data-stu-id="571d9-170">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="571d9-171">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="571d9-171">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="571d9-172">Non applicable</span><span class="sxs-lookup"><span data-stu-id="571d9-172">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="571d9-173">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-173">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-174">Permet de gérer la fonctionnalité Conversation permanente, ainsi que des salles de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="571d9-174">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="571d9-175">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="571d9-175">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="571d9-176">Non applicable</span><span class="sxs-lookup"><span data-stu-id="571d9-176">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="571d9-177">Tous les rôles prédéfinis fournis dans Lync Server ont une étendue globale.</span><span class="sxs-lookup"><span data-stu-id="571d9-177">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="571d9-178">Pour respecter les pratiques du « privilège minimum », vous ne devez pas affecter d’utilisateurs à des rôles ayant une étendue globale s’ils doivent uniquement administrer un groupe limité de serveurs ou d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="571d9-178">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="571d9-179">Pour ce faire, vous pouvez créer des rôles basés sur un rôle existant, mais avec une étendue plus limitée.</span><span class="sxs-lookup"><span data-stu-id="571d9-179">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="571d9-180">Création d’un rôle inclus dans une étendue</span><span class="sxs-lookup"><span data-stu-id="571d9-180">Creating a Scoped Role</span></span>

<span data-ttu-id="571d9-181">Quand vous créez un rôle ayant une étendue limitée (rôle inclus dans une étendue), vous spécifiez l’étendue et le rôle existant sur lequel il est basé, mais aussi le groupe Active Directory auquel le rôle est affecté.</span><span class="sxs-lookup"><span data-stu-id="571d9-181">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="571d9-182">Le groupe Active Directory que vous spécifiez doit déjà être créé.</span><span class="sxs-lookup"><span data-stu-id="571d9-182">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="571d9-183">L’applet de commande suivante est un exemple de création d’un rôle ayant les privilèges de l’un des rôles d’administrateur prédéfinis, mais dont l’étendue est limitée.</span><span class="sxs-lookup"><span data-stu-id="571d9-183">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="571d9-184">Il crée un rôle appelé `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="571d9-184">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="571d9-185">Le rôle a les capacités du rôle CsServerAdministrator prédéfini, mais seulement pour les serveurs situés dans le site Site01.</span><span class="sxs-lookup"><span data-stu-id="571d9-185">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="571d9-186">Pour que cette applet de commande fonctionne, le site Site01 doit déjà être défini et un groupe de sécurité universel nommé `Site01 Server Administrators` doit déjà exister.</span><span class="sxs-lookup"><span data-stu-id="571d9-186">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="571d9-187">Une fois cette cmdlet exécutée, tous les utilisateurs membres du `Site01 Server Administrators` groupe disposent des privilèges d’administrateur de serveur pour les serveurs dans Site01.</span><span class="sxs-lookup"><span data-stu-id="571d9-187">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="571d9-188">De plus, tous les utilisateurs qui sont ajoutés ultérieurement à ce groupe de sécurité universel obtiendront également les privilèges de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-188">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="571d9-189">Notez que le rôle lui-même et le groupe de sécurité universel auquel il est affecté sont appelés `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="571d9-189">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="571d9-190">L’exemple suivant limite l’étendue d’utilisateur au lieu de l’étendue du serveur.</span><span class="sxs-lookup"><span data-stu-id="571d9-190">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="571d9-191">Il crée un `Sales Users Administrator` rôle pour administrer les comptes d’utilisateur dans l’unité d’organisation Sales.</span><span class="sxs-lookup"><span data-stu-id="571d9-191">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="571d9-192">Le groupe de sécurité universel SalesUsersAdministrator doit déjà être créé pour que cette cmdlet fonctionne.</span><span class="sxs-lookup"><span data-stu-id="571d9-192">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="571d9-193">Création d’un rôle</span><span class="sxs-lookup"><span data-stu-id="571d9-193">Creating a New Role</span></span>

<span data-ttu-id="571d9-p115">Pour créer un rôle ayant accès à un ensemble d’applets de commande non inclus dans l’un des rôles prédéfinis, ou à un ensemble de scripts ou de modules, vous devez encore une fois commencer par utiliser l’un des rôles prédéfinis comme modèle. Notez que les scripts et les modules que les rôles sont tenus d’exécuter doivent être stockés aux emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="571d9-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="571d9-196">Le chemin d’accès au module Lync, par défaut C : \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ modules \\ Lync</span><span class="sxs-lookup"><span data-stu-id="571d9-196">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="571d9-197">Le chemin d’accès au script utilisateur, par défaut C : \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ Adminscripts</span><span class="sxs-lookup"><span data-stu-id="571d9-197">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="571d9-198">Pour créer un rôle, vous devez utiliser l’applet de commande **New-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="571d9-198">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="571d9-199">Avant d’exécuter **New-CsAdminRole**, vous devez d’abord créer le groupe de sécurité universel sous-jacent qui sera associé à ce rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-199">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="571d9-200">Les applets de commande suivantes servent d’exemple pour la création d’un rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-200">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="571d9-201">Ils créent un nouveau type de rôle appelé `MyHelpDeskScriptRole` .</span><span class="sxs-lookup"><span data-stu-id="571d9-201">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="571d9-202">Ce nouveau rôle offre les mêmes capacités que le rôle prédéfini CsHelpDesk avec en outre la possibilité d’exécuter les fonctions d’un script nommé « testscript ».</span><span class="sxs-lookup"><span data-stu-id="571d9-202">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="571d9-203">Pour que cette applet de commande fonctionne, vous devez d’abord avoir créé le groupe de sécurité universel MyHelpDeskScriptRole.</span><span class="sxs-lookup"><span data-stu-id="571d9-203">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="571d9-204">Après avoir exécuté cette applet de commande, vous pouvez directement affecter des utilisateurs à ce rôle (dans ce cas, ils ont une étendue globale) ou créer un rôle inclus dans une étendue basé sur ce rôle, comme expliqué dans Création d’un rôle inclus dans une étendue, plus haut dans ce document.</span><span class="sxs-lookup"><span data-stu-id="571d9-204">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="571d9-205">Affectation de rôles aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="571d9-205">Assigning Roles to Users</span></span>

<span data-ttu-id="571d9-206">Chaque rôle Lync Server est associé à un groupe de sécurité universel Active Directory sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="571d9-206">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="571d9-207">Tous les utilisateurs que vous ajoutez au groupe sous-jacent héritent des capacités de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-207">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="571d9-208">Les exemples des sections précédentes ont créé un nouveau rôle et attribué un groupe de sécurité universel existant au nouveau rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-208">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="571d9-209">Pour affecter un rôle existant à un ou plusieurs utilisateurs, ajoutez ces utilisateurs au groupe associé au rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-209">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="571d9-210">Vous pouvez ajouter des utilisateurs individuels et des groupes de sécurité universels à ces groupes.</span><span class="sxs-lookup"><span data-stu-id="571d9-210">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="571d9-211">Par exemple, le rôle **CsAdministrator** est automatiquement accordé au groupe de sécurité universel **administrateurs CS** dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="571d9-211">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="571d9-212">Ce groupe de sécurité universel est créé dans Active Directory lorsque vous déployez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="571d9-212">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="571d9-213">Pour accorder ce privilège à un utilisateur ou à un groupe, vous pouvez simplement l’ajouter au groupe **CS Administrators**.</span><span class="sxs-lookup"><span data-stu-id="571d9-213">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="571d9-214">Un utilisateur peut se voir affecter plusieurs rôles RBAC en étant ajouté aux groupes Active Directory sous-jacents qui correspondent à chaque rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-214">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="571d9-215">Veuillez noter que lorsque vous créez un rôle, les utilisateurs qui sont par la suite ajoutés au groupe Active Directory sous-jacent sont dotés des capacités de ce rôle</span><span class="sxs-lookup"><span data-stu-id="571d9-215">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="571d9-216">Modification des capacités d’un rôle</span><span class="sxs-lookup"><span data-stu-id="571d9-216">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="571d9-p121">Vous pouvez modifier la liste des applets de commande et des scripts qu’un rôle peut exécuter. Dans le cas des rôles personnalisés, vous pouvez modifier à la fois les applets de commande et les scripts. Dans le cas des rôles prédéfinis, vous pouvez modifier uniquement les scripts. Chaque applet de commande que vous tapez peut ajouter, supprimer ou remplacer des applets de commande ou des scripts.</span><span class="sxs-lookup"><span data-stu-id="571d9-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="571d9-220">Pour modifier un rôle, utilisez l’applet de commande **Set-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="571d9-220">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="571d9-221">L’applet de commande suivante supprime un script du rôle.</span><span class="sxs-lookup"><span data-stu-id="571d9-221">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="571d9-222">Planification pour RBAC</span><span class="sxs-lookup"><span data-stu-id="571d9-222">Planning for RBAC</span></span>

<span data-ttu-id="571d9-223">Pour chaque personne qui doit disposer de n’importe quel type de droits d’administration pour votre déploiement Lync Server, déterminez exactement les tâches qu’elles doivent effectuer, puis affectez-les aux rôles avec le privilège et l’étendue les moins appropriés pour leur travail.</span><span class="sxs-lookup"><span data-stu-id="571d9-223">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="571d9-224">Si nécessaire, vous pouvez utiliser l’applet de commande **Set-CsAdminRole** pour créer un rôle associée aux seules applets de commande nécessaires à l’exécution des tâches de cette personne.</span><span class="sxs-lookup"><span data-stu-id="571d9-224">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="571d9-p124">Les utilisateurs qui disposent du rôle CsAdministrator peuvent créer tous les types de rôles, y compris les rôles basés sur CsAdministrator, et leur affecter des utilisateurs. La meilleure pratique consiste à affecter le rôle CsAdministrator à un très petit groupe d’utilisateurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="571d9-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

