---
title: Mise à niveau vers Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Résumé : Découvrez comment effectuer une mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015.'
ms.openlocfilehash: 30cd73e8c21c9ee60521e1c2bddf8bddf4d23b6f
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860565"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Mise à niveau vers Skype Entreprise Server 2015
 
**Résumé:** Découvrez comment effectuer une mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015. 
  
Utilisez les procédures de ce document pour effectuer une mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015 à l’aide du générateur de topologie Skype Entreprise Server et de la nouvelle fonctionnalité de mise à niveau In-Place. Si vous souhaitez effectuer une mise à niveau à partir de Lync Server 2010 ou Office Communications Server 2007 R2, consultez [Plan to upgrade to Skype Entreprise Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> Les mises à niveau sur place étaient disponibles en Skype Entreprise Server 2015, mais elles ne sont plus prises en charge dans Skype Entreprise Server 2019. La coexistence côte à côte est prise en charge, consultez [Migration vers Skype Entreprise Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.
  
## <a name="upgrade-from-lync-server-2013"></a>Mise à niveau à partir de Lync Server 2013

La mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015 implique l’installation des logiciels requis, l’utilisation du générateur de topologie Skype Entreprise Server pour mettre à niveau les bases de données dans le pool et l’utilisation de la mise à niveau Skype Entreprise Server In-Place sur chacun des serveurs associés au pool. Pour terminer la mise à niveau, suivez les huit étapes décrites dans cette rubrique.
  
### <a name="before-you-begin"></a>Avant de commencer

- Passez [en revue le plan de mise à niveau vers Skype Entreprise Server 2015](../plan-your-deployment/upgrade.md).
    
- Passez [en revue les exigences du serveur pour Skype Entreprise Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installer les prérequis pour Skype Entreprise Server 2015](install/install-prerequisites.md) .
    
- [Installer Skype Entreprise Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Étape 1 : Installer les outils d’administrateur et télécharger la topologie

1. Connecter à l’ordinateur de la topologie qui n’a pas Lync OCSCore ou d’autres composants Lync installés.
    
2. À partir du support d’installation de Skype Entreprise Server 2015, exécutez **Setup.exe** à partir de **OCS_Volume\Setup\AMD64**. 
    
3. Cliquez sur **Installer**. 
    
4. Permet d'accepter le contrat de licence.
    
5. Dans l’Assistant Déploiement, cliquez sur **Installer les outils Administrateur**, puis suivez les étapes d’installation.
    
     ![Capture d’écran de l’Assistant Déploiement avec le lien vers les outils d’administration d’installation mis en évidence.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. À partir du Windows écran d'accueil, ouvrez Skype Entreprise Server Générateur de topologie.
    
7. Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis sur **Suivant**.
    
8. Entrez un nom pour la topologie, puis cliquez sur **Enregistrer**.
    
9. Accédez à l’emplacement où vous avez enregistré la topologie et effectuez une copie de la topologie.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Étape 2 : Mettre à niveau et publier la topologie à l’aide du Générateur de topologie

Avant de commencer le processus de mise à niveau, tous les services doivent être en cours d’exécution pour les pools que vous prévoyez de mettre à niveau. Ainsi, les modifications de topologie seront répliquées dans la base de données locale des serveurs du pool.
  
> [!IMPORTANT]
>  Enregistrez une copie de votre fichier de topologie avant la mise à niveau. Après la mise à niveau, vous ne pourrez pas rétrograder la topologie.> Si vos services se trouvent sur les mêmes serveurs que vos bases de données, comme le service de conversation permanente se trouve sur le même serveur que la base de données de conversation permanente, ignorez cette étape et passez à l’étape 4. Après avoir arrêté les services, exécutez le programme d’installation de la mise à niveau In-Place sur chaque serveur pour mettre à niveau les bases de données locales.
  
> [!NOTE]
> Si la topologie a une base de données principale mise en miroir, les bases de données principal et mise en miroir s’affichent **lorsque vous publiez la topologie à l’aide** du Générateur de topologie. Assurez-vous que toutes les bases de données s’exécutent sur le principal et sélectionnez uniquement le principal, et non le miroir, lors de la publication de la topologie, sinon vous verrez un avertissement après la publication de la topologie.
  
Choisissez l’une des options ci-dessous pour mettre à niveau et publier une nouvelle topologie à l’aide du générateur de topologie Skype Entreprise Server 2015. Après avoir effectué les étapes et publié la topologie mise à jour, passez à l’étape 3 de cette rubrique.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Option 1 : Mettre à niveau un pool frontal isolé et les magasins d’archivage et de surveillance associés

Si le pool que vous mettez à niveau a une dépendance de magasin d’archivage et de surveillance, lorsque vous effectuez les étapes suivantes, le magasin d’archivage et de surveillance est également mis à niveau.
  
1. Dans le Générateur de topologie, cliquez avec le bouton droit sur un pool Lync Server 2013, sélectionnez **Mettre à niveau vers Skype Entreprise Server 2015**, puis suivez les étapes. 
    
     ![Capture d’écran du menu contextuel avec l’option de mise à niveau pour Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. Dans le Générateur de topologie, cliquez sur **Publication d’action** > **topologie** ou **Publication** de **la topologie** >  **d’action** > . 
    
     ![Capture d’écran du menu Action avec l’option Publier la topologie dans le Générateur de topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Lors de la publication, choisissez d’installer une base de données sur le magasin d’archivage et de surveillance.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Option 2 : Mettre à niveau le pool frontal sans mettre à niveau les magasins d’archivage et de surveillance

Si vous effectuez les étapes suivantes, l’archivage et la surveillance du pool sélectionné sont désactivés. Le pool n’aura pas de magasins d’archivage et de surveillance après la mise à niveau.
  
1. Dans le Générateur de topologie, sélectionnez le pool Lync Server 2013 que vous souhaitez mettre à niveau.
    
2. Supprimez la dépendance aux magasins d’archivage et de surveillance Lync Server 2013. 
    
   - Accédez aux **propriétés** **Action** >  Edit.
    
   - Décochez la case **d’archivage** .
    
     ![Capture d’écran de la case à cocher Archivage dans la boîte de dialogue Modifier les propriétés.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Désactivez la case à cocher **Surveillance** .
    
     ![Capture d’écran de la boîte de dialogue Modifier les propriétés qui affiche la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Cliquez avec le bouton droit sur le pool Lync Server 2013, sélectionnez **Mettre à niveau vers Skype Entreprise Server 2015**, puis suivez les étapes. 
    
     ![Capture d’écran du menu contextuel avec l’option de mise à niveau pour Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Dans le Générateur de topologie, cliquez sur **Publication d’action** > **topologie** ou **Publication** de **la topologie** >  **d’action** > . 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Option 3 : Mettre à niveau le pool frontal et l’associer à de nouveaux magasins d’archivage et de surveillance Skype Entreprise Server 2015

Si vous effectuez les étapes suivantes, l’archivage et la surveillance s’arrêtent dans le magasin précédent et démarrent dans le nouveau magasin que vous avez créé. 
  
1. Dans le Générateur de topologie, sélectionnez le pool Lync Server 2013 que vous souhaitez mettre à niveau. 
    
2. Supprimez la dépendance aux magasins d’archivage et de surveillance Lync Server 2013. 
    
   - Accédez aux **propriétés** **Action** >  Edit.
    
   - Décochez la case **d’archivage** .
    
     ![Capture d’écran de la case à cocher Archivage dans la boîte de dialogue Modifier les propriétés.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Désactivez la case à cocher **Surveillance** .
    
     ![Capture d’écran de la boîte de dialogue Modifier les propriétés qui affiche la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Cliquez avec le bouton droit sur le pool Lync Server 2013, sélectionnez **Mettre à niveau vers Skype Entreprise Server 2015**, puis suivez les étapes. 
    
     ![Capture d’écran du menu contextuel avec l’option de mise à niveau pour Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Créez un magasin SQL pour l’archivage. 
    
   - Sélectionnez les **propriétés** pool et **Action** >  Edit. 
    
   -  Activez la case à cocher **Archivage**.
    
   - Cliquez sur **Nouveau**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les propriétés qui affiche le bouton Nouveau sous la section Archivage.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Créez un magasin SQL pour la surveillance. 
    
   - Sélectionnez les **propriétés** pool et **Action** >  Edit. 
    
   -  Activez la case à cocher **Surveillance** .
    
   - Cliquez sur **Nouveau**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les propriétés qui affiche le bouton Nouveau sous la section Surveillance.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. Dans le Générateur de topologie, cliquez sur **Publication d’action** > **topologie** ou **Publication** de **la topologie** >  **d’action** > . 
    
7. Lors de la publication, choisissez d’installer la base de données sur le nouveau magasin d’archivage et de surveillance.
    
### <a name="step-3-wait-for-replication"></a>Étape 3 : Attendre la réplication

Donnez un certain temps à la réplication pour publier la topologie mise à jour sur tous les serveurs de l’environnement.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Étape 4 : Arrêter tous les services du pool à mettre à niveau

Sur chaque serveur qui entretient le pool que vous allez mettre à niveau, exécutez l’applet de commande suivante dans PowerShell :
  
```powershell
Disable-CsComputer -Scorch
```

Nous vous recommandons d’utiliser Disable-CsComputer, car vous devrez peut-être redémarrer le serveur pendant le processus de mise à niveau In-Place. Si vous utilisez Stop-CsWindowsService, certains services peuvent redémarrer automatiquement après un redémarrage. Cela peut entraîner l’échec de la mise à niveau In-Place.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Étape 5 : Mettre à niveau des pools frontaux et des serveurs de pool non frontaux

> [!NOTE]
>  Avant de procéder à la mise à niveau, installez toutes les nouvelles conditions préalables requises pour Skype Entreprise Server 2015, notamment : > au moins 32 Go d’espace libre avant de tenter une mise à niveau. En outre, assurez-vous que le lecteur est un lecteur local fixe, n’est pas connecté par USB ou Firewire, est mis en forme avec le système de fichiers NTFS, n’est pas compressé et ne contient pas de fichier de page.> PowerShell version 6.2.9200.0 ou ultérieure.> La dernière mise à jour cumulative Lync Server 2013 installée.> SQL Server 2012 SP1 installée.> La base de connaissances suivante est installée (installée automatiquement si vous utilisez Microsoft Update) : > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
Utilisez la mise à niveau In-Place sur chaque serveur pour mettre à jour le pool frontal, le pool Edge, le serveur de médiation et le pool de conversation permanente.
  
1. Sur chaque serveur, exécutez **Setup.exe** à partir de **OCS_Volume\Setup\amd64** sur le support d’installation Skype Entreprise Server 2015.
    
2. Acceptez le contrat de licence et suivez les invites pour la mise à niveau In-Place.
    
3. Répétez ces étapes pour chaque serveur du pool frontal et sur chaque serveur de pool non frontal.
    
> [!NOTE]
> Vous pouvez être invité à redémarrer le serveur pendant la mise à niveau In-Place. C'est d'accord. Après le redémarrage, la mise à niveau In-Place se poursuit à partir de l’endroit où elle s’est terminée. 
  
Une fois la mise à niveau In-Place terminée, le message suivant s’affiche.
  
![Capture d’écran montrant la mise à niveau sur place terminée avec succès.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Étape 6 : Redémarrer les services sur tous les serveurs mis à niveau

> [!NOTE]
> Avant de redémarrer les services, assurez-vous que %ProgramData%\WindowsFabric n’existe pas sur tous les serveurs frontaux. S’il existe, supprimez-le avant de démarrer les services. 
  
- Une fois que vous avez mis à niveau tous les serveurs du pool frontal, redémarrez les services à l’aide de la commande PowerShell suivante : 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > S’il existe déjà un redémarrage système en attente nécessaire avant de commencer à exécuter In-Place Mise à niveau, In-Place mise à niveau ne vous demande pas de redémarrer à la fin de l’installation. Certaines exceptions d’assembly sont levées sur le premier serveur frontal lorsque vous essayez de démarrer des services à l’aide de l’applet de commande Start-CSPool. Pour résoudre ces erreurs, redémarrez tous les serveurs du pool et exécutez à nouveau l’applet de commande. 
  
- Sur les serveurs de pool non frontaux, redémarrez les services à l’aide de la commande suivante :
    
  ```powershell
  Start-CsWindowsService
  ```

Une fois que vous avez cliqué sur **OK** sur la page In-Place Mise à niveau, vous verrez le rappel suivant pour effectuer cette étape.
  
![Capture d’écran montrant les étapes suivantes une fois la mise à niveau sur place terminée.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Étape 7 : Vérifier que la fonctionnalité Skype Entreprise fonctionne

Pour vous assurer que la mise à niveau a réussi, pour le pool qui a été mis à niveau, testez Skype Entreprise pour vous assurer que la fonctionnalité fonctionne comme prévu. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Étape 8 : Mettre à niveau des pools secondaires

Répétez les étapes décrites dans cette rubrique pour mettre à niveau tous les pools supplémentaires que vous avez dans votre environnement.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Résoudre les problèmes liés à la mise à niveau In-Place

Si la mise à niveau In-Place échoue, vous pouvez voir un message similaire à ce qui se trouve dans l’image suivante. 
  
![Capture d’écran montrant l’échec de la mise à niveau sur place, car aucune mise à jour cumulative requise n’est installée.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Passez en revue le message complet en bas de la page pour vous aider à résoudre le problème. Cliquez sur **Afficher les journaux** pour obtenir plus de détails.
  
Si la mise à niveau In-Place échoue lors de la **vérification de la préparation de la mise à niveau** ou de l’installation **des prérequis manquants**, assurez-vous que toutes les dernières mises à jour Windows Server, Lync Server et SQL Server sont appliquées et que tous les logiciels et rôles nécessaires sont installés. Pour obtenir la liste des éléments requis, consultez [la configuration requise pour Skype Entreprise Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et [les prérequis d’installation pour Skype Entreprise Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Voir aussi

[Planifier la mise à niveau vers Skype Entreprise Server 2015](../plan-your-deployment/upgrade.md)
  
[Configuration requise pour Skype Entreprise Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installer les prérequis pour Skype Entreprise Server 2015](install/install-prerequisites.md)
  
[Installer Skype Entreprise Server 2015](install/install.md)
