---
title: 'Lync Server 2013 : utilisation de Microsoft SQL Server 2008 R2 en tant que base de données System Center Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 800da512c3cc9690c368c9d397774df0dea2d0e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Utilisation de Microsoft SQL Server 2008 R2 comme base de données System Center Operations Manager pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-29_

Pour utiliser SQL Server 2008 R2 comme base de données principale, procédez comme indiqué dans cette rubrique.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configuration de SQL Server 2008 R2 et SQL Server Reporting Services

Avant de commencer l’installation de System Center Operations Manager, vous devez effectuer deux modifications à SQL Server 2008 R2 et à votre configuration SQL Server Reporting Services. (Ces modifications ne sont requises que si vous utilisez SQL Server 2008 R2 comme base de données Operations Manager.) Tout d’abord, procédez comme suit sur l’ordinateur qui hébergera votre base de données Operations Manager :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **exécuter** , **tapez C\\: Program\\Files Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting Services\\ReportServer** , puis appuyez sur entrée.

3.  Dans le dossier **ReportServer**, ouvrez le fichier **rsreportserver.config** dans le Bloc-notes ou dans un autre éditeur de texte.

4.  Au début du fichier vous verrez une série de nœuds « Add Key ». Recherchez l’entrée qui commence ** \<à ajouter Key = "SecureConnectionLevel"** et définissez la valeur sur **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Enregistrez le fichier **rsreportserver.config** et fermez l’éditeur de texte.

Une fois que vous avez modifié le fichier de configuration du serveur de rapports, vous devez affecter le certificat correct à SQL Server Reporting Services. Pour cela :

1.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **outils de configuration**, puis sur gestionnaire de **configuration de Reporting Services**.

2.  Dans la boîte de dialogue **Connexion relative à la configuration de Reporting Services**, assurez-vous que le nom du serveur apparaît dans la zone **Nom du serveur**. Sélectionnez l’instance SQL Server qui doit héberger votre base de données Operations Manager (par exemple, **ARCHINST**) dans la liste déroulante **instance de serveur de rapports** , puis cliquez sur **se connecter**.

3.  Dans le Gestionnaire de configuration de Reporting Services, cliquez sur **  URL du service web **.

4.  Dans la page **URL du service web**, sélectionnez le certificat à utiliser pour Reporting Services dans la liste déroulante **Certificat SSL **, puis cliquez sur **Appliquer**. Après quelques secondes, deux URL apparaissent sous **URL du service web Report Server**.

5.  Cliquez sur les deux URL pour vérifier que vous pouvez accéder à SQL Server Reporting Services.

6.  Fermez le Gestionnaire de configuration de Reporting Services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Création d’une base de données System Center Operations Manager pour une utilisation avec SQL Server 2008 R2

Si vous souhaitez configurer System Center Operations Manager pour utiliser une base de données SQL Server 2008 R2, vous devez créer manuellement la base de données Operations Manager sur l’ordinateur qui exécute SQL Server 2008 R2. (Encore une fois, ces étapes ne sont pas nécessaires si vous utilisez SQL Server 2005 ou SQL Server 2008 comme base de données principale).

Pour créer manuellement une base de données Operations Manager, procédez comme suit :

1.  Sur le support d’installation de System Center Operations Manager 2007 R2,\\dans le dossier amd64 SupportTools, double-cliquez sur **DBCreateWizard. exe**.

2.  Dans l’Assistant Configuration de base de données, dans la page **Bienvenue dans l’Assistant Configuration de base de données**, cliquez sur **Suivant**.

3.  Dans la page **Informations sur la base de données**, ne modifiez pas les paramètres et cliquez sur **Suivant**.

4.  Dans la **page Configuration du groupe d’administration** , entrez un nom pour votre groupe d’administration (par exemple, **analyse Lync Server**) dans la zone Nom du groupe d' **administration** , puis cliquez sur **suivant**.

5.  Dans la page **Rapports d’erreurs Operations Manager**, cliquez sur **Suivant**.

6.  Dans la page **Résumé**, cliquez sur **Terminer**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Création d’un entrepôt de données System Center Operations Manager pour une utilisation avec SQL Server 2008 R2

Microsoft Lync Server 2013 est livré avec trois nouveaux rapports System Center Operations Manager :

  - **Rapport de disponibilité des scénarios de bout en bout**   ce rapport présente la disponibilité/temps de fonctionnement des services Lync Server clés tels que l’inscription ou la présence.

  - **Rapport de capacité**   à l’aide des informations des compteurs de performance, ce rapport affiche les tendances des composants système, notamment la disponibilité de la mémoire et l’utilisation du processeur.

  - **Rapport de composants**   ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.

Pour pouvoir utiliser ces nouveaux rapports, vous devez installer un entrepôt de données System Center Operations Manager. (Un Data Warehouse offre un stockage à long terme des données opérationnelles.) Pour utiliser un Data Warehouse avec SQL Server 2008 R2, vous devez effectuer les étapes suivantes sur l’ordinateur qui héberge votre base de données SQL Server :

1.  Sur le support d’installation de System Center Operations Manager,\\dans\\le dossier amd64 du programme d’installation d’SupportTools, double-cliquez sur **DBCreateWizard. exe**.

2.  Dans l’Assistant Configuration de base de données, dans la page **Bienvenue dans l’Assistant Configuration de base de données**, cliquez sur **Suivant**.

3.  Dans la page **Informations sur la base de données**, sélectionnez **Base de données de magasin de données Operations Manager** dans la liste déroulante **Type de base de données** et cliquez sur **Suivant**.

4.  Dans la page **Résumé**, cliquez sur **Terminer**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Installation de la console System Center Operations Manager

La console Operations Manager est l’outil principal utilisé pour gérer System Center Operations Manager. Avant d’installer la console Operations Manager, assurez-vous que vous avez installé une version prise en charge de SQL Server avec le service SQL Server Reporting. Nous vous recommandons également d’exécuter le Gestionnaire de configuration de Reporting Services de SQL Server pour vérifier que Reporting Services est correctement installé et configuré.

Pour installer la console System Center Operations Manager, procédez comme suit :

1.  Sur le support d’installation de System Center Operations Manager, double-cliquez sur **SetupOM. exe**.

2.  Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **vérifier les conditions préalables**.

3.  Dans la visionneuse requise de System Center Operations Manager, sélectionnez les composants System Center à installer : (**serveur**; **Console**; et **PowerShell**), puis cliquez sur **vérifier**. Vérifiez qu’aucun problème de blocage n’est signalé et cliquez sur **Fermer**. Si un problème de blocage est signalé, corrigez-le et cliquez sur **Vérifier** pour exécuter de nouveau le test des conditions préalables.

4.  Dans le programme d’installation de System Center Operations Manager, cliquez sur **installer Operations Manager**.

5.  Dans l’Assistant Installation de System Center Operations Manager, dans la page **Bienvenue dans l’Assistant Installation de System Center Operations Manager** , cliquez sur **suivant**.

6.  Dans la page **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.

7.  Sur la page **inscription du produit** , tapez votre nom dans la zone nom d' **utilisateur** et le nom de votre organisation dans la zone **organisation** . Tapez votre clé de produit System Center Operations Manager dans la zone **Entrez votre clé de CD à 25 chiffres** , puis cliquez sur **suivant**.

8.  Dans la page **Installation personnalisée**, sélectionnez les options de System Center à installer et cliquez sur **Suivant**. Vous devez sélectionner **Serveur d’administration**, **Interfaces utilisateur** et **Console web ** pour installer ces fonctionnalités. Ne sélectionnez pas **Base de données**, car cette fonctionnalité ne doit pas être installée.

9.  Sur la page **de l’instance du serveur de base de données SC** , vérifiez que le nom de l’ordinateur sur lequel les bases de données Operations Manager sont installées apparaît dans la zone **serveur de base de données System Center** . Cliquez sur **Suivant**.

10. Dans la page **Compte d’action du serveur d’administration**, sélectionnez **Compte d’ordinateur de domaine ou local**, puis entrez les valeurs appropriées dans les zones **Compte d’utilisateur**, **Mot de passe** et **Ordinateur local ou du domaine**. Cliquez sur **Suivant**.

11. Dans la page **SDK et compte de service de configuration**, sélectionnez **Compte d’ordinateur de domaine ou local**, puis entrez les valeurs appropriées dans les zones **Compte d’utilisateur**, **Mot de passe** et **Ordinateur local ou du domaine**. Cliquez sur **Suivant**.

12. Dans la page **Rapports d’erreurs Operations Manager**, cliquez sur **Suivant**.

13. Dans la page **Programme d’amélioration du produit**, cliquez sur **Suivant**.

14. Dans la page **Prêt à installer le programme**, cliquez sur **Installer**.

15. Dans la page **Fin de l’Assistant Installation de System Center - Operations Manager**, désactivez les cases à cocher **Sauvegarder la clé de chiffrement** et **Démarrer la console**, puis cliquez sur **Terminer**.

16. Dans le programme d’installation de System Center Operations Manager, cliquez sur **quitter**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Installation de System Center Reporting Services

Après l’installation et la configuration de la console System Center Operations Manager, vous devez installer System Center Reporting Services. Si vous utilisez SQL Server 2008 R2 comme base de données principale Operations Manager, cela signifie que vous devez d’abord modifier temporairement le groupe de sécurité associé à SQL Server Reporting Services. Si vous utilisez SQL Server 2008 R2, vous devez effectuer les opérations suivantes :

1.  Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.

2.  Dans le Gestionnaire de serveur, développez **Configuration** et **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.

3.  Recherchez le groupe suivant, où ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance de SQL Server pour la base de données System Center : **SQLServerReportServerUser $ ATL-SC-\_001 $ MSRS10 50. ARCHINST**.

4.  Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**. Renommez le groupe en supprimant ** \_50** du nom du groupe. Par exemple : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Fermez le Gestionnaire de serveur.

À ce stade, vous êtes prêt à installer System Center Reporting Services. Pour ce faire, procédez comme suit :

1.  Sur le support d’installation de System Center Operations Manager 2007 R2, double-cliquez sur **SetupOM. exe**.

2.  Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **installer la création de rapports d’Operations Manager**.

3.  Dans l’Assistant Configuration de création de rapports de System Center Operations Manager 2007 R2, sur la page Bienvenue dans le **programme d’installation des rapports Operations Manager** , cliquez sur **suivant**.

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

16. Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **quitter**.

Une fois que System Center Reporting a été installé, vous utilisez la procédure suivante pour réinitialiser le nom du groupe de sécurité associé à SQL Server Reporting. Cette procédure n’est nécessaire que si vous utilisez SQL Server :

1.  Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.

2.  Dans le Gestionnaire de serveur, développez **Configuration** et **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.

3.  Recherchez le groupe suivant, où ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance de SQL Server pour les bases de données d’archivage et de surveillance : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**. Renommez le groupe en ajoutant ** \_50** à la fin du nom du groupe, juste avant le nom de l’instance SQL Server. Par exemple : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Fermez le Gestionnaire de serveur.

Si la console de System Center Operations est ouverte vous devez fermer l’application et la redémarrer. Autrement, l’onglet **Rapports** n’apparaîtra pas dans l’interface utilisateur de la console. Notez qu’après le redémarrage de la console Operations, l’affichage des rapports de surveillance sous l’onglet **Rapports** peut prendre quelques minutes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

