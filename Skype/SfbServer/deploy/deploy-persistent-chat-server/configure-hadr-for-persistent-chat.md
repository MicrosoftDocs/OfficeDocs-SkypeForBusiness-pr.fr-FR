---
title: Configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 265065a5b4ff52dc65dccb4b0e045e3d9e21c452
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601879"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015.
  
Skype Entreprise Server prend en charge plusieurs modes de haute disponibilité pour vos serveurs principaux, y compris la mise en miroir de bases de données. Pour plus d’informations, voir [Plan for high availability and disaster recovery in Skype Entreprise Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Les groupes de disponibilité AlwaysOn ne sont pas pris en charge avec les serveurs de conversation permanente. 

> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.
  
Avant de configurer votre déploiement de conversation permanente pour la haute disponibilité et la récupération d’urgence, assurez-vous que vous êtes familiarisé avec les concepts de plan de haute disponibilité et de récupération d’urgence pour le serveur de conversation permanente dans [Skype Entreprise Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) La solution de récupération d’urgence pour le serveur de conversation permanente décrite dans ces rubriques repose sur un pool de serveurs de conversation permanente étiré. Le contenu de planification décrit les besoins en ressources et la topologie de pool étirée qui permet la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente, y compris l’utilisation de la mise en miroir SQL Server pour la haute disponibilité et de la livraison des journaux de SQL Server pour la récupération d’urgence.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Utiliser le Générateur de topologie pour configurer la haute disponibilité et la récupération d’urgence

Dans le Générateur de topologie, effectuez les étapes suivantes pour configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente.
  
1. Ajoutez les bases de données miroir et la base de données secondaire de livraison de journaux SQL Server magasins.
    
2. Modifiez les propriétés du service serveur de conversation permanente comme dans :
    
    a. activer la mise en miroir pour la base de données primaire ;
    
    b. Ajoutez le miroir principal SQL Server magasin.
    
    c. Activez la base SQL Server de livraison des journaux de bord.
    
    d. Ajoutez la SQL Server secondaire SQL Server de livraison de journaux de bord.
    
    e. Ajoutez le SQL Server miroir du magasin pour la base de données secondaire.
    
    f. Publiez la topologie.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurer la SQL Server de journal pour la base de données principale du serveur de conversation permanente

À l’SQL Server Management Studio, connectez-vous à l’instance de base de données de livraison de journaux secondaire du serveur de conversation permanente et assurez-vous que SQL Server Agent est en cours d’exécution. Connectez-vous ensuite à l’instance de base de données principale de conversation permanente et effectuez les étapes suivantes :
  
1. Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.
    
2. Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.
    
3. Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.
    
4. Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.
    
5. Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès vers le partage que vous avez créé pour le dossier de sauvegarde des journaux de transactions.
    
6. Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local vers le dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier (exemple : c:\sauvegarde)**. (Dans le cas contraire, laissez cette zone vide.)
    
    > [!IMPORTANT]
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local à ce dossier. 
  
7. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.
    
8. Examinez l’échéancier des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser la planification de votre installation, cliquez sur **Planifier** et ajustez la planification de SQL Server’agent si nécessaire.
    
9. Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.
    
10. Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.
    
11. Cliquez **Connecter** et connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.
    
12. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.
    
13. Sous **l’onglet Initialiser** la base de données secondaire, choisissez l’option Oui, générez une sauvegarde complète de la base de données principale et restituer dans la base de données secondaire (et créez la base de données secondaire si elle **n’existe pas).**
    
14. Sous l’onglet **Copier les fichiers**, dans la zone **Dossier de destination des fichiers copiés**, tapez le chemin d’accès au dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées. Ce dossier se trouve souvent sur le serveur secondaire.
    
15. Examinez la planification des copies dans la zone **Planification** sous **Copier le travail**. Pour personnaliser la planification de votre installation, cliquez sur **Planifier** et ajustez la planification de SQL Server’agent si nécessaire. Cette planification doit être approximativement la même que celle des sauvegardes.
    
16. Sous l’onglet **Restaurer**, sous **État de la base de données lors de la restauration des sauvegardes**, choisissez l’option **Mode sans récupération**.
    
17. Sous **Retarder la restauration des sauvegardes d’au moins :**, sélectionnez **0 minutes**.
    
18. Choisissez un seuil d’alerte sous **Envoyer une alerte si aucune restauration ne se produit en l’espace de**.
    
19. Examinez la planification des restaurations dans la zone **Planification** sous **Restaurer le travail**. Pour personnaliser la planification de votre installation, cliquez sur **Planifier,** ajustez la planification de l’agent SQL Server si nécessaire, puis cliquez sur **OK.** Cette planification doit être approximativement la même que celle des sauvegardes.
    
20. Dans la boîte de dialogue **Propriétés de la base de données**, cliquez sur **OK** pour lancer le processus de configuration.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurer la SQL Server des journaux de livraison entre le miroir principal et la base de données secondaire

Effectuez les étapes suivantes pour que la livraison des journaux de bord continue si la base de données de conversation permanente principale est retentée vers sa base de données miroir.
  
1. Faire échouer manuellement la base de données de conversation permanente principale vers le miroir. Pour ce faire, utilisez l’Skype Entreprise Server Management Shell et l’cmdlet **Invoke-CsDatabaseFailover.**
    
2. À l’SQL Server Management Studio, connectez-vous à l’instance miroir du serveur de conversation permanente principale.
    
3. Assurez-vous que l’agent SQL Server est en cours d’exécution.
    
4. Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.
    
5. Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.
    
6. Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.
    
7. Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.
    
8. Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès réseau du partage que vous avez créé pour le dossier de sauvegarde du journal des transactions.
    
9. Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier**. (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)
    
    > [!IMPORTANT]
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin d’accès local à ce dossier. 
  
10. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.
    
11. Examinez l’échéancier des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser la planification de votre installation, cliquez sur **Planifier** et ajustez la planification de SQL Server’agent, le cas échéant.
    
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
    
20. Sélectionnez et exécutez la première moitié de la requête (voir l’étape 18) jusqu’à la ligne : -- Fin : script à exécuter au niveau \* \* \* \* \* \* principal : \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > L’exécution manuelle de ce script est nécessaire, car SQL Server Management Studio ne prend pas en charge plusieurs bases de données principales dans une configuration SQL Server’envoi de journaux de bord. 
  
21. Sélectionnez **Annuler** pour fermer le panneau de configuration de copie des journaux de transaction et établir une configuration de travail qui implémente correctement la copie des journaux de transaction pour la base de données primaire et la base de données en miroir (en cas de basculement).
    
22. Retourne manuellement la base de données de conversation permanente principale à la base de données principale. Pour ce faire, utilisez l’Skype Entreprise Server Management Shell et l’cmdlet **Invoke-CsDatabaseFailover.**
    

