---
title: Résumé des certificats - découverte automatique
TOCTitle: Résumé des certificats - découverte automatique
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945616(v=OCS.15)
ms:contentKeyID: 53095362
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - découverte automatique

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le service de découverte automatique Lync Server 2013 s’exécute sur le directeur et le pool de serveurs frontaux, et une fois publié dans le DNS, peut être utilisé par les clients Lync pour localiser des services de serveur et d’utilisateur. Si vous effectuez une mise à niveau depuis Lync Server 2010 et que vous n’avez pas déployé le service de mobilité, pour que les clients puissent utiliser la découverte automatique, vous devez modifier les listes des autres noms de sujet des certificats sur chaque directeur et serveur frontal qui exécute le service de découverte automatique. En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.

La décision quant à l’utilisation de listes d’autres noms de sujet sur les proxys inverses repose sur votre choix de publier le service de découverte automatique sur le port 80 ou sur le port 443 :

  - **Publication sur le port 80** Aucune modification de certificat n’est requise si la requête initiale adressée au service de découverte automatique a lieu via le port 80. Ceci est dû au fait que les appareils mobiles qui exécutent Lync accèdent au proxy inverse sur le port 80 en externe, puis accèdent par le biais d’un pontage à un directeur ou à un serveur frontal sur le port 8080 en interne. Pour plus d’informations, consultez la section « Processus de découverte automatique initiale à l’aide du port 80 » [Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publication sur le port 443** La liste des autres noms de sujet sur les certificats utilisés par la règle de publication des services web externes doit contenir une entrée *lyncdiscover.\<sipdomain\>* pour chaque domaine SIP situé au sein de votre organisation.
    
    > [!IMPORTANT]  
    > Nous vous recommandons vivement d’utiliser HTTPS sur HTTP. HTTPS utilise des certificats pour chiffrer le trafic. HTTP n’offre pas de chiffrement et toutes les données envoyées sont du texte brut.

La réémission de certificats à l’aide d’une autorité de certification interne constitue généralement un processus simple. Toutefois, pour les certificats publics utilisés dans la règle de publication des services web, l’ajout de plusieurs entrées d’autres noms de sujet peut s’avérer onéreux. Pour remédier à ce problème, nous recommandons la connexion de découverte automatique initiale via le port 80, laquelle est ensuite redirigée vers le port 8080 sur le directeur ou le serveur frontal.

> [!NOTE]  
> Si votre infrastructure Lync Server 2013 utilise des certificats internes émis par une autorité de certification interne et que vous prévoyez de prendre en charge la connexion sans fil d’appareils mobiles, la chaîne de certificats racine de l’autorité de certification interne doit être installée sur les appareils mobiles ou vous devez passer à un certificat public sur votre infrastructure Lync Server 2013.

Cette rubrique décrit les autres noms de sujet ajoutés requis pour le directeur, le serveur frontal et le proxy inverse. Seuls les autres noms de sujet ajoutés sont référencés. Pour obtenir de l’aide sur les autres entrées des certificats, reportez-vous aux sections de planification. Pour plus d’informations, voir [Scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) et [Scénarios de proxy inverse dans Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

Les tableaux suivants définissent les entrées des autres noms de sujet de découverte automatique pour le pool de directeurs, le pool de serveurs frontaux et le proxy inverse :

### Exigences relatives au certificat du pool directeur

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée d’autre nom de sujet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique interne</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;nom de domaine interne&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;domainesip&gt;</em></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Vous assignez au certificat par défaut le certificat récemment mis à jour avec la nouvelle entrée SAN. Vous pouvez également utiliser SAN=*.<em>&lt;domainesip&gt;</em>.

### Exigences relatives au certificat du pool frontal

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée d’autre nom de sujet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique interne</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;nom de domaine interne&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;domainesip&gt;</em></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Vous assignez au certificat par défaut le certificat récemment mis à jour avec la nouvelle entrée SAN. Vous pouvez également utiliser SAN=*.<em>&lt;domainesip&gt;</em>

### Exigences relatives au certificat de proxy inverse (autorité de certification publique)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée d’autre nom de sujet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;domainesip&gt;</em></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Vous assignez le certificat mis à jour avec la nouvelle entrée SAN à l’écouteur SSL sur le proxy inverse.
