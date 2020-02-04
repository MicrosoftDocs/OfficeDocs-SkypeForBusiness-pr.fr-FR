---
title: 'Lync Server 2013 : configuration requise pour la sauvegarde et la restauration : données'
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
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : données

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-26_

Lync Server utilise les paramètres et les informations de configuration stockées dans les bases de données et les données qui sont stockées dans les bases de données et les magasins de fichiers. Cette rubrique décrit les données que vous devez sauvegarder pour pouvoir restaurer le service en cas d’échec ou d’interruption de votre organisation, ainsi que les données et composants utilisés par Lync Server et dont vous avez besoin pour vous sauvegarder séparément.

<div>

## <a name="settings-and-configuration-requirements"></a>Paramètres et configuration requise

Cette rubrique inclut les procédures de sauvegarde et de restauration des paramètres et des informations de configuration nécessaires à la récupération du service Lync Server. Les informations de configuration se trouvent dans le magasin de gestion central ou sur une autre base de données principale ou sur un serveur Standard Edition Server.

Le tableau suivant répertorie les paramètres et les informations de configuration nécessaires pour la sauvegarde et la restauration.

### <a name="settings-and-configuration-data"></a>Paramètres et données de configuration

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
<th>Description/moment de la sauvegarde</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informations de configuration de la topologie</p></td>
<td><p>Magasin de gestion centralisée (base de données : XDS. mdf)</p></td>
<td><p>Paramètres de topologie, de stratégie et de configuration.</p>
<p>Sauvegardez vos sauvegardes régulières et après avoir utilisé le panneau de configuration ou les applets de commande Lync Server pour modifier votre configuration ou vos stratégies.</p></td>
</tr>
<tr class="even">
<td><p>Informations d’emplacement</p></td>
<td><p>Magasin de gestion centralisée (base de données : lis. mdf)</p></td>
<td><p>Informations de configuration de 9-1-1 voix entreprise améliorée (E9-1-1). Ces informations sont généralement statiques.</p>
<p>Sauvegardez vos sauvegardes régulières.</p></td>
</tr>
<tr class="odd">
<td><p>Informations de configuration du groupe de réponse</p></td>
<td><p>Serveur principal ou Standard Edition Server (base de données : RgsConfig. mdf)</p></td>
<td><p>Response Group Group agent, files d’attente et flux de travail.</p>
<p>Sauvegardez vos sauvegardes régulières et après avoir ajouté ou modifié des groupes d’agents, des files d’attente ou des flux de travail.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Exigences en matière de données

Vous trouverez ci-dessous la liste des données du serveur Lync dont vous avez besoin pour vous permettre de restaurer le service Lync Server en cas d’échec.

Notez que certains types de données ne sont pas nécessaires pour la récupération. Cette rubrique ne contient pas de procédures pour la sauvegarde de ces types de données, notamment les suivantes :

  - Des données utilisateur temporaires, telles que des points de terminaison et des abonnements, des serveurs de conférence actifs et des États de conférence temporaire (base de données : RtcDyn. mdf);

  - Données du carnet d’adresses (bases de données : RTCAb. mdf et Rtcab1. mdf). La base de données du carnet d’adresses est automatiquement générée à partir des services de domaine Active Directory.

  - Informations dynamiques pour l’application de parc d’appels (base de données : CpsDyn. mdf)

  - Données de groupe de réponse passagère, telles que l’état de connexion d’un agent et les informations d’attente d’appel (base de données : RgsDyn. mdf)

  - La base de données de conformité pour les discussions permanentes (base de données : MgcComp. mdf). Si la conformité des conversations permanentes est activée, les informations contenues dans la base de données de compatibilité des conversations permanentes sont temporaires tant qu’un adaptateur est configuré pour lire des informations de la base de données et le convertir dans un autre format. Par conséquent, la base de données de conformité d’une conversation permanente est considérée comme temporaire.
    
    Lync Server 2013 permanent Chat Server est fourni avec un adaptateur XML. Vous pouvez également installer des adaptateurs personnalisés qui prennent ces données et les déplacer vers d’autres sources, telles que des archives hébergées d’Exchange.

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
<th>Type de données</th>
<th>Emplacement de stockage</th>
<th>Description/moment de la sauvegarde</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Données utilisateur persistantes</p></td>
<td><p>Serveur principal ou Standard Edition Server (base de données : RTCXDS. mdf)</p></td>
<td><p>Droits d’utilisateur, listes des contacts utilisateur, données du serveur ou du pool, conférences planifiées, etc. Les données utilisateur n’incluent pas le contenu chargé dans une conférence.</p>
<p>Sauvegardez vos sauvegardes régulières. Ces informations sont dynamiques, mais la perte des mises à jour n’est pas irrémédiablement apportée à Lync Server si vous avez besoin de procéder à la restauration de votre dernière sauvegarde normale. Si les listes de contacts sont essentielles pour votre organisation, vous pouvez sauvegarder ces données plus fréquemment.</p></td>
</tr>
<tr class="even">
<td><p>Archivage de données</p></td>
<td><p>Archivage de la base de données (base de données : LcsLog. mdf)</p>
<p>Ces données peuvent être stockées sur Exchange 2013, si vous avez activé l’option d’intégration de Microsoft Exchange. Dans le cas contraire, il s’agit d’une base de données d’archivage Lync Server, qui peut être colocalisée avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</p></td>
<td><p>Messagerie instantanée et contenu de la réunion.</p>
<p>Cette information n’est pas essentielle pour Lync Server, mais elle peut être essentielle pour les fins réglementaires de votre organisation. Déterminez votre planning de sauvegarde en conséquence.</p></td>
</tr>
<tr class="odd">
<td><p>Surveiller les données</p></td>
<td><p>Surveiller des bases de données (LcsCDR. mdf et QoeMetrics. mdf)</p>
<p>Ces bases de données risquent d’être colocalisées avec une autre base de données Lync Server ou autonome sur un serveur de base de données distinct.</p></td>
<td><p>Les enregistrements des détails des appels (LcsCDR. mdf) et la qualité de l’expertise (QoE) (QoeMetrics. mdf).</p>
<p>Les enregistrements des détails des appels sont dynamiques et peuvent être importants pour votre entreprise. Déterminez votre planning de sauvegarde en tenant compte de l’utilisation de ces enregistrements pour des raisons réglementaires.</p>
<p>Les informations sur la qualité de l’expérimentation sont dynamiques. La perte de données QoE n’est pas essentielle pour l’opération de Lync Server, mais elle peut être essentielle pour votre entreprise. Déterminez votre planning de sauvegarde en fonction de la façon dont ces informations sont importantes pour votre organisation.</p></td>
</tr>
<tr class="even">
<td><p>Données de chat permanent</p></td>
<td><p>Base de données de chat permanent (MGD. mdf).</p>
<p>Cette base de données est susceptible d’être colocalisée avec une autre base de données Lync Server ou indépendante sur un serveur de base de données distinct.</p></td>
<td><p>Les données de conversation permanente sont des messages de discussion en cours de publication dans des salles de conversation. Il s’agit souvent de données critiques pour les entreprises.</p>
<p>Vous pouvez choisir d’utiliser la sauvegarde SQL Server ou exporter la base de données à l’aide de l’applet de passe <strong>Export-CsPersistentChatData</strong> fournie dans Lync Server. Pour la récupération des données, vous pouvez importer et restaurer la base de données à l’emplacement de la dernière sauvegarde complète, ce qui signifie que vous ne pouvez pas restaurer la base de données vers le point de défaillance.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Exigences relatives aux données du magasin de fichiers

Dans un déploiement Enterprise Edition, le magasin de fichiers de Lync Server se trouve généralement sur un serveur de fichiers. Dans un déploiement Standard Edition, le magasin de fichiers de Lync Server se trouve par défaut sur le serveur Standard Edition Server. En règle générale, il existe un magasin de fichiers Lync Server partagé pour un site. Le magasin de fichiers permanents chat utilise le même partage de fichiers que le magasin de fichiers du serveur Lync.

Les emplacements du magasin de fichiers \\ \\sont\\identifiés par le nom de partage du serveur. Pour trouver les emplacements spécifiques de vos magasins de fichiers, ouvrez le générateur de topologie et recherchez dans le nœud **magasins de fichiers** .

Le tableau suivant identifie les banques de fichiers que vous devez sauvegarder et restaurer.

### <a name="file-stores"></a>Magasins de fichiers

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
<th>Description/moment de la sauvegarde</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Magasin de fichiers de Lync Server</p></td>
<td><p>Généralement sur un serveur de fichiers, un groupe de fichiers ou un serveur Standard Edition Server</p></td>
<td><p>Le contenu de la réunion, les métadonnées de contenu de la réunion, les journaux de conformité des réunions, les fichiers de données d’application, les fichiers de mise à jour des mises à jour de périphériques, les fichiers audio pour les réunions de groupe de réponse</p>
<p>Sauvegardez vos sauvegardes régulières.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Exigences de sauvegarde supplémentaires

Pour vous aider à garantir la possibilité de restaurer les services Lync Server en cas d’échec, vous devez sauvegarder les composants nécessaires qui ne font pas partie de Lync Server. Les composants suivants ne sont pas sauvegardés ou restaurés dans le cadre du processus de sauvegarde et de restauration de Lync Server décrits dans ce document :

  - **Services de domaine Active Directory**   vous devez sauvegarder les services de domaine Active Directory (AD DS) en utilisant les outils Active Directory en même temps que la sauvegarde de Lync Server. Il est important de maintenir la synchronisation AD DS sur Lync Server, afin d’éviter les problèmes qui peuvent survenir lorsque Lync Server attend des objets de contact qui ne correspondent pas à ceux d’AD DS. AD DS stocke les paramètres suivants qui sont utilisés par Lync Server :
    
      - URI SIP utilisateur et autres paramètres utilisateur.
    
      - Objets de contact pour des applications telles que Response Group et attendant.
    
      - Pointeur vers le magasin de gestion central.
    
      - Compte d’authentification Kerberos (objet ordinateur facultatif) et groupes de sécurité Lync Server.
    
    Pour plus d’informations sur l’utilisation de la fonction de sauvegarde et de restauration des services AD DS dans Windows Server 2008, voir le guide étape par étape [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)de sauvegarde et récupération AD DS à l’adresse.

  - **Autorités de certification et certificats**   utilisez la stratégie de votre organisation pour sauvegarder votre autorité de certification et vos certificats. Si vous utilisez des clés privées exportables, vous pouvez sauvegarder le certificat et la clé privée, puis les exporter si vous suivez les procédures décrites dans ce document pour restaurer Lync Server. Si vous utilisez une autorité de certification interne, vous pouvez procéder de nouveau à l’inscription si vous avez besoin de restaurer Lync Server. Il est important que vous conserviez la clé privée à un emplacement sécurisé pour qu’elle soit disponible en cas d’échec d’un ordinateur.

  - **System Center Operations Manager**   si vous utilisez Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager) pour surveiller votre déploiement de Lync Server, vous pouvez éventuellement sauvegarder les données qu’il crée lors de l’analyse de Lync Server. Utilisez votre processus de sauvegarde SQL Server standard pour sauvegarder les fichiers System Center Operations Manager. Ces fichiers ne sont pas restaurés lors de la récupération.

  - **Configuration de la passerelle de réseau téléphonique commuté (PSTN)**   si vous utilisez des appareils de succursale voix entreprise ou survivables, vous devez sauvegarder la configuration de la passerelle PSTN. Pour plus d’informations sur la sauvegarde et la restauration des configurations de passerelle RTC, consultez votre fournisseur.

  - **Versions et coexistence de Lync Server ou d’Office Communications Server**   si votre déploiement Lync Server 2013 est le même que celui de Lync Server 2010 ou une version antérieure d’Office Communications Server, vous ne pouvez pas utiliser les procédures de ce document pour sauvegarder ou restaurer la version antérieure. À la place, vous devez utiliser les procédures de sauvegarde et de restauration indiquées spécifiquement pour votre version antérieure. Pour plus d’informations sur la sauvegarde et la restauration de Lync Server [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) 2010, voir. Pour plus d’informations sur la sauvegarde et la restauration de Microsoft Office Communications Server 2007 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)R2, voir.

  - **Informations**   sur l’infrastructure vous devez sauvegarder des informations relatives à votre infrastructure, telles que la configuration de votre pare-feu, la configuration de l’équilibrage de charge, la configuration d’Internet Information Services (IIS), les enregistrements DNS (Domain Name System), les adresses IP et la configuration du protocole de configuration du protocole DHCP. Pour plus d’informations sur la sauvegarde de ces composants, contactez leurs fournisseurs respectifs.

  - **Microsoft Exchange et Exchange Unified Messaging (um)**   sauvegarde et restauration de Microsoft Exchange et Exchange um comme décrit dans la documentation Microsoft Exchange. Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)2013, voir. Pour plus d’informations sur la sauvegarde et la restauration d’Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)2010, voir.
    
    Notez que Lync Server 2013 offre la possibilité d’utiliser les listes de contacts de l’utilisateur, les photos haute définition et les données d’archivage stockées dans Exchange 2013. Pour plus d’informations sur la sauvegarde de ces types de données, consultez la liste suivante :
    
      - Les **photos haute définition** sont sauvegardées dans le cadre de la sauvegarde du serveur Exchange.
    
      - Le **magasin de contacts unifié** est présenté dans Lync Server 2013. Un magasin de contacts unifié permet aux utilisateurs de conserver toutes leurs informations de contact dans Exchange 2013.
        
        Assurez-vous que les sauvegardes sont à jour pour les utilisateurs en termes de stockage ou de gestion des contacts de l’utilisateur dans le magasin de contacts unifié ou sur le serveur principal Lync. Les scénarios suivants vous montrent où la migration de contacts utilisateur vers le magasin de contacts unifié peut provoquer des problèmes pour le processus de sauvegarde et de restauration.
        
        **Scénario 1 :** Les contacts des utilisateurs sont déplacés vers le magasin de contacts unifié, et une restauration est effectuée à partir d’une sauvegarde de serveur Lync prélevée avant la migration des contacts utilisateurs. Dans ce scénario, l’utilisateur aura un état de contacts obsolètes jusqu’à un jour jusqu’à ce que la tâche de migration de Lync Server commence à migrer les contacts de l’utilisateur vers Exchange. (Notez que, dans la mesure où les contacts de l’utilisateur ont été précédemment transférés dans le magasin de contacts unifié, les informations de contact Exchange seront utilisées). Ce scénario ne nécessite aucune intervention de l’administrateur.
        
        **Scénario 2 :** Les contacts des utilisateurs étaient auparavant stockés dans le magasin de contacts unifié, puis restaurés. Une restauration est effectuée à partir d’une sauvegarde de serveur Lync effectuée lorsque les contacts de l’utilisateur ont été stockés dans le magasin de contacts unifié. Dans ce scénario, un message d’erreur `Error: Incorrect Exchange Version` figurant dans les journaux du client ou du serveur Lyss est susceptible de signaler un problème. L’utilisateur sera en mesure d’accéder à sa liste de contacts dans Lync 2013 directement à partir d’Exchange, mais l’état du client ne correspond pas à l’état du serveur Lync. Pour résoudre ce problème, un administrateur doit exécuter les applets de cmdlet **Invoke-CsUCSRollback** pour les utilisateurs concernés.
    
      - Les **données d’archivage** peuvent être stockées dans Exchange 2013. Cette information n’est pas essentielle pour Lync Server, mais elle peut être essentielle pour les fins réglementaires de votre organisation. Si les données d’archivage sont stockées dans Exchange et sont importantes pour votre organisation, suivez les procédures de sauvegarde et de restauration d’Exchange. Notez que les données d’archivage stockées dans Exchange ne peuvent pas être replacées sur Lync Server. Par ailleurs, il est impossible de déplacer des données déjà stockées dans la base de données d’archivage Lync vers Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

