---
title: 'Lync Server 2013 : Résumé des ports - Proxy inverse'
TOCTitle: Résumé des ports - Proxy inverse
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204932(v=OCS.15)
ms:contentKeyID: 49297268
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Proxy inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le proxy inverse a des exigences minimales en matière de pare-feu et de port/protocole.

  - Les exigences en matière de pare-feu externe sont le paramétrage HTTPS/TCP/443 et le paramétrage HTTP/TCP/80 facultatif. HTTPS est utilisé pour les communications sécurisées TLS et SSL par le biais du proxy inverse. HTTP est utilisé si vous choisissez d’autoriser l’accès au service de découverte automatique quand la modification de certificats risque de s’avérer difficile ou trop coûteuse.

  - Normalement, les clients contactent Office Web Apps Server sur HTTPS et Office Web Apps Server reçoit les communications des clients internes sur HTTPS/TCP/443. La configuration recommandée consiste à autoriser HTTPS/TCP/443 entre le proxy inverse et Office Web Apps Server.

  - Le port 8080 sert à router le trafic depuis l’interface interne du proxy inverse jusqu’à l’adresse IP virtuelle du serveur frontal ou du pool de serveurs frontaux, ou l’adresse IP virtuelle facultative du directeur ou du pool de directeurs. Le port TCP 8080 est nécessaire aux appareils mobiles exécutant Lync pour rechercher le service de découverte automatique dans les situations où la modification du certificat de règle de publication du service web externe n’est pas souhaitable (par exemple, si vous avez un grand nombre de domaines SIP). Si vous choisissez d’acquérir de nouveaux certificats avec les entrées SAN nécessaires, le port TCP 8080 n’est pas nécessaire et devient facultatif.

  - Le port 4443 sert à router le trafic depuis l’interface interne du proxy inverse jusqu’à l’adresse IP virtuelle du serveur frontal ou du pool de serveurs frontaux, ou l’adresse IP virtuelle facultative du directeur ou du pool de directeurs.
    
    ![Proxy inverse et services web externes](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "Proxy inverse et services web externes")  
    
    > [!CAUTION]  
    > Ne confondez pas le trafic du port 4443 sur TCP du proxy inverse au déploiement interne avec le trafic du port 4443 sur TCP en provenance du serveur Standard Edition ou du pool de serveurs frontaux qui gère le rôle du magasin central de gestion.


## Détails sur les ports et protocoles

### Informations sur le pare-feu pour le serveur proxy inverse : interface externe

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Indifférente</p></td>
<td><p>Port d’écoute du proxy inverse</p></td>
<td><p>(Facultatif) Redirection vers HTTPS si l’utilisateur entre http:// <em>&lt;nom_domaine_complet_site_publié&gt;</em></p>
<p>Également nécessaire en cas d’utilisation d’Office Web Apps pour la conférence et du service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service web externe.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Port d’écoute du proxy inverse</p></td>
<td><p>Téléchargement de carnets d’adresses, service de requête sur le web du carnet d’adresses, découverte automatique, mises à jour de clients, contenu de réunions, mises à jour de périphériques, développement de groupes, Office Web Apps pour les conférences, conférences rendez-vous et réunions.</p></td>
</tr>
</tbody>
</table>


### Informations sur le pare-feu pour le serveur proxy inverse : interface interne

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>serveur frontal, pool de serveurs frontaux, directeur, pool de directeurs</p></td>
<td><p>Nécessaire en cas d’utilisation du service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service web externe.</p>
<p>Le trafic envoyé au port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy inverse, de sorte que les services web du pool puissent le différencier du trafic web interne.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>serveur frontal, pool de serveurs frontaux, directeur, pool de directeurs</p></td>
<td><p>Le trafic envoyé vers le port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy inverse, de sorte que les services web du pool puissent le différencier du trafic web interne.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>Office Web Apps pour la conférence</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

