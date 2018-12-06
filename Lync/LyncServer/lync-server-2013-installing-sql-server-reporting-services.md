---
title: Installation de SQL Server Reporting Services
TOCTitle: Installation de SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204957(v=OCS.15)
ms:contentKeyID: 49297408
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation de SQL Server Reporting Services

 

_**Dernière rubrique modifiée :** 2012-06-20_

Si vous avez l’intention d’utiliser les rapports de surveillance Microsoft Lync Server 2013 (voir la section suivante de ce document pour plus d’informations), vous devez d’abord installer SQL Server Reporting Services. Vous pouvez le faire lors de l’installation de Microsoft SQL Server ou à tout moment après l’installation de SQL Server. Si vous n’avez pas installé SQL Server, suivez les instructions fournies plus haut dans cette documentation. Lorsque vous installez SQL Server, dans la page Sélection des composants, veillez à sélectionner Reporting Services pour installer SQL Server Reporting Services.

Si vous avez déjà installé SQL Server, mais que vous n’avez pas installé SQL Server Reporting Services, vous pouvez ajouter ce composant en suivant les instructions ci-après pour SQL Server 2008 R2 ou SQL Server 2012.

Pour vérifier que Reporting Services a été correctement installé, procédez comme suit :

1.  Si vous exécutez Microsoft SQL Server 2008 R2, cliquez successivement sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **Outils de configuration**, puis sur **Gestionnaire de configuration de Reporting Services**.
    
    Si vous exécutez Microsoft SQL Server 2012, cliquez successivement sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft SQL Server 2012**, sur **Outils de configuration**, puis sur **Gestionnaire de configuration de Reporting Services**.

2.  Dans la boîte de dialogue **Connexion relative à la configuration de Reporting Services**, vérifiez que le nom de votre serveur apparaît dans la zone **Nom du serveur** et que le nom de l’instance de SQL Server qui stocke vos données de surveillance apparaît dans la zone **Instance du serveur de rapports**. Cliquez sur **Connexion**.

Dans le Gestionnaire de configuration de Reporting Services, le volet État de Report Server doit indiquer que SQL Server Reporting Services est installé et que Reporting Services est en cours d’exécution : l’état Report Server doit être **Démarré** et le bouton **Démarrer** doit être grisé et non disponible. Si Reporting Services n’est pas en cours d’exécution, cliquez sur **Démarrer** pour démarrer le service.

Si aucune base de données n’est répertoriée en regard de l’étiquette Nom de la base de données du serveur de rapports, procédez comme suit :

1.  Dans le Gestionnaire de configuration de Reporting Services, cliquez sur **Base de données**.

2.  Dans le volet Base de données du serveur de rapports, cliquez sur **Changer la base de données**.

3.  Dans le volet Action de l’Assistant de configuration de la base de données du serveur de rapports, sélectionnez **Créer une nouvelle base de données de serveur de rapports**, puis cliquez sur **Suivant**.

4.  Dans le volet Serveur de bases de données de l’Assistant de configuration de la base de données du serveur de rapports, vérifiez que les informations contenues dans les zones **Nom du serveur**, **Type d’authentification** et **Nom d’utilisateur** sont correctes. Cliquez sur **Tester la connexion** pour vérifier qu’une connexion peut être établie au serveur de base de données, puis cliquez sur **Suivant**.

5.  Dans le volet Base de données de l’Assistant de configuration de la base de données du serveur de rapports, acceptez les valeurs par défaut pour **Nom de la base de données**, **Langue** et **Mode du serveur de rapports**, puis cliquez sur **Suivant**.

6.  Dans le volet Informations d’identification de l’Assistant de configuration de la base de données du serveur de rapports, vérifiez que les informations contenues dans la liste déroulante **Nom du serveur** et dans les zones **Nom d’utilisateur** et **Mot de passe** sont correctes, puis cliquez sur **Suivant**.

7.  Dans le volet Résumé de l’Assistant de configuration de la base de données du serveur de rapports, cliquez sur **Suivant**.

8.  Dans le volet État d’avancement et fin de l’Assistant de configuration de la base de données du serveur de rapports, cliquez sur **Terminer**.

Pour vérifier que les URL de Reporting Services ont bien été configurées, cliquez sur **URL du service web**. Vous devriez voir une ou plusieurs URL sous la rubrique **URL du service web Report Server**. Cliquez sur chacune de ces URL pour vérifier que vous pouvez accéder à la page d’accueil de l’installation locale de SQL Server Reporting Services.

