---
title: 'Lync Server 2013 : Enregistrements DNS requis pour les URL simples'
TOCTitle: Enregistrements DNS requis pour les URL simples
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425874(v=OCS.15)
ms:contentKeyID: 49296929
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements DNS requis pour les URL simples dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lync Server 2013 prend en charge les URL simples, qui permettent aux utilisateurs de se joindre plus facilement aux réunions et aux administrateurs d’accéder plus facilement aux outils d’administration de Lync Server. Pour plus d’informations sur les URL simples, reportez-vous à [Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server prend en charge les trois URL simples suivantes : Meet, Dial-In et Admin. Vous devez configurer les URL simples Meet et Dial-In. La configuration de l’URL simple Admin est facultative. Les enregistrements DNS (Domain Name System) dont vous avez besoin pour assurer la prise en charge des URL simples dépendent de la façon dont vous avez défini ces URL simples et selon que vous voulez ou non prendre en charge la récupération d’urgence pour les URL simples.

## Option 1 de définition des URL simples

Dans l’option 1, vous devez créer une URL de base pour chaque URL simple.

> [!NOTE]  
> Lorsqu’un utilisateur clique sur un lien d’URL simple de réunion, le serveur que l’enregistrement DNS A résout détermine le logiciel client à démarrer. Une fois que le logiciel client a démarré, il communique automatiquement avec le pool hébergeant la conférence. Ainsi, les utilisateurs sont acheminés vers le serveur approprié indépendamment du serveur ou pool sur lequel les enregistrements DNS A d’URL simple sont résolus.

### Option 1 de définition des URL simples

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


Si vous utilisez l’Option 1, vous devez définir ce qui suit :

  - Pour chaque URL simple Meet, il est nécessaire de définir un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.
    
    Si votre organisation compte plusieurs domaines SIP et si vous utilisez cette option, vous devez créer des URL simples Meet pour chaque domaine SIP et créer un enregistrement DNS A pour chaque URL simple Meet. Par exemple, si votre organisation comporte les deux domaines contoso.com et fabrikam.com, vous devez créer des enregistrements DNS A à la fois pour https://meet.contoso.com et pour https://meet.fabrikam.com.
    
    En outre, si vous disposez de plusieurs domaines SIP et si vous souhaitez réduire les enregistrements et les certificats DNS requis pour ces URL simples, utilisez l’option 3 présentée dans la suite de cette rubrique.

  - Pour chaque URL simple Dial-In, il est nécessaire de créer un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.

  - L’URL simple Admin ne sert qu’en interne. Elle requiert un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.

## Option 2 de définition des URL simples

Avec l’Option 2, les URL simples Meet, Dial-in et Admin ont une URL de base commune, telle que lync.contoso.com. Ainsi, ces URL simples ne requièrent qu’un enregistrement DNS A pour résoudre lync.contoso.com en l’adresse IP du pool directeur ou du pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.

Notez que si votre organisation compte plusieurs domaines SIP, vous devez tout de même créer des URL simples Meet pour chaque domaine SIP et un enregistrement DNS A pour chaque URL simple Meet. Dans cet exemple, trois URL simples sont basées sur lync.contoso.com et une URL simple Meet supplémentaire est configurée avec une autre URL de base pour fabrikam.com. Dans cet exemple, vous devez créer des enregistrements DNS A à la fois pour https://lync.contoso.com et pour https://lync.fabrikam.com. L’Option 3 présente une autre méthode de gestion des noms et des enregistrements DNS A si vous disposez de plusieurs domaines SIP.

### Option 2 de définition des URL simples

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


## Option 3 de définition des URL simples

L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples distinctes, mais souhaitez réduire les enregistrements et les certificats DNS requis pour ces URL simples. Dans cet exemple, un seul enregistrement DNS A est nécessaire. Il est chargé de résoudre lync.contoso.com en l’adresse IP du pool directeur ou du pool frontal.

### Option 3 de définition des URL simples

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
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


## Option de récupération d’urgence pour les URL simples

Si plusieurs de vos sites contiennent des pools de serveurs frontaux et si votre fournisseur DNS prend en charge GeoDNS, vous pouvez configurer vos enregistrements DNS pour que les URL simples prennent en charge la récupération d’urgence. Ainsi, même si un pool de serveurs frontaux entier connaît une défaillance, la fonctionnalité d’URL simple sera toujours opérationnelle. Cette fonctionnalité de récupération d’urgence prend en charge les URL simples Meet et Dial-In.

Pour configurer cette option, créez deux adresses GeoDNS. Chacune d’elles comprend deux enregistrements DNS A ou CNAME qui aboutissent à deux pools couplés à des fins de récupération d’urgence. Une adresse GeoDNS est utilisée pour l’accès interne et aboutit au nom de domaine complet web interne ou à l’adresse IP d’équilibrage de charge des deux pools. L’autre adresse GeoDNS est utilisée pour l’accès externe et aboutit au nom de domaine complet web externe ou à l’adresse IP d’équilibrage de charge des deux pools. L’exemple ci-dessous s’applique à l’URL simple Meet et utilise les noms de domaine complets des pools.

```
Meet-int.geolb.contoso.com
    Pool1InternalWebFQDN.contoso.com
    Pool2InternalWebFQDN.contoso.com
```
```
Meet-ext.geolb.contoso.com
    Pool1ExternalWebFQDN.contoso.com
    Pool2ExternalWebFQDN.contoso.com
```    

Créez ensuite des enregistrements CNAME qui font aboutir l’URL simple Meet (telles que meet.contoso.com) aux deux adresses GeoDNS.

> [!NOTE]  
> Si votre réseau utilise le <em>hairpinning</em> (routage de l’ensemble du trafic de l’URL simple via le lien externe, dont le trafic en provenance de votre organisation), vous pouvez simplement configurer l’adresse GeoDNS externe et faire aboutir votre adresse URL simple Meet uniquement à cette adresse externe.

Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS de façon à distribuer les demandes aux deux pools selon la méthode du tourniquet (round robin), ou bien vous connecter principalement à un pool (par exemple, le pool le plus proche géographiquement) et utiliser l’autre pool seulement en cas de problème de connectivité.

Vous pouvez définir la même configuration pour l’URL simple Dial-In. Pour cela, créez des enregistrements supplémentaires tels que ceux de l’exemple précédent en remplaçant `meet` par `dialin` dans les enregistrements DNS. Pour l’URL simple Admin, utilisez l’une des trois options mentionnées plus haut dans cette section.

Après avoir défini cette configuration, vous devez utiliser une application de surveillance pour configurer la recherche de défaillance via la surveillance HTTP. Pour l’accès externe, procédez à une surveillance pour faire aboutir les demandes de découverte automatique HTTPS GET auprès du nom de domaine complet web externe ou de l’adresse IP d’équilibrage de charge pour les deux pools. Par exemple, les demandes suivantes ne doivent pas contenir d’en-tête **ACCEPT** et doivent renvoyer **200 OK**.

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

Pour l’accès interne, vous devez surveiller le port 5061 sur le nom de domaine complet web interne ou l’adresse IP d’équilibrage de charge pour les deux pools. Si des problèmes de connectivité sont détectés, l’adresse IP virtuelle de ces deux pools doit fermer les ports 80, 443 et 444.

