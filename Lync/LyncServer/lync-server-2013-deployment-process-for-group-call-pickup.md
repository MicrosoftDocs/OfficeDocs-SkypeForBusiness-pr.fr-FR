---
title: 'Lync Server 2013: processus de déploiement pour le prélèvement d’appels de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="7c2a9-102">Processus de déploiement pour l’enlèvement de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c2a9-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c2a9-103">_**Dernière modification de la rubrique:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="7c2a9-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="7c2a9-104">Cette section fournit une vue d’ensemble des étapes de déploiement d’un appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="7c2a9-105">Vous devez déployer Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer la cueillette d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="7c2a9-106">Les composants requis par la cueillette de groupe sont installés et activés lors du déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="7c2a9-107">Processus de déploiement de la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="7c2a9-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c2a9-108">Phase</span><span class="sxs-lookup"><span data-stu-id="7c2a9-108">Phase</span></span></th>
<th><span data-ttu-id="7c2a9-109">Étapes</span><span class="sxs-lookup"><span data-stu-id="7c2a9-109">Steps</span></span></th>
<th><span data-ttu-id="7c2a9-110">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="7c2a9-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="7c2a9-111">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="7c2a9-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c2a9-112">Activer l’outil Kit de ressources SEFAUtil dans la topologie</span><span class="sxs-lookup"><span data-stu-id="7c2a9-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7c2a9-113">Utilisez l’applet de commande <strong>New-CsTrustedApplicationPool</strong> pour créer un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="7c2a9-114">Utilisez l’applet de commande <strong>New-CsTrustedApplication</strong> pour spécifier l’outil SEFAUtil comme application approuvée.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="7c2a9-115">Exécutez l’applet de commande <strong>Enable-CsTopology</strong> pour activer la topologie.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="7c2a9-116">Installez les outils du kit de ressources sur un serveur frontal qui se trouve dans le pool d’applications approuvé créé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="7c2a9-117">Vérifiez que l’outil SEFAUtil fonctionne correctement en l’exécutant pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7c2a9-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7c2a9-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7c2a9-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7c2a9-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c2a9-120">Configurer les plages de numéros de prise d’appel dans la table des numéros d’appel parqué</span><span class="sxs-lookup"><span data-stu-id="7c2a9-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="7c2a9-121">Utilisez l’applet de nouvelle applet de <strong>nouveau-CSCallParkOrbit</strong> pour créer des plages de numéros de capture d’appel dans la table d’appel en orbite et attribuez-lui le type GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7c2a9-122">Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de capture d’appels de groupe dans la table de stationnement du parc.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="7c2a9-123">Les plages de numéros des numéros de téléphone ne sont pas disponibles dans le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="7c2a9-p103">Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont en général configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) comme numéros de plages dans la table des numéros d’appel parqué.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-p103">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="7c2a9-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7c2a9-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7c2a9-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c2a9-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="7c2a9-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c2a9-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="7c2a9-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7c2a9-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7c2a9-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurer des numéros de groupe de capture d’appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7c2a9-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c2a9-131">Affectation d’un numéro de capture d’appel aux utilisateurs et activation de la cueillette d’appel de groupe pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="7c2a9-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="7c2a9-132">Utilisez le paramètre/enablegrouppickup dans l’outil de gestion des ressources SEFAUtil pour activer le prélèvement d’appels de groupe et affecter un numéro de téléphone pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7c2a9-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe</a></span><span class="sxs-lookup"><span data-stu-id="7c2a9-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c2a9-134">Informer les utilisateurs du numéro de prise d’appel qui leur a été affecté et de tout autre numéro digne d’intérêt</span><span class="sxs-lookup"><span data-stu-id="7c2a9-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="7c2a9-135">Dans la mesure où les utilisateurs peuvent récupérer un appel passé à un utilisateur de groupe, les utilisateurs peuvent souhaiter surveiller plus d’un groupe.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7c2a9-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communiquer des attributions d’appels de groupe aux utilisateurs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7c2a9-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c2a9-137">Vérifier le déploiement d’un appel de groupe</span><span class="sxs-lookup"><span data-stu-id="7c2a9-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="7c2a9-138">Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="7c2a9-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="7c2a9-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Facultatif Vérifier le déploiement d’un appel de groupe dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7c2a9-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

