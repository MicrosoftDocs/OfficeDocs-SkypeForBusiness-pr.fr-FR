---
title: "Résumé des enr. DNS - Féd. SIP, XMPP et messagerie instantanée publique"
TOCtitle: "Résumé des enr. DNS - Féd. SIP, XMPP et messagerie instantanée publique"
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49296455
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des enregistrements DNS - Fédération SIP, fédération XMPP et messagerie instantanée publique

 

_**Dernière rubrique modifiée :** 2017-03-09_

Les enregistrements DNS nécessaires à la définition d’une fédération avec les partenaires Office Communications Server ou Lync Server varient selon que vous autorisez la découverte DNS automatique de votre domaine par d’autres partenaires. Si vous publiez l’enregistrement SRV \_sipfederationtls.\_tcp. *\<Nom de domaine SIP\>*, les autres domaines SIP fédérés pourront « découvrir » votre fédération. Vous pouvez choisir quels domaines fédérés sont autorisés à communiquer avec vous en utilisant les paramètres Domaines autorisés et Domaines bloqués du Panneau de configuration Lync Server ou en configurant les domaines autorisés ou bloqués à l’aide de Lync Server Management Shell et des applets de commande PowerShell **Get**, **Set**, **New**, **Remove-CsAllowedDomain** et **-CsBlockedDomain**. Pour plus d’informations sur la configuration de ces paramètres et sur l’utilisation des applets de commande PowerShell, voir **Rubriques connexion** à la fin de cette rubrique.

Le tableau récapitulatif des enregistrements DNS décrit les entrées requises pour une fédération ouverte (détectable). Si vous ne souhaitez pas implémenter Federation Discovery, vous pouvez choisir de ne pas configurer l’enregistrement \_sipfederationtls.\_tcp. *\<Nom de domaine SIP\>*.

> [!IMPORTANT]  
> Dans certains cas précis, vous devez disposer de l’enregistrement SRV _sipfederationtls._tcp. <em>&lt;Nom de domaine SIP&gt;</em>, mais vous ne voulez pas d’une fédération détectable. Cela peut se produire lorsque vous avez déployé la mobilité pour vos utilisateurs. Le centre d’échanges de notifications push de la mobilité est un type spécial de fédération qui est utilisé pour les clients Microsoft Lync Mobile sur Apple iPhone ou iPad à l’aide du client Lync 2010 Mobile, ou sur Windows Phone à l’aide du client Lync 2010 Mobile ou Lync 2013 Mobile. L’enregistrement SRV _sipfederationtls._tcp. <em>&lt;Nom de domaine SIP&gt;</em> est utilisé dans le cas de la mobilité et de la notification push. Pour résoudre ce problème et contrôler votre détectabilité, désélectionnez le paramètre <strong>Activer la découverte du domaine partenaire</strong> pour désactiver la découverte.

Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, créez deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements dans le service Edge d’accès de votre serveur Edge ou pool de serveurs Edge.

Lors de la configuration du système DNS pour la connectivité PIC (Public IM Connectivity), vous constaterez que la configuration qui prend en charge les utilisateurs externes prend également en charge la connectivité PIC. Si vous avez déjà configuré votre serveur Edge ou pool de serveurs Edge, vous devez disposer des enregistrements DNS nécessaires pour la prendre en charge.

## Résumé des enregistrements DNS - Fédération SIP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/Port</th>
<th>Nom de domaine complet (FQDN)</th>
<th>Adresse IP/Enregistrement d’hôte FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service Edge d’accès. Requise pour permettre la découverte DNS automatique de votre fédération par d’autres partenaires de fédération potentiels, elle est aussi connue sous le nom de « Domaines SIP autorisés » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p>
<div>

> [!IMPORTANT]  
> Cet enregistrement SRV est requis pour la mobilité et le centre d’échanges de notifications push. Lorsque plusieurs domaines SIP sont présents, créez et publiez un enregistrement SRV pour chaque domaine amené à contenir plusieurs clients Lync Mobile. Le service de notifications Push et le service de notifications Push Apple risquent de ne pas fonctionner comme prévu si un enregistrement SRV explicite n’est pas affecté à chaque domaine SIP pris en charge par le déploiement.
</div></td>
</tr>
</tbody>
</table>


## Résumé des enregistrements DNS - XMPP (Extensible Messaging and Presence Protocol)


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
<th>Nom de domaine complet (FQDN)</th>
<th>Adresse IP/enregistrement d’hôte de nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez si nécessaire pour tous les domaines SIP internes avec des utilisateurs prenant en charge Lync où le contact avec des contacts XMPP est autorisé par le biais de la configuration de la stratégie d’accès externe via une stratégie globale, une stratégie de site dans laquelle se trouve l’utilisateur ou une stratégie utilisateur appliquée à l’utilisateur prenant en charge Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP. Pour plus d’informations, voir les rubriques dans <strong>Voir aussi</strong>.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre proxy XMPP d’hébergement de serveur Edge ou de pool de serveurs Edge</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA)</p></td>
</tr>
</tbody>
</table>


## Résumé des enregistrements DNS - Connectivité PIC (Public IM Connectivity)


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
<th>Nom de domaine complet/enregistrement DNS</th>
<th>Adresse IP/nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface du service Edge d’accès</p></td>
<td><p>Interface externe du service Edge d’accès(Contoso). Répéter selon les besoins pour tous les domaines SIP avec des utilisateurs Lync.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Tâches

[Configuration de la fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configuration des notifications push dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  

#### Concepts

[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Autres ressources

[Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

