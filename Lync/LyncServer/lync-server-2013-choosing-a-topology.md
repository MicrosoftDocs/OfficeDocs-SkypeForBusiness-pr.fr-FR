---
title: 'Lync Server 2013 : Sélection d’une topologie'
TOCTitle: Sélection d’une topologie
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425716(v=OCS.15)
ms:contentKeyID: 49296539
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sélection d’une topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lorsque vous choisissez une topologie, vous pouvez utiliser l’une des options de topologie prises en charge suivantes :

> [!NOTE]  
> Sauf mention contraire, si vous disposez déjà d’une expérience de Microsoft Lync Server 2010, vous constaterez que l’aide de cette rubrique a subi peu de modifications.

  - [Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

> [!IMPORTANT]  
> Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.

Le tableau ci-dessous récapitule les fonctionnalités associées aux topologies Microsoft Lync Server 2013 prises en charge. Le titre des colonnes indique la fonctionnalité disponible pour une option de configuration Edge donnée. Par exemple, vous pouvez voir que l’option Serveur Edge mise à l’échelle (charge DNS équilibrée) prend en charge la haute disponibilité, peut utiliser des adresses IP privées non routables (avec NAT) ou des adresses IP publiques routables affectées aux interfaces externes du serveur Edge et permet de réduire les coûts, car elle ne nécessite pas de programme d’équilibrage de la charge matérielle.

Les scénarios de basculement Edge pris en charge avec l’équilibrage de la charge DNS sont les sessions point à point Lync vers Lync, les sessions de conférence Lync et les sessions Lync vers RTC et Office 365. Les scénarios de basculement Edge qui ne tirent pas parti de l’équilibrage de la charge DNS sont les basculements d’utilisateurs distants de la messagerie unifiée Exchange (antérieure à Exchange 2010 SP1), la connectivité PIC et la fédération avec les serveurs exécutant Office Communications Server.

### Récapitulatif des options de topologie de serveur Edge

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Topologie</th>
<th>Haute disponibilité</th>
<th>Enregistrement DNS A supplémentaire requis pour un serveur Edge externe du pool Edge</th>
<th>Basculement Edge pour les sessions Lync vers Lync</th>
<th>Basculement Edge pour les sessions de fédération EUM/PIC/OCS Lync vers Lync</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge unique utilisant NAT </p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge unique utilisant les adresses IP publiques</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Serveur Edge mis à l’échelle (charge DNS équilibrée) utilisant NAT </p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge mis à l’échelle (charge DNS équilibrée) utilisant les adresses IP publiques</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Serveur Edge mis à l’échelle (avec charge matérielle équilibrée)</p></td>
<td><p>Oui</p></td>
<td><p>Non (un enregistrement DNS A par VIP)</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
</tbody>
</table>


**\*** Le basculement pour la connectivité PIC (Public IM Connectivity) et la fédération avec des serveurs exécutant Office Communications Server ne sont pas disponibles avec l’équilibrage de la charge DNS. Le basculement de la messagerie unifiée Exchange (utilisateur distant) en utilisant l’équilibrage de la charge DNS requiert Exchange Server 2010 SP1 ou une version ultérieure.

> [!NOTE]  
> Serveur Edge mis à l’échelle (équilibrage de charge DNS)
> 
> <ul><li><p>Adresses IP publiques routables</p></li>
> <li><p>Adresse IP privée non routable si la conversion d’adresses réseau symétrique est utilisée</li></ul>
>
> Si vous utilisez une adresse IP publique ou une adresse IP privée avec conversion d’adresses réseau, vous utilisez le même nombre d’adresses IP en fonction de la configuration que vous avez définie dans le Générateur de topologie. Vous pouvez configurer le serveur Edge pour utiliser une seule adresse IP avec des ports distincts par service ou utiliser des adresses IP distinctes par service, mais le même port (par défaut, TCP 443).
> 
> Si vous décidez d’utiliser des adresses IP privées non routables avec conversion d’adresses réseau :
> 
> <ul><li><p>Vous devez utiliser des adresses IP privées routables sur les trois interfaces externes</p></li>
> <li><p>Vous devez configurer la conversion d’adresses réseau symétrique pour le trafic entrant et sortant</p></li></ul>
> 
> Les topologies de serveur Edge mises à l’échelle (avec équilibrage de la charge matérielle) doivent utiliser des adresses IP publiques.


Lync Server 2013 autorise le placement d’interfaces externes de serveur Edge d’accès, de conférence web et A/V derrière un routeur ou un pare-feu exécutant la conversion d’adresses réseau (NAT) pour des topologies de serveur Edge uniques et consolidées mises à l’échelle à la fois.

L’utilisation de la technologie NAT pour toutes les interfaces externes Edge exige le recours à l’équilibrage de la charge DNS. Comparé aux programmes d’équilibrage de la charge matérielle, l’équilibrage de la charge DNS (Domain Name System) permet de réduire le nombre d’adresses IP publiques pour chaque serveur Edge au sein d’un pool comme le décrit la liste suivante :

  - Topologie Edge Lync Server 2013 consolidée mise à l’échelle (avec charge DNS équilibrée) Nécessite trois adresses IP publiques pour chaque serveur Edge dans un pool de serveurs Edge

  - Topologie Edge Lync Server 2013 consolidée mise à l’échelle (avec charge matérielle équilibrée) ) Nécessite trois adresses IP publiques pour les adresses IP virtuelles du programme d’équilibrage de la charge (exigence ponctuelle qui ne grandit pas au fur et à mesure que des serveurs Edge sont ajoutés au pool) plus trois adresses IP publiques pour chaque serveur Edge dans un pool.

### Exigences d’adresses IP pour la topologie Edge consolidée (adresse IP par rôle)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de serveurs Edge par pool</th>
<th>Nombre d’adresses IP requises pour Lync Server 2013 (charge DNS équilibrée)</th>
<th>Nombre d’adresses IP requises pour Lync Server 2013 (charge matérielle équilibrée)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 15</p></td>
</tr>
</tbody>
</table>


### Exigences d’adresses IP pour la topologie Edge consolidée mise à l’échelle (adresse IP unique pour tous les rôles)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de serveurs Edge par pool</th>
<th>Nombre d’adresses IP requises pour Lync Server 2013 (charge DNS équilibrée)</th>
<th>Nombre d’adresses IP requises pour Lync Server 2013 (charge matérielle équilibrée)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
<td><p>1 (1 par adresse IP virtuelle) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (1 par adresse IP virtuelle) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1 (1 par adresse IP virtuelle) + 4</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>1 (1 par adresse IP virtuelle) + 5</p></td>
</tr>
</tbody>
</table>


Les principaux points devant orienter la sélection de la topologie sont la haute disponibilité et l’équilibrage de la charge. Si la haute disponibilité est requise, cela peut influencer la décision que vous prendrez en matière d’équilibrage de la charge.

  - **Haute disponibilité**   Si la haute disponibilité est requise, déployez au moins deux serveurs Edge dans un pool. Un seul pool Edge est capable de prendre en charge jusqu’à douze serveurs Edge. Pour davantage de capacité, vous pouvez déployer plusieurs pools Edge. En règle générale, 10 % du nombre d’utilisateurs inclus dans la base auront besoin d’un accès externe.
    
    > [!IMPORTANT]  
    > Le Générateur de topologie vous permet de configurer jusqu’à vingt serveurs Edge dans un même pool de serveurs Edge. Le nombre maximal de serveurs Edge testé et pris en charge dans un pool est douze et la prise en charge par le Générateur de topologie d’un nombre supérieur à douze ne doit pas être interprété comme une prise en charge implicite de plus de douze serveurs Edge dans un même pool de serveurs Edge.

  - **Équilibrage de la charge matérielle**   L’équilibrage de la charge matérielle est pris en charge pour la charge des serveurs EdgeLync Server 2013 quand les adresses IP publiquement routables font appel à des interfaces Edge externes. Par exemple, vous devez utiliser cette approche dans les situations où le basculement est nécessaire aux applications suivantes :
    
      - Solution PIC (Public IM Connectivity)
    
      - fédération avec des entreprises exécutant Microsoft Office Communications Server 2007 ou Microsoft Office Communications Server 2007 R2.
    
      - accès externe à la messagerie unifiée Exchange 2007 ou Exchange 2010 ;
        
        > [!IMPORTANT]  
        > L’équilibrage de la charge DNS pour Exchange 2010 SP1 et version ultérieure n’est pas pris en charge pour messagerie unifiée Exchange.    
    Ces trois applications continueront à fonctionner, mais ne pourront pas tirer parti de l’équilibrage de la charge DNS et ne se connecteront qu’au premier serveur Edge du pool. En cas d’indisponibilité de ce serveur, la connexion échoue. Par exemple, si plusieurs serveurs Edge sont déployés sur un pool en vue de gérer la charge de trafic fédérée, seul un proxy d’accès recevra le trafic alors que les autres seront inactifs.

> [!IMPORTANT]  
> L’utilisation de l’équilibrage de la charge DNS est recommandée pour la fédération avec des entreprises exécutant Lync Server 2010 et Microsoft Office 365. Notez que si la plupart des partenaires de la fédération utilisent Office Communications Server 2007 ou Office Communications Server 2007 R2, les performances risquent d’être sensiblement affectées.
