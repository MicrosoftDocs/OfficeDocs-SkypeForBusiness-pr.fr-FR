---
title: "LS 2013 : Rés. DNS - SE cons. màé, éq. ch. DNS ac ad. IP pr., conv. d’ad. Rés."
TOCTitle: Résumé DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398201(v=OCS.15)
ms:contentKeyID: 49296301
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-03-09_

Les enregistrements DNS requis pour l’accès à distance à Lync Server 2013 sont assez simples comparés à ceux des certificats et des ports. En outre, de nombreux enregistrements sont facultatifs, selon la manière dont vous configurez les clients Lync 2013 et selon que la fédération est activée ou désactivée.

Pour plus d’informations sur les enregistrements DNS Lync 2013 requis, reportez-vous à [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients Lync 2013 si vous ne souhaitez pas utiliser une configuration DNS Split-Brain, reportez-vous à la section « Configuration automatique sans configuration DNS Split Brain » dans [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau ci-dessous fournit un résumé des enregistrements DNS requis pour prendre en charge la topologie Edge consolidée unique présentée dans la figure Topologie Edge consolidée unique. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync 2013. Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

## IMPORTANT : cartes réseau de serveur Edge requises

Pour éviter des problèmes de routage, vérifiez que les serveurs Edge sont équipés d’au moins deux cartes réseau et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe. Par exemple, comme l’indique la figure Topologie Edge consolidée mise à l’échelle dans [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), la passerelle par défaut doit pointer vers le pare-feu externe.

Vous pouvez configurer deux cartes réseau dans chacun de vos serveurs Edge comme suit :

  - **Carte réseau 1 - nœud 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 affecté.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il y a un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 1 - nœud 2 (interface interne)**
    
    Interface interne avec 172.25.33.11 affecté.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il y a un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 - nœud 1 (interface externe)**
    
    Trois adresses IP privées sont affectées à cette carte réseau, par exemple 10.45.16.10 pour le serveur Edge d’accès, 10.45.16.20 pour le serveur Edge de conférence web et 10.45.16.30 pour le serveur Edge AV.
    
    > [!NOTE]  
    > Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge. Même si les adresses IP sont enregistrées, les numéros de port doivent être différents pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic. Le fait d’affecter aux ports les valeurs 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence web et 443/TCP pour le service Edge A/V, par exemple, peut générer des problèmes pour les utilisateurs distants se trouvant derrière un pare-feu qui n’autorise pas le trafic sur 5061/TCP et 444/TCP. Par ailleurs, l’utilisation de trois adresses IP distinctes facilite l’identification et la résolution des problèmes puisqu’il est possible d’appliquer un filtre selon l’adresse IP.    
    L’adresse IP publique des serveurs Edge d’accès avec la passerelle par défaut définie sur le routeur intégré (10.45.16.1) est l’adresse principale.
    
    Les adresses IP privées du service de conférence web et du service Edge A/V sont des adresses IP supplémentaires dans la section **Avancé** des propriétés **Protocole Internet version 4 (TCP/IPv4)** et **Protocole Internet version 6 (TCP/IPv6)** des **Propriétés de la connexion au réseau local** dans Windows Server.

  - **Carte réseau 2 - nœud 2 (interface externe)**
    
    Trois adresses IP privées sont affectées à cette carte réseau, par exemple 10.45.16.11 pour le serveur Edge d’accès, 10.45.16.21 pour le serveur Edge de conférence web et 10.45.16.31 pour le serveur Edge AV.
    
    L’adresse IP publique des serveurs Edge d’accès avec la passerelle par défaut définie sur le routeur intégré (10.45.16.1) est l’adresse principale.
    
    Les adresses IP privées du service de conférence web et du service Edge A/V sont des adresses IP supplémentaires dans la section **Avancé** des propriétés **Protocole Internet version 4 (TCP/IPv4)** et **Protocole Internet version 6 (TCP/IPv6)** des **Propriétés de la connexion au réseau local** dans Windows Server.

> [!TIP]  
> La configuration du serveur Edge avec deux cartes réseau est une option. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Cela permet d’utiliser une carte réseau distincte par service serveur Edge et une collection de données potentiellement plus concise en cas d’identification et de résolution des problèmes.

### Enregistrements DNS requis pour le serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées utilisant la technologie NAT (exemple)

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
<th>Nom de domaine complet/enregistrement DNS</th>
<th>Adresse IP/nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 et 131.107.155.11</p></td>
<td><p>Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 et 131.107.155.21</p></td>
<td><p>Interface externe de serveur Edge de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 et 131.107.155.31</p></td>
<td><p>Interface externe de serveur Edge A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du serveur Edge d’accès. Requise pour que la configuration automatique des clients Lync 2013 et Lync 2010 fonctionne en externe. Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du serveur Edge d’accès SIP. Requise pour permettre la découverte DNS automatique de partenaires fédérés connus sous le nom de « Domaines SIP autorisés » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 et 172.25.33.11</p></td>
<td><p>Interface interne de serveur Edge consolidé</p></td>
</tr>
</tbody>
</table>


## Enregistrements requis pour la fédération


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
<th>FQDN</th>
<th>Adresse IP/enregistrement d’hôte de nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du serveur Edge d’accès SIP. Requise pour permettre la découverte DNS automatique de votre fédération par d’autres partenaires de fédération potentiels, elle est aussi connue sous le nom de « Domaines SIP autorisés » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p>
<div>

> [!IMPORTANT]  
> Cet enregistrement SRV est requis pour la mobilité et le centre d’échanges de notifications push.
</div></td>
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
<th>Emplacement/TYPE/Port</th>
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
<td><p>Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
</tbody>
</table>


## Résumé des enregistrements DNS pour le protocole XMPP (Extensible Messaging et Presence Protocol)


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
<th>FQDN</th>
<th>Adresse IP/enregistrement d’hôte de nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP sur le service Edge d’accès ou pool de serveurs Edge. Répétez si nécessaire pour tous les domaines SIP internes avec des utilisateurs prenant en charge Lync où le contact avec des contacts XMPP est autorisé par le biais de la configuration de la stratégie d’accès externe via une stratégie globale, une stratégie de site dans laquelle se trouve l’utilisateur ou une stratégie utilisateur appliquée à l’utilisateur prenant en charge Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP. Pour plus d’informations, reportez-vous aux rubriques dans <strong>Voir aussi</strong>.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre proxy XMPP d’hébergement de serveur Edge ou de pool de serveurs Edge</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA)</p></td>
</tr>
</tbody>
</table>

