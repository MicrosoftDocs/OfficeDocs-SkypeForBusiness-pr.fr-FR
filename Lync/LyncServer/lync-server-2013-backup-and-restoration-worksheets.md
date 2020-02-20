---
title: 'Lync Server 2013 : feuilles de calcul de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af90939e8034c8bf240ec04514a1a30044a14c94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Le plan de sauvegarde et de restauration de votre organisation doit contenir des détails sur la manière et le moment de sauvegarder les données et les paramètres. Vous pouvez utiliser les feuilles de calcul présentées ici pour vous aider à documenter ces informations pour votre déploiement et pour les besoins de votre organisation en matière de sauvegarde et de restauration.

Utilisez les feuilles de calcul suivantes pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les informations de base de données, de magasin de fichiers et de paramètres d’un pool Lync Server ou d’un serveur Standard Edition Server. Conservez une ou plusieurs copies de ces feuilles de calcul dans un endroit sûr afin qu’elles soient facilement accessibles si vous devez restaurer Lync Server.

<div>


> [!NOTE]  
> Les feuilles de cette section traitent uniquement les informations requises pour restaurer les données et les paramètres des serveurs et des bases de données Lync Server. Si vous devez documenter d’autres informations de restauration, telles que les informations de réinstallation des systèmes d’exploitation et d’autres logiciels, utilisez les plans de déploiement de votre organisation, ainsi que les plans de sauvegarde et de restauration pour répondre à ces exigences.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Feuille de calcul de sauvegarde et de restauration de base de données

Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer des bases de données Lync Server.

### <a name="database-information-for-backup-and-restoration"></a>Informations de base de données pour la sauvegarde et la restauration

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de données</th>
<th>Nom de serveur (FQDN)</th>
<th>Planification de la sauvegarde</th>
<th>Outil de sauvegarde de base de données</th>
<th>Jeu de sauvegarde</th>
<th>Destination de la sauvegarde</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de données RTC sur le serveur principal pour les données utilisateur</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-applet csuserdata</strong></p></td>
<td><p>Nom</p>
<p>Pire</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>Base de données LcsLog (nom par défaut) sur le serveur de base de données d’archivage</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nom</p>
<p>Pire</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de données LcsCdr sur le serveur de base de données de surveillance pour les enregistrements des détails des appels</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nom</p>
<p>Pire</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Base de données QoEMetrics sur le serveur de base de données de surveillance pour les données QoE (qualité de l’expérience)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nom</p>
<p>Pire</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de données de conversation permanente</p></td>
<td></td>
<td></td>
<td><p>Outil de gestion SQL Server ou cmdlet <strong>Export-applet cspersistentchatdata</strong></p></td>
<td><p>Nom</p>
<p>Pire</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Aucune sauvegarde ou restauration n’est requise pour les bases de données suivantes :

  - RTCDyn. Les données utilisateur temporaires de cette base de données ne sont pas nécessaires à la restauration du service.

  - RTCAb. La base de données de carnet d’adresses est recréée automatiquement à partir de la liste d’adresses globale (LAG) dans les services de domaine Active Directory.

  - Rgsdyn. Les données de service Response Group de cette base de données ne sont pas nécessaires à la restauration du service.

  - Cpsdyn. Les informations dynamiques pour l’application de parcage d’appel ne sont pas nécessaires à la restauration du service.

  - MgcComp. La base de données de conformité pour la conversation permanente n’est pas nécessaire pour la restauration du service.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Feuille de calcul de sauvegarde et de restauration du magasin de fichiers

Utilisez le tableau suivant pour enregistrer les informations nécessaires à la sauvegarde et à la restauration des magasins de fichiers. Les magasins de fichiers contiennent des données telles que des métadonnées de contenu de réunion, des journaux de conformité de réunion, des journaux de mise à jour pour les mises à jour de périphérique et des fichiers audio pour le groupe de réponse, le parcage d’appel et les applications d’annonce.

### <a name="file-store-information-for-backup-and-restoration"></a>Informations sur le magasin de fichiers pour la sauvegarde et la restauration

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Contenu</th>
<th>Nom de serveur (FQDN)</th>
<th>Planification de la sauvegarde</th>
<th>Outil de sauvegarde de système de fichiers</th>
<th>Partage de fichiers à sauvegarder *</th>
<th>Destination de la sauvegarde</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Magasin de fichiers Lync Server</p></td>
<td></td>
<td></td>
<td><p>Outil de sauvegarde standard, tel que Robocopy</p></td>
<td><p>Sur le serveur de fichiers pour Enterprise Edition. Sur Standard Edition, par défaut, pour le déploiement Standard Edition. En règle générale, un par site.</p></td>
<td></td>
<td><p>Les fichiers nommés <strong>Meeting. active</strong> ne doivent pas être sauvegardés. Ces fichiers sont en cours d’utilisation et sont verrouillés pendant qu’une réunion a lieu.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Feuille de calcul de restauration et de sauvegarde des paramètres

Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les paramètres.

### <a name="settings-information-for-backup-and-restoration"></a>Informations sur les paramètres de sauvegarde et de restauration

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de données</th>
<th>Nom de serveur (FQDN)</th>
<th>Planification de la sauvegarde</th>
<th>Outil de sauvegarde</th>
<th>Nom du fichier de configuration (. Xml)</th>
<th>Emplacement de sauvegarde</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de données XDS dans le magasin central de gestion pour la configuration de la topologie (Global)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Base de données lis dans le magasin central de gestion pour les informations d’emplacement E9-1-1 (Global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsLisConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Base de données RgsConfig sur le serveur principal pour la configuration Response Group (pool)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-applet csrgsconfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

