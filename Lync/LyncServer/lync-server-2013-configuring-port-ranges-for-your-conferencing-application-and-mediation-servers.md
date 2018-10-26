---
title: "Conf. des plages de ports pour vos serv. de confér., d’app. et de médiation"
TOCtitle: "Conf. des plages de ports pour vos serv. de confér., d’app. et de médiation"
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204872(v=OCS.15)
ms:contentKeyID: 49297160
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des plages de ports pour vos serveurs de conférence, d’applications et de médiation

 

_**Dernière rubrique modifiée :** 2015-04-30_

Pour implémenter la qualité de service (QoS), vous devez configurer des plages de ports identiques pour l’audio, la vidéo et le partage d’applications sur vos serveurs de conférence, d’applications et de médiation. En outre, ces plages de ports ne doivent absolument pas se chevaucher. Pour prendre un exemple simple, supposons que vous utilisiez les ports 10000 à 10999 pour la vidéo sur vos serveurs de conférence. Cela signifie que vous devez également réserver les ports 10000 à 10999 pour la vidéo sur vos serveurs d’applications et de médiation. Sinon, la qualité de service ne fonctionnera pas comme prévu.

De même, supposons que vous réserviez les ports 10000 à 10999 pour la vidéo mais que vous réserviez ensuite les ports 10500 à 11999 pour l’audio. Cela peut créer des problèmes de qualité de service, car les plages de ports se chevauchent. Avec la qualité de service, chaque modalité doit posséder un ensemble unique de ports : si vous utilisez les ports 10000 à 10999 pour la vidéo, vous devez utiliser une autre plage (par exemple, 11000 à 11999 pour l’audio).

Par défaut, les plages de ports audio et vidéo ne se chevauchent pas dans Microsoft Lync Server 2013 ; toutefois, les plages de ports affectées au partage d’application chevauchent les plages de ports affectées à l’audio et la vidéo (en retour, cela signifie qu’aucune de ces plages n’est unique). Vous pouvez vérifier les plages de ports existantes de vos serveurs de conférence, d’applications et de médiation en exécutant les trois commandes suivantes à partir de Lync Server 2013 Management Shell :

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Comme vous pouvez le voir dans les commandes précédentes, chaque type de port (audio, vidéo et partage d’application) se voit affecter deux valeurs de propriétés distinctes : le port de début et le nombre de ports. Le port de début indique le premier port utilisé pour la modalité concernée. Par exemple, si le port de début audio est 50000, cela signifie que le premier port utilisé pour le trafic audio est le port 50000. Si le nombre de ports audio est égal à 2 (il s’agit ici d’une valeur non valide utilisée uniquement à titre d’illustration), cela signifie que seuls 2 ports sont alloués pour l’audio. Si le premier port est le port 50000 et s’il existe deux ports au total, cela signifie que le second port doit être le port 50001 (les plages de ports doivent être contigües). Ainsi, la plage de ports pour l’audio doit inclure les ports 50000 à 50001.<br />
Notez également que le serveur d’applications et le serveur de médiation ne prennent en charge la qualité de service que pour l’audio. Vous n’avez pas besoin de modifier les ports vidéo ou de partage d’application sur vos serveurs d’applications ou vos serveurs de médiation.

Si vous exécutez les trois commandes précédentes, vous verrez que les valeurs de ports par défaut de Lync Server 2013 sont configurées comme suit :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriété</th>
<th>Serveur de conférence</th>
<th>Serveur d’applications</th>
<th>Serveur de médiation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


Comme indiqué précédemment, quand vous configurez les ports Lync Server pour la qualité de service, vous devez vous assurer que : 1) les paramètres des ports audio sont identiques sur vos serveurs de conférence, d’applications et de médiation, et que 2) les plages de ports ne se chevauchent pas. Si vous examinez attentivement le tableau précédent, vous voyez que les plages de ports sont identiques sur les trois types de serveur. Par exemple, le port audio de début est fixé au port 49152 sur chaque type de serveur et le nombre total de ports réservés à l’audio sur chaque serveur est également identique : 8 348. Toutefois, les plages de ports se chevauchent : les ports audio débutent au port 49152 mais c’est le cas également pour les ports réservés au partage d’application. Pour permettre une qualité de service optimale, le partage d’application doit être reconfiguré afin d’utiliser une plage de ports unique. Par exemple, vous pouvez configurer le partage d’application pour démarrer au port 40803 et utiliser 8 348 ports. Pourquoi 8 348 ports ? Si vous ajoutez les valeurs 40 803 + 8 348, cela signifie que le partage d’application utilise les ports 40803 à 49151. Comme les ports audio ne commencent pas avant le port 49152, vous n’avez plus de plages de ports qui se chevauchent.

Après avoir sélectionné la nouvelle plage de ports pour le partage d’application, vous pouvez effectuer votre modification à l’aide de l’applet de commande Set-CsConferencingServer. Cette modification n’a pas à être effectuée sur vos serveurs d’applications ou vos serveurs de médiation, car ces serveurs ne gèrent pas le trafic du partage d’application. Vous ne devez changer les valeurs de ports de ces serveurs que si vous décidez de réaffecter les ports utilisés pour le trafic audio.

Pour modifier les valeurs de ports du partage d’application sur un seul serveur de conférence, exécutez une commande semblable à ce qui suit à partir de Lync Server Management Shell :

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si vous voulez effectuer ces modifications sur tous vos serveurs de conférence, vous pouvez exécuter cette commande à la place :

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Après avoir modifié les paramètres des ports, vous devez arrêter, puis redémarrer chaque service affecté par les modifications.

Il n’est pas obligatoire que vos serveurs de conférence, serveurs d’applications et serveurs de médiation partagent la même plage de ports. Le seul impératif est de réserver les plages de ports uniques sur tous vos serveurs. Toutefois, l’administration est généralement plus facile si vous utilisez le même ensemble de ports sur tous vos serveurs.

