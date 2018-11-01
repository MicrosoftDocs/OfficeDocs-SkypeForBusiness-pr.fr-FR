---
title: 'Besoins de sauvegarde et de restauration dans Lync Server 2013 : données'
TOCTitle: 'Besoins de sauvegarde et de restauration dans Lync Server 2013 : données'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202194(v=OCS.15)
ms:contentKeyID: 53095556
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Besoins de sauvegarde et de restauration dans Lync Server 2013 : données

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server utilise des paramètres et des informations de configuration qui sont stockés dans des bases de données, ainsi que des données stockées dans des bases de données et des magasins de fichiers. Cette rubrique décrit les données qu’il est nécessaire de sauvegarder afin de pouvoir rétablir le service si votre organisation est confrontée à une défaillance ou une panne, puis elle identifie les données et les composants utilisés par Lync Server qu’il est nécessaire de sauvegarder séparément.

## Paramètres et configuration requis

Cette rubrique inclut des procédures pour la sauvegarde et la restauration des paramètres et informations de configuration requis pour la récupération du service Lync Server. Ces informations de configuration se trouvent dans le magasin central de gestion, dans une autre base de données principale ou sur un serveur Standard Edition.

Le tableau suivant identifie les paramètres et informations de configuration qu’il est nécessaire de sauvegarder et restaurer.

### Paramètres et données de configuration

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de données</th>
<th>Emplacement de stockage</th>
<th>Description / Quand les sauvegarder</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration de la topologie</p></td>
<td><p>magasin central de gestion (base de données : Xds.mdf)</p></td>
<td><p>Paramètres de la topologie, de stratégie et de configuration</p>
<p>À sauvegarder dans le cadre de vos sauvegardes régulières et après avoir utilisé le Panneau de configuration Lync Server ou des applets de commande pour modifier votre configuration ou vos stratégies.</p></td>
</tr>
<tr class="even">
<td><p>Informations d’emplacement</p></td>
<td><p>magasin central de gestion (base de données : Lis.mdf)</p></td>
<td><p>Informations de configuration Voix Entreprise E9-1-1 (Enhanced 9-1-1). Ces informations sont généralement statiques.</p>
<p>À sauvegarder dans le cadre de vos sauvegardes régulières.</p></td>
</tr>
<tr class="odd">
<td><p>Informations de configuration Response Group</p></td>
<td><p>Serveur principal ou serveur Standard Edition (base de données : RgsConfig.mdf)</p></td>
<td><p>Groupes d’agents, files d’attente et flux de travail Response Group.</p>
<p>À sauvegarder dans le cadre de vos sauvegardes régulières et après avoir ajouté ou modifié des groupes d’agents, files d’attente ou flux de travail.</p></td>
</tr>
</tbody>
</table>


## Données requises

Voici une liste des données Lync Server que vous devez sauvegarder afin de pouvoir restaurer le service Lync Server en cas de panne.

Notez que certains types de données ne sont pas requis pour la récupération. Cette rubrique ne propose pas les procédures de sauvegarde de ces types de données, qui comprennent notamment :

  - Données utilisateur temporaires, telles que les systèmes d’extrémité et les abonnements, les serveurs de conférence actifs, les états temporaires des conférences (base de données : RtcDyn.mdf)

  - Données de carnet d’adresses (bases de données : Rtcab.mdf et Rtcab1.mdf). La base de données de carnet d’adresses est régénérée automatiquement à partir de services de domaine Active Directory

  - Informations dynamiques pour l’application de parcage d’appel (base de données : CpsDyn.mdf)

  - Données Response Group temporaires, telles que l’état de connexion de l’agent et les informations d’attente des appels (base de données : RgsDyn.mdf)

  - La base de données de conformité pour conversation permanente (base de données : MgcComp.mdf). Si la conformité de la conversation permanente est activée, les informations de la base de données de conformité conversation permanente sont temporaires tant qu’un adaptateur est configuré pour lire les informations de la base de données et les convertir dans un autre format. C’est pourquoi la base de données de conformité pour conversation permanente est considérée comme étant temporaire.
    
    Lync Server 2013 serveur de conversations permanentes est fourni avec un adaptateur XML. Vous pouvez également installer des adaptateurs personnalisés qui déplacent ces données vers d’autres sources, telles que des archives hébergées Exchange.

Le tableau suivant identifie les données qu’il est nécessaire de sauvegarder et restaurer.

### Données stockées dans des bases de données

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de données</th>
<th>Emplacement de stockage</th>
<th>Description / Quand les sauvegarder</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Données utilisateur persistantes</p></td>
<td><p>Serveur principal ou serveur Standard Edition (base de données : RTCXDS.mdf)</p></td>
<td><p>Droits d’utilisateur, listes de contacts des utilisateurs, données du serveur ou pool, conférences planifiées, etc. Ces données utilisateur ne comprennent pas le contenu téléchargé dans une conférence.</p>
<p>À sauvegarder dans le cadre de vos sauvegardes régulières. Ces informations sont dynamiques, mais la perte des mises à jour n’est pas catastrophiques pour Lync Server si vous avez besoin de restaurer votre dernière sauvegarde régulière. Si les listes de contacts sont cruciales pour votre organisation, vous pouvez sauvegarder ces données plus souvent.</p></td>
</tr>
<tr class="even">
<td><p>Données d’archivage</p></td>
<td><p>Base de données d’archivage (base de données : LcsLog.mdf)</p>
<p>Ces données peuvent être stockées dans Exchange 2013, si vous avez activé l’option d’intégration Microsoft Exchange. Dans le cas contraire, ces données sont conservées dans une base de données d’archivage Lync Server, qui peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de bases de données séparé.</p></td>
<td><p>Contenu de messagerie instantanée et des réunions.</p>
<p>Ces données ne sont pas cruciales pour Lync Server, mais elles peuvent l’être pour votre organisation à des fins de contrôle. Déterminez votre calendrier de sauvegarde en conséquence.</p>
<p>Lync Server prend en charge le mode de récupération simple uniquement pour les bases de données d’archivage. Avec le mode de récupération simple, les bases de données sont récupérées à la date de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer une base de données à la date de la défaillance ou à un moment spécifique.</p></td>
</tr>
<tr class="odd">
<td><p>Données de surveillance</p></td>
<td><p>Bases de données de surveillance (LcsCDR.mdf et QoeMetrics.mdf)</p>
<p>Ces bases de données sont colocalisées avec une autre base de données Lync Server ou sont autonomes sur un serveur de bases de données séparé.</p></td>
<td><p>Enregistrements des détails des appels (LcsCDR.mdf) et mesures de la qualité de l’expérience (QoeMetrics.mdf).</p>
<p>Les enregistrements des détails des appels sont dynamiques et peuvent s’avérer cruciaux pour votre entreprise. Définissez votre calendrier de sauvegarde en déterminant si vous avez besoin de ces enregistrements à des fins de contrôle.</p>
<p>Les informations sur la qualité de l’expérience sont dynamiques. La perte des données QoE n’est pas cruciale pour le fonctionnement de Lync Server, mais elle peut l’être pour votre entreprise. Définissez votre calendrier de sauvegarde en fonction de l’importance de ces informations pour votre organisation.</p>
<p>Lync Server prend en charge le mode de récupération simple uniquement pour les bases de données de surveillance. Avec le mode de récupération simple, les bases de données sont récupérées à la date de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer une base de données à la date de la défaillance ou à un moment spécifique.</p></td>
</tr>
<tr class="even">
<td><p>Données de conversation permanente</p></td>
<td><p>Base de données de conversation permanente (mgd.mdf).</p>
<p>Cette base de données peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de bases de données séparé.</p></td>
<td><p>Les données de conversation permanente représentent du contenu de conversation publié dans des salles de conversation. Ces données sont souvent critiques pour l’entreprise.</p>
<p>Vous pouvez choisir d’utiliser la sauvegarde SQL Server ou d’exporter la base de données en utilisant l’applet de commande <strong>Export-CsPersistentChatData</strong> fournie avec Lync Server. Pour la récupération des données, vous pouvez importer et restaurer la base de données à la date de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer la base de données à la date exacte de la panne.</p></td>
</tr>
</tbody>
</table>


## Données de magasin de fichiers requises

Dans un déploiement Enterprise Edition, le magasin de fichiers Lync Server se trouve sur un serveur de fichiers. Dans un déploiement Standard Edition, le magasin de données Lync Server se trouve par défaut sur le serveur Standard Edition. En règle générale, il existe un magasin de fichiers Lync Server partagé pour un site. Le magasin de fichiers conversation permanente utilise le même partage de fichier que le magasin de fichiers Lync Server.

Les emplacements de magasin de fichiers s’identifient sous la forme \\\\serveur\\nom du partage. Pour trouver les emplacements propres à vos magasins de fichiers, ouvrez le Générateur de topologie et examinez le nœud **Magasins de fichiers**.

Le tableau suivant identifie les magasins de fichiers qu’il est nécessaire de sauvegarder et restaurer.

### Magasins de fichiers

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de données</th>
<th>Emplacement de stockage</th>
<th>Description / Quand les sauvegarder</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Magasin de fichier Lync Server</p></td>
<td><p>Généralement sur un serveur de fichiers, un cluster de fichiers ou un serveur Standard Edition</p></td>
<td><p>Contenu des réunions, métadonnées du contenu des réunions, journaux de conformité des réunions, fichiers des données d’application, fichiers de mise à jour pour les mises à jour des périphériques, fichiers audio pour les applications Response Group, de parcage d’appel et d’annonce et fichiers publiés dans les salles de conversation permanente.</p>
<p>À sauvegarder dans le cadre de vos sauvegardes régulières.</p></td>
</tr>
</tbody>
</table>


## Autres sauvegardes requises

Pour garantir la restauration des services Lync Server en cas de panne, vous devez sauvegarder les composants requis qui ne font pas partie de Lync Server. Les composants suivants ne sont pas sauvegardés ni restaurés dans le cadre du processus de sauvegarde et de restauration de Lync Server décrit dans ce document :

  - **services de domaine Active Directory**   Vous devez sauvegarder AD DS à l’aide des outils Active Directory en même temps que vous sauvegardez Lync Server. Il est important que AD DS soit synchronisé avec Lync Server, pour éviter les problèmes qui peuvent se produire quand Lync Server attend des objets contact qui ne correspondent pas à ceux d’AD DS. AD DS stocke les paramètres suivants qui sont utilisés par Lync Server :
    
      - URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur
    
      - Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence.
    
      - Un pointeur vers le magasin central de gestion
    
      - Compte d’authentification Kerberos (un objet ordinateur facultatif) et groupes de sécurité Lync Server.
    
    Pour plus d’informations sur la sauvegarde et la restauration des services de domaine Active Directory dans Windows Server 2008, voir « Guide pas à pas de sauvegarde et de récupération des services de domaine Active Directory (AD DS) » à l’adresse <http://go.microsoft.com/fwlink/?linkid=209105>.

  - **Autorité de certification et certificats**   Utilisez la stratégie de votre organisation pour sauvegarder votre autorité de certification et vos certificats. Si vous utilisez des clés privées exportables, vous pouvez sauvegarder le certificat et la clé privée, puis les exporter si vous suivez les procédures indiquées dans ce document afin de restaurer Lync Server. Si vous utilisez une autorité de certification interne, vous pouvez vous réinscrire si vous avez besoin de restaurer Lync Server. Il est important de conserver la clé privée dans un endroit sécurisé où elle sera disponible en cas de panne d’un ordinateur.

  - **System Center Operations Manager**   Si vous utilisez Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager) pour surveiller votre déploiement Lync Server, vous pouvez éventuellement sauvegarder les données créées pendant la surveillance de Lync Server. Utilisez votre processus de sauvegarde SQL Server standard pour sauvegarder les fichiers System Center Operations Manager. Ces fichiers ne sont pas restaurés pendant la récupération.

  - **Configuration des passerelles PSTN (réseau téléphonique commuté)**   Si vous utilisez Voix Entreprise ou des serveurs Survivable Branch Appliance, vous devez sauvegarder la configuration des passerelles PSTN. Contactez votre fournisseur pour plus d’informations sur la sauvegarde et la restauration des configurations des passerelles PSTN.

  - **Versions coexistantes de Lync Server ou Office Communications Server**   Si votre déploiement Lync Server 2013 coexiste avec Lync Server 2010 ou une version antérieure de Office Communications Server, vous ne pouvez pas utiliser les procédures de ce document pour la sauvegarde ou la restauration de la version antérieure. Vous devez utiliser à la place les procédures de sauvegarde et de restauration décrites pour votre version antérieure. Pour plus d’informations sur la sauvegarde et la restauration de Lync Server 2010, voir <http://go.microsoft.com/fwlink/?linkid=265417> . Pour plus d’informations sur la sauvegarde et la restauration de Microsoft Office Communications Server 2007 R2, voir <http://go.microsoft.com/fwlink/?linkid=168162>.

  - **Informations d’infrastructure**   Sauvegardez les informations relatives à votre infrastructure, telles que la configuration de votre pare-feu, de l’équilibrage de la charge, des services Internet (IIS), les enregistrements DNS (Domain Name System) et les adresses IP et la configuration DHCP (Dynamic Host Configuraton Protocol). Pour plus d’informations sur la sauvegarde de ces composants, contactez leurs fournisseurs respectifs.

  - **Microsoft Exchange et la messagerie unifiée Exchange (UM)**   Sauvegardez et restaurez Microsoft Exchange et messagerie unifiée Exchange comme indiqué dans la documentation Microsoft Exchange. Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server 2013, voir <http://go.microsoft.com/fwlink/?linkid=285384>. Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server 2010, voir <http://go.microsoft.com/fwlink/?linkid=209179>.
    
    Notez que dans Lync Server 2013 vous avez la possibilité de stocker des listes de contacts, des photos en haute définition et des données d’archivage dans Exchange 2013. Consultez la liste suivante pour apprendre à sauvegarder ces types de données :
    
      - Les **photos en haute définition** sont sauvegardées dans le cadre de la sauvegarde Exchange Server.
    
      - Le **magasin de contact unifié** est une nouveauté de Lync Server 2013. Il permet aux utilisateurs de conserver toutes leurs informations de contact dans Exchange 2013.
        
        Assurez-vous que les sauvegardes des utilisateurs sont à jour en ce qui concerne leurs contacts dans le magasin de contact unifié ou sur le serveur principal Lync. Les scénarios suivants montrent les problèmes qui peuvent se poser pour le sauvegarde et la restauration lors de la migration des contacts utilisateur vers le magasin de contact unifié.
        
        **Scénario 1 :** les contacts des utilisateurs sont migrés vers le magasin de contact unifié et une restauration est effectuée à partir d’une sauvegarde Lync Server datant d’avant la migration des contacts. Dans ce scénario, l’utilisateur aura des contacts périmés pendant un jour jusqu’à ce que la tâche de migration Lync Server commence à migrer les contacts vers Exchange. (Notez que dans la mesure où les contacts des utilisateurs ont été précédemment migrés vers le magasin de contact unifié, les informations de contact Exchange seront utilisées). Aucune intervention de l’administrateur n’est nécessaire dans ce scénario.
        
        **Scénario 2 :** Les contacts des utilisateurs ont été précédemment stockés dans le magasin de contact unifié, mais remplacés (roll back). Une restauration est effectuée à partir dune sauvegarde Lync Server datant du stockage des contacts dans le magasin de contact unifié. Dans ce scénario, un message d’erreur `Error: Incorrect Exchange Version` dans les journaux du client ou Lync Server peut indiquer ce problème. L’utilisateur sera en mesure d’accéder à sa liste des contacts dans Lync 2013 directement à partir d’Exchange, mais l’état du client ne correspondra pas à l’état Lync Server. Pour corriger cela, un administrateur doit exécuter les applets de commande **Invoke-CsUCSRollback** pour les utilisateurs concernés.
    
      - Les **données d’archivage** peuvent être stockées dans Exchange 2013. Ces données ne sont pas critiques à Lync Server, mais peuvent l’être pour votre organisation (contraintes réglementaires). Si les données d’archivage sont stockées dans Exchange et sont critiques pour votre organisation, appliquez les Exchangeprocédures de sauvegarde et de restauration. Notez que les données d’archivage stockées dans Exchange ne peuvent pas être redéplacées dans Lync Server. De plus, il n’est pas possible de déplacer les données déjà stockées dans la base de données d’archivage Lync vers Exchange.

