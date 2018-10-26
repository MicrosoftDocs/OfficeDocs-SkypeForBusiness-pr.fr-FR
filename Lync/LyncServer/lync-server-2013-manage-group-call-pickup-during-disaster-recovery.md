---
title: Gérer la prise d’appel de groupe pendant une récupération d’urgence
TOCTitle: Gérer la prise d’appel de groupe pendant une récupération d’urgence
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945618(v=OCS.15)
ms:contentKeyID: 53095388
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gérer la prise d’appel de groupe pendant une récupération d’urgence

 

_**Dernière rubrique modifiée :** 2015-03-09_

Quand un pool de serveurs frontaux devient indisponible en raison d’un incident inattendu, le service est basculé vers le pool de sauvegarde. Durant le basculement vers le pool de sauvegarde, les utilisateurs sont redirigés vers le pool de sauvegarde et placés en mode résistance. Dans ce mode, les utilisateurs ne peuvent pas prendre les appels d’autres utilisateurs ou voir leurs appels pris par d’autres utilisateurs. Quand le basculement est terminé, les utilisateurs peuvent réutiliser la prise d’appel de groupe normalement.

Durant la restauration automatique sur le pool principal, les utilisateurs sont redirigés vers le pool principal et de nouveau placés en mode résistance. La prise d’appel de groupe n’est pas disponible tant que les utilisateurs demeurent en mode résistance.

Cette section présente certaines observations sur la prise d’appel de groupe pendant une récupération d’urgence et décrit l’expérience utilisateur.

## Observations sur la prise d’appel de groupe pendant une récupération d’urgence

Durant la récupération d’urgence, les utilisateurs redirigés vers le pool de sauvegarde durant le processus de basculement utilisent l’application de parcage d’appel exécutée dans le pool de sauvegarde pour les numéros de groupe de prise d’appel. Par conséquent, la prise en charge de la prise d’appel de groupe durant la récupération d’urgence nécessite le déploiement et l’activation de l’application de parcage d’appel dans le pool principal et le pool de sauvegarde.

Les plages de numéros de la prise d’appel de groupe dans la table des numéros d’appel parqué doivent être redirigées vers le pool de sauvegarde une fois terminé le processus de basculement vers le pool de sauvegarde. Les plages de numéros doivent être redirigées vers le pool principal une fois terminé le processus de restauration automatique sur le pool principal. Pour rediriger les plages de la prise d’appel de groupe, utilisez l’applet de commande **Set-CsCallParkOrbit**.

Si vous déployez un nouveau pool doté d’un autre nom de domaine complet (FQDN) pour remplacer le pool principal, vous devez réaffecter l’intégralité des plages de numéros de la prise d’appel de groupe associées au pool principal vers le FQDN du nouveau pool. Pour réaffecter les plages de numéros au nouveau pool, vous pouvez utiliser l’applet de commande **Set-CsCallParkOrbit**. Pour plus d’informations sur l’applet de commande **Set-CsCallParkOrbit**, voir [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit).

## Expérience de la prise d’appel de groupe en cas de défaillance d’un pool

Le tableau suivant synthétise les informations relatives à l’utilisation de la prise d’appel de groupe via les phases de la récupération d’urgence.

### Expérience utilisateur durant la récupération d’urgence

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
<th>Restauration automatique sur le pool principal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><p><strong>Pendant le processus de basculement :</strong></p>
<ul>
<li><p>La prise d’appel de groupe n’est pas disponible pour les utilisateurs en mode résistance</p></li>
</ul>
<p><strong>Une fois le basculement effectué :</strong></p>
<ul>
<li><p>La prise d’appel de groupe est disponible quand les utilisateurs quittent le mode résistance et les plages de numéros de la prise d’appel de groupe sont redirigées vers le pool de sauvegarde.</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique :</strong></p>
<ul>
<li><p>La prise d’appel de groupe n’est pas disponible pour les utilisateurs en mode résistance</p></li>
</ul>
<p><strong>Une fois le processus de restauration automatique effectué :</strong></p>
<ul>
<li><p>La prise d’appel de groupe est disponible quand les utilisateurs quittent le mode résistance et les plages de numéros de la prise d’appel de groupe sont redirigées vers le pool principal.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels dans la file d’attente de la prise d’appel de groupe</p></td>
<td><p><strong>Pendant le processus de basculement :</strong></p>
<ul>
<li><p>Les appels dans la file d’attente ne peuvent pas être traités par le biais de la prise d’appel de groupe.</p></li>
</ul>
<p><strong>Une fois le basculement effectué :</strong></p>
<ul>
<li><p>Aucun appel ne reste dans cet état.</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique :</strong></p>
<ul>
<li><p>Les appels dans la file d’attente ne peuvent pas être traités par le biais de la prise d’appel de groupe.</p></li>
</ul>
<p><strong>Une fois le processus de restauration automatique effectué :</strong></p>
<ul>
<li><p>Les appels dans la file d’attente ne peuvent pas être traités par le biais de la prise d’appel de groupe.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Appel établi</p></td>
<td><p><strong>Pendant le processus de basculement :</strong></p>
<ul>
<li><p>Les appels demeurent connectés.</p></li>
</ul>
<p><strong>Une fois le basculement effectué :</strong></p>
<ul>
<li><p>Les appels demeurent connectés.</p></li>
</ul></td>
<td><p><strong>Pendant le processus de restauration automatique :</strong></p>
<ul>
<li><p>Les appels demeurent connectés.</p></li>
</ul>
<p><strong>Une fois le processus de restauration automatique effectué :</strong></p>
<ul>
<li><p>Les appels demeurent connectés.</p></li>
</ul></td>
</tr>
</tbody>
</table>

