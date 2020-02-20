---
title: 'Lync Server 2013 : gestion de la prise d’appel de groupe lors de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 633ccf1c792f951d13c747c935af51569365c753
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Gestion de la prise d’appel de groupe lors de la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Lorsqu’un pool frontal devient indisponible en raison d’un incident non planifié, le service est basculé vers le pool de sauvegarde. Lors du basculement vers le pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et sont en mode résistance. En mode résistance, les utilisateurs ne peuvent pas reprendre les appels des autres utilisateurs ou avoir des appels pris par d’autres utilisateurs. Une fois le basculement terminé, les utilisateurs peuvent de nouveau utiliser la prise d’appel de groupe comme d’habitude.

Pendant la restauration automatique vers le pool principal, les utilisateurs sont redirigés vers le pool principal et resont en mode résilience. La fonctionnalité de prise d’appel de groupe n’est pas disponible tant que les utilisateurs ne sont pas en mode résistance.

Cette section présente des considérations relatives à la prise d’appel de groupe lors de la récupération d’urgence et décrit également l’expérience utilisateur.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Considérations relatives à la prise d’appel de groupe lors de la récupération d’urgence

Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parcage d’appel en cours d’exécution dans le pool de sauvegarde pour les numéros de groupe de prise d’appel. Par conséquent, la prise en charge de la prise d’appel de groupe pendant la récupération d’urgence nécessite le déploiement et l’activation de l’application de parcage d’appel à la fois dans le pool principal et dans le pool de sauvegarde.

Les plages de numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel doivent être redirigées vers le pool de sauvegarde une fois le processus de basculement vers le pool de sauvegarde terminé. Les plages de numéros doivent être redirigées vers le pool principal une fois le processus de retour arrière vers le pool principal terminé. Pour rediriger les plages de prise d’appel de groupe, utilisez la cmdlet **Set-CsCallParkOrbit** .

Si vous déployez un nouveau pool avec un nom de domaine complet (FQDN) différent pour remplacer le pool principal, vous devez réaffecter toutes les plages de numéros de prise d’appel de groupe associées au pool principal au nom de domaine complet du nouveau pool. Pour réaffecter des plages de numéros au nouveau pool, vous pouvez utiliser la cmdlet **Set-CsCallParkOrbit** . Pour plus d’informations sur l’applet de commande **Set-CsCallParkOrbit** , voir [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Expérience de prise d’appel de groupe en cas de défaillance du pool

Le tableau suivant résume l’expérience de prise d’appel de groupe par le biais des phases de récupération d’urgence.

### <a name="user-experience-during-disaster-recovery"></a>Expérience utilisateur durant la récupération d’urgence

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>État de l’appel</th>
<th>Basculement vers le pool de sauvegarde</th>
<th>Restauration automatique vers le pool principal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><p><strong>Lors du processus de basculement :</strong></p>
<ul>
<li><p>La prise d’appel de groupe n’est pas disponible pour les utilisateurs en mode résilience</p></li>
</ul>
<p><strong>Une fois le basculement terminé :</strong></p>
<ul>
<li><p>Prise d’appel de groupe disponible lorsque les plages de numéros de prise d’appel de résilience et de groupe sont redirigées vers le pool de sauvegarde</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique :</strong></p>
<ul>
<li><p>La prise d’appel de groupe n’est pas disponible pour les utilisateurs en mode résilience</p></li>
</ul>
<p><strong>Une fois la restauration terminée :</strong></p>
<ul>
<li><p>Prise d’appel de groupe disponible lorsque les plages de numéros de prise d’appel de résilience et de groupe sont redirigées vers le pool principal</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels dans la file d’attente de prise d’appel de groupe</p></td>
<td><p><strong>Lors du processus de basculement :</strong></p>
<ul>
<li><p>Les appels en file d’attente ne peuvent pas être traités via la prise d’appel de groupe.</p></li>
</ul>
<p><strong>Une fois le basculement terminé :</strong></p>
<ul>
<li><p>Aucun appel dans cet État</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique :</strong></p>
<ul>
<li><p>Les appels en file d’attente ne peuvent pas être traités via la prise d’appel de groupe.</p></li>
</ul>
<p><strong>Une fois la restauration terminée :</strong></p>
<ul>
<li><p>Les appels en file d’attente ne peuvent pas être traités via la prise d’appel de groupe.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Appel établi</p></td>
<td><p><strong>Lors du processus de basculement :</strong></p>
<ul>
<li><p>Les appels restent connectés</p></li>
</ul>
<p><strong>Une fois le basculement terminé :</strong></p>
<ul>
<li><p>Les appels restent connectés</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique :</strong></p>
<ul>
<li><p>Les appels restent connectés</p></li>
</ul>
<p><strong>Une fois la restauration terminée :</strong></p>
<ul>
<li><p>Les appels restent connectés</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

