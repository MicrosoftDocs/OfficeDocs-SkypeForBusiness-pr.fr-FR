---
title: Feuilles de travail de sauvegarde et de restauration
TOCTitle: Feuilles de travail de sauvegarde et de restauration
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202169(v=OCS.15)
ms:contentKeyID: 53095381
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Feuilles de travail de sauvegarde et de restauration

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le plan de sauvegarde et de restauration pour votre organisation doit fournir des détails sur la façon et le moment où vous sauvegardez les données et les paramètres. Vous pouvez utiliser les feuilles de travail présentées ici pour vous aider à documenter les informations relatives à vos déploiements spécifiques et aux exigences de sauvegarde et de restauration de votre organisation.

Utilisez les feuilles de travail suivantes pour enregistrer les informations nécessaires à la sauvegarde et à la restauration de la base de données, du magasin de fichiers, et les informations relatives aux paramètres pour un pool Lync Server ou un serveur Standard Edition. Conservez une ou plusieurs copies de ces feuilles de travail dans un emplacement sécurisé et facile d’accès dans le cas où vous deviez effectuer une restauration de Lync Server.

> [!NOTE]  
> Les feuilles de travail présentes dans cette section couvrent uniquement les informations nécessaires pour restaurer les données et les paramètres des bases de données et des serveurs Lync Server. Si vous devez documenter d’autres informations de restauration, telles que les informations de réinstallation des systèmes d’exploitation et d’autres logiciels, utilisez les plans de déploiement ainsi que les plans de sauvegarde et de restauration de votre organisation pour répondre à ces exigences.

## Feuille de travail de sauvegarde et de restauration de la base de données

Utilisez le tableau suivant pour enregistrer les informations nécessaires à la sauvegarde et à la restauration des bases de données Lync Server.

### Informations sur la base de données pour la sauvegarde et la restauration

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
<th>Nom de domaine complet (FQDN) du serveur</th>
<th>Planification de la sauvegarde</th>
<th>Outil de sauvegarde de la base de données</th>
<th>Définition de la sauvegarde</th>
<th>Destination de la sauvegarde</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de données Rtc sur le serveur principal pour les données utilisateur</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Applet de commande <strong>Export-CsUserData</strong></p></td>
<td><p>Nom :</p>
<p>Expiration :</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>Base de données LcsLog (nom par défaut) sur le serveur de base de données d’archivage</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nom :</p>
<p>Expiration :</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de données LcsCdr sur le serveur de base de données de surveillance pour l’enregistrement des détails des appels</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nom :</p>
<p>Expiration :</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Base de données QoEMetrics sur le serveur de base de données de surveillance pour des données de qualité de l’expérience (QoE)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Outil de gestion SQL Server</p></td>
<td><p>Nom :</p>
<p>Expiration :</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de données de conversation permanente</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>Outil de gestion SQL Server ou applet de commande <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Nom :</p>
<p>Expiration :</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


Aucune sauvegarde et restauration n’est requise pour les bases de données suivantes :

  - Rtcdyn. Les données utilisateur temporaires de cette base de données ne sont pas nécessaires pour la restauration du service.

  - Rtcab. La base de données du carnet d’adresses est automatiquement recréée à partir de la liste d’adresses globale dans les services de domaine Active Directory.

  - Rtcab. Les données du service Response Group temporaires de cette base de données ne sont pas nécessaires pour la restauration du service.

  - Cpsdyn. Les informations dynamiques pour cette application de parcage d’appel ne sont pas nécessaires pour la restauration du service.

  - MgcComp. La base de données de conformité pour la conversation permanente n’est pas nécessaire pour la restauration de service.

## Feuille de travail de sauvegarde et de restauration du magasin de fichiers

Utilisez le tableau suivant pour enregistrer les informations nécessaires à la sauvegarde et à la restauration des magasins de fichiers. Les magasins de fichiers contiennent des données telles que des métadonnées de contenu de réunion, des journaux de conformité de réunion, des journaux de mise à jour pour des mises à jour de périphériques ainsi que des fichiers audio pour les applications Response Group, de parcage d’appel et d’annonce.

### Informations sur le magasin de fichiers pour la sauvegarde et la restauration

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
<th>Nom de domaine complet (FQDN) du serveur</th>
<th>Planification de la sauvegarde</th>
<th>Outil de sauvegarde du système de fichiers</th>
<th>Partage de fichiers à sauvegarder *</th>
<th>Destination de la sauvegarde</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>magasin de fichiers Lync Server</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>Outil de sauvegarde standard comme Robocopy</p></td>
<td><p>Sur un serveur de fichiers pour Enterprise Edition. Sur Standard Edition par défaut, pour un déploiement Standard Edition. Généralement, un par site.</p></td>
<td><p></p></td>
<td><p>Les fichiers nommés <strong>Meeting.Active</strong> ne doivent pas être sauvegardés. Ces fichiers sont utilisés et verrouillés lors d’une réunion.</p></td>
</tr>
</tbody>
</table>


## Feuille de travail de sauvegarde et de restauration des paramètres

Utilisez le tableau suivant pour enregistrer les informations nécessaires à la sauvegarde et à la restauration des paramètres.

### Informations sur les paramètres pour la sauvegarde et la restauration

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
<th>Nom de domaine complet (FQDN) du serveur</th>
<th>Planification de la sauvegarde</th>
<th>Outil de sauvegarde</th>
<th>Nom du fichier de configuration (.xml)</th>
<th>Emplacement de sauvegarde</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de données Xds dans la configuration de la topologie (globale) du magasin central de gestion</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Applet de commande <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Base de données Lis dans le magasin central de gestion pour les informations d’emplacement E9-1-1 (global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Applet de commande <strong>Export-CsLisConfiguration</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Base de données RgsConfig sur le serveur principal pour la configuration (pool) Response Group</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Applet de commande <strong>Export-CsRgsConfiguration</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>

