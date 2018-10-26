---
title: "Résumé des certif. - Fédération SIP, XMPP et messagerie instantanée publique"
TOCtitle: "Résumé des certif. - Fédération SIP, XMPP et messagerie instantanée publique"
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49298094
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Fédération SIP, fédération XMPP et messagerie instantanée publique

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les certificats dont vous avez besoin pour la fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server correspondent aux certificats que vous configurez, demandez et assignez à votre serveur Edge.

Les exigences de certificat pour l’activation et l’établissement de communications avec des partenaires XMPP (Extensible Messaging and Presence Protocol) requièrent l’ajout d’entrées pour vos domaines XMPP. L’enregistrement qui est inclus sur le certificat en tant qu’autre nom de l’objet (SAN) est le domaine pouvant participer aux communications XMPP. Ce domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous voulez activer XMPP pour l’ensemble de votre domaine, ou des domaines enfants sélectionnés (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.

Avant de configurer des certificats pour la connectivité PIC (Public IM Connectivity), notez qu’ils ne sont en rien différents des certificats des autres types de fédération SIP ou même des certificats de serveur Edge standard, La seule exception concerne America Online qui nécessite une configuration de certificat unique. Outre l’utilisation améliorée de la clé du serveur habituelle, America Online requiert du ou des certificats (dans le cas d’un pool de serveurs Edge) qu’ils contiennent également l’utilisation améliorée de la clé du client. Cette dernière constitue un ajout au certificat et fait partie du certificat public externe attribué à votre serveur Edge.

Pour confirmer que vous disposez des certificats requis pour votre déploiement de serveur Edge, passez en revue les rubriques répertoriées dans la section **Voir aussi**.



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Nom du sujet</th>
<th>Autres noms du sujet (SAN)</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge d’accès/périmètre externe</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>

> [!NOTE]  
> Pour prendre en charge l’espace de noms XMPP contoso.com

<p>sip.fabrikam.com</p>

> [!NOTE]  
> Pour prendre en charge l’espace de noms SIP fabrikam.com


> [!NOTE]  
> Pour prendre en charge l’espace de noms XMPP fabrikam.com

</td>
<td><p>Le certificat doit provenir d’une autorité de certification publique et comporter l’utilisation améliorée de la clé du serveur et l’utilisation améliorée de la clé du client si la connectivité PIC (Public IM Connectivity) avec AOL doit être déployée. Le certificat est attribué aux interfaces de serveur Edge externes pour :</p>
<ul>
<li><p>service Edge d’accès</p></li>
<li><p>service Edge de conférence web</p></li>
<li><p>service Edge A/V</p></li>
</ul>

> [!NOTE]  
> Techniquement, un certificat n’est pas affecté à un serveur Edge A/V. Les communications et l’authentification sont sécurisées via le service MRAS (Media Relay Authentication Service), lequel utilise le certificat affecté à l’interface interne du serveur serveur Edge.

<p>Notez que les autres noms de sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez les entrées d’autres noms de sujet dont vous avez besoin pour les domaines SIP supplémentaires, ainsi que d’autres entrées que vous devez prendre en charge. Le nom de sujet est répliqué dans l’autre nom de sujet et doit être présent pour un fonctionnement correct.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Tâches

[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Concepts

[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Résumé des certificats - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Résumé des certificats - Serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Résumé des certificats - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[Résumé des certificats - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

