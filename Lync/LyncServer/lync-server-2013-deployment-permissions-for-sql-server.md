---
title: 'Lync Server 2013 : Autorisations de déploiement de SQL Server'
TOCTitle: Autorisations de déploiement de SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398375(v=OCS.15)
ms:contentKeyID: 49297236
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autorisations de déploiement de SQL Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Microsoft SQL Server 2012 nécessite de respecter des conditions préalables lors de l’installation et du déploiement de Lync Server 2013. Comme Windows et SQL Server définissent leur sécurité différemment, la connexion en tant qu’administrateur dans le domaine Active Directory n’accorde pas implicitement les autorisations pour SQL Server. Vous devez être membre de l’entité sysadmin sur le serveur SQL Server que vous configurez.

## Autorisations requises pour l’installation de la base de données et de Lync Server

Les options suivantes détaillent les trois associations d’autorisations et d’appartenance à un groupe pour l’installation des fichiers Lync Server 2013 et des bases de données SQL Server. Choisissez le scénario qui répond le mieux aux exigences de votre organisation.

### Associations des autorisations et de l’appartenance à un groupe

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôle SQL Server ou Lync Server 2013</th>
<th>Autorisations SQL Server et appartenance à un groupe en fonction du rôle</th>
<th>Autorisations Lync Server 2013 et appartenance à un groupe en fonction du rôle</th>
<th>Possibilités associées aux autorisations</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Administrateur Lync Server 2013</p></td>
<td><p>Doit être membre du groupe de sécurité sysadmins SQL Server et membre du groupe Administrateurs local SQL Server</p></td>
<td><p>Doit être membre du groupe RTCUniversalServerAdmins</p></td>
<td><p>L’administrateur Lync Server 2013 dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Administrateur SQL Server</p></td>
<td><p>Membre du groupe sysadmins SQL Server (ou équivalent) et membre du groupe Administrateurs local SQL Server</p></td>
<td><p>Doit être membre du groupe RTCUniversalServerReadOnly</p></td>
<td><p>L’administrateur SQL Server dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Les deux administrateurs partageant les tâches d’installation</p></td>
<td><p>L’administrateur SQL Server est membre du groupe sysadmins (ou équivalent) et membre du groupe Administrateurs local SQL Server</p></td>
<td><p>L’administrateur Lync Server 2013 est membre de RTCUniversalServerAdmins</p></td>
<td><p>L’administrateur Lync Server 2013 peut installer Lync Server 2013, mais pas les bases de données. L’administrateur SQL Server utilise les applets de commande Lync Server Management Shell et Windows PowerShell fournies par l’administrateur Lync Server 2013 pour installer les bases de données. Le Lync Server 2013 Management Shell utilisé par l’administrateur SQL Server est installé sur le serveur frontal. Cela évite de devoir installer les outils d’administration Lync Server 2013 sur le serveur SQL Server.</p></td>
</tr>
</tbody>
</table>

