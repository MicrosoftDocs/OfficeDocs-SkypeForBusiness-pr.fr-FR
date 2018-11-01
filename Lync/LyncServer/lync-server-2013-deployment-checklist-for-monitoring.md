---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour la surveillance'
TOCTitle: Liste de vérification du déploiement pour la surveillance
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204874(v=OCS.15)
ms:contentKeyID: 49891344
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour la surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Même si la fonctionnalité de surveillance est déjà installée et activée sur chaque serveur frontal, vous devez entreprendre plusieurs étapes supplémentaires avant de pouvoir réellement collecter des données de surveillance pour Microsoft Lync Server 2013. Ces étapes sont décrites dans la liste de vérification suivante :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Phase</p></td>
<td><p>Étapes</p></td>
<td><p>Rôles et appartenance aux groupes</p></td>
<td><p>Documentation</p></td>
</tr>
<tr class="even">
<td><p><strong>Installer le matériel et les logiciels prérequis</strong></p></td>
<td><p>Installez une version prise en charge de Microsoft SQL Server sur l’ordinateur qui fera office de magasin de données principal pour la surveillance.</p></td>
<td><p>Utilisateur de domaine qui est également membre du groupe Administrateurs local.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans le guide de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013</a> dans le guide de prise en charge</p></td>
</tr>
<tr class="odd">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge la surveillance</strong></p></td>
<td><p>Utilisez le générateur de topologie Lync Server 2013 pour ajouter des bases de données de surveillance à la topologie, puis publiez la topologie mise à jour.</p></td>
<td><p>Pour définir une topologie, utilisateur membre du groupe Utilisateurs local.</p>
<p>Pour publier la topologie, utilisateur membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Association d’un magasin de surveillance à un pool frontal dans Lync Server 2013</a> dans le guide de déploiement</p></td>
</tr>
<tr class="even">
<td><p><strong>Activer les paramètres de surveillance appropriés</strong></p></td>
<td><p>Activez l’enregistrement des détails des appels et/ou la surveillance QoE au niveau des étendues Global et/ou Site.</p></td>
<td><p>Utilisateur membre du groupe RTCUniversalServerAdmins ou disposant d’un rôle RBAC qui permet d’accéder aux applets de commande CsCdrConfiguration et CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuration des paramètres de l’enregistrement des détails des appels et de la qualité de l’expérience dans Lync Server 2013</a> dans le guide des opérations</p></td>
</tr>
</tbody>
</table>

