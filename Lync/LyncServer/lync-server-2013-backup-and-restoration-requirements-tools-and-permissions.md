---
title: 'Spécifications de sauvegarde et de restauration : outils et autorisations'
TOCTitle: 'Spécifications de sauvegarde et de restauration : outils et autorisations'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202171(v=OCS.15)
ms:contentKeyID: 53095393
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Spécifications de sauvegarde et de restauration : outils et autorisations

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette rubrique identifie les outils que vous pouvez utiliser pour sauvegarder et restaurer Lync Server 2013, les autorisations dont vous avez besoin et si vous pouvez exécuter les commandes à distance ou localement. En particulier, cette rubrique aborde les outils fournis avec Lync Server pour la sauvegarde et la restauration.

## Sauvegardes

Pour sauvegarder Lync Server, utilisez les outils identifiés dans le tableau suivant. Toutes les commandes dont vous avez besoin pour sauvegarder Lync Server peuvent être scriptées et exécutées à distance.

### Outils pour sauvegarder Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour sauvegarder :</th>
<th>Utilisez cet outil ou applet de commande :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Données de configuration de topologie (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Données du service Informations d’emplacement (E9-1-1) (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Données de configuration pour Response Group (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Données utilisateur persistantes (base de données Rtcxds.mdf)</p>
<p>ID de conférence</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Base de données d’archivage (LcsLog.mdf)</p></li>
<li><p>Base de données des enregistrements des détails d’appels de surveillance (LcsCDR.mdf)</p></li>
<li><p>Base de données QoE de surveillance (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Outil de base de données SQL Server, tel que SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Base de données de conversation permanente (Mgc.mdf)</p></td>
<td><p>Procédures de sauvegarde SQL Server ou Export-CsPersistentChatData. Export-CsPersistentChatData exporte les données de conversation permanente dans un fichier.</p></td>
</tr>
<tr class="odd">
<td><p>Tous les magasins de fichiers : magasin de fichiers Lync Server, magasin de fichiers d’archivage</p>

> [!NOTE]  
> Les fichiers nommés <strong>Meeting.Active</strong> ne doivent pas être sauvegardés. Ces fichiers sont en cours d’utilisation et verrouillés pendant le déroulement d’une réunion.

</td>
<td><p>Outil de gestion de système de fichiers standard, comme Robocopy.</p></td>
</tr>
</tbody>
</table>


## Restauration

Pour restaurer Lync Server, utilisez les outils indiqués dans le tableau suivant. Toutes les commandes dont vous avez besoin pour restaurer Lync Server peuvent être scriptées. Certaines peuvent être exécutées à distance, mais d’autres doivent être exécutées localement, comme spécifié dans le tableau suivant.

### Outils pour restaurer Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour :</th>
<th>Utilisez cet outil ou applet de commande :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Construire un ordinateur neuf ou propre</p></td>
<td><ul>
<li><p>Logiciel d’installation du système d’exploitation Windows</p></li>
<li><p>Logiciel d’installation de SQL Server</p></li>
<li><p>Composant logiciel enfichable Certificates Microsoft Management Console (MMC), si vous restaurez les certificats à l’aide d’une clé privée exportable</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Restaurer les données d’un magasin de fichiers</p></td>
<td><p>Outil de gestion de système de fichiers standard, comme Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Recréer des bases de données vides et définir des autorisations pour ce qui suit :</p>
<ul>
<li><p>magasin central de gestion</p></li>
<li><p>Serveur principal</p></li>
<li><p>Base de données de surveillance</p></li>
<li><p>Base de données d’archivage</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Restaurer le pointeur des services de domaine Active Directory vers le magasin central de gestion</p>

> [!NOTE]  
> Si vous perdez le point de connexion de service, vous pouvez réexécuter cette applet de commande.

</td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importer la topologie, les stratégies et les paramètres de configuration dans le magasin central de gestion (Xds.mdf)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Publier et activer la topologie</p></td>
<td><p>Générateur de topologie</p>
<p>-ou-</p>
<p>Publish-CsTopology et Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Activer la dernière topologie publiée</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Réinstaller des composants Lync Server</p></td>
<td><p>Programme d’installation de Lync Server</p>

> [!NOTE]  
> Situé dans le dossier ou le support d’installation de Lync Server à l’emplacement \setup\amd64\Setup.exe.

</td>
</tr>
<tr class="odd">
<td><p>Restaurer les données d’information d’emplacement (E9-1-1) (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Restaurer les données utilisateur persistantes (Rtcxds.mdf)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Restaurer les données de configuration pour Response Group (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>

> [!NOTE]  
> Si la configuration est restaurée dans un pool nouvellement déployé et dont la base de données ne contient pas de données Response Group, vous devez utiliser l’option –OverwriteOwner. Utilisez cette option même si les données en cours de restauration se trouvent dans un pool portant le même nom de domaine complet. Sinon, l’importation est vouée à l’échec, car Active Directory contient déjà des objets contact pour les services Response Group.

</td>
</tr>
<tr class="even">
<td><p>Restaurer les bases de données suivantes :</p>
<ul>
<li><p>Base de données d’archivage (LcsLog.mdf)</p></li>
<li><p>Bases de données de surveillance : base de données des enregistrements de détails d’appels (LcsCDR.mdf) et base de données QoE (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Outils de gestion de base de données SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Base de données de conversation permanente (Mgs.mdf)</p></td>
<td><p>Procédures de restauration SQL Server ou Import-CsPersistentChatData. Vous pouvez utiliser Import-CsPersistentChatData avec un fichier créé par Export-CsPersistentChatData ; les données seront importées dans la base de données de conversation permanente.</p></td>
</tr>
</tbody>
</table>


## Autorisations requises

Les utilisateurs doivent être membres du groupe **RTCUniversalServerAdmins** pour exécuter toutes les commandes décrites dans cette rubrique. La plupart des commandes de sauvegarde et de restauration ne prennent pas en charge le contrôle d’accès basé sur un rôle. Notez toutefois les deux exceptions que sont les applets de commande de conversation permanente Export-CsPersistentChatData et Import-CsPersistentChatData, qui doivent être exécutées par un utilisateur membre du groupe CsPersistentChatAdministrator. Pour exécuter l’Assistant Déploiement de Lync Server, un utilisateur doit également être membre du groupe Administrateurs local.

