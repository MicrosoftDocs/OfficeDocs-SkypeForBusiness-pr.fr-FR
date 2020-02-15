---
title: 'Lync Server 2013 : paramètres de négociation pour les partenaires fédérés XMPP'
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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Les paramètres des types de négociation dans la configuration d’un partenaire XMPP possèdent un large éventail de combinaisons possibles. Toutes ces combinaisons ne sont pas valides. Le tableau détaillé de cette rubrique définit les paramètres valides et non valides. Les configurations courantes sont présentées dans le premier tableau, le second tableau détaillant toutes les combinaisons possibles. Notez que vous ne pouvez pas utiliser SASL ( *simple Authentication and Security Layer* ) **sauf si** le protocole TLS ( *Transport Layer Security* ) est également disponible. SASL est envoyé dans un format non chiffré (lisible) et ne doit jamais être transmis sauf s’il est protégé par un autre moyen, tel que TLS.

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
<th>Protocole TLS (Transport Layer Security)</th>
<th>Authentification SASL (Simple Authentication and Security Layer)</th>
<th>Authentification rappel</th>
<th>Méthode (s) d’authentification attendue (s)</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td><p>TLS et SASL sont nécessaires pour s’assurer que le flux de messages SASL est sécurisé. Rappel n’est pas disponible et ne peut pas être utilisé pour une méthode de secours si le partenaire fédéré XMPP n’a pas défini TLS sur obligatoire ou facultatif.</p></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL sur TLS, rappel TLS, TCP rappel</p></td>
<td><p>En exigeant TLS, si le partenaire fédéré XMPP a défini SASL sur Optional ou l’authentification SASL requise est utilisée. Si SASL n’est pas disponible, rappel over TLS est utilisé.</p></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL sur TLS, rappel TLS, TCP rappel</p></td>
<td><p>Bien que très flexible dans les méthodes de négociation proposées, ces paramètres s’appuient sur les paramètres du partenaire de Fédération XMPP. Si le partenaire a le protocole TLS facultatif ou obligatoire mais que SASL n’est pas pris en charge, les rappel TLS seront disponibles. Si le partenaire utilise TLS et SASL défini sur Optional ou Required, la sélection optimale de TLS sur SASL est utilisée.</p></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>TCP rappel</p></td>
<td><p>Dans de nombreux cas, le protocole TCP rappel est la seule solution possible. Moins souhaitable que d’autres options, il offre un niveau de confiance.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Matrice des méthodes de négociation de Fédération XMPP-terminé

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
<th>Protocole TLS (Transport Layer Security)</th>
<th>Authentification SASL (Simple Authentication and Security Layer)</th>
<th>Authentification rappel</th>
<th>Méthode d’authentification attendue</th>
<th>Remarques, avertissements ou erreurs pour une configuration non valide</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>Vrai</p></td>
<td><p>SASL sur TLS</p></td>
<td><div>

> [!WARNING]  
> Rappel ne fonctionne pas si SASL et TLS sont tous deux requis.


</div></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Obligatoire</p></td>
<td><p>Vrai</p></td>
<td><p>SASL sur TLS, rappel TLS, TCP rappel</p></td>
<td><div>

> [!WARNING]  
> SASL requiert TLS. Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.


</div></td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requiert TLS. Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.


</div></td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Obligatoire</p></td>
<td><p>Vrai</p></td>
<td><p>TCP rappel</p></td>
<td><div>

> [!WARNING]  
> SASL requiert TLS. Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.


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
> Étant donné que SASL requiert TLS et que TLS n’est pas disponible, SASL/TLS ne peut pas aboutir. TCP rappel est défini sur false et ne peut pas être utilisé.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL sur TLS, rappel TLS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>SASL sur TLS, rappel TLS, TCP rappel</p></td>
<td><div>

> [!WARNING]  
> SASL requiert TLS. Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.


</div></td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td><div>

> [!WARNING]  
> SASL requiert TLS. Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.


</div></td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Facultatif</p></td>
<td><p>Vrai</p></td>
<td><p>TCP rappel</p></td>
<td><div>

> [!WARNING]  
> SASL requiert TLS. Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.


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
> SASL requiert TLS. Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.


</div></td>
</tr>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>Rappel TLS</p></td>
<td><p>La configuration autorise la rappel TLS.</p></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration non valide</p></td>
<td><div>

> [!WARNING]  
> SASL ou rappel doit être activé.


</div></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>TLS rappel, TCP rappel</p></td>
<td><p>En fonction des choix de négociation de l’autre point de terminaison, les rappel TCP ou TLS seront acceptées.</p></td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration non valide</p></td>
<td><div>

> [!WARNING]  
> SASL ou rappel doit être activé.


</div></td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Vrai</p></td>
<td><p>TCP rappel</p></td>
<td><p>Le protocole TCP rappel est la seule méthode de négociation disponible</p></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration non valide</p></td>
<td><div>

> [!WARNING]  
> SASL ou rappel doit être activé.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

