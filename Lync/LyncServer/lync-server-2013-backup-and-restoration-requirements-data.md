---
title: 'Lync Server 2013 : exigences en matière de sauvegarde et de restauration : données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4688c143a16ffd7113a03172274436f7c1371694
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : données

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-26_

Lync Server utilise les paramètres et les informations de configuration stockés dans les bases de données, ainsi que les données stockées dans les bases de données et les magasins de fichiers. Cette rubrique décrit les données que vous devez sauvegarder pour pouvoir restaurer le service si votre organisation rencontre une défaillance ou une panne, et identifie également les données et les composants utilisés par Lync Server que vous devez sauvegarder séparément.

<div>

## <a name="settings-and-configuration-requirements"></a>Paramètres et configuration requis

Cette rubrique inclut des procédures de sauvegarde et de restauration des paramètres et des informations de configuration nécessaires pour la récupération du service Lync Server. Les informations de configuration se trouvent dans le magasin central de gestion ou sur une autre base de données principale ou sur un serveur Standard Edition Server.

Le tableau suivant identifie les paramètres et les informations de configuration que vous devez sauvegarder et restaurer.

### <a name="settings-and-configuration-data"></a>Paramètres et données de configuration

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DataType</th>
<th>Emplacement de stockage</th>
<th>Description/quand sauvegarder</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informations de configuration de la topologie</p></td>
<td><p>Magasin central de gestion (base de données : XDS. mdf)</p></td>
<td><p>Paramètres de topologie, de stratégie et de configuration.</p>
<p>Sauvegardez vos sauvegardes régulières et une fois que vous avez utilisé le panneau de configuration ou les cmdlets Lync Server pour modifier votre configuration ou vos stratégies.</p></td>
</tr>
<tr class="even">
<td><p>Informations d’emplacement</p></td>
<td><p>Magasin central de gestion (base de données : lis. mdf)</p></td>
<td><p>Informations de configuration d’Enterprise Voice Enhanced 9-1-1 (E9-1-1). Ces informations sont généralement statiques.</p>
<p>Sauvegardez vos sauvegardes régulières.</p></td>
</tr>
<tr class="odd">
<td><p>Informations de configuration du groupe Response Group</p></td>
<td><p>Serveur principal ou serveur Standard Edition (base de données : RgsConfig. mdf)</p></td>
<td><p>Groupes d’agents Response Group, files d’attente et flux de travail.</p>
<p>Sauvegardez vos sauvegardes régulières et après avoir ajouté ou modifié des groupes d’agents, des files d’attente ou des flux de travail.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Données requises

Voici une liste des données Lync Server que vous devez sauvegarder afin de pouvoir restaurer le service Lync Server en cas de défaillance.

Notez que certains types de données ne sont pas requis pour la récupération. Cette rubrique ne contient pas les procédures de sauvegarde de ces types de données, notamment les suivantes :

  - Les données utilisateur temporaires, telles que les points de terminaison et les abonnements, les serveurs de conférence actifs et les États de conférence transitoires (base de données : RtcDyn. mdf)

  - Données de carnet d’adresses (bases de données : RTCAb. mdf et Rtcab1. mdf). La base de données de carnet d’adresses est automatiquement régénérée à partir des services de domaine Active Directory.

  - Informations dynamiques pour l’application de parcage d’appel (base de données : CpsDyn. mdf)

  - Données de groupe de réponse transitoires, telles que l’état de connexion de l’agent et les informations d’attente d’appel (base de données : RgsDyn. mdf)

  - La base de données de conformité pour la conversation permanente (base de données : MgcComp. mdf). Si la conformité de conversation permanente est activée, les informations contenues dans la base de données de conformité de conversation permanente sont transitoires tant que vous disposez d’un adaptateur configuré pour lire les informations de la base de données et les convertir dans un autre format. La base de données de conformité pour la conversation permanente est donc considérée comme transitoire.
    
    Lync Server 2013 le serveur de conversation permanente est fourni avec une carte XML. Vous pouvez également installer des adaptateurs personnalisés qui prennent ces données et les déplacer vers d’autres sources, telles que les archives hébergées sur Exchange.

Le tableau suivant identifie les données que vous devez sauvegarder et restaurer.

### <a name="data-stored-in-databases"></a>Données stockées dans des bases de données

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DataType</th>
<th>Emplacement de stockage</th>
<th>Description/quand sauvegarder</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Données utilisateur persistantes</p></td>
<td><p>Serveur principal ou serveur Standard Edition (base de données : RTCXDS. mdf)</p></td>
<td><p>Les droits d’utilisateur, les listes de contacts des utilisateurs, les données du serveur ou du pool, les conférences planifiées, etc. Ces données utilisateur n’incluent pas le contenu téléchargé vers une conférence.</p>
<p>Sauvegardez vos sauvegardes régulières. Ces informations sont dynamiques, mais la perte de mises à jour n’est pas catastrophique pour Lync Server si vous devez effectuer une restauration à votre dernière sauvegarde régulière. Si les listes de contacts sont essentielles à votre organisation, vous pouvez sauvegarder ces données plus fréquemment.</p></td>
</tr>
<tr class="even">
<td><p>Données d’archivage</p></td>
<td><p>Base de données d’archivage (base de données : LcsLog. mdf)</p>
<p>Ces données peuvent être stockées sur Exchange 2013, si vous avez activé l’option d’intégration de Microsoft Exchange. Dans le cas contraire, ces données sont conservées dans une base de données d’archivage Lync Server, qui peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</p></td>
<td><p>Messagerie instantanée et contenu de la réunion.</p>
<p>Ces données ne sont pas essentielles à Lync Server, mais elles peuvent être critiques pour votre organisation à des fins de réglementation. Déterminez votre planification de sauvegarde en conséquence.</p></td>
</tr>
<tr class="odd">
<td><p>Données de surveillance</p></td>
<td><p>Bases de données de surveillance (LcsCDR. mdf et QoeMetrics. mdf)</p>
<p>Ces bases de données peuvent être colocalisées avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</p></td>
<td><p>Enregistrements des détails des appels (LcsCDR. mdf) et mesures de qualité de l’expérience (QoE) (QoeMetrics. mdf).</p>
<p>Les enregistrements des détails des appels sont dynamiques et peuvent être essentiels à votre entreprise. Déterminez votre planning de sauvegarde en prenant en compte si vous avez besoin de ces enregistrements pour des raisons de réglementation.</p>
<p>Les informations sur la qualité de l’expérience sont dynamiques. La perte de données QoE n’est pas essentielle pour le fonctionnement de Lync Server, mais elle peut être cruciale pour votre entreprise. Déterminez votre planning de sauvegarde en fonction de l’importance de ces informations pour votre organisation.</p></td>
</tr>
<tr class="even">
<td><p>Données de conversation permanente</p></td>
<td><p>Base de données de conversation permanente (gérées. mdf).</p>
<p>Cette base de données peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</p></td>
<td><p>Les données de conversation permanente sont le contenu de conversation réel publié dans les salles de conversation. Ces données sont souvent essentielles à l’entreprise.</p>
<p>Vous pouvez choisir d’utiliser la sauvegarde SQL Server ou exporter la base de données à l’aide de la cmdlet <strong>Export-applet cspersistentchatdata</strong> fournie dans Lync Server. Pour la récupération des données, vous pouvez importer et restaurer la base de données au point de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer la base de données au point de défaillance.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Exigences relatives aux données du magasin de fichiers

Dans un déploiement Enterprise Edition, le magasin de fichiers Lync Server se trouve généralement sur un serveur de fichiers. Dans un déploiement Standard Edition, le magasin de fichiers Lync Server se trouve par défaut sur le serveur Standard Edition. En règle générale, il existe un magasin de fichiers Lync Server partagé pour un site. Le magasin de fichiers de conversation permanente utilise le même partage de fichiers que le magasin de fichiers Lync Server.

Les emplacements de magasin de fichiers \\ \\sont\\identifiés comme nom de partage du serveur. Pour rechercher les emplacements spécifiques de vos magasins de fichiers, ouvrez le générateur de topologies et regardez dans le nœud **magasins de fichiers** .

Le tableau suivant identifie les magasins de fichiers que vous devez sauvegarder et restaurer.

### <a name="file-stores"></a>Magasins de fichiers

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DataType</th>
<th>Emplacement de stockage</th>
<th>Description/quand sauvegarder</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Magasin de fichiers Lync Server</p></td>
<td><p>Généralement sur un serveur de fichiers, un cluster de fichiers ou un serveur Standard Edition</p></td>
<td><p>Contenu de réunion, métadonnées de contenu de réunion, journaux de conformité de réunion, fichiers de données d’application, fichiers de mise à jour pour les mises à jour de périphériques, fichiers audio pour les groupes Response Group, parcage d’appel et applications d’annonce, et fichiers publiés dans les salles de conversation permanente.</p>
<p>Sauvegardez vos sauvegardes régulières.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Autres exigences de sauvegarde

Pour vous aider à restaurer les services Lync Server en cas de panne, vous devez sauvegarder les composants nécessaires qui ne font pas partie de Lync Server lui-même. Les composants suivants ne sont pas sauvegardés ni restaurés dans le cadre du processus de sauvegarde et de restauration de Lync Server décrit dans ce document :

  - **Services de domaine Active Directory**   vous devez sauvegarder AD DS à l’aide des outils Active Directory en même temps que Lync Server. Il est important de maintenir AD DS synchronisé avec Lync Server, afin d’éviter les problèmes qui peuvent se produire lorsque Lync Server attend des objets contact qui ne correspondent pas à ceux dans AD DS. AD DS stocke les paramètres suivants utilisés par Lync Server :
    
      - URI SIP de l’utilisateur et autres paramètres utilisateur.
    
      - Objets contact pour les applications telles que Response Group et le service de conférence.
    
      - Pointeur vers le magasin central de gestion.
    
      - Le compte d’authentification Kerberos (un objet ordinateur facultatif) et les groupes de sécurité Lync Server.
    
    Pour plus d’informations sur la sauvegarde et la restauration des services AD DS dans Windows Server 2008, voir « Guide pas à pas de la sauvegarde et de [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)la récupération AD DS » à l’adresse.

  - **Autorité de certification et certificats**   utilisez la stratégie de votre organisation pour sauvegarder votre autorité de certification et vos certificats. Si vous utilisez des clés privées exportables, vous pouvez sauvegarder le certificat et la clé privée, puis les exporter si vous utilisez les procédures décrites dans ce document pour restaurer Lync Server. Si vous utilisez une autorité de certification interne, vous pouvez réinscrire si vous avez besoin de restaurer Lync Server. Il est important de conserver la clé privée dans un endroit sûr où elle sera disponible en cas de défaillance d’un ordinateur.

  - **System Center Operations Manager**   si vous utilisez Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager) pour surveiller votre déploiement Lync Server, vous pouvez sauvegarder les données qu’il crée pendant qu’il analyse Lync Server. Utilisez votre processus de sauvegarde SQL Server standard pour sauvegarder les fichiers System Center Operations Manager. Ces fichiers ne sont pas restaurés lors de la récupération.

  - **Configuration de la passerelle PSTN (réseau téléphonique commuté)**   si vous utilisez des appliances voix entreprise ou Survivable Branch Appliances, vous devez sauvegarder la configuration de la passerelle PSTN. Pour plus d’informations sur la sauvegarde et la restauration des configurations de passerelle PSTN, consultez votre fournisseur.

  - **Versions coexistantes de Lync Server ou Office Communications Server**   si votre déploiement Lync Server 2013 coexiste avec Lync Server 2010 ou une version antérieure d’Office Communications Server, vous ne pouvez pas utiliser les procédures décrites dans ce document pour sauvegarder ou restaurer la version antérieure. Au lieu de cela, vous devez utiliser les procédures de sauvegarde et de restauration documentées spécifiquement pour votre version précédente. Pour plus d’informations sur la sauvegarde et la restauration de Lync Server [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) 2010, reportez-vous à la rubrique. Pour plus d’informations sur la sauvegarde et la restauration de Microsoft Office Communications Server 2007 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)R2, reportez-vous à la rubrique.

  - **Informations**   relatives à l’infrastructure dont vous avez besoin pour sauvegarder des informations sur votre infrastructure, telles que la configuration de votre pare-feu, la configuration de l’équilibrage de charge, la configuration des services Internet (IIS), les enregistrements DNS (Domain Name System) et les adresses IP, ainsi que la configuration du protocole DHCP (Dynamic Host Configuration Protocol). Pour plus d’informations sur la sauvegarde de ces composants, consultez leur fournisseur respectif.

  - **Microsoft Exchange et la messagerie unifiée Exchange**   sauvegarde et restauration de Microsoft Exchange et de la messagerie unifiée Exchange, comme décrit dans la documentation de Microsoft Exchange. Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)2013, voir. Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)2010, voir.
    
    Notez que Lync Server 2013 offre la possibilité de faire en sorte que les listes de contacts de l’utilisateur, les photos des utilisateurs à haute définition et les données d’archivage soient stockées dans Exchange 2013. Consultez la liste suivante pour savoir comment sauvegarder ces types de données :
    
      - Les **photos haute définition** sont sauvegardées dans le cadre de la sauvegarde Exchange Server.
    
      - Le **magasin de contacts unifié** est présenté dans Lync Server 2013. Magasin de contacts unifié permet aux utilisateurs de conserver toutes leurs informations de contact dans Exchange 2013.
        
        Vous devez vous assurer que les sauvegardes sont à jour pour les utilisateurs en ce qui concerne le stockage de leurs contacts dans le magasin de contacts unifié ou sur le serveur principal Lync. Les scénarios suivants montrent où la migration des contacts de l’utilisateur vers le magasin de contacts unifié peut entraîner des problèmes pour le processus de sauvegarde et de restauration.
        
        **Scénario 1 :** Les contacts de l’utilisateur sont migrés vers le magasin de contacts unifié et une restauration est effectuée à partir d’une sauvegarde Lync Server effectuée avant la migration des contacts de l’utilisateur. Dans ce scénario, l’utilisateur aura un état de contacts obsolètes jusqu’à un jour jusqu’à ce que la tâche de migration Lync Server commence à migrer les contacts de l’utilisateur vers Exchange. (Notez que, étant donné que les contacts utilisateur ont déjà été migrés vers le magasin de contacts unifié, les informations de contact Exchange seront utilisées). Aucune intervention de l’administrateur n’est nécessaire dans ce scénario.
        
        **Scénario 2 :** Les contacts utilisateur étaient précédemment stockés dans le magasin de contacts unifié, puis annulés. Une restauration est effectuée à partir d’une sauvegarde Lync Server effectuée lorsque les contacts de l’utilisateur ont été stockés dans le magasin de contacts unifié. Dans ce scénario, un message d’erreur `Error: Incorrect Exchange Version` de dans les journaux du client ou du serveur Lyss peut indiquer qu’il s’agit d’un problème. L’utilisateur pourra accéder à sa liste de contacts dans Lync 2013 directement à partir d’Exchange, mais l’état du client ne correspondra pas à l’état du serveur Lync. Pour résoudre ce problème, un administrateur doit exécuter les applets de commande **Invoke-CsUCSRollback** pour les utilisateurs concernés.
    
      - Les **données d’archivage** peuvent être stockées dans Exchange 2013. Ces données ne sont pas essentielles à Lync Server, mais elles peuvent être critiques pour votre organisation à des fins de réglementation. Si les données d’archivage sont stockées dans Exchange et qu’elles sont essentielles pour votre organisation, suivez les procédures de sauvegarde et de restauration d’Exchange. Notez que les données d’archivage stockées dans Exchange ne peuvent pas être déplacées vers Lync Server. De plus, il n’existe aucun moyen de déplacer des données déjà stockées dans la base de données d’archivage Lync vers Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

