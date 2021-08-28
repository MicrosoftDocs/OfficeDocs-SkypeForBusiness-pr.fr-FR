---
title: Déployer un groupe de disponibilité Always On sur un serveur principal dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Déployez (installez) un groupe de disponibilité Always On dans votre Skype Entreprise Server déploiement.
ms.openlocfilehash: 72bd60e102bfa121e2b8f7704032f54242aee202
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620480"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Déployer un groupe de disponibilité Always On sur un serveur principal dans Skype Entreprise Server
 
Déployez (installez) un groupe de disponibilité Always On (AG) dans Skype Entreprise Server déploiement.
  
La façon dont vous déployez une ag ag varie selon que vous la déployez dans un nouveau pool, un pool existant qui utilise la mise en miroir ou un pool existant qui n’a actuellement aucune haute disponibilité pour la base de données principale.
  
> [!NOTE]
> L’utilisation d’une ag ag avec un rôle serveur de conversation permanente n’est pas prise en charge. 
  
- [Déployer un groupe de disponibilité Always On sur un nouveau pool frontal](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Déployer un groupe de disponibilité Always On sur un pool existant qui utilise la mise en miroir de bases de données](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Déployer un groupe de disponibilité Always On sur un pool existant qui n’utilise pas la mise en miroir de bases de données](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Déployer un groupe de disponibilité Always On sur un nouveau pool frontal
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Activez la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG. Sur chaque serveur, faites les étapes suivantes :
    
   - Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**
    
   - Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.** Ici, cochez la case **Clustering deover.**
    
   - Dans la **zone Ajouter des fonctionnalités requises** pour le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**
    
   - Cliquez sur **Installer**.
    
2. Validez la configuration du cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**
    
   - Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**
    
   - Sur la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**
    
   - Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale. Cliquez ensuite **sur Terminer** pour terminer la validation.
    
     L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé. Vous n’êtes pas obligé d’utiliser le stockage partagé. Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.
    
3. Créez le cluster Windows server failover cluster (WSFC).
    
   - Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**
    
   - Sur la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Ajoutez le nom du cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.
    
   - Sur la page Confirmation, cliquez sur **Suivant**.
    
   - Une fois le cluster créé, cliquez sur **Terminer.**
    
4. Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers. Pour ce faire, utilisez les étapes suivantes :
    
   - Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur Configurer le **quorum du cluster Paramètres**.
    
   - Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**
    
   - Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**
    
   - Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.
    
   - Sur la page **Confirmation**, cliquez sur **Suivant**.
    
5. Sur chaque serveur du cluster, activez la fonctionnalité AG dans Gestionnaire de configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service. 
    
   - Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez **la case à cocher Activer les groupes de disponibilité AlwaysOn.** Redémarrez le service SQL Server lorsque vous y invitez.
   
6. Utilisez le Générateur de topologie pour créer le pool frontal, comme expliqué dans Créer et publier une nouvelle [topologie dans Skype Entreprise Server](../../deploy/install/create-and-publish-new-topology.md). Lorsque vous le faites, spécifiez la ag ag comme SQL magasin pour le pool.
    
7. Créez le groupe de disponibilité.
    
   - Ouvrez SQL Server Management Studio et connectez-vous à l’SQL Server instance.
    
   - Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.** Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**
    
   - Si la page **Introduction** s’affiche, cliquez sur **Suivant.**
    
   - Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
   - Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn. Cliquez ensuite sur **Next (Suivant)**.
    
     N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou Persistent Chat dans le groupe de disponibilité AlwaysOn, car elles ne sont pas pris en charge dans ce scénario. Vous pouvez inclure toutes les autres bases Skype Entreprise Server de données dans le groupe de disponibilité AlwaysOn.
    
   - Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances de SQL que vous avez jointes en tant que Windows cluster de bas niveau de serveur.
    
   - Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.** Ne sélectionnez pas **l’option Secondaire lisible.**
    
   - Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.
    
   - Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité. Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
   - Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**
    
   - Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture. Cliquez ensuite sur **Next (Suivant)**.
    
     Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données. Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.
    
   - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
   - Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.
      
8. Une fois le pool et le groupe d’disponibilité de service déployés, effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de disponibilité AlwaysOn. 
    
   - Ouvrez le Générateur de topologie, **sélectionnez Télécharger la topologie** à partir d’un déploiement existant, puis cliquez sur **OK.**
    
   - Développez Skype Entreprise Server, développez votre topologie et développez **SQL Server Stores.** Cliquez avec le bouton droit SQL magasin du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés.**
    
     - En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe du listener de l’AG.
    
   - Publiez la topologie. Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.** Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.
    
   - Ouvrez SQL Server Management Studio, puis accédez au ag. Le faire échouer vers un réplica secondaire.
    
   - Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Déployer un groupe de disponibilité Always On sur un pool existant qui utilise la mise en miroir de bases de données
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si le pool que vous misez à niveau vers une ag ag héberge le magasin central de gestion de votre organisation, vous devez d’abord déplacer le cms vers un autre pool avant de mettre à niveau ce pool. Utilisez lMove-CsManagementServer cmdlet pour déplacer le pool. Si vous n’avez pas d’autre pool dans votre organisation, vous pouvez déployer temporairement un serveur Édition Standard et déplacer le cmS vers ce serveur avant de mettre à niveau votre pool vers le groupe de sécurité d’entreprise. 
  
1. Pour faire échouer toutes les données du miroir vers le nœud principal, ouvrent Skype Entreprise Server Management Shell et tapent l’cmdlet suivante.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Répétez cette cmdlet pour chaque type de base de données dans le pool. Vous pouvez utiliser l’cmdlet suivante pour rechercher tous les types de base de données stockés dans ce pool.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Utilisez le Générateur de topologie pour supprimer la mise en miroir de base de données du pool.
    
   - Ouvrez le Générateur de topologie. Dans votre topologie, développez **Êdition Entreprise pools** frontux, cliquez avec le bouton droit sur le nom du pool, puis cliquez sur **Modifier les propriétés.**
    
   - Pour chaque type de SQL dans le pool, activez la case à **cocher Activer SQL la** mise en miroir du Store.
    
3. Publiez la topologie modifiée. Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.** Ensuite, dans la page de confirmation, cliquez sur **Suivant**
    
4. Utilisez SQL Server Management Studio pour rompre le miroir.
    
   - Ouvrez SQL Server Management Studio, accédez à vos bases de données, cliquez avec le bouton droit sur **Tâches** et cliquez sur **Miroir.** Cliquez ensuite **sur Supprimer la mise en** miroir et sur **OK.**
    
   - Répétez cette phase pour toutes les bases de données du pool qui seront converties en ag.
    
5. Configurer la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG. Sur chaque serveur, faites les étapes suivantes :
    
   - Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**
    
   - Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.** Ici, cochez la case **Clustering deover.**
    
   - Dans la **zone Ajouter des fonctionnalités requises** pour le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**
    
   - Cliquez sur **Installer**.
    
6. Validez la configuration du cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**
    
   - Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**
    
   - Sur la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**
    
   - Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale. Cliquez ensuite **sur Terminer** pour terminer la validation.
    
     L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé. Vous n’êtes pas obligé d’utiliser le stockage partagé. Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.
    
7. Créez le cluster de Windows serveur.
    
   - Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**
    
   - Sur la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Ajoutez le nom du cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.
    
   - Sur la page Confirmation, cliquez sur **Suivant**.
    
   - Une fois le cluster créé, cliquez sur **Terminer.**
    
8. Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers. Pour ce faire, utilisez les étapes suivantes :
    
   - Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur Configurer le **quorum du cluster Paramètres**.
    
   - Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**
    
   - Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**
    
   - Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.
    
   - Sur la page **Confirmation**, cliquez sur **Suivant**.
    
9. Sur chaque serveur du cluster, activez la fonctionnalité AG dans Gestionnaire de configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service. 
    
   - Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez **la case à cocher Activer les groupes de disponibilité AlwaysOn.** Redémarrez le service SQL Server lorsque vous y invitez.
    
10. Créez le groupe de disponibilité.
    
    - Ouvrez SQL Server Management Studio et connectez-vous à l’SQL Server instance.
    
    - Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.** Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**
    
    - Si la page **Introduction** s’affiche, cliquez sur **Suivant.**
    
    - Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
    - Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le groupe de disponibilité AlwaysOn. Cliquez ensuite sur **Next (Suivant)**.
    
    N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou Persistent Chat dans le groupe de disponibilité AlwaysOn, car elles ne sont pas pris en charge dans ce scénario. Vous pouvez inclure toutes les autres bases Skype Entreprise Server de données dans le groupe de disponibilité AlwaysOn.
    
    - Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances de SQL que vous avez jointes en tant que Windows cluster de bas niveau de serveur.
    
    - Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.** Ne sélectionnez pas **l’option Secondaire lisible.**
    
    - Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.
    
      - Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité. Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
    - Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**
    
    - Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture. Cliquez ensuite sur **Next (Suivant)**.
    
    Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données. Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.
    
    - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
    - Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.
    
11. Créez un magasin spécifiant l’auditeur AG et en spécifiant le principal de l’ancien miroir comme nœud principal de l’AG.
    
    - Ouvrez le Générateur de topologie. Dans votre topologie, développez **Composants partagés,** cliquez avec le bouton **droit sur SQL Server Store,** puis cliquez sur Nouveau **SQL Server Store.**
    
    - Dans la page Définir un nouveau **magasin SQL,** activez d’abord la case à cocher Haute disponibilité **Paramètres,** puis assurez-vous que les groupes de disponibilité AlwaysOn SQL apparaissent dans la zone de la zone de mise à jour.
    
    - Dans la **SQL Server FQDN** de l’écouteur de disponibilité, tapez le FQDN de l’écoute que vous avez créé lorsque vous avez créé le groupe de disponibilité.
    
    - Dans la **SQL Server FQDN,** tapez le FQDN du nœud principal de l’ag, puis cliquez sur **OK**. Il doit s’y prendre comme principal de l’ancien miroir pour ce magasin.
    
12. Associez la nouvelle AG au pool frontal.
    
    - Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool à associer à l’AG, puis cliquez **sur Modifier les propriétés.**
    
    - Sous **Associations,** dans la **SQL Server Store,** sélectionnez l’AG. Sélectionnez le même groupe pour toutes les autres bases de données du pool que vous souhaitez déplacer vers le ag.
    
    - Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies sur la ag ag, cliquez sur **OK**.
    
13. Publiez la topologie. Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.** Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
14. Effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de disponibilité AlwaysOn.
    
    - Ouvrez le Générateur de topologie, **sélectionnez Télécharger la topologie** à partir d’un déploiement existant, puis cliquez sur **OK.**
    
    - Développez Skype Entreprise Server, développez votre topologie et développez **SQL Server Stores.** Cliquez avec le bouton droit SQL magasin de la nouvelle ag, puis cliquez **sur Modifier les propriétés.**
    
    - En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe du listener de l’AG.
    
    - Publiez la topologie. Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.** Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.
    
    - Ouvrez SQL Server Management Studio, puis accédez au ag. Le faire échouer vers un réplica secondaire.
    
    - Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Déployer un groupe de disponibilité Always On sur un pool existant qui n’utilise pas la mise en miroir de bases de données
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Si le pool que vous misez à niveau vers une ag ag héberge le magasin central de gestion de votre organisation, vous devez d’abord déplacer le cms vers un autre pool avant de mettre à niveau ce pool. Utilisez lMove-CsManagementServer cmdlet pour déplacer le pool. Si vous n’avez pas d’autre pool dans votre organisation, vous pouvez déployer temporairement un serveur Édition Standard et déplacer le cmS vers ce serveur avant de mettre à niveau votre pool vers le groupe de sécurité d’entreprise. 
  
1. Configurer la fonctionnalité clustering de failover sur tous les serveurs de base de données qui feront partie de l’AG. Sur chaque serveur, faites les étapes suivantes :
    
   - Ouvrez le Gestionnaire de serveur et cliquez **sur Ajouter des rôles et des fonctionnalités.**
    
   - Cliquez **sur Suivant** jusqu’à atteindre la zone Sélectionner les **fonctionnalités.** Ici, cochez la case **Clustering deover.**
    
   - Dans la **zone Ajouter des fonctionnalités requises** pour le clustering de failover, cliquez sur Ajouter des **fonctionnalités.**
    
   - Cliquez sur **Installer**.
    
2. Validez la configuration du cluster.
    
   - Dans le Gestionnaire de serveur, cliquez sur le menu **Outils,** puis cliquez sur Gestionnaire **du cluster de failover.**
    
   - Sous **Actions** sur le côté droit de l’écran, cliquez **sur Valider la configuration.**
    
   - Sur la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Sélectionnez les serveurs à ajouter au cluster, puis cliquez sur **Exécuter tous les tests.**
    
   - Dans la **zone Résumé,** vérifiez les erreurs que l’Assistant signale. Cliquez ensuite **sur Terminer** pour terminer la validation.
    
     L’Assistant signalera probablement plusieurs avertissements, en particulier si vous n’utilisez pas de stockage partagé. Vous n’êtes pas obligé d’utiliser le stockage partagé. Toutefois, si  vous voyez des messages d’erreur, vous devez résoudre ces problèmes avant de continuer.
    
3. Créez le cluster Windows server failover cluster (WSFC).
    
   - Dans **l’Assistant Gestion du cluster de failover,** cliquez avec le bouton droit sur Gestion du cluster de **failover,** puis cliquez **sur Créer un cluster.**
    
   - Sur la page **Avant de commencer**, cliquez sur **Suivant**.
    
   - Ajoutez le nom du cluster et l’adresse IP. Lorsque les paramètres sont validés, cliquez sur **Suivant**.
    
   - Sur la page Confirmation, cliquez sur **Suivant**.
    
   - Une fois le cluster créé, cliquez sur **Terminer.**
    
4. Nous vous recommandons de configurer les paramètres de quorum de cluster pour utiliser un témoin de partage de fichiers. Pour ce faire, utilisez les étapes suivantes :
    
   - Cliquez avec le bouton droit sur le nom du cluster, cliquez sur **Autres actions,** puis cliquez sur Configurer le **quorum du cluster Paramètres**.
    
   - Dans la page **Sélectionner l’option de configuration du quorum,** cliquez sur Sélectionner le témoin de **quorum.**
    
   - Dans la page **Sélectionner un témoin de quorum,** cliquez sur Configurer un témoin de partage de **fichiers.**
    
   - Dans la page **Configurer le témoin de partage** de fichiers, tapez le chemin d’accès du partage de fichiers que vous souhaitez utiliser, puis cliquez sur **Suivant**.
    
   - Sur la page **Confirmation**, cliquez sur **Suivant**.
    
5. Sur chaque serveur du cluster, activez AG dans Gestionnaire de configuration SQL Server.
    
   - Ouvrez le Gestionnaire de configuration SQL Server. Dans l’arborescence sur le côté gauche de l’écran, cliquez sur **SQL Server Services,** puis double-cliquez sur SQL Server service. 
    
   - Dans la **zone Propriétés,** sélectionnez **l’onglet Haute disponibilité AlwaysOn.** Activez **la case à cocher Activer les groupes de disponibilité AlwaysOn.** Redémarrez le service SQL Server lorsque vous y invitez.
    
6. Créez le groupe de disponibilité.
    
   - Ouvrez SQL Server Management Studio et connectez-vous à l’SQL Server instance.
    
   - Dans l’Explorateur d’objets, développez **le dossier Haute disponibilité Always On.** Cliquez avec le bouton droit **sur le dossier Groupes de** disponibilité, puis cliquez sur Assistant Nouveau groupe de **disponibilité.**
    
   - Si la page **Introduction** s’affiche, cliquez sur **Suivant.**
    
   - Dans la page **Spécifier le nom du** groupe de disponibilité, tapez le nom du groupe de disponibilité, puis cliquez sur **Suivant**.
    
   - Dans la page Sélectionner des bases de données, sélectionnez les bases de données que vous souhaitez inclure dans le ag. Cliquez ensuite sur **Next (Suivant)**.
    
     N’incluez pas les bases de données **ReportServer,** **ReportServerTempDB** ou De conversation permanente dans la ag, car celles-ci ne sont pas pris en charge dans ce scénario. Vous pouvez inclure toutes les autres bases de données Skype Entreprise Server données dans le ag.
    
   - Dans la page **Spécifier les réplicas,** cliquez sur **l’onglet Réplicas.** Cliquez ensuite sur le bouton Ajouter des **réplicas,** puis connectez-vous aux autres instances SQL que vous avez jointes en tant que nodes de WSFC.
    
   - Pour chaque instance, sélectionnez les options **Deover automatique et** **Validation synchrone.** Ne sélectionnez pas **l’option Secondaire lisible.**
    
   - Cliquez sur **l’onglet Points de terminaison** et vérifiez que le **numéro de port** est 5022.
    
   - Cliquez sur **l’onglet d’écoute,** puis sélectionnez l’option Créer **un listener de** groupe de disponibilité. Sous cette option, tapez un nom pour l’port d’écoute et définissez le **port** sur 1433 (les autres ports ne sont pas pris en charge pour cette option).
    
   - Cliquez **sur** Ajouter, puis dans la zone **Adresse IPv4,** fournissez votre adresse IP virtuelle préférée, puis cliquez sur **OK.**
    
   - Dans la **page** Sélectionner la synchronisation initiale des données, sélectionnez Complète et spécifiez un dossier accessible aux réplicas et pour qui le compte de service SQL Server utilisé par les deux réplicas dispose d’autorisations d’écriture. Cliquez ensuite sur **Next (Suivant)**.
    
     Ce partage de fichiers sera utilisé temporairement lors de l’initialisation des bases de données. Si vous avez affaire à des bases de données de grande taille, nous vous recommandons de les initialiser manuellement si votre bande passante réseau ne peut pas prendre en charge la taille des sauvegardes de base de données.
    
     - Dans la page Validation, vérifiez que toutes les vérifications de validation sont réussies, puis cliquez sur **Suivant**.
    
   - Dans la page **Résumé,** vérifiez tous les paramètres et cliquez sur Terminer.
    
7. Créez un magasin spécifiant l’écoute AG.
    
   - Ouvrez le Générateur de topologie. Dans votre topologie, développez **Composants partagés,** cliquez avec le bouton **droit sur SQL Server Store,** puis cliquez sur Nouveau **SQL Server Store.**
    
   - Dans la page Définir un nouveau **magasin SQL,** activez d’abord la case à cocher Haute disponibilité **Paramètres,** puis assurez-vous que les groupes de disponibilité AlwaysOn SQL apparaissent dans la zone de la zone de mise à jour.
    
   - Dans la **SQL Server FQDN** de l’écouteur de disponibilité, tapez le FQDN de l’écoute que vous avez créé lorsque vous avez créé le groupe de disponibilité.
    
   - Dans la **SQL Server FQDN,** tapez le FQDN du nœud principal de l’ag, puis cliquez sur **OK**.
    
8. Associez le nouveau groupe de disponibilité Always On au pool frontal.
    
   - Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool à associer à l’AG, puis cliquez **sur Modifier les propriétés.**
    
   - Sous **Associations,** dans la **SQL Server Store,** sélectionnez l’AG. Sélectionnez le même groupe pour toutes les autres bases de données du pool que vous souhaitez déplacer vers le ag.
    
   - Lorsque vous êtes sûr que toutes les bases de données nécessaires sont définies sur la ag ag, cliquez sur **OK**.
    
9. Publiez la topologie. Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.** Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
10. Effectuez quelques étapes finales pour vous assurer que les connexions SQL sont sur chacun des réplicas du groupe de l’ag.
    
    - Ouvrez le Générateur de topologie, **sélectionnez Télécharger la topologie** à partir d’un déploiement existant, puis cliquez sur **OK.**
    
    - Développez Skype Entreprise Server, développez votre topologie et développez **SQL Server Stores.** Cliquez avec le bouton droit SQL magasin de la nouvelle ag, puis cliquez **sur Modifier les propriétés.**
    
    - En bas de la page, dans la zone **SQL Server FQDN,** modifiez la valeur en nom de nom de groupe du listener de l’AG.
    
    - Publiez la topologie. Dans le menu **Action,** cliquez **sur Topologie,** puis **publiez.** Ensuite, dans la page de confirmation, cliquez sur **Suivant**. Patientez ensuite quelques minutes pour que la nouvelle topologie soit répliquée.
    
    - Ouvrez SQL Server Management Studio, puis accédez au ag. Le faire échouer vers un réplica secondaire.
    
    - Ouvrez Skype Entreprise Server Management Shell et tapez l’cmdlet suivante pour créer SQL connexions sur ce réplica :
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Répétez les deux étapes précédentes (faire échouer le groupe vers un réplica secondaire, puis  `Install-CsDatabase -Update` utilisez) pour chaque réplica du groupe.
