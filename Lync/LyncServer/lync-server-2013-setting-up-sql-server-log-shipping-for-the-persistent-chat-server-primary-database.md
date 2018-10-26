---
title: "LS 2013 : Conf. copie journ. trans. SQL Server pr BD prin. du serv. conv. p."
TOCTitle: Configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204653(v=OCS.15)
ms:contentKeyID: 49296169
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la copie des journaux de transaction SQL Server dans Lync Server 2013 pour la base de données principale du serveur de conversation permanente

 

_**Dernière rubrique modifiée :** 2012-11-12_

À l’aide de SQL Server Management Studio, connectez-vous à l’instance de la base de données des copies des journaux de transaction secondaire du serveur de conversations permanentes et assurez-vous que l’agent SQL Server est en cours d’exécution.

À l’aide de SQL Server Management Studio connecté à l’instance de la base de données principale de conversation permanente, procédez comme suit :

1.  Assurez-vous que l’agent SQL Server est en cours d’exécution.

2.  Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés** .

3.  Sous **Sélectionner une page** , cliquez sur **Envoi des journaux de transactions** .

4.  Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions** .

5.  Sous **Sauvegardes des journaux de transactions** , cliquez sur **Paramètres de sauvegarde** .

6.  Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde** , tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.

7.  Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local vers le dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier (exemple : c:\\sauvegarde)** . (Dans le cas contraire, laissez cette zone vide.)
    
    > [!IMPORTANT]  
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier le chemin d’accès local de ce dossier.

8.  Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de** .

9.  Examinez la planification des sauvegarde dans la zone **Planification** sous **Travail de sauvegarde** . Pour personnaliser la planification de votre installation, cliquez sur **Planification** et ajustez la planification de l’agent SQL Server comme il convient.

10. Sous **Compression** , sélectionnez **Utiliser le paramètre du serveur par défaut** , puis cliquez sur **OK** .

11. Sous **Instances de serveurs et bases de données secondaires** , cliquez sur **Ajouter** .

12. Cliquez sur **Connecter** et connectez-vous à l’instance de SQL Server que vous avez configurée comme serveur secondaire.

13. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.

14. Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Oui, générer une sauvegarde complète de la base de données primaire et la restaurer dans la base de données secondaire (créer la base de données secondaire si elle n’existe pas)**.

15. Sous l’onglet **Copier les fichiers** , dans la zone **Dossier de destination des fichiers copiés** , tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.

16. Examinez la planification des copies dans la zone **Planification** sous **Copier le travail** . Pour personnaliser la planification de votre installation, cliquez sur **Planification** et ajustez la planification de l’agent SQL Server comme il convient. Cette planification doit être approximativement la même que celle des sauvegardes.

17. Sous l’onglet **Restaurer** , sous **État de la base de données lors de la restauration des sauvegardes** , choisissez l’option **Mode sans récupération** .

18. Sous **Retarder la restauration des sauvegardes d’au moins :** , sélectionnez **0 minutes** .

19. Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de** .

20. Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail** . Pour personnaliser la planification de votre installation, cliquez sur **Planification** , ajustez la planification de l’agent SQL Server comme il convient et cliquez sur **OK** . Cette planification doit être approximativement la même que celle des sauvegardes.

21. Dans la boîte de dialogue **Propriétés de la base de données** , cliquez sur **OK** pour lancer le processus de configuration.

