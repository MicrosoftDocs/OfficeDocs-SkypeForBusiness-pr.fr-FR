---
title: 'Lync Server 2013 : Restauration d’un serveur de conversation permanente'
TOCTitle: Restauration d’un serveur de conversation permanente
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204970(v=OCS.15)
ms:contentKeyID: 49297462
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration d’un serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-05_

Cette procédure décrit les étapes nécessaires pour lancer une récupération suite à une défaillance du serveur de conversations permanentes et rétablir les opérations à partir du centre de données principal.

Lors d’une défaillance du serveur de conversations permanentes, le centre de données principal subit une panne complète, rendant les bases de données primaire et miroir indisponibles. Le centre de données principal bascule vers le serveur de sauvegarde.

La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits. La procédure part du principe que le centre de données principal a été récupéré suite à une panne totale et que les bases de données mgc et mgccomp ont été reconstruites et réinstallées à l’aide du Générateur de topologie.

La procédure s’appuie aussi sur le fait qu’aucun nouveau serveur (miroir et de sauvegarde) n’a été déployé au cours de la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, conformément à la définition donnée dans [Basculement vers un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).

Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.

## Pour restaurer le serveur de conversations permanentes

1.  Effacer tous les serveurs de la liste des serveurs actifs du serveur de conversations permanentesà l’aide de l’applet de commande `Set-CsPersistentChatActiveServer` de Lync Server Management Shell. Les serveurs de conversations permanentes cessent ainsi de se connecter aux bases de données mgc et mgccomp au cours de la restauration.
    
    > [!IMPORTANT]  
    > L’agent SQL Server sur le serveur principal serveur de conversations permanentes secondaire doit être en cours d’exécution sous un compte privilégié. Plus précisément, le compte doit disposer des droits suivants :    <ul>    
> <li><p>Accès en lecture au partage réseau dans lequel les sauvegardes sont placées</p></li>    
> <li><p>Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées</p></li>    </ul>


2.  Désactivez la mise en miroir sur la base de données mgc de sauvegarde :
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.
    
    2.  Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches** , puis cliquez sur **Miroir** .
    
    3.  Cliquez sur **Supprimer la mise en miroir** .
    
    4.  Cliquez sur **OK** .
    
    5.  Procédez de la même façon avec la base de données mgccomp.

3.  Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.
    
    2.  Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches** , puis cliquez sur **Sauvegarder** . La boîte de dialogue **Sauvegarder la base de données** s’affiche.
    
    3.  Dans **Type de sauvegarde** , sélectionnez **Complète** .
    
    4.  Pour **Composant de sauvegarde** , cliquez sur **Base de données** .
    
    5.  Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.
    
    6.  *\<Facultatif\>* Dans **Description** , entrez une description du jeu de sauvegarde.
    
    7.  Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.
    
    8.  Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.
    
    9.  Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.

4.  Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.
    
    1.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc primaire.
    
    2.  Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches** , sur **Restaurer** , puis cliquez sur **Base de données** . La boîte de dialogue **Restaurer la base de données** s’affiche.
    
    3.  Sélectionnez **À partir du périphérique** .
    
    4.  Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde** . Dans **Support de sauvegarde** , sélectionnez **Fichier** . Cliquez sur **Ajouter** , sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK** .
    
    5.  Dans **Sélectionnez les jeux de sauvegarde à restaurer** , sélectionnez la sauvegarde.
    
    6.  Dans le volet **Sélectionner une page** , cliquez sur **Options** .
    
    7.  Dans **Options de restauration** , sélectionnez uniquement **Remplacer la base de données existante** .
    
    8.  Dans **État de récupération** , sélectionnez **Laisser la base de données opérationnelle** .
    
    9.  Cliquez sur **OK** pour lancer le processus de restauration.

5.  Configurez l’envoi de journaux SQL Server pour la base de données primaire. Suivez les procédures décrites dans [Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) pour établir l’envoi de journaux pour la base de données mgc primaire.

6.  Définissez les serveurs actifs du serveur de conversations permanentes. Dans Lync Server Management Shell, utilisez l’applet de commande **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    > [!IMPORTANT]  
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données.

La restauration du pool à son état normal exécute la commande Windows PowerShell suivante :

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsPersistentChatState](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPersistentChatState).

