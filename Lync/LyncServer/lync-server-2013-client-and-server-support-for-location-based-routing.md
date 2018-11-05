---
title: "Lync Server 2013 : Prise en ch. des clients et des serv. pour routage géodép."
TOCTitle: Prise en charge des clients et des serveurs pour le routage géodépendant
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994024(v=OCS.15)
ms:contentKeyID: 53095382
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge des clients et des serveurs pour le routage géodépendant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le routage géodépendant est appliqué par Lync Server. Lync Server peut identifier les sites réseau à partir desquels les utilisateurs se connectent au sein du réseau d’entreprise. Comme les utilisateurs distants sont situés en dehors du réseau d’entreprise, leur emplacement est considéré comme inconnu.

## Prise en charge de Lync Server

Le routage géodépendant requiert le déploiement de Lync Server 2013 CU1 sur l’ensemble des pools de serveurs frontaux et serveurs Standard Edition dans une topologie donnée. Si Lync Server 2013 n’est pas installé sur certains composants Lync dans la topologie, les restrictions de routage géodépendant ne peuvent pas être entièrement appliquées.

Le tableau ci-dessous identifie les combinaisons de rôles serveur et versions prises en charge pour le routage géodépendant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Version du pool</th>
<th>Version du serveur de médiation</th>
<th>Pris en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mise à jour cumulative pour Lync Server 2013 de février 2013</p></td>
<td><p>Mise à jour cumulative pour Lync Server 2013 de février 2013</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative pour Lync Server 2013 de février 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative pour Lync Server 2013 de février 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative pour Lync Server 2013 de février 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>Quelconque</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>Quelconque</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Quelconque</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


## Prise en charge du client Lync

Le tableau ci-dessous identifie les clients pris en charge par le routage géodépendant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de client</th>
<th>Pris en charge</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Oui</p></td>
<td><p>Mise à jour cumulative pour Lync 2013 de février 2013 comprise</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Non</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Intendant</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync pour Windows 8</p></td>
<td><p>Non</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>Non</p></td>
<td><p>Le protocole VoIP doit être désactivé pour les clients Lync Mobile 2013 pour les utilisateurs pour lesquels le routage géodépendant est activé.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

> [!NOTE]  
> Pour désactiver le protocole VoIP pour les clients Lync Mobile 2013, affectez une stratégie de mobilité avec le paramètre Audio/Vidéo IP désélectionné pour tous les utilisateurs pour lesquels le routage géodépendant est activé. Pour plus d’informations sur la stratégie de mobilité, reportez-vous à <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</a>.

## Voir aussi

#### Autres ressources

[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

