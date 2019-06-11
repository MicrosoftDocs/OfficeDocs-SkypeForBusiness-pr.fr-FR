---
title: 'Lync Server 2013: Résumé de certification-connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Résumé de certification-connectivité de messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-19_

Pour configurer des certificats pour la connectivité de messagerie instantanée publique, vous devez d’abord noter qu’il n’y a rien d’autre que d’autres types de Fédération SIP ou même des certificats de serveur Edge standard, à l’exception que America Online (AOL) nécessite une seule configuration de certificat. Outre l’utilisation améliorée de la clé avancée du serveur, America Online nécessite que le ou les certificats (dans le cas d’un pool de périphérie) contiennent également l’utilisation améliorée de l’utilisation du client. L’utilisation améliorée de l’utilisation du client est un ajout du certificat, qui fait partie du certificat public externe affecté à votre serveur Edge.

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Résumé de certification-connectivité de messagerie instantanée publique


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Nom de l’objet</th>
<th>Autres noms d’objet (SAN)/Order</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Périphérie externe/accès</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit faire partir d’une autorité de certification publique et doit disposer de l’utilisation de l’utilisation améliorée de l’utilisation du serveur et de l’utilisation améliorée de la messagerie instantanée pour le client. Le certificat est attribué aux interfaces du serveur Edge externe pour les éléments suivants:</p>
<ul>
<li><p>Service Edge d’accès</p></li>
<li><p>Service Edge de conférence web</p></li>
<li><p>Service Edge A/V</p></li>
</ul>
<p>Notez que les San sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie. Vous pouvez ajouter des entrées SAN selon vos besoins pour des domaines SIP supplémentaires et d’autres entrées que vous devez prendre en charge. Le nom du sujet est répliqué sur le SAN et doit être présent pour une opération correcte.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

