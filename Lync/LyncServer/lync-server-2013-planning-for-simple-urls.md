---
title: 'Lync Server 2013 : Planification des URL simples'
TOCTitle: Planification des URL simples
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398287(v=OCS.15)
ms:contentKeyID: 49296472
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification des URL simples dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-12-11_

Grâce aux URL simples les utilisateurs peuvent rejoindre les réunions plus facilement et les administrateurs peuvent accéder aux outils d’administration Lync Server en un clin d’œil.

Lync Server prend en charge trois URL simples :

  - **Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation. Un exemple d’URL simple de réunion est https://meet.contoso.com. Une URL de réunion particulière serait https://meet.contoso.com/ *nomutilisateur* /7322994.
    
    Avec l’URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre, à communiquer et à distribuer.

  - **Dial-in** URL simple d’accès qui permet d’accéder à la page web des paramètres de conférence rendez-vous. Cette page indique les numéros d’accès aux conférences et les langues dans lesquels ils sont disponibles. Elle présente également les informations relatives aux conférences affectées aux utilisateurs (c’est-à-dire, pour les réunions qui ne doivent pas être planifiées) et comporte des contrôles DTMF à utiliser en cours de conférence. Enfin, elle permet aux utilisateurs de gérer leur code confidentiel et les informations relatives aux conférences qui leur ont été affectées. L’URL simple d’accès est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Un exemple d’URL simple d’accès est https://dialin.contoso.com.

  - **Admin** URL d’administration qui permet d’accéder rapidement au Panneau de configuration Lync Server. Depuis un ordinateur derrière les pare-feu de l’organisation, un administrateur peut ouvrir le Panneau de configuration Lync Server en tapant l’URL simple d’administration dans un navigateur. L’URL simple d’administration est interne à votre organisation. Un exemple d’URL simple d’administration est https://admin.contoso.com.

## Étendue des URL simples

Vous pouvez configurer les URL simples de sorte que leur étendue soit globale mais vous pouvez également spécifier des URL simples différentes pour chaque site central dans votre organisation. Si une URL simple globale et une URL simple de site sont spécifiées, l’URL simple de site prévaut.

Dans la plupart des cas, nous vous conseillons de définir des URL simples uniquement au niveau global, pour que l’URL simple de réunion d’un utilisateur ne change pas si celui-ci passe d’un site à un autre ; en revanche ne définissez pas d’URL globales pour les organisations qui doivent utiliser des numéros de téléphone différents pour les utilisateurs se trouvant dans différents sites. Notez que si vous définissez une URL simple (par exemple, une URL simple d’accès) en tant qu’URL simple de site pour un site, vous devez également définir les autres URL simples pour ce site en tant qu’URL simples de site.

Vous pouvez définir des URL simples globales dans le Générateur de topologie. En revanche, pour définir une URL simple de site, vous devez utiliser l’applet de commande Set-CsSimpleURLConfiguration.

## Dénomination des URL simples

Il existe trois options recommandées pour nommer les URL simples. L’option que vous choisissez influe sur la configuration des enregistrements et des certificats DNS A qui prennent en charge les URL simples. Dans chaque option, vous devez configurer une URL simple de réunion pour chaque domaine SIP dans votre organisation.

Dans votre organisation, une seule URL simple est nécessaire pour l’accès et une seule pour l’administration, quel que soit le nombre de domaines dont vous disposez.

Pour plus d’informations sur les enregistrements et les certificats DNS A nécessaires, reportez-vous à [Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) et [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Dans l’option 1, vous devez créer un nom de domaine SIP pour chaque URL simple.

Si vous utilisez cette option, vous devez prévoir un enregistrement DNS A distinct pour chaque URL simple et chaque URL simple de réunion doit être nommée dans les certificats.

### Option 1 de dénomination d’URL simple

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL simple</strong></p></td>
<td><p><strong>Exemple</strong></p></td>
</tr>
<tr class="even">
<td><p>Meet</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com et ainsi de suite (une URL pour chaque domaine SIP dans votre organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Appel entrant</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Avec l’option 2, les URL simples sont basées sur le nom de domaine lync.contoso.com. Par conséquent, vous n’avez besoin que d’un seul enregistrement DNS A pour les trois types d’URL simple. Cet enregistrement DNS A référence lync.contoso.com. Mais vous avez quand même besoin d’enregistrements DNS A distincts pour les autres domaines SIP dans votre organisation.

### Option 2 de dénomination d’URL simple

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL simple</strong></p></td>
<td><p><strong>Exemple</strong></p></td>
</tr>
<tr class="even">
<td><p>Meet</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet et ainsi de suite (une URL pour chaque domaine SIP dans votre organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Appel entrant</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples de réunion distinctes mais souhaitez réduire les enregistrements et les certificats DNS requis pour ces URL simples.

### Option 3 de dénomination d’URL simple

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL simple</strong></p></td>
<td><p><strong>Exemple</strong></p></td>
</tr>
<tr class="even">
<td><p>Meet</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Appel entrant</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


## Dénomination d’URL simple et règles de validation

Les applets de commande du Générateur de topologie et de Lync Server Management Shell appliquent plusieurs règles de validation pour les URL simples. Vous devez définir des URL simples pour les réunions et l’accès et éventuellement une URL pour l’administration. Chaque domaine SIP doit avoir une URL simple de réunion mais une seule URL simple est nécessaire pour l’accès et une seule pour l’administration dans toute l’organisation.

Chaque URL simple dans l’organisation doit avoir un nom unique. Ce nom ne peut pas être le préfixe d’une autre URL simple (par exemple, vous ne pouvez pas définir lync.contoso.com/Meet comme URL simple de réunion et lync.contoso.com/Meet/Dialin comme URL simple d’accès). Les noms d’URL simples ne peuvent pas contenir le nom de domaine complet d’un pool ou les informations relatives à un port (par exemple, https://FQDN:88/meet n’est pas autorisé). Toutes les URL simples doivent commencer par le préfixe https://.

Les URL simples peuvent uniquement contenir des caractères alphanumériques, c’est-à-dire a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, les URL simples peuvent ne pas fonctionner comme prévu.

## Modifications des URL simples après leur déploiement

Si vous modifiez une URL simple après son déploiement, vous devez savoir en quoi cette modification risque d’altérer les enregistrements et les certificats DNS pour les URL simples. Si la base d’une URL simple est modifiée, vous devez également modifier les enregistrements et les certificats DNS. Par exemple, si vous modifiez https://lync.contoso.com/Meet de sorte qu’elle devienne https://meet.contoso.com, l’URL de base change, lync.contoso.com est remplacé par meet.contoso.com. Par conséquent, vous devez modifier les enregistrements et les certificats DNS de sorte qu’ils fassent référence à meet.contoso.com. Si vous avez modifié l’URL simple, de sorte que https://lync.contoso.com/Meet devienne https://lync.contoso.com/Meetings, l’URL de base lync.contoso.com ne change pas. Il n’est donc pas nécessaire de modifier les enregistrements ou les certificats DNS.

Cependant, lorsque vous modifiez le nom d’une URL simple, vous devez exécuter **Enable-CsComputer** sur chaque directeur et serveur frontal pour enregistrer cette modification.

## Voir aussi

#### Concepts

[Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

