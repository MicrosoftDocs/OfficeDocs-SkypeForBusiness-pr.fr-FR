---
title: Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Résumé: Découvrez comment gérer l’utilisation du serveur Chat permanent et de la reprise après sinistre dans Skype entreprise Server 2015.'
ms.openlocfilehash: 5cf0fc8ba175111a0e0760f4447bd309c34b759c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279304"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Découvrez comment gérer la haute disponibilité et la reprise après sinistre du serveur Chat permanent dans Skype entreprise Server 2015.
  
Cette rubrique décrit la procédure de basculement et de basculement du serveur de conversation permanent. Avant de lire ce sujet, veillez à lire [plan pour une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent dans Skype entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) et à [configurer une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Basculement du serveur de conversation permanent

Le basculement pour le serveur de chat permanent est conçu pour être essentiellement un processus manuel.
  
La procédure de basculement repose sur l’hypothèse que le centre de données secondaire est opérationnel et qu’il est en cours d’exécution, mais les services serveur de chat permanent dans lesquels réside la base de données de chat permanent principal sont entièrement indisponibles, y compris les suivantes:
  
- La base de données principale de chat serveur et la base de données miroir du serveur de chat permanent sont inversées.
    
- Le serveur frontal de Skype entreprise Server est arrêté.
    
La procédure consiste en deux étapes de base :
  
- Récupérez la base de données de chat persistante principale (MGC).
    
- Établir la mise en miroir pour la nouvelle base de données principale.
    
La base de données de compatibilité des conversations permanentes (mgccomp) n’a pas pu être lancée. Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données. Il est de votre responsabilité, en tant qu’administrateur de chat permanent, de gérer correctement la sortie de la carte pour éviter la perte de données.
  
Basculer vers un serveur de conversation permanente :
  
1. Supprimez l’envoi de journaux de la base de données d’envoi de journaux de sauvegarde du serveur Chat permanent.
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données dans laquelle réside la base de données de sauvegarde serveur de chat MGC.
    
   - Ouvrez une fenêtre de requête pour la base de données principale.
    
   - Utilisez la commande suivante pour annuler la copie des journaux de transaction :
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.
    
3. Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire. Pour plus d’informations, reportez-vous [à la rubrique Procédure: appliquer une sauvegarde du journal des transactions (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :
    
   - Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :
    
   - **exec sp_who2** pour identifier les connexions à la base de données mgc.
    
   - **Arrêtez \<le\> SPID** pour terminer ces connexions.
    
   - Mettez en ligne la base de données :
    
   - **restaurer la base de données mgc avec récupération**.
    
5. Dans Skype entreprise Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity "service: ATL-CS-001.litwareinc.com"-PoolState FailedOver** pour basculer vers la base de données de sauvegarde MGC. Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.
    
    La base de données mgc de sauvegarde est désormais la base de données principale.
    
6. Dans Skype entreprise Server Management Shell, vous pouvez utiliser l’applet de passe **install-CsMirrorDatabase** pour établir un miroir haute disponibilité pour la base de données de sauvegarde qui sert désormais de base de données principale. Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir. Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.
    
7. Définissez les serveurs actifs de chat permanent serveur. À partir de Skype entreprise Server Management Shell, utilisez l’applet de contrôle **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    > [!IMPORTANT]
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données. 
  
    À ce stade, le basculement de la base de données principale du serveur Chat permanent vers la base de données de sauvegarde du serveur Chat permanent s’effectue correctement.
    
## <a name="fail-back-persistent-chat-server"></a>Échec du serveur de conversation persistante

Cette procédure décrit les étapes nécessaires à la récupération d’une défaillance du serveur de chat permanent et à la restauration d’opérations à partir du centre de données principal.
  
Lors de l’échec du serveur Chat permanent, le centre de données principal est en panne, et les bases de données principales et miroirs deviennent indisponibles. Le centre de données principal bascule vers le serveur de sauvegarde.
  
La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits. Cette procédure part du principe que le centre de données principal a été restauré à partir d’une panne totale et que la base de données MGC et la base de données mgccomp ont été recréées puis réinstallées à l’aide du générateur de topologie.
  
La procédure s’appuie aussi sur le fait qu’aucun nouveau serveur (miroir et de sauvegarde) n’a été déployé au cours de la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, conformément à la définition donnée dans Basculement vers un serveur de conversation permanente.
  
Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.
  
1. Effacez tous les serveurs de la liste de serveurs actifs de chat permanent du serveur à l’aide de l’applet de contrôle **Set-CsPersistentChatActiveServer** de Skype entreprise Server Management Shell. Cela a pour fin la connexion à la base de données MGC et de la base de données mgccomp lors du retour arrière.
    
    > [!IMPORTANT]
    > L’agent SQL Server sur le serveur principal de chat permanent du serveur principal doit être en cours d’exécution sous un compte privilégié. Plus précisément, le compte doit disposer des droits suivants : 
  
   - Accès en lecture au partage réseau dans lequel les sauvegardes sont placées
    
   - Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées
    
2. Désactivez la mise en miroir sur la base de données mgc de sauvegarde :
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.
    
   - Cliquez sur **Supprimer la mise en miroir**.
    
   - Cliquez sur **OK**.
    
   - Procédez de la même façon avec la base de données mgccomp.
    
3. Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance Backup MGC.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.
    
   - Dans **Type de sauvegarde**, sélectionnez **Complète**.
    
   - Pour **Composant de sauvegarde**, cliquez sur **Base de données**.
    
   - Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.
    
   -  * \<Facultatif\> *  Dans **Description**, entrez une description du jeu de sauvegarde.
    
   - Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.
    
   - Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.
    
   - Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.
    
4. Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance MGC principale.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.
    
   - Sélectionnez **À partir du périphérique**.
    
   - Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.
    
   - Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.
    
   - Dans le volet **Sélectionner une page**, cliquez sur **Options**.
    
   - Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.
    
   - Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.
    
   - Cliquez sur **OK** pour lancer le processus de restauration.
    
5. Configurer l’envoi du journal SQL Server pour la base de données principale. Suivez les procédures de [configuration de haute disponibilité et de récupération d’urgence pour le serveur de chat permanent dans Skype entreprise server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) de manière à établir une expédition du journal pour la base de données MGC principale.
    
6. Définissez les serveurs actifs de chat permanent serveur. À partir de Skype entreprise Server Management Shell, utilisez l’applet de contrôle **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    > [!IMPORTANT]
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données. 
  
Pour restaurer le pool à son état normal, exécutez la commande Windows PowerShell suivante:
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Pour plus d’informations, voir la rubrique d’aide sur l’applet de commande [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).
  

