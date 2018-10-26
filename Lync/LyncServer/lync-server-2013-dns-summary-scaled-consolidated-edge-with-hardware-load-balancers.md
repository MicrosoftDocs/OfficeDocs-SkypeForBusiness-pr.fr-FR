---
title: "Lync Server 2013 : Rés. des enr. DNS - SE conso. màé avec des éq. de ch. Mat."
TOCTitle: Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398670(v=OCS.15)
ms:contentKeyID: 49297942
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les enregistrements DNS requis pour l’accès à distance à Lync Server 2013 sont assez simples comparés à ceux des certificats et des ports. En outre, de nombreux enregistrements sont facultatifs, selon la manière dont vous configurez les clients Lync 2013 et selon que la fédération est activée ou désactivée.

Pour plus d’informations sur les enregistrements DNS Lync 2013 requis, reportez-vous à [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients Lync 2013 si vous ne souhaitez pas utiliser une configuration DNS Split-Brain, reportez-vous à la section « Configuration automatique sans configuration DNS Split Brain » dans [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau ci-dessous contient une synthèse des enregistrements DNS requis pour prendre en charge le serveur Edge consolidé ajusté (avec équilibrage de charge matérielle) présenté dans la figure. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync. Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

## IMPORTANT : cartes réseau de serveur Edge requises

Pour éviter des problèmes de routage, vérifiez que les serveurs Edge sont équipés d’au moins deux cartes réseau et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe. Par exemple, comme l’illustre la figure Topologie Edge consolidée mise à l’échelle dans [Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), la passerelle par défaut doit pointer vers le pare-feu externe.

Vous pouvez configurer deux cartes réseau dans chacun de vos serveurs Edge comme suit :

  - **Carte réseau 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 affecté.
    
    Aucune passerelle par défaut.
    
    Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne serveur Edge et les réseaux qui contiennent des clients ou serveurs Lync Server exécutant Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 (interface externe)**
    
    Trois adresses IP publiques sont affectées à cette carte réseau, par exemple, 131.107.155.10 pour le service Edge d’accès, 131.107.155.20 pour le service Edge de conférence web, 131.107.155.30 pour le service Edge A/V.
    
    > [!NOTE]  
    > Les adresses IP affectées aux interfaces réseau externes réelles du serveur Edge peuvent varier en fonction de l’équilibreur de charge matérielle choisi. Pour plus d’informations sur les exigences liées aux adresses IP, reportez-vous à la documentation de votre équilibreur de charge matérielle.<br />
    Il est possible, bien que non recommandé, d’utiliser une seule adresse IP pour toutes les interfaces de service Edge. Même si cela économise des adresses IP, des numéros de port différents sont requis pour chaque service. Le numéro de port par défaut est 443/TCP (garantit que la plupart des pare-feux distants autorisent le trafic). La modification des valeurs de port sur (par exemple) 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence web et 443/TCP pour le service Edge A/V peut engendrer des problèmes pour les utilisateurs distants si le pare-feu derrière lequel ils se trouvent n’autorise pas le trafic via les ports 5061/TCP et 444/TCP. En outre, trois adresses IP distinctes facilitent l’identification et la résolution des problèmes, car vous pouvez filtrer selon l’adresse IP.    
    L’adresse IP du service Edge d’accès avec la passerelle par défaut définie sur le routeur Internet (131.107.155.1) est l’adresse principale.
    
    Les adresses IP service Edge de conférence web et service Edge A/V sont secondaires.

> [!TIP]  
> La configuration du serveur Edge avec deux cartes réseau est une option. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Cela permet d’utiliser une carte réseau distincte par service serveur Edge et une collection de données potentiellement plus concise en cas d’identification et de résolution des problèmes.

### Enregistrements DNS requis pour le serveur Edge consolidé ajusté, équilibrage de charge matérielle (exemple)

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
<td><p>Interface externe du service Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externe du service Edge de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interface externe du service Edge A/V</p></td>
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
<td><p>Interface externe du service Edge d’accès SIP. Requise pour la découverte DNS automatique des partenaires fédérés ou « Domaine SIP autorisé » (appelé fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync et des clients Microsoft Lync Mobile qui utilisent le service de notifications Push ou le service de notifications Push Apple</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interne de serveur Edge consolidé</p></td>
</tr>
</tbody>
</table>

