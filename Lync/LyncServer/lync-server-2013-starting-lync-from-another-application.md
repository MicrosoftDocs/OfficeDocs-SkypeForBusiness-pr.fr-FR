---
title: 'Lync Server 2013: démarrage de Lync à partir d’une autre application'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Démarrage de Lync à partir d’une autre application

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-20_

Vous pouvez utiliser des paramètres de ligne de commande pour démarrer rapidement Lync 2013. Par exemple, si un utilisateur clique sur un numéro de téléphone dans une autre application, l’application peut démarrer une instance de Lync 2013 et lancer un appel vers ce numéro.

Lync 2013 peut également reconnaître une liste délimitée par des points-virgules de noms de contacts pour les conférences multipièces.

Si Lync 2013 est configuré de manière à se connecter automatiquement au démarrage, puis en démarrant Lync 2013 avec des paramètres de ligne de commande, vous ouvrez la fenêtre principale de Lync. Si Lync n’est pas configuré de manière à se connecter automatiquement au démarrage, la fenêtre de connexion s’ouvre.

Le tableau suivant répertorie les paramètres disponibles.

### <a name="lync-2013-command-line-parameters"></a>Paramètres de ligne de commande Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Long</th>
<th>Format des données</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel</p></td>
<td><p>URI tel</p></td>
<td><p>Ouvre la fenêtre de conversation pour un appel audio sans composer le numéro spécifié.</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>Tel:, SIP: ou URI tel de type</p></td>
<td><p>Ouvre la fenêtre de conversation pour un appel audio sans composer le numéro spécifié.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>URI SIP</p></td>
<td><p>Ouvre la fenêtre de conversation avec l’URI (Uniform Resource Identifier) SIP spécifié dans la liste des participants.</p></td>
</tr>
<tr class="even">
<td><p>Quels</p></td>
<td><p>URI SIP</p></td>
<td><p>Si Lync 2013 est configuré pour utiliser le protocole TLS (Transport Layer Security), fonctionne exactement comme pour SIP:. Si TLS n’est pas utilisé, affiche une boîte de dialogue informant l’utilisateur qu’un niveau de sécurité supérieur est requis.</p></td>
</tr>
<tr class="odd">
<td><p>donne</p></td>
<td><p>URI SIP de la Conférence à rejoindre</p></td>
<td><p>Si URI est Self, instancie le focus et affiche le focus uniquement. Dans le cas contraire, ouvre l’affichage de la liste, mais n’envoie pas d’invitation.</p></td>
</tr>
<tr class="even">
<td><p>Pseudo</p></td>
<td><p>URI SIP</p></td>
<td><p>Affiche une fenêtre de conversation par messagerie instantanée uniquement avec l’URI SIP. Accepte plusieurs URI SIP spécifiés entre crochets (&lt;&gt;) sans séparateur.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


Le tableau suivant contient des exemples de ces paramètres de ligne de commande.

### <a name="command-line-parameter-examples"></a>Exemples de paramètres de ligne de commande

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instanci</th>
<th>Conduit</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>Ouvre une seule vue de téléphone avec + 14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto: tel: + 14255550101</p></td>
<td><p>Ouvre une seule vue de téléphone avec + 14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Ouvre une seule vue de téléphone avec kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Ouvre une fenêtre de conversation avec kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Ouvre une fenêtre de conversation et affiche les options de participation à une réunion audio.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

