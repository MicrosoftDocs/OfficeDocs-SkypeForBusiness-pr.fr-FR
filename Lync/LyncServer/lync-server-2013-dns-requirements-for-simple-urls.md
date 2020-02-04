---
title: 'Lync Server 2013 : Enregistrements DNS requis pour les URL simples'
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
ms.openlocfilehash: bfc827a1cd48bdc6a7a15b8ba54f7ac451d1b352
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Enregistrements DNS requis pour les URL simples dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Lync Server 2013 prend en charge des URL simples qui simplifient la participation à des réunions pour vos utilisateurs et permettent d’accéder plus facilement aux outils d’administration de Lync Server. Pour plus d’informations sur les URL simples, voir [planification d’URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server prend en charge les trois URL simples suivantes : réunion, accès et administration. Vous devez configurer des URL simples pour la réunion et le rendez-vous, et l’URL simple d’administration est facultative. Les enregistrements DNS (Domain Name System) nécessaires à la prise en charge d’URL simples dépendent de la façon dont vous avez défini ces URL simples et de la prise en charge de la reprise après sinistre pour des URL simples.

<div>

## <a name="simple-url-option-1"></a>Option d’URL simple 1

Dans l’option 1, vous créez une nouvelle URL de base pour chaque URL simple.

<div class="">


> [!NOTE]  
> Lorsqu’un utilisateur clique sur un lien de réunion d’URL simple, le serveur résolu par l’enregistrement DNS pour déterminer le logiciel client approprié à démarrer. Lorsque le logiciel client est démarré, il communique automatiquement avec le pool sur lequel la Conférence est hébergée. De cette façon, les utilisateurs sont dirigés vers le serveur approprié pour le contenu de la réunion, quel que soit le serveur ou le pool sur lequel les enregistrements sont résolus.



</div>

### <a name="simple-url-option-1"></a>Option d’URL simple 1

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
<td><p>Correspondre</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.comet ainsi de suite (un pour chaque domaine SIP de votre organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Rendez-vous</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Administrateur</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Si vous utilisez l’option 1, vous devez définir les éléments suivants :

  - Pour chaque URL de la réunion, vous avez besoin d’un enregistrement DNS A qui résout l’URL en adresse IP du directeur, si vous en avez déployé une. Dans le cas contraire, elle doit résoudre vers l’adresse IP de l’équilibrage de charge d’un pool frontal. Si vous n’avez pas déployé de pool et que vous utilisez un déploiement Standard Edition Server, l’enregistrement DNS A doit résoudre vers l’adresse IP d’un serveur Standard Edition au sein de votre organisation.
    
    Si vous avez plusieurs domaines SIP au sein de votre organisation et que vous utilisez cette option, vous devez créer des URL d’URL simples pour chaque domaine SIP et vous avez besoin d’un enregistrement DNS A pour chaque URL de la réunion. Par exemple, si vous avez à la fois contoso.com et fabrikam.com, vous devez créer des enregistrements DNS https://meet.contoso.com A https://meet.fabrikam.compour les deux et.
    
    Par ailleurs, si vous avez plusieurs domaines SIP et que vous souhaitez réduire les exigences d’enregistrements DNS et de certificats pour ces URL simples, utilisez l’option 3 décrite plus loin dans cette rubrique.

  - Dans le cas de l’URL d’accès à la Conférence rendez-vous, vous avez besoin d’un enregistrement DNS A qui résout l’URL vers l’adresse IP du réalisateur, si vous en avez déployé une. Dans le cas contraire, elle doit résoudre vers l’adresse IP de l’équilibrage de charge d’un pool frontal. Si vous n’avez pas déployé de pool et que vous utilisez un déploiement Standard Edition Server, l’enregistrement DNS A doit résoudre vers l’adresse IP d’un serveur Standard Edition au sein de votre organisation.

  - L’URL simple d’administration est réservée à un usage interne. Il nécessite un enregistrement DNS A qui résout l’URL vers l’adresse IP du directeur, si vous en avez déployé une. Dans le cas contraire, elle doit résoudre vers l’adresse IP de l’équilibrage de charge d’un pool frontal. Si vous n’avez pas déployé de pool et que vous utilisez un déploiement Standard Edition Server, l’enregistrement DNS A doit résoudre vers l’adresse IP d’un serveur Standard Edition au sein de votre organisation.

</div>

<div>

## <a name="simple-url-option-2"></a>Option d’URL simple 2

Avec l’option 2, les URL de base, de conférence rendez-vous et d’administration, telles que lync.contoso.com. Par conséquent, vous n’avez besoin que d’un seul enregistrement DNS pour ces URL simples, ce qui a pour effet de répartir lync.contoso.com vers l’adresse IP d’un pool de réalisateurs ou d’un pool frontal. Si vous n’avez pas déployé de pool et que vous utilisez un déploiement Standard Edition Server, l’enregistrement DNS A doit résoudre vers l’adresse IP d’un serveur Standard Edition au sein de votre organisation.

Notez que si vous avez plusieurs domaines SIP dans votre organisation, vous devez quand même créer des URL simples pour chaque domaine SIP et vous avez besoin d’un enregistrement DNS A pour chaque URL de la réunion. Dans cet exemple, alors que trois URL simples sont basées sur lync.contoso.com, une URL simple de l’interface de fabrikam.com est configurée avec une autre URL de base. Dans cet exemple, vous devez créer des enregistrements DNS A pour https://lync.contoso.com les https://lync.fabrikam.comdeux et. L’option simple d’URL 3 vous permet d’utiliser une autre méthode pour gérer l’attribution de noms et les enregistrements DNS A si vous avez plusieurs domaines SIP.

### <a name="simple-url-option-2"></a>Option d’URL simple 2

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
<td><p>Correspondre</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meetet ainsi de suite (un pour chaque domaine SIP de votre organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Rendez-vous</p></td>
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

## <a name="simple-url-option-3"></a>Option d’URL simple 3

L’option 3 est particulièrement utile si vous avez de nombreux domaines SIP et que vous souhaitez qu’ils disposent d’URL simples distinctes et qu’ils souhaitent limiter les exigences d’enregistrements DNS et de certificats pour ces URL simples. Dans cet exemple, vous avez besoin d’un enregistrement DNS A unique, qui résout lync.contoso.com sur l’adresse IP d’un pool de réalisateurs ou d’une liste frontale.

### <a name="simple-url-option-3"></a>Option d’URL simple 3

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
<td><p>Correspondre</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Rendez-vous</p></td>
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

## <a name="disaster-recovery-option-for-simple-urls"></a>Option de reprise après sinistre pour les URL simples

Si vous disposez de plusieurs sites et que votre fournisseur DNS prend en charge GeoDNS, vous pouvez configurer vos enregistrements DNS pour des URL simples afin de prendre en charge la reprise après sinistre, afin que la fonctionnalité d’URL n’intervient qu’à la fin de l’exécution d’un pool frontal complet. Cette fonctionnalité de reprise après sinistre prend en charge les URL de la réunion et du rendez-vous simples.

Pour le configurer, créez deux adresses GeoDNS. Chaque adresse possède deux enregistrements DNS A ou CNAMe qui sont résolus en deux regroupements qui sont associés à des fins de récupération par sinistre. Une adresse GeoDNS est utilisée pour l’accès interne et est résolue vers l’adresse IP du nom de domaine complet ou du nom de domaine complet (FQDN) du site Web interne. L’autre adresse GeoDNS est utilisée pour l’accès externe et est résolue sur l’adresse IP de nom de domaine complet ou du nom de domaine complet des deux pools. Voici un exemple de l’URL de la réunion, en utilisant les noms de domaine complets (FQDN) pour les pools.

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

Ensuite, créez des enregistrements CNAMe qui résolvent votre URL de réunion simple (par exemple, meet.contoso.com) sur les deux adresses GeoDNS.

<div class="">


> [!NOTE]  
> Si votre réseau utilise <EM>Hairpinning</EM> (le routage de tout le trafic d’URL par le biais du lien externe, y compris le trafic qui provient de votre organisation), vous pouvez simplement configurer l’adresse GeoDNS externe et résoudre votre URL de la réunion pour qu’elle utilise uniquement cette adresse externe.



</div>

Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS pour utiliser une méthode de tourniquet circulaire pour distribuer les demandes aux deux pools, ou pour vous connecter principalement à un pool (par exemple, le pool localisé plus près) et utiliser l’autre pool uniquement en cas de échec de connectivité.

Vous pouvez configurer la même configuration pour l’URL d’accès à la Conférence rendez-vous. Pour ce faire, créez des enregistrements supplémentaires comme ceux de l’exemple précédent, `dialin` `meet` en remplaçant les enregistrements DNS. Pour l’URL simple d’administration, utilisez l’une des trois options indiquées plus haut dans cette section.

Une fois cette configuration configurée, vous devez utiliser une application de surveillance pour configurer la surveillance HTTP et surveiller les échecs. Pour un accès externe, assurez-vous que les demandes de découverte automatique associées à l’adresse IP du nom de domaine complet ou du nom de domaine complet des deux pools sont correctes. Par exemple, les requêtes suivantes ne doivent pas contenir d’en-tête **Accept** et doivent retourner **200 OK**.

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

Pour un accès interne, vous devez surveiller le port 5061 sur l’adresse IP du nom de domaine complet (FQDN) du site Web interne ou du solde de charge des deux pools. Si des échecs de connectivité sont détectés, l’adresse VIP de ces groupes doit fermer les ports 80, 443 et 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

