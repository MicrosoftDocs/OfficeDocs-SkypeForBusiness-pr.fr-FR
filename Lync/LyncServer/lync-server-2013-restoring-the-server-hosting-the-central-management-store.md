---
title: 'Lync Server 2013: restauration du serveur qui héberge le magasin de gestion central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Restauration du serveur qui héberge le magasin de gestion central dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Le déploiement d’un serveur Lync dispose d’une banque d’administration centrale unique, dont une copie est répliquée sur chaque serveur exécutant un rôle serveur Lync Server. Cette rubrique décrit la procédure de restauration d’un serveur principal ou d’un serveur Standard Edition Server qui héberge la Banque centrale de gestion.

Pour trouver le pool sur lequel se trouve le serveur de gestion central, ouvrez le générateur de topologies, cliquez sur **Lync Server**et recherchez dans le volet droit sous **serveur de gestion central**.

Si le serveur principal hébergeant la Banque de gestion centrale se trouve dans une configuration en miroir et que la base de données miroir est toujours fonctionnelle, nous vous recommandons d’effectuer une sauvegarde de ce miroir en continu, puis de procéder à une restauration complète sur la base de données principale et sur la base de données miroir, à l’aide de cette sauvegarde, en suivant la procédure de restauration ci-dessous. Cela est nécessaire, car la restauration du serveur principal nécessite la modification et la publication de la topologie, et cette opération peut être réalisée uniquement si le CMS de la base de données principale est opérationnel. Notez également que les rôles de base de données principaux et en miroir ne peuvent pas être modifiés si la topologie ne peut pas être publiée.

<div>


> [!NOTE]  
> Si un serveur principal ou un serveur Standard Edition n’héberge pas le magasin d’administration centrale, voir <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">restauration d’un serveur principal Enterprise Edition dans Lync server 2013</A> ou <A href="lync-server-2013-restoring-a-standard-edition-server.md">restauration d’un serveur Standard Edition Server dans Lync Server 2013</A>. S’il s’agit d’un serveur principal qui héberge le magasin central de gestion est dans une configuration en miroir et que le miroir ne peut pas être utilisé, voir <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">restaurer un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror</A>. Si un autre serveur a échoué, voir <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">restauration d’un serveur membre Enterprise Edition dans Lync server 2013</A>.



</div>

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration. Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>Pour restaurer le magasin central de gestion

1.  Commencez par un serveur propre ou nouveau qui porte le même nom de domaine complet (FQDN) que l’ordinateur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Pour effectuer cette étape, suivez les procédures de déploiement du serveur de votre organisation.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe administrateurs locaux, connectez-vous au serveur que vous restaurez.

3.  Si vous restaurez un serveur Standard Edition Server, restaurez le magasin de fichiers à partir de $Backup à l’emplacement de stockage des fichiers sur le serveur, puis partagez le dossier.
    
    <div>
    

    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé pour que les composants qui les utilisent puissent y accéder.

    
    </div>

4.  Effectuez l’une des actions suivantes :
    
      - Si vous installez un serveur Standard Edition Server, recherchez le dossier d’installation ou le média de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de Setup. exe amd64. exe. Dans l’Assistant Déploiement, cliquez sur **préparer le premier Standard Edition Server** et suivez les instructions de l’Assistant pour installer le centre de gestion central.
    
      - Si vous installez un serveur back-end d’entreprise, installez SQL Server 2012 ou SQL Server 2008 R2, en conservent le nom de l’instance avant l’échec.
        
        <div>
        

        > [!NOTE]  
        > En fonction du serveur que vous restaurez et sur votre déploiement, le serveur peut inclure plusieurs bases de données colocalisées ou distinctes. Suivez la même procédure pour installer SQL Server que vous avez utilisé à l’origine pour déployer le serveur, y compris les autorisations et les connexions SQL Server.

        
        </div>

5.  À partir d’un serveur frontal, démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

6.  Recréez le magasin central de gestion. Dans la ligne de commande, tapez :
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Exemple :
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Définissez le point de contrôle des services de domaine Active Directory pour le centre de gestion central. Dans la ligne de commande, tapez :
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Exemple :
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Si vous perdez le point de connexion, vous pouvez réexécuter cette cmdlet.

    
    </div>

8.  Importez les données du magasin de gestion central à partir de $Backup. Dans la ligne de commande, tapez :
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Exemple :
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Activez les modifications que vous venez d’apporter. À partir de la ligne de commande, tapez :
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Après l’activation de la topologie, vous pouvez rechercher le document de topologie dans la base de données.

    
    </div>

10. Si vous restaurez un serveur principal Enterprise Edition qui héberge également le MCG, ou si vous avez besoin de recréer un miroir du MCG, procédez comme suit. Dans le cas contraire, passez à l’étape 11.
    
    Installez les bases de données autonomes en procédant comme suit:
    
    1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.
    
    4.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **installer la base de données**.
    
    5.  Suivez l’Assistant d' **installation de base de données** . S’il s’agit de la restauration d’une base de données autre que la Banque centrale de gestion de ce serveur, dans la page **créer des bases de données** , sélectionnez les bases de données que vous voulez recréer.
        
        <div>
        

        > [!NOTE]  
        > Seules les bases de données autonomes sont affichées dans la page <STRONG>créer des bases de données</STRONG> . Les bases de données colocalisées sont créées lorsque vous exécutez l’Assistant Déploiement de Lync Server.

        
        </div>
    
    6.  Si vous restaurez un serveur principal en miroir, continuez à suivre le reste de l’Assistant jusqu’à ce que vous arriviez à l’invite de création d’une base de données miroir. Sélectionnez la base de données que vous voulez installer, puis terminez la procédure.
    
    7.  Suivez les autres instructions de l’Assistant, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!TIP]  
    > Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de applet <STRONG>install-CsDatabase</STRONG> pour créer une base de données et l’applet de la cmdlet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir. Pour en savoir plus, voir <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">installer-CsDatabase</A> et <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">installer-CsMirrorDatabase</A>.

    
    </div>

11. Si vous restaurez un serveur Standard Edition Server, recherchez le dossier d’installation ou le média de Lync Server et démarrez l’Assistant Déploiement de Lync \\Server\\situé\\à l’installation de Setup. exe amd64. exe. Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes:
    
    1.  Exécutez l' **étape 1: installer le magasin de configuration local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez l' **étape 2: configurer ou supprimer les composants serveur Lync** pour installer les rôles serveur de Lync Server.
    
    3.  Exécutez l' **étape 3: demandez, installez ou attribuez des certificats** pour attribuer les certificats.
    
    4.  Exécutez l' **étape 4: démarrer des services** pour démarrer des services sur le serveur.
    
    Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement pour le rôle de serveur que vous restaurez.

12. Restaurez les données utilisateur en procédant comme suit:
    
    1.  Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.
    
    2.  Avant de restaurer les données utilisateur, vous devez arrêter les services Lync. Pour ce faire, tapez:
        
            Stop-CsWindowsService
    
    3.  Pour restaurer les données utilisateur, à partir de la ligne de commande, tapez:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Redémarrez les services Lync en entrant:
        
            Start-CsWindowsService

13. Restaurez les données d’informations de géolocalisation dans le magasin central de gestion. Dans la ligne de commande, tapez :
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Exemple :
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Si vous avez déployé Response Group sur ce pool ou Server Standard Edition Server, restaurez les données de configuration du groupe de réponse. Pour plus d’informations, consultez la rubrique [restauration des paramètres du groupe de réponses dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Si vous restaurez un serveur principal qui inclut l’archivage ou la surveillance de bases de données, restaurez les données d’archivage ou de contrôle à l’aide d’un outil de gestion SQL Server, tel que SQL Server Management Studio. Pour plus d’informations, reportez-vous à la rubrique [restauration de données d’analyse ou d’archivage dans Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

