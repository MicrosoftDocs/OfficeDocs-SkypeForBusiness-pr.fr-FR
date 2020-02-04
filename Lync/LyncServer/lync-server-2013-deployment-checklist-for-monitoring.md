---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71b7d69054df266139f3f13ca0ca53e1803f44b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Liste de vérification du déploiement pour la surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

Même si la surveillance est déjà installée et activée sur chaque serveur frontal, il existe toujours plusieurs étapes que vous devez effectuer avant de pouvoir recueillir des données d’analyse pour Microsoft Lync Server 2013. Ces étapes sont décrites dans la liste de vérification suivante :


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
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans le Guide de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge de Software and Infrastructure Server dans Lync Server 2013</a> dans le Guide de prise en charge</p></td>
</tr>
<tr class="odd">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge la surveillance</strong></p></td>
<td><p>Utilisez le générateur de topologie Lync Server 2013 pour ajouter des bases de données de surveillance à la topologie, puis publiez la topologie mise à jour.</p></td>
<td><p>Pour définir une topologie, utilisateur membre du groupe Utilisateurs local.</p>
<p>Pour publier la topologie, utilisateur membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Association d’un magasin d’analyse à un pool frontal dans Lync Server 2013</a> dans le Guide de déploiement</p></td>
</tr>
<tr class="even">
<td><p><strong>Activer les paramètres de surveillance appropriés</strong></p></td>
<td><p>Activez l’enregistrement des détails des appels (CDR) et/ou la qualité de l’expertise (QoE) au niveau du global et/ou des étendues de site.</p></td>
<td><p>Utilisateur membre du groupe RTCUniversalServerAdmins ou disposant d’un rôle RBAC qui permet d’accéder aux applets de commande CsCdrConfiguration et CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuration des paramètres d’enregistrement des détails des appels et de la qualité de l’utilisation dans Lync Server 2013</a> dans le guide des opérations</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

