---
title: 'Lync Server 2013 : Basculement vers un serveur de conversation permanente'
TOCTitle: Basculement vers un serveur de conversation permanente
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204772(v=OCS.15)
ms:contentKeyID: 49296729
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Basculement vers un serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-05_

Le basculement du serveur de conversations permanentes est conçu pour être, en règle générale, un processus manuel.

La procédure de basculement repose sur l’hypothèse que le centre de données secondaire est actif et opérationnel, mais les services du serveur de conversations permanentes sur lequel se trouve la base de données de conversation permanente principale sont totalement indisponibles, dont les services suivants :

  - La base de données principale du serveur de conversations permanentes et la base de données miroir du serveur de conversations permanentes sont inactives.

  - Le serveur frontalLync Server est inactif.

La procédure consiste en deux étapes de base :

  - Récupérer la base de données de conversation permanente principale (mgc).

  - Établir la mise en miroir pour la nouvelle base de données principale.

La base de données de conformité de conversation permanente (mgccomp) n’est pas basculée. Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données. Il est de votre responsabilité, en tant qu’administrateur de conversation permanente, de gérer correctement la sortie de l’adaptateur pour éviter la perte des données.

## Pour basculer le serveur de conversations permanentes

1.  Supprimer la copie des journaux de transaction de la base de données de copie des journaux de transaction de sauvegarde du serveur de conversations permanentes.
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données dans laquelle se trouve la base de données mgc de sauvegarde du serveur de conversations permanentes.
    
    2.  Ouvrez une fenêtre de requête pour la base de données principale.
    
    3.  Utilisez la commande suivante pour annuler la copie des journaux de transaction :
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.

3.  Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire. Pour plus d’informations, reportez-vous à « Procédure : appliquer une sauvegarde du journal des transactions (Transact-SQL) » à l’adresse http://go.microsoft.com/fwlink/?linkid=247428\&clcid=0x40C.

4.  Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :
    
    1.  Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :
        
        1.  **exec sp\_who2** pour identifier les connexions à la base de données mgc.
        
        2.  **kill \<spid\>** pour mettre fin à ces connexions.
    
    2.  Mettez en ligne la base de données :
        
        1.  **restaurer la base de données mgc avec récupération** .

5.  Dans Lync Server Management Shell, utilisez la commande **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** pour basculer la base de données de sauvegarde mgc. Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.
    
    La base de données mgc de sauvegarde est désormais la base de données principale.

6.  Dans Lync Server Management Shell, utilisez l’applet de commande **Install-CsMirrorDatabase** pour établir un miroir de haute disponibilité pour la base de données de sauvegarde qui sert désormais de base de données principale. Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir. Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration. Pour plus d’informations, reportez-vous à la section « Utilisation des applets de commande Lync Server Management Shell » dans [Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Définissez le serveur de conversations permanentes actif. Dans l’interface de commande Lync Server, utilisez l’applet de commande **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    > [!IMPORTANT]  
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.    
    À ce stade, le basculement de la base de données principale du serveur de conversations permanentes vers la base de données de sauvegarde du serveur de conversations permanentes s’effectue correctement.

