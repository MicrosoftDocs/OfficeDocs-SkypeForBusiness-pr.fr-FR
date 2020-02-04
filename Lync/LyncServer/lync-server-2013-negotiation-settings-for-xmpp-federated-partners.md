---
title: 'Lync Server 2013 : Paramètres de négociation pour les partenaires fédérés XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Les paramètres des types de négociations dans la configuration d’un partenaire XMPP possèdent une large gamme de combinaisons possibles. Toutes ces combinaisons ne sont pas valides. Le tableau décrit dans cette rubrique définit les paramètres valides et non valides. Les configurations courantes sont présentées dans la première table, la deuxième table présentant toutes les combinaisons possibles. Notez que vous ne pouvez pas utiliser *l’authentification simple et la couche de sécurité* (SASL) **, sauf si** le protocole TLS ( *Transport Layer Security* ) est également disponible. SASL est envoyé dans un format non chiffré (lisible) et ne doit jamais être transmis tant qu’il est protégé par un autre moyen, tel que TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Méthodes courantes de négociation de Fédération XMPP

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
<th>TLS (Transport Layer Security)</th>
<th>Authentification simple et couche de sécurité (SASL)</th>
<th>Authentification Dialback</th>
<th>Méthode (s) d’authentification attendue</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL via TLS</p></td>
<td><p>TLS et SASL requis permettent de s’assurer que le flux de messages SASL est sécurisé. Dialback n’est pas disponible et ne peut pas être utilisé pour une méthode de secours si le partenaire fédéré de XMPP n’a pas configuré TLS sur requis ou facultatif.</p></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL via TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>Par le biais du protocole TLS, si le partenaire fédéré XMPP a défini SASL sur l’option Optional ou Required SASL est utilisé. Si SASL n’est pas disponible, Dialback sur TLS sera utilisé.</p></td>
</tr>
<tr class="odd">
<td><p>Facultatif </p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL via TLS, TLS Dialback, TCP Dialback</p></td>
<td><p>S’ils sont très flexibles dans les méthodes de négociation proposées, ces paramètres dépendent des paramètres du partenaire de Fédération XMPP. Si les protocoles TLS sont facultatifs ou requis alors que SASL n’est pas pris en charge, les Dialback TLS seront disponibles. Si le partenaire utilise les protocoles TLS et SASL définis sur facultatif ou requis, la sélection optimale de TLS sur SASL est utilisée.</p></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>TCP Dialback</p></td>
<td><p>Dans de nombreux cas, TCP Dialback est la seule solution possible. Moins désirable que d’autres options, il fournit un certain niveau de confiance.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Matrice des méthodes de négociation de Fédération XMPP-complet

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
<th>TLS (Transport Layer Security)</th>
<th>Authentification simple et couche de sécurité (SASL)</th>
<th>Authentification Dialback</th>
<th>Méthode d’authentification attendue</th>
<th>Remarques, avertissement ou erreur pour une configuration incorrecte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>Vrai</p></td>
<td><p>SASL via TLS</p></td>
<td><div>

> [!WARNING]  
> Dialback ne fonctionnera pas si les protocoles SASL et TLS sont requis.


</div></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL via TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Obligatoire</p></td>
<td><p>Vrai</p></td>
<td><p>SASL via TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL nécessite le protocole TLS. L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.


</div></td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL via TLS</p></td>
<td><div>

> [!WARNING]  
> SASL nécessite le protocole TLS. L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.


</div></td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Obligatoire</p></td>
<td><p>Vrai</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL nécessite le protocole TLS. L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.


</div></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Configuration non valide


</div></td>
<td><div>

> [!WARNING]  
> Dans la mesure où SASL nécessite le protocole TLS et que TLS n’est pas disponible, la fonctionnalité SASL/TLS ne peut pas aboutir. TCP Dialback est défini sur false et ne peut pas être utilisé.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL via TLS, TLS Dialback</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td><p>SASL via TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Facultatif </p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL via TLS, TLS Dialback, TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL nécessite le protocole TLS. L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.


</div></td>
</tr>
<tr class="even">
<td><p>Facultatif </p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td><p>SASL via TLS</p></td>
<td><div>

> [!WARNING]  
> SASL nécessite le protocole TLS. L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.


</div></td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL nécessite le protocole TLS. L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.


</div></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Configuration non valide


</div></td>
<td><div>

> [!WARNING]  
> SASL nécessite le protocole TLS. L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>Dialback TLS</p></td>
<td><p>La configuration autorise Dialback TLS.</p></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration non valide</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback doit être activé.


</div></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>Dialback TLS, TCP Dialback</p></td>
<td><p>En fonction des choix de négociation des autres points de terminaison, les protocoles TCP ou TLS Dialback seront acceptés.</p></td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration non valide</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback doit être activé.


</div></td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>TCP Dialback</p></td>
<td><p>TCP Dialback est la seule méthode de négociation disponible.</p></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration non valide</p></td>
<td><div>

> [!WARNING]  
> SASL ou Dialback doit être activé.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

