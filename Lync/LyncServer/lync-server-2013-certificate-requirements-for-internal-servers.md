---
title: 'Lync Server 2013 : conditions requises pour les certificats pour les serveurs internes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bd350a4b552d63b635f8ec5a25ed7803de4b55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Exigences de certificat pour les serveurs internes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-02-17_

Les serveurs internes qui exécutent Lync Server et qui nécessitent des certificats incluent le serveur Standard Edition, le serveur frontal Enterprise Edition, le serveur de médiation et le directeur. Le tableau suivant indique les certificats requis pour ces serveurs. Vous pouvez utiliser l’Assistant Certificat Lync Server pour demander ces certificats.

<div>


> [!TIP]  
> Les certificats génériques sont pris en charge pour les autres noms de sujet associés aux URL simples sur le pool frontal, le serveur frontal ou le directeur. Pour plus d’informations sur la prise en charge des certificats génériques, consultez la rubrique <A href="lync-server-2013-wildcard-certificate-support.md">générique Certificate support in Lync Server 2013</A>.



</div>

Bien qu’il soit recommandé d’utiliser une autorité de certification d’entreprise interne pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique. Pour obtenir la liste des autorités de certification publiques qui fournissent des certificats conformes aux exigences spécifiques pour les certificats de communications unifiées et qui ont conclu un partenariat avec Microsoft afin de s’assurer qu’ils fonctionnent avec l’Assistant Certificat Lync Server, consultez la base de connaissances Microsoft 929395, « partenaires de certificat de communications unifiées pour Exchange Server et Communications Server », à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).

La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits. Pour la version 2013, Lync Server 2013 et d’autres produits serveur Microsoft, y compris Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Pour plus d’informations, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.

Pour les connexions à partir de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008, le système d’exploitation Windows Server 2008 R2, le système d’exploitation Windows Vista et Microsoft Lync Phone Edition, Lync Server 2013 inclut la prise en charge de (mais pas exiger) les certificats signés à l’aide de la fonction de hachage cryptographique SHA-256. Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.

Les tableaux suivants indiquent les certificats requis par rôle serveur pour les pools frontaux et les serveurs Standard Edition Server. Tous ces certificats sont des certificats de serveur web standard à clé privée non exportables

Notez que l’utilisation avancée de la clé pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.

<div>


> [!NOTE]  
> Chaque nom convivial de certificat doit être unique dans le magasin de l’ordinateur.



</div>

<div>


> [!NOTE]  
> Si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devrez les ajouter dans l’autre nom de sujet du certificat.



</div>

### <a name="certificates-for-standard-edition-server"></a>Certificats pour les serveurs Standard Edition Server

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
<th>Nom du sujet/nom commun</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet (FQDN) du pool</p></td>
<td><p>Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur</p>
<p>Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</p></td>
<td><p>SN = SE01. contoso. com ; SAN = SE01. contoso. com</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
<td><p>Sur le serveur Standard Edition Server, le nom de domaine complet du serveur est le même que celui du pool.</p>
<p>L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</p>
<p>Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.</p></td>
</tr>
<tr class="even">
<td><p>Web interne</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web interne (qui est le même que celui du serveur)</p></li>
<li><p>URL simples Meet</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou, une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = *. contoso. com</p></td>
<td><p>Vous ne pouvez pas remplacer le nom de domaine complet Web interne dans le générateur de topologie.</p>
<p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web externe</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>Répondre aux URL simples par domaine SIP</p></li>
<li><p>Ou, une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = *. contoso. com</p></td>
<td><p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificats pour les serveurs frontaux dans un pool frontal

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
<th>Nom du sujet/nom commun</th>
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
<td><p>SN = EEpool. contoso. com ; SAN = EEpool. contoso. com ; SAN = ee01. contoso. com</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
<td><p>L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</p>
<p>Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.</p></td>
</tr>
<tr class="even">
<td><p>Web interne</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet Web interne (qui n’est pas le même que le nom de domaine complet du serveur)</p></li>
<li><p>Nom de domaine complet du serveur</p></li>
<li><p>Nom de domaine complet du pool Lync</p></li>
<li><p>URL simples Meet</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou, une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = *. contoso. com</p></td>
<td><p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web externe</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou, une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = *. contoso. com</p></td>
<td><p>Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Certificats pour le directeur

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
<th>Nom du sujet/nom commun</th>
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
<td><p>SN = dir-pool.contoso.com ; SAN = dir-pool.contoso.com ; SAN = DIR01. contoso. com</p>
<p>Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
</tr>
<tr class="even">
<td><p>Web interne</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web interne (qui est le même que celui du serveur)</p></li>
<li><p>Nom de domaine complet du serveur</p></li>
<li><p>Nom de domaine complet du pool Lync</p></li>
<li><p>URL simples Meet</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou, une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN = DIR01. contoso. com ; SAN = DIR01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</p>
<p>SN = DIR01. contoso. com ; SAN = DIR01. contoso. com SAN = *. contoso. com</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web externe</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou, une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>Le nom de domaine complet du directeur de site Web externe doit être différent du pool frontal ou du serveur frontal.</p>
<p>SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</p>
<p>SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = *. contoso. com</p></td>
</tr>
</tbody>
</table>


Si vous disposez d’un pool de serveurs de médiation autonomes, chaque serveur dans le pool nécessite les certificats répertoriés dans le tableau suivant. (Si vous colocalisez les serveurs de médiation avec les serveurs frontaux, les certificats répertoriés dans le tableau « Certificats pour les serveurs frontaux dans un pool frontal » plus haut dans cette rubrique suffisent).

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificats pour les serveurs de médiation autonomes

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
<th>Nom du sujet/nom commun</th>
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
<td><p>SN = medsvr-pool.contoso.net ; SAN = medsvr-pool.contoso.net ; SAN = medsvr01. contoso. net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificats pour les Survivable Branch Appliances

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
<th>Nom du sujet/nom commun</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet de l’appliance</p></td>
<td><p>SIP. &lt;sipdomain&gt; (nécessite une entrée par domaine SIP)</p></td>
<td><p>SN = sba01. contoso. net ; SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Voir aussi


[Prise en charge de certificat générique dans Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

