---
title: "LS 2013 : Rés. enr. DNS - SE cons. màé, éq. de ch. DNS avec des ad. IP pub."
TOCTitle: Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205319(v=OCS.15)
ms:contentKeyID: 49299069
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-03-09_

Les enregistrements DNS requis pour l’accès à distance à Lync Server 2013 sont assez simples comparés à ceux des certificats et des ports. En outre, de nombreux enregistrements sont facultatifs, selon la manière dont vous configurez les clients Lync 2013 et selon que la fédération est activée ou désactivée.

Pour plus d’informations sur les enregistrements DNS Lync 2013 requis, reportez-vous à [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients Lync 2013 si vous ne souhaitez pas utiliser une configuration DNS Split-Brain, reportez-vous à la section « Configuration automatique sans configuration DNS Split Brain » dans [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau ci-dessous fournit un résumé des enregistrements DNS requis pour prendre en charge la topologie Edge consolidée unique présentée dans la figure Topologie Edge consolidée unique. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync 2013. Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

## IMPORTANT : cartes réseau de serveur Edge requises

Pour éviter des problèmes de routage, vérifiez que les serveurs Edge sont équipés d’au moins deux cartes réseau et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe. Par exemple, comme l’illustre la figure Topologie Edge consolidée mise à l’échelle dans [Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md), la passerelle par défaut doit pointer vers le pare-feu externe.

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
    
    Trois adresses IP privées sont affectées à cette carte réseau (par exemple, 131.107.155.10 pour le service Edge d’accès, 131.107.155.20 pour le service Edge de conférence web et 131.107.155.30 pour le service Edge A/V).
    
    L’adresse IP publique du service Edge d’accès avec la passerelle par défaut définie sur le routeur public (131.107.155.1) est l’adresse principale.
    
    Les adresses IP privées du service Edge de conférence web et du service Edge A/V sont des adresses IP supplémentaires dans la section **Avancées** des propriétés du **Protocole Internet version 4 (TCP/IPv4)** et du **Protocole Internet version 6 (TCP/IPv6)** des **Propriétés de la connexion au réseau local** dans Windows Server.
    
    > [!NOTE]  
    > Il est possible, ne s’affichentue non recommandé, d’utiliser une seule adresse IP pour toutes les interfaces de service Edge. Même si cela économise des adresses IP, des numéros de port différents sont requis pour chaque service. Le numéro de port par défaut est 443/TCP (garantit que la plupart des pare-feux distants autorisent le trafic). La modification des valeurs de port sur (par exemple) 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence web et 443/TCP pour le service Edge A/V peut engendrer des problèmes pour les utilisateurs distants si le pare-feu derrière lequel ils se trouvent n’autorise pas le trafic via les ports 5061/TCP et 444/TCP. En outre, trois adresses IP distinctes facilitent l’identification et la résolution des problèmes, car vous pouvez filtrer selon l’adresse IP.

  - **Carte réseau 2 - nœud 2 (interface externe)**
    
    Trois adresses IP privées sont affectées à cette carte réseau (par exemple, 131.107.155.11 pour le service Edge d’accès, 131.107.155.22 pour le service Edge de conférence web et 131.107.155.31 pour le service Edge A/V).
    
    L’adresse IP publique du service Edge d’accès avec la passerelle par défaut définie sur le routeur public (131.107.155.1) est l’adresse principale.
    
    Les adresses IP privées du service Edge de conférence web et du service Edge A/V sont des adresses IP supplémentaires dans la section **Avancées** des propriétés du **Protocole Internet version 4 (TCP/IPv4)** et du **Protocole Internet version 6 (TCP/IPv6)** des **Propriétés de la connexion au réseau local** dans Windows Server.

> [!TIP]  
> La configuration du serveur Edge avec deux cartes réseau est une option. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Cela permet d’utiliser une carte réseau distincte par service serveur Edge et une collection de données potentiellement plus concise en cas d’identification et de résolution des problèmes.

### Enregistrements DNS requis pour la topologie Edge consolidée mise à l’échelle, équilibrage de la charge DNS avec des adresses IP publiques (exemple)

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
<td><p>Interface externe du service Edge d’accès(Contoso). Répéter selon le besoin pour tous les domaines SIP avec des utilisateurs Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 et 131.107.155.21</p></td>
<td><p>Interface externe du service Edge de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 et 131.107.155.31</p></td>
<td><p>Interface externe service Edge A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service Edge d’accès. Requis pour la configuration automatique des clients Lync 2013 et Lync 2010 afin de travailler en externe. Répéter selon le besoin pour tous les domaines SIP avec des utilisateurs Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service Edge d’accès. Requis pour la découverte DNS automatique des partenaires fédérés appelé « Domaine SIP autorisé » (appelé fédération étendue dans les versions précédentes). Répéter selon le besoin pour tous les domaines SIP avec des utilisateurs Lync</p></td>
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
<td><p>Interface externe du service Edge d’accès SIP. Requis pour la découverte DNS automatique de votre fédération vers d’autres partenaires de fédération potentiels, appelé « Domaines SIP autorisés » (appelé fédération étendue dans les versions précédentes).</p>
<div>

> [!IMPORTANT]  
> Répéter selon le besoin pour tous les domaines SIP avec des utilisateurs Lync et des clients Microsoft Lync Mobile qui utilisent le service de notifications Push ou le service de notifications Push Apple
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
<td><p>Interface externe du service Edge d’accès(Contoso). Répéter selon le besoin pour tous les domaines SIP avec des utilisateurs Lync</p></td>
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
<td><p>Interface externe de proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répéter selon le besoin pour tous les domaines SIP avec des utilisateurs Lync lorsque le contact avec des contacts XMPP est autorisé via la configuration de la stratégie d’accès externe dans le cadre d’une stratégie globale, une stratégie de site incluant l’utilisateur ou une stratégie d’utilisateur appliquée à l’utilisateur Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie de partenaires fédérés XMPP. Pour plus d’informations, reportez-vous aux rubriques dans <strong>Voir aussi</strong>.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre proxy XMPP d’hébergement de serveur Edge ou de pool de serveurs Edge</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA)</p></td>
</tr>
</tbody>
</table>

