---
title: "Lync Server 2013 : Conf. mat. et logicielle requise pour le directeur"
TOCTitle: Configuration matérielle et logicielle requise pour le directeur
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398560(v=OCS.15)
ms:contentKeyID: 49297735
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-05-19_

Cette section aborde en détail la configuration matérielle et logicielle requise pour le directeur et les scénarios de colocalisation pris en charge pour le directeur.

## Configuration matérielle requise pour le directeur

Le tableau ci-dessous répertorie la configuration matérielle requise pour le directeur :

### Configuration matérielle requise pour le directeur

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Spécification minimale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processeur</p></td>
<td><ul>
<li><p>Processeur 64 bits, quadruple cœur 2,0 GHz ou supérieur</p></li>
<li><p>Biprocesseur 64 bits, double cœur 2,0 GHz ou supérieur</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>4 Go</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>Lecteur de disque dur (HDD) 10 000 tr/min</p></li>
<li><p>Disque SSD à hautes performances avec des performances supérieures ou égales à celles d’un disque dur de 10 000 tr/min</p></li>
<li><p>2x disques RAID 10 (agrégés par bandes et en miroir) 15 000 tr/min pour les fichiers de données des bases de données</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>Cartes réseau Dual-port 1 gigabit par seconde (Gbps) (recommandé)</p></li>
<li><p>Carte réseau d’un gigabit (prise en charge)</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Configuration logicielle requise pour le directeur

Le rôle directeur peut uniquement être déployé sur des serveurs exécutant Lync Server 2013 Enterprise Edition.

Un des systèmes d’exploitation 64 bits suivants est requis pour les directeurs :

  - Windows Server 2008 R2 Standard avec Service Pack 1

  - Windows Server 2008 R2 Enterprise avec Service Pack 1

  - Windows Server 2008 R2 Datacenter avec Service Pack 1

  - Le système d’exploitation Windows Server 2012 Standard

  - Le système d’exploitation Windows Server 2012 Datacenter

Lync Server 2013 requiert également l’installation des programmes et mises à jour suivants décrits dans la rubrique [Autres prises en charge et configurations de serveur requises dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).

## Colocalisation prise en charge

Le rôle serveur directeur ne peut être colocalisé avec aucun autre rôle serveur dans Lync Server 2013. Cependant, si vous ne déployez pas de directeur, les serveurs frontaux assument alors ce rôle.

