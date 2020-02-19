---
title: 'Lync Server 2013 : planification des URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85b01956d901d5c4060dc1cf14f9991fdfce261c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planification des URL simples dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-12-11_

Les URL simples facilitent la participation aux réunions pour vos utilisateurs et facilitent l’accès aux outils d’administration de Lync Server pour vos administrateurs.

Lync Server prend en charge trois URL simples :

  - **Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation. Un exemple d’URL simple de réunion est https://meet.contoso.com. Une URL pour une réunion particulière peut être https://meet.contoso.com/ *username*/7322994.
    
    Avec l’URL simple de réunion, les liens pour joindre des réunions sont faciles à comprendre, à communiquer et à distribuer.

  - **Dial-in** qui permet d’accéder à la page web Paramètres de conférence rendez-vous. Cette page affiche les numéros d’accès de conférence avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées) et les contrôles DTMF de conférence, et prend en charge la gestion du numéro d’identification personnel ( PIN) et les informations de conférence affectées. L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. Voici https://dialin.contoso.comun exemple de l’URL simple Dial-in.

  - L' **administrateur** permet un accès rapide au panneau de configuration Lync Server. À partir de n’importe quel ordinateur dans les pare-feu de votre organisation, un administrateur peut ouvrir le panneau de configuration Lync Server en tapant l’URL simple d’administration dans un navigateur. L’URL simple d’administration est interne à votre organisation. Un exemple d’URL simple admin esthttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Étendue des URL simples

Vous pouvez configurer les URL simples de sorte que leur étendue soit globale mais vous pouvez également spécifier des URL simples différentes pour chaque site central dans votre organisation. Si une URL simple d’étendue globale et une URL simple d’étendue de site sont spécifiées, l’URL simple de l’étendue du site a la priorité.

Dans la plupart des cas, nous vous conseillons de définir des URL simples uniquement au niveau global, pour que l’URL simple de réunion d’un utilisateur ne change pas si celui-ci passe d’un site à un autre ; en revanche ne définissez pas d’URL globales pour les organisations qui doivent utiliser des numéros de téléphone différents pour les utilisateurs se trouvant dans différents sites. Notez que si vous définissez une URL simple (par exemple une URL simple d’accès) en tant qu’URL simple de site pour un site, vous devez également définir les autres URL simples pour ce site en tant qu’URL simples de site.

<div>


> [!NOTE]  
> Si vous choisissez d’utiliser des URL simples d’étendue site, vos utilisateurs ne peuvent pas passer d’un pool frontal à un autre dans différents sites sans que ces utilisateurs replanifient toutes leurs réunions planifiées, car les URL simples de la réunion sont différentes d’un site à un autre. Cela inclut les scénarios de basculement lorsque les pools dans les relations de sauvegarde se trouvent dans des sites distincts. Lorsque vous devez basculer entre les sites où les URL simples d’étendue de site sont déployées, les utilisateurs ne peuvent pas participer à leurs réunions en raison de l’étendue de l’URL. Pour plus d’informations, consultez <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Vous pouvez définir des URL simples globales dans le générateur de topologie. En revanche, pour définir une URL simple de site, vous devez utiliser l’applet de commande Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Dénomination des URL simples

Il existe trois options recommandées pour nommer les URL simples. L’option que vous choisissez influe sur la configuration des enregistrements et des certificats DNS A qui prennent en charge les URL simples. Dans chaque option, vous devez configurer une URL simple de réunion pour chaque domaine SIP dans votre organisation.

Dans votre organisation, une seule URL simple est nécessaire pour l’accès et une seule pour l’administration, quel que soit le nombre de domaines dont vous disposez.

Pour plus d’informations sur les enregistrements et les certificats DNS A nécessaires, consultez la rubrique [DNS Requirements for simple URLs in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) et [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Dans l’option 1, vous devez créer un nom de domaine SIP pour chaque URL simple.

Si vous utilisez cette option, vous devez prévoir un enregistrement DNS A distinct pour chaque URL simple et chaque URL simple de réunion doit être nommée dans les certificats.

### <a name="simple-url-naming-option-1"></a>Option 1 de dénomination d’URL simple

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
<td><p>https://meet.contoso.com, https://meet.fabrikam.com, et ainsi de suite (une pour chaque domaine SIP de votre organisation)</p></td>
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


Avec l’option 2, les URL simples sont basées sur le nom de domaine lync.contoso.com. Par conséquent, vous n’avez besoin que d’un seul enregistrement DNS A pour les trois types d’URL simple. Cet enregistrement DNS A référence lync.contoso.com. Mais vous avez quand même besoin d’enregistrements DNS A distincts pour les autres domaines SIP dans votre organisation.

### <a name="simple-url-naming-option-2"></a>Option 2 de dénomination d’URL simple

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
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, et ainsi de suite (une pour chaque domaine SIP de votre organisation)</p></td>
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


L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples de réunion distinctes mais souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples.

### <a name="simple-url-naming-option-3"></a>Option 3 de dénomination d’URL simple

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
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrateur</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Dénomination d’URL simple et règles de validation

Le générateur de topologies et les applets de commande Lync Server Management Shell appliquent plusieurs règles de validation pour vos URL simples. Vous devez définir des URL simples pour les réunions et l’accès, et éventuellement une URL pour l’administration. Chaque domaine SIP doit avoir une URL simple de réunion mais une seule URL simple est nécessaire pour l’accès et une seule pour l’administration dans toute l’organisation.

Chaque URL simple de votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous ne pouvez pas définir lync.contoso.com/Meet comme votre URL simple de réunion et lync.contoso.com/Meet/Dialin comme votre URL simple de numérotation). Les noms d’URL simples ne peuvent pas contenir le nom de domaine complet de l’un de vos pools https://FQDN:88/meet , ni aucune information de port (par exemple, n’est pas autorisé). Toutes les URL simples doivent commencer par le préfixe https://.

Les URL simples peuvent uniquement contenir des caractères alphanumériques, c’est-à-dire a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, les URL simples peuvent ne pas fonctionner comme prévu.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Modifications des URL simples après leur déploiement

Si vous modifiez une URL simple après le déploiement initial, vous devez savoir comment la modification influe sur vos enregistrements DNS et les certificats pour les URL simples. Si la base d’une URL simple change, vous devez également modifier les enregistrements DNS et les certificats. Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com en Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com. Si vous avez modifié l’URL simple https://lync.contoso.com/Meet vers https://lync.contoso.com/Meetings, l’url de base de Lync.contoso.com reste la même, de sorte qu’aucune modification de certificat ou de DNS n’est nécessaire.

Chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque directeur et serveur frontal pour enregistrer la modification.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration DNS requise pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

