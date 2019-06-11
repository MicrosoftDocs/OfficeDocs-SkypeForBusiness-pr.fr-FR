---
title: DNS Summary-SIP, Fédération de XMPP et messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Résumé DNS-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-03-09_

Les enregistrements DNS (Domain Name System) requis pour la définition d’une Fédération auprès d’Office Communications Server ou de partenaires Lync Server sont déterminés par votre décision d’autoriser la découverte automatique de DNS de votre domaine par d’autres partenaires en perspective. Si vous publiez \_le sipfederationtls. \_TCP. * \<Nom\> de domaine SIP* Enregistrement SRV, tout autre domaine fédéré SIP peut «découvrir» votre Fédération. Vous pouvez contrôler quels domaines fédérés peuvent communiquer avec vous à l’aide des paramètres des domaines et des domaines bloqués dans le panneau de configuration de Lync Server, ou en définissant la configuration des domaines autorisés ou bloqués à l’aide de Lync Server Management Shell et du ** Obtenir**, **définir**, **nouveau**, **supprimer-CsAllowedDomain** et **-CsBlockedDomain** des cmdlets PowerShell. Pour plus d’informations sur la configuration de ces paramètres et l’utilisation des cmdlets PowerShell, voir les **Rubriques connexes** à la fin de cette rubrique.

La table de synthèse des enregistrements DNS représente les entrées nécessaires pour une Fédération ouverte ou détectable. Si vous ne voulez pas implémenter la découverte de la Fédération, vous pouvez décider de \_ne pas configurer le sipfederationtls. \_TCP. Enregistrement de *nom\> de domaine SIP. \<*

<div>


> [!IMPORTANT]
> Il existe des scénarios spécifiques dans lesquels vous devez disposer du _sipfederationtls. _ TCP. <EM> &lt;Nom&gt; de domaine SIP</EM> Enregistrement SRV, mais vous ne souhaitez pas disposer d’une Fédération détectable. Par exemple, vous avez déployé une mobilité pour vos utilisateurs. Le système de notifications de transmission mobile Clearinghouse (PNCH) est un type spécial de Fédération qui est utilisé pour les clients mobiles Microsoft Lync sur Apple iPhone ou iPad utilisant le client mobile Lync 2010 ou Windows Phone à l’aide des clients mobiles Lync 2010 mobile ou Lync 2013. _Sipfederationtls. _ TCP. <EM> &lt;Nom&gt; de domaine SIP</EM> L’enregistrement SRV est utilisé dans le cas d’une notification de mobilité et de transmission. Pour limiter ce problème et contrôler votre détectabilité, décochez la case <STRONG>activer la découverte de domaines partenaires</STRONG> pour désactiver la découverte.



</div>

Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, vous devez créer deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements au service Edge d’accès de votre serveur Edge ou de votre pool Edge.

Lorsque vous configurez DNS (Domain Name System) pour la connectivité de messagerie instantanée publique, vous constaterez que la configuration qui prend en charge les utilisateurs externes prend en charge la connectivité de messagerie instantanée publique. Si vous avez déjà configuré votre serveur Edge ou votre pool Edge, vous devez disposer des enregistrements DNS nécessaires à la prise en charge de la connectivité de messagerie instantanée publique.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Résumé DNS-Fédération SIP incluant la connectivité de messagerie instantanée publique


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
<th>Enregistrement d’adresse IP/nom de domaine complet</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5061 externes</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>L’interface externe du service Edge d’accès est requise pour une découverte automatique de votre Fédération auprès d’autres partenaires de Fédération potentiels, et est désignée sous le nom de «domaines SIP autorisés» (appelé Fédération avancée dans les versions antérieures). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</p>



> [!IMPORTANT]
> Cet enregistrement SRV est requis pour la mobilité et l’hébergement d’échanges de notifications de transmission. Dans les cas où il existe plusieurs domaines SIP, vous pouvez créer et publier un enregistrement SRV pour chaque domaine qui disposera de clients mobiles Lync. Le service de notifications de transmission et le service de notifications de type Apple peut ne pas fonctionner comme prévu s’il n’y a pas d’enregistrement SRV explicite pour chaque domaine SIP pris en charge par le déploiement.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS Summary-extensible Messaging and Presence Protocol (XMPP)


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
<th>Enregistrement d’adresse IP/nom de domaine complet</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP du service Edge d’accès ou du pool Edge. Répétez cette opération pour tous les domaines SIP internes avec Lync pour les utilisateurs pour lesquels le contact avec les contacts XMPP est autorisé via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, d’une stratégie de site à l’emplacement de l’utilisateur ou d’une stratégie utilisateur appliquée au Utilisateur compatible Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie partenaires fédérés de XMPP. Pour plus d’informations, voir rubriques supplémentaires dans la <strong>section Voir aussi</strong> .</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre serveur Edge ou pool d’hébergement de proxy XMPP</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de la fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configuration des notifications push dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

