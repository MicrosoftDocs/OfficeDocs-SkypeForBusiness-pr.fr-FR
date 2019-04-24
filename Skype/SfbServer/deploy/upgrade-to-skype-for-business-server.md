---
title: Mise à niveau vers Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Résumé : Découvrez comment mettre à niveau à partir de Lync Server 2013 Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 0a09de79bd60917667dfb2e7ca33310da3b04ddd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211634"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Upgrade to Skype for Business Server 2015
 
**Résumé :** Découvrez comment mettre à niveau à partir de Lync Server 2013 Skype pour Business Server 2015. Téléchargez une version d’évaluation gratuite de Skype pour Business Server 2015 à partir du [Centre d’évaluation de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Mise à niveau à partir de Lync Server 2013 vers Skype pour Business Server 2015 à l’aide de la Skype pour le Générateur de topologie Business Server et la nouvelle fonctionnalité de mise à niveau sur Place, utilisez les procédures décrites dans ce document. Si vous souhaitez mettre à niveau à partir de Lync Server 2010 ou Office Communications Server 2007 R2, voir [planifier la mise à niveau vers Skype pour Business Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> Mises à niveau sur place étaient disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Côte à côte coexistence est pris en charge, consultez [Migration vers Skype pour Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.
  
## <a name="upgrade-from-lync-server-2013"></a>Mise à niveau à partir de Lync Server 2013

Mise à niveau de Lync Server 2013 pour Skype pour Business Server 2015 implique l’installation de logiciels, à l’aide de la Skype pour le Générateur de topologie Business Server mise à niveau des bases de données dans le pool et à l’aide de la Skype pour Business Server In-Place Upgrade sur chaque serveur de la associé au pool de serveurs. Pour effectuer la mise à niveau, parcourez les huit étapes dans cette rubrique.
  
### <a name="before-you-begin"></a>Avant de commencer

- Reportez-vous à [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Passez en revue la [configuration serveur requise pour Skype pour Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installer les composants requis pour Skype pour Business Server 2015](install/install-prerequisites.md) .
    
- [Installer Skype pour Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Étape 1 : Installer les outils d’administrateur et télécharger la topologie

1. Connectez-vous à l’ordinateur dans la topologie qui n’a pas de Lync OCSCore ou tous les autres composants Lync installés.
    
2. À partir de Skype pour le support d’installation Business Server 2015, exécutez **Setup.exe** à partir de **OCS_Volume\Setup\AMD64**. 
    
3. Cliquez sur **Installer**. 
    
4. Acceptez les termes du contrat de licence.
    
5. Dans l’Assistant Déploiement, cliquez sur **Installer les outils d’administrateur**, puis suivez les étapes d’installation.
    
     ![Capture d’écran de l’Assistant Déploiement avec lien Installer les outils d’administrateur.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. À partir de l’écran de démarrage de Windows, ouvrez Skype pour le Générateur de topologie du serveur Business.
    
7. Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis sur **Suivant**.
    
8. Entrez un nom pour la topologie, puis cliquez sur **Enregistrer**.
    
9. Accédez à l’emplacement où vous avez enregistré la topologie, puis effectuez une copie de la topologie.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Étape 2 : mise à niveau et publication de la topologie à l’aide du Générateur de topologie

Avant de commencer le processus de mise à niveau, tous les services doivent être en cours d’exécution pour les pools que vous envisagez de mettre à niveau. Les changements de la topologie pourront ainsi être répliqués dans la base de données locale des serveurs dans le pool.
  
> [!IMPORTANT]
>  Enregistrez une copie de votre fichier de topologie avant la mise à niveau. Une fois que vous mettez à niveau, vous ne serez pas en mesure de rétrograder le topology.> si vos services se trouvent sur les mêmes serveurs que vos bases de données, telles que la conversation permanente service est sur le même serveur que la base de données de conversation permanente, ignorez cette étape et passez à l’étape 4. Après avoir arrêté les services, exécutez le programme de mise à niveau sur place sur chaque serveur pour effectuer la mise à niveau vers les bases de données locales.
  
> [!NOTE]
> Si la topologie comporte une base de données principale mise en miroir, les bases de données principale et en miroir s’affichent **lorsque vous publiez la topologie** à l’aide du générateur de topologie. Vérifiez que toutes les bases de données sont exécutées dans la base de données principale et veillez à sélectionner la base de données principale et non la base de données miroir lors de la publication de la topologie, autrement un avertissement s’affichera après la publication de la topologie.
  
Choisissez une des options ci-dessous pour mettre à niveau et publier une nouvelle topologie à l’aide de la Skype pour le Générateur de topologie Business Server 2015. Après avoir effectué ces étapes et publié la topologie mise à jour, passez à l’Étape 3 de cette rubrique.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Option 1 : Mettre à niveau un pool frontal isolé et les magasins d’archivage et de surveillance associés

Si le pool que vous mettez à niveau a une dépendance des magasins d’archivage et de surveillance, quand vous utilisez les étapes suivantes, le magasin d’archivage et de surveillance est aussi mis à niveau.
  
1. Dans le Générateur de topologie avec le bouton droit à un pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype pour Business Server 2015**, suivez les étapes. 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. Dans le Générateur de topologie, cliquez sur **Action** > **publier la topologie** ou **Action** > **topologie** > **Publier**. 
    
     ![Capture d’écran du menu Action avec l’option Publier la topologie dans le Générateur de topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Au cours de la publication, choisissez d’installer une base de données dans le magasin d’archivage et de surveillance.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Option 2 : Mise à niveau le pool frontal sans mise à niveau d’archivage et surveillance des magasins

Si vous utilisez les étapes suivantes, l’archivage et la surveillance pour le pool sélectionné sont désactivées. Le pool n’aura pas de magasins d’archivage et de surveillance après la mise à niveau.
  
1. Dans le Générateur de topologie, sélectionnez le pool Lync Server 2013 que vous souhaitez mettre à niveau.
    
2. Supprimer la dépendance pour les magasins de surveillance et d’archivage de Lync Server 2013. 
    
   - Accédez à **l’Action** > **Modifier les propriétés**.
    
   - Désactivez la case à cocher **Archivage**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Archivage.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Désactivez la case à cocher **Surveillance**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Avec le bouton droit le pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype pour Business Server 2015**, suivez les étapes. 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Dans le Générateur de topologie, cliquez sur **Action** > **publier la topologie** ou **Action** > **topologie** > **Publier**. 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Option 3 : Mise à niveau le pool frontal et l’associer à nouveau Skype pour les magasins Business Server 2015 archivage et la surveillance

Si vous utilisez les étapes suivantes, l’archivage et la surveillance s’arrêteront dans le magasin précédent et commenceront dans le nouveau magasin que vous avez créé. 
  
1. Dans le Générateur de topologie, sélectionnez le pool Lync Server 2013 que vous souhaitez mettre à niveau. 
    
2. Supprimer la dépendance pour les magasins de surveillance et d’archivage de Lync Server 2013. 
    
   - Accédez à **l’Action** > **Modifier les propriétés**.
    
   - Désactivez la case à cocher **Archivage**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Archivage.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Désactivez la case à cocher **Surveillance**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Avec le bouton droit le pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype pour Business Server 2015**, suivez les étapes. 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Créez un nouveau magasin SQL pour l’archivage. 
    
   - Sélectionnez le pool et **l’Action** > **Modifier les propriétés**. 
    
   -  Activez la case à cocher **Archivage**.
    
   - Cliquez sur **Nouveau**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres figurant le bouton Nouveau dans la section Archivage.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Créez un nouveau magasin SQL pour la surveillance. 
    
   - Sélectionnez le pool et **l’Action** > **Modifier les propriétés**. 
    
   -  Activez la case à cocher **Surveillance**.
    
   - Cliquez sur **Nouveau**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres figurant le bouton Nouveau dans la section Surveillance.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. Dans le Générateur de topologie, cliquez sur **Action** > **publier la topologie** ou **Action** > **topologie** > **Publier**. 
    
7. Au cours de la publication, choisissez d’installer la base de données dans le magasin d’archivage et de surveillance.
    
### <a name="step-3-wait-for-replication"></a>Étape 3 : Attendre la réplication

Laissez à la réplication le temps de publier la topologie mise à jour vers tous les serveurs de l’environnement.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Étape 4 : Arrêter les services dans le pool à mettre à niveau

Sur chaque serveur qui traite le pool que vous allez mettre à niveau, exécutez la cmdlet suivante dans PowerShell :
  
```
Disable-CsComputer -Scorch
```

Nous recommandons l’utilisation de Disable-CsComputer, car vous devrez peut-être redémarrer le serveur au cours du processus de mise à niveau sur Place. Si vous utilisez Stop-CsWindowsService, certains services peuvent redémarrer automatiquement après un redémarrage. Cela peut entraîner l’échec de la mise à niveau sur place.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Étape 5 : Mettre à niveau les pools frontaux et les serveurs des pools non frontaux

> [!NOTE]
>  Avant la mise à niveau installez tous les nouveaux composants requis requis pour Skype pour Business Server 2015 comprenant : > au moins 32 Go d’espace libre avant d’essayer une mise à niveau. En outre, assurez-vous que le lecteur est un lecteur local fixe, n’est pas connecté par USB ou Firewire, est mis en forme avec le système de fichiers NTFS, n’est pas compressé et ne possède pas de page file.> PowerShell version 6.2.9200.0 ou ultérieure .> la plus récente de Lync Server 2013 Mise à jour cumulative installée .> SQL Server 2012 SP1 installé .> installé la base de connaissances suivants (installé automatiquement si vous utilisez Microsoft Update) : > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
Utilisez la mise à niveau sur Place sur chaque serveur à mettre à jour le pool frontal, pool de serveurs Edge, serveur de médiation et le pool de conversation permanente.
  
1. Sur chaque serveur, exécutez **Setup.exe** à partir de **OCS_Volume\Setup\amd64** sur le Skype pour le support d’installation Business Server 2015.
    
2. Acceptez le contrat de licence, puis suivez les instructions pour la mise à niveau sur Place.
    
3. Répétez ces étapes pour chaque serveur dans le pool frontal et sur chaque serveur du pool Front-End.
    
> [!NOTE]
> Vous pouvez être invité à redémarrer le serveur au cours de la mise à niveau sur Place. C'est d'accord. Après le redémarrage, la In-Place Upgrade continuera à partir de l’endroit. 
  
Lorsque la mise à niveau sur place réussit, le message suivant s’affiche.
  
![Capture d’écran montrant que la mise à niveau sur place a réussi.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Étape 6 : Redémarrer les services sur tous les serveurs mis à niveau

> [!NOTE]
> Avant de redémarrer les services, vérifiez que %ProgramData%\WindowsFabric n’existe pas sur tous les serveurs frontaux. S’il existe, supprimez-le avant de démarrer les services. 
  
- Une fois que vous avez mis à niveau tous les serveurs du pool frontal, redémarrez les services à l’aide de la commande PowerShell suivante : 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > Si un redémarrage système déjà en attente est nécessaire avant le lancement d’une procédure de mise à niveau sur place, la mise à niveau sur place ne vous demandera alors pas de redémarrer à la fin de l’installation. Des exceptions d’assembly seront alors levées concernant le premier serveur frontal lorsque vous tenterez de démarrer des services à l’aide de l’applet de commande Start-CSPool. Pour résoudre ces erreurs, redémarrez tous les serveurs du pool et réexécutez l’applet de commande. 
  
- Sur les serveurs du pool non frontal, redémarrez les services en utilisant la commande suivante :
    
  ```
  Start-CsWindowsService
  ```

Après avoir cliqué sur **OK** sur la page de mise à niveau sur place, le rappel suivant s’affiche vous invitant à compléter le reste de l’étape.
  
![Capture d’écran montrant les étapes qui suivent la mise à niveau sur place réussie.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Étape 7 : Vérification Skype pour fonctionne Business

Pour vous assurer que la mise à niveau a réussi, pour le pool qui a été mis à niveau, test Skype pour les entreprises pour vous assurer que la fonctionnalité fonctionne comme prévu. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Étape 8 : Mettre à niveau les pools secondaires

Répétez les étapes de cette rubrique pour mettre à niveau les autres pools de votre environnement.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Résoudre les problèmes de la mise à niveau sur place

Si la mise à niveau sur place échoue, un message tel que celui qui figure sur l’image suivante peut s’afficher. 
  
![Capture d’écran montrant l’échec de la mise à niveau sur place à cause de la non-installation d’une mise à jour cumulative obligatoire.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Examinez le message complet au bas de la page pour vous aider à résoudre le problème. Cliquez sur **Afficher les journaux** pour obtenir plus de détails.
  
En cas d’échec de la mise à niveau sur Place sur les **composants requis manquants installation**ou de **Préparation de mise à niveau de vérification** , assurez-vous que le serveur possède toutes les Windows Server, Lync Server et SQL Server jour appliquée et tous les logiciels requis et les rôles sont installé. Pour une liste de ce que sont les conditions requises, voir [configuration du serveur pour Skype pour Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et [installer les composants requis pour Skype pour Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Voir aussi

[Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installation des composants prérequis pour Skype Entreprise Server 2015](install/install-prerequisites.md)
  
[Installer Skype Entreprise Server 2015](install/install.md)
