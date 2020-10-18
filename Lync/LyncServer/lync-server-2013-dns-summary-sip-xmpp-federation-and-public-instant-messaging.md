---
title: Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique
description: Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40013b8346cc049f844a827b21bef81a66f6950
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572760"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-03-09_

Les enregistrements DNS (Domain Name System) requis pour la définition d’une Fédération avec Office Communications Server ou les partenaires Lync Server sont déterminés par votre décision d’autoriser la découverte automatique de DNS de votre domaine par d’autres partenaires en perspective. Si vous publiez le \_ sipfederationtls. \_ TCP. *\<SIP domain name\>* Enregistrement SRV, tout autre domaine fédéré SIP pourra « détecter » votre Fédération. Vous pouvez contrôler les domaines fédérés pouvant communiquer avec vous en utilisant les paramètres domaines et domaines bloqués dans le panneau de configuration Lync Server, ou en définissant la configuration des domaines autorisés ou bloqués à l’aide de Lync Server Management Shell et des applets de commande PowerShell **Get**, **Set**, **New**, **Remove-CsAllowedDomain** et **-applet csblockeddomain** . Pour plus d’informations sur la configuration de ces paramètres et l’utilisation des applets de commande PowerShell, consultez les **Rubriques connexes** à la fin de cette rubrique.

Le tableau récapitulatif des enregistrements DNS décrit les entrées requises pour une fédération ouverte (détectable). Si vous ne souhaitez pas implémenter la découverte de Fédération, vous pouvez décider de ne pas configurer le \_ sipfederationtls. \_ TCP. *\<SIP domain name\>* enregistrement.

<div>


> [!IMPORTANT]
> Il existe des scénarios spécifiques dans lesquels vous devez disposer de l' _sipfederationtls. _ TCP. Enregistrement SRV de <EM> &lt; &gt; nom de domaine SIP</EM> , mais vous ne souhaitez pas avoir une Fédération découvrable. Une telle instance est l’endroit où vous avez déployé la mobilité pour vos utilisateurs. Le centre de notifications mobiles Mobility (échanges) est un type spécial de Fédération utilisé pour les clients mobiles Microsoft Lync sur un iPhone ou un iPad Apple à l’aide du client mobile Lync 2010 ou de Windows Phone à l’aide des clients mobiles Lync 2010 mobile ou Lync 2013. _Sipfederationtls. _ TCP. L’enregistrement SRV de <EM> &lt; &gt; nom de domaine SIP</EM> est utilisé en cas de mobilité et de notification de transmission. Pour atténuer ce problème et contrôler votre détectabilité, désactivez la case à <STRONG>coactivation activer la découverte du domaine partenaire</STRONG> pour désactiver la découverte.



</div>

Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, vous devez créer deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements vers le service Edge d’accès de votre serveur Edge ou pool de serveurs Edge.

Lorsque vous configurez DNS (Domain Name System) pour la connectivité de messagerie instantanée publique, vous constaterez que la configuration qui prend en charge les utilisateurs externes prend en charge la connectivité PIC. Si vous avez déjà configuré votre serveur Edge ou votre pool de serveurs Edge, vous devez disposer des enregistrements DNS nécessaires à la prise en charge de la connectivité PIC.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Résumé des enregistrements DNS-Fédération SIP, y compris la connectivité de messagerie instantanée publique


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/port</th>
<th>FQDN</th>
<th>Adresse IP/Enregistrement d’hôte FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service Edge d’accès requise pour la découverte automatique de DNS de votre Fédération auprès des autres partenaires de Fédération potentiels, et appelée « domaines SIP autorisés » (appelée fédération étendue dans les versions précédentes). Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync.</p>



> [!IMPORTANT]
> Cet enregistrement SRV est requis pour la mobilité et le centre d’échanges de notifications push. Dans les cas où il existe plusieurs domaines SIP, créez et publiez un enregistrement SRV pour chaque domaine qui aura des clients mobiles Lync. Le service de notifications et les services de notifications d’Apple ne fonctionnent pas comme prévu s’il n’existe pas d’enregistrement SRV explicite pour chaque domaine SIP pris en charge par le déploiement.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Résumé des enregistrements DNS-protocole XMPP (extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/port</th>
<th>FQDN</th>
<th>Adresse IP/Enregistrement d’hôte FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-server._tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez cette opération autant que nécessaire pour tous les domaines SIP internes avec des utilisateurs activés de Lync où les contacts XMPP sont autorisés dans la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, de la stratégie de site où se trouve l’utilisateur ou de la stratégie de l’utilisateur appliquée à l’utilisateur à extension Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP. Voir les rubriques de la <strong>section Voir aussi</strong> pour plus de détails</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre serveur Edge ou le pool de serveurs Edge qui héberge le proxy XMPP</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement (A ou AAAA) d’hôte.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de la Fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configuration des notifications de type transmission dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

