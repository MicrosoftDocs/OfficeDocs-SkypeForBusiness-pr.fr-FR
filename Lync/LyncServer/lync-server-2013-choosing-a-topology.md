---
title: 'Lync Server 2013 : Sélection d’une topologie'
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
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Sélection d’une topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Dernière modification de la rubrique :** 2013-02-21_

Lorsque vous choisissez une topologie, vous pouvez utiliser l’une des options de topologie suivantes prises en charge :

<div>


> [!NOTE]
> Sauf indication contraire, si vous avez une connaissance de Microsoft Lync Server 2010, les conseils sont en grande partie inchangés.



</div>

  - [Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.



</div>

Le tableau suivant récapitule les fonctionnalités disponibles avec les topologies Microsoft Lync Server 2013 prises en charge. Les en-têtes de colonne indiquent les fonctionnalités disponibles pour une option de configuration latérale donnée. Par exemple, en utilisant l’option de répartition de charge DNS, vous pouvez voir qu’elle prend en charge une haute disponibilité, qu’elle peut utiliser des adresses IP privées non routables (avec la traduction d’adresses réseau) ou des adresses IP publiques routables attribuées aux interfaces externes d’Edge, et réduit les coûts, car un aucun équilibrage de charge matérielle n’est requis.

Les scénarios de basculement de périphérie pris en charge lors de l’équilibrage de charge DNS sont des sessions Lync-to-Lync, des sessions de conférence Lync, des sessions Lync-to-RTC et Office 365. Les scénarios de basculement vers le bord qui ne bénéficient pas de l’équilibrage de charge DNS sont de basculement pour la messagerie unifiée Exchange Remote User (MU) (antérieure à Exchange 2010 SP1), la connectivité de messagerie instantanée publique et la Fédération avec les serveurs exécutant des communications Office Serveurs.

### <a name="summary-of-edge-server-topology-options"></a>Résumé des options de topologie du serveur Edge

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
<th>Enregistrements DNS supplémentaires requis pour le serveur Edge externe dans le pool Edge</th>
<th>Reprise latérale pour les sessions Lync-to-Lync</th>
<th>Reprise latérale pour les sessions de Fédération Lync-to-Lync EUM/PIC/OCS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Un seul bord avec tar</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Bordure unique avec adresse IP publique</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Edge mis à l’échelle (équilibrage de charge DNS) avec tar</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Contour ajusté (équilibrage de charge DNS) avec adresse IP publique</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Répartition de charge matérielle latérale mise à l’échelle</p></td>
<td><p>Oui</p></td>
<td><p>Non (un enregistrement DNS A par VIP)</p></td>
<td><p>Oui</p></td>
<td><p>Oui</p></td>
</tr>
</tbody>
</table>


**\*** Le basculement pour la connectivité de messagerie instantanée publique, et la Fédération avec des serveurs exécutant Office Communications Server n’est pas disponible avec l’équilibrage de charge DNS. Le basculement de l’accès à la messagerie unifiée (d’utilisation distante) Exchange Server 2010 SP1 ou une version ultérieure est requise.



> [!NOTE]
> Il est possible d’utiliser les topologies à un seul bord et à l’échelle de l’horizontale (équilibrage de charge DNS) :
> <ul><li><p>Adresses IP publiques routables</p></li>
> <li><p>Adresse IP privée non routable si la traduction d’adresses réseau symétriques est utilisée</p></li>
>
> <ul><li> Si vous utilisez une adresse IP publique ou une adresse IP privée avec la traduction d’adresses réseau (NAT), vous devez toujours utiliser le même nombre d’adresses IP en fonction de votre choix de configuration dans le générateur de topologie. Vous pouvez configurer le serveur de périphérie de sorte qu’il utilise une seule adresse IP avec des ports distincts par service, ou utiliser des adresses IP distinctes par service, mais utiliser le même port (par défaut, TCP 443).</li></ul>>
> Si vous décidez d’utiliser des adresses IP privées sans routage avec tar :
> <ul><li><p>Vous devez utiliser des adresses IP privées routables sur les trois interfaces externes</p></li>
> <li><p>Vous devez configurer la traduction d’adresses réseau symétrique pour le trafic entrant et sortant.</p></li></ul>>
> La topologie de l’équilibrage du matériel doit utiliser des adresses IP publiques.



Lync Server 2013 prend en charge le placement d’accès, de conférences Web et d’interfaces externes A/V à partir d’un routeur ou d’un pare-feu qui effectue la traduction d’adresses réseau (NAT) pour les topologies de serveur de périphérie unique et à l’échelle.

L’utilisation de la traduction d’adresses réseau pour toutes les interfaces externes d’Edge nécessite l’utilisation de l’équilibrage de charge DNS. Par rapport à l’utilisation d’un dispositif d’équilibrage de la charge matérielle, l’utilisation de l’équilibrage de charge DNS sans NAT vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool Edge, comme décrit dans la liste suivante :

  - Lync Server 2013 (l’équilibrage de charge DNS) nécessite trois adresses IP publiques pour chaque serveur Edge d’un pool Edge.

  - Lync Server 2013 (équilibrage de charge matérielle) nécessite trois adresses IP publiques pour les adresses IP virtuelles de l’équilibrage de charge (une exigence qui n’est pas incrémentée en raison de l’ajout de serveurs Edge supplémentaires au pool) et de trois adresses IP publiques par Serveur Edge dans un pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Exigences relatives à l’adresse IP pour les bords consolidés mis à l’échelle (adresse IP par rôle)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de serveurs Edge par pool</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge DNS)</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge matérielle)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>deuxième</p></td>
<td><p>6</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>09</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>midi</p></td>
<td><p>3 (1 par adresse IP virtuelle) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>0,15</p></td>
<td><p>3 (1 par VIP) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>Exigences relatives à l’adresse IP pour les bords consolidés mis à l’échelle (adresse IP unique pour tous les rôles)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de serveurs Edge par pool</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge DNS)</th>
<th>Nombre d’adresses IP requises Lync Server 2013 (équilibrage de charge matérielle)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>deuxième</p></td>
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


Les points de décision principaux pour la sélection de la topologie sont haute disponibilité et équilibrage de la charge. La configuration requise pour une haute disponibilité peut influer sur la décision d’équilibrage de la charge.

  - **Haute disponibilité**   Si vous avez besoin d’une haute disponibilité, déployez au moins deux serveurs Edge dans un pool. Un seul pool de bords peut prendre en charge jusqu’à 12 serveurs de périphérie. Si une plus grande capacité est requise, vous pouvez déployer plusieurs pools de périphérie. En règle générale, 10% d’une base d’utilisateurs donnée doivent disposer d’un accès externe.
    
    <div>
    

    > [!IMPORTANT]
    > Le générateur de topologie vous permet de configurer un maximum de 25 serveurs Edge dans un seul pool Edge. Le nombre maximal de serveurs de périphérie testé et pris en charge dans un pool est de douze et le générateur de topologie autorisant un nombre supérieur à douze ne doit pas être interprété comme une prise en charge implicite de plus de douze serveurs de frontière dans un seul pool Edge.

    
    </div>

  - **Équilibrage de charge matérielle**   Le système d’équilibrage de la charge matérielle est pris en charge pour l’équilibrage de charge des serveurs Edge Lync Server 2013 lors de l’utilisation d’adresses IP routables publiques pour les interfaces externes de périphérie. Par exemple, vous pouvez utiliser cette approche dans les situations dans lesquelles le basculement est requis pour l’une des applications suivantes :
    
      - Solution PIC (Public IM Connectivity)
    
      - Fédération avec des sociétés exécutant Microsoft Office Communications Server 2007 ou Microsoft Office Communications Server 2007 R2
    
      - Accès externe à la messagerie unifiée Exchange 2007 ou à la messagerie unifiée Exchange 2010
        
        <div>
        

        > [!IMPORTANT]
        > L’équilibrage de charge DNS pour Exchange 2010 SP1 et les versions ultérieures est pris en charge pour la messagerie unifiée Exchange.

        
        </div>
    
    Ces trois applications continuent de fonctionner, mais elles ne sont pas compatibles avec l’équilibrage de charge DNS et ne se connectent qu’au premier serveur Edge du pool. Si ce serveur n’est pas disponible, la connexion échouera. Par exemple, si plusieurs serveurs Edge sont déployés dans un pool pour gérer le chargement du trafic fédéré, un seul proxy d’accès reçoit réellement le trafic alors que les autres sont inactifs.

<div>


> [!IMPORTANT]
> Il est recommandé d’utiliser l’équilibrage de charge DNS si vous vous fédérationz avec des entreprises utilisant Lync Server 2010 et Microsoft Office 365. Sachez qu’il existe d’importants impacts sur les performances si la plupart de vos partenaires fédérés utilisent Office Communications Server 2007 ou Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

