---
title: Déploiement d’un groupe toujours disponible sur un serveur principal dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Déploiement (installation) d’un groupe toujours disponible dans le déploiement de Skype entreprise Server.
ms.openlocfilehash: 2cfc75aecd53a82e146feefd944134a4695c21fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240125"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Déploiement d’un groupe toujours disponible sur un serveur principal dans Skype entreprise Server
 
Déploiement (installation) d’un groupe toujours disponible sur le déploiement de Skype entreprise Server.
  
Le mode de déploiement d’un programme AG dépend du mode de déploiement dans un nouveau pool, d’un pool existant qui utilise la mise en miroir ou d’un pool existant qui n’est actuellement pas disponible pour la base de données principale.
  
> [!NOTE]
> L’utilisation de la fonction AG avec un rôle serveur de chat permanent n’est pas prise en charge. 
  
- [Déploiement d’un groupe toujours disponible sur une nouvelle liste frontale](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Déployer un groupe toujours disponible sur un pool existant qui utilise la mise en miroir de base de données](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Déployer un groupe toujours disponible sur un pool existant qui n’utilise pas la mise en miroir de base de données](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Déploiement d’un groupe toujours disponible sur une nouvelle liste frontale
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Activez la fonctionnalité de mise en cluster de basculement sur tous les serveurs de base de données qui feront partie de la AG. Sur chaque serveur, procédez comme suit :
    
   - Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.
    
   - Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.
    
   - Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.
    
   - Cliquez sur **Installer**.
    
2. Validez la configuration de cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.
    
   - Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.
    
   - Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.
    
     L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.
    
3. Créez le cluster de basculement de Windows Server (WSFC).
    
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
    
5. Sur chaque serveur dans le cluster, activez la fonction AG dans le gestionnaire de configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server.  
    
   - Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.
   
6. Utilisez le générateur de topologie pour créer le pool frontal, comme décrit dans la rubrique [créer et publier une nouvelle topologie dans Skype entreprise Server](../../deploy/install/create-and-publish-new-topology.md). Le cas échéant, spécifiez la AG comme magasin SQL pour le pool.
    
7. Créez le groupe de disponibilité.
    
   - Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.
    
   - Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** . Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.
    
   - Si la page **Présentation** s’affiche, cliquez sur **Suivant**.
    
   - Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
   - Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous voulez inclure dans le groupe disponibilité AlwaysOn. Then click **Next**.
    
     N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou persistante dans le groupe disponibilité AlwaysOn, car ces informations ne sont pas prises en charge dans ce scénario. Vous pouvez inclure les autres bases de données Skype entreprise Server dans le groupe disponibilité AlwaysOn.
    
   - Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.
    
   - Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.
    
   - Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.
    
   - Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
   - Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.
    
   - Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.
    
     Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.
    
   - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
   - Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.
      
8. Après le déploiement du pool et de la AG, réalisez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du groupe disponibilité AlwaysOn. 
    
   - Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
   - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Cliquez avec le bouton droit sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **modifier les propriétés**.
    
     - En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.
    
   - Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.
    
   - Ouvrez SQL Server Management Studio, puis accédez à la AG. Faites-le basculer vers un réplica secondaire.
    
   - Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica:
    
   ```
   Install-CsDatabase -Update
   ```

   - Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Déployer un groupe toujours disponible sur un pool existant qui utilise la mise en miroir de base de données
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si le pool sur lequel vous effectuez la mise à niveau vers un serveur AG héberge le magasin de gestion central de votre organisation, vous devez d’abord déplacer le MCG vers un autre pool avant de mettre à niveau ce pool. Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool. Si vous n’avez pas d’autre liste au sein de votre organisation, vous pouvez déployer temporairement un serveur Standard Edition et déplacer le CMS vers ce serveur avant de mettre à niveau votre groupe vers la AG. 
  
1. Basculez toutes les données du miroir vers le nœud principal en ouvrant Skype entreprise Server Management Shell et en tapant l’applet de commande suivante.
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Répétez cette applet de commande pour chaque type de base de données dans le pool. Vous pouvez utiliser l’applet de commande ci-dessous pour trouver tous les types de bases de données stockées dans ce pool.
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Utilisez le générateur de topologie pour supprimer la mise en miroir de la base de données du pool.
    
   - Ouvrez le générateur de topologie. Dans votre topologie, développez **Pools frontaux Entreprise Edition**, cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés**.
    
   - Pour chaque type de magasin SQL dans le pool, désactivez la case à cocher **Activer la mise en miroir du magasin SQL**.
    
3. Publiez la topologie modifiée. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
4. Utilisez SQL Server Management Studio afin de rompre la mise en miroir.
    
   - Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir**. Cliquez ensuite sur **Supprimer la mise en miroir** et cliquez sur **OK**.
    
   - Répétez cette opération pour toutes les bases de données de la liste de ressources partagées qui seront converties en AG.
    
5. Configurez la fonctionnalité de clustering de basculement sur tous les serveurs de base de données qui feront partie de la AG. Sur chaque serveur, procédez comme suit :
    
   - Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.
    
   - Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.
    
   - Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.
    
   - Cliquez sur **Installer**.
    
6. Validez la configuration de cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.
    
   - Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.
    
   - Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.
    
     L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.
    
7. Créez le cluster Windows Server Failover.
    
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
    
9. Sur chaque serveur dans le cluster, activez la fonction AG dans le gestionnaire de configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server.  
    
   - Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.
    
10. Créez le groupe de disponibilité.
    
    - Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.
    
    - Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** . Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.
    
    - Si la page **Présentation** s’affiche, cliquez sur **Suivant**.
    
    - Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
    - Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous voulez inclure dans le groupe disponibilité AlwaysOn. Then click **Next**.
    
    N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou persistante dans le groupe disponibilité AlwaysOn, car ces informations ne sont pas prises en charge dans ce scénario. Vous pouvez inclure les autres bases de données Skype entreprise Server dans le groupe disponibilité AlwaysOn.
    
    - Dans la page **Spécifier des réplicas**, cliquez sur l’onglet **Réplicas**. Cliquez ensuite sur le bouton **Ajouter des réplicas**, puis connectez-vous aux autres instances SQL que vous avez jointes comme nœuds du cluster de basculement Windows Server.
    
    - Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.
    
    - Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.
    
      - Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
    - Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.
    
    - Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.
    
    Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.
    
    - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
    - Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.
    
11. Créez une nouvelle banque spécifiant l’écouteur AG et spécifiez le principal de l’ancien miroir en tant que nœud principal de la AG.
    
    - Ouvrez le générateur de topologie. Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.
    
    - Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.
    
    - Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.
    
    - Dans la zone **FQDN SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal de la AG, puis cliquez sur **OK**. Il doit s’agir du principal de l’ancien miroir pour ce magasin.
    
12. Associez le nouveau AG au pool frontal.
    
    - Dans le générateur de topologie, cliquez avec le bouton droit sur le pool à associer à la AG, puis cliquez sur **modifier les propriétés**.
    
    - Sous **associations**, dans la zone **SQL Server Store** , sélectionnez AG. Sélectionnez le même groupe pour toutes les autres bases de données de la liste que vous voulez déplacer vers la AG.
    
    - Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies sur AG, cliquez sur **OK**.
    
13. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
14. Effectuez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du groupe disponibilité AlwaysOn.
    
    - Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
    - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Cliquez avec le bouton droit sur le magasin SQL du nouveau AG, puis cliquez sur **modifier les propriétés**.
    
    - En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.
    
    - Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.
    
    - Ouvrez SQL Server Management Studio, puis accédez à la AG. Faites-le basculer vers un réplica secondaire.
    
    - Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica:
    
    ```
    Install-CsDatabase -Update
    ```

    - Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Déployer un groupe toujours disponible sur un pool existant qui n’utilise pas la mise en miroir de base de données
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si le pool sur lequel vous effectuez la mise à niveau vers un serveur AG héberge le magasin de gestion central de votre organisation, vous devez d’abord déplacer le MCG vers un autre pool avant de mettre à niveau ce pool. Utilisez l’applet de commande Move-CsManagementServer pour déplacer le pool. Si vous n’avez pas d’autre liste au sein de votre organisation, vous pouvez déployer temporairement un serveur Standard Edition et déplacer le CMS vers ce serveur avant de mettre à niveau votre groupe vers la AG. 
  
1. Configurez la fonctionnalité de clustering de basculement sur tous les serveurs de base de données qui feront partie de la AG. Sur chaque serveur, procédez comme suit :
    
   - Ouvrez le Gestionnaire de serveur et cliquez sur **Ajout de rôles et de fonctionnalités**.
    
   - Cliquez sur **Suivant** jusqu’à ce que vous accédiez à la zone **Sélectionner les fonctionnalités**. Ici, activez la case à cocher **Clustering de basculement**.
    
   - Dans la zone **Ajouter des fonctionnalités requises pour le clustering de basculement ?**, cliquez sur **Ajouter des fonctionnalités**.
    
   - Cliquez sur **Installer**.
    
2. Validez la configuration de cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils**, puis sur **Gestionnaire du cluster de basculement**.
    
   - Sous **Actions** dans la partie droite de l’écran, cliquez sur **Valider la configuration**.
    
   - Dans la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests**.
    
   - Dans la boîte **Résumé**, vérifiez les erreurs signalées par l’Assistant, puis cliquez sur **Terminer** pour terminer la validation.
    
     L’Assistant signalera probablement plusieurs avertissements, notamment si vous n’utilisez pas le stockage partagé. Vous n’avez pas besoin d’utiliser le stockage partagé. Toutefois, si des messages **Erreur** s’affichent, vous devez corriger ces problèmes avant de poursuivre.
    
3. Créez le cluster de basculement de Windows Server (WSFC).
    
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
    
5. Sur chaque serveur du cluster, activez AG dans le gestionnaire de configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence dans la partie gauche de l’écran, cliquez sur **Services SQL Server**, puis double-cliquez sur le service SQL Server.  
    
   - Dans la zone **Propriétés**, sélectionnez l’onglet **Haute disponibilité AlwaysOn**. Activez la case à cocher **Activer les groupes de disponibilité AlwaysOn**. Redémarrez le service SQL Server lorsque vous y êtes invité.
    
6. Créez le groupe de disponibilité.
    
   - Ouvrez SQL Server Management Studio, puis connectez-vous à l’instance SQL Server.
    
   - Dans l’Explorateur d’objets, développez le dossier **toujours à haute disponibilité** . Cliquez avec le bouton droit sur le dossier **Groupes de disponibilité**, puis cliquez sur **Assistant Nouveau groupe de disponibilité**.
    
   - Si la page **Présentation** s’affiche, cliquez sur **Suivant**.
    
   - Dans la page **Spécifier le nom du groupe de disponibilité**, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
   - Dans la page Sélectionner une base de données, sélectionnez les bases de données que vous voulez inclure dans le AG. Then click **Next**.
    
     N’incluez pas les bases de données de chat **reportserver**, **ReportServerTempDB**ou permanentes dans la AG, car elles ne sont pas prises en charge dans ce scénario. Vous pouvez inclure toutes les autres bases de données Skype entreprise Server du AG.
    
   - Dans la page **spécifier** des réplicas, cliquez sur l’onglet **fac-similés** . Cliquez ensuite sur le bouton **Ajouter** des réplicas, puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nœuds du WSFC.
    
   - Pour chaque instance, sélectionnez les options **Basculement automatique** et **Validation synchrone**. Ne sélectionnez pas l’option **Secondaire lisible**.
    
   - Cliquez sur l’onglet **Points de terminaison** et vérifiez que le **Numéro de port** est défini sur 5022.
    
   - Cliquez sur l’onglet **Port d’écoute**, puis sélectionnez l’onglet **Créer un port de d’écoute de groupe de disponibilité**. Sous cette option, tapez un nom pour le port d’écouteur et définissez le **Port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
   - Cliquez sur **Ajouter**, puis dans la zone **Adresse IPv4**, fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK**.
    
   - Dans la page **Sélectionner la synchronisation de données initiale**, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et que le compte de service SQL Server a utilisé et sur lequel il a des autorisations d’écriture. Ensuite, cliquez sur **Suivant**.
    
     Ce partage de fichiers sera utilisé temporairement lorsque vous initialiserez les bases de données. Si vous devez gérer de grandes bases de données, nous vous recommandons de les initialiser manuellement au cas où votre bande passante réseau ne pourrait pas prendre en charge la taille des sauvegardes de bases de données.
    
     - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
   - Dans la page **Résumé**, vérifiez tous les paramètres et cliquez sur Terminer.
    
7. Créez une nouvelle banque spécifiant l’écouteur AG.
    
   - Ouvrez le générateur de topologie. Dans votre topologie, développez **Composants partagés**, cliquez avec le bouton droit sur **Magasins SQL Server**, puis cliquez sur **Nouveau magasin SQL Server**.
    
   - Dans la page **Définir un nouveau magasin SQL**, activez tout d’abord la case à cocher **Paramètres de la haute disponibilité**, puis assurez-vous que Groupes de disponibilité SQL AlwaysOn s’affiche dans la zone déroulante.
    
   - Dans la zone **Nom de domaine complet de disponibilité SQL Server**, tapez le nom de domaine complet du port d’écoute que vous avez défini lors de la création du groupe de disponibilité.
    
   - Dans la zone **FQDN SQL Server** , entrez le nom de domaine complet (FQDN) du nœud principal de la AG, puis cliquez sur **OK**.
    
8. Associez le nouveau groupe toujours disponible au pool frontal.
    
   - Dans le générateur de topologie, cliquez avec le bouton droit sur le pool à associer à la AG, puis cliquez sur **modifier les propriétés**.
    
   - Sous **associations**, dans la zone **SQL Server Store** , sélectionnez AG. Sélectionnez le même groupe pour toutes les autres bases de données de la liste que vous voulez déplacer vers la AG.
    
   - Lorsque vous êtes certain que toutes les bases de données nécessaires sont définies sur AG, cliquez sur **OK**.
    
9. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
10. Effectuez quelques étapes finales pour vous assurer que les connexions SQL se trouvent sur chacun des réplicas du AG.
    
    - Ouvrez le générateur de topologie, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
    - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Cliquez avec le bouton droit sur le magasin SQL du nouveau AG, puis cliquez sur **modifier les propriétés**.
    
    - En bas de la page, dans la zone **FQDN SQL Server** , remplacez la valeur par le nom de domaine complet (FQDN) de l’écouteur de la AG.
    
    - Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Attendez que la nouvelle topologie soit répliquée. L’opération peut prendre quelques minutes.
    
    - Ouvrez SQL Server Management Studio, puis accédez à la AG. Faites-le basculer vers un réplica secondaire.
    
    - Ouvrez Skype entreprise Server Management Shell et tapez l’applet de commande suivante pour créer les connexions SQL sur ce réplica:
    
      ```
      Install-CsDatabase -Update
      ```

      - Répétez les deux étapes précédentes (basculez le groupe vers un réplica secondaire, puis `Install-CsDatabase -Update`utilisez) pour chaque réplica du groupe.
