---
title: Synthèse des ports - Découverte automatique dans Lync Server 2013
TOCTitle: Synthèse des ports - Découverte automatique dans Lync Server 2013
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945642(v=OCS.15)
ms:contentKeyID: 53095458
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Synthèse des ports - Découverte automatique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-04-06_

Le service de découverte automatique Lync Server 2013 s’exécute sur le directeur et le pool de serveurs frontaux, et une fois publié dans le système DNS à l’aide des enregistrements d’hôtes `lyncdiscover.<domain>` et `lyncdiscoverinternal.<domain>`, il peut être utilisé par les clients pour rechercher des fonctionnalités de Lync Server. Pour que les appareils mobiles exécutant Lync Mobile puissent utiliser la découverte automatique, vous devrez peut-être au préalable modifier les listes des autres noms du sujet des certificats sur chaque directeur et serveur frontal qui exécute le service de découverte automatique. En outre, il peut s’avérer nécessaire de modifier les listes des autres noms du sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.

La décision d’utiliser des listes d’autres noms du sujet sur les proxys inverses repose sur votre choix de publier le service de découverte automatique sur le port 80 ou sur le port 443 :

  - **Publication sur le port 80** Pour les appareils mobiles, aucune modification de certificat n’est requise si la requête initiale adressée au service de découverte automatique est effectuée via le port 80. Ceci est dû au fait que les appareils mobiles qui exécutent Lync accèdent au proxy inverse sur le port 80 en externe, puis sont redirigés vers un directeur ou un serveur frontal sur le port 8080 en interne.

  - **Publication sur le port 443** La liste des autres noms du sujet sur les certificats utilisés par la règle de publication des services web externes doit contenir une entrée `lyncdiscover.<sipdomain>` pour chaque domaine SIP situé au sein de votre organisation.
    
    > [!IMPORTANT]  
    > Pour les nouvelles installations ou les mises à niveau à partir de Lync Server 2010 où vous avez déployé la mobilité, vous avez soit utilisé le port 80 pour la découverte automatique du service de mobilité, soit réémis des certificats avec le nom du sujet et les autres noms du sujet corrects en place. Examinez les certificats sur votre directeur et votre serveur frontal pour vérifier le chemin d’accès choisi.

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
<td><p>(Facultatif) Redirection vers HTTPS si l’utilisateur entre http://<em>&lt;nom_domaine_complet_site_publié&gt;</em> Également nécessaire en cas d’utilisation d’Office Web Apps pour les conférences et du service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service web externe.</p></td>
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
<td><p>serveur frontal, pool de serveurs frontaux, directeur, pool de directeurs, Office Web Apps pour les conférences</p></td>
<td><p>Nécessaire en cas d’utilisation du service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service web externe. Le trafic envoyé au port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy inverse, de sorte que les services web du pool puissent le différencier du trafic web interne.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>serveur frontal, pool de serveurs frontaux, directeur, pool de directeurs, Office Web Apps pour les conférences</p></td>
<td><p>Le trafic envoyé vers le port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy inverse, de sorte que les services web du pool puissent le différencier du trafic web interne.</p></td>
</tr>
</tbody>
</table>

