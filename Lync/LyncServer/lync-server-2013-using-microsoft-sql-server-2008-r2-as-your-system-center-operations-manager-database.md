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
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Utilisation de Microsoft SQL Server 2008 R2 en tant que base de données Gestionnaire d’opérations System Center pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-29_

Pour utiliser SQL Server 2008 R2 en tant que base de données principale, suivez les étapes décrites dans cette rubrique.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configuration de SQL Server 2008 R2 et SQL Server Reporting Services

Avant de commencer à installer System Center Operations Manager, vous devez apporter deux modifications à SQL Server 2008 R2 et à votre configuration SQL Server Reporting Services. (Ces modifications sont requises uniquement si vous utilisez SQL Server 2008 R2 en tant que base de données Operations Manager.) Tout d’abord, procédez comme suit sur l’ordinateur qui héberge votre base de données Operations Manager :

1.  Cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , **tapez C\\: Program\\Files Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting Services\\ReportServer** , puis appuyez sur entrée.

3.  Dans le dossier **reportserver** , ouvrez le fichier **RSReportServer. config** dans le bloc-notes ou dans un autre éditeur de texte.

4.  Au début du fichier, vous verrez une série de nœuds « ajouter une touche ». Recherchez l’entrée commençant ** \<par ajouter Key = « SecureConnectionLevel »** et définissez la valeur sur **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Enregistrez le fichier **RSReportServer. config** , puis fermez votre éditeur de texte.

Après avoir effectué la mise à jour du fichier de configuration du serveur de rapports, vous devez affecter le certificat approprié à SQL Server Reporting Services. Pour cela, procédez comme suit :

1.  Cliquez sur **Démarrer**, **sur tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **outils de configuration**, puis sur gestionnaire de **configuration Reporting Services**.

2.  Dans la boîte de dialogue **connexion de configuration de Reporting Services** , assurez-vous que le nom de votre serveur apparaît dans la zone **nom du serveur** . Sélectionnez l’instance de SQL Server qui héberge votre base de données Operations Manager (par exemple, **ARCHINST**) dans la liste déroulante de l' **instance Report Server** , puis cliquez sur **se connecter**.

3.  Dans le gestionnaire de configuration Reporting Services, cliquez sur **URL du service Web**.

4.  Dans la page **URL du service Web** , sélectionnez le certificat à utiliser pour la création de rapports services dans la liste déroulante **certificat SSL** , puis cliquez sur **appliquer**. Après quelques secondes, une paire d’URL est affichée sous **URL du service Web de Report Server**.

5.  Cliquez sur les deux URL pour vérifier que vous pouvez accéder à SQL Server Reporting Services.

6.  Fermez le gestionnaire de configuration de report services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Création d’une base de données System Center Operations Manager à utiliser avec SQL Server 2008 R2

Si vous voulez configurer System Center Operations Manager de façon à utiliser une base de données SQL Server 2008 R2, vous devez « manuellement » créer la base de données Operations Manager sur l’ordinateur exécutant SQL Server 2008 R2. (De nouveau, cette procédure n’est pas nécessaire si vous utilisez SQL Server 2005 ou SQL Server 2008 comme base de données principale.)

Pour créer manuellement une base de données Operations Manager, procédez comme suit :

1.  Sur le média de configuration de System Center Operations Manager 2007 R2,\\dans le dossier amd64 de SupportTools, double-cliquez sur **DBCreateWizard. exe**.

2.  Dans l’Assistant Configuration de la base de données, dans la page **Bienvenue dans l’Assistant Configuration de la base de données** , cliquez sur **suivant**.

3.  Dans la page **informations de la base de données** , conservez tous les paramètres, puis cliquez sur **suivant** .

4.  Dans la **page Configuration du groupe de gestion** , tapez un nom pour votre groupe d’administration (par exemple, analyse du **serveur Lync**) dans la zone **nom du groupe de gestion** , puis cliquez sur **suivant**.

5.  Dans la page **rapports d’erreurs Operations Manager** , cliquez sur **suivant**.

6.  Dans la page **Résumé** , cliquez sur **Terminer**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Création d’un entrepôt de données System Center Operations Manager à utiliser avec SQL Server 2008 R2

Microsoft Lync Server 2013 est fourni avec trois nouveaux rapports System Center Operations Manager :

  - **Rapport de disponibilité du scénario de bout en bout**   ce rapport décrit en détail la disponibilité des services principaux de Lync Server tels que l’inscription ou la présence.

  - **Rapport de capacité**   utilisant des informations de compteurs de performance, ce rapport affiche des tendances pour les composants système tels que la disponibilité de la mémoire et l’utilisation du processeur.

  - **Rapport de composant**   ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.

Pour pouvoir utiliser ces nouveaux rapports, vous devez installer un Data Warehouse System Center Operations Manager. (Un entrepôt de données fournit un espace de stockage de données opérationnelles longue durée.) Pour utiliser un entrepôt de données avec SQL Server 2008 R2, vous devez effectuer les étapes suivantes sur l’ordinateur qui héberge votre base de données SQL Server :

1.  Sur le média de configuration de System Center Operations Manager,\\dans\\le dossier SupportTools de configuration, double-cliquez sur **DBCreateWizard. exe**.

2.  Dans l’Assistant Configuration de la base de données, dans la page **Bienvenue dans l’Assistant Configuration de la base de données** , cliquez sur **suivant**.

3.  Dans la page **informations de la base de** données, sélectionnez **base de données du Data Warehouse Operations Manager** dans la liste déroulante **type de base de données** , puis cliquez sur **suivant**.

4.  Dans la page **Résumé** , cliquez sur **Terminer**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Installation de la console System Center Operations Manager

La console Operations Manager est l’outil principal utilisé pour gérer System Center Operations Manager. Avant d’installer la console Operations Manager, assurez-vous d’avoir installé une version prise en charge de SQL Server, ainsi que le service SQL Server Reporting. Il est également recommandé d’exécuter le gestionnaire de configuration Reporting Services de SQL Server pour vérifier que le service de création de rapports est correctement installé et configuré.

Pour installer la console System Center Operations Manager, procédez comme suit :

1.  Sur le média de configuration de System Center Operations Manager, double-cliquez sur **SetupOM. exe**.

2.  Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **vérifier les conditions préalables**.

3.  Dans la visionneuse de logiciels de System Center Operations Manager, sélectionnez les composants System Center à installer : (**serveur**; **Console**; et **PowerShell**), puis cliquez sur **vérifier**. Vérifiez qu’aucun problème de blocage n’a été signalé, puis cliquez sur **Fermer**. Si un problème de blocage a été signalé, corrigez le problème, puis cliquez sur **vérifier** pour réexécuter les tests préalables.

4.  Dans le programme d’installation de System Center Operations Manager, cliquez sur **installer Operations Manager**.

5.  Dans l’Assistant Configuration de System Center Operations Manager, dans la page Bienvenue dans l' **Assistant Configuration de System Center Operations Manager** , cliquez sur **suivant**.

6.  Sur la page **contrat de licence utilisateur final** , sélectionnez **J’accepte les conditions du contrat de licence** , puis cliquez sur **suivant**.

7.  Sur la page **inscription de produit** , tapez votre nom dans la zone nom d' **utilisateur** et le nom de votre organisation dans la zone **organisation** . Tapez votre clé de produit System Center Operations Manager dans la zone **Entrez votre clé** de produit à 25 chiffres, puis cliquez sur **suivant**.

8.  Dans la page **configuration personnalisée** , sélectionnez les options du centre de systèmes à installer, puis cliquez sur **suivant**. Sélectionnez serveur de **gestion**, **interfaces utilisateur**et **console Web** à installer. La **base de données** ne doit pas être sélectionnée et ne peut pas être installée.

9.  Dans la page d' **instance du serveur de base de données SC** , vérifiez que le nom de l’ordinateur sur lequel les bases de données du gestionnaire d’opérations sont installées apparaît dans la zone **serveur de base de données System Center** . Cliquez sur **Suivant**.

10. Sur la **page compte d’action du serveur de gestion** , sélectionnez **domaine ou compte d’ordinateur local** , puis entrez les valeurs appropriées dans les zones **compte d’utilisateur**, **mot de passe**et **domaine ou ordinateur local** . Cliquez sur **Suivant**.

11. Sur la page du **compte de service SDK et de configuration** , sélectionnez **domaine ou compte d’ordinateur local** , puis entrez les valeurs appropriées dans les zones **compte d’utilisateur**, **mot de passe**et **domaine ou ordinateur local** . Cliquez sur **Suivant**.

12. Dans la page **rapports d’erreurs Operations Manager** , cliquez sur **suivant**.

13. Sur la page du **programme d’amélioration** du produit, cliquez sur **suivant**.

14. Dans la page êtes-vous **prêt à installer le programme** , cliquez sur **installer**.

15. Dans la page **fin de la procédure de configuration de System Center Operations Manager** , désactivez la **clé de chiffrement de sauvegarde** et **Démarrez les cases à cocher** de la console, puis cliquez sur **Terminer**.

16. Dans le programme d’installation de System Center Operations Manager, cliquez sur **quitter**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Installation de System Center Reporting Services

Après l’installation et la configuration de la console System Center Operations Manager, vous devez installer System Center Reporting Services. Si vous utilisez SQL Server 2008 R2 comme base de données principale Operations Manager, cela signifie que vous devez tout d’abord apporter un changement temporaire au groupe de sécurité associé à SQL Server Reporting Services. Si vous utilisez SQL Server 2008 R2, vous devez effectuer les opérations suivantes :

1.  Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.

2.  Dans le gestionnaire de serveur, développez **configuration**, **utilisateurs et groupes locaux**, puis cliquez sur **groupes**.

3.  Recherchez le groupe suivant, dans lequel ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance SQL Server de la base de données du centre de données : **SQLServerReportServerUser $ ATL-\_SC-001 $ MSRS10 50. ARCHINST**.

4.  Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**. Renommez le groupe en supprimant ** \_50** du nom du groupe. Par exemple : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Fermez le gestionnaire de serveur.

À ce stade, vous êtes prêt à installer System Center Reporting Services. Pour ce faire :

1.  Sur le média de configuration de System Center Operations Manager 2007 R2, double-cliquez sur **SetupOM. exe**.

2.  Dans System Center Operations Manager 2007 R2, cliquez sur **installer le rapport Operations Manager**.

3.  Dans l’Assistant Configuration de création de rapports de System Center Operations Manager 2007 R2, dans la page Bienvenue dans le **programme d’installation de création de rapports Operations Manager** , cliquez sur **suivant**.

4.  Dans la page **contrat de licence utilisateur final** , sélectionnez **J’accepte les conditions du contrat de licence** , puis cliquez sur **suivant**.

5.  Sur la page **inscription de produit** , assurez-vous que votre nom et le nom de votre organisation apparaissent dans les zones nom d' **utilisateur** et **organisation** , puis cliquez sur **suivant**.

6.  Dans la page **configuration personnalisée** , cliquez sur **serveur de création de rapports** , sélectionnez **ce composant, et tous les composants dépendants, seront installés sur le lecteur de disque local**. Cliquez sur **entrepôt de données** et sélectionnez **ce composant ne sera pas disponible**, puis cliquez sur **suivant**.

7.  Dans la page **connexion à un serveur de gestion racine** , tapez le nom de votre serveur de gestion de la racine Operations Manager dans la zone **serveur de gestion racine** , puis cliquez sur **suivant**.

8.  Dans la page **se connecter à l’entrepôt de données Operations Manager** , entrez l’instance SQL Server dans laquelle se trouve votre entrepôt de données dans la zone **instance SQL Server** . (Si votre entrepôt de données se trouve dans l’instance par défaut, tapez simplement le nom du serveur, par exemple : ATL-SQL-001.) Vérifiez que le nom de la base de données **OperationsManagerDW** s’affiche dans la zone **nom** et que le port **1433** s’affiche dans la zone **port SQL Server** . Cliquez sur **Suivant**.

9.  Dans la page d' **instance SQL Server Report** , sélectionnez votre serveur SQL Server Reporting dans la liste déroulante **Enter SQL Server Reporting Services** , puis cliquez sur **Next (suivant**).

10. Sur la page **compte d’écriture du magasin de données** , entrez le nom et le mot de passe de l’utilisateur auquel vous souhaitez attribuer des autorisations d’écriture dans l’entrepôt de données dans les zones compte d' **utilisateur** et **mot de passe** . Sélectionnez le domaine de l’utilisateur dans la liste déroulante **Domain** , puis cliquez sur **Next (suivant**).

11. Sur la page **compte du lecteur de données** , entrez le nom et le mot de passe du compte d’utilisateur à utiliser lorsque SQL Reporting Services interroge l’entrepôt de données dans les zones compte d' **utilisateur** et **mot de passe** . Sélectionnez le domaine de compte dans la liste déroulante **Domain** , puis cliquez sur **Next (suivant**).

12. Dans la page **rapports de données opérationnelles** , cliquez sur **suivant**.

13. Sur la page **Microsoft Update** , cliquez sur **suivant**.

14. Dans la page êtes-vous **prêt à installer le programme** , cliquez sur **installer**.

15. Dans la page **fin de l’Assistant Installation des composants de création de rapports Operations Manager** , cliquez sur **Terminer**.

16. Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **quitter**.

Après l’installation de la fonctionnalité de création de rapports du centre de systèmes, vous pouvez utiliser la procédure suivante pour réinitialiser le nom du groupe de sécurité associé à la création de rapports SQL Server. Là encore, cette procédure est requise uniquement si vous utilisez SQL Server :

1.  Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.

2.  Dans le gestionnaire de serveur, développez **configuration**, **utilisateurs et groupes locaux**, puis cliquez sur **groupes**.

3.  Recherchez le groupe suivant, dans lequel ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance SQL Server pour les bases de données d’archivage et de surveillance : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**. Pour renommer le groupe, ajoutez ** \_50** à la fin du nom du groupe, juste avant le nom de l’instance SQL Server. Par exemple : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Fermez le gestionnaire de serveur.

Si la console opérations de System Center est ouverte, vous devez fermer l’application, puis la redémarrer. dans le cas contraire, l’onglet **création de rapports** n’apparaît pas dans l’interface utilisateur de la console opérations. Notez que, après le redémarrage de la console d’opérations pour la première fois, tous les rapports d’analyse apparaissent dans l’onglet **rapports** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

