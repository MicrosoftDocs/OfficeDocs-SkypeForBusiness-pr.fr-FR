---
title: 'Lync Server 2013 : Autorisations et conditions prérequises pour la configuration de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="c20c1-102">Autorisations et conditions prérequises pour la configuration de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c20c1-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c20c1-103">_**Dernière modification de la rubrique:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c20c1-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c20c1-104">Response Group est une fonctionnalité de gestion des appels voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="c20c1-104">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="c20c1-105">Cette rubrique décrit ce que vous devez mettre en place avant de pouvoir configurer les informations d’identification et les autorisations d’administration dont vous avez besoin pour effectuer des tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="c20c1-105">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="c20c1-106">Cette section suppose que vous avez lu la documentation de planification liée au groupe réponse.</span><span class="sxs-lookup"><span data-stu-id="c20c1-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="c20c1-107">Pour plus d’informations, reportez-vous à [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c20c1-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="c20c1-108">Outils de configuration et rôles d’administration</span><span class="sxs-lookup"><span data-stu-id="c20c1-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="c20c1-109">Pour configurer Response Group, vous pouvez utiliser les outils d’administration suivants:</span><span class="sxs-lookup"><span data-stu-id="c20c1-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="c20c1-110">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="c20c1-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="c20c1-111">outil de configuration Response Group</span><span class="sxs-lookup"><span data-stu-id="c20c1-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="c20c1-112">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c20c1-112">Lync Server Management Shell</span></span>

<span data-ttu-id="c20c1-113">Pour configurer les groupes Response Group, vous devez être membre d’au moins l’un des rôles d’administrateur suivants :</span><span class="sxs-lookup"><span data-stu-id="c20c1-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20c1-114"><strong>Groupe de sécurité Active Directory (1)</strong></span><span class="sxs-lookup"><span data-stu-id="c20c1-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="c20c1-115">Création d’un flux de travail</span><span class="sxs-lookup"><span data-stu-id="c20c1-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="c20c1-116">Affectation d’un responsable</span><span class="sxs-lookup"><span data-stu-id="c20c1-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="c20c1-117">Création/Affectation des agents, des files d’attente</span><span class="sxs-lookup"><span data-stu-id="c20c1-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="c20c1-118">Création/Gestion des congés et des heures d’ouverture</span><span class="sxs-lookup"><span data-stu-id="c20c1-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="c20c1-119">Activation/Désactivation d’un flux de travail</span><span class="sxs-lookup"><span data-stu-id="c20c1-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="c20c1-120">Configuration d’un flux de travail (réponse vocale interactive ou groupe de recherche)</span><span class="sxs-lookup"><span data-stu-id="c20c1-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20c1-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="c20c1-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="c20c1-122">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-122">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-123">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-123">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-124">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-124">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-125">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-125">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-126">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-126">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-127">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c20c1-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="c20c1-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="c20c1-129">√(2)</span><span class="sxs-lookup"><span data-stu-id="c20c1-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-130">√(3)</span><span class="sxs-lookup"><span data-stu-id="c20c1-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-131">√(3)</span><span class="sxs-lookup"><span data-stu-id="c20c1-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-132">√(3)</span><span class="sxs-lookup"><span data-stu-id="c20c1-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-133">√(3)</span><span class="sxs-lookup"><span data-stu-id="c20c1-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20c1-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="c20c1-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="c20c1-135">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-135">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-136">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-136">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-137">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-137">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-138">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-138">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-139">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-139">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-140">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c20c1-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="c20c1-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="c20c1-142">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-142">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-143">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-143">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-144">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-144">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-145">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-145">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-146">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-146">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-147">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20c1-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="c20c1-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="c20c1-149">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-149">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-150">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-150">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-151">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-151">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-152">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-152">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-153">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-153">√</span></span></p></td>
<td><p><span data-ttu-id="c20c1-154">√</span><span class="sxs-lookup"><span data-stu-id="c20c1-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c20c1-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="c20c1-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="c20c1-156">√(4)</span><span class="sxs-lookup"><span data-stu-id="c20c1-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-157">√(4)</span><span class="sxs-lookup"><span data-stu-id="c20c1-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-158">√(4)</span><span class="sxs-lookup"><span data-stu-id="c20c1-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-159">√(4)</span><span class="sxs-lookup"><span data-stu-id="c20c1-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-160">√(4)</span><span class="sxs-lookup"><span data-stu-id="c20c1-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="c20c1-161">√(4)</span><span class="sxs-lookup"><span data-stu-id="c20c1-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c20c1-162"><STRONG>(1)</STRONG> un objet utilisateur des services de domaine Active Directory doit être membre du groupe de sécurité Active Directory spécifié.</span><span class="sxs-lookup"><span data-stu-id="c20c1-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="c20c1-163">Un administrateur ou membre du groupe Active Directory délégué disposant des autorisations appropriées pour ajouter des utilisateurs à un groupe de sécurité (par exemple, administrateur, opérateurs de compte) doit ajouter un objet utilisateur au groupe de sécurité ou au groupe de la liste de contrôle pour l’utilisateur. Utilisez les fonctions indiquées.</span><span class="sxs-lookup"><span data-stu-id="c20c1-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="c20c1-164"><STRONG>(2)</STRONG> uniquement pour les flux de travail attribués par le CsResponseGroupAdministrator à CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="c20c1-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="c20c1-165"><STRONG>(3)</STRONG> un responsable de groupe de réponse peut affecter un autre membre de CsResponseGroupManager à un flux de travail géré par le responsable actuel.</span><span class="sxs-lookup"><span data-stu-id="c20c1-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="c20c1-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator ne peut exécuter que des applets de action de type «Get» Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c20c1-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="c20c1-167">Conditions préalables à la configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="c20c1-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="c20c1-168">Response Group nécessite les composants suivants:</span><span class="sxs-lookup"><span data-stu-id="c20c1-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="c20c1-169">service d’application</span><span class="sxs-lookup"><span data-stu-id="c20c1-169">Application service</span></span>

  - <span data-ttu-id="c20c1-170">application Response Group</span><span class="sxs-lookup"><span data-stu-id="c20c1-170">Response Group application</span></span>

  - <span data-ttu-id="c20c1-171">Modules linguistiques</span><span class="sxs-lookup"><span data-stu-id="c20c1-171">Language packs</span></span>

  - <span data-ttu-id="c20c1-172">Magasin de fichiers (pour conserver les fichiers audio)</span><span class="sxs-lookup"><span data-stu-id="c20c1-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="c20c1-173">Services Web (comprend les outils de configuration de Response Group et la console de connexion et de connexion des agents)</span><span class="sxs-lookup"><span data-stu-id="c20c1-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="c20c1-174">Tous ces composants sont installés par défaut lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c20c1-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="c20c1-175">Vous devrez peut-être effectuer les tâches suivantes avant de configurer Response Group:</span><span class="sxs-lookup"><span data-stu-id="c20c1-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="c20c1-176">Activez les utilisateurs pour Lync Server 2013 et voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="c20c1-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="c20c1-177">Modification d’un fichier de configuration pour la conformité aux normes FIPS (Federal Information Processing Standard)</span><span class="sxs-lookup"><span data-stu-id="c20c1-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="c20c1-178">Modification du classement de base de données pour prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents</span><span class="sxs-lookup"><span data-stu-id="c20c1-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="c20c1-179">Activation des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c20c1-179">Enabling Users</span></span>

<span data-ttu-id="c20c1-180">La première étape de la configuration d’un groupe de réponse consiste à créer des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="c20c1-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="c20c1-181">Avant de créer un groupe d’agents, vous devez activer les utilisateurs qui seront agents pour le groupe de réponses pour Lync Server 2013 et voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="c20c1-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="c20c1-182">L’activation des utilisateurs pour Lync Server 2013 est généralement une étape du déploiement du serveur Enterprise Edition Server ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="c20c1-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="c20c1-183">Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, voir [désactiver ou réactiver un compte d’utilisateur pour Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="c20c1-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="c20c1-184">L’activation des utilisateurs pour voix entreprise est généralement une étape du déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="c20c1-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="c20c1-185">Pour plus d’informations, reportez-vous à [activer l’application voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="c20c1-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="c20c1-186">Conformité aux normes FIPS</span><span class="sxs-lookup"><span data-stu-id="c20c1-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="c20c1-187">Cette section ne vous concerne que si votre organisation doit se conformer aux normes FIPS (Federal Information Processing Standard).</span><span class="sxs-lookup"><span data-stu-id="c20c1-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="c20c1-188">Pour respecter les normes FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un autre algorithme de chiffrement une fois les services web installés.</span><span class="sxs-lookup"><span data-stu-id="c20c1-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="c20c1-189">Vous devez préciser qu’ASP.NET utilise l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour traiter les données d’état d’affichage.</span><span class="sxs-lookup"><span data-stu-id="c20c1-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="c20c1-190">Dans le cas d’une application de groupe de réponse, cette exigence s’applique à l’outil de configuration de Response Group et à la console de connexion et de connexion de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c20c1-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="c20c1-191">Pour plus d’informations sur cette configuration requise, voir l’article de la base de connaissances Microsoft 911722, «vous pouvez recevoir un message d’erreur lorsque vous accédez à des pages Web ASP.NET dont ViewState est activé après la mise [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)à niveau de ASP.net 1,1 vers ASP.NET 2,0» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c20c1-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="c20c1-192">Pour modifier le fichier Web.config, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c20c1-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="c20c1-193">Dans un éditeur de texte, comme Bloc-Notes, ouvrez le fichier d’application Web.config.</span><span class="sxs-lookup"><span data-stu-id="c20c1-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="c20c1-194">Dans le fichier Web. config, recherchez la `<system.web>` section.</span><span class="sxs-lookup"><span data-stu-id="c20c1-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="c20c1-195">Ajoutez la section `<machineKey>` suivante dans la `<system.web>` section:</span><span class="sxs-lookup"><span data-stu-id="c20c1-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="c20c1-196">Enregistrez le fichier Web.config.</span><span class="sxs-lookup"><span data-stu-id="c20c1-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="c20c1-197">Redémarrez le service Internet Information Services (IIS) en exécutant la commande suivante à l’invite de commandes:</span><span class="sxs-lookup"><span data-stu-id="c20c1-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="c20c1-198">Prise en charge des caractères Yi, Meng et Zang</span><span class="sxs-lookup"><span data-stu-id="c20c1-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="c20c1-199">Cette section ne vous concerne que si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.</span><span class="sxs-lookup"><span data-stu-id="c20c1-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c20c1-200">Pour plus d’informations sur les caractères Yi, Meng et Zang et pourquoi ils peuvent être importants pour votre déploiement, voir les informations sur les jeux <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>de caractères GB18030.</span><span class="sxs-lookup"><span data-stu-id="c20c1-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="c20c1-p106">Pour assurer une prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux ci-dessous dans chaque base de données Rgsconfig :</span><span class="sxs-lookup"><span data-stu-id="c20c1-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="c20c1-203">dbo.AgentGroups</span><span class="sxs-lookup"><span data-stu-id="c20c1-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="c20c1-204">dbo.BusinessHours</span><span class="sxs-lookup"><span data-stu-id="c20c1-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="c20c1-205">dbo.HolidaySets</span><span class="sxs-lookup"><span data-stu-id="c20c1-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="c20c1-206">dbo.Queues</span><span class="sxs-lookup"><span data-stu-id="c20c1-206">dbo.Queues</span></span>

  - <span data-ttu-id="c20c1-207">dbo.Workflows</span><span class="sxs-lookup"><span data-stu-id="c20c1-207">dbo.Workflows</span></span>

<span data-ttu-id="c20c1-208">Pour SQL Server 2008 R2 et SQL Server 2012, utilisez le classement\_Latin\_général 100 (sensible aux lettres).</span><span class="sxs-lookup"><span data-stu-id="c20c1-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="c20c1-209">Si vous utilisez ce classement, certains noms d’objet ne dépendent pas des minuscules/majuscules.</span><span class="sxs-lookup"><span data-stu-id="c20c1-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="c20c1-210">Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c20c1-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="c20c1-211">Pour plus d’informations sur l’utilisation de cet outil, voir utilisation de [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c20c1-211">For details about using this tool, see "Using SQL Server Management Studio" at [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="c20c1-212">Pour modifier le classement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c20c1-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="c20c1-213">Assurez-vous que SQL Server Management Studio est configuré de manière à autoriser les modifications nécessaires à la recréation des tables.</span><span class="sxs-lookup"><span data-stu-id="c20c1-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="c20c1-214">Pour plus d’informations, consultez la boîte de dialogue «Enregistrer (non [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)autorisé)» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c20c1-214">For details, see "Save (Not Permitted) Dialog Box" at [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="c20c1-215">Pour plus d’informations sur la définition d’un assemblage de colonnes, voir la section «Procédure: définir l’assemblage de colonnes ( [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)Visual Database Tools)».</span><span class="sxs-lookup"><span data-stu-id="c20c1-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="c20c1-216">À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="c20c1-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="c20c1-217">Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table, puis cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c20c1-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="c20c1-218">Modifiez le classement de la colonne **Nom** et enregistrez la table.</span><span class="sxs-lookup"><span data-stu-id="c20c1-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

