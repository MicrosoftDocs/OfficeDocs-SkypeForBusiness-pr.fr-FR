---
title: Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Résumé : Découvrez comment gérer les serveurs de conversation permanente haute disponibilité et récupération d’urgence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 477897362a01ae3ac6097c50eaed8f9ece31f49d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371633"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestion de la haute disponibilité et de la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer des serveurs de conversation permanente haute disponibilité et récupération d’urgence dans Skype pour Business Server 2015.
  
Cette rubrique décrit comment basculer et restaurer le serveur de conversation permanente. Avant de lire cette rubrique, vous devez avoir lu [planifier la haute disponibilité et de récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) et [Configure une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Entreprise 2015 Server](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Faire basculer le serveur de conversation permanente

Le basculement de serveur de conversation permanente est conçu pour être principalement un processus manuel.
  
La procédure de basculement se base sur l’hypothèse que le centre de données secondaire est actif et en cours d’exécution, mais les services de serveur de conversation permanente où se trouve la base de données primaire conversation permanente sont totalement indisponibles, y compris les suivantes :
  
- Base de données primaire persistent Chat Server et la base de données miroir Persistent Chat Server sont inactives.
    
- Skype pour Business Server serveur frontal est inactif.
    
La procédure consiste en deux étapes de base :
  
- Récupérer la conversation permanente base de données principale (mgc).
    
- Établir la mise en miroir pour la nouvelle base de données principale.
    
La base de données de conformité conversation permanente (mgccomp) n’est pas basculé. Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données. Il vous incombe, en tant qu’administrateur de conversation permanente, pour gérer correctement la sortie de la carte pour éviter toute perte de données.
  
Basculer vers un serveur de conversation permanente :
  
1. Supprimer des journaux de transaction de la base de données Persistent Chat Server sauvegarde l’envoi de journaux.
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance de base de données où se trouve la base de données mgc de sauvegarde Persistent Chat Server.
    
   - Ouvrez une fenêtre de requête pour la base de données principale.
    
   - Utilisez la commande suivante pour annuler la copie des journaux de transaction :
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.
    
3. Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire. Pour plus d’informations, voir [procédure : appliquer une sauvegarde du journal des transactions (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :
    
   - Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :
    
   - **exec sp_who2** pour identifier les connexions à la base de données mgc.
    
   - **kill \<spid\> ** pour mettre fin à ces connexions.
    
   - Mettez en ligne la base de données :
    
   - **restaurer la base de données mgc avec récupération**.
    
5. Dans Skype pour Business Server Management Shell, utilisez la commande **Set-CsPersistentChatState-Identity « service : atl-cs-001.litwareinc.com » - PoolState FailedOver** pour faire basculer la base de données mgc sauvegarde. Veillez à remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.
    
    La base de données mgc de sauvegarde est désormais la base de données principale.
    
6. Dans Skype pour Business Server Management Shell, utilisez l’applet de commande **Install-CsMirrorDatabase** pour établir une mise en miroir haute disponibilité pour la base de données de sauvegarde qui sert désormais la base de données principale. Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir. Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.
    
7. Définir les serveurs actifs du serveur de conversation permanente. À partir de Skype pour Business Server Management Shell, utilisez l’applet de commande **Set-cspersistentchatactiveserver ne** pour définir la liste de serveurs actives.
    
    > [!IMPORTANT]
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données. 
  
    À ce stade, le basculement de la base de données principale du serveur de conversation permanente à la base de données Persistent Chat Server sauvegarde se termine correctement.
    
## <a name="fail-back-persistent-chat-server"></a>Échec du serveur de conversation permanente

Cette procédure décrit les étapes nécessaires pour récupérer d’une défaillance du serveur de conversation permanente et pour rétablir les opérations à partir du centre de données principal.
  
Défaillance d’un serveur de conversation permanente, le centre de données principal subit une panne complète et le serveur principal et miroir de bases de données ne sont plus disponibles. Le centre de données principal bascule vers le serveur de sauvegarde.
  
La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits. La procédure suppose que le centre de données principal a été récupéré à partir d’une panne totale et que la base de données mgc et la base de données mgccomp ont été régénérés et réinstallés à l’aide du Générateur de topologie.
  
La procédure s’appuie aussi sur le fait qu’aucun nouveau serveur (miroir et de sauvegarde) n’a été déployé au cours de la période de basculement, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, conformément à la définition donnée dans Basculement vers un serveur de conversation permanente.
  
Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.
  
1. Désactivez tous les serveurs de la liste Persistent Chat Server Active Server à l’aide de l’applet de commande **Set-cspersistentchatactiveserver ne** le Skype pour Business Server Management Shell. Cela arrête tous les serveurs de conversation permanente de se connecter à la base de données mgc et la base de données mgccomp durant la restauration.
    
    > [!IMPORTANT]
    > L’agent SQL Server sur le serveur secondaire Persistent Chat Server le serveur principal doit être en cours d’exécution sous un compte privilégié. Plus précisément, le compte doit disposer des droits suivants : 
  
   - Accès en lecture au partage réseau dans lequel les sauvegardes sont placées
    
   - Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées
    
2. Désactivez la mise en miroir sur la base de données mgc de sauvegarde :
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.
    
   - Cliquez sur **Supprimer la mise en miroir**.
    
   - Cliquez sur **OK**.
    
   - Procédez de la même façon avec la base de données mgccomp.
    
3. Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.
    
   - Dans **Type de sauvegarde**, sélectionnez **Complète**.
    
   - Pour **Composant de sauvegarde**, cliquez sur **Base de données**.
    
   - Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.
    
   -  * \<Facultatif\> *  Dans la zone **Description**, entrez une description du jeu de sauvegarde.
    
   - Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.
    
   - Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.
    
   - Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.
    
4. Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.
    
   - À l’aide de SQL Server Management Studio, connectez-vous à l’instance mgc primaire.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.
    
   - Sélectionnez **À partir du périphérique**.
    
   - Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.
    
   - Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.
    
   - Dans le volet **Sélectionner une page**, cliquez sur **Options**.
    
   - Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.
    
   - Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.
    
   - Cliquez sur **OK** pour lancer le processus de restauration.
    
5. Configurer les journaux SQL Server pour la base de données principale. Suivez les procédures [configuration de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) pour établir l’envoi de journaux pour la base de données mgc primaire.
    
6. Définir les serveurs actifs du serveur de conversation permanente. À partir de Skype pour Business Server Management Shell, utilisez l’applet de commande **Set-cspersistentchatactiveserver ne** pour définir la liste de serveurs actives.
    
    > [!IMPORTANT]
    > Tous les serveurs actifs doivent être situés au sein du même centre de données que celui de la nouvelle base de données primaire, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données. 
  
Pour restaurer le pool à son état normal, exécutez la commande Windows PowerShell suivante :
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .
  

