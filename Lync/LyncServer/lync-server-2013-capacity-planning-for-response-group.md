---
title: 'Lync Server 2013 : Planification de capacité de Response Group'
TOCTitle: Planification de capacité de Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412754(v=OCS.15)
ms:contentKeyID: 49298370
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de capacité de Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le tableau ci-dessous décrit le modèle utilisateur de Response Group dont vous pouvez vous servir comme base pour les exigences de planification de capacité.

> [!NOTE]  
> Les chiffres du tableau suivant supposent que vous utilisez des fichiers 16 kHz, mono, 16 bits (.wav) pour tous les fichiers audio Response Group. Si vous utilisez d’autres formats de fichier, tels que Windows Media Audio (.wma), les chiffres peuvent changer.

> [!IMPORTANT]  
> N’oubliez pas que pour la planification de capacité de récupération d’urgence, chaque pool d’un pool associé doit être capable de gérer les charges de travail de tous les groupes de réponse des deux pools.

### Modèle utilisateur de Response Group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesure</th>
<th>Par pool Enterprise Edition (avec 8 serveurs frontaux)</th>
<th>Par serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels entrants par seconde</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sessions anonymes simultanées (sans messagerie instantanée)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>Sessions anonymes simultanées (avec messagerie instantanée)</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>Agents actifs (formels et informels)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Nombre de groupes de recherche</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de groupes de réponse vocale interactive (utilisation de la reconnaissance vocale)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>

