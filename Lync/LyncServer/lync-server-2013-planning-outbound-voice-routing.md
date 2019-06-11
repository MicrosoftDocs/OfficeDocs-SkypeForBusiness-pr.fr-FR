---
title: 'Lync Server 2013 : Planification du routage des communications vocales sortantes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5315b18e83b84980ff6d61e5385626e104a5e1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Planification du routage des communications vocales sortantes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Le routage des appels sortants s’applique aux appels destinés à une passerelle du réseau téléphonique commuté (PSTN), au Trunk ou au PBX (Private Branch Exchange). Lorsqu’un utilisateur place un appel, le serveur normalise le numéro de téléphone au format E. 164, si nécessaire, et tente de correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction de la chaîne de numérotation fournie. Les paramètres de serveur du tableau ci-dessous permettent de configurer la logique de routage des appels sortants.

### <a name="lync-server-outbound-call-routing-settings"></a>Paramètres de routage des appels sortants de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objet</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Plan de numérotation</p></td>
<td><p>Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé, en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels.</p></td>
</tr>
<tr class="even">
<td><p>Règle de normalisation</p></td>
<td><p>Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont acheminés vers chaque emplacement, utilisateur ou objet contact. La même chaîne de numérotation peut être interprétée et convertie différemment selon l’emplacement d’origine de la numérotation et la personne ou l’objet contact passant l’appel. Un ensemble de règles de normalisation associées à un emplacement particulier constitue un plan de numérotation.</p></td>
</tr>
<tr class="odd">
<td><p>Stratégie de voix</p></td>
<td><p>Une stratégie de voix associe un ou plusieurs enregistrements d’utilisation PSTN à un utilisateur ou groupe d’utilisateurs. Elle fournit également une liste de fonctionnalités d’appel que vous pouvez activer ou désactiver.</p></td>
</tr>
<tr class="even">
<td><p>Enregistrement d’utilisation PSTN</p></td>
<td><p>Un enregistrement d’utilisation PTSN indique une classe d’appel (interne, local ou longue distance) qui peut être passée par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation.</p></td>
</tr>
<tr class="odd">
<td><p>Itinéraire d’appel</p></td>
<td><p>Un itinéraire d’appel associe les numéros de téléphone cibles à des jonctions et des enregistrements d’utilisation PTSN spécifiques. Une passerelle PSTN est considérée comme une jonction.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Dans cette section

Cette section fournit des recommandations pour la configuration des paramètres de serveur de routage des appels sortants suivants:

  - <span></span>  
    [Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Stratégies de voix dans Lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Trunking SIP dans Lync Server 2013](lync-server-2013-sip-trunking.md)  
[Connexions SIP directes dans Lync Server 2013](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

