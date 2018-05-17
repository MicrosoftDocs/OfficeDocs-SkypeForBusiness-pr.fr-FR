---
title: Déployer un groupe de disponibilité toujours actif sur un serveur principal dans Skype pour Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Déployer le déploiement (installation) un toujours sur groupe de disponibilité dans votre Skype pour Business Server.
ms.openlocfilehash: ed6155ca1d3c7b24450bd8ca5099c2f6fc75e8a4
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a>Déployer un groupe de disponibilité toujours actif sur un serveur principal dans Skype pour Business Server 2015
 
Déployer le déploiement (installation) un toujours sur disponibilité Group (AG) dans votre Skype pour Business Server.
  
Comment déployer une AG dépend de si vous déployez il dans un nouveau pool, un pool existant qui utilise la mise en miroir ou un pool existant qui est actuellement pas de haute disponibilité pour la base de données principale.
  
> [!NOTE]
> À l’aide d’un AG avec un rôle de serveur de conversation permanente n’est pas pris en charge. 
  
- [Déployer un toujours sur groupe de disponibilité dans un nouveau pool frontal](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Déployer un toujours sur groupe de disponibilité sur un pool existant qui utilise la mise en miroir de base de données](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Déployer un toujours sur groupe de disponibilité sur un pool existant qui n’utilise pas la mise en miroir de base de données](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Déployer un toujours sur groupe de disponibilité dans un nouveau pool frontal
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Activer la fonctionnalité Clustering avec basculement sur tous les serveurs de base de données qui feront partie de l’AG. Sur chaque serveur, procédez comme suit :
    
   - Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.
    
   - Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.
    
   - Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.
    
   - Cliquez sur **Installer**.
    
2. Validez la configuration de cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.
    
   - Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.
    
   - Dans la zone**Résumé** , vérifiez les erreurs de rapports de l’Assistant. Cliquez sur **Terminer** pour terminer la validation.
    
    L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.
    
3. Créer un Cluster de basculement Windows Server (WSFC).
    
   - Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.
    
   - Dans la page Confirmation, cliquez sur **Suivant**.
    
   - Après la création du cluster, cliquez sur **Terminer**.
    
4. Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :
    
   - Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.
    
   - Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.
    
   - Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.
    
   - Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.
    
   - Dans la page **Confirmation**, cliquez sur **Suivant**.
    
5. Sur chaque serveur du cluster, activez la fonctionnalité AG dans le Gestionnaire de Configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server.  
    
   - Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.
    
6. Créez le groupe de disponibilité.
    
   - Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.
    
   - Dans l’Explorateur d’objets, développez le dossier **Toujours sur une haute disponibilité** . Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.
    
   - Si la page **Présentation** s’affiche, cliquez sur **Suivant**.
    
   - Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
   - Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn. Then click **Next**.
    
    N’incluez pas le **ReportServer**, **ReportServerTempDB**ou bases de données de conversation permanente dans le groupe de disponibilité AlwaysOn, comme ils ne sont pas pris en charge dans ce scénario. Vous pouvez inclure tous les autres Skype pour les bases de données Business Server dans le groupe de disponibilité AlwaysOn.
    
   - Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.
    
   - Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.
    
   - Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.
    
   - Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
   - Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.
    
   - Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.
    
    Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.
    
   - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
   - Dans la page**Résumé** , vérifiez tous les paramètres et cliquez sur Terminer.
    
7. Utilisez le Générateur de topologie pour créer le pool frontal, comme expliqué dans [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md). Lorsque vous le faites, spécifiez le AG comme le magasin SQL pour le pool.
    
8. Une fois le pool et l’AG sont déployés, effectuer certaines étapes finales pour vous assurer que les connexions SQL sur chacun des réplicas dans le groupe de disponibilité AlwaysOn. 
    
   - Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.
    
   - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Cliquez sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur ** Propriétés ** Modifier.
    
    - En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur de l’AG.
    
   - Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.
    
   - Ouvrez SQL Server Management Studio et accédez à la AG. Faites-le basculer vers un réplica secondaire.
    
   - Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions SQL sur le réplica :
    
   ```
   Install-CsDatabase -Update
   ```

   - Répétez les deux étapes précédentes (bascule vers le groupe à un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Déployer un toujours sur groupe de disponibilité sur un pool existant qui utilise la mise en miroir de base de données
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si le pool que vous mettez à niveau vers un AG héberge le magasin Central de gestion pour votre organisation, vous devez déplacer le CMS vers un autre pool avant de mettre à niveau de ce pool. Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool. Si vous ne disposez pas d’un autre pool dans votre organisation, vous pouvez déployer un serveur Standard Edition server temporairement et déplacer le CMS sur ce serveur de mise à niveau de votre pool à la AG. 
  
1. Faire basculer toutes les données à partir de la mise en miroir au nœud principal en ouvrant Skype pour Business Server Management Shell et en tapant l’applet de commande suivante.
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Répétez cette applet de commande pour chaque type de base de données dans le pool. Vous pouvez utiliser l’applet de commande ci-dessous pour trouver tous les types de bases de données stockées dans ce pool.
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Utilisation du Générateur de topologie pour supprimer la mise en miroir de base de données à partir du pool
    
   - Ouvrez le Générateur de topologie. Dans votre topologie, développez **Pools frontaux Entreprise Edition**, cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés**.
    
   - Pour chaque type de magasin SQL dans le pool, désactivez la case à cocher **Activer la mise en miroir du magasin SQL**.
    
3. Publiez la topologie modifiée. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
4. Utilisez SQL Server Management Studio afin de rompre la mise en miroir.
    
   - Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir**. Cliquez ensuite sur **Supprimer la mise en miroir** et cliquez sur **OK**.
    
   - Répétez cette procédure pour toutes les bases de données du pool qui sera converti en un AG.
    
5. Configurer la fonctionnalité Clustering avec basculement sur tous les serveurs de base de données qui feront partie de l’AG. Sur chaque serveur, procédez comme suit :
    
   - Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.
    
   - Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.
    
   - Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.
    
   - Cliquez sur **Installer**.
    
6. Validez la configuration de cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.
    
   - Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.
    
   - Dans la zone**Résumé** , vérifiez les erreurs de rapports de l’Assistant. Cliquez sur **Terminer** pour terminer la validation.
    
    L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.
    
7. Créer un Cluster de basculement Windows Server.
    
   - Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.
    
   - Dans la page Confirmation, cliquez sur **Suivant**.
    
   - Après la création du cluster, cliquez sur **Terminer**.
    
8. Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :
    
   - Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.
    
   - Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.
    
   - Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.
    
   - Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.
    
   - Dans la page **Confirmation**, cliquez sur **Suivant**.
    
9. Sur chaque serveur du cluster, activez la fonctionnalité AG dans le Gestionnaire de Configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server.  
    
   - Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.
    
10. Créez le groupe de disponibilité.
    
    - Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.
    
    - Dans l’Explorateur d’objets, développez le dossier **Toujours sur une haute disponibilité** . Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.
    
    - Si la page **Présentation** s’affiche, cliquez sur **Suivant**.
    
    - Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
    - Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn. Then click **Next**.
    
    N’incluez pas le **ReportServer**, **ReportServerTempDB**ou bases de données de conversation permanente dans le groupe de disponibilité AlwaysOn, comme ils ne sont pas pris en charge dans ce scénario. Vous pouvez inclure tous les autres Skype pour les bases de données Business Server dans le groupe de disponibilité AlwaysOn.
    
    - Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.
    
    - Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.
    
    - Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.
    
     - Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
    - Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.
    
    - Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.
    
    Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.
    
    - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
    - Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.
    
11. Créer un nouveau magasin spécifiant le port d’écoute AG et en spécifiant le principal du miroir ancien comme nœud principal de l’AG.
    
    - Ouvrez le Générateur de topologie. Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.
    
    - Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.
    
    - Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.
    
    - Dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal de l’AG, puis cliquez sur **OK**. Il doit s’agir du principal de l’ancien miroir pour ce magasin.
    
12. Associez le nouveau AG le pool frontal.
    
    - Dans le Générateur de topologie, cliquez sur le pool à associer avec AG, cliquez sur **Modifier les propriétés**.
    
    - Sous **Associations**, dans la zone **Magasin SQL Server** , sélectionnez le AG. Sélectionnez le groupe même pour les autres bases de données dans le pool auquel vous souhaitez déplacer vers le AG.
    
    - Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies à l’AG, cliquez sur **OK**.
    
13. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
14. Effectuer certaines étapes finales pour vous assurer que les connexions SQL sur chacun des réplicas dans le groupe de disponibilité AlwaysOn.
    
    - Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.
    
    - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Avec le bouton droit de la nouvel AG magasin SQL, puis cliquez sur **Modifier les propriétés**.
    
    - En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur de l’AG.
    
    - Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.
    
    - Ouvrez SQL Server Management Studio et accédez à la AG. Faites-le basculer vers un réplica secondaire.
    
    - Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions SQL sur le réplica :
    
    ```
    Install-CsDatabase -Update
    ```

    - Répétez les deux étapes précédentes (bascule vers le groupe à un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Déployer un toujours sur groupe de disponibilité sur un pool existant qui n’utilise pas la mise en miroir de base de données
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si le pool que vous mettez à niveau vers un AG héberge le magasin Central de gestion pour votre organisation, vous devez déplacer le CMS vers un autre pool avant de mettre à niveau de ce pool. Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool. Si vous ne disposez pas d’un autre pool dans votre organisation, vous pouvez déployer un serveur Standard Edition server temporairement et déplacer le CMS sur ce serveur de mise à niveau de votre pool à la AG. 
  
1. Configurer la fonctionnalité Clustering avec basculement sur tous les serveurs de base de données qui feront partie de l’AG. Sur chaque serveur, procédez comme suit :
    
   - Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.
    
   - Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.
    
   - Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.
    
   - Cliquez sur **Installer**.
    
2. Validez la configuration de cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.
    
   - Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.
    
   - Dans la zone**Résumé** , vérifiez les erreurs de rapports de l’Assistant. Cliquez sur **Terminer** pour terminer la validation.
    
    L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.
    
3. Créer un Cluster de basculement Windows Server (WSFC).
    
   - Dans l’Assistant **Gestion du cluster de basculement**, cliquez avec le bouton droit sur **Gestion du cluster de basculement**, puis cliquez sur **Créer cluster**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Ajoutez le nom de cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.
    
   - Dans la page Confirmation, cliquez sur **Suivant**.
    
   - Après la création du cluster, cliquez sur **Terminer**.
    
4. Nous vous recommandons de configurer les paramètres du quorum de cluster à utiliser comme partage de fichiers témoin. Pour cela, procédez comme suit :
    
   - Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions**, puis cliquez sur **Configurer les paramètres du quorum de cluster**.
    
   - Dans la page **Sélectionner l’option de configuration du quorum**, cliquez sur **Sélectionner le quorum témoin**.
    
   - Dans la page **Sélectionner un quorum témoin**, cliquez sur **Configurer un partage de fichiers témoin**.
    
   - Dans la page **Configurer le partage de fichiers témoin**, entrez le chemin d’accès au partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.
    
   - Dans la page **Confirmation**, cliquez sur **Suivant**.
    
5. Sur chaque serveur du cluster, activer AG dans le Gestionnaire de Configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server.  
    
   - Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.
    
6. Créez le groupe de disponibilité.
    
   - Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.
    
   - Dans l’Explorateur d’objets, développez le dossier **Toujours sur une haute disponibilité** . Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.
    
   - Si la page **Présentation** s’affiche, cliquez sur **Suivant**.
    
   - Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
   - Dans la page Sélectionner les bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le AG. Then click **Next**.
    
    N’incluez pas le **ReportServer**, **ReportServerTempDB**ou bases de données de conversation permanente du groupe AG, comme ils ne sont pas pris en charge dans ce scénario. Vous pouvez inclure tous les autres Skype pour les bases de données Business Server du groupe AG.
    
   - Dans la page **Spécifier les réplicas** , cliquez sur l’onglet **réplicas** . Cliquez sur le bouton **Ajouter les réplicas** , puis se connecter à d’autres instances SQL que vous avez rejoint sous forme de nœuds de la WSFC.
    
   - Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.
    
   - Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.
    
   - Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
   - Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.
    
   - Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.
    
    Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.
    
    - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
   - Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.
    
7. Créer un nouveau magasin spécifiant le port d’écoute AG.
    
   - Ouvrez le Générateur de topologie. Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.
    
   - Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.
    
   - Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.
    
   - Dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal de l’AG, puis cliquez sur **OK**.
    
8. Associez le nouveau toujours sur groupe de disponibilité avec le pool frontal.
    
   - Dans le Générateur de topologie, cliquez sur le pool à associer avec AG, cliquez sur **Modifier les propriétés**.
    
   - Sous **Associations**, dans la zone **Magasin SQL Server** , sélectionnez le AG. Sélectionnez le groupe même pour les autres bases de données dans le pool auquel vous souhaitez déplacer vers le AG.
    
   - Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies à l’AG, cliquez sur **OK**.
    
9. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
10. Effectuer certaines étapes pour vous assurer que les connexions SQL sur tous les réplicas du groupe AG finales.
    
    - Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.
    
    - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Avec le bouton droit de la nouvel AG magasin SQL, puis cliquez sur ** Propriétés ** Modifier.
    
    - En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , modifiez la valeur pour le nom de domaine complet de l’écouteur de l’AG.
    
    - Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.
    
    - Ouvrez SQL Server Management Studio et accédez à la AG. Faites-le basculer vers un réplica secondaire.
    
    - Ouvrez Skype pour Business Server Management Shell et entrez l’applet de commande suivante pour créer les connexions SQL sur le réplica :
    
     ```
     Install-CsDatabase -Update
     ```

     - Répétez les deux étapes précédentes (bascule vers le groupe à un réplica secondaire, puis utilisez `Install-CsDatabase -Update`) pour chaque réplica dans le groupe.
    

