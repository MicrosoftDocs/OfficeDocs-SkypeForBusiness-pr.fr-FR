---
title: 'Lync Server 2013: configurer le regroupement SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurer le regroupement SQL Server pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-01-10_

Microsoft Lync Server 2013 prend en charge la mise en cluster pour SQL Server 2012 et SQL Server 2008 R2. Pour plus d’informations sur les fonctionnalités prises en charge, voir [prise en charge de logiciels de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md).

Vous devez configurer et configurer le cluster SQL Server avant d’installer et de déployer le serveur frontal et la base de données principale d’Enterprise Edition. Pour obtenir des recommandations et des instructions de configuration pour la mise en cluster de basculement dans SQL Server 2012, voir <http://technet.microsoft.com/en-us/library/hh231721.aspx>. Pour la mise en cluster de basculement dans SQL <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>Server 2008, voir.

Lorsque vous installez SQL Server, vous devez installer SQL Server Management Studio pour gérer les emplacements des bases de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lorsque vous installez SQL Server.

<div>


> [!IMPORTANT]  
> Pour installer et déployer les bases de données sur le serveur SQL Server, vous devez être membre du groupe SQL Server sysadmin pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander à l’ajouter au groupe jusqu’à ce que les fichiers de la base de données soient déployés. Si vous ne pouvez pas être membre du groupe sysadmin, vous devez fournir à votre administrateur de base de données SQL Server le script de configuration et de déploiement de celles-ci. Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires pour accomplir ces procédures, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Pour configurer le regroupement SQL Server

1.  Après avoir effectué l’installation et la configuration de la mise en cluster de SQL Server, vous définissez SQL Server Store dans le générateur de topologie à l’aide du nom de cluster virtuel de l’instance SQL Server (configuré dans le programme d’installation de SQL Server clustering) et de l’instance. nom de la base de données SQL Server. Différent d’un serveur SQL Server unique, vous devez utiliser le nom de domaine complet (FQDN) du nœud virtuel pour un serveur SQL Server groupé.
    
    <div>
    

    > [!NOTE]  
    > Il n’est pas nécessaire de configurer les nœuds de cluster Windows Server individuels pour le générateur de topologie. Vous utiliserez uniquement le nom du cluster SQL Server virtuel.

    
    </div>

2.  Si vous utilisez le générateur de topologie pour déployer vos bases de données, vous devez être membre du groupe SQL Server sysadmin. Si vous êtes membre du groupe SQL Server sysadmin, mais que vous n’avez pas de privilèges sur le domaine (par exemple, un rôle d’administrateur de base de données SQL Server), vous disposez des droits nécessaires pour créer les bases de données, mais pas pour lire les informations nécessaires dans Lync Server. Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires au déploiement de Lync Server, reportez-vous à la section [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Assurez-vous que le dossier de base de données et les fichiers journaux par défaut sont mappés correctement aux disques partagés dans le groupe SQL Server en utilisant SQL Server Management Studio. Il s’agit d’une procédure obligatoire si vous créez des bases de données à l’aide du générateur de topologie.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas installé SQL Server Management Studio, vous pouvez l’installer en réexécutant le programme d’installation de SQL Server, puis en sélectionnant l’outil de gestion en tant que composant supplémentaire pour le déploiement SQL Server existant.

    
    </div>

4.  Installez les bases de données pour le serveur SQL Server à l’aide du générateur de topologie ou des cmdlets Windows PowerShell. Pour utiliser le générateur de topologie, utilisez la procédure suivante. Pour utiliser les applets de cmdlet Windows PowerShell, consultez l' [installation de la base de données à l’aide de Lync Server Management Shell dans Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Pour créer des bases de données à l’aide du générateur de topologie

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.
    
    <div>
    

    > [!WARNING]  
    > La procédure suivante suppose que vous avez défini et configuré votre topologie dans le générateur de topologie. Pour plus d’informations sur la définition de votre topologie, voir<A href="lync-server-2013-defining-and-configuring-the-topology.md">définition et configuration de la topologie dans Lync Server 2013</A>. Pour utiliser le générateur de topologie afin de publier la topologie et de configurer la base de données, vous devez vous connecter en tant qu’utilisateur disposant des droits d’utilisateur et des appartenances aux groupes appropriés. Pour plus d’informations sur les droits et les appartenances aux groupes requis, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A>.

    
    </div>

2.  Dans le générateur de topologie, lorsque vous publiez la topologie, dans la page **créer des bases de données** , cliquez sur **avancé**.

3.  La page **Sélectionner l’emplacement du fichier de base de données** propose deux options qui déterminent le mode de déploiement des fichiers de base de données sur le cluster SQL Server. Sélectionnez l’une des options suivantes :
    
      - **Déterminez automatiquement l’emplacement du fichier de base de données.** Cette sélection utilise un algorithme pour déterminer les emplacements du journal de la base de données et des fichiers de données en fonction de la configuration du lecteur sur le serveur SQL Server. Les fichiers seront distribués de telle sorte qu’ils puissent essayer d’offrir des performances optimales.
    
      - Utilisez les valeurs par défaut des instances SQL Server. Si vous sélectionnez cette option, les fichiers journaux et de données seront installés conformément aux paramètres de l’instance SQL Server. Après le déploiement des fichiers de base de données sur le serveur SQL Server, l’administrateur de votre base de données SQL Server a besoin de replacer les fichiers pour optimiser les performances de votre configuration spécifique de SQL Server.

4.  Achevez la publication de la topologie et vérifiez qu’il n’y a pas eu d’erreur pendant l’opération.

</div>

</div>

<span> </span>

</div>

</div>

</div>

