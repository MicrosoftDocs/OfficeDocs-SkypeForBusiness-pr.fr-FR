---
title: 'Lync Server 2013: gérer la collecte d’appels de groupe lors de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Gérer la cueillette des appels de groupe lors de la récupération après sinistre dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-30_

Lorsqu’un pool frontal devient indisponible en raison d’un incident imprévu, le service n’a pas pu être placé sur le pool de sauvegarde. Pendant le basculement vers le pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et sont en mode de résilience. Dans le mode de résilience, les utilisateurs ne peuvent pas capter les appels d’autres utilisateurs ou avoir leurs appels sélectionnés par d’autres utilisateurs. Lorsque le basculement est terminé, l’utilisateur peut à nouveau utiliser le prélèvement d’appel de groupe, comme d’habitude.

Pendant la restauration automatique vers le pool principal, les utilisateurs sont redirigés vers le pool principal et sont de nouveau en mode de résilience. La fonctionnalité de cueillette des appels de groupe n’est pas disponible tant que les utilisateurs n’ont pas le mode de résilience.

Cette section présente certaines considérations relatives à la collecte d’appels de groupe lors de la récupération après incident et décrit également l’interface utilisateur.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Éléments à prendre en compte lors d’une reprise d’appel de groupe

Lors de la récupération d’urgence, les utilisateurs qui ont été redirigés vers le pool de sauvegarde dans le cadre du processus de basculement utilisent l’application de parc d’appels qui s’exécute dans le pool de sauvegarde pour les numéros de groupe de capture d’appel. Par conséquent, la prise en charge de la collecte des appels de groupe lors de la récupération d’urgence nécessite le déploiement et l’activation de l’application de stationnement d’appel dans le pool principal et le pool de sauvegarde.

Le numéro de capture des appels de groupe dans la table d’orbite du parc d’appels doit être redirigé vers le pool de sauvegarde après le processus de basculement vers le pool de sauvegarde. Les plages de chiffres doivent être redirigées vers le pool principal après le processus de restauration automatique vers le pool principal. Pour rediriger les plages de capture des appels de groupe, utilisez la cmdlet **Set-CsCallParkOrbit** .

Si vous déployez un nouveau pool avec un nom de domaine complet différent (FQDN) pour remplacer le pool principal, vous devez réaffecter toutes les plages de numéros de la liste des appels de groupe associés au pool principal au FQDN du nouveau pool. Pour réattribuer des plages de nombres à la nouvelle liste, vous pouvez utiliser l’applet de cmdlet **Set-CsCallParkOrbit** . Pour plus d’informations sur l’applet **de connexion Set-CsCallParkOrbit** , reportez-vous à [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Capture d’écran d’un appel de groupe lors d’une panne de réserve

Le tableau suivant résume la fonction de découverte des appels de groupe lors des phases de reprise après sinistre.

### <a name="user-experience-during-disaster-recovery"></a>Utilisation de l’utilisateur pendant une reprise après sinistre

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
<td><p><strong>Pendant le processus de basculement:</strong></p>
<ul>
<li><p>Le prélèvement d’appels de groupe n’est pas disponible pour les utilisateurs en mode de résilience</p></li>
</ul>
<p><strong>Après le basculement complet:</strong></p>
<ul>
<li><p>Le choix d’appel de groupe est disponible lorsque les utilisateurs ont des plages de résilience et de groupe redirigées vers le pool de sauvegarde</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique:</strong></p>
<ul>
<li><p>Le prélèvement d’appels de groupe n’est pas disponible pour les utilisateurs en mode de résilience</p></li>
</ul>
<p><strong>Après la restauration automatique:</strong></p>
<ul>
<li><p>Le prélèvement d’appel de groupe est disponible lorsque les utilisateurs ont des plages de résilience et de redirection des appels de groupe redirigés vers le pool principal</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels dans la file d’attente de cueillette des appels de groupe</p></td>
<td><p><strong>Pendant le processus de basculement:</strong></p>
<ul>
<li><p>Les appels dans la file d’attente ne peuvent pas être traités par le biais du prélèvement d’appels de groupe.</p></li>
</ul>
<p><strong>Après le basculement complet:</strong></p>
<ul>
<li><p>Aucun appel dans cet État</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique:</strong></p>
<ul>
<li><p>Les appels dans la file d’attente ne peuvent pas être traités par le biais du prélèvement d’appels de groupe.</p></li>
</ul>
<p><strong>Après la restauration automatique:</strong></p>
<ul>
<li><p>Les appels dans la file d’attente ne peuvent pas être traités par le biais du prélèvement d’appels de groupe.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Appel établi</p></td>
<td><p><strong>Pendant le processus de basculement:</strong></p>
<ul>
<li><p>Appels Restez connectés</p></li>
</ul>
<p><strong>Après le basculement complet:</strong></p>
<ul>
<li><p>Appels Restez connectés</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique:</strong></p>
<ul>
<li><p>Appels Restez connectés</p></li>
</ul>
<p><strong>Après la restauration automatique:</strong></p>
<ul>
<li><p>Appels Restez connectés</p></li>
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

