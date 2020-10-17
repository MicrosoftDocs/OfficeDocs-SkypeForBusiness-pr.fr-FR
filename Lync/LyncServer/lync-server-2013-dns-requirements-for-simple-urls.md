---
title: 'Lync Server 2013 : configuration DNS requise pour les URL simples'
description: 'Lync Server 2013 : configuration DNS requise pour les URL simples.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564960"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Configuration DNS requise pour les URL simples dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Lync Server 2013 prend en charge les URL simples qui facilitent la participation des réunions pour vos utilisateurs et facilitent l’accès aux outils d’administration de Lync Server pour vos administrateurs. Pour plus d’informations sur les URL simples, voir [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server prend en charge les trois URL simples suivantes : réunion, Conférence rendez-vous et administrateur. Vous devez configurer des URL simples pour la réunion et l’appel entrant, et l’URL simple d’administration est facultative. Les enregistrements DNS (Domain Name System) dont vous avez besoin pour prendre en charge les URL simples dépendent de la façon dont vous avez défini ces URL simples et si vous souhaitez prendre en charge la récupération d’urgence pour les URL simples.

<div>

## <a name="simple-url-option-1"></a>Option 1 de définition des URL simples

Dans l’option 1, vous devez créer une URL de base pour chaque URL simple.

<div class="">


> [!NOTE]  
> Lorsqu’un utilisateur clique sur un lien d’URL simple de réunion, le serveur que l’enregistrement DNS A résout détermine le logiciel client à démarrer. Une fois que le logiciel client a démarré, il communique automatiquement avec le pool hébergeant la conférence. Ainsi, les utilisateurs sont acheminés vers le serveur approprié indépendamment du serveur ou pool sur lequel les enregistrements DNS A d’URL simple sont résolus.



</div>

### <a name="simple-url-option-1"></a>Option 1 de définition des URL simples

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
<td><p>Satisfaction</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com , et ainsi de suite (une pour chaque domaine SIP de votre organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Appels entrants</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Administrateur</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Si vous utilisez l’Option 1, vous devez définir ce qui suit :

  - Pour chaque URL simple Meet, il est nécessaire de définir un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.
    
    Si votre organisation compte plusieurs domaines SIP et si vous utilisez cette option, vous devez créer des URL simples Meet pour chaque domaine SIP et créer un enregistrement DNS A pour chaque URL simple Meet. Par exemple, si vous avez à la fois contoso.com et fabrikam.com, vous allez créer des enregistrements DNS A pour les deux https://meet.contoso.com et https://meet.fabrikam.com .
    
    En outre, si vous disposez de plusieurs domaines SIP et si vous souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples, utilisez l’option 3 présentée plus loin dans cette rubrique.

  - Pour chaque URL simple Dial-In, il est nécessaire de créer un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.

  - L’URL simple Admin ne sert qu’en interne. Elle requiert un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.

</div>

<div>

## <a name="simple-url-option-2"></a>Option 2 de définition des URL simples

Avec l’Option 2, les URL simples Meet, Dial-in et Admin ont une URL de base commune, telle que lync.contoso.com. Ainsi, ces URL simples ne requièrent qu’un enregistrement DNS A pour résoudre lync.contoso.com en l’adresse IP du pool directeur ou du pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.

Notez que si votre organisation compte plusieurs domaines SIP, vous devez tout de même créer des URL simples Meet pour chaque domaine SIP et un enregistrement DNS A pour chaque URL simple Meet. Dans cet exemple, trois URL simples sont basées sur lync.contoso.com et une URL simple Meet supplémentaire est configurée avec une autre URL de base pour fabrikam.com. Dans cet exemple, vous devez créer des enregistrements DNS A pour les deux https://lync.contoso.com et https://lync.fabrikam.com . L’Option 3 présente une autre méthode de gestion des noms et des enregistrements DNS A si vous disposez de plusieurs domaines SIP.

### <a name="simple-url-option-2"></a>Option 2 de définition des URL simples

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
<td><p>Satisfaction</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet , et ainsi de suite (une pour chaque domaine SIP de votre organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Appels entrants</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrateur</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>Option 3 de définition des URL simples

L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples distinctes, mais souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples. Dans cet exemple, un seul enregistrement DNS A est nécessaire. Il est chargé de résoudre lync.contoso.com en l’adresse IP du pool directeur ou du pool frontal.

### <a name="simple-url-option-3"></a>Option 3 de définition des URL simples

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
<td><p>Satisfaction</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Appels entrants</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrateur</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Option de récupération d’urgence pour les URL simples

Si vous avez plusieurs sites qui contiennent des pools frontaux et que votre fournisseur DNS prend en charge GeoDNS, vous pouvez configurer vos enregistrements DNS pour des URL simples afin de prendre en charge la récupération d’urgence, de sorte que la fonctionnalité d’URL simple continue même si un pool frontal entier tombe en panne. Cette fonctionnalité de récupération d’urgence prend en charge les URL simples de conférence et d’accès à distance.

Pour configurer cette option, créez deux adresses GeoDNS. Chacune d’elles comprend deux enregistrements DNS A ou CNAME qui aboutissent à deux pools couplés à des fins de récupération d’urgence. Une adresse GeoDNS est utilisée pour l’accès interne et aboutit au nom de domaine complet web interne ou à l’adresse IP d’équilibrage de charge des deux pools. L’autre adresse GeoDNS est utilisée pour l’accès externe et aboutit au nom de domaine complet web externe ou à l’adresse IP d’équilibrage de charge des deux pools. L’exemple ci-dessous s’applique à l’URL simple Meet et utilise les noms de domaine complets des pools.

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

Créez ensuite des enregistrements CNAME qui font aboutir l’URL simple Meet (telles que meet.contoso.com) aux deux adresses GeoDNS.

<div class="">


> [!NOTE]  
> Si votre réseau utilise le <EM>hairpinning</EM> (routage de l’ensemble du trafic de l’URL simple via le lien externe, y compris le trafic en provenance de votre organisation), vous pouvez simplement configurer l’adresse GeoDNS externe et faire aboutir votre adresse URL simple Meet uniquement à cette adresse externe.



</div>

Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS de façon à distribuer les demandes aux deux pools selon la méthode du tourniquet (round robin), ou bien vous connecter principalement à un pool (par exemple, le pool le plus proche géographiquement) et utiliser l’autre pool seulement en cas de problème de connectivité.

Vous pouvez définir la même configuration pour l’URL simple Dial-In. Pour ce faire, créez des enregistrements supplémentaires comme ceux de l’exemple précédent, `dialin` en remplaçant `meet` les enregistrements DNS. Pour l’URL simple Admin, utilisez l’une des trois options mentionnées plus haut dans cette section.

Après avoir défini cette configuration, vous devez utiliser une application de surveillance pour configurer la recherche de défaillance via la surveillance HTTP. Pour l’accès externe, surveillez pour vous assurer que le protocole HTTPs obtient des demandes de découverte automatique pour le nom de domaine complet Web externe ou l’adresse IP du programme d’équilibrage de charge pour les deux pools. Par exemple, les demandes suivantes ne doivent pas contenir d’en-tête **ACCEPT** et doivent retourner **200 OK**.

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Pour l’accès interne, vous devez surveiller le port 5061 sur le nom de domaine complet web interne ou l’adresse IP d’équilibrage de charge pour les deux pools. Si des problèmes de connectivité sont détectés, l’adresse IP virtuelle de ces deux pools doit fermer les ports 80, 443 et 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

