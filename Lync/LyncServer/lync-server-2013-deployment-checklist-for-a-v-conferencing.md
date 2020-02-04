---
title: Liste de vérification de déploiement de Lync Server 2013 pour les conférences A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Liste de vérification de déploiement pour les conférences A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Comme pour le déploiement de vos autres composants Lync Server 2013, le déploiement de conférences A/V nécessite l’utilisation du générateur de topologie pour créer et publier une topologie incluant des conférences.

<div>

## <a name="deployment-sequence"></a>Séquence de déploiement

Vous pouvez déployer des conférences en même temps que le déploiement de votre topologie initiale ou après le déploiement d’au moins un pool frontal ou d’un serveur Standard Edition Server.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Processus de déploiement de conférences

Le tableau suivant fournit une vue d’ensemble des étapes nécessaires au déploiement des conférences dans une topologie existante.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Rôles et appartenance aux groupes</th>
<th>Documentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installer le matériel et les logiciels prérequis</strong></p></td>
<td><p>Les conférences s’exécutent sur des serveurs front-end d’un pool frontal et de serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</p>
<div>

> [!NOTE]  
> Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, reportez-vous à la rubrique <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configuration de l’intégration avec Office Web Apps Server et Lync Server 2013</A>.


</div></td>
<td><p>Utilisateur du domaine qui est membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Support du logiciel serveur et de l’infrastructure dans Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Déterminez la configuration système requise pour Lync Server 2013</a> dans la documentation de planification.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p><strong>Création de la topologie interne appropriée pour prendre en charge la conférence</strong></p></td>
<td><p>Exécutez le générateur de topologie pour ajouter des conférences à la topologie, puis publiez la topologie.</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers 2013 Lync Server (de manière à ce que le générateur de topologie puisse configurer les DACL requis)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définissez et configurez une topologie dans le générateur de topologies de Lync Server 2013</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configuration des stratégies de conférence et de la prise en charge</strong></p></td>
<td><p>Utilisez le panneau de configuration de Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affecter des utilisateurs au rôle [] ou CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation opérations.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble des conférences dans Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Définition de la configuration requise pour les conférences dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

