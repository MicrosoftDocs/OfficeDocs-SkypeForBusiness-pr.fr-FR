---
title: 'Lync Server 2013 : processus de déploiement de la prise d’appel de groupe'
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
ms.openlocfilehash: 52f7646010e4048d135e11c98d06a651f923d633
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522611"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Processus de déploiement de la prise d’appel de groupe dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Cette section fournit une vue d’ensemble des étapes nécessaires au déploiement de la prise d’appel de groupe. Vous devez déployer Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer la prise d’appel de groupe. Les composants requis par la prise d’appel de groupe sont installés et activés lorsque vous déployez voix entreprise.

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
<td><p>Activer l’outil de kit de ressources SEFAUtil dans la topologie</p></td>
<td><ol>
<li><p>Utilisez la cmdlet <strong>New-CsTrustedApplicationPool</strong> pour créer un pool d’applications approuvées.</p></li>
<li><p>Utilisez la cmdlet <strong>New-CsTrustedApplication</strong> pour spécifier l’outil SEFAUtil en tant qu’application approuvée.</p></li>
<li><p>Exécutez la cmdlet <strong>Enable-CsTopology</strong> pour activer la topologie.</p></li>
<li><p>Installez les outils du kit de ressources sur un serveur frontal qui se trouve dans le pool d’applications approuvées créé à l’étape 1.</p></li>
<li><p>Vérifiez que SEFAUtil s’exécute correctement en l’exécutant pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Déployer l’outil SEFAUtil dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configuration des plages de numéros de prise d’appel dans la table des orbites de parcage d’appel</p></td>
<td><p>Utilisez la cmdlet <strong>New-CSCallParkOrbit</strong> pour créer des plages de numéros de prise d’appel dans la table des orbites de parcage d’appel et affecter les plages de prise d’appel au type GroupPickup.</p>
<div>

> [!NOTE]  
> Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel. Les plages de numéros de prise d’appel de groupe ne sont pas disponibles dans le panneau de configuration Lync Server.


</div>
<div>

> [!NOTE]  
> Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont généralement configurées en tant que bloc d’extensions virtuelles. L’affectation de numéros DID (appels directs vers l’intérieur) sous forme de numéros de plage dans la table des orbites de parcage d’appel n’est pas prise en charge.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurer les numéros de groupe de prise d’appel dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Affecter un numéro de prise d’appel aux utilisateurs et activer la prise d’appel de groupe pour les utilisateurs</p></td>
<td><p>Utilisez le paramètre/enablegrouppickup dans l’outil de kit de ressources SEFAUtil pour activer la prise d’appel de groupe et affecter un numéro de prise d’appel pour les utilisateurs.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe</a></p></td>
</tr>
<tr class="even">
<td><p>Avertir les utilisateurs du numéro de prise d’appel et de tout autre nombre d’intérêt</p></td>
<td><p>Étant donné qu’un utilisateur peut récupérer un appel passé à un utilisateur de la prise d’appel de groupe, les utilisateurs peuvent souhaiter surveiller plusieurs groupes.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communiquer des attributions de prise d’appel de groupe aux utilisateurs dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérifier le déploiement de la prise d’appel de groupe</p></td>
<td><p>Testez le placement et la récupération des appels pour vous assurer que votre configuration fonctionne comme prévu.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Module Vérifier le déploiement de la prise d’appel de groupe dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

