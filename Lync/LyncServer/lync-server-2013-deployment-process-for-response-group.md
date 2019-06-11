---
title: 'Lync Server 2013: processus de déploiement pour Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="2f927-102">Processus de déploiement pour Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f927-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f927-103">_**Dernière modification de la rubrique:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="2f927-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="2f927-104">Cette section fournit une vue d’ensemble des phases et étapes du déploiement de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="2f927-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="2f927-105">Procédure de déploiement du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="2f927-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f927-106">Phase</span><span class="sxs-lookup"><span data-stu-id="2f927-106">Phase</span></span></th>
<th><span data-ttu-id="2f927-107">Étapes</span><span class="sxs-lookup"><span data-stu-id="2f927-107">Steps</span></span></th>
<th><span data-ttu-id="2f927-108">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2f927-108">Permissions</span></span></th>
<th><span data-ttu-id="2f927-109">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="2f927-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f927-110">Installer l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="2f927-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="2f927-111">L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2f927-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="2f927-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2f927-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2f927-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement d’Enterprise Voice dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f927-114">Installer des composants pour Response Group</span><span class="sxs-lookup"><span data-stu-id="2f927-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="2f927-115">Les applets de commande Lync Server, le panneau de configuration de Lync Server, l’outil de configuration de Response Group, l’outil de connexion des agents et la console de connexion et le service Web du client de groupe de réponse sont installés dans le cadre de services Web.</span><span class="sxs-lookup"><span data-stu-id="2f927-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="2f927-116">Les services Web sont installés lorsque vous déployez un pool Enterprise Edition ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="2f927-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="2f927-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2f927-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2f927-118"><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f927-119">Activer les utilisateurs pour Lync 2013 et voix entreprise</span><span class="sxs-lookup"><span data-stu-id="2f927-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="2f927-120">Activez les utilisateurs qui seront agents de Lync Server et de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="2f927-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="2f927-121">Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="2f927-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="2f927-122">En général, les utilisateurs sont activés pour Lync Server lors du déploiement Enterprise Edition ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="2f927-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="2f927-123">Les utilisateurs sont activés pour voix entreprise pendant le déploiement de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="2f927-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="2f927-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2f927-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="2f927-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="2f927-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2f927-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2f927-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f927-129">Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail</span><span class="sxs-lookup"><span data-stu-id="2f927-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2f927-130">Utilisez le panneau de configuration de Lync Server ou Lync Server Management Shell pour effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="2f927-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="2f927-131">Créez et configurez des groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="2f927-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="2f927-132">Créez et configurez des files d’attente.</span><span class="sxs-lookup"><span data-stu-id="2f927-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="2f927-133">Vous pouvez également utiliser Lync Server Management Shell pour créer des heures de travail et des jours fériés prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="2f927-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="2f927-134">Utilisez l’outil de configuration de Response Group ou Lync Server Management Shell pour créer des flux de travail (groupes de recherche ou flux de réponse vocale interactifs), y compris des heures et des jours fériés de groupe de réponse personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2f927-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2f927-135">Vous pouvez accéder à l’outil de configuration de Response Group par le biais du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f927-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="2f927-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2f927-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2f927-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="2f927-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2f927-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2f927-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="2f927-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="2f927-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="2f927-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Création des groupes d’agents Response Group Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2f927-143"><a href="lync-server-2013-create-response-group-queues.md">Création des files d’attente Response Group dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2f927-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Facultatif Définir les heures d’activité du groupe de réponses dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2f927-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Facultatif Définir des jeux de vacances de groupe de réponse dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2f927-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Créer ou modifier un flux de travail dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f927-147">(Facultatif) Personnaliser les paramètres au niveau de l’application</span><span class="sxs-lookup"><span data-stu-id="2f927-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="2f927-148">Utilisez Lync Server Management Shell pour personnaliser la configuration par défaut de Music-Holding, le fichier audio de musique par défaut, la période de grâce aux retours de l’agent et la configuration du contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="2f927-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="2f927-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2f927-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2f927-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="2f927-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2f927-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2f927-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2f927-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gestion des paramètres du groupe de réponses au niveau de l’application dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f927-155">(Facultatif) Déléguer la gestion des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="2f927-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="2f927-156">Affectez aux utilisateurs le rôle CsResponseGroupManager pour déléguer la configuration de Response groups.</span><span class="sxs-lookup"><span data-stu-id="2f927-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="2f927-157">Les responsables de groupe de réponse peuvent alors configurer les groupes de réponse qui leur sont attribués.</span><span class="sxs-lookup"><span data-stu-id="2f927-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="2f927-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2f927-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2f927-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="2f927-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2f927-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2f927-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f927-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2f927-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f927-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f927-164">Vérifier votre déploiement Response Group</span><span class="sxs-lookup"><span data-stu-id="2f927-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="2f927-165">Testez la réponse aux appels des flux de travail de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="2f927-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

