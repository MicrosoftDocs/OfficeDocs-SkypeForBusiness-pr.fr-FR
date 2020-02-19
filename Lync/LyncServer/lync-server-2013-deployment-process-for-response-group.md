---
title: 'Lync Server 2013 : processus de déploiement du groupe Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c87519c26a0804ad6c9f275d2e12c4a26988d29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="0197d-102">Processus de déploiement du groupe Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0197d-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0197d-103">_**Dernière modification de la rubrique :** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="0197d-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="0197d-104">Cette section fournit une vue d’ensemble des phases et des étapes nécessaires au déploiement de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="0197d-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="0197d-105">Processus de déploiement de Response Group</span><span class="sxs-lookup"><span data-stu-id="0197d-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0197d-106">Phase</span><span class="sxs-lookup"><span data-stu-id="0197d-106">Phase</span></span></th>
<th><span data-ttu-id="0197d-107">Étapes</span><span class="sxs-lookup"><span data-stu-id="0197d-107">Steps</span></span></th>
<th><span data-ttu-id="0197d-108">Autorisations</span><span class="sxs-lookup"><span data-stu-id="0197d-108">Permissions</span></span></th>
<th><span data-ttu-id="0197d-109">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="0197d-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0197d-110">Installer l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="0197d-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="0197d-111">L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0197d-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="0197d-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0197d-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0197d-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement de voix entreprise dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0197d-114">Installer les composants de Response Group</span><span class="sxs-lookup"><span data-stu-id="0197d-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="0197d-115">Applets de commande Lync Server, le panneau de configuration Lync Server, l’outil de configuration Response Group, la console de connexion et de déconnexion des agents et le service Web du client Response Group sont installés dans le cadre des services Web.</span><span class="sxs-lookup"><span data-stu-id="0197d-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="0197d-116">Les services Web sont installés lorsque vous déployez un pool Enterprise Edition ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="0197d-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="0197d-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0197d-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0197d-118"><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Microsoft Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0197d-119">Activer les utilisateurs pour Lync 2013 et voix entreprise</span><span class="sxs-lookup"><span data-stu-id="0197d-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="0197d-120">Autorisez les utilisateurs qui seront des agents pour Lync Server et voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0197d-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="0197d-121">Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="0197d-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="0197d-122">En règle générale, les utilisateurs sont activés pour Lync Server pendant le déploiement du serveur Enterprise Edition ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0197d-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="0197d-123">Les utilisateurs sont activés pour voix entreprise pendant le déploiement de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0197d-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="0197d-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0197d-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="0197d-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="0197d-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0197d-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0197d-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Activer les utilisateurs pour voix entreprise dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0197d-129">Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail</span><span class="sxs-lookup"><span data-stu-id="0197d-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0197d-130">Utilisez le panneau de configuration Lync Server ou Lync Server Management Shell pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0197d-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="0197d-131">Créez et configurez des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="0197d-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="0197d-132">Créez et configurez des files d’attente.</span><span class="sxs-lookup"><span data-stu-id="0197d-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="0197d-133">Si vous le souhaitez, utilisez Lync Server Management Shell pour créer des heures ouvrées et des congés d’un groupe Response Group prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="0197d-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="0197d-134">Utilisez l’outil de configuration Response Group ou Lync Server Management Shell pour créer des flux de travail (groupes de recherche ou flux d’appels de réponse vocale interactive), y compris les heures ouvrées et les congés des groupes Response Group personnalisés.</span><span class="sxs-lookup"><span data-stu-id="0197d-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0197d-135">Vous pouvez accéder à l’outil de configuration Response Group via le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0197d-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="0197d-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0197d-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0197d-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="0197d-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0197d-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0197d-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="0197d-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="0197d-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="0197d-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Créer des groupes d’agents Response Group Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0197d-143"><a href="lync-server-2013-create-response-group-queues.md">Créer des files d’attente Response Group dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0197d-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Module Définition des heures d’ouverture d’un groupe Response Group dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0197d-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Module Définir les groupes de congés Response Group dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0197d-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Création ou modification d’un flux de travail dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0197d-147">(Facultatif) Personnaliser les paramètres au niveau de l’application</span><span class="sxs-lookup"><span data-stu-id="0197d-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="0197d-148">Utilisez Lync Server Management Shell pour personnaliser la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de l’appel d’invocation d’un agent et la configuration du contexte de l’appel.</span><span class="sxs-lookup"><span data-stu-id="0197d-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="0197d-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0197d-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0197d-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="0197d-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0197d-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0197d-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0197d-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestion des paramètres de groupe Response Group au niveau de l’application dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0197d-155">(Facultatif) Déléguer la gestion des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="0197d-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="0197d-156">Attribuez aux utilisateurs le rôle CsResponseGroupManager pour déléguer la configuration des groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="0197d-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="0197d-157">Les responsables des groupes Response Group peuvent ensuite configurer les groupes Response Group qui leur sont attribués.</span><span class="sxs-lookup"><span data-stu-id="0197d-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="0197d-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0197d-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0197d-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="0197d-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0197d-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0197d-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0197d-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0197d-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0197d-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0197d-164">Vérifier votre déploiement Response Group</span><span class="sxs-lookup"><span data-stu-id="0197d-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="0197d-165">Testez la réponse aux appels des workflows de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="0197d-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

