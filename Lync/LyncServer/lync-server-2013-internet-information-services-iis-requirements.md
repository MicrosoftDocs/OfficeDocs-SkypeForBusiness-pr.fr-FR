---
title: 'Lync Server 2013 : Configuration requise pour les services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb0350178a19a75ac821a452ef90e10da297677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Configuration requise pour les services Internet (IIS) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-19_

Plusieurs composants de Lync Server 2013 requièrent Internet Information Services (IIS). Cette rubrique décrit les fonctionnalités IIS spécifiques nécessaires à la prise en charge de Lync Server. Les rubriques de cette section décrivent la configuration requise pour les composants spécifiques pour IIS.

Lorsque le rôle serveur Web (IIS) est activé sur Windows Server 2008, différents services de rôle sont installés par défaut. Le tableau suivant décrit les services de rôle supplémentaires qui doivent être installés lorsque le rôle serveur Web (IIS) est activé sur Windows Server 2008.


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
<td><p>Redirection HTTP</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Extensibilité .NET</p></td>
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
<td><p>Compatibilité de gestion IIS 6</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" />Note de sécurité:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si vous utilisez IIS 7,0 sur un système d’exploitation Windows Server 2008, le programme d’installation de Lync Server désactive l’authentification en mode noyau dans les services Internet (IIS).</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

