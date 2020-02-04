---
title: 'Lync Server 2013 : processus de déploiement pour le prélèvement d’appels de groupe'
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
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Processus de déploiement pour l’enlèvement de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Cette section fournit une vue d’ensemble des étapes de déploiement d’un appel de groupe. Vous devez déployer Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer la cueillette d’appel de groupe. Les composants requis par la cueillette de groupe sont installés et activés lors du déploiement d’Enterprise Voice.

### <a name="group-call-pickup-deployment-process"></a>Processus de déploiement de la prise d’appel de groupe

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Groupes et rôles requis</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Activer l’outil Kit de ressources SEFAUtil dans la topologie</p></td>
<td><ol>
<li><p>Utilisez l’applet de commande <strong>New-CsTrustedApplicationPool</strong> pour créer un pool d’applications approuvées.</p></li>
<li><p>Utilisez l’applet de commande <strong>New-CsTrustedApplication</strong> pour spécifier l’outil SEFAUtil comme application approuvée.</p></li>
<li><p>Exécutez l’applet de commande <strong>Enable-CsTopology</strong> pour activer la topologie.</p></li>
<li><p>Installez les outils du kit de ressources sur un serveur frontal qui se trouve dans le pool d’applications approuvé créé à l’étape 1.</p></li>
<li><p>Vérifiez que l’outil SEFAUtil fonctionne correctement en l’exécutant pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les plages de numéros de prise d’appel dans la table des numéros d’appel parqué</p></td>
<td><p>Utilisez l’applet de nouvelle applet de <strong>nouveau-CSCallParkOrbit</strong> pour créer des plages de numéros de capture d’appel dans la table d’appel en orbite et attribuez-lui le type GroupPickup.</p>
<div>

> [!NOTE]  
> Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de capture d’appels de groupe dans la table de stationnement du parc. Les plages de numéros des numéros de téléphone ne sont pas disponibles dans le panneau de configuration de Lync Server.


</div>
<div>

> [!NOTE]  
> Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont en général configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) comme numéros de plages dans la table des numéros d’appel parqué.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurer des numéros de groupe de capture d’appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Affectation d’un numéro de capture d’appel aux utilisateurs et activation de la cueillette d’appel de groupe pour les utilisateurs</p></td>
<td><p>Utilisez le paramètre/enablegrouppickup dans l’outil de gestion des ressources SEFAUtil pour activer le prélèvement d’appels de groupe et affecter un numéro de téléphone pour les utilisateurs.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe</a></p></td>
</tr>
<tr class="even">
<td><p>Informer les utilisateurs du numéro de prise d’appel qui leur a été affecté et de tout autre numéro digne d’intérêt</p></td>
<td><p>Dans la mesure où les utilisateurs peuvent récupérer un appel passé à un utilisateur de groupe, les utilisateurs peuvent souhaiter surveiller plus d’un groupe.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communiquer des attributions d’appels de groupe aux utilisateurs dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérifier le déploiement d’un appel de groupe</p></td>
<td><p>Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Facultatif Vérifier le déploiement d’un appel de groupe dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

