---
title: "Lync Server 2013 : Résumé des enr. DNS - SE unique cons. avec ad. IP publiques"
TOCTitle: Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP publiques
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205025(v=OCS.15)
ms:contentKeyID: 49297829
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-03-09_

Les enregistrements DNS requis pour l’accès à distance à Lync Server 2013 sont assez simples comparés à ceux des certificats et des ports. En outre, de nombreux enregistrements sont facultatifs, selon la manière dont vous configurez les clients Lync 2013 et selon que la fédération est activée ou désactivée.

Pour plus d’informations sur les enregistrements DNS Lync 2013 requis, reportez-vous à [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients Lync 2013 lorsque le DNS split-brain n’est pas configuré, reportez-vous à « Configuration automatique sans configuration DNS Split Brain » dans [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau ci-dessous fournit un résumé des enregistrements DNS requis pour prendre en charge la topologie Edge consolidée unique présentée dans la figure Topologie Edge consolidée unique. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync 2013 et Lync 2010. Si vous envisagez d’utiliser des objets de stratégie de groupe pour configurer des clients Lync, les enregistrements de configuration automatique associés ne sont pas nécessaires.

## IMPORTANT : cartes réseau de serveur Edge requises

Pour éviter des problèmes de routage, vérifiez que vos serveurs Edge disposent de deux cartes réseau et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe. Par exemple, comme indiqué dans la figure Topologie Edge consolidée unique avec adresses IP publiques dans [Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), la passerelle par défaut doit pointer vers le routeur externe sur le réseau de périmètre Internet ou le pare-feu qui peut fournir les adresses IP publiques. La relation réseau pour les interfaces de serveur Edge est une relation d’itinéraire au lieu d’une relation NAT.

Vous pouvez configurer deux cartes réseau dans votre serveur Edge comme suit :

  - **Carte réseau 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 affecté.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il y a un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 (interface externe)**
    
    Trois adresses IP publiques sont affectées à cette carte réseau, par exemple, 131.107.155.10 pour le serveur Edge d’accès, 131.107.155.20 pour le serveur Edge de conférence web, 131.107.155.30 pour le serveur Edge AV.
    
    > [!NOTE]  
    > Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge. Même si les adresses IP sont enregistrées, les numéros de port doivent être différents pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic. Le fait d’affecter aux ports les valeurs 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence web et 443/TCP pour le service Edge A/V, par exemple, peut générer des problèmes pour les utilisateurs distants se trouvant derrière un pare-feu qui n’autorise pas le trafic sur 5061/TCP et 444/TCP. Par ailleurs, l’utilisation de trois adresses IP distinctes facilite l’identification et la résolution des problèmes puisqu’il est possible d’appliquer un filtre selon l’adresse IP.    
    L’adresse IP publique des serveurs Edge d’accès avec la passerelle par défaut définie sur le routeur public (131.107.155.1) est l’adresse principale.
    
    Les adresses IP publiques des serveurs de conférence web et Edge A/V sont des adresses IP supplémentaires dans la section **Avancé** des propriétés **Protocole Internet version 4 (TCP/IPv4)** et **Protocole Internet version 6 (TCP/IPv6)** des **Propriétés de la connexion au réseau local** dans Windows Server.

> [!TIP]  
> La configuration du serveur Edge avec deux cartes réseau est une option. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Cela permet d’utiliser une carte réseau distincte par service serveur Edge et une collection de données potentiellement plus concise en cas d’identification et de résolution des problèmes.

### Enregistrements DNS requis pour un serveur Edge consolidé unique avec des adresses IP publiques (Exemple)

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
<td><p>131.107.155.10</p></td>
<td><p>Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externe de serveur Edge de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
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
<td><p>Interface externe du serveur Edge d’accès SIP. Requise pour permettre la découverte DNS automatique des partenaires fédérés, elle est aussi connue sous le nom de « Domaine SIP autorisé » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interne de serveur Edge consolidé</p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> Les enregistrements répertoriés dans le tableau précédent sont indiqués avec une extension <em>.net</em> ou une extension <em>.com</em> pour mettre en avant la zone dans laquelle ils doivent se trouver si vous n’utilisez pas une configuration DNS split-brain. Si vous utilisez une configuration DNS split-brain, tous les enregistrements seraient dans la même zone, leur version, interne ou externe, permettant de les distinguer. Pour plus d’informations, reportez-vous à « DNS Split-Brain » dans <a href="lync-server-2013-determine-dns-requirements.md">Détermination de la configuration requise pour DNS pour Lync Server 2013</a>.

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

