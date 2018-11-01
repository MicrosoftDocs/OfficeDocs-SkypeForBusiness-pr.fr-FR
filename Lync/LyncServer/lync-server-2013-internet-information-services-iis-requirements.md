---
title: 'Lync Server 2013 : Configuration requise pour les services Internet (IIS)'
TOCTitle: Configuration requise pour les services Internet (IIS)
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398321(v=OCS.15)
ms:contentKeyID: 49297177
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour les services Internet (IIS) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Plusieurs composants Lync Server 2013 nécessitent services Internet (IIS). Cette rubrique décrit les fonctionnalités des services Internet (IIS) nécessaires à la prise en charge de Lync Server. Les rubriques de cette section présentent les exigences relatives à certains composants pour les services Internet (IIS).

Lorsque le rôle serveur web (IIS) est activé sur Windows Server 2008, divers services de rôle sont installés par défaut. Le tableau ci-dessous décrit les services de rôle supplémentaires devant être installés lorsque le rôle serveur web (IIS) est activé sur Windows Server 2008.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Service de rôle</th>
<th>Fonctionnalité</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fonctionnalités HTTP communes</p></td>
<td><p>Redirection HTTP</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Extensibilité .NET</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>Extensions ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Filtres ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Intégrité et diagnostics</p></td>
<td><p>Outils de journalisation</p></td>
</tr>
<tr class="odd">
<td><p>Intégrité et diagnostics</p></td>
<td><p>Suivi</p></td>
</tr>
<tr class="even">
<td><p>Sécurité</p></td>
<td><p>Authentification de base</p></td>
</tr>
<tr class="odd">
<td><p>Sécurité</p></td>
<td><p>Authentification Windows</p></td>
</tr>
<tr class="even">
<td><p>Outils de gestion</p></td>
<td><p>Scripts et outils de gestion des services Internet (IIS)</p></td>
</tr>
<tr class="odd">
<td><p>Outils de gestion</p></td>
<td><p>Compatibilité avec la gestion des services Internet (IIS) 6</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />Sécurité Remarque :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si vous utilisez les services Internet (IIS) 7.0 sur un système d’exploitation Windows Server 2008, le programme d’installation de Lync Server désactive l’authentification du mode noyau dans les services Internet (IIS).</td>
</tr>
</tbody>
</table>


## Dans cette section

  - [Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

