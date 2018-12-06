---
title: Configurer le clustering SQL Server pour Lync Server 2013
TOCTitle: Configurer le clustering SQL Server pour Lync Server 2013
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56559396
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer le clustering SQL Server pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync Server 2013 prend en charge le clustering pour SQL Server 2012 et SQL Server 2008 R2. Pour plus d’informations sur les éléments pris en charge, voir [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md).

Vous devez définir et configurer le cluster SQL Server avant d’installer et de déployer le serveur frontal Enterprise Edition et la base de données principale. Pour consulter les pratiques recommandées et les instructions d’installation relatives au clustering de basculement dans SQL Server 2012, voir <http://technet.microsoft.com/fr-fr/library/hh231721.aspx>. Pour le clustering de basculement dans SQL Server 2008, voir <http://technet.microsoft.com/fr-fr/library/ms189134(v=sql.105).aspx>.

Lorsque vous installez SQL Server, vous devez installer SQL Server Management Studio pour gérer les emplacements des bases de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lorsque vous installez SQL Server.

> [!IMPORTANT]  
> Pour installer et déployer les bases de données sur le serveur SQL Server, vous devez être membre du groupe sysadmin SQL Server pour le serveur SQL Server sur lequel vous installez les fichiers de base de données. Si vous n’êtes pas membre de ce groupe, vous devez demander à être ajouté au groupe jusqu’au déploiement des fichiers de base de données. Si vous ne pouvez pas être défini comme membre du groupe sysadmin, vous devez fournir à votre administrateur de base de données SQL Server le script nécessaire à la configuration et au déploiement des bases de données. Pour plus d’informations sur les droits et autorisations d’utilisateur dont vous avez besoin pour accomplir les procédures, voir <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Autorisations de déploiement de SQL Server dans Lync Server 2013</a>.

## Pour configurer le clustering SQL Server

1.  Une fois que vous avez terminé l’installation et la configuration du clustering SQL Server, vous devez définir le magasin SQL Server dans le générateur de topologies à l’aide du nom de cluster virtuel de l’instance SQL Server (tel que configuré lors de l’installation du clustering SQL Server) et le nom d’instance de la base de données SQL Server. Contrairement à un serveur SQL Server unique, vous utiliserez le nom de domaine complet du nœud virtuel pour un serveur SQL Server en cluster.
    
    > [!NOTE]  
    > Les nœuds de cluster Windows Server individuels ne doivent pas être configurés pour le générateur de topologies. Vous utiliserez uniquement le nom du cluster SQL Server virtuel.

2.  Si vous utilisez le générateur de topologies pour déployer vos bases de données, vous devez être membre du groupe sysadmin SQL Server. Si vous êtes membre de ce groupe, mais que vous n’avez pas de privilège dans le domaine (par exemple, un rôle d’administrateur de base de données SQL Server), vous êtes autorisé à créer les bases de données mais pas à lire les informations nécessaires dans Lync Server. Pour plus d’informations sur les droits et autorisations d’utilisateur nécessaires au déploiement de Lync Server, voir [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Vérifiez que les valeurs par défaut des dossiers des bases de données et fichiers journaux sont correctement mappés aux disques partagés dans le cluster SQL Server à l’aide de SQL Server Management Studio. Cette procédure est obligatoire si vous créerez les bases de données à l’aide du générateur de topologies.
    
    > [!NOTE]  
    > Si vous n’avez pas installé SQL Server Management Studio, vous pouvez l’installer en réexécutant le programme d’installation de SQL Server, puis en sélectionnant l’outil de gestion comme une fonctionnalité ajoutée pour le déploiement SQL Server existant.

4.  Installez les bases de données pour le serveur SQL Server à l’aide du générateur de topologies ou des applets de commande Windows PowerShell. Pour utiliser le générateur de topologies, utilisez la procédure suivante. Pour utiliser les applets de commande Windows PowerShell, voir [Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

## Pour créer des bases de données à l’aide du générateur de topologies

1.  Démarrez le générateur de topologies : cliquez sur **Démarrer** , **Tous les programmes** , **Microsoft Lync Server 2013** , puis sur **Générateur de topologies Lync Server**.
    
    > [!WARNING]  
    > La procédure suivante suppose que vous avez défini et configuré votre topologie dans le générateur de topologies. Pour plus d’informations sur la définition de votre topologie, voir <a href="lync-server-2013-defining-and-configuring-the-topology.md">Définition et configuration de la topologie dans Lync Server 2013</a>. Pour utiliser le générateur de topologies pour publier la topologie et configurer la base de données, vous devez vous connecter en tant qu’utilisateur avec les droits d’utilisateur et appartenances aux groupes corrects. Pour plus d’informations sur les droits et appartenances aux groupes requis, voir <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Autorisations de déploiement de SQL Server dans Lync Server 2013</a>.

2.  Dans le générateur de topologies, tandis que vous publiez la topologie, sur la page **Créer des bases de données**, cliquez sur **Avancé**.

3.  La page **Sélectionner un emplacement de fichier de base de données** inclut deux options qui déterminent le mode de déploiement des fichiers de base de données vers le cluster SQL Server. Sélectionnez l’une des options suivantes :
    
      - **Déterminer automatiquement l’emplacement du fichier de base de données.** Cette sélection utilise un algorithme pour déterminer les emplacements des fichiers journaux et de données de la base de données selon la configuration de lecteur sur le serveur SQL Server. Les fichiers seront distribués de façon à optimiser les performances.
    
      - Utiliser les valeurs par défaut de l’instance SQL Server. La sélection de cette option installe les fichiers journaux et de données selon les paramètres de l’instance SQL Server. Une fois les fichiers de base de données déployés vers le serveur SQL Server, votre administrateur de base de données SQL Server peut déplacer les fichiers pour optimiser les performances conformément à vos exigences de configuration SQL Server spécifiques.

4.  Finalisez la publication de la topologie et vérifiez qu’aucune erreur n’est survenue pendant l’opération.

