---
title: Gérer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Résumé : Découvrez comment gérer la haute disponibilité et la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: bf24bbb7f8672f0bc3a75b83f4f57320dc975092
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860011"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gérer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer la haute disponibilité et la récupération d’urgence du serveur de conversation permanente dans Skype Entreprise Server 2015.
  
Cette rubrique décrit comment faire échouer et faire échouer le serveur de conversation permanente. Avant de lire cette rubrique, veillez à lire Planifier la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans [Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) et à configurer la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans [Skype Entreprise Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Faire échouer le serveur de conversation permanente

Le failover pour le serveur de conversation permanente est conçu pour être principalement un processus manuel.
  
La procédure de failover repose sur l’hypothèse que le centre de données secondaire est opérationnel, mais les services du serveur de conversation permanente où se trouve la base de données de conversation permanente principale sont complètement indisponibles, notamment :
  
- La base de données principale du serveur de conversation permanente et la base de données miroir du serveur de conversation permanente sont en panne.
    
- Skype Entreprise Server Le serveur frontal est en panne.
    
La procédure consiste en deux étapes de base :
  
- Récupérez la base de données de conversation permanente principale (mgc).
    
- Établir la mise en miroir pour la nouvelle base de données principale.
    
La base de données de conformité de conversation permanente (mgccomp) n’est pas recalculée. Le contenu de cette base de données est temporaire et purgé au fur et à mesure que l’adaptateur de conformité traite les données. Il est de votre responsabilité, en tant qu’administrateur de conversation permanente, de gérer correctement la sortie de la carte afin d’éviter la perte de données.
  
Pour faire échouer le serveur de conversation permanente :
  
1. Supprimez la copie des journaux de livraison de la base de données de copie des journaux de sauvegarde du serveur de conversation permanente.
    
   - À l SQL Server Management Studio, connectez-vous à l’instance de base de données où se trouve la base de données mgc de sauvegarde du serveur de conversation permanente.
    
   - Ouvrez une fenêtre de requête pour la base de données principale.
    
   - Utilisez la commande suivante pour annuler la copie des journaux de transaction :
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copiez tous les fichiers de sauvegarde non copiés se trouvant sur le partage de sauvegarde vers le dossier de destination de la copie du serveur de sauvegarde.
    
3. Appliquez dans l’ordre toutes les sauvegardes du journal des transactions non appliquées à la base de données secondaire. Pour plus d’informations, [voir How to: Apply a Transaction Log Backup (Transact-SQL).](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))
    
4. Mettez en ligne la base de données mgc de sauvegarde. Dans la fenêtre de requête ouverte à l’étape 1b, procédez comme suit :
    
   - Mettez fin à toutes les connexions à la base de données mgc, le cas échéant :
    
   - **exec sp_who2** pour identifier les connexions à la base de données mgc.
    
   - **kill \<spid\>** pour mettre fin à ces connexions.
    
   - Mettez en ligne la base de données :
    
   - **restaurer la base de données mgc avec récupération.**
    
5. Dans Skype Entreprise Server Management Shell, utilisez la commande **Set-CsPersistentChatState -Identity « service:atl-cs-001.litwareinc.com » -PoolState FailedOver** pour faire échouer la base de données de sauvegarde mgc. N’oubliez pas de remplacer le nom de domaine complet de votre pool de conversation permanente par atl-cs-001.litwareinc.com.
    
    La base de données mgc de sauvegarde est désormais la base de données principale.
    
6. Dans Skype Entreprise Server Management Shell, utilisez l’cmdlet **Install-CsMirrorDatabase** pour établir un miroir de haute disponibilité pour la base de données de sauvegarde qui sert désormais de base de données principale. Utilisez l’instance de la base de données de sauvegarde en tant que base de données principale et l’instance de la base de données miroir de sauvegarde en tant qu’instance miroir. Il ne s’agit pas du même miroir que celui qui a été initialement configuré pour la base de données principale pendant la configuration.
    
7. Définissez les serveurs actifs du serveur de conversation permanente. À partir Skype Entreprise Server Management Shell, utilisez l’applet de commandes **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    > [!IMPORTANT]
    > Tous les serveurs actifs doivent être situés dans le même centre de données que celui de la nouvelle base de données principale, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données. 
  
    À ce stade, le passage de la base de données principale du serveur de conversation permanente à la base de données de sauvegarde du serveur de conversation permanente se termine correctement.
    
## <a name="fail-back-persistent-chat-server"></a>Faire échouer le serveur de conversation permanente

Cette procédure décrit les étapes nécessaires à la récupération après une défaillance du serveur de conversation permanente et à la reprise des opérations à partir du centre de données principal.
  
En cas de défaillance du serveur de conversation permanente, le centre de données principal subit une panne complète et les bases de données principale et miroir deviennent indisponibles. Le centre de données principal bascule vers le serveur de sauvegarde.
  
La procédure suivante rétablit le fonctionnement normal une fois le centre de données principal sauvegardé et les serveurs reconstruits. La procédure suppose que le centre de données principal a été récupéré après une panne totale et que la base de données mgc et la base de données mgccomp ont été reconstruites et réinstallées à l’aide du Générateur de topologie.
  
La procédure suppose également qu’aucun nouveau serveur miroir et serveur de sauvegarde n’a été déployé pendant la période de failover, et que le seul serveur déployé est le serveur de sauvegarde et son serveur miroir, comme défini précédemment dans Le serveur de conversation permanente fail over Persistent Chat.
  
Ces étapes visent à récupérer la configuration telle qu’elle existait avant la défaillance, cette dernière ayant provoqué le basculement du serveur principal vers le serveur de sauvegarde.
  
1. Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype Entreprise Server Management Shell. Cela empêche tous les serveurs de conversation permanente de se connecter à la base de données mgc et à la base de données mgccomp pendant la récupération.
    
    > [!IMPORTANT]
    > L’agent SQL Server sur le serveur principal du serveur de conversation permanente secondaire doit être en cours d’exécution sous un compte privilégié. Plus précisément, le compte doit disposer des droits suivants : 
  
   - Accès en lecture au partage réseau dans lequel les sauvegardes sont placées
    
   - Accès en écriture au répertoire local spécifique vers lequel les sauvegardes sont copiées
    
2. Désactivez la mise en miroir sur la base de données mgc de sauvegarde :
    
   - À l SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Miroir**.
    
   - Cliquez sur **Supprimer la mise en miroir**.
    
   - Cliquez sur **OK**.
    
   - Procédez de la même façon avec la base de données mgccomp.
    
3. Sauvegardez la base de données mgc afin qu’elle puisse être restaurée vers la nouvelle base de données primaire :
    
   - À l SQL Server Management Studio, connectez-vous à l’instance mgc de sauvegarde.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**. La boîte de dialogue **Sauvegarder la base de données** s’affiche.
    
   - Dans **Type de sauvegarde**, sélectionnez **Complète**.
    
   - Pour **Composant de sauvegarde**, cliquez sur **Base de données**.
    
   - Acceptez le nom du jeu de sauvegarde par défaut suggéré dans **Nom** ou entrez un autre nom pour le jeu de sauvegarde.
    
   -  *\<Optional\>*  Dans **Description,** entrez une description du jeu de sauvegarde.
    
   - Supprimez l’emplacement de sauvegarde par défaut de la liste de destination.
    
   - Ajoutez un fichier à la liste en utilisant le chemin d’accès à l’emplacement de partage que vous avez établi pour l’envoi de journaux. Ce chemin d’accès est accessible à la base de données primaire et à la base de données de sauvegarde.
    
   - Cliquez sur **OK** pour fermer la boîte de dialogue et lancer le processus de sauvegarde.
    
4. Restaurez la base de données primaire à l’aide de la base de données de sauvegarde créée à l’étape précédente.
    
   - À l SQL Server Management Studio, connectez-vous à l’instance mgc principale.
    
   - Cliquez avec le bouton droit sur la base de données mgc, pointez sur **Tâches**, sur **Restaurer**, puis cliquez sur **Base de données**. La boîte de dialogue **Restaurer la base de données** s’affiche.
    
   - Sélectionnez **À partir du périphérique**.
    
   - Cliquez sur le bouton Parcourir pour ouvrir la boîte de dialogue **Spécifier la sauvegarde**. Dans **Support de sauvegarde**, sélectionnez **Fichier**. Cliquez sur **Ajouter**, sélectionnez le fichier de sauvegarde que vous avez créé à l’étape 3, puis cliquez sur **OK**.
    
   - Dans **Sélectionnez les jeux de sauvegarde à restaurer**, sélectionnez la sauvegarde.
    
   - Dans le volet **Sélectionner une page**, cliquez sur **Options**.
    
   - Dans **Options de restauration**, sélectionnez uniquement **Remplacer la base de données existante**.
    
   - Dans **État de récupération**, sélectionnez **Laisser la base de données opérationnelle**.
    
   - Cliquez sur **OK** pour lancer le processus de restauration.
    
5. Configurez la SQL Server des journaux de livraison pour la base de données principale. Suivez les procédures de la procédure de configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente dans [Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) pour établir la livraison des journaux pour la base de données mgc principale.
    
6. Définissez les serveurs actifs du serveur de conversation permanente. À partir Skype Entreprise Server Management Shell, utilisez l’applet de commandes **Set-CsPersistentChatActiveServer** pour définir la liste des serveurs actifs.
    
    > [!IMPORTANT]
    > Tous les serveurs actifs doivent être situés dans le même centre de données que celui de la nouvelle base de données principale, ou dans un centre de données avec une connexion à latence faible/bande passante élevée à la base de données. 
  
Pour restaurer l’état normal du pool, exécutez la commande Windows PowerShell suivante :
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Set-CsPersistentChatState.](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)
