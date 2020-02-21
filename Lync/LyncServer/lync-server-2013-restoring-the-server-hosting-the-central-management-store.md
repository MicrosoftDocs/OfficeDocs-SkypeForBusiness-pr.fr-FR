---
title: 'Lync Server 2013 : restauration du serveur qui héberge le magasin central de gestion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772646b8122e228aa43818aa5fe7fe2fb6689366
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Restauration du serveur qui héberge le magasin central de gestion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Un déploiement Lync Server possède un seul magasin central de gestion, dont une copie est répliquée sur chaque serveur exécutant un rôle serveur Lync Server. Cette rubrique décrit comment restaurer un serveur principal ou un serveur Standard Edition qui héberge le magasin central de gestion.

Pour trouver le pool où se trouve le serveur de gestion centralisée, ouvrez le générateur de topologies, cliquez sur **Lync Server**, puis regardez dans le volet droit sous **serveur de gestion centralisée**.

Si le serveur principal qui héberge le magasin central de gestion se trouve dans une installation en miroir et que la base de données miroir reste fonctionnelle, nous vous recommandons d’effectuer une sauvegarde de ce miroir en continu, puis d’effectuer une restauration complète sur la base de données principale et sur le base de données miroir, à l’aide de cette sauvegarde, en suivant la procédure de restauration ci-dessous. Cette opération est nécessaire car la restauration du serveur principal nécessite la modification et la publication de la topologie, ce qui n’est possible que si la base de données principale hébergeant le MCG est opérationnelle. Notez également que les rôles de base de données principale et miroir ne peuvent pas être interchangeables si la topologie ne peut pas être publiée.

<div>


> [!NOTE]  
> Si un serveur principal ou un serveur Standard Edition qui n’héberge pas le magasin central de gestion a échoué, consultez la rubrique <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restauration d’un serveur principal Enterprise Edition dans Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restauration d’un serveur Standard Edition dans Lync Server 2013</A>. Si un serveur principal qui héberge le magasin central de gestion se trouve dans une configuration mise en miroir et que seul le miroir a échoué, consultez la rubrique <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror</A>. Si un autre serveur a échoué, consultez la rubrique <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restauration d’un serveur membre Enterprise Edition dans Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration. Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Pour restaurer le magasin central de gestion

1.  Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs local, ouvrez une session sur le serveur que vous restaurez.

3.  Si vous restaurez un serveur Standard Edition, restaurez le magasin de fichiers en copiant le magasin de fichiers approprié à partir de $Backup vers l’emplacement du magasin de fichiers sur le serveur, puis partagez le dossier.
    
    <div>
    

    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé afin que les composants qui utilisent les fichiers puissent y accéder.

    
    </div>

4.  Effectuez l’une des opérations suivantes :
    
      - Si vous installez un serveur Standard Edition, accédez au dossier ou au support d’installation de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server qui \\se\\trouve\\à l’installation de amd64 Setup. exe. Dans l’Assistant Déploiement, cliquez sur **préparer d’abord le serveur Standard Edition** et suivez l’Assistant pour installer le magasin central de gestion.
    
      - Si vous installez un serveur principal d’entreprise, installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instance qu’avant la défaillance.
        
        <div>
        

        > [!NOTE]  
        > En fonction du serveur que vous restaurez et de votre déploiement, le serveur peut inclure plusieurs bases de données colocalisées ou distinctes. Suivez la même procédure pour installer SQL Server que celle que vous avez utilisée à l’origine pour déployer le serveur, avec les autorisations et les comptes de connexion SQL Server.

        
        </div>

5.  À partir d’un serveur frontal, démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

6.  Recréez le magasin central de gestion. Sur la ligne de commande, tapez :
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Par exemple :
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Définissez le point de contrôle des services de domaine Active Directory pour le magasin central de gestion. Sur la ligne de commande, tapez :
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Par exemple :
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Si vous perdez le point de connexion, vous pouvez réexécuter cette applet de commande.

    
    </div>

8.  Importez les données du magasin central de gestion à partir de $Backup. Sur la ligne de commande, tapez :
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Par exemple :
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Activez les modifications que vous venez de faire. Sur la ligne de commande, tapez :
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Lorsque vous avez activé la topologie, vous pouvez trouver le document de topologie dans la base de données.

    
    </div>

10. Si vous restaurez un serveur principal Enterprise Edition qui héberge également le MCG, ou si vous devez recréer un miroir du MCG, suivez cette étape. Sinon, passez à l’étape 11.
    
    Installez les bases de données autonomes en procédant comme suit :
    
    1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.
    
    4.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **installer la base de données**.
    
    5.  Suivez l’Assistant d' **installation de base de données** . Si vous restaurez une base de données autre que le magasin central de gestion sur ce serveur, dans la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez recréer.
        
        <div>
        

        > [!NOTE]  
        > Seules les bases de données autonomes s’affichent dans la page <STRONG>Créer des bases de données</STRONG>. Les bases de données colocalisées sont créées lorsque vous exécutez l’Assistant Déploiement de Lync Server.

        
        </div>
    
    6.  Si vous restaurez un serveur principal en miroir, continuez à suivre le reste de l’Assistant jusqu’à ce que vous arriviez à une invite de créer une base de données miroir. Sélectionnez la base de données que vous souhaitez installer et terminez le processus.
    
    7.  Suivez le reste de l’Assistant, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!TIP]  
    > Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de commande <STRONG>install-applet csdatabase</STRONG> pour créer chaque base de données et la cmdlet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir. Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-applet csdatabase</A> et <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.

    
    </div>

11. Si vous restaurez un serveur Standard Edition, accédez au dossier d’installation ou au support de Lync Server et démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de amd64 Setup. exe. Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes :
    
    1.  Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez l' **étape 2 : installer ou supprimer des composants Lync Server** pour installer les rôles serveur Lync Server.
    
    3.  Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.
    
    4.  Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.
    
    Pour plus d’informations sur l’exécution de l’Assistant Déploiement, reportez-vous à la documentation de déploiement du rôle serveur que vous restaurez.

12. Restaurez les données utilisateur en effectuant ce qui suit :
    
    1.  Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.
    
    2.  Avant de restaurer les données utilisateur, vous devez arrêter Lync services. Pour ce faire, tapez :
        
            Stop-CsWindowsService
    
    3.  Pour restaurer les données utilisateur, à la ligne de commande, tapez :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Redémarrez Lync services en tapant :
        
            Start-CsWindowsService

13. Restaurer les données d’informations d’emplacement dans le magasin central de gestion. Sur la ligne de commande, tapez :
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Par exemple :
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Si vous avez déployé Response Group sur ce pool ou serveur Standard Edition, restaurez les données de configuration du groupe Response Group. Pour plus d’informations, reportez-vous à la rubrique [restauration des paramètres de Response Group dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Si vous restaurez un serveur principal qui inclut des bases de données d’archivage ou de surveillance, restaurez les données d’archivage ou de surveillance à l’aide d’un outil de gestion SQL Server, tel que SQL Server Management Studio. Pour plus d’informations, reportez-vous à la rubrique [restauration des données de surveillance ou d’archivage dans Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

