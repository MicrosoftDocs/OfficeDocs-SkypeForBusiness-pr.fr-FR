---
title: "Ut. de Microsoft SQL Server 2008 R2 comme BD System Center Operations Manager"
TOCtitle: "Ut. de Microsoft SQL Server 2008 R2 comme BD System Center Operations Manager"
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49891232
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de Microsoft SQL Server 2008 R2 comme base de données System Center Operations Manager

 

_**Dernière rubrique modifiée :** 2013-07-29_

Pour utiliser SQL Server 2008 R2 comme base de données principale, effectuez la procédure indiquée dans cette rubrique.

## Configuration de SQL Server 2008 R2 et de SQL Server Reporting Services

Avant de commencer l’installation de System Center Operations Manager, vous devez apporter deux modifications à la configuration de SQL Server 2008 R2 et de SQL Server Reporting Services. (Ces modifications sont nécessaires seulement si vous utilisez SQL Server 2008 R2 comme base de données Operations Manager.) Effectuez d’abord ce qui suit sur l’ordinateur qui hébergera votre base de données Operations Manager :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer**, puis appuyez sur Entrée.

3.  Dans le dossier **ReportServer**, ouvrez le fichier **rsreportserver.config** dans le Bloc-notes ou dans un autre éditeur de texte.

4.  Au début du fichier vous verrez une série de nœuds « Add Key ». Recherchez l’entrée qui commence par **\<Add Key="SecureConnectionLevel"** et définissez la valeur sur **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Enregistrez le fichier **rsreportserver.config** et fermez l’éditeur de texte.

Une fois que vous avez modifié le fichier de configuration du serveur de rapports, vous devez affecter le certificat correct à SQL Server Reporting Services. Pour cela :

1.  Cliquez sur **Démarrer**, **Tous les programmes**, **Microsoft SQL Server 2008 R2**, **Outils de configuration**, puis sur **Gestionnaire de configuration de Reporting Services**.

2.  Dans la boîte de dialogue **Connexion relative à la configuration de Reporting Services**, assurez-vous que le nom du serveur apparaît dans la zone **Nom du serveur**. Sélectionnez l’instance de SQL Server qui hébergera la base de données Operations Manager (par exemple, **ARCHINST**) dans la liste déroulante **Instance du serveur de rapports** et cliquez sur **Connecter**.

3.  Dans le Gestionnaire de configuration de Reporting Services, cliquez sur **URL du service web** .

4.  Dans la page **URL du service web**, sélectionnez le certificat à utiliser pour Reporting Services dans la liste déroulante **Certificat SSL** , puis cliquez sur **Appliquer**. Après quelques secondes, deux URL apparaissent sous **URL du service web Report Server**.

5.  Cliquez sur les deux URL pour vérifier que vous pouvez accéder à SQL Server Reporting Services.

6.  Fermez le Gestionnaire de configuration de Reporting Services.

## Création d’une base de données System Center Operations Manager à utiliser avec SQL Server 2008 R2

Si vous voulez configurer System Center Operations Manager pour qu’il utilise une base de données SQL Server 2008 R2, vous devez manuellement créer la base de données Operations Manager sur l’ordinateur qui exécute SQL Server 2008 R2. (Ces opérations ne sont pas nécessaires si vous utilisez SQL Server 2005 ou SQL Server 2008 comme base de données principale.)

Pour créer manuellement une base de données Operations Manager procédez comme suit :

1.  Dans le support d’installation de System Center Operations Manager 2007 R2, dans le dossier SupportTools\\AMD64, double-cliquez sur **DBCreateWizard.exe**.

2.  Dans l’Assistant Configuration de base de données, dans la page **Bienvenue dans l’Assistant Configuration de base de données**, cliquez sur **Suivant**.

3.  Dans la page **Informations sur la base de données**, ne modifiez pas les paramètres et cliquez sur **Suivant**.

4.  Dans la page **Configuration du groupe d’administration**, tapez le nom du groupe d’administration (par exemple, Surveillance **Lync Server**) dans la zone **Nom du groupe d’administration**, puis cliquez sur **Suivant**.

5.  Dans la page **Rapports d’erreurs Operations Manager**, cliquez sur **Suivant**.

6.  Dans la page **Résumé**, cliquez sur **Terminer**.

## Création d’un entrepôt de données System Center Operations Manager à utiliser avec SQL Server 2008 R2

Microsoft Lync Server 2013 est fourni avec trois nouveaux rapports System Center Operations Manager :

  - **Rapport de disponibilité des scénarios de bout en bout** Ce rapport présente la disponibilité/durée active des services Lync Server clés tels que l’inscription ou la présence.

  - **Rapport de capacité** Ce rapport utilise les informations du compteur de performances pour montrer les tendances des composants système, notamment la mémoire disponible et l’utilisation du processeur.

  - **Rapport de composants** Ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.

Afin d’utiliser ces nouveaux rapports vous devez installer un entrepôt de données System Center Operations Manager. (Un entrepôt de données permet un stockage à long terme des données relatives aux opérations.) Pour utiliser un entrepôt de données avec SQL Server 2008 R2, vous devez effectuer la procédure suivante sur l’hôte qui héberge la base de données SQL Server :

1.  Dans le support d’installation de System Center Operations Manager, dans le dossier Setup\\SupportTools\\AMD64, double-cliquez sur **DBCreateWizard.exe**.

2.  Dans l’Assistant Configuration de base de données, dans la page **Bienvenue dans l’Assistant Configuration de base de données**, cliquez sur **Suivant**.

3.  Dans la page **Informations sur la base de données**, sélectionnez **Base de données de magasin de données Operations Manager** dans la liste déroulante **Type de base de données** et cliquez sur **Suivant**.

4.  Dans la page **Résumé**, cliquez sur **Terminer**.

## Installation de la console de System Center Operations Manager

La console de Operations Manager est l’outil principal permettant de gérer System Center Operations Manager. Avant d’installer la console de Operations Manager, assurez-vous que vous avez installé une version prise en charge de SQL Server ainsi que SQL Server Reporting Services. Nous vous recommandons également d’exécuter le Gestionnaire de configuration de Reporting Services de SQL Server pour vérifier que Reporting Services est correctement installé et configuré.

Pour installer la console de System Center Operations Manager :

1.  Dans le support d’installation de System Center Operations Manager, double-cliquez sur **SetupOM.exe**.

2.  Dans l’installation de System Center Operations Manager 2007 R2, cliquez sur **Vérifier la configuration requise**.

3.  Dans la visionneuse de condition préalable de System Center Operations Manager, sélectionnez les composants de System Center à installer : (**Serveur**, **Console** et **PowerShell**), puis cliquez sur **Vérifier**. Vérifiez qu’aucun problème de blocage n’est signalé et cliquez sur **Fermer**. Si un problème de blocage est signalé, corrigez-le et cliquez sur **Vérifier** pour exécuter de nouveau le test des conditions préalables.

4.  Dans l’installation de System Center Operations Manager, cliquez sur **Installer Operations Manager**.

5.  Dans l’Assistant Installation de System Center Operations Manager, dans la page **Bienvenue dans l’Assistant Installation de System Center Operations Manager**, cliquez sur **Suivant**.

6.  Dans la page **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.

7.  Dans la page **Inscription du produit**, tapez votre nom dans la zone **Nom de l’utilisateur** et le nom de votre organisation dans la zone **Organisation**. Tapez la clé de produit de System Center Operations Manager dans la zone **Entrez la clé de CD (CD key) à 25 chiffres.**, puis cliquez sur **Suivant**.

8.  Dans la page **Installation personnalisée**, sélectionnez les options de System Center à installer et cliquez sur **Suivant**. Vous devez sélectionner **Serveur d’administration**, **Interfaces utilisateur** et **Console web** pour installer ces fonctionnalités. Ne sélectionnez pas **Base de données**, car cette fonctionnalité ne doit pas être installée.

9.  Dans la page **Instance du serveur de base de données SC**, vérifiez que le nom de l’ordinateur sur lequel les bases de données Operations Manager sont installées apparaît dans la zone **Serveur de base de données System Center**. Cliquez sur **Suivant**.

10. Dans la page **Compte d’action du serveur d’administration**, sélectionnez **Compte d’ordinateur de domaine ou local**, puis entrez les valeurs appropriées dans les zones **Compte d’utilisateur**, **Mot de passe** et **Ordinateur local ou du domaine**. Cliquez sur **Suivant**.

11. Dans la page **SDK et compte de service de configuration**, sélectionnez **Compte d’ordinateur de domaine ou local**, puis entrez les valeurs appropriées dans les zones **Compte d’utilisateur**, **Mot de passe** et **Ordinateur local ou du domaine**. Cliquez sur **Suivant**.

12. Dans la page **Rapports d’erreurs Operations Manager**, cliquez sur **Suivant**.

13. Dans la page **Programme d’amélioration du produit**, cliquez sur **Suivant**.

14. Dans la page **Prêt à installer le programme**, cliquez sur **Installer**.

15. Dans la page **Fin de l’Assistant Installation de System Center - Operations Manager**, désactivez les cases à cocher **Sauvegarder la clé de chiffrement** et **Démarrer la console**, puis cliquez sur **Terminer**.

16. Dans l’installation de System Center Operations Manager, cliquez sur **Quitter**.

## Installation de System Center Reporting Services

Après avoir installé et configuré la console de System Center Operations Manager, vous devez installer System Center Reporting Services. Si vous utilisez SQL Server 2008 R2 comme base de données principale d’Operations Manager, vous devez donc modifier temporairement le groupe de sécurité associé à SQL Server Reporting Services. Si vous utilisez SQL Server 2008 R2, procédez comme suit :

1.  Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.

2.  Dans le Gestionnaire de serveur, développez **Configuration** et **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.

3.  Recherchez le groupe suivant, où atl-sc-001 représente le nom de votre ordinateur et ARCHINST l’instance SQL Server pour la base de données de System Center : **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.

4.  Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**. Renommez le groupe en supprimant **\_50** dans son nom. Par exemple : **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.

5.  Fermez le Gestionnaire de serveur.

À ce stade, vous êtes prêt à installer System Center Reporting Services. Pour ce faire, procédez comme suit :

1.  Dans le support d’installation de System Center Operations Manager 2007 R2, double-cliquez sur **SetupOM.exe**.

2.  Dans l’installation de System Center Operations Manager 2007 R2, cliquez sur **Installer Operations Manager Reporting**.

3.  Dans l’Assistant Installation de System Center Operations Manager 2007 R2 Reporting, dans la page **Bienvenue dans l’installation d’Operations Manager Reporting**, cliquez sur **Suivant**.

4.  Dans la page **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.

5.  Dans la page **Inscription du produit**, assurez-vous que votre nom et celui de votre organisation apparaissent dans les zones **Nom de l’utilisateur** et **Organisation**, puis cliquez sur **Suivant**.

6.  Dans la page **Installation personnalisée**, cliquez sur **Serveur de rapports** et sélectionnez **Ce composant et tous les composants associés seront installés sur le disque local.**. Cliquez sur **Entrepôt de données**, sélectionnez **Ce composant ne sera pas disponible.**, puis cliquez sur **Suivant**.

7.  Dans la page **Connexion au serveur d’administration principal**, tapez le nom du serveur d’administration racine Operations Manager dans la zone **Serveur d’administration racine**, puis cliquez sur **Suivant**.

8.  Dans la page **Se connecter à l’entrepôt de données d’Operations Manager**, tapez l’instance SQL Server dans laquelle se trouve l’entrepôt de données dans la zone **Instance SQL Server**. (Si l’entrepôt de données se trouve dans l’instance par défaut, tapez simplement le nom du serveur, par exemple : atl-sql-001.) Vérifiez que le nom de la base de données **OperationsManagerDW** apparaît dans la zone **Nom** et que le port **1433** apparaît dans la zone **Port du serveur SQL**. Cliquez sur **Suivant**.

9.  Dans la page **Instance SQL Server Reporting**, sélectionnez le serveur de rapports SQL Server dans la liste déroulante **Entrez le nom du serveur SQL Server Reporting Services.** et cliquez sur **Suivant**.

10. Dans la page **Compte d’écriture d’entrepôt de données**, entrez le nom et le mot de passe de l’utilisateur, auquel des autorisations d’accès en écriture à l’entrepôt de données devront être accordées, dans les zones **Compte d’utilisateur** et **Mot de passe**. Sélectionnez le domaine de l’utilisateur dans la liste déroulante **Domaine** et cliquez sur **Suivant**.

11. Dans la page **Compte de lecteur de données**, entrez le nom et le mot de passe du compte d’utilisateur à utiliser lorsque SQL Reporting Services interroge l’entrepôt de données dans les zones **Compte d’utilisateur** et **Mot de passe**. Sélectionnez le domaine du compte dans la liste déroulante **Domaine** et cliquez sur **Suivant**.

12. Dans la page **Rapports de données opérationnelles**, cliquez sur **Suivant**.

13. Dans la page **Microsoft Update**, cliquez sur **Suivant**.

14. Dans la page **Prêt à installer le programme**, cliquez sur **Installer**.

15. Dans la page **Fin de l’Assistant Installation des composants d’Operations Manager Reporting**, cliquez sur **Terminer**.

16. Dans l’installation de System Center Operations Manager 2007 R2, cliquez sur **Quitter**.

Une fois que vous avez installé System Center Reporting Services, procédez comme suit pour redéfinir le nom du groupe de sécurité associé à SQL Server Reporting. Cette procédure est uniquement requise si vous utilisez SQL Server :

1.  Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.

2.  Dans le Gestionnaire de serveur, développez **Configuration** et **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.

3.  Recherchez le groupe suivant, où atl-sc-001 représente le nom de votre ordinateur et ARCHINST l’instance SQL Server pour les bases de données d’archivage et de surveillance : **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.

4.  Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**. Renommez le groupe en ajoutant **\_50** à la fin de son nom, juste avant le nom de l’instance SQL Server. Par exemple : **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.

5.  Fermez le Gestionnaire de serveur.

Si la console de System Center Operations est ouverte vous devez fermer l’application et la redémarrer. Autrement, l’onglet **Rapports** n’apparaîtra pas dans l’interface utilisateur de la console. Notez qu’après le redémarrage de la console Operations, l’affichage des rapports de surveillance sous l’onglet **Rapports** peut prendre quelques minutes.

