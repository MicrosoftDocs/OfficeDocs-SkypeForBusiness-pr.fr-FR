---
title: 'Lync Server 2013 : Publication de la topologie'
TOCTitle: Publication de la topologie
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425880(v=OCS.15)
ms:contentKeyID: 49296946
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publication de la topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-01_

Pour pouvoir publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez avoir ouvert une session en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. Il est également possible de déléguer les autorisations d’administrateur appropriées. Pour plus d’informations, reportez-vous à [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Pour procéder à d’autres modifications de la configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est nécessaire.

Après avoir défini votre topologie dans le Générateur de topologie, vous devez la publier sur le magasin central de gestion. Le magasin central de gestion permet un stockage renforcé et schématisé des données dont vous avez besoin pour définir, configurer, mettre à jour, administrer, décrire et exploiter un déploiement Lync Server 2013. Il permet aussi de valider ces données dans le but d’harmoniser les configurations. Toutes les modifications apportées aux données de configuration ont lieu dans le magasin central de gestion pour aider à éviter les problèmes de synchronisation. Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, dont les serveurs Edge.

> [!NOTE]  
> SQL Server nécessite 20 Go d’espace disponible au minimum pour publier correctement la topologie initiale et créer le serveur de gestion centralisée.

> [!NOTE]  
> Pour Enterprise Edition uniquement : pour pouvoir publier la topologie, le serveur principal SQL Server doit être en ligne et accessible, et les exceptions de pare-feu nécessaires doivent être configurées. Pour plus d’informations sur la définition des exceptions de pare-feu, reportez-vous à <a href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Description des exigences de pare-feu pour SQL Server avec Lync Server 2013</a>. Pour plus d’informations sur la configuration de SQL Server, reportez-vous à <a href="lync-server-2013-configure-sql-server-for-lync-server.md">Configuration de SQL Server pour Lync Server 2013</a>.

## Pour publier une topologie

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Sélectionnez le fichier de topologie sur l’ordinateur local. Si vous utilisez l’ordinateur sur lequel vous avez défini la topologie, il s’agit de l’emplacement où vous l’avez enregistré au cours d’une procédure précédente. Il s’agit en général du dossier Documents de l’utilisateur qui a configuré la topologie.

3.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013**, puis cliquez sur **Publier la topologie** .

4.  Dans la page **Publier la topologie** , cliquez sur **Suivant** .

5.  Dans la page **Créer des bases de données** , sélectionnez les bases de données à publier.
    
    > [!NOTE]  
    > Si vous ne disposez pas des droits appropriés pour créer certaines bases de données, vous pouvez désactiver les cases à cocher en regard de celles-ci et demander à une personne dotée des droits appropriées de les créer plus tard. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Autorisations de déploiement de SQL Server dans Lync Server 2013</a>.

6.  Vous pouvez cliquer sur **Avancé** . Choisissez une option de sélection de l’emplacement des fichiers de données Advanced SQL Server parmi les suivantes :
    
      - **Déterminer automatiquement l’emplacement du fichier de base de données**  : cette option détermine les meilleures performances opérationnelles en fonction de la configuration des disques de votre serveur SQL Server et répartit les fichiers journaux et de données au meilleur emplacement.
    
      - **Utiliser les valeurs par défaut de l’instance SQL Server**  : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK** , puis sur **Suivant** .

7.  Dans la page **Sélectionner un serveur de gestion centralisée** , sélectionnez un pool de serveurs frontaux.

8.  Vous pouvez cliquer sur **Avancé** . Choisissez une option de sélection de l’emplacement des fichiers de données Advanced SQL Server parmi les suivantes :
    
      - **Déterminer automatiquement l’emplacement du fichier de base de données**  : cette option détermine les meilleures performances opérationnelles en fonction de la configuration des disques de votre serveur SQL Server et répartit les fichiers journaux et de données au meilleur emplacement.
    
      - **Utiliser les valeurs par défaut de l’instance SQL Server**  : cette option place les fichiers journaux et de données sur le serveur SQL Server en fonction des paramètres de l’instance. Elle ne fait pas appel à la fonctionnalité d’analyse opérationnelle de SQL Server qui permet de déterminer le meilleur emplacement des fichiers journaux et de données. L’administrateur SQL Server place généralement les fichiers journaux et de données à des emplacements conformes aux procédures de gestion des serveurs SQL Server et de l’organisation.
    
    Cliquez sur **OK** .

9.  Cliquez sur **Suivant** pour terminer le processus de publication.

10. Au terme du processus, cliquez sur **Terminer** .
    
    Une fois que la topologie est publiée, vous pouvez commencer à installer un réplica local du magasin central de gestion sur chaque serveur de votre topologie exécutant Lync Server 2013. Il est recommandé de commencer par le premier pool de serveurs frontaux.

## Voir aussi

#### Autres ressources

[Configuration des serveurs et des pools frontaux pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)

