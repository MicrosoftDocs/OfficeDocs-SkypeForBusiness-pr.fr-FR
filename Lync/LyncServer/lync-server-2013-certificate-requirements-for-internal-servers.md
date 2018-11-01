---
title: 'Lync Server 2013 : Exigences de certificat pour les serveurs internes'
TOCTitle: Exigences de certificat pour les serveurs internes
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398094(v=OCS.15)
ms:contentKeyID: 49296103
ms.date: 02/18/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exigences de certificat pour les serveurs internes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-02-17_

Les serveurs internes qui exécutent Lync Server et qui requièrent des certificats sont les suivants : le serveur Standard Edition, le serveur frontal Enterprise Edition, le serveur de médiation et le directeur. Le tableau ci-dessous indique les certificats requis pour ces serveurs. Vous pouvez utiliser l’Assistant Certificat de Lync Server pour demander ces certificats.

> [!TIP]  
> Les certificats avec caractères génériques sont pris en charge pour les autres noms d’objets associés à des URL simples sur le pool de serveurs frontaux, le serveur frontal ou le directeur. Pour plus d’informations sur la prise en charge des certificats avec caractères génériques, reportez-vous à <a href="lync-server-2013-wildcard-certificate-support.md">Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013</a>.

Même si une autorité de certification d’entreprise interne est recommandée pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique. Pour obtenir la liste des autorités de certification publiques fournissant des certificats conformes aux exigences des communications unifiées et ayant conclu un partenariat avec Microsoft afin de garantir la compatibilité de leurs certificats avec l’Assistant Certificat de Lync Server, consultez l’article 929395 de la Base de connaissances Microsoft « Partenaires de certificat de communications unifiées pour Exchange Server et Communications Server », à l’adresse [http://go.microsoft.com/fwlink/?linkid=202834\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=202834%26clcid=0x40c).

Les communications avec d’autres applications et serveurs, comme Exchange 2013, nécessitent un certificat qui soit pris en charge par les autres applications et produits. Pour la version 2013, Lync Server 2013 et les autres produits serveur Microsoft, dont Exchange 2013 et SharePoint Server, prennent en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Pour plus d’informations, reportez-vous à [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou des opérations.

Pour les connexions établies à partir de clients exécutant système d’exploitation Windows 7, système d’exploitation Windows Server 2008, système d’exploitation Windows Server 2008 R2, système d’exploitation Windows Vista et Microsoft Lync Phone Edition, Lync Server 2013 inclut (mais ne requiert pas) la prise en charge des certificats signés à l’aide de la fonction de hachage de chiffrement SHA-256. Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.

Les tableaux suivants indiquent les certificats requis par rôle serveur pour les pools frontaux et les serveurs Standard Edition. Tous ces certificats sont des certificats de serveur web standard à clé privée non exportables.

Notez que l’utilisation améliorée de la clé (EKU) pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.

> [!NOTE]  
> Le nom convivial de chaque certificat doit être unique dans le magasin de l’ordinateur.

> [!NOTE]  
> Si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devrez les ajouter dans Autre nom du sujet du certificat.

### Certificats pour les serveurs Standard Edition Server

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
<th>Certificat</th>
<th>Nom du sujet/ Nom commun</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet (FQDN) du pool</p></td>
<td><p>Nom de domaine complet du pool et nom de domaine complet du serveur</p>
<p>Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</p></td>
<td><p>SN=se01.contoso.com ; SAN=se01.contoso.com</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
<td><p>Sur le serveur Standard Edition, le nom de domaine complet du serveur est le même que celui du pool.</p>
<p>L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</p>
<p>Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.</p></td>
</tr>
<tr class="even">
<td><p>Web interne</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p><ul><li><p>Nom de domaine complet web interne (qui est le même que celui du serveur)</p></li><li><p>URL simples Meet</p></li><li><p>URL simple Dial-in</p></li><li><p>URL simple Admin</p>
<p></p></li><li><p>Ou, une entrée de caractère générique pour les URL simples</p></li></ul>
<p></p></td>
<td><p>SN=se01.contoso.com ; SAN=se01.contoso.com ; SAN=meet.contoso.com ; SAN=meet.fabrikam.com ; SAN=dialin.contoso.com ; SAN=admin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=se01.contoso.com ; SAN=se01.contoso.com ; SAN=*.contoso.com</p></td>
<td><p>Vous ne pouvez pas remplacer le nom de domaine complet web interne dans le Générateur de topologie.</p>
<p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p><ul><li><p>Nom de domaine complet web externe</p></li><li><p>URL simple Dial-in</p></li><li><p>URL simples de réunion par domaine SIP</p></li><li><p>Ou, une entrée de caractère générique pour les URL simples</p></li></ul></td>
<td><p>SN=se01.contoso.com ; SAN=webcon01.contoso.com ; SAN=meet.contoso.com ; SAN=meet.fabrikam.com ; SAN=dialin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=se01.contoso.com ; SAN=webcon01.contoso.com ; SAN=*.contoso.com</p></td>
<td><p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
</tbody>
</table>


### Certificats pour les serveurs frontaux dans un pool frontal

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
<th>Certificat</th>
<th>Nom du sujet/ Nom commun</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Nom de domaine complet du pool et nom de domaine complet du serveur.</p>
<p>Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</p></td>
<td><p>SN=eepool.contoso.com ; SAN=eepool.contoso.com ; SAN=ee01.contoso.com</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
<td><p>L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</p>
<p>Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.</p></td>
</tr>
<tr class="even">
<td><p>Web interne</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Pour chaque élément suivant :</p><ul><li><p>Nom de domaine complet web interne (qui n’est PAS le même que celui du serveur)</p></li><li><p>Nom de domaine complet du serveur</p></li><li><p>Nom de domaine complet du pool Lync</p></li><li><p>URL simples Meet</p></li><li><p>URL simple Dial-in</p></li><li><p>URL simple Admin</p></li><li><p>Ou, une entrée de caractère générique pour les URL simples</p></li></ul>
<p></p></td>
<td><p>SN=ee01.contoso.com ; SAN=ee01.contoso.com ; SAN=meet.contoso.com ; SAN=meet.fabrikam.com ; SAN=dialin.contoso.com ; SAN=admin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=ee01.contoso.com ; SAN=ee01.contoso.com ; SAN=*.contoso.com</p></td>
<td><p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Pour chaque élément suivant :</p><ul><li><p>Nom de domaine complet web externe</p></li><li><p>URL simple Dial-in</p></li><li><p>URL simple Admin</p></li><li><p>Ou, une entrée de caractère générique pour les URL simples</p></li></ul></td>
<td><p>SN=ee01.contoso.com ; SAN=webcon01.contoso.com ; SAN=meet.contoso.com ; SAN=meet.fabrikam.com ; SAN=dialin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=ee01.contoso.com ; SAN=webcon01.contoso.com ; SAN=*.contoso.com</p></td>
<td><p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
</tbody>
</table>


### Certificats pour le directeur

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificat</th>
<th>Nom du sujet/ Nom commun</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet du pool directeur</p></td>
<td><p>Nom de domaine complet du directeur, nom de domaine complet du pool directeur</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</p></td>
<td><p>SN=dir-pool.contoso.com ; SAN=dir-pool.contoso.com ; SAN=dir01.contoso.com</p>
<p>Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
</tr>
<tr class="even">
<td><p>Web interne</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p><ul><li><p>Nom de domaine complet web interne (qui est le même que celui du serveur)</p></li><li><p>URL simples Meet</p></li><li><p>URL simple Dial-in</p></li><li><p>URL simple Admin</p></li><li><p>Ou, une entrée de caractère générique pour les URL simples</p></li></ul>
<p></p></td>
<td><p>SN=dir01.contoso.com ; SAN=dir01.contoso.com ; SAN=meet.contoso.com ; SAN=meet.fabrikam.com ; SAN=dialin.contoso.com ; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com ; SAN=dir01.contoso.com ; SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p><ul><li><p>Nom de domaine complet web externe</p></li><li><p>URL simple Dial-in</p></li><li><p>URL simple Admin</p></li><li><p>Ou, une entrée de caractère générique pour les URL simples</p></li></ul></td>
<td><p>Le nom de domaine complet du pool directeur doit être différent du pool de serveurs frontaux ou du serveur frontal.</p>
<p>SN=dir01.contoso.com ; SAN=directorwebcon01.contoso.com ; SAN=meet.contoso.com ; SAN=meet.fabrikam.com ; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com ; SAN=directorwebcon01.contoso.com ; SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


Si vous disposez d’un pool de serveurs de médiation autonomes, chaque serveur dans le pool nécessite les certificats répertoriés dans le tableau suivant. (Si vous colocalisez les serveurs de médiation avec les serveurs frontaux, les certificats répertoriés dans le tableau « Certificats pour les serveurs frontaux dans un pool frontal » plus haut dans cette rubrique suffisent.)

### Certificats pour les serveurs de médiation autonomes

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificat</th>
<th>Nom du sujet/ Nom commun</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Nom de domaine complet du pool</p>
<p>Nom de domaine complet du serveur membre du pool</p></td>
<td><p>SN=medsvr-pool.contoso.net ; SAN= medsvr-pool.contoso.net ; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### Certificats pour les Survivable Branch Appliances

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Certificat</th>
<th>Nom du sujet/ Nom commun</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet de l’appareil</p></td>
<td><p>SIP.&lt;sipdomain&gt; (une entrée nécessaire par domaine SIP)</p></td>
<td><p>SN=sba01.contoso.net ; SAN=sip.contoso.com ; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)

