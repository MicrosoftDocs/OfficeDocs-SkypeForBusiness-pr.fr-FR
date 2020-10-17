---
title: 'Lync Server 2013 : Résumé des certificats-connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512781"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Résumé des certificats-connectivité de messagerie instantanée publique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

Pour configurer des certificats pour la connectivité de messagerie instantanée publique, vous devez tout d’abord remarquer qu’il n’y a rien de différent des autres types de Fédération SIP ou même des certificats de serveur Edge standard, à la seule différence qu’America Online (AOL) nécessite une configuration de certificat unique. En plus de l’utilisation avancée de la clé (EKU) du serveur, America Online nécessite le certificat ou les certificats (dans le cas d’un pool de serveurs Edge) pour contenir également l’utilisation améliorée de la clé client. L’EKU client est un complément du certificat et fait partie du certificat public externe attribué à votre serveur Edge.

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Résumé du certificat – Connectivité PIC (Public IM Connectivity)


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
<th>Nom du sujet</th>
<th>Autres noms du sujet (SAN)/Ordre</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge externe/d’accès</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit provenir d’une autorité de certification publique et doit disposer de l’utilisation améliorée de l’étendue du serveur et de l’EKU client si la connectivité PIC avec AOL doit être déployée. Le certificat est affecté aux interfaces du serveur Edge externe pour les éléments suivants :</p>
<ul>
<li><p>service Edge d’accès</p></li>
<li><p>service Edge de conférence Web</p></li>
<li><p>Service Edge A/V</p></li>
</ul>
<p>Notez que les autres noms du sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez des entrées SAN selon les besoins liés aux autres domaines SIP et entrées que vous devez prendre en charge. Le nom du sujet est répliqué dans l’autre nom du sujet et doit être présent pour assurer un fonctionnement correct.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

