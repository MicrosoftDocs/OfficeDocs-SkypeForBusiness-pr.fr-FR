---
title: Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 5c53652cf5084b5a6c021c38f71f1cccc0322efa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225489"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015.
  
Skype pour Business Server prend en charge plusieurs modes de haute disponibilité pour vos serveurs principaux, y compris la mise en miroir de base de données. Pour plus d'informations, reportez-vous à la rubrique [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Groupes de disponibilité AlwaysOn ne sont pas pris en charge avec les serveurs de conversation permanente. 
  
Avant de configurer votre déploiement de conversation permanente pour la haute disponibilité et de récupération d’urgence, veillez à ce que vous êtes familiarisé avec les concepts présentés dans le [Plan de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). La solution de récupération d’urgence pour les serveurs de conversation permanente décrites dans ces rubriques repose sur un pool de serveurs de conversation permanente étiré. Décrit les besoins en ressources et la topologie de pool étiré qui permet une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente, notamment à l’aide de la mise en miroir SQL Server pour une haute disponibilité et SQL Server envoi de journaux pour le contenu de planification récupération d’urgence.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence

Dans le générateur de topologie, effectuez les étapes suivantes pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente.
  
1. Ajoutez les bases de données miroir et le journal d’expédition base de données secondaire que magasins SQL Server.
    
2. Modifier les propriétés du service serveur de conversation permanente pour :
    
    a. activer la mise en miroir pour la base de données primaire ;
    
    b. Ajouter le magasin SQL Server miroir principal ;
    
    c. Activer la base de données de journaux SQL Server.
    
    d. Ajoutez l’envoi de journaux SQL Server secondaire du magasin SQL Server.
    
    e. Ajouter le miroir du magasin SQL Server pour la base de données secondaire.
    
    f. Publiez la topologie.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente

À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données Persistent Chat Server secondaire envoi de journaux et assurez-vous que l’Agent SQL Server est en cours d’exécution. Connectez-vous à l’instance de base de données principale de conversation permanente, puis effectuez les opérations suivantes :
  
1. Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.
    
2. Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.
    
3. Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.
    
4. Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.
    
5. Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.
    
6. Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local vers le dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier (exemple : c:\sauvegarde)**. (Dans le cas contraire, laissez cette zone vide.)
    
    > [!IMPORTANT]
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer le dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local pour ce dossier. 
  
7. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.
    
8. Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser la planification de votre installation, cliquez sur **la planification**et ajustez la planification de l’Agent SQL Server.
    
9. Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.
    
10. Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.
    
11. Cliquez sur **se connecter** et se connecter à l’instance de SQL Server que vous avez configuré en tant que serveur secondaire.
    
12. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.
    
13. Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Oui, générer une sauvegarde complète de la base de données primaire et la restaurer dans la base de données secondaire (créer la base de données secondaire si elle n’existe pas)**.
    
14. Sous l’onglet **Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés**, tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.
    
15. Examinez la planification des copies dans la zone **Planification** sous **Copier le travail**. Pour personnaliser la planification de votre installation, cliquez sur **la planification**et ajustez la planification de l’Agent SQL Server. Cette planification doit être approximativement la même que celle des sauvegardes.
    
16. Sous l’onglet **Restaurer**, sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Mode sans récupération**.
    
17. Sous **Retarder la restauration des sauvegardes d’au moins :**, sélectionnez **0 minutes**.
    
18. Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de**.
    
19. Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail**. Pour personnaliser la planification de votre installation, cliquez sur **la planification**, ajustez la planification de l’Agent SQL Server et cliquez sur **OK**. Cette planification doit être approximativement la même que celle des sauvegardes.
    
20. Dans la boîte de dialogue **Propriétés de la base de données**, cliquez sur **OK** pour lancer le processus de configuration.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire

Effectuez les étapes suivantes pour l’envoi de journaux pour continuer si la base de données primaire conversation permanente est basculé vers sa base de données miroir.
  
1. Basculer manuellement la base de données de conversation permanente principal vers le serveur miroir. Cette opération est effectuée à l’aide de la Skype pour Business Server Management Shell et l’applet de commande **Invoke-CsDatabaseFailover** .
    
2. À l’aide de SQL Server Management Studio, connectez-vous à l’instance miroir Persistent Chat Server principal.
    
3. N’oubliez pas que l’Agent SQL Server est en cours d’exécution.
    
4. Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.
    
5. Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.
    
6. Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.
    
7. Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.
    
8. Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès réseau du partage que vous avez créé pour le dossier de sauvegarde du journal des transactions.
    
9. Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier**. (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)
    
    > [!IMPORTANT]
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer le dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local pour ce dossier. 
  
10. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.
    
11. Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser la planification de votre installation, cliquez sur **la planification**et ajustez la planification de l’Agent SQL Server, selon les besoins.
    
    > [!IMPORTANT]
    > Utilisez les mêmes paramètres que ceux de la base de données primaire. 
  
12. Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.
    
13. Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.
    
14. Cliquez sur **Connexion**, puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.
    
15. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.
    
16. Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Non, la base de données secondaire est initialisée**.
    
17. Sous l’onglet **Copier les fichiers**, dans **Dossier de destination des fichiers copiés**, tapez le chemin d’accès du dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées, puis cliquez sur **OK**. Ce dossier est souvent situé sur le serveur secondaire.
    
18. Ouvrez la liste déroulante **Créer un script de configuration**, puis sélectionnez **Créer un script de configuration dans une nouvelle fenêtre de requête**.
    
19. Dans la nouvelle fenêtre de requête, dans **Propriétés de la base de données**, cliquez sur **OK** pour commencer le processus de configuration.
    
20. Sélectionnez et exécutez la première moitié de la requête (voir l’étape 18) up à la ligne :-- \* \* \* \* \* \* fin : Script à exécuter sur le serveur principal : \* \* \* \* \* \*.
    
    > [!IMPORTANT]
    > Exécution manuelle de ce script est nécessaire car SQL Server Management Studio ne prend pas en charge plusieurs bases de données primaires dans une configuration de l’envoi de journaux SQL Server. 
  
21. Sélectionnez **Annuler** pour fermer le panneau de configuration de copie des journaux de transaction et établir une configuration de travail qui implémente correctement la copie des journaux de transaction pour la base de données primaire et la base de données en miroir (en cas de basculement). 
    
22. Restaurez manuellement la base de données de conversation permanente principal vers le serveur principal. Cette opération est effectuée à l’aide de la Skype pour Business Server Management Shell et l’applet de commande **Invoke-CsDatabaseFailover** .
    

