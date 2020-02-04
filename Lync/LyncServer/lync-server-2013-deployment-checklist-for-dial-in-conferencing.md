---
title: Liste de vérification du déploiement pour la conférence rendez-vous dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf496dcb24c021246bfbb6e7a5ef7b3a3a5acc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="66030-102">Liste de vérification du déploiement pour la conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66030-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66030-103">_**Dernière modification de la rubrique :** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="66030-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="66030-104">Les composants requis pour les conférences rendez-vous sont déployés lorsque vous déployez la charge de travail de conférence.</span><span class="sxs-lookup"><span data-stu-id="66030-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="66030-105">Pour pouvoir configurer les conférences rendez-vous, vous devez déployer l’entreprise voix ou un serveur de médiation et une passerelle de réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="66030-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="66030-106">Toutes les étapes décrites dans le tableau ci-dessous doivent être effectuées pour que les utilisateurs puissent se connecter à partir du RTC pour participer à une conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="66030-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66030-107">Si vous effectuez une migration à partir d’Office Communications Server 2007 R2, vous devez appliquer les mises à jour les plus récentes à votre environnement Office Communications Server 2007 R2 avant de déployer la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66030-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="66030-108">Processus de déploiement de conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="66030-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66030-109">Phase</span><span class="sxs-lookup"><span data-stu-id="66030-109">Phase</span></span></th>
<th><span data-ttu-id="66030-110">Étapes</span><span class="sxs-lookup"><span data-stu-id="66030-110">Steps</span></span></th>
<th><span data-ttu-id="66030-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="66030-111">Permissions</span></span></th>
<th><span data-ttu-id="66030-112">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="66030-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66030-113"><strong>Créer une topologie incluant la charge de travail de conférence, y compris un serveur de médiation et une passerelle RTC, et déployer le pool frontal ou le serveur Standard Edition Server</strong></span><span class="sxs-lookup"><span data-stu-id="66030-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="66030-114">Exécutez le générateur de topologie pour configurer votre topologie.</span><span class="sxs-lookup"><span data-stu-id="66030-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="66030-115">Lors de la configuration de la topologie, sélectionnez l’option de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66030-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="66030-116">Publiez la topologie et déployez le pool frontal ou le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="66030-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="66030-117">Le cas échéant, créez un serveur de médiation autonome et associez-le à une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="66030-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="66030-118">Cette étape est requise uniquement si vous n’avez pas déployé Enterprise Voice et que vous n’collocate pas le serveur de médiation avec l’Enterprise EditionFront end Server ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="66030-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="66030-119">Si vous déployez Enterprise Voice, vous installez et configurez les serveurs de médiation et les passerelles RTC dans le cadre du déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="66030-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="66030-120">Si vous collocate le serveur de médiation, vous installez et configurez le serveur de médiation dans le cadre du déploiement de la liste frontale ou du déploiement du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="66030-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="66030-121">DomainAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-121">Domain Admins</span></span></p>
<p><span data-ttu-id="66030-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-123">Administrateur</span><span class="sxs-lookup"><span data-stu-id="66030-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66030-124"><a href="lync-server-2013-deploying-lync-server.md">Déploiement de Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="66030-125">Pour créer un pool de serveurs de médiation autonome : <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">déploiement de serveurs de médiation et définition d’homologues dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66030-126"><strong>Configure dial plans</strong></span><span class="sxs-lookup"><span data-stu-id="66030-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-127">Un plan de numérotation est un ensemble de règles de normalisation des numéros de téléphone qui convertit des numéros de téléphone composés depuis un emplacement spécifique à un format standard (E.164) unique à des fins d’autorisation téléphonique et de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="66030-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="66030-128">Le même numéro de téléphone composé depuis différents emplacements peut, en fonction des plans de numérotation concernés, être résolu en différents numéros E.164, conformément à chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="66030-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="66030-129">Si vous déployez Enterprise Voice, vous configurez des plans de numérotation dans le cadre de ce déploiement et vous devez vous assurer que les plans de numérotation sont également compatibles avec les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66030-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="66030-130">Si vous ne déployez pas Enterprise Voice, vous devez configurer des plans de numérotation pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66030-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="66030-131">Utilisez le panneau de configuration de Lync Server 2013 ou Lync Server Management Shell pour configurer les plans de numérotation comme suit :</span><span class="sxs-lookup"><span data-stu-id="66030-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="66030-132">Créez un ou plusieurs plans de numérotation pour le routage des numéros de téléphone d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66030-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="66030-p105">Attribuez un plan de numérotation par défaut à chaque pool. Définissez la <strong>Région de la conférence rendez-vous</strong> sur l’emplacement géographique auquel le plan de numérotation s’applique. La région associe le plan de numérotation aux numéros d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66030-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="66030-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="66030-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66030-141"><strong>Vérifier qu’une région a été affectée aux plans de numérotation</strong></span><span class="sxs-lookup"><span data-stu-id="66030-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-142">Exécutez les commandes d’applet <strong>Get-CsDialPlan</strong> et <strong>Set-CsDialPlan</strong> pour vous assurer qu’une région a été affectée à tous les plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="66030-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="66030-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="66030-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Vérifier que le plan de numérotation Lync Server 2013 a des régions affectées</a></span><span class="sxs-lookup"><span data-stu-id="66030-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66030-148"><strong>(Facultatif) Vérifier ou modifier les conditions relatives au code confidentiel de l’utilisateur (PIN).</strong></span><span class="sxs-lookup"><span data-stu-id="66030-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-149">Utilisez le panneau de configuration de Lync Server 2013 ou Lync Server Management Shell pour afficher ou modifier la <strong>stratégie de code confidentiel</strong>de conférence.</span><span class="sxs-lookup"><span data-stu-id="66030-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="66030-150">Vous pouvez spécifier une longueur de code confidentiel minimale, un nombre maximal de tentatives d’ouverture de session, une expiration du code confidentiel et si des modèles communs sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="66030-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="66030-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Facultatif) Vérification des paramètres de stratégie de code confidentiel dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66030-155"><strong>Configurer une stratégie de conférence pour prendre en charge la conférence rendez-vous</strong></span><span class="sxs-lookup"><span data-stu-id="66030-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-156">Utilisez le panneau de configuration de Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de <strong>stratégie de conférence</strong> .</span><span class="sxs-lookup"><span data-stu-id="66030-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="66030-157">Spécifiez si :</span><span class="sxs-lookup"><span data-stu-id="66030-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="66030-158">l’appel de conférence RTC est activé ;</span><span class="sxs-lookup"><span data-stu-id="66030-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="66030-159">les utilisateurs peuvent inviter des participants anonymes ;</span><span class="sxs-lookup"><span data-stu-id="66030-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="66030-p108">des utilisateurs non authentifiés peuvent participer à une conférence en utilisant un appel sortant. Avec cette fonctionnalité, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="66030-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66030-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configuration de la stratégie de conférence rendez-vous dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66030-166"><strong>Configure dial-in access numbers</strong></span><span class="sxs-lookup"><span data-stu-id="66030-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-167">Utilisez le panneau de configuration de Lync Server 2013 ou Lync Server Management Shell pour configurer les numéros d’accès rendez-vous que les utilisateurs appellent pour appeler une conférence, et indiquez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.</span><span class="sxs-lookup"><span data-stu-id="66030-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="66030-168">Les trois premiers numéros d’accès pour la région spécifiée par le plan de numérotation de l’organisateur sont inclus dans l’invitation à la conférence.</span><span class="sxs-lookup"><span data-stu-id="66030-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="66030-169">Tous les numéros d’accès sont disponibles sur la page des paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66030-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="66030-170">Après avoir créé des numéros d’accès rendez-vous, vous pouvez utiliser l’applet de connexion <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> pour modifier le nom d’affichage des objets de contact Active Directory de sorte que les utilisateurs puissent facilement identifier le numéro d’accès approprié.</span><span class="sxs-lookup"><span data-stu-id="66030-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="66030-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configuration des numéros d’accès aux conférences rendez-vous dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66030-175"><strong>(Facultatif) Vérifier les paramètres de conférence rendez-vous</strong></span><span class="sxs-lookup"><span data-stu-id="66030-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-176">Utilisez l’applet de commande <strong>Get-CsDialinConferencingAccessNumber</strong> pour rechercher des plans de numérotation présentant une région de conférence rendez-vous qui n’est pas utilisée par un numéro d’accès et les numéros d’accès sans affectation de région.</span><span class="sxs-lookup"><span data-stu-id="66030-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="66030-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="66030-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="66030-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="66030-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="66030-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Facultatif) Vérification des paramètres de conférence rendez-vous dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66030-183"><strong>(Facultatif) Modifier le mappage des clés des commandes DTMF</strong></span><span class="sxs-lookup"><span data-stu-id="66030-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-184">Utilisez l’applet de commande <strong>Set-CsDialinConferencingDtmfConfiguration</strong> pour modifier les touches utilisées pour les commandes de numérotation à deux tonalités (DTMF), que les participants peuvent utiliser pour contrôler les paramètres de la Conférence (par exemple, activer et désactiver le son ou verrouiller et déverrouiller).</span><span class="sxs-lookup"><span data-stu-id="66030-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="66030-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Facultatif) Modification du mappage des clés des commandes DTMF dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66030-189"><strong>(Facultatif) Modifier le comportement des annonces d’entrée et de sortie d’une conférence</strong></span><span class="sxs-lookup"><span data-stu-id="66030-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-190">Utilisez l’applet de commande <strong>Set-CsDialinConferencingConfiguration</strong> pour modifier le mode de fonctionnement des annonces lorsque les participants accèdent ou quittent une conférence.</span><span class="sxs-lookup"><span data-stu-id="66030-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="66030-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Facultatif) Activation et désactivation des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66030-195"><strong>(Facultatif) Vérifier la conférence rendez-vous</strong></span><span class="sxs-lookup"><span data-stu-id="66030-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-196">Utilisez l’applet de commande <strong>Test-CsDialInConferencing</strong> pour tester le fonctionnement des numéros d’accès pour le pool spécifié.</span><span class="sxs-lookup"><span data-stu-id="66030-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="66030-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="66030-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Facultatif) Vérification de la conférence rendez-vous dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66030-201"><strong>Déploiement du complément de réunion en ligne pour Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="66030-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-202">Déployez le complément réunion en ligne pour Lync 2013 de sorte que les utilisateurs puissent programmer des conférences prenant en charge la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66030-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="66030-203">Le complément réunion en ligne pour Lync 2013 est installé automatiquement lorsque vous installez Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="66030-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="66030-204">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="66030-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="66030-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Déploiement du complément de réunion en ligne pour Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66030-206"><strong>Configuration des paramètres des comptes d’utilisateurs</strong></span><span class="sxs-lookup"><span data-stu-id="66030-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-207">Utilisez le panneau de configuration de Lync Server 2013 ou Lync Server Management Shell pour configurer l’URI de la <strong>ligne</strong> téléphonique en tant que numéro de téléphone normalisé unique (par exemple, tel : + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="66030-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="66030-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="66030-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="66030-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="66030-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="66030-211"><a href="lync-server-2013-configure-user-account-settings.md">Configuration des paramètres des comptes d’utilisateurs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66030-212">(Recommandé) Configurer des répertoires de conférence</span><span class="sxs-lookup"><span data-stu-id="66030-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="66030-213">Utilisez l’applet de commande <strong>New-CsConferenceDirectory</strong> pour créer un répertoire de conférence tous les 999 utilisateurs dans le pool.</span><span class="sxs-lookup"><span data-stu-id="66030-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="66030-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="66030-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Conditions requises pour les conférences rendez-vous dans Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(recommandé) créer des répertoires de conférences</a></span><span class="sxs-lookup"><span data-stu-id="66030-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66030-216"><strong>(Facultatif) Accueillir les utilisateurs à la conférence rendez-vous et définir le code confidentiel initial</strong></span><span class="sxs-lookup"><span data-stu-id="66030-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="66030-217">Utilisez le script <strong>Set-CsPinSendCAWelcomeMail</strong> pour définir les codes confidentiels initiaux des utilisateurs et envoyer un message de bienvenue qui contient le code confidentiel initial ainsi qu’un lien vers la page des paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66030-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="66030-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="66030-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="66030-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Facultatif) Accueil des utilisateurs dans les conférences rendez-vous dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="66030-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

