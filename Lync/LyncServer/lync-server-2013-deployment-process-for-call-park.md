---
title: 'Lync Server 2013: processus de déploiement pour le parc d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab02c8cfbf0f1ca71aff85c8a71a2bcb20ee3fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="c2cc5-102">Processus de déploiement du parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2cc5-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2cc5-103">_**Dernière modification de la rubrique:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c2cc5-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c2cc5-104">Cette section fournit une vue d’ensemble des étapes de déploiement de l’application de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="c2cc5-105">Vous devez déployer Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="c2cc5-106">Les composants requis par le parc d’appels sont installés et activés lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="c2cc5-107">Procédure de déploiement du parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="c2cc5-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2cc5-108">Phase</span><span class="sxs-lookup"><span data-stu-id="c2cc5-108">Phase</span></span></th>
<th><span data-ttu-id="c2cc5-109">Étapes</span><span class="sxs-lookup"><span data-stu-id="c2cc5-109">Steps</span></span></th>
<th><span data-ttu-id="c2cc5-110">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="c2cc5-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="c2cc5-111">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="c2cc5-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2cc5-112">Configurer les plages d’orbites de parcage d’appel dans la table des orbites</span><span class="sxs-lookup"><span data-stu-id="c2cc5-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-113">Utilisez le panneau de configuration de Lync Server ou l’applet <strong>de commande New-CSCallParkOrbit</strong> pour créer les plages d’orbites dans la table de stationnement d’appel et associez-les au service d’application qui héberge l’application de stationnement d’appels.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c2cc5-p102">Pour une intégration transparente aux plans de numérotation existants, les plages d’orbites sont en général configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) comme numéros d’orbites dans la table des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="c2cc5-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c2cc5-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c2cc5-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Créer ou modifier une gamme de parc d’appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2cc5-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2cc5-121">Configuration des paramètres de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="c2cc5-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-122">Utilisez l’applet de cmdlet <strong>Set-CsCpsConfiguration</strong> pour configurer les paramètres du parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="c2cc5-123">Nous vous conseillons d’effectuer au moins une configuration de l’option <strong>OnTimeoutURI</strong> pour configurer la destination de secours à utiliser lorsqu’un appel parqué arrive à expiration. Vous pouvez également configurer les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="c2cc5-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="c2cc5-124">(Facultatif) <strong>EnableMusicOnHold</strong> pour activer ou désactiver l’attente musicale.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="c2cc5-125">(Facultatif) <strong>MaxCallPickupAttempts</strong> pour déterminer le nombre de fois qu’un appel parqué doit sonner de nouveau sur le téléphone de destination avant d’être transféré à l’URI (Uniform Resource Identifier) de remplacement.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="c2cc5-126">(Facultatif) <strong>CallPickupTimeoutThreshold</strong> pour déterminer le délai qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2cc5-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c2cc5-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c2cc5-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-131"><a href="lync-server-2013-configure-call-park-settings.md">Configurer les paramètres de parc d’appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2cc5-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2cc5-132">Si vous le souhaitez, personnalisez l’attente musicale</span><span class="sxs-lookup"><span data-stu-id="c2cc5-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-133">Si vous ne voulez pas utiliser l’attente musicale par défaut, personnalisez et téléchargez un fichier audio à l’aide de l’applet de commande <strong>Set-CsCallParkServiceMusicOnHoldFile</strong>.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c2cc5-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c2cc5-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personnaliser le parc d’appels en attente dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2cc5-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2cc5-139">Configurer la stratégie vocale pour activer le parc d’appels pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c2cc5-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-140">Utilisez le panneau de configuration de Lync Server ou l’applet de commande <strong>Set-CSVoicePolicy</strong> avec l’option <strong>EnableCallPark</strong> pour activer le parc d’appels pour les utilisateurs dans la stratégie vocale.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c2cc5-141">Par défaut, le parc d’appels est désactivé pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="c2cc5-142">Si vous disposez de plusieurs stratégies de voix, définissez la propriété EnableCallPark pour toutes les stratégies de voix et pas seulement pour la stratégie par défaut.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="c2cc5-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c2cc5-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c2cc5-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-147"><a href="lync-server-2013-enable-call-park-for-users.md">Activer le parc d’appels pour les utilisateurs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2cc5-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2cc5-148">Vérification des règles de normalisation pour le parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="c2cc5-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-p104">Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez que les règles de normalisation ne comportent aucune plage d’orbites. Si nécessaire, créez des règles de normalisation supplémentaires pour empêcher la normalisation des orbites.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c2cc5-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c2cc5-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c2cc5-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c2cc5-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Vérifier les règles de normalisation du parc d’appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2cc5-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2cc5-157">Vérifier le déploiement de votre parc d’appels</span><span class="sxs-lookup"><span data-stu-id="c2cc5-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="c2cc5-158">Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="c2cc5-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c2cc5-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Facultatif Vérifier le déploiement du parc d’appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2cc5-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

