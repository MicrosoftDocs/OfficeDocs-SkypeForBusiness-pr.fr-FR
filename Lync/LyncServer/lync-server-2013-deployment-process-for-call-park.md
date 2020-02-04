---
title: 'Lync Server 2013 : processus de déploiement pour le parc d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Processus de déploiement du parc d’appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Cette section fournit une vue d’ensemble des étapes de déploiement de l’application de parc d’appels. Vous devez déployer Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer le parc d’appels. Les composants requis par le parc d’appels sont installés et activés lorsque vous déployez Enterprise Voice.

### <a name="call-park-deployment-process"></a>Procédure de déploiement du parcage d’appel

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
<td><p>Configurer les plages d’orbites de parcage d’appel dans la table des orbites</p></td>
<td><p>Utilisez le panneau de configuration de Lync Server ou l’applet <strong>de commande New-CSCallParkOrbit</strong> pour créer les plages d’orbites dans la table de stationnement d’appel et associez-les au service d’application qui héberge l’application de stationnement d’appels.</p>
<div>

> [!NOTE]  
> Pour une intégration transparente aux plans de numérotation existants, les plages d’orbites sont en général configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) comme numéros d’orbites dans la table des orbites de parcage d’appel.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Créer ou modifier une gamme de parc d’appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configuration des paramètres de parcage d’appel</p></td>
<td><p>Utilisez l’applet de cmdlet <strong>Set-CsCpsConfiguration</strong> pour configurer les paramètres du parc d’appels. Nous vous conseillons d’effectuer au moins une configuration de l’option <strong>OnTimeoutURI</strong> pour configurer la destination de secours à utiliser lorsqu’un appel parqué arrive à expiration. Vous pouvez également configurer les paramètres suivants :</p>
<ul>
<li><p>(Facultatif) <strong>EnableMusicOnHold</strong> pour activer ou désactiver l’attente musicale.</p></li>
<li><p>(Facultatif) <strong>MaxCallPickupAttempts</strong> pour déterminer le nombre de fois qu’un appel parqué doit sonner de nouveau sur le téléphone de destination avant d’être transféré à l’URI (Uniform Resource Identifier) de remplacement.</p></li>
<li><p>(Facultatif) <strong>CallPickupTimeoutThreshold</strong> pour déterminer le délai qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Configurer les paramètres de parc d’appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Si vous le souhaitez, personnalisez l’attente musicale</p></td>
<td><p>Si vous ne voulez pas utiliser l’attente musicale par défaut, personnalisez et téléchargez un fichier audio à l’aide de l’applet de commande <strong>Set-CsCallParkServiceMusicOnHoldFile</strong>.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personnaliser le parc d’appels en attente dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer la stratégie vocale pour activer le parc d’appels pour les utilisateurs</p></td>
<td><p>Utilisez le panneau de configuration de Lync Server ou l’applet de commande <strong>Set-CSVoicePolicy</strong> avec l’option <strong>EnableCallPark</strong> pour activer le parc d’appels pour les utilisateurs dans la stratégie vocale.</p>
<div>

> [!NOTE]  
> Par défaut, le parc d’appels est désactivé pour tous les utilisateurs.


</div>
<div>

> [!NOTE]  
> Si vous disposez de plusieurs stratégies de voix, définissez la propriété EnableCallPark pour toutes les stratégies de voix et pas seulement pour la stratégie par défaut.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Activer le parc d’appels pour les utilisateurs dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérification des règles de normalisation pour le parcage d’appel</p></td>
<td><p>Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez que les règles de normalisation ne comportent aucune plage d’orbites. Si nécessaire, créez des règles de normalisation supplémentaires pour empêcher la normalisation des orbites.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Vérifier les règles de normalisation du parc d’appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vérifier le déploiement de votre parc d’appels</p></td>
<td><p>Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Facultatif Vérifier le déploiement du parc d’appels dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

