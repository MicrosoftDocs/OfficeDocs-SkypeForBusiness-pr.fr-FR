---
title: "LS 2013 : Déf. copie journ. trans. SQL Server entre BD mir. princ. et BD sec."
TOCTitle: Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire de copie des journaux de transaction
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204887(v=OCS.15)
ms:contentKeyID: 49297172
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire de copie des journaux de transaction dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Procédez comme suit pour garantir la continuité de la copie des journaux de transaction en cas de basculement de la base de données primaire de conversation permanente vers la base de données miroir.

1.  Effectuez un basculement manuel de la base de données primaire de conversation permanente vers sa base de données miroir. Pour ce faire, utilisez Lync Server Management Shell et l’applet de commande **Invoke-CsDatabaseFailover**. Pour plus d’informations, reportez-vous à « Utilisation des applets de commande Lync Server Management Shell » dans [Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance miroir du serveur de conversations permanentes principal.

3.  Assurez-vous que l’agent SQL Server est en cours d’exécution.

4.  Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés** .

5.  Sous **Sélectionner une page** , cliquez sur **Envoi des journaux de transactions** .

6.  Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions** .

7.  Sous **Sauvegardes des journaux de transactions** , cliquez sur **Paramètres de sauvegarde** .

8.  Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde** , tapez le chemin d’accès réseau du partage que vous avez créé pour le dossier de sauvegarde du journal des transactions.

9.  Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier** . (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)
    
    > [!IMPORTANT]  
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier le chemin d’accès local de ce dossier.

10. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de** .

11. Examinez l’échéancier des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde** . Pour personnaliser la planification de votre installation, cliquez sur **Planification** , puis ajustez la planification de SQL Server Agent, selon les besoins.
    
    > [!IMPORTANT]  
    > Utilisez les mêmes paramètres que ceux de la base de données primaire.

12. Sous **Compression** , sélectionnez **Utiliser le paramètre du serveur par défaut** , puis cliquez sur **OK** .

13. Sous **Instances de serveurs et bases de données secondaires** , cliquez sur **Ajouter** .

14. Cliquez sur **Connexion** , puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.

15. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.

16. Sous l’onglet **Initialiser la base de données secondaire** , sélectionnez l’option **Non, la base de données secondaire est initialisée** .

17. Sous l’onglet **Copier les fichiers** , dans **Dossier de destination des fichiers copiés** , tapez le chemin d’accès du dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées, puis cliquez sur **OK** . Ce dossier est souvent situé sur le serveur secondaire.

18. Ouvrez la liste déroulante **Créer un script de configuration** , puis sélectionnez **Créer un script de configuration dans une nouvelle fenêtre de requête** .

19. Dans la nouvelle fenêtre de requête, dans **Propriétés de la base de données** , cliquez sur **OK** pour commencer le processus de configuration.

20. Sélectionnez et exécutez la première moitié de la requête (reportez-vous à l’étape 18) jusqu’à la ligne : -- \*\*\*\*\*\* Fin : script à exécuter sur le serveur principal : \*\*\*\*\*\*.
    
    > [!IMPORTANT]  
    > L’exécution manuelle de ce script est nécessaire, car SQL Server Management Studio ne prend pas en charge plusieurs bases de données primaires dans une configuration de copie des journaux de transaction SQL Server.

21. Sélectionnez **Annuler** pour fermer le panneau de configuration de copie des journaux de transaction et établir une configuration de travail qui implémente correctement la copie des journaux de transaction pour la base de données primaire et la base de données en miroir (en cas de basculement).

22. Effectuez une restauration automatique de la base de données primaire de conversation permanente vers la base de données primaire. Pour ce faire, utilisez Lync Server Management Shell et l’applet de commande **Invoke-CsDatabaseFailover**. Pour plus d’informations, reportez-vous à « Utilisation des applets de commande Lync Server Management Shell » dans [Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

## Voir aussi

#### Concepts

[Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

