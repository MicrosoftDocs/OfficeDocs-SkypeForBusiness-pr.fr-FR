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
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Sauvegarder et restaurer des feuilles de calcul pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Le plan de sauvegarde et de restauration de votre organisation doit contenir des détails sur la façon dont et quand vous sauvegardez des données et des paramètres. Vous pouvez utiliser les feuilles de calcul présentées ici pour documenter ces informations pour votre déploiement spécifique et pour les besoins en matière de sauvegarde et de restauration de votre organisation.

Utilisez les feuilles de calcul suivantes pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer des informations de base de données, de magasin de fichiers et de paramètres pour un pool de serveurs Lync ou un serveur Standard Edition Server. Conservation d’une ou plusieurs copies de ces feuilles de calcul dans un emplacement sécurisé de sorte qu’elles soient facilement accessibles si vous devez restaurer Lync Server.

<div>


> [!NOTE]  
> Les feuilles de calcul de cette section couvrent uniquement les informations nécessaires pour restaurer les données et les paramètres des bases de données et serveurs Lync Server. Si vous avez besoin de documenter d’autres informations de restauration, telles que les informations de réinstallation de systèmes d’exploitation et autres logiciels, utilisez les plans de déploiement de votre organisation ainsi que les plans de sauvegarde et de restauration pour répondre à ces exigences.



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
<th>Bases</th>
<th>Nom du serveur (FQDN)</th>
<th>Planning de sauvegarde</th>
<th>Outil de sauvegarde de base de données</th>
<th>Jeu de sauvegarde</th>
<th>Destination de la sauvegarde</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de données RTC sur le serveur principal pour les données utilisateur</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsUserData</strong></p></td>
<td><p>Nommer</p>
<p>Leur</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>Base de données LcsLog (nom par défaut) sur le serveur de base de données d’archivage</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nommer</p>
<p>Leur</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de données LcsCdr sur analyse du serveur de base de données pour les enregistrements des détails des appels (CdR)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nommer</p>
<p>Leur</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Base de données QoEMetrics sur l’analyse des données d’un serveur de base de données</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nommer</p>
<p>Leur</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de données de conversation permanente</p></td>
<td></td>
<td></td>
<td><p>Outil de gestion SQL Server ou cmdlet <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Nommer</p>
<p>Leur</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Aucune sauvegarde ou restauration requise pour les bases de données suivantes :

  - Rtcdyn. Les données utilisateur temporaires de cette base de données ne sont pas nécessaires à la restauration du service.

  - Rtcab. La base de données du carnet d’adresses est recréée automatiquement à partir de la liste d’adresses globale dans les services de domaine Active Directory (AD DS).

  - Rgsdyn. Il n’est pas nécessaire de restaurer les données du service de groupe de réponse temporaire dans cette base de données pour la restauration du service.

  - Cpsdyn. Les informations dynamiques pour l’application de stationnement d’appel ne sont pas nécessaires pour la restauration du service.

  - MgcComp. La base de données de conformité pour la conversation permanente n’est pas nécessaire pour la restauration du service.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Feuille de calcul de sauvegarde et de restauration du magasin de fichiers

Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les magasins de fichiers. Les magasins de fichiers contiennent des données telles que les métadonnées de contenu de la réunion, les journaux de mise à jour des mises à jour pour les mises à jour de l’appareil et les fichiers audio pour le groupe de réponse, le parc d’appels et les applications d’annonce.

### <a name="file-store-information-for-backup-and-restoration"></a>Informations de stockage de fichiers pour la sauvegarde et la restauration

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
<th>Nom du serveur (FQDN)</th>
<th>Planning de sauvegarde</th>
<th>Outil de sauvegarde du système de fichiers</th>
<th>Partage de fichiers à sauvegarder *</th>
<th>Destination de la sauvegarde</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Magasin de fichiers de Lync Server</p></td>
<td></td>
<td></td>
<td><p>Outil de sauvegarde standard, tel que Robocopy</p></td>
<td><p>Sur le serveur de fichiers Enterprise Edition. Sur l’édition standard par défaut, pour le déploiement Standard Edition. En règle générale, un par site.</p></td>
<td></td>
<td><p>Les fichiers nommés <strong>réunion. actif</strong> ne doivent pas être sauvegardés. Ces fichiers sont utilisés et sont verrouillés lors d’une réunion.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Sauvegarder les paramètres et la feuille de calcul de restauration

Utilisez le tableau suivant pour enregistrer les informations dont vous avez besoin pour sauvegarder et restaurer les paramètres.

### <a name="settings-information-for-backup-and-restoration"></a>Informations de paramètres pour la sauvegarde et la restauration

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
<th>Bases</th>
<th>Nom du serveur (FQDN)</th>
<th>Planning de sauvegarde</th>
<th>Outil de sauvegarde</th>
<th>Nom du fichier de configuration (. Xml)</th>
<th>Emplacement de sauvegarde</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de données XDS dans le magasin central de gestion pour la configuration de la topologie (globale)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Base de données lis dans le magasin central de gestion pour E9-1-1 informations d’emplacement (Global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsLisConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Base de données RgsConfig du serveur principal pour la configuration de Response Group (pool)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsRgsConfiguration</strong></p></td>
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

