---
title: 'Lync Server 2013 : configurer le clustering SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21fac13a22e2b2acf400ca154551a0705544644f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535211"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurer le clustering SQL Server pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-10_

Microsoft Lync Server 2013 prend en charge la mise en cluster pour SQL Server 2012 et SQL Server 2008 R2. Pour plus d’informations sur les éléments pris en charge, consultez la rubrique [prise en charge logicielle des bases de données dans Lync Server 2013](lync-server-2013-database-software-support.md).

Vous devez installer et configurer le cluster SQL Server avant d’installer et de déployer le serveur frontal et la base de données principale Enterprise Edition. Pour obtenir les meilleures pratiques et des instructions de configuration pour le clustering de basculement dans SQL Server 2012, reportez-vous à <https://technet.microsoft.com/library/hh231721.aspx> . Pour le clustering de basculement dans SQL Server 2008, reportez-vous à <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .

Lorsque vous installez SQL Server, pensez à installer SQL Server Management Studio pour la gestion des emplacements des fichiers de la base de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lors de l’installation de SQL Server.

<div>


> [!IMPORTANT]  
> Pour installer et déployer des bases de données sur un serveur SQL Server, vous devez être membre du groupe SQL Server sysadmin pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous ne l’êtes pas, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés. Si vous ne pouvez pas devenir membre du groupe sysadmin, transmettez le script de configuration et de déploiement des bases de données à l’administrateur des bases de données SQL Server. Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires pour effectuer les procédures, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Pour configurer le clustering SQL Server

1.  Une fois que vous avez terminé l’installation et la configuration du clustering SQL Server, vous définissez le magasin SQL Server dans le générateur de topologie à l’aide du nom de cluster virtuel de l’instance SQL Server (tel que configuré dans le programme d’installation du clustering SQL Server) et du nom de l’instance de la base de données SQL Server. À partir d’un autre serveur SQL Server unique, vous allez utiliser le nom de domaine complet (FQDN) du nœud virtuel d’un serveur SQL Server en cluster.
    
    <div>
    

    > [!NOTE]  
    > Il n’est pas nécessaire que les nœuds de cluster Windows Server individuels soient configurés pour le générateur de topologie. Vous n’allez utiliser que le nom du cluster SQL Server virtuel.

    
    </div>

2.  Si vous utilisez le générateur de topologie pour déployer vos bases de données, vous devez être membre du groupe sysadmin SQL Server. Si vous êtes membre du groupe sysadmin SQL Server, mais que vous n’avez pas de privilèges dans le domaine (par exemple, un rôle d’administrateur de base de données SQL Server), vous disposez des droits pour créer les bases de données, mais pas pour lire les informations nécessaires dans Lync Server. Pour plus d’informations sur les droits utilisateur et les autorisations nécessaires au déploiement de Lync Server, reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Vérifiez que les paramètres par défaut du dossier de la base de données et des fichiers journaux sont correctement mappés sur les disques partagés dans le cluster SQL Server à l’aide de SQL Server Management Studio. Cette procédure est nécessaire si vous créez des bases de données à l’aide du Générateur de topologies.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas installé SQL Server Management Studio, vous pouvez le faire en réexécutant le programme d’installation de SQL Server, puis en sélectionnant l’outil de gestion en tant que fonctionnalité à ajouter au déploiement SQL Server existant.

    
    </div>

4.  Installez les bases de données pour le serveur basé sur SQL Server à l’aide du générateur de topologie ou des applets de commande Windows PowerShell. Pour utiliser le générateur de topologie, procédez comme suit. Pour utiliser les applets de commande Windows PowerShell, voir [installation de base de données à l’aide de Lync Server Management Shell dans Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Pour créer des bases de données à l’aide du générateur de topologies

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.
    
    <div>
    

    > [!WARNING]  
    > La procédure suivante suppose que vous ayez défini et configuré votre topologie dans le générateur de topologies. Pour plus d’informations sur la définition de votre topologie, reportez-vous à<A href="lync-server-2013-defining-and-configuring-the-topology.md">la rubrique Defining and Configuring the Topology in Lync Server 2013</A>. Pour publier et configurer la base de données à l’aide du Générateur de topologies, vous devez ouvrir une session avec un compte d’utilisateur disposant des droits et appartenances aux groupes qui conviennent. Pour plus d’informations sur les droits requis et les appartenances aux groupes, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A>.

    
    </div>

2.  Dans le générateur de topologie, lorsque vous publiez la topologie, dans la page **créer des bases de données** , cliquez sur **avancé**.

3.  La page **Sélectionner un emplacement de fichier de base de données** comporte deux options qui déterminent la façon dont les fichiers de base de données sont déployés sur le cluster SQL Server. Sélectionnez l’une des options suivantes :
    
      - **Déterminer automatiquement l’emplacement du fichier de base de données.** L’emplacement des fichiers journaux de base de données est déterminé à l’aide d’un algorithme en fonction de la configuration des disques du serveur SQL Server. Les fichiers sont répartis de sorte à privilégier les performances.
    
      - Utiliser les valeurs par défaut de l’instance SQL Server. Si vous sélectionnez cette option, les fichiers journaux et de données sont installés en fonction des paramètres de l’instance SQL Server. Une fois les fichiers de base de données déployés sur le serveur SQL Server, l’administrateur de la base de données SQL Server souhaitera peut-être les déplacer pour optimiser les performances selon les spécificités de votre configuration SQL Server.

4.  Terminez la publication de la topologie et confirmez qu’aucune erreur ne s’est produite au cours de cette opération.

</div>

</div>

<span> </span>

</div>

</div>

</div>

