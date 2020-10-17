---
title: 'Lync Server 2013 : processus de déploiement de la prise d’appel de groupe'
description: 'Lync Server 2013 : processus de déploiement de la prise d’appel de groupe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a01409b257c685ae71dfdb13074f2d8ea590cd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552490"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="0eb98-103">Processus de déploiement de la prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0eb98-103">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eb98-104">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0eb98-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0eb98-105">Cette section fournit une vue d’ensemble des étapes nécessaires au déploiement de la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="0eb98-105">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="0eb98-106">Vous devez déployer Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="0eb98-106">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="0eb98-107">Les composants requis par la prise d’appel de groupe sont installés et activés lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0eb98-107">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="0eb98-108">Processus de déploiement de la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="0eb98-108">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0eb98-109">Phase</span><span class="sxs-lookup"><span data-stu-id="0eb98-109">Phase</span></span></th>
<th><span data-ttu-id="0eb98-110">Étapes</span><span class="sxs-lookup"><span data-stu-id="0eb98-110">Steps</span></span></th>
<th><span data-ttu-id="0eb98-111">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="0eb98-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="0eb98-112">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="0eb98-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0eb98-113">Activer l’outil de kit de ressources SEFAUtil dans la topologie</span><span class="sxs-lookup"><span data-stu-id="0eb98-113">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0eb98-114">Utilisez la cmdlet <strong>New-CsTrustedApplicationPool</strong> pour créer un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="0eb98-114">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="0eb98-115">Utilisez la cmdlet <strong>New-CsTrustedApplication</strong> pour spécifier l’outil SEFAUtil en tant qu’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="0eb98-115">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="0eb98-116">Exécutez la cmdlet <strong>Enable-CsTopology</strong> pour activer la topologie.</span><span class="sxs-lookup"><span data-stu-id="0eb98-116">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="0eb98-117">Installez les outils du kit de ressources sur un serveur frontal qui se trouve dans le pool d’applications approuvées créé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="0eb98-117">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="0eb98-118">Vérifiez que SEFAUtil s’exécute correctement en l’exécutant pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="0eb98-118">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0eb98-119">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0eb98-119">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0eb98-120"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Déployer l’outil SEFAUtil dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0eb98-120"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb98-121">Configuration des plages de numéros de prise d’appel dans la table des orbites de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="0eb98-121">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="0eb98-122">Utilisez la cmdlet <strong>New-CSCallParkOrbit</strong> pour créer des plages de numéros de prise d’appel dans la table des orbites de parcage d’appel et affecter les plages de prise d’appel au type GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="0eb98-122">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0eb98-123">Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="0eb98-123">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="0eb98-124">Les plages de numéros de prise d’appel de groupe ne sont pas disponibles dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0eb98-124">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="0eb98-125">Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont généralement configurées en tant que bloc d’extensions virtuelles.</span><span class="sxs-lookup"><span data-stu-id="0eb98-125">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="0eb98-126">L’affectation de numéros DID (appels directs vers l’intérieur) sous forme de numéros de plage dans la table des orbites de parcage d’appel n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0eb98-126">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="0eb98-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0eb98-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0eb98-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0eb98-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0eb98-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0eb98-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0eb98-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0eb98-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0eb98-131"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurer les numéros de groupe de prise d’appel dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0eb98-131"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0eb98-132">Affecter un numéro de prise d’appel aux utilisateurs et activer la prise d’appel de groupe pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0eb98-132">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="0eb98-133">Utilisez le paramètre/enablegrouppickup dans l’outil de kit de ressources SEFAUtil pour activer la prise d’appel de groupe et affecter un numéro de prise d’appel pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0eb98-133">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0eb98-134"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe</a></span><span class="sxs-lookup"><span data-stu-id="0eb98-134"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb98-135">Avertir les utilisateurs du numéro de prise d’appel et de tout autre nombre d’intérêt</span><span class="sxs-lookup"><span data-stu-id="0eb98-135">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="0eb98-136">Étant donné qu’un utilisateur peut récupérer un appel passé à un utilisateur de la prise d’appel de groupe, les utilisateurs peuvent souhaiter surveiller plusieurs groupes.</span><span class="sxs-lookup"><span data-stu-id="0eb98-136">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0eb98-137"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communiquer des attributions de prise d’appel de groupe aux utilisateurs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0eb98-137"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0eb98-138">Vérifier le déploiement de la prise d’appel de groupe</span><span class="sxs-lookup"><span data-stu-id="0eb98-138">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="0eb98-139">Testez le placement et la récupération des appels pour vous assurer que votre configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="0eb98-139">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="0eb98-140"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Module Vérifier le déploiement de la prise d’appel de groupe dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0eb98-140"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

