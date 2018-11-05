---
title: 'Lync Server 2013 : Paramètres de négociation pour les partenaires fédérés XMPP'
TOCTitle: Paramètres de négociation pour les partenaires fédérés XMPP
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ552456(v=OCS.15)
ms:contentKeyID: 49299266
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les paramètres des types de négociation dans la configuration d’un partenaire XMPP offrent de nombreuses combinaisons possibles. Toutes ne sont pas correctes. Le tableau détaillé dans cette rubrique définit les paramètres corrects et incorrects. Les configurations courantes sont présentées dans le premier tableau, le deuxième tableau détaillant toutes les combinaisons possibles. Notez que vous ne pouvez avoir *Simple Authentication and Security Layer* (SASL) **que si***Transport Layer Security* (TLS) est également disponible. SASL est envoyé dans un format non chiffré (lisible) et ne doit jamais être transmis sans être protégé par un autre moyen, tel que TLS.

### Méthodes de négociation de fédération XMPP courantes

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
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Authentification de rappel</th>
<th>Méthode(s) d’authentification attendue(s)</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td><p>Définir TLS et SASL sur obligatoire permet de s’assurer que le flux de message SASL est sécurisé. Le rappel n’est pas disponible et ne peut pas être utilisé pour une méthode de remplacement si le partenaire fédéré XMPP n’a pas défini TLS sur obligatoire ou facultatif.</p></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>True</p></td>
<td><p>SASL sur TLS, Rappel TLS, Rappel TCP</p></td>
<td><p>En exigeant TLS, si le partenaire fédéré XMPP a défini SASL sur facultatif ou obligatoire, SASL est utilisé. Si SASL n’est pas disponible, le rappel sur TLS est utilisé.</p></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Facultatif</p></td>
<td><p>True</p></td>
<td><p>SASL sur TLS, Rappel TLS, Rappel TCP</p></td>
<td><p>Même s’ils sont très flexibles dans les méthodes de négociation offertes, ces paramètres dépendent des paramètres du partenaire de fédération XMPP. Si le partenaire a TLS défini sur facultatif ou obligatoire, mais que SASL n’est pas pris en charge, le rappel TLS sera disponible. Si le partenaire a TLS et SASL définis sur facultatif ou obligatoire, la sélection optimale de TLS sur SASL est utilisée.</p></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>True</p></td>
<td><p>Rappel TCP</p></td>
<td><p>Dans de nombreux cas, le rappel TCP constitue la seule solution possible. S’il est moins intéressant que d’autres options, il offre tout de même un certain niveau de confiance.</p></td>
</tr>
</tbody>
</table>


### Matrice de méthodes de négociation de fédération XMPP - Terminé

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
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Authentification de rappel</th>
<th>Méthode d’authentification attendue</th>
<th>Notes, avertissements ou erreurs pour configuration incorrecte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>True</p></td>
<td><p>SASL sur TLS</p></td>
<td>

> [!WARNING]  
> Le rappel ne fonctionne pas si SASL et TLS sont tous deux obligatoires.

</td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Obligatoire</p></td>
<td><p>True</p></td>
<td><p>SASL sur TLS, Rappel TLS, Rappel TCP</p></td>
<td>

> [!WARNING]  
> SASL nécessite TLS. Rendre TLS facultatif peut entraîner l’échec de négociations de session.

</td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td>


> [!WARNING]  
> SASL nécessite TLS. Rendre TLS facultatif peut entraîner l’échec de négociations de session.

</td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Obligatoire</p></td>
<td><p>True</p></td>
<td><p>Rappel TCP</p></td>
<td>

> [!WARNING]  
> SASL nécessite TLS. Rendre TLS facultatif peut entraîner l’échec de négociations de session.

</td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Obligatoire</p></td>
<td><p>False</p></td>
<td>

> [!WARNING]  
> Configuration incorrecte

</td>
<td>

> [!WARNING]  
> Puisque TLS est requis par SASL et qu’il n’est pas disponible, SASL/TLS ne peut pas aboutir. Le rappel TCP est défini sur false, et ne peut pas être utilisé.

</td>
</tr>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>True</p></td>
<td><p>SASL sur TLS, rappel TLS</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Facultatif</p></td>
<td><p>True</p></td>
<td><p>SASL sur TLS, Rappel TLS, Rappel TCP</p></td>
<td>

> [!WARNING]  
> SASL nécessite TLS. Rendre TLS facultatif peut entraîner l’échec de négociations de session.

</td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td><p>SASL sur TLS</p></td>
<td>

> [!WARNING]  
> SASL nécessite TLS. Rendre TLS facultatif peut entraîner l’échec de négociations de session.

</td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Facultatif</p></td>
<td><p>True</p></td>
<td><p>Rappel TCP</p></td>
<td>

> [!WARNING]  
> SASL nécessite TLS. Rendre TLS facultatif peut entraîner l’échec de négociations de session.

</td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Facultatif</p></td>
<td><p>False</p></td>
<td>

> [!WARNING]  
> Configuration incorrecte

</td>
<td>

> [!WARNING]  
> SASL nécessite TLS. Rendre TLS facultatif peut entraîner l’échec de négociations de session.

</td>
</tr>
<tr class="odd">
<td><p>Obligatoire</p></td>
<td><p>Non pris en charge</p></td>
<td><p>True</p></td>
<td><p>Rappel TLS</p></td>
<td><p>La configuration tient compte du rappel TLS.</p></td>
</tr>
<tr class="even">
<td><p>Obligatoire</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration incorrecte</p></td>
<td>

> [!WARNING]  
> SASL ou le rappel doit être activé.

</td>
</tr>
<tr class="odd">
<td><p>Facultatif</p></td>
<td><p>Non pris en charge</p></td>
<td><p>True</p></td>
<td><p>Rappel TLS, Rappel TCP</p></td>
<td><p>En fonction des choix de négociation de l’autre point de terminaison, la rappel TCP ou TLS sera accepté.</p></td>
</tr>
<tr class="even">
<td><p>Facultatif</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration incorrecte</p></td>
<td>

> [!WARNING]  
> SASL ou le rappel doit être activé.

</td>
</tr>
<tr class="odd">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>True</p></td>
<td><p>Rappel TCP</p></td>
<td><p>Le rappel TCP est la seule méthode de négociation disponible</p></td>
</tr>
<tr class="even">
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>False</p></td>
<td><p>Configuration incorrecte</p></td>
<td>

> [!WARNING]  
> SASL ou le rappel doit être activé.

</td>
</tr>
</tbody>
</table>

