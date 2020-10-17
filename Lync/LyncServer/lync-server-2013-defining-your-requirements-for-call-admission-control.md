---
title: 'Lync Server 2013 : définition de la configuration requise pour le contrôle d’admission des appels'
description: 'Lync Server 2013 : définition de la configuration requise pour le contrôle d’admission des appels.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f675ac5811e0c0c1c23dc76ebb8b4525857836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545420"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-28_

La planification du contrôle d’admission des appels (CAC) requiert des informations détaillées sur votre topologie de réseau d’entreprise. Pour vous aider à planifier vos stratégies de contrôle d’admission des appels, procédez comme suit.

1.  Identifiez les concentrateurs/dorsales principales (appelés *régions réseau*) dans votre réseau d’entreprise.

2.  Identifiez les bureaux et emplacements (appelés *sites réseau*) dans chaque région réseau.

3.  Déterminez l’itinéraire réseau entre chaque paire de régions réseau.

4.  Déterminez les limites de bande passante pour chaque liaison réseau étendu (WAN).
    
    <div>
    

    > [!NOTE]  
    > Les limites de bande passante font référence à la proportion de bande passante sur une liaison de réseau étendu allouée au trafic audio et vidéo de l’entreprise. Quand une liaison réseau étendu est décrite comme « à bande passante restreinte », la liaison réseau étendu a une limite de bande passante qui est inférieure au trafic maximal prévu sur la liaison.

    
    </div>

5.  Identifiez les sous-réseaux IP qui sont affectés à chaque site réseau.

Pour expliquer ces concepts, nous prendrons l’exemple de topologie réseau présenté à la figure suivante.

**Exemple de topologie pour le contrôle d’admission des appels**

![Exemple de topologie de réseau Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Exemple de topologie de réseau Litware Inc.")

<div>


> [!NOTE]  
> Tous les sites réseau sont associés à une région réseau. Par exemple, Portland, Reno et Albuquerque sont inclus dans la région Amérique du Nord. Dans cette figure, seules les liaisons réseau étendu auxquelles des stratégies de service Contrôle d’admission des appels sont appliquées sont présentées, avec des limites de bande passante. Les sites réseau Chicago, New York et Détroit apparaissent dans l’ovale de la région Amérique du Nord, car ils ne sont soumis à aucune limite de bande passante et ne nécessitent donc aucune stratégie de service Contrôle d’admission des appels.



</div>

Les composants de cet exemple de topologie sont décrits dans les sections suivantes. Pour plus d’informations sur la planification de cette topologie, notamment les limites de bande passante, voir [example : Gathering Your Requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

<div>

## <a name="identify-network-regions"></a>Identifier les régions réseau

Une région réseau représente une dorsale principale ou un concentrateur réseau.

Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.

Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient un ensemble de sites réseau (voir la définition des sites réseau plus loin dans cette rubrique). Collaborez avec votre équipe responsable des opérations réseau pour identifier vos régions réseau.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>Association d’un site central avec chaque région réseau

CAC exige qu’un site central Lync Server soit défini pour chaque région réseau. Le site central est sélectionné en fonction de la meilleure connectivité réseau et de la bande passante la plus élevée parmi les autres sites de la région réseau. L’exemple précédent de topologie réseau montre trois régions réseau, chacune comportant un site central qui gère les décisions du service Contrôle d’admission des appels. Dans l’exemple précédent, l’association appropriée est indiquée dans le tableau ci-après.

<div>


> [!NOTE]  
> Les sites centraux ne correspondent pas nécessairement aux sites réseau. Dans les exemples de cette documentation, certains sites centraux (Chicago, Londres et Pékin) ont les mêmes noms que les sites réseau. Toutefois, même si un site central et un site réseau partagent le même nom, le site central est un élément de la topologie Lync Server, tandis que le site réseau fait partie du réseau global dans lequel réside la topologie Lync Server.



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>Régions réseau, sites centraux et sites réseau

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Région réseau</th>
<th>Site central</th>
<th>Sites réseau</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amérique du Nord</p></td>
<td><p>Renne</p></td>
<td><p>Renne</p>
<p>New York</p>
<p>Détroit</p>
<p>Agence</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>Londres</p></td>
<td><p>Londres</p>
<p>Cologne</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>Pékin</p></td>
<td><p>Pékin</p>
<p>Rigide</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>Identifier les sites réseau

Un site réseau représente un lieu physique pour votre organisation, par exemple des bureaux, un ensemble de bâtiments ou un campus. Tout lieu physique qui comporte un réseau local (LAN) et une connectivité de réseau étendu (WAN) vers d’autres sites est considéré comme un site réseau. Commencez par inventorier tous les bureaux de votre organisation. Dans notre exemple de topologie, la région réseau Amérique du Nord comporte les sites réseau suivants : New York, Chicago, Détroit, Portland, Reno et Albuquerque.

Vous devez associer chaque site réseau à une région réseau. Selon que le site réseau dispose d’une liaison réseau étendu restreinte, une stratégie de bande passante est associée au site réseau. Pour plus d’informations sur les stratégies de service Contrôle d’admission des appels et la bande passante que vous allouez en les utilisant, voir « Définir des stratégies de bande passante » plus loin dans cette rubrique. Pour configurer le service Contrôle d’admission des appels, associez des sites réseau à des régions réseau, puis créez des stratégies d’allocation de bande passante qui doivent être appliquées aux connexions à bande passante restreinte entre un site ou une région spécifique, mais aussi aux connexions réseau étendu entre des sites et des régions.

</div>

<div>

## <a name="identify-network-links"></a>Identifier des liaisons réseau

Les liaisons réseau représentent les connexions au réseau étendu physique qui relient différentes régions et différents sites. Dans notre exemple de topologie, il y a deux liaisons réseau régionales, cinq liaisons réseau entre des régions et des sites, et une liaison réseau entre deux sites.

Les deux liaisons régionales sont entre Amérique du Nord et EMEA, représentés par NA-EMEA-LINK, et entre APAC et EMEA, représentés par EMEA-APAC-LINK.

Les liaisons de sites sont indiquées par des traits connectant Portland, Reno et Albuquerque à la région Amérique du Nord, Manille à la région APAC, et Cologne à la région EMEA. Le trait entre Reno et Albuquerque indique une liaison réseau directe entre ces deux sites.

</div>

<div>

## <a name="define-bandwidth-policies"></a>Définir des stratégies de bande passante

Collaborez avec votre équipe responsable des opérations réseau pour déterminer la quantité de bande passante de réseau étendu mise à disposition du trafic audio et vidéo en temps réel sur les liaisons réseau étendu de votre organisation. Les stratégies de bande passante sont généralement appliquées aux liaisons réseau étendu si l’utilisation de la bande passante est restreinte ; c’est-à-dire, si on pense qu’elle sera supérieure à la bande passante pouvant être allouée aux modes audio et vidéo.

Les *stratégies de bande passante* du service Contrôle d’admission des appels définissent la bande passante maximale qui peut être réservée aux modes audio et vidéo en temps réel. Comme le service Contrôle d’admission des appels ne limite pas la bande passante d’un autre trafic de données, il ne peut pas empêcher les autres trafics de données (par exemple, un transfert de fichiers volumineux ou la diffusion en continu de morceaux de musique) d’utiliser toute la bande passante réseau.

Les stratégies de bande passante CAC peuvent définir un ou plusieurs des éléments suivants :

  - Bande passante totale maximale allouée à l’audio.

  - Bande passante totale maximale allouée à la vidéo.

  - Bande passante maximale allouée à un appel audio unique (session).

  - Bande passante maximale allouée à un appel vidéo unique (session).

<div>


> [!NOTE]  
> Toutes les valeurs de bande passante CAC représentent les limites de bande passante <EM>unidirectionnelle</EM> maximales.



</div>

<div>


> [!NOTE]  
> Les fonctionnalités de stratégie de voix Lync Server 2013 permettent de remplacer les vérifications de stratégie de bande passante pour les appels entrants vers l’utilisateur (pas pour les appels sortants passés par l’utilisateur). Une fois la session établie, la consommation de bande passante est calculée avec précision. Ce paramètre doit être utilisé avec modération. Pour plus d’informations, voir <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">créer une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

Pour optimiser l’utilisation de la bande passante par session, tenez compte du type des codecs audio et vidéo qui seront utilisés. Plus particulièrement, allouez suffisamment de bande passante pour un codec que vous pensez utiliser fréquemment. À l’inverse, si vous souhaitez empêcher le média d’utiliser un codec nécessitant davantage de bande passante, définissez une bande passante maximale par session qui soit suffisamment basse pour décourager ce type d’utilisation. Pour l’audio, tous les codecs ne sont pas disponibles pour chaque scénario. Par exemple :

  - Les appels audio P2P entre les points de terminaison Lync utiliseront RTAudio (8 kHz) ou RTAudio (16 kHz) lorsque vous factorerez la bande passante et la définition des priorités des codecs.

  - Les appels de conférence entre les points de terminaison Lync et le service de conférence A/V utiliseront G. 722 ou Siren.

  - Les appels vers le réseau téléphonique commuté (PSTN) vers ou à partir de points de terminaison Lync utiliseront G. 711 ou RTAudio (8 kHz).

Utilisez le tableau suivant pour optimiser les paramètres de bande passante par session maximale.

### <a name="bandwidth-utilization-by-codecs"></a>Utilisation de la bande passante par codecs

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec</th>
<th>Besoin en bande passante sans correction des erreurs de transfert (FEC)</th>
<th>Besoin en bande passante avec correction des erreurs de transfert (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8 kHz)</p></td>
<td><p>49,8 Kbits/s</p></td>
<td><p>61,6 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16 kHz)</p></td>
<td><p>67 Kbits/s</p></td>
<td><p>96 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57,6 Kbits/s</p></td>
<td><p>73,6 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>G. 711</p></td>
<td><p>102 Kbits/s</p></td>
<td><p>166 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>105,6 Kbits/s</p></td>
<td><p>169,6 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 i/s)</p></td>
<td><p>260 Kbits/s</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 i/s)</p></td>
<td><p>610 Kbits/s</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Les besoins en bande passante prennent en compte le traitement des éléments suivants : Ethernet II, IP, UDP (User Datagram Protocol), RTP (Real-Time Transport Protocol) et SRTP (Secure Real-Time Transport Protocol). Ils incluent également 10 Kbits/s pour le traitement RTCP.



</div>

Les codecs G.722.1 et Siren sont similaires, mais offrent différentes vitesses de transmission.

G. 722, le codec par défaut pour la Conférence Lync Server, est complètement différent des codecs G. 722.1 et Siren.

Le codec Siren est utilisé dans Lync Server dans les situations suivantes :

  - La stratégie de bande passante est définie sur une valeur trop basse pour permettre l’utilisation de G.722.

  - Si un client Communications Server 2007 ou Communications Server 2007 R2 se connecte à un service de conférence Lync Server (car ces clients ne prennent pas en charge le codec G. 722).

### <a name="bandwidth-utilization-by-scenario"></a>Utilisation de la bande passante par scénario

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario</th>
<th>Besoins en bande passante optimisés pour la quantité (Kbits/s)</th>
<th>Besoins en bande passante pour le mode équilibré (Kbits/s)</th>
<th>Besoins en bande passante optimisés pour la qualité (Kbits/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels audio d’égal à égal</p></td>
<td><p>45 Kbits/s</p></td>
<td><p>62 Kbits/s</p></td>
<td><p>91 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>Téléconférences</p></td>
<td><p>53 Kbits/s</p></td>
<td><p>101 Kbits/s</p></td>
<td><p>165 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>Appels RTC (entre Lync 2013 et la passerelle PSTN, avec déviation du trafic multimédia)</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>161 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>Appels RTC (entre Lync 2013 et le serveur de médiation sans déviation du trafic multimédia)</p></td>
<td><p>45 Kbits/s</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>161 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>Appels RTC (entre le serveur de médiation et la passerelle PSTN, sans déviation du trafic multimédia)</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>161 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>Appels Lync Polycom</p></td>
<td><p>101 Kbits/s</p></td>
<td><p>101 Kbits/s</p></td>
<td><p>101 Kbits/s</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.

Dans notre exemple, le site New York de la région Amérique du Nord se voit affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Supposons que Bob, qui travaille généralement à Détroit, se rende dans les bureaux de New York pour suivre une formation. Quand il allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages réservées à New York (par exemple, 172.29.80.103).

<div>


> [!WARNING]  
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour le contournement de média. Un client Lync prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels, mais pas le contournement de média, le contrôle d’admission des appels fonctionnera correctement même si vous configurez des sous-réseaux virtuels.)<BR>Par exemple, si un client se connecte sur un ordinateur dont l’adresse IP est 172.29.81.57 avec un masque de sous-réseau IP 255.255.255.0, Lync 2013 demande l’ID de contournement associé au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, bien que le client appartienne au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre des sous-réseaux exactement comme fournis par les clients Lync (qui sont configurés avec des sous-réseaux pendant la configuration du réseau, de façon statique ou par DHCP).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

