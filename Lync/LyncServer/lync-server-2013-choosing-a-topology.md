---
title: 'Lync Server 2013 : choix d’une topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc30881da768d8dad9f952df37bdf1accdf091b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Choix d’une topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Dernière modification de la rubrique :** 2013-02-21_

Lorsque vous choisissez une topologie, vous pouvez utiliser l’une des options de topologie prises en charge suivantes :

<div>


> [!NOTE]
> Sauf indication contraire, si vous avez une expérience de Microsoft Lync Server 2010, vous trouverez ci-dessous des conseils inchangés.



</div>

  - [Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.



</div>

Le tableau suivant récapitule les fonctionnalités disponibles avec les topologies Microsoft Lync Server 2013 prises en charge. Le titre des colonnes indique la fonctionnalité disponible pour une option de configuration Edge donnée. Par exemple, vous pouvez voir que l’option Serveur Edge mise à l’échelle (charge DNS équilibrée) prend en charge la haute disponibilité, peut utiliser des adresses IP privées non routables (avec NAT) ou des adresses IP publiques routables affectées aux interfaces externes du serveur Edge et permet de réduire les coûts, car elle ne nécessite pas de programme d’équilibrage de la charge matérielle.

Les scénarios de basculement de serveur Edge pris en charge avec l’équilibrage de charge DNS sont des sessions de point à point entre Lync et Lync, des sessions de conférence Lync, des sessions Lync à PSTN et Office 365. Les scénarios de basculement de serveur Edge qui ne bénéficient pas de l’équilibrage de charge DNS sont des basculements pour la messagerie unifiée Exchange de l’utilisateur distant (avant Exchange 2010 SP1), la connectivité de messagerie instantanée publique et la Fédération avec des serveurs exécutant les communications Office Serveurs.

### <a name="summary-of-edge-server-topology-options"></a>Récapitulatif des options de topologie de serveur Edge

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
<th>Basculement de serveur Edge pour les sessions Lync à Lync</th>
<th>Basculement Edge pour les sessions Lync-to-Lync EUM/PIC/OCS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge unique utilisant NAT</p></td>
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
<td><p>Serveur Edge mis à l’échelle (charge DNS équilibrée) utilisant NAT</p></td>
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


**\*** Le basculement pour la connectivité PIC (public Instant Messaging) et la Fédération avec des serveurs exécutant Office Communications Server ne sont pas disponibles avec l’équilibrage de charge DNS. Le basculement de la messagerie unifiée Exchange (utilisateur distant) à l’aide de l’équilibrage de charge DNS nécessite Exchange Server 2010 SP1 ou une version ultérieure.



> [!NOTE]
> Serveur Edge mis à l’échelle (équilibrage de charge DNS)
> <ul><li><p>Adresses IP publiques routables</p></li>
> <li><p>Adresse IP privée non routable si la traduction d’adresses réseau (NAT) symétrique est utilisée</p></li>
>
> <ul><li> Si vous utilisez une adresse IP publique ou une adresse IP privée avec NAT, vous continuerez à utiliser le même nombre d’adresses IP en fonction de votre choix de configuration dans le générateur de topologie. Vous pouvez configurer le serveur Edge de sorte qu’il utilise une seule adresse IP avec des ports distincts par service, ou utiliser des adresses IP distinctes par service, mais utiliser le même port (par défaut, TCP 443).</li></ul>>
> Si vous décidez d’utiliser des adresses IP privées non routables avec tar, procédez comme suit :
> <ul><li><p>Vous devez utiliser des adresses IP privées routables sur les trois interfaces externes</p></li>
> <li><p>Vous devez configurer la traduction d’adresses réseau symétrique pour le trafic entrant et sortant</p></li></ul>>
> Les topologies de serveur Edge mises à l’échelle (avec équilibrage de la charge matérielle) doivent utiliser des adresses IP publiques.



Lync Server 2013 prend en charge le positionnement des interfaces externes d’accès, de conférence Web et de serveur Edge A/V derrière un routeur ou un pare-feu qui effectue la traduction d’adresses réseau (NAT) pour les topologies de serveur Edge consolidées simples et mises à l’ampleur.

L’utilisation de la technologie NAT pour toutes les interfaces externes Edge exige le recours à l’équilibrage de la charge DNS. Comparé aux programmes d’équilibrage de la charge matérielle, l’équilibrage de la charge DNS (Domain Name System) permet de réduire le nombre d’adresses IP publiques pour chaque serveur Edge au sein d’un pool comme le décrit la liste suivante :

  - Lync Server 2013 serveur Edge consolidé mis à l’ampleur (charge DNS équilibrée) nécessite trois adresses IP publiques pour chaque serveur Edge dans un pool de serveurs Edge.

  - Lync Server 2013 serveur Edge consolidé mis à l’ampleur (avec charge matérielle équilibrée) nécessite trois adresses IP publiques pour les adresses IP virtuelles du programme d’équilibrage de charge (une exigence de temps qui n’est pas incrémentée au fur et à mesure que des serveurs Edge sont ajoutés au pool) plus trois adresses IP publiques par Serveur Edge dans un pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Exigences d’adresses IP pour la topologie Edge consolidée (adresse IP par rôle)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de serveurs Edge par pool</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (charge DNS équilibrée)</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (charge matérielle équilibrée)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>n°2</p></td>
<td><p>6 </p></td>
<td><p>3 (1 par adresse IP virtuelle) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9 </p></td>
<td><p>3 (1 par adresse IP virtuelle) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 12</p></td>
</tr>
<tr class="even">
<td><p>disque</p></td>
<td><p>15 </p></td>
<td><p>3 (1 par adresse IP virtuelle) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>Exigences d’adresses IP pour la topologie Edge consolidée mise à l’échelle (adresse IP unique pour tous les rôles)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de serveurs Edge par pool</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (charge DNS équilibrée)</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (charge matérielle équilibrée)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>n°2</p></td>
<td><p>n°2</p></td>
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
<td><p>disque</p></td>
<td><p>disque</p></td>
<td><p>1 (1 par adresse IP virtuelle) + 5</p></td>
</tr>
</tbody>
</table>


Les principaux points devant orienter la sélection de la topologie sont la haute disponibilité et l’équilibrage de la charge. Si la haute disponibilité est requise, cela peut influencer la décision que vous prendrez en matière d’équilibrage de la charge.

  - **Haute disponibilité**   Si vous avez besoin d’une haute disponibilité, déployez au moins deux serveurs Edge dans un pool. Un pool Edge unique prend en charge jusqu’à douze serveurs Edge. Pour davantage de capacité, vous pouvez déployer plusieurs pools Edge. En règle générale, 10 % du nombre d’utilisateurs inclus dans la base auront besoin d’un accès externe.
    
    <div>
    

    > [!IMPORTANT]
    > Le générateur de topologies vous permet de configurer jusqu’à vingt serveurs Edge dans un seul pool de serveurs Edge. Le nombre maximal testé et pris en charge de serveurs Edge dans un pool est de douze et le générateur de topologie autorise un nombre supérieur à douze ne doit pas être interprété comme une prise en charge implicite de plus de douze serveurs Edge dans un seul pool Edge.

    
    </div>

  - **Équilibrage de la charge matérielle**   L’équilibrage de la charge matérielle est pris en charge pour l’équilibrage de charge des serveurs Edge Lync Server 2013 lors de l’utilisation d’adresses IP routables publiquement pour les interfaces externes Edge. Par exemple, vous devez utiliser cette approche dans les situations où le basculement est nécessaire aux applications suivantes :
    
      - solution PIC (Public IM Connectivity) ;
    
      - Fédération avec des entreprises exécutant Microsoft Office Communications Server 2007 ou Microsoft Office Communications Server 2007 R2
    
      - accès externe à la messagerie unifiée Exchange 2007 ou Exchange 2010 ;
        
        <div>
        

        > [!IMPORTANT]
        > L’équilibrage de charge DNS pour Exchange 2010 SP1 et les versions ultérieures est pris en charge pour la messagerie unifiée Exchange.

        
        </div>
    
    Ces trois applications continueront à fonctionner, mais ne pourront pas tirer parti de l’équilibrage de la charge DNS et ne se connecteront qu’au premier serveur Edge du pool. En cas d’indisponibilité de ce serveur, la connexion échoue. Par exemple, si plusieurs serveurs Edge sont déployés sur un pool en vue de gérer la charge de trafic fédérée, seul un proxy d’accès recevra le trafic alors que les autres seront inactifs.

<div>


> [!IMPORTANT]
> L’utilisation de l’équilibrage de charge DNS est recommandée si vous vous fédérer avec des entreprises utilisant Lync Server 2010 et Microsoft Office 365. Sachez qu’il existe un impact significatif sur les performances si la plupart de vos partenaires fédérés utilisent Office Communications Server 2007 ou Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

