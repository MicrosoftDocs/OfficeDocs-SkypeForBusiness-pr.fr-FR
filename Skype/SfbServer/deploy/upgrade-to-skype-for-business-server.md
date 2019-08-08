---
title: Mise à niveau vers Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Résumé: Découvrez comment effectuer une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015. Télécharger une version d’évaluation gratuite de Skype entreprise Server 2015 à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: c34cbc7ce1d755f093ac14bc85d78106216c450b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237447"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Upgrade to Skype for Business Server 2015
 
**Résumé:** Découvrez comment effectuer une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015. Télécharger une version d’évaluation gratuite de Skype entreprise Server 2015 à partir du [Centre d’évaluation Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Pour effectuer une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015 à l’aide du générateur de topologie Skype entreprise Server et de la nouvelle fonctionnalité de mise à niveau sur place, suivez les procédures décrites dans ce document. Si vous voulez effectuer une mise à niveau à partir de Lync Server 2010 ou d’Office Communications Server 2007 R2, voir [planifier la mise à niveau vers Skype entreprise Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> Les mises à niveau sur place étaient disponibles dans Skype entreprise Server 2015, mais ne sont plus prises en charge dans Skype entreprise Server 2019. Le coexistence côte à côte est pris en charge, reportez-vous à la rubrique [migration vers Skype entreprise Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.
  
## <a name="upgrade-from-lync-server-2013"></a>Effectuer une mise à niveau à partir de Lync Server 2013

La mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015 implique l’installation de logiciels requis, en utilisant le générateur de topologie Skype entreprise Server pour mettre à niveau des bases de données de la liste, et l’utilisation de la mise à niveau sur place de Skype entreprise Server sur chaque serveurs associés au pool. Pour procéder à la mise à niveau, passez en revue les huit étapes décrites dans cette rubrique.
  
### <a name="before-you-begin"></a>Avant de commencer

- Reportez-vous à [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Reportez-vous [à la configuration requise pour Skype entreprise server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installez la configuration requise pour Skype entreprise Server 2015](install/install-prerequisites.md) .
    
- [Installez Skype entreprise Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Étape 1 : Installer les outils d’administrateur et télécharger la topologie

1. Connectez-vous à un ordinateur dans la topologie sur laquelle Lync OCSCore ou tout autre composant Lync n’est pas installé.
    
2. À partir du support d’installation de Skype entreprise Server 2015, exécutez **Setup. exe** à partir de **OCS_Volume\Setup\AMD64**. 
    
3. Cliquez sur **Installer**. 
    
4. Acceptez les termes du contrat de licence.
    
5. Dans l’Assistant Déploiement, cliquez sur **Installer les outils d’administrateur**, puis suivez les étapes d’installation.
    
     ![Capture d’écran de l’Assistant Déploiement avec lien Installer les outils d’administrateur.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Dans l’écran de démarrage de Windows, ouvrez le générateur de topologie Skype entreprise Server.
    
7. Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis sur **Suivant**.
    
8. Entrez un nom pour la topologie, puis cliquez sur **Enregistrer**.
    
9. Accédez à l’emplacement où vous avez enregistré la topologie, puis effectuez une copie de la topologie.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Étape 2 : mise à niveau et publication de la topologie à l’aide du Générateur de topologie

Avant de démarrer le processus de mise à niveau, tous les services doivent être exécutés pour les pools que vous envisagez de mettre à niveau. Les changements de la topologie pourront ainsi être répliqués dans la base de données locale des serveurs dans le pool.
  
> [!IMPORTANT]
>  Enregistrez une copie de votre fichier de topologie avant la mise à niveau. Après la mise à niveau, vous ne serez pas en mesure d’effectuer la mise à niveau de la topologie. > si vos services se trouvent sur le même serveur que vos bases de données, comme le service de chat permanent se trouve sur le même serveur que la base de données de chat persistante, ignorez cette étape, puis passez à l’étape 4. Après avoir arrêté les services, exécutez le programme de mise à niveau sur place sur chaque serveur pour effectuer la mise à niveau vers les bases de données locales.
  
> [!NOTE]
> Si la topologie comporte une base de données principale mise en miroir, les bases de données principale et en miroir s’affichent **lorsque vous publiez la topologie** à l’aide du générateur de topologie. Vérifiez que toutes les bases de données sont exécutées dans la base de données principale et veillez à sélectionner la base de données principale et non la base de données miroir lors de la publication de la topologie, autrement un avertissement s’affichera après la publication de la topologie.
  
Sélectionnez l’une des options ci-dessous pour mettre à niveau et publier une nouvelle topologie à l’aide du générateur de topologie 2015 de Skype entreprise Server. Après avoir effectué ces étapes et publié la topologie mise à jour, passez à l’Étape 3 de cette rubrique.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Option 1 : Mettre à niveau un pool frontal isolé et les magasins d’archivage et de surveillance associés

Si le pool que vous mettez à niveau a une dépendance des magasins d’archivage et de surveillance, quand vous utilisez les étapes suivantes, le magasin d’archivage et de surveillance est aussi mis à niveau.
  
1. Dans le générateur de topologie, cliquez avec le bouton droit sur un pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype entreprise server 2015**, puis suivez les étapes. 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. Dans le générateur de topologie, cliquez sur **action** > **publier** la topologie ou la**topologie** > **** d' **action** > publier. 
    
     ![Capture d’écran du menu Action avec l’option Publier la topologie dans le Générateur de topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Au cours de la publication, choisissez d’installer une base de données dans le magasin d’archivage et de surveillance.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Option 2: mise à niveau de la liste frontale sans mise à niveau de l’archivage et de la surveillance

Si vous utilisez les étapes suivantes, l’archivage et la surveillance pour le pool sélectionné sont désactivées. Le pool n’aura pas de magasins d’archivage et de surveillance après la mise à niveau.
  
1. Dans le générateur de topologie, sélectionnez le pool Lync Server 2013 que vous voulez mettre à niveau.
    
2. Supprimez la dépendance aux magasins d’archivage et de surveillance Lync Server 2013. 
    
   - Accédez à **** > **Propriétés de modification**d’action.
    
   - Désactivez la case à cocher **Archivage**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Archivage.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Désactivez la case à cocher **Surveillance**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Cliquez avec le bouton droit sur le pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype entreprise server 2015**, puis suivez les étapes. 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Dans le générateur de topologie, cliquez sur **action** > **publier** la topologie ou la**topologie** > **** d' **action** > publier. 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Option 3: mise à niveau de la réserve frontale et associée aux nouvelles boutiques Skype entreprise Server 2015 d’archivage et de surveillance

Si vous utilisez les étapes suivantes, l’archivage et la surveillance s’arrêteront dans le magasin précédent et commenceront dans le nouveau magasin que vous avez créé. 
  
1. Dans le générateur de topologie, sélectionnez le pool Lync Server 2013 que vous voulez mettre à niveau. 
    
2. Supprimez la dépendance aux magasins d’archivage et de surveillance Lync Server 2013. 
    
   - Accédez à **** > **Propriétés de modification**d’action.
    
   - Désactivez la case à cocher **Archivage**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Archivage.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Désactivez la case à cocher **Surveillance**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres qui contient la case à cocher Surveillance.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Cliquez avec le bouton droit sur le pool Lync Server 2013, sélectionnez **mettre à niveau vers Skype entreprise server 2015**, puis suivez les étapes. 
    
     ![Capture d’écran du menu contextuel présentant l’option de mise à niveau vers Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Créez un nouveau magasin SQL pour l’archivage. 
    
   - Sélectionnez les propriétés de **** > **modification**du pool et de l’action. 
    
   -  Activez la case à cocher **Archivage**.
    
   - Cliquez sur **Nouveau**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres figurant le bouton Nouveau dans la section Archivage.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Créez un nouveau magasin SQL pour la surveillance. 
    
   - Sélectionnez les propriétés de **** > **modification**du pool et de l’action. 
    
   -  Activez la case à cocher **Surveillance**.
    
   - Cliquez sur **Nouveau**.
    
     ![Capture d’écran de la boîte de dialogue Modifier les paramètres figurant le bouton Nouveau dans la section Surveillance.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. Dans le générateur de topologie, cliquez sur **action** > **publier** la topologie ou la**topologie** > **** d' **action** > publier. 
    
7. Au cours de la publication, choisissez d’installer la base de données dans le magasin d’archivage et de surveillance.
    
### <a name="step-3-wait-for-replication"></a>Étape 3 : Attendre la réplication

Laissez à la réplication le temps de publier la topologie mise à jour vers tous les serveurs de l’environnement.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Étape 4 : Arrêter les services dans le pool à mettre à niveau

Sur chaque serveur qui dessert le pool que vous allez mettre à niveau, exécutez l’applet de commande suivante dans PowerShell:
  
```
Disable-CsComputer -Scorch
```

Nous vous recommandons d’utiliser Disable-CsComputer, car il est possible que vous deviez redémarrer le serveur pendant le processus de mise à niveau sur place. Si vous utilisez Stop-CsWindowsService, certains services peuvent redémarrer automatiquement après un redémarrage. Cela peut entraîner l’échec de la mise à niveau sur place.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Étape 5 : Mettre à niveau les pools frontaux et les serveurs des pools non frontaux

> [!NOTE]
>  Avant de procéder à la mise à niveau, procédez à l’installation de tous les nouveaux éléments requis pour Skype entreprise Server 2015 qui incluent: > au moins 32 Go d’espace libre avant d’effectuer une mise à niveau. De plus, assurez-vous que le lecteur est un lecteur local fixe, qu’il n’est pas connecté par USB ou FireWire, qu’il est mis en forme avec le système de fichiers NTFS, qu’il n’est pas compressé et qu’il ne contient pas de fichier de page. > PowerShell version 6.2.9200.0 ou ultérieure. > la dernière version de Lync Server 2013 Mise à jour cumulative installée. > SQL Server 2012 SP1 installé. > la mise à jour des Ko suivants (installée automatiquement si vous utilisez Microsoft Update): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)
  
Utilisez la mise à niveau sur place de chaque serveur pour mettre à jour la liste frontale, le pool de médiation et le serveur de médiation.
  
1. Sur chaque serveur, exécutez **Setup. exe** à partir de **OCS_Volume\Setup\amd64** sur le support d’installation de Skype entreprise Server 2015.
    
2. Acceptez le contrat de licence et suivez les invites de la mise à niveau sur place.
    
3. Répétez ces étapes pour chaque serveur dans le pool frontal et sur chacun d’eux.
    
> [!NOTE]
> Vous pouvez être invité à redémarrer le serveur pendant la mise à niveau sur place. C'est d'accord. Après le redémarrage, la mise à niveau sur place reste là là où elle s’était arrêtée. 
  
Lorsque la mise à niveau sur place réussit, le message suivant s’affiche.
  
![Capture d’écran montrant que la mise à niveau sur place a réussi.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Étape 6 : Redémarrer les services sur tous les serveurs mis à niveau

> [!NOTE]
> Avant de redémarrer les services, assurez-vous que%ProgramData%\WindowsFabric n’existe pas sur tous les serveurs frontaux. S’il existe, supprimez-le avant de démarrer les services. 
  
- Après avoir effectué la mise à niveau de tous les serveurs dans la liste frontale, redémarrez les services en utilisant la commande PowerShell suivante: 
    
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
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Étape 7: vérifier le fonctionnement de la fonctionnalité Skype entreprise

Pour vous assurer que la mise à niveau a réussi, pour le pool qui a été mis à niveau, testez Skype entreprise pour vous assurer que le fonctionnement fonctionne correctement. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Étape 8 : Mettre à niveau les pools secondaires

Répétez les étapes de cette rubrique pour mettre à niveau les autres pools de votre environnement.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Résoudre les problèmes de la mise à niveau sur place

Si la mise à niveau sur place échoue, un message tel que celui qui figure sur l’image suivante peut s’afficher. 
  
![Capture d’écran montrant l’échec de la mise à niveau sur place à cause de la non-installation d’une mise à jour cumulative obligatoire.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Examinez le message complet au bas de la page pour vous aider à résoudre le problème. Cliquez sur **Afficher les journaux** pour obtenir plus de détails.
  
Si la mise à niveau sur place échoue pour vérifier la disponibilité de la **mise à niveau** ou **l’installation des conditions préalables manquantes**, assurez-vous que le serveur comporte les mises à jour Windows Server, Lync Server et SQL Server, ainsi que tous les logiciels et rôles requis. ordinateur. Pour obtenir la liste des éléments requis, voir [Configuration requise pour Skype entreprise server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et installer la configuration requise [pour skype entreprise Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Voir aussi

[Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installation des composants prérequis pour Skype Entreprise Server 2015](install/install-prerequisites.md)
  
[Installer Skype Entreprise Server 2015](install/install.md)
