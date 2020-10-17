---
title: 'Lync Server 2013 : démarrage de Lync à partir d’une autre application'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d10e70615083796baa0934c6291b377dcd18005
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519511"
---
# <a name="starting-lync-from-another-application"></a>Démarrage de Lync à partir d’une autre application

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Vous pouvez utiliser des paramètres de ligne de commande pour lancer rapidement Lync 2013. Par exemple, si un utilisateur clique sur un numéro de téléphone dans une autre application, l’application peut démarrer une instance de Lync 2013 et initier un appel à ce numéro.

Lync 2013 peut également reconnaître une liste de noms de contact délimités par des points-virgules pour les conférences à plusieurs.

Si Lync 2013 est configuré pour se connecter automatiquement lorsqu’il est démarré, le démarrage de Lync 2013 avec des paramètres de ligne de commande ouvre la fenêtre principale de Lync. Si Lync n’est pas configuré pour la connexion automatique au démarrage, la fenêtre de connexion s’ouvre.

Le tableau suivant présente les paramètres disponibles.

### <a name="lync-2013-command-line-parameters"></a>Paramètres de Command-Line Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Extension</th>
<th>Format des données</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Téléphone</p></td>
<td><p>URI tel</p></td>
<td><p>Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</p></td>
</tr>
<tr class="even">
<td><p>protocoles callto</p></td>
<td><p>tel:, sip: ou URI tel à taper</p></td>
<td><p>Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>URI SIP</p></td>
<td><p>Ouvre la fenêtre de conversation avec l’URI SIP spécifié dans la liste des participants.</p></td>
</tr>
<tr class="even">
<td><p>Câbles</p></td>
<td><p>URI SIP</p></td>
<td><p>Si Lync 2013 est configuré pour utiliser le protocole TLS (Transport Layer Security), fonctionne exactement comme SIP :. Si TLS n’est pas utilisé, affiche une boîte de dialogue informant l’utilisateur qu’un niveau de sécurité supérieur est requis.</p></td>
</tr>
<tr class="odd">
<td><p>CONF</p></td>
<td><p>URI SIP de la conférence à rejoindre</p></td>
<td><p>Si l’URI est automatique, instancie le focus et affiche la vue tableau uniquement. Sinon, affiche la vue tableau mais n’envoie pas INVITE.</p></td>
</tr>
<tr class="even">
<td><p>messagerie instantanée</p></td>
<td><p>URI SIP</p></td>
<td><p>Affiche une fenêtre de conversation de messagerie instantanée uniquement avec l’URI SIP. Accepte plusieurs URI SIP spécifiés entre chevrons ( &lt; &gt; ) sans séparateur.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


Le tableau suivant fournit des exemples de ces paramètres de ligne de commande.

### <a name="command-line-parameter-examples"></a>Exemples de paramètres de ligne de commande

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instance</th>
<th>Résultats</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tél : + 14255550101</p></td>
<td><p>Ouvre une vue téléphone uniquement avec +14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel:+ 14255550101</p></td>
<td><p>Ouvre une vue téléphone uniquement avec +14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Ouvre une vue téléphone uniquement avec kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Ouvre une fenêtre de conversation avec kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf : SIP :https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Ouvre une fenêtre de conversation et affiche les options de participation à une réunion.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

