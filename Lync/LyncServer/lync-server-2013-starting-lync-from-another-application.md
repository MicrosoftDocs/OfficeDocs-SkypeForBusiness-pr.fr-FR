---
title: Démarrage de Lync à partir d’une autre application
TOCTitle: Démarrage de Lync à partir d’une autre application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398376(v=OCS.15)
ms:contentKeyID: 53095424
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Démarrage de Lync à partir d’une autre application

 

_**Dernière rubrique modifiée :** 2015-03-09_

Vous pouvez utiliser les paramètres de ligne de commande pour démarrer rapidement Lync 2013. Par exemple, si un utilisateur clique sur un numéro de téléphone dans une autre application, l’application peut démarrer une instance de Lync 2013 et initier un appel à ce numéro.

Lync 2013 peut aussi reconnaître une liste de noms de contacts délimités par des points-virgules pour la conférence multipartie.

Si Lync 2013 est configuré pour la connexion automatique au démarrage, le démarrage de Lync 2013 à l’aide des paramètres de ligne de commande ouvre la fenêtre principale Lync. Si Lync n’est pas configuré pour la connexion automatique au démarrage, la fenêtre de connexion s’ouvre.

Le tableau suivant présente les paramètres disponibles.

### Paramètres de ligne de commande Lync 2013

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
<td><p>tel:</p></td>
<td><p>URI tel</p></td>
<td><p>Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</p></td>
</tr>
<tr class="even">
<td><p>callto:</p></td>
<td><p>tel:, sip: ou URI tel à taper</p></td>
<td><p>Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</p></td>
</tr>
<tr class="odd">
<td><p>sip:</p></td>
<td><p>URI SIP</p></td>
<td><p>Ouvre la fenêtre de conversation avec l’URI SIP spécifié dans la liste des participants.</p></td>
</tr>
<tr class="even">
<td><p>Sips:</p></td>
<td><p>URI SIP</p></td>
<td><p>Si Lync 2013 est configuré pour utiliser le protocole TLS (Transport Layer Security), fonctionne exactement comme sip:. Si TLS n’est pas utilisé, affiche une boîte de dialogue informant l’utilisateur qu’un niveau de sécurité supérieur est requis.</p></td>
</tr>
<tr class="odd">
<td><p>conf:</p></td>
<td><p>URI SIP de la conférence à rejoindre</p></td>
<td><p>Si l’URI est automatique, instancie le focus et affiche la vue tableau uniquement. Sinon, affiche la vue tableau mais n’envoie pas INVITE.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>im:</p></td>
<td><p>URI SIP</p></td>
<td><p>Affiche une fenêtre de conversation de messagerie instantanée uniquement avec l’URI SIP. Accepte plusieurs URI SIP spécifiés entre crochets pointus (&lt;&gt;) sans aucun séparateur.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


Le tableau suivant fournit des exemples de ces paramètres de ligne de commande.

### Exemples de paramètres de ligne de commande

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
<td><p>Tel:+14255550101</p></td>
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
<td><p>conf:sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Ouvre une fenêtre de conversation et affiche les options audio de participation à une réunion.</p></td>
</tr>
</tbody>
</table>

