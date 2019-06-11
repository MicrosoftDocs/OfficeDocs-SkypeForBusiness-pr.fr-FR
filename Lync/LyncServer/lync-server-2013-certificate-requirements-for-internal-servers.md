---
title: 'Lync Server 2013 : Exigences de certificat pour les serveurs internes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a3f1eb54321c6cac7548d282bd3cea31c3f24a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Exigences de certificat pour les serveurs internes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-02-17_

Les serveurs internes exécutant Lync Server et qui nécessitent des certificats incluent Standard Edition Server, Enterprise Edition front end Server, serveur de médiation et Director. Le tableau suivant répertorie les conditions requises pour les certificats pour ces serveurs. Vous pouvez utiliser l’Assistant certificat de serveur Lync pour demander ces certificats.

<div>


> [!TIP]  
> Les certificats génériques sont pris en charge pour les noms de remplacement d’objet associés aux URL simples sur le pool frontal, serveur frontal ou Director. Pour plus d’informations sur la prise en charge des certificats génériques, voir <A href="lync-server-2013-wildcard-certificate-support.md">prise en charge des certificats génériques dans Lync Server 2013</A>.



</div>

Même si une autorité de certification d’entreprise interne est recommandée pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique. Pour obtenir une liste des autorités de certification publiques qui fournissent des certificats qui répondent à des exigences spécifiques pour les certificats de communications unifiées (UC) et qui ont un partenariat avec Microsoft pour s’assurer qu’ils fonctionnent avec l’Assistant certificat de Lync Server, voir l’article connaissances Microsoft 929395 de base, «partenaires de certification de communications unifiées pour Exchange Server et Communications Server [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)» au.

La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits. Pour la version 2013, Lync Server 2013 et d’autres produits Microsoft Server, dont Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation Open (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Pour plus d’informations, reportez-vous à la section [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenariat dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.

Pour les connexions de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008, le système d’exploitation Windows Server 2008 R2, le système d’exploitation Windows Vista et Microsoft Lync Phone Edition, Lync Server 2013 prend en charge (mais pas requis) certificats signés à l’aide de la fonction de hachage de chiffrement SHA-256. Pour prendre en charge l’accès externe à l’aide de l’algorithme SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.

Les tableaux suivants illustrent les exigences de certificat par rôle de serveur pour les pools frontaux et les serveurs Standard Edition. Il s’agit d’un certificat de serveur Web standard, d’une clé privée, d’un serveur non transférable.

Notez que l’utilisation améliorée de la clé du serveur est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.

<div>


> [!NOTE]  
> Chaque nom convivial de certificat doit être unique dans le magasin d’ordinateurs.



</div>

<div>


> [!NOTE]  
> Si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devez l’ajouter dans le nom de l’autre nom de l’objet du certificat.



</div>

### <a name="certificates-for-standard-edition-server"></a>Certificats pour Standard Edition Server

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
<th>Nom de l’objet/nom usuel</th>
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
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
<td><p>Sur un serveur Standard Edition Server, le nom de domaine complet du serveur est identique au nom de domaine complet du pool.</p>
<p>L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</p>
<p>Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.</p></td>
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
<li><p>Ou une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Vous ne pouvez pas remplacer le FQDN Web interne dans le générateur de topologie.</p>
<p>Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web externe</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simples de réunion par domaine SIP</p></li>
<li><p>Ou une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Certificats pour serveur frontal dans un pool frontal

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
<th>Nom de l’objet/nom usuel</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Nom de domaine complet (FQDN) du pool et du nom de domaine complet du serveur.</p>
<p>Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</p>
<p>Si ce pool est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP que vous utilisez).</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </p>
<p>Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</p></td>
<td><p>L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</p>
<p>Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.</p></td>
</tr>
<tr class="even">
<td><p>Site Web interne</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web interne (qui N’EST PAS le même que celui du serveur)</p></li>
<li><p>Nom de domaine complet du serveur</p></li>
<li><p>Nom de domaine complet du pool Lync</p></li>
<li><p>URL simples Meet</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</p>
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
<li><p>Ou une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Utilisation d’un certificat de caractère générique :</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</p>
<p>Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Certificats pour Director

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
<th>Nom de l’objet/nom usuel</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet (FQDN) du pool de réalisateurs</p></td>
<td><p>Nom de domaine complet (FQDN) du réalisateur du pool</p>
<p>Si ce pool est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP que vous utilisez).</p></td>
<td><p>SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = DIR01. contoso. com</p>
<p>Si ce pool de directeurs est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous devez également disposer de SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</p></td>
</tr>
<tr class="even">
<td><p>Site Web interne</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web interne (qui est le même que celui du serveur)</p></li>
<li><p>Nom de domaine complet du serveur</p></li>
<li><p>Nom de domaine complet du pool Lync</p></li>
<li><p>URL simples Meet</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Web externe</p></td>
<td><p>Nom de domaine complet du serveur</p></td>
<td><p>Pour chaque élément suivant :</p>
<ul>
<li><p>Nom de domaine complet web externe</p></li>
<li><p>URL simple Dial-in</p></li>
<li><p>URL simple Admin</p></li>
<li><p>Ou une entrée de caractère générique pour les URL simples</p></li>
</ul></td>
<td><p>Le FQDN Web de Director doit être différent du serveur frontal ou du pool frontal.</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


Si vous disposez d’un pool de serveurs de médiation autonome, vous avez besoin des certificats répertoriés dans le tableau ci-dessous. Si vous collocate un serveur de médiation avec les serveurs frontaux, les certificats répertoriés dans le tableau «certificats pour le serveur frontal du pool frontal», plus haut dans cette rubrique sont suffisants.

### <a name="certificates-for-stand-alone-mediation-server"></a>Certificats pour un serveur de médiation autonome

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
<th>Nom de l’objet/nom usuel</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet du pool</p></td>
<td><p>Nom de domaine complet du pool</p>
<p>Nom de domaine complet du serveur de membres du pool</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Certificats pour l’appareil de branchement survivant

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
<th>Nom de l’objet/nom usuel</th>
<th>Autre nom du sujet</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>Nom de domaine complet de l’appareil</p></td>
<td><p>SIP. &lt;sipdomain&gt; (nécessite une entrée par domaine SIP)</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Voir aussi


[Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

