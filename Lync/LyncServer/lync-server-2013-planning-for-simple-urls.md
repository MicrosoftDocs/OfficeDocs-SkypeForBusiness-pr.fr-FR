---
title: 'Lync Server 2013 : Planification des URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17dbfce9f699f31e09bb66d6d596e0a3cbf0ba96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planification des URL simples dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-12-11_

Les URL simples permettent de participer plus facilement à des réunions pour vos utilisateurs et permettent d’accéder plus facilement aux outils d’administration de Lync Server.

Lync Server prend en charge trois URL simples:

  - La **fonction réunion** est utilisée comme URL de base pour toutes les conférences du site ou de l’organisation. Par exemple, une URL de réunion simple https://meet.contoso.comest. Une URL pour une réunion particulière peut être https://meet.contoso.com/ *nom d’utilisateur*/7322994.
    
    Avec l’URL de la réunion, vous pouvez facilement comprendre les liens permettant de participer à des réunions, et facilement communiquer et diffuser.

  - Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous. Cette page présente les numéros de conférence rendez-vous avec les langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées), les commandes DTMF en conférence et prend en charge la gestion du numéro d’identification personnel ( Code confidentiel) et informations de conférence affectées. L’URL d’accès à un rendez-vous est incluse dans toutes les invitations à une réunion de sorte que les utilisateurs qui souhaitent se connecter à la réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Par exemple, l’URL de connexion simple est https://dialin.contoso.com.

  - L' **administrateur** vous permet d’accéder rapidement au panneau de configuration de Lync Server. À partir de n’importe quel ordinateur au sein des pare-feu de votre organisation, un administrateur peut ouvrir le panneau de configuration de Lync Server en entrant l’URL simple d’administration dans un navigateur. L’URL simple Admin est interne à votre organisation. Par exemple, l’URL d’administration simple esthttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Étendue d’URL simple

Vous pouvez configurer vos URL simples pour qu’elles aient une étendue globale ou spécifier différentes URL simples pour chaque site central de votre organisation. S’il s’agit d’une URL simple d’étendue globale et d’une URL simple d’étendue de site, l’URL d’étendue du site est prioritaire.

Dans la plupart des cas, nous vous conseillons de définir des URL simples uniquement au niveau global, de telle sorte que l’URL de la réunion n’est pas la même que celle d’un site à l’autre. Il peut s’agir d’organisations qui ont besoin d’utiliser différents numéros de téléphone pour les utilisateurs rendez-vous sur différents sites. Notez que si vous définissez une URL simple (par exemple, l’URL d’accès à la Conférence rendez-vous) sur un site, vous devez également définir d’autres URL simples sur ce site comme niveau de site.

<div>


> [!NOTE]  
> Si vous choisissez d’utiliser des URL simples à portée de site, vos utilisateurs ne seront pas en mesure de basculer entre les listes frontales sur les différents sites sans que les utilisateurs replanifient toutes leurs réunions planifiées, car les URL simples de la réunion sont différentes entre les sites. Cela inclut les scénarios de basculement dans lesquels les relations de sauvegarde se trouvent dans des sites distincts. Lorsque vous avez besoin de basculer entre les sites dans lesquels les URL simples de votre site sont déployées, les utilisateurs ne seront pas en mesure de rejoindre leurs réunions en raison de l’étendue de l’URL. Pour plus d’informations, consultez <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Vous pouvez définir des URL simples globales dans le générateur de topologie. Pour définir une URL simple au niveau du site, vous devez utiliser l’applet de cmdlet Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Attribution d’un nom à vos URL simples

Il existe trois options recommandées pour nommer vos URL simples. L’option que vous choisissez a des implications sur la configuration de vos enregistrements DNS A et des certificats qui prennent en charge des URL simples. Dans chaque option, vous devez configurer une seule URL de la réunion pour chaque domaine SIP de votre organisation.

Vous avez toujours besoin d’une seule URL dans l’ensemble de votre organisation pour le rendez-vous, et l’autre pour l’administrateur, quel que soit le nombre de domaines SIP.

Pour plus d’informations sur les enregistrements et les certificats DNS requis, voir [exigences DNS pour les URL simples dans Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) et les [certificats requis pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Dans l’option 1, vous créez un nouveau nom de domaine SIP pour chaque URL simple.

Si vous utilisez cette option, vous avez besoin d’un enregistrement DNS A distinct pour chaque URL simple et chaque URL de la réunion doit être nommée dans vos certificats.

### <a name="simple-url-naming-option-1"></a>Option de nom d’URL simple 1

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


Avec l’option 2, les URL simples sont basées sur le nom de domaine lync.contoso.com. Par conséquent, vous avez besoin d’un enregistrement DNS A qui active les trois types d’URL simples. Cet enregistrement DNS A fait référence à lync.contoso.com. Par ailleurs, vous avez encore besoin d’enregistrements DNS A séparés pour d’autres domaines SIP de votre organisation.

### <a name="simple-url-naming-option-2"></a>Option de nom d’URL simple 2

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


L’option 3 est particulièrement utile si vous avez de nombreux domaines SIP et que vous souhaitez qu’ils soient séparés par des URL simples et qu’ils souhaitent limiter les exigences d’enregistrements DNS et de certificats pour ces URL simples.

### <a name="simple-url-naming-option-3"></a>Option de nom d’URL simple 3

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
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrateur</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Règles de validation et d’attribution d’URL simples

Le générateur de topologie et les applets de contrôle Lync Server Management Shell appliquent plusieurs règles de validation pour vos URL simples. Vous devez définir des URL simples pour la réunion et le numéro de téléphone, mais la définition d’une pour l’administrateur est facultative. Chaque domaine SIP doit être doté d’une URL simple de connexion, mais vous n’avez besoin que d’une seule URL de composition unique et d’une URL simple d’administration pour l’ensemble de votre organisation.

Chaque URL simple de votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous n’avez pas pu définir lync.contoso.com/Meet comme URL simple de la Conférence). Les noms d’URL simples ne peuvent pas contenir le nom de domaine complet de l’un de vos groupes, https://FQDN:88/meet ni aucune information de port (par exemple, n’est pas autorisée). Toutes les URL simples doivent commencer par le préfixe https://.

Les URL simples peuvent contenir des caractères alphanumériques (c’est-à-dire, a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, les URL simples risquent de ne pas fonctionner comme prévu.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Modification d’URL simples après le déploiement

Si vous modifiez une URL simple après le déploiement initial, vous devez tenir compte de la façon dont le changement a un impact sur vos enregistrements DNS et les certificats pour les URL simples. Si la base d’une URL simple change, vous devez également modifier les enregistrements DNS et les certificats. Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com à Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com. Si vous avez changé l’URL simple https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingsà, l’url de base de Lync.contoso.com reste inchangée et aucune modification du DNS ou du certificat n’est nécessaire.

Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque réalisateur et serveur frontal pour enregistrer la modification.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

