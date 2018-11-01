---
title: Plateformes matérielles de serveur pour Lync Server 2013
TOCTitle: Plateformes matérielles de serveur
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398835(v=OCS.15)
ms:contentKeyID: 49298845
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Plateformes matérielles de serveur pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les rôles serveur Lync Server 2013 et les ordinateurs exécutant des outils d'administration Lync Server requièrent du matériel 64 bits.

Le matériel spécifique utilisé pour le déploiement de Lync Server 2013 peut varier en fonction des impératifs de taille et d'utilisation. Cette section décrit le matériel recommandé. Même s'il s'agit de recommandations, et non d'impératifs, l'utilisation de matériel ne respectant pas ces recommandations peut entraîner des baisses de performance significatives et d'autres problèmes.

## Plateforme matérielle recommandée

Pour obtenir les meilleures performances, nous vous recommandons d'exécuter Lync Server sur les serveurs avec un matériel qui satisfait la configuration requise indiquée dans le tableau suivant. Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres. Notez que cette configuration matérielle requise est supérieure à celle des versions précédentes de Lync Server, car tous les serveurs frontaux exécutent SQL Server dans Lync Server 2013 pour l'essentiel.

> [!NOTE]  
> La collaboration NIC est prise en charge et doit être transparente sur Lync Server. Pour plus d'informations, reportez-vous à <a href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming (Association de carte réseau et de Communications Server ou Lync Server)</a>..

### Matériel recommandé pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition Server, les serveurs de conversation permanente, le magasin de conversation permanente et le magasin de conformité de conversation permanente (rôles Serveur principal pour le serveur de conversation permanente)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Recommandation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processeur</p></td>
<td><p>Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur.</p>
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>32 giga-octets (Go).</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul><li><p>8 disques durs ou plus 10 000 tr/min avec au moins 72 Go d'espace disponible.</p>
<p>Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</p>
<p>- OU -</p></li><li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tr/min.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul><li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l'association à une seule adresse MAC et une seule adresse IP).</p>
<div>

> [!NOTE]  
> Les configurations doubles ou à plusieurs connexions ne sont pas prises en charge pour les serveurs serveurs frontaux, serveurs principaux, serveurs Standard Edition et serveurs de conversations permanentes.<br />
Les connexions ILO/DRAC/etc. non exposées au système d'exploitation et utilisées pour la surveillance et la gestion du matériel des serveurs ne constituent pas un serveur à plusieurs connexions et ne sont donc pas prises en charge.
</div></li></ul></td>
</tr>
</tbody>
</table>


### Matériel recommandé pour les serveurs Edge, les serveurs de médiation autonomes et les directeurs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Recommandation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processeur</p></td>
<td><ul><li><p>Biprocesseur 64 bits, quadruple cœur, 2 GHz ou supérieur</p>
<p>- OU -</p></li><li><p>Processeur 64 bits à quatre voies, double cœur, 2 GHz ou supérieur</p></li></ul>
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>16 giga-octets (Go).</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul><li><p>4 disques durs ou plus 10 000 tr/min avec au moins 72 Go d'espace disponible.</p>
<p>La configuration des disques doit être de type 2x RAID 1.</p>
<p>- OU -</p></li><li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 4 disques durs mécaniques 10 000 tr/min.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul><li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l'association à une seule adresse MAC et une seule adresse IP). 2 interfaces réseau sont requises sur serveurs Edge et sont prises en charge sur les serveurs serveurs de médiation autonomes.</p></li></ul>
<div>

> [!NOTE]  
> Les configurations doubles ou à plusieurs connexions ne sont pas prises en charge pour les serveurs directeurs.<br />
Les connexions ILO/DRAC/etc. non exposées au système d'exploitation et utilisées pour la surveillance et la gestion du matériel des serveurs ne constituent pas un serveur à plusieurs connexions et ne sont donc pas prises en charge.
</div>
<p>Les serveurs serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau double port, 1 Gbit/s ou plus (ou deux cartes réseau appariées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et à une adresse IP unique, pour un total de deux paires).</p>
<p>L'installation de cartes d'interface réseau (NIC) supplémentaires pour permettre la configuration d'une adresse IP PSTN spécifique est prise en charge sur les serveurs serveurs de médiation autonomes.</p></td>
</tr>
</tbody>
</table>

