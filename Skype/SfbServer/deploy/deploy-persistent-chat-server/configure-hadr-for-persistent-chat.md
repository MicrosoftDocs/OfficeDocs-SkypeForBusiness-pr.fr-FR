---
title: Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Résumé : cette rubrique vous explique comment configurer la haute disponibilité et la récupération après sinistre pour le serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 81fcc37ecbdf513decd89481c8a651404d91294a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795525"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Pour plus d’informations sur la configuration d’une haute disponibilité et d’une reprise après sinistre pour le serveur Chat permanent, voir Skype entreprise Server 2015.
  
Skype entreprise Server prend en charge plusieurs modes de haute disponibilité pour votre serveur principal, y compris la mise en miroir de la base de données. Pour plus d'informations, reportez-vous à la rubrique [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Les groupes de disponibilité AlwaysOn ne sont pas pris en charge par les serveurs de chat permanents. 

> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.
  
Avant de configurer votre déploiement de chat permanent pour une haute disponibilité et une reprise après sinistre, assurez-vous que vous connaissez les concepts de la [planification de la haute disponibilité et de la reprise après sinistre pour le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). La solution de reprise après sinistre pour serveur de chat permanent décrite dans ces rubriques est basée sur un pool de serveurs de chat permanent étiré. Le contenu de la planification décrit les exigences en ressources et la topologie de pool étiré qui permet une disponibilité élevée et une reprise après sinistre pour le serveur de chat permanent, y compris l’utilisation de la mise en miroir SQL Server pour la haute disponibilité et l’envoi du journal SQL Server pour reprise après sinistre.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Utilisation du générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence

Dans le générateur de topologie, effectuez les étapes suivantes pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente.
  
1. Ajoutez les bases de données miroir et les magasins de données secondaires SQL Server.
    
2. Modifiez les propriétés du service de chat permanent serveur pour :
    
    a. activer la mise en miroir pour la base de données primaire ;
    
    b. Ajoutez le magasin SQL Server en miroir principal.
    
    c. Activez la base de données d’envoi de journaux de SQL Server.
    
    d. Ajoutez la banque SQL Server secondaire pour l’envoi du journal SQL Server.
    
    e. Ajoutez le miroir SQL Server Store pour la base de données secondaire.
    
    touche. Publiez la topologie.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configuration de la copie des journaux de transaction SQL Server pour la base de données principale du serveur de conversation permanente

À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données d’envoi de journaux secondaires du serveur Chat permanent et assurez-vous que l’agent SQL Server est en cours d’exécution. Ensuite, connectez-vous à l’instance de base de données principale de chat permanent et effectuez les étapes suivantes :
  
1. Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.
    
2. Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.
    
3. Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.
    
4. Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.
    
5. Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.
    
6. Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local vers le dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier (exemple : c:\sauvegarde)**. (Dans le cas contraire, laissez cette zone vide.)
    
    > [!IMPORTANT]
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin local vers ce dossier. 
  
7. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.
    
8. Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser le planning de votre installation, cliquez sur **Planning**, puis ajustez la planification de l’agent SQL Server selon vos besoins.
    
9. Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.
    
10. Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.
    
11. Cliquez sur **se connecter** , puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.
    
12. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.
    
13. Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Oui, générer une sauvegarde complète de la base de données primaire et la restaurer dans la base de données secondaire (créer la base de données secondaire si elle n’existe pas)**.
    
14. Sous l’onglet **Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés**, tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.
    
15. Examinez la planification des copies dans la zone **Planification** sous **Copier le travail**. Pour personnaliser le planning de votre installation, cliquez sur **Planning**, puis ajustez la planification de l’agent SQL Server selon vos besoins. Cette planification doit être approximativement la même que celle des sauvegardes.
    
16. Sous l’onglet **Restaurer**, sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Mode sans récupération**.
    
17. Sous **Retarder la restauration des sauvegardes d’au moins :**, sélectionnez **0 minutes**.
    
18. Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de**.
    
19. Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail**. Pour personnaliser le planning de votre installation, cliquez sur **Planning**, ajustez la planification de l’agent SQL Server selon les besoins, puis cliquez sur **OK**. Cette planification doit être approximativement la même que celle des sauvegardes.
    
20. Dans la boîte de dialogue **Propriétés de la base de données**, cliquez sur **OK** pour lancer le processus de configuration.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire

Pour continuer, procédez comme suit pour l’envoi de journaux dans le cas où la base de données de chat persistante principale a basculé vers sa base de données miroir.
  
1. Basculez manuellement vers le miroir sur la base de données de conversation persistante principale. Pour ce faire, utilisez Skype entreprise Server Management Shell et l’applet **de passe Invoke-CsDatabaseFailover** .
    
2. À l’aide de SQL Server Management Studio, connectez-vous à l’instance de miroir du serveur de chat permanent principal.
    
3. Assurez-vous que l’agent SQL Server est en cours d’exécution.
    
4. Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.
    
5. Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.
    
6. Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.
    
7. Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.
    
8. Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès réseau du partage que vous avez créé pour le dossier de sauvegarde du journal des transactions.
    
9. Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier**. (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)
    
    > [!IMPORTANT]
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin local vers ce dossier. 
  
10. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.
    
11. Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser le planning de votre installation, cliquez sur **Planning**, puis ajustez la planification de l’agent SQL Server, selon les besoins.
    
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
    
20. Sélectionnez et exécutez la première moitié de la requête (Voir l’étape 18) jusqu’à la ligne :- \* \* \* \* \* \* -end : script à exécuter sur le principal \* \* \* \* \* \*:.
    
    > [!IMPORTANT]
    > L’exécution manuelle de ce script est nécessaire car SQL Server Management Studio ne prend pas en charge plusieurs bases de données principales dans une configuration d’envoi du journal SQL Server. 
  
21. Sélectionnez **Annuler** pour fermer le panneau de configuration de copie des journaux de transaction et établir une configuration de travail qui implémente correctement la copie des journaux de transaction pour la base de données primaire et la base de données en miroir (en cas de basculement). 
    
22. Restaurez manuellement la base de données de conversation persistante principale sur le serveur principal. Pour ce faire, utilisez Skype entreprise Server Management Shell et l’applet de passe **Invoke-CsDatabaseFailover** .
    

