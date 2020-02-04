---
title: Documentation des outils du kit de ressources Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 511a4ee9920237e1671a44a2f7481b40fbeb8e1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Documentation des outils du kit de ressources Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-09_

Cette rubrique décrit les outils qui font partie du kit de ressources de Lync Server 2013, notamment l’objet de chaque outil et des exemples de son utilisation. Les outils du kit de ressources de Lync Server 2013 permettent d’effectuer des tâches de routine plus facilement pour les administrateurs informatiques qui déploient et gèrent Lync Server 2013. Par exemple, l’outil **Web Conf Data** permet de contrôler aisément les données téléchargées par les utilisateurs au cours d’une réunion en ligne. L’outil **SEFAUtil** permet de définir le transfert des appels de délégué et le répondeur automatique pour les utilisateurs. Nous recommandons aux administrateurs informatiques d’utiliser ces outils pour gérer plus efficacement Lync Server 2013.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installation des outils du kit de ressources

Pour installer Lync Server 2013, les outils du kit de ressources, téléchargez **OCSReskit. msi**. Vous pouvez télécharger le programme d’installation des outils du kit de ressources [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)à partir du centre de téléchargement à l’adresse.

Exécutez **OCSResKit.msi ** pour effectuer une installation simple. Le fichier. msi installe tous les outils dans le chemin d’accès suivant : **%\\fichiers programme% Microsoft\\Lync Server 2013 reskit**. Les outils exécutables autonomes se trouvent dans ce dossier. Les outils qui comportent également des fichiers se trouvent dans leurs propres sous-dossiers.

</div>

<div>

## <a name="supported-environments"></a>Environnements pris en charge

Pour des performances optimales, les outils du kit de ressources de Lync Server 2013 doivent être installés dans le même environnement et avec les mêmes spécifications requises pour Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Présentation des outils du kit de ressources

La liste suivante décrit les outils fournis dans le kit de ressources de Lync Server 2013. Pour plus d’informations, reportez-vous à la section suivante.

  - ABSConfig

  - Bandwidth Policy Service Monitor

  - Bandwidth Utilization Analyzer

  - Call Parkometer

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Network Configuration Viewer

  - Response Group Agent Live

  - SEFAUtil

  - SYSPrep.ps1

  - Unassigned Number Announcements Migration

  - Web Conf Data

</div>

<div>

## <a name="absconfig"></a>ABSConfig

L’outil de configuration du service de carnet d’adresses (ABSConfig) est un outil administratif qui permet aux administrateurs de personnaliser la configuration du service de carnet d’adresses dans Lync Server 2013. Cet outil permet également aux administrateurs de Lync Server 2013 de restaurer les paramètres de service de carnet d’adresses par défaut.

<div>

## <a name="description"></a>Description

ABSConfig est une application graphique d’interface utilisateur qui permet aux administrateurs de configurer des attributs de services de domaine Active Directory liés au service de carnet d’adresses.

Les principaux scénarios suivants s’appliquent à l’outil :

  - Pour permettre aux administrateurs de mapper les attributs dans les services de domaine Active Directory aux attributs de Lync Server 2013.

  - permettre aux administrateurs de spécifier un attribut des services de domaine Active Directory à inclure dans les fichiers du service de carnet d’adresses ou à exclure de ceux-ci ;

  - permettre aux administrateurs de restaurer les paramètres par défaut du service de carnet d’adresses.

L’outil ABSConfig peut être démarré en utilisant le fichier absConfig. exe. L’outil s’ouvre dans l’onglet **configurer les attributs** . Le tableau suivant contient des options permettant de mapper les attributs des services de domaine Active Directory aux champs d’attribut pour Lync Server 2013 et de spécifier les utilisateurs à inclure ou exclure dans les fichiers du service de carnet d’adresses en fonction de filtres d’attributs spécifiques. D’autres options permettent de personnaliser la valeur du numéro de téléphone à inclure dans le fichier de carnet d’adresses. L’option **Restore Defaults (Paramètres par défaut) ** permet aux administrateurs de restaurer les valeurs par défaut des paramètres du service de carnet d’adresses.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Modifications de Lync Server 2010

Dans l’outil de configuration ABS de Lync Server 2013, les attributs (lignes) risquent d’être supprimés en décochez la case « Activer » pour l’attribut. Ce résultat est le même que celui de la suppression de la ligne dans Lync Server 2010.

<div>


> [!NOTE]  
> La case à cocher Activer se trouve dans l’extrémité droite de la colonne. Il est possible que vous deviez faire défiler la liste vers la droite pour afficher la colonne



</div>

</div>

<div>

## <a name="output"></a>Sortie

ABSConfig stocke la configuration du service de carnet d’adresses dans la base de données.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>Objectif

ABSConfig offre un moyen rapide et facile de personnaliser le service de carnet d’adresses Lync Server 2013.

</div>

<div>

## <a name="requirements"></a>Configuration requise

<div>

## <a name="computer"></a>Ordinateur

ABSConfig ne peut être exécuté qu’à partir d’un ordinateur appartenant à un domaine sur lequel Lync Server 2013 est installé. Dans le cas de Lync Server 2013, Enterprise Edition, cet outil peut être exécuté sur n’importe quel serveur frontal sur lequel le service de carnet d’adresses est activé lors de l’installation.

</div>

<div>

## <a name="network"></a>Réseau

L’ordinateur doit pouvoir se connecter au pool frontal et à la base de données principale.

</div>

<div>

## <a name="software"></a>Logiciels

Les composants logiciels suivants doivent être installés avant d’exécuter l’outil ABSConfig :

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>Utilisateurs

Administrateurs disposant des autorisations requises pour mettre à jour le déploiement de Lync Server 2013.

</div>

</div>

<div>

## <a name="examples"></a>Exemples

ABSConfig peut être démarré en tapant **ABSConfig.exe** dans une invite de commandes. L’interface utilisateur de l’outil ABSConfig se présente comme suit :

![Outil ABSConfig. exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Outil ABSConfig. exe.")

</div>

<div>

## <a name="summary"></a>Résumé

L’outil ABSConfig fournit aux administrateurs un outil rapide et facile à utiliser pour personnaliser le service de carnet d’adresses Lync Server 2013.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Bandwidth Policy Service Monitor

L’outil Bandwidth Policy Service Monitor permet aux administrateurs d’afficher la liste des éléments suivants :

1.  Tous les services de stratégie de bande passante configurés pour Lync Server 2013 (authentification et noyau) dans la topologie

2.  connexions effectuées par chaque service aux autres services de stratégie de bande passante et aux serveurs Edge ;

3.  liaisons configurées dans le document de configuration du réseau et utilisation de la bande passante en temps réel, telle que signalée par les services de stratégie de bande passante individuels.

<div>

## <a name="description"></a>Description

L’outil Bandwidth Policy Service Monitor est implémenté sous la forme d’une application à interface utilisateur graphique. Les administrateurs démarrent l’outil en exécutant PDPMonUI.exe.

Lorsque l’outil démarre, il tente de découvrir la liste des services de stratégie de bande passante dans la topologie. Une fois la mise à jour initiale effectuée, le volet situé à gauche de la fenêtre reçoit une liste de services regroupés selon les clusters auxquels ils appartiennent.

Lorsque les administrateurs sélectionnent un service de stratégie de bande passante particulier, le volet situé à droite affiche les informations relatives à ce service particulier. Ce volet inclut également deux onglets principaux qui affichent des informations.

<div>

## <a name="machine-info-tab"></a>Onglet Machine Info (Informations sur l’ordinateur)

L’onglet **Machine Info (Informations sur l’ordinateur)** fournit des informations sur le service de stratégie de bande passante sélectionné, ainsi que la liste et l’état des connexions effectuées par le service de stratégie de bande passante sélectionné aux autres services.

</div>

<div>

## <a name="topology-info-tab"></a>Onglet Topology Info (Informations sur la topologie)

L’onglet **Topology Info (Informations sur la topologie)** affiche la liste des liaisons configurées dans les paramètres de configuration du réseau. Pour chaque liaison, la capacité de bande passante audio et vidéo est indiquée. La bande passante actuellement utilisée est également indiquée, en Kbps et en pourcentage de la capacité. L’outil utilise des couleurs pour mettre en valeur les liaisons dont l’utilisation atteint presque la capacité maximale afin que les administrateurs puissent les isoler rapidement.

<div>


> [!NOTE]  
>  Si l’outil Bandwidth Policy Service Monitor rencontre des défaillances lorsqu’il se connecte aux services de stratégie de la bande passante configurés, aucune information n’apparaît sous les onglets <STRONG>Machine Info (Informations sur l’ordinateur) </STRONG> et <STRONG>Topology Info (Informations sur la topologie)</STRONG>. Il est toutefois possible que l’outil se connecte avant de perdre la connexion au service. En pareil cas, les administrateurs peuvent voir des informations obsolètes. Les onglets incluent des informations d’horodatage (<STRONG>Last Updated (Dernière mise à jour)</STRONG>) qui permettent aux administrateurs de voir la date/l’heure de la dernière mise à jour des données pour un service de stratégie de bande passante particulier.



</div>

</div>

</div>

<div>

## <a name="output"></a>Sortie

Il n’y a aucune sortie de ligne de commande. La sortie du programme apparaît dans l’interface utilisateur graphique principale.

</div>

<div>

## <a name="purpose"></a>Objectif

L’outil Bandwidth Policy Service Monitor permet aux administrateurs de consulter l’état des services de stratégie de bande passante définis dans la topologie. Ils peuvent également voir l’utilisation de la bande passante en temps réel pour toutes les liaisons définies dans le document de configuration du réseau.

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil Moniteur du service de stratégie de bande passante doit être exécuté sur un ordinateur qui fait partie de la topologie du serveur Lync.

</div>

<div>

## <a name="summary"></a>Résumé

L’outil Bandwidth Policy Service Monitor est utile pour contrôler l’état des services de stratégie de bande passante dans la topologie et connaître l’utilisation de la bande passante en temps réel pour les liaisons définies dans les paramètres de configuration du réseau.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer

L’outil Bandwidth Utilization Analyzer crée des rapports sur divers affichages de la consommation de bande passante par les points de terminaison d’UC entre les liaisons de réseau étendu dans le réseau d’entreprise. Ces rapports permettent d’identifier le modèle actuel de consommation de la bande passante et de planifier la capacité de bande passante.

<div>

## <a name="description"></a>Description

Bandwidth Utilization Analyzer est implémenté sous la forme d’une application à interface utilisateur graphique. Cet outil génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau et constitue une aide pour planifier la capacité. Il traite également la capacité de bande passante affectée aux diverses liaisons par itération.

</div>

<div>

## <a name="output"></a>Sortie

Bandwidth Utilization Analyzer offre une représentation graphique de la capacité de bande passante et de l’utilisation de la bande passante audio pour les liaisons de réseau étendu configurées dans le système.

</div>

<div>

## <a name="purpose"></a>Objectif

Dans tous les déploiements voix et vidéo, il est essentiel de surveiller et comprendre les tendances d’utilisation de la bande passante par le trafic multimédia au sein du réseau de l’entreprise. L’outil Bandwidth Utilization Analyzer permet aux administrateurs d’y parvenir. L’outil effectue les opérations suivantes :

  - génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau ;

  - permet de planifier la capacité plus efficacement et de traiter la capacité de bande passante affectée aux diverses liaisons par itération.

Bandwidth Utilization Analyzer peut générer une représentation graphique des rapports sur la capacité et l’utilisation de la bande passante, comme suit :

  - liaisons de réseau étendu au sein du réseau d’entreprise ;

  - filtrage des liaisons de réseau étendu sélectionnées ;

  - filtrage des liaisons de réseau étendu ayant dépassé leur capacité ;

  - filtrage des liaisons de réseau étendu ayant sous-utilisé la bande passante approvisionnée ;

  - filtrage des liaisons de réseau étendu ayant atteint des niveaux critiques (utilisation de la bande passante supérieure à 90 % de la capacité de bande passante de la liaison de réseau étendu) ;

  - filtrage selon le type de liaison de réseau étendu (liaisons réseau-site, liaisons inter-régions et liaisons au sein d’un site) ;

  - filtrage par région réseau.

<div>

## <a name="applications"></a>Applications

Bandwidth Utilization Analyzer inclut les deux applications (outils) suivantes :

  - **WanLinkLogCollector. exe**   cet outil permet à l’utilisateur d’entrer les informations requises.

  - **BandwidthUtilizationAnalyzer. xlsm**  un rapport de feuille de calcul Microsoft Excel est automatiquement lancé par WanLinkLogCollector. exe. Cette application permet à l’utilisateur d’appliquer des filtres au rapport, comme indiqué plus loin dans cet article.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phases d’utilisation de Bandwidth Utilization Analyzer

L’utilisation de Bandwidth Utilization Analyzer implique deux phases :

  - collecte des journaux, effectuée à l’aide de WanLinkLogCollector.exe ;

  - personnalisation des rapports, effectuée à l’aide de BandwidthUtilizationAnalyzer.xlsm.

<div>


> [!IMPORTANT]  
> Il est recommandé que BandwidthUtilizationAnalyzer.xlsm ne soit pas démarré manuellement par les utilisateurs finaux.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Démarrage de Bandwidth Utilization Analyzer

Démarrez WanLinkLogCollector.exe dans une invite de commandes ou à l’aide de l’Explorateur Windows.

**Utilisation de WanLinkLogCollector.exe**

L’utilisation de WanLinkLogCollector.exe comporte trois étapes :

1.  **Journalisation la chronologie**   fournit la chronologie à laquelle le rapport doit être généré.

2.  **Spécifier les répertoires**   de fichiers pour fournir des informations sur l’emplacement des fichiers

3.  **Collecter les journaux et lancer la visionneuse**  de rapports pour exécuter la commande permettant de générer le rapport

<div>

## <a name="step-1---log-the-timeline"></a>Étape 1 - Définition de la chronologie

La définition de la chronologie permet à l’utilisateur de l’outil de spécifier les éléments suivants, comme indiqué dans la figure suivante. 

1.  **Date de début** Date de début de la chronologie pour laquelle le rapport doit être généré (par exemple, 1er août 2010).

2.  **Date de fin** Date de fin de la chronologie pour laquelle le rapport doit être généré (par exemple, 30 septembre 2010).
    
    ![Dates de début et de fin dans l’utilisation de la bande passante A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Dates de début et de fin dans l’utilisation de la bande passante A")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>Étape 2 - Définition des répertoires de fichiers

Les répertoires de fichiers suivants peuvent être spécifiés par l’utilisateur, comme indiqué.

  - **Emplacement des fichiers journaux du serveur** Emplacement du dossier dans lequel les journaux du serveur de stratégie de bande passante sont stockés. Il s’agit généralement \<de\>\\\<la sélection de\>\\FileServer\\de AppServerFiles Fe.

  - **Emplacement de stockage des fichiers temporaires** Emplacement du fichier temporaire où les fichiers intermédiaires sont stockés lors de la génération du rapport.

![Répertoires de fichiers dans l’utilisation de la bande passante anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Répertoires de fichiers dans l’utilisation de la bande passante anal")

<div>


> [!NOTE]  
> Vérifiez que l’utilisateur de l’outil dispose d’un accès suffisant aux journaux de serveur et au dossier du magasin des fichiers temporaires.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Étape 3 - Collecte des journaux et démarrage de la visionneuse de rapports

Pour collecter les journaux et démarrer la visionneuse de rapports, cliquez sur **Execute (Exécuter)** comme indiqué ci-dessous. Cette opération permet de collecter les données requises.

![Collecte de données dans la Analité de l’utilisation de la bande passante](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecte de données dans la Analité de l’utilisation de la bande passante")

Une fois le contenu saisi validé, le message suivant apparaît.

![Journaux de notification collectés dans la bande passante utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Journaux de notification collectés dans la bande passante utili")

Cliquez sur **OK**. BandwidthUtilizationAnalyzer.xlsm démarre automatiquement. Suivez les instructions du message. Pour plus d’informations, voir **Utilisation de BandwidthUtilizationAnalyzer.xlsm ** dans la section suivante.

</div>

<div>


**Utilisation de BandwidthUtilizationAnalyzer.xlsm**

1.  Une fois BandwidthUtilizationAnalyzer.xlsm démarré automatiquement, cliquez sur **Refresh (Actualiser)**, comme indiqué ci-dessous.
    
    ![BandwidthUtilizationAnalyzer. xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm  ")

2.  Si un dossier de fichiers est ouvert, sélectionnez consolidated.csv à l’emplacement spécifié dans le message, comme indiqué ci-dessous. Il indique également l’emplacement **C :\\Temp**.
    
    ![Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.")

3.  Cliquez sur **Import (Importer)**.

4.  La représentation graphique est générée automatiquement. Elle est disponible lorsque le pointeur de traitement en arrière-plan disparaît.
    
    ![Application de filtres dans le mode état.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres dans le mode état.")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>Application de filtres à l’affichage du rapport

Les filtres suivants peuvent être appliqués à l’affichage du rapport :

![Application de filtres dans le mode état.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres dans le mode état.")

1.  **Name (Nom)** Filtrage des liaisons de réseau étendu (le filtre apparaît dans la partie droite du graphique). Le préfixe représente les types de liaisons suivants (voir l’encadré bleu vertical) :
    
      - **S Site (S (site))** Liaison de réseau étendu entre un site réseau et une région réseau
    
      - **IS Inter-Site (IS (intersite))** Liaison de réseau étendu entre deux sites réseau
    
      - **R Inter-Region (R (inter-régions))** Liaison de réseau étendu entre deux régions réseau

2.  **Exceeded limit (Limite dépassée)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est supérieure à la capacité de bande passante

3.  **Critical levels (Niveaux critiques)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante a atteint 90 % ou plus de la capacité de bande passante

4.  **Under-utilized (Sous-utilisé)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est inférieure à 25 % de la capacité de bande passante

5.  **Link type (Type de liaison)** Filtrage des types de liaisons de réseau étendu suivants :
    
      - **Network site (Site réseau)**
    
      - **Inter-site (intersite)**
    
      - **Inter-Region (Inter-régions)**

6.  **Region (Région)** Filtrage de la région réseau

Les figures suivantes présentent les filtres décrits précédemment.

Filtrage sur **Name (Nom)**. Sélectionnez la liste des liaisons devant être affichées dans le graphique.

![Filtrage par nom dans BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrage par nom dans BandwidthUtilizationAnalyzer.")

Filtrage sur **Exceeded limit (Limite dépassée)**. Sélectionnez **True ** pour appliquer le filtre.

![Filtrage par limite dépassée.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrage par limite dépassée.")

Filtrage sur **Critical levels (Niveaux critiques)**. Sélectionnez **True** pour appliquer le filtre.

![Filtrage par niveaux critiques.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrage par niveaux critiques.")

Filtrage sur **Under utilized (Sous-utilisé)**. Sélectionnez **True** pour appliquer le filtre.

![Filtrage en sous utilisé.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrage en sous utilisé.")

Filtrage sur **Link Type (Type de liaison)**. Sélectionnez le ou les types devant être affichés.

![Filtrage par type de lien.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrage par type de lien.")

Filtrage sur **Region (Région)**. Sélectionnez la liste des régions pour lesquelles afficher les liaisons.

![Filtrage par région.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrage par région.")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Configuration requise

  - .NET Framework 3.5

  - Microsoft Excel 2010 ou Excel 2007

</div>

<div>

## <a name="summary"></a>Résumé

Bandwidth Utilization Analyzer permet de représenter l’utilisation de la bande passante audio pour le trafic des communications unifiées dans le réseau. Il permet également de créer des rapports sur l’utilisation de la bande passante vidéo dans le réseau.

</div>

</div>

<div>

## <a name="call-parkometer"></a>Call Parkometer

L’application en ligne de commande Call Parkometer permet d’accéder facilement à la base de données des orbites de parcage d’appel.

<div>

## <a name="description"></a>Description

L’outil Call Parkometer permet de suivre les appels actuellement parqués. Il collecte également des statistiques sur les orbites et l’utilisation du serveur de parcage d’appel. Cet outil de ligne de commande fournit les deux accès en lecture et en écriture à la base de données SQL Server de CPS orbite à partir d’un ordinateur connecté localement ou distant.

Toutes les options s’excluent mutuellement. La syntaxe suivante est appliquée à la ligne de commande :

  - 
            Paramètre **–o** : répertorie toutes les plages d’orbites configurées pour ce pool.

  - 
            Paramètre **–n** : répertorie toutes les orbites actuellement utilisées dans ce pool. Les informations suivantes sont affichées :
    
      - URI (Uniform Resource Identifier) SIP du parqué et du parqueur.
    
      - Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.
    
      - Date/heure du parcage de l’appel.

  - 
            Paramètre **–f** : indique le nombre d’orbites actuellement libres dans le pool.

  - **-r \<n\> ** paramètre : répertorie \<les\> n derniers appels parqués. Les informations suivantes sont affichées :
    
      - URI SIP du parqué.
    
      - URI SIP du parqueur.
    
      - Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.
    
      - Date/heure de récupération ou d’abandon de l’appel.

  - **-t\<n\> ** paramètre-tests de réservation d’une orbite dans la base de données pour afficher la randomisation des numéros en orbites attribués.

</div>

<div>

## <a name="output"></a>Sortie

Selon les paramètres d’entrée spécifiés dans l’invite de commandes, l’outil Call Parkometer affiche la sortie suivante :

  - plages d’orbites configurées pour ce pool ;

  - appels actuellement parqués ;

  - nombre d’orbites libres (disponibles) ;

  - appels parqués récemment ;

  - orbites réservées pour le test des valeurs d’orbite uniformes et aléatoires.

</div>

<div>

## <a name="purpose"></a>Objectif

L’outil CPS vie à fournir un accès par ligne de commande à la base de données du serveur de parcage d’appel. L’administrateur peut consulter l’utilisation du serveur de parcage d’appel et déterminer le nombre d’orbites affectées à un pool.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Aucune configuration n’est requise si cet outil est exécuté sur l’ordinateur qui exécute le serveur de parcage d’appel. Si cet outil est exécuté sur un ordinateur distant, la base de données SQL Server utilisée par Lync Server 2013 doit être configurée pour autoriser l’accès à distance. L’appel de Parkometer doit être configuré à l’aide d’une chaîne de connexion de base de données SQL Server pour se connecter au serveur SQL Server du pool. Cette chaîne de connexion de base de données SQL Server est définie dans le fichier de configuration **parkometer. exe. config**. Il doit être placé dans le même répertoire que parkometer. exe. Le fichier XML suivant est un exemple de parkometer. exe. config. Le nom d’utilisateur\\(par exemple, « monmotdepasse »), le mot de passe (par exemple, la monmotdepasse) et le nom d’hôte (par exemple, « MyServer »).

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a>Exemples

Plages d’orbites déployées : le paramètre –o répertorie les plages d’orbites configurées pour ce pool

![Plages orbites dans Parkometer d’appel.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Plages orbites dans Parkometer d’appel.")

Appels actuellement parqués : le paramètre –n répertorie les orbites actuellement utilisées sur ce pool

![Appels actuellement en cours d’appel dans Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Appels actuellement en cours d’appel dans Parkometer.")

Nombre d’orbites libres : le paramètre –f indique le nombre d’orbites actuellement libres dans le pool

![Orbites libres dans Parkometer d’appel.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Orbites libres dans Parkometer d’appel.")

Appels récemment mis en garde : le paramètre \<–\> r n \<recense\> les n derniers appels parqués, comme illustré ci-dessous.

![Appels récemment dans le Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Appels récemment dans le Parkometer.")

Test de réservation orbite : les \<tests\> de paramètre – t n servent à réapprovisionner une orbite dans la base de données, comme illustré ci-dessous.

![Testez les réservations orbites dans l’appel Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testez les réservations orbites dans l’appel Parkometer.")

</div>

<div>

## <a name="summary"></a>Résumé

L’outil en ligne de commande Call Parkometer fournit des informations détaillées sur le serveur de parcage d’appel.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

Le kit de ressources de CleanupStorageServiceData permet la suppression des données orphelines de la base de données utilisée par le service de stockage Lync Server (LYSS). La seule fonction du service de stockage consiste à mettre en tampon la communication entre Lync Server et les différents points de terminaison de stockage des données principaux tels que SQL Server et Exchange.

<div>

## <a name="description"></a>Description

Pour prendre en charge une haute disponibilité, LYSS accepte et enregistre temporairement des copies de ces données sur plusieurs serveurs frontaux du pool, et supprime ces données une fois qu’elles ont été transmises à l’emplacement de stockage de longue durée final. Dans le cas d’une opération normale, il est possible qu’il n’y ait pas de situations normales, qu’un serveur se bloque ou rencontre un problème de traitement et que certaines données ne soient pas nettoyées correctement. Ces données sont inoffensives, mais elles consomment des ressources de traitement limitées. La plupart des opérations de maintenance de données requises normales sont automatisées, mais cet outil permet d’identifier et de supprimer en toute sécurité ces données orphelines lorsque la suppression automatisée n’est pas possible. L’utilisation de cet outil est indiquée lors du déclenchement d’une alerte de système d’exploitation du gestionnaire d’intégrité, qui demande à l’administrateur de supprimer les données inutiles des bases de données LYSS locales du pool. Il s’agit d’un événement correspondant dans le journal des événements sur le front end qui déclenchait l’alerte. Les détails de l’événement contiennent les informations relatives à la quantité de données orphelines contenues sur le front end et sont déclenchées lorsque ces données dépassent certains seuils prédéfinis.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de Lync Server 2013. L’outil s’exécute sur des ordinateurs liés à un domaine dans lesquels Lync Server et Lync Server 2013 Management Shell sont installés. L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux dans la liste. Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée. Cette base de données est utilisée par l’outil CleanupStorageServiceData pour obtenir les détails de connexion nécessaires pour communiquer avec le service de routage de Lync Server. Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’autorisations en lecture/écriture sur le partage de fichiers sur lequel il souhaite écrire le journal de sortie. Par ailleurs, cet outil dépend du niveau de cohérence de l’État. Ainsi, chaque serveur frontal doit être opérationnel, l’instance SQL Server LYNCLOCAL et la base de données LYSS doivent être en mesure de se connecter, et chaque groupe de routage doit disposer d’un ensemble complet de 1 serveur frontal principal et de 2 front-end secondaires. ervers.

</div>

<div>

## <a name="examples"></a>Exemples

C :\\Program Files\\Microsoft Lync Server 2013\\reskit\\StorageService\> ImportStorageServiceData. exe

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a>DBAnalyze

<div>

## <a name="description"></a>Description

DBAnalyze est un outil de ligne de commande qui permet aux administrateurs de collecter des rapports d’analyse sur les bases de données Lync Server 2013. DBAnalyze inclut les modes suivants : diagnostic, données des utilisateurs, conférence, unités de contrôle multipoint et fragmentation des disques :

  - **Le mode**   diagnostic crée un rapport qui inclut des informations sur les tables (nombre d’enregistrements, fragmentation, la taille des données et la taille d’index), les données et les fichiers journaux, la dernière période de sauvegarde, le niveau de distribution des contacts avec les serveurs qui exécutent Microsoft Office Communications Server, le nombre moyen d’autorisations, de contacts, de conteneurs, d’abonnements, de publications, de points de terminaison par utilisateur, de personnes incorrectement hébergées Conférences, conférences actives et version de la base de données.
    
    <div>
    

    > [!NOTE]  
    > L’exécution du mode Diagnostic peut affecter les performances des serveurs.

    
    </div>

  - Le **mode**  de données utilisateur signale les données de contact, de conteneur, d’abonnement, de publication, d’autorisation et de groupe de contacts pour un utilisateur spécifié ou pour les utilisateurs qui disposent de cet utilisateur dans leurs listes de contacts et d’autorisations. Ce mode transmet également des données résumées sur les conférences organisées par un utilisateur ou auxquelles il est invité.

  - **Le mode**   de conférence rapporte des données détaillées pour une conférence spécifique, y compris tous les détails de l’horaire de la Conférence, la liste d’invités, la liste des types de médias autorisés pour la Conférence, les MCU actifs (unités de contrôle multipoint), la liste des participants actifs et l’état de signalisation de chaque participant.

  - ****  Le décodage de l’ID de réunion décode un ID de réunion RTC (réseau téléphonique commuté) spécifié par le commutateur **/pstnid** , mais ne se connecte pas à la fin des informations détaillées.

  - **Résoudre**un ID de réunion RTC qui est spécifié par le commutateur/pstnid et affiche des informations sur la Conférence indiquée par l’ID. ****    

  - **Le mode**  MCU signale l’ID, le type de média, l’URL, le statut de pulsation, le chargement de la Conférence et le chargement du participant pour chaque MCU du pool.

  - **Le mode**  de fragmentation du disque affiche l’état de fragmentation de tous les disques.

Cet outil permet de diagnostiquer plusieurs problèmes ou de planifier la capacité. Par exemple, si la plupart des utilisateurs hébergés sur un serveur A définissent des utilisateurs hébergés sur le serveur B comme contacts, l’administrateur peut déplacer les utilisateurs du serveur A vers le serveur B afin de réduire le trafic entre les serveurs.

</div>

<div>

## <a name="output"></a>Sortie

Cet outil génère des rapports prédéfinis sur la base de données Lync Server 2013. **Chemin :** % ProgramFiles%\\Microsoft Lync Server 2013\\reskit

</div>

<div>

## <a name="purpose"></a>Objectif

Pour installer DbAnalyze. exe, copiez-le dans un dossier local, puis exécutez l’outil. Pour utiliser l’outil, exécutez la commande suivante à partir de la ligne de commande.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Les descriptions des options de la ligne de commande sont décrites ci-dessous.

![Options de ligne de commande pour DbAnalyze. exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Options de ligne de commande pour DbAnalyze. exe.")

</div>

<div>

## <a name="requirements"></a>Configuration requise

**Ordinateur** DBAnalyze ne peut être exécuté qu’à partir d’un ordinateur appartenant à un domaine sur lequel Lync Server 2013 est installé.

**Réseau** L’ordinateur doit pouvoir se connecter à la base de données principale.

Le **logiciel** ; Les composants logiciels de Lync Server 2013 doivent être installés avant d’exécuter DBAnalyze.

**Utilisateurs** Le tableau ci-dessous indique les administrateurs disposant des autorisations nécessaires pour accéder aux bases de données Lync Server 2013.

![Tableau des autorisations pour DbAnalyze. exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tableau des autorisations pour DbAnalyze. exe.")

<div>


> [!NOTE]  
> Un compte d’administrateur local est nécessaire pour le mode <STRONG>/report:disk</STRONG>.



</div>

</div>

<div>

## <a name="examples"></a>Exemples

Les exemples suivants constituent des commandes Dbanalyze.exe correctes :

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>Résumé

DBAnalyzer permet aux administrateurs d’analyser rapidement et facilement des bases de données Lync Server 2013.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

L’outil de kit de ressources ImportStorageServiceData permet de réimporter les données de file d’attente et de point de terminaison éliminées du service de stockage Lync Server dans le service de stockage.

<div>

## <a name="description"></a>Description

L’élimination de données du service de stockage peut être automatique (périodique) selon le statut des éléments de file d’attente ou la taille de la base de données. Elle peut survenir suite à l’invocation manuelle de l’applet de commande de basculement du pool ou StorageServiceFullFlush (invoquée par l’applet de commande de basculement du pool). Notez que les données ne peuvent pas être réimportées si la taille de la base de données du service de stockage (LYSS) au premier plan se trouve au-dessus du niveau normal, car cela risque de provoquer une exportation supplémentaire de données. De plus, tous les problèmes susceptibles d’avoir contribué à des erreurs qui entraînaient l’augmentation de la file d’attente du service de stockage doivent être résolus (par exemple, des erreurs de point de terminaison Exchange, des problèmes de réseau ou d’autres problèmes).

**Scénario 1 :** lors du basculement du pool, les fichiers peuvent être éliminés du service de stockage de chaque serveur frontal. Une fois le basculement terminé, l’outil doit être exécuté pour réimporter les données.

**Scénario 2 :** les données sont éliminées automatiquement chaque jour ou suite au dépassement de certains seuils de taille par la base de données du service de stockage (par exemple, 60 %, 80 %, 90 % de remplissage). Ces données éliminées automatiquement doivent être régulièrement réimportées par l’administrateur. Dans le cas ci-dessus, si le Pack de contrôle SCOM n’est pas déployé, il existe des événements pour le service de stockage Lync Server relatif aux données vidées du service de stockage. Les ID d’événement 32075 (démarrage du vidage complet), 32076 (fin du vidage complet), 32082 (démarrage du vidage de niveau maintenance), 32083 (fin du vidage de niveau maintenance), 32089 (vidage effectué à cause du remplissage de la base de données). Notez que ces ID d’événement correspondent à la version finale. Lorsqu’un administrateur voit ces événements, cela signifie qu’il y a des fichiers qui ont été vidés. Ces données doivent être importées régulièrement à l’aide de cet outil, par exemple une fois par semaine.

Dans le cas d’un service en ligne, si le Pack de gestion de l’intégrité pour Lync Server est déployé, de nouvelles alertes peuvent être déclenchées qui demandent à l’administrateur de réimporter les données vidées dans le service de stockage. Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui déclenchait l’alerte. L’événement fournit une description du chemin d’accès parent sous lequel se trouvent les fichiers de données vidées, ainsi que du nombre de fichiers qui répondent aux critères d’alerte. Le critère d’alerte est que le chemin d’accès parent est inférieur ou égal à X jours (où X et Y sont prédéfinis dans le StorageService, mais peut être substitué en modifiant le fichier APPCONFIG.) Vous trouverez ci-dessous deux exemples d’événements qui peuvent déclencher l’alerte d’intégrité, en étant leur chemin parent. Il existe une possibilité de partage de fichiers de service Web, tandis que l’autre est le répertoire de données d’application local de chaque frontal. (par exemple, c\\:\\ProgramData\\Microsoft Lync\\Server StorageService). L’administrateur doit alors exécuter cet outil reskit.

Cet outil augmente la charge processeur et d’E/S sur le serveur frontal sur lequel il est exécuté, ainsi que sur les autre serveurs frontaux, si les données n’appartiennent pas au serveur frontal sur lequel l’outil est exécuté. Il est recommandé d’exécuter cet outil lorsque les serveurs frontaux ne sont pas soumis à une charge processeur et d’E/S importante, par exemple en dehors des heures de pointe. Deuxièmement, cet outil peut prendre 2 à 3 minutes pour importer un fichier de données. Tenez compte de ce qui suit lors de l’estimation de la durée d’exécution de l’outil. Par défaut, le fichier journal détaillé généré par l’outil apparaît sur le magasin de fichiers. Supprimez-le si aucune erreur n’est signalée, car la taille de celui-ci peut atteindre plusieurs Mo, voire davantage.

![Exemples de journaux d’événements du serveur de stockage.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Exemples de journaux d’événements du serveur de stockage.")

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de Lync Server 2013. L’outil s’exécute sur des ordinateurs liés à un domaine dans lesquels Lync Server et Lync Server Management Shell sont installés. L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux de la liste. Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée. Cette base de données est utilisée par l’outil pour récupérer l’emplacement du partage de fichiers WebService pour le pool. Par ailleurs, avant d’utiliser l’outil, chaque serveur frontal doit d’abord activer l’accès distant Windows PowerShell à l’aide de **Enable-PSRemoting** sur chaque serveur frontal, ainsi que de l’ordinateur à partir duquel l’outil est exécuté. Dans le cas contraire, les commandes Windows PowerShell distantes de cet outil échoueront. La fonctionnalité d’accès distant de Windows PowerShell peut être désactivée sur tous les serveurs frontaux de la liste une fois l’opération terminée. Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’autorisations en lecture/écriture sur le partage de fichiers WebPart pour le pool sur lequel ils exécutent cet outil. Dans le cas contraire, l’outil échoue avec des erreurs d’autorisation d’e/s.

<div>


> [!NOTE]  
> Sur Windows Server 2012, la mise à niveau de Windows PowerShell est activée par défaut, mais pas sur le système d’exploitation Windows Server 2008.



</div>

</div>

<div>

## <a name="examples"></a>Exemples

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a>LCSSync

L’outil LCSSync facilite le déploiement du logiciel de communication Lync Server 2013 dans un environnement multiforêt. Cet outil permet de synchroniser des utilisateurs et des groupes à partir de forêts utilisateur différentes en tant qu’objet de contact services de domaine Active Directory (AD FS) à une forêt centrale sur laquelle Lync Server 2013 est installé.

<div>

## <a name="description"></a>Description

LCSSync utilise les objets de contact des services de domaine Active Directory synchronisés dans la forêt centrale pour permettre aux utilisateurs de Lync Server. Pour fournir une connexion unique, le compte d’utilisateur principal doit être mappé à l’objet de contact services de domaine Active Directory (AD FS) dans la forêt centrale de Lync Server 2013. Cet outil aide à effectuer l’opération de mappage. Il fournit des modèles pour la création des agents de gestion dans Microsoft Identity Integration Server.

</div>

<div>

## <a name="summary"></a>Résumé

L’outil LCSSync facilite le déploiement de Lync Server dans un environnement multiforêt.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

L’outil LookupUserConsole affiche des informations de routage internes de Lync Server concernant des utilisateurs spécifiques. Ces informations peuvent être utiles au personnel du support technique Microsoft dans le cadre du diagnostic des problèmes de déploiement et de routage.

<div>

## <a name="description"></a>Description

L’exécution de LookupUserConsole. exe entraîne l’ouverture d’une invite de commandes qui accepte les adresses SIP et tente d’afficher des informations de routage internes du serveur Lync associées. Tapez **exit** pour quitter l’outil LookupUserConsole.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de Lync Server 2013. L’outil s’exécute sur des ordinateurs liés à un domaine sur lesquels Lync Server est installé

</div>

<div>

## <a name="examples"></a>Exemples

C :\\fichiers\\programme Microsoft Lync Server 2013\\reskit\>LookupUserConsole. exe

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

L’outil MSTurnPing permet à un administrateur de logiciels de communications Microsoft Lync Server 2013 de vérifier l’état des serveurs exécutant les services d’authentification par périphérique audio et vidéo, ainsi que les serveurs qui exécutent des services de stratégie de bande passante dans la topologie.

<div>

## <a name="description"></a>Description

L’outil MSTurnPing permet à un administrateur de logiciels de communication de Lync Server 2013 de vérifier l’état des serveurs exécutant les services d’authentification par périphérique audio/vidéo et audio/vidéo, ainsi que les serveurs qui exécutent des services de stratégie de bande passante dans la topologie.

L’outil permet d’effectuer les tests suivants :

1.  Test des serveurs Edge A/V : l’outil effectue des tests sur tous les serveurs Edge A/V dans la topologie comme suit :
    
      - Vérifier que le service d’authentification audio/vidéo de Lync Server est démarré et peut fournir des informations d’identification appropriées.
    
      - Vérifier que le service Edge audio/vidéo de Lync Server est démarré et peut allouer correctement les ressources sur le bord externe.

2.  Test des services de stratégie de bande passante : l’outil effectue des tests sur tous les serveurs exécutant les services de stratégie de bande passante dans la topologie comme suit :
    
      - Vérifier que le service de stratégie de bande passante de Lync Server (authentification) est démarré et peut fournir des informations d’identification appropriées.
    
      - Vérifier que le service de stratégie de bande passante de Lync Server (cœur) est démarré et peut procéder à la vérification de la bande passante.

Cet outil doit être exécuté à partir d’un ordinateur qui fait partie de la topologie et sur lequel le magasin local est installé. 

</div>

<div>

## <a name="output"></a>Sortie

L’outil génère des résultats pour chacune des opérations.

  - Pour le test **AudioVideoEdgeServer**, l’outil génère les résultats suivants :
    
      - Les résultats des tests pour les ordinateurs qui fournissent le service d’authentification audio/vidéo de Lync Server dans la topologie ;
    
      - Les résultats des tests pour les ordinateurs qui fournissent le service Edge audio/vidéo de Lync Server dans la topologie

  - Pour le test **BandwidthPolicyServer**, l’outil génère les résultats suivants :
    
      - Les résultats des tests pour les ordinateurs qui fournissent le service de stratégie de bande passante Lync Server (authentification) dans la topologie ;
    
      - Les résultats des tests pour les ordinateurs qui fournissent le service de stratégie de bande passante Lync Server (cœur) dans la topologie ;

</div>

<div>

## <a name="requirements"></a>Configuration requise

  - Cet outil doit être exécuté à partir d’un ordinateur de la topologie sur lequel le magasin local est installé.

  - L’outil doit être exécuté par un administrateur ayant accès au magasin local.

</div>

<div>

## <a name="examples"></a>Exemples

Voici un exemple de saisie pour l’outil.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>Résumé

Cet outil peut être utile pour les administrateurs de Lync Server 2013 qui souhaitent vérifier l’état des serveurs qui exécutent les services audio/vidéo et de stratégie de bande passante.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Network Configuration Viewer

La visionneuse de configuration réseau peut être utilisée par les administrateurs de logiciels de communications de Microsoft Lync Server 2013 pour afficher la topologie de réseau de contrôle d’admission des appels (CAC) pour une entreprise mise en service pour autoriser les sessions de communication en temps réel, comme les appels vocaux ou appels vidéo en fonction de la capacité de bande passante spécifiée. Les administrateurs de Lync Server 2013 définissent des stratégies CAC qui sont appliquées par les services de stratégie de bande passante installés avec Lync Server 2013.

<div>

## <a name="description"></a>Description

Network Configuration Viewer (NetworkConfigurationViewer.exe) permet aux administrateurs d’effectuer les tâches suivantes :

  - Chargez et affichez la topologie de réseau CAC à partir d’un déploiement 2013 Lync Server dans un format graphique.

  - charger et afficher la topologie réseau de contrôle d’admission des appels à partir d‘un fichier journal de serveur de stratégie de bande passante dans un format graphique ;

  - enregistrer et stocker la topologie réseau de contrôle d’admission des appels dans un format XML sur le disque ;

  - enregistrer et stocker le diagramme de la topologie réseau de contrôle d’admission des appels au format JPG ou BMP ;

  - afficher les données de configuration de la topologie réseau de contrôle d’admission des appels ;

  - afficher la topologie réseau de contrôle d’admission des appels dans une arborescence ;

  - définir des connecteurs personnalisés pour les liaisons de la topologie réseau de contrôle d’admission des appels (par exemple, liaisons site-région, région-région et site-site) ;

  - afficher les informations de site, informations de région, stratégies de bande passante et liaisons réseau approvisionnées de la topologie réseau de contrôle d’admission des appels.

</div>

<div>

## <a name="purpose"></a>Objectif

Afficher les liaisons de la topologie réseau de contrôle d’admission des appels dans une interface graphique.

</div>

<div>

## <a name="examples"></a>Exemples

**Chargez et affichez la topologie de réseau CAC à partir d’un déploiement 2013 Lync Server dans un format graphique :** Les administrateurs de Lync Server 2013 peuvent charger et afficher la configuration topologique du réseau CAC sur n’importe quel ordinateur Lync Server 2013 à l’aide de l’option **Télécharger la configuration réseau** , comme illustré dans la figure ci-dessous. L’outil ne parvient pas à télécharger ou à afficher une telle configuration lors de son déploiement sur un ordinateur qui n’est pas connecté au magasin de configuration Lync.

![Téléchargement de la configuration réseau.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Téléchargement de la configuration réseau.")

**Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal du serveur de stratégie de bande passante dans un format graphique :** Les serveurs de stratégie de bande passante Lync Server 2013 enregistrent la topologie du réseau CAC dans le cadre du mécanisme de journalisation dans l’emplacement du partage de fichiers 2013 Server. Les administrateurs de Lync Server peuvent afficher ce type de fichier dans un format graphique à l’aide de l’option **ouvrir la configuration réseau** , comme illustré ci-dessous.

![Ouverture d’un fichier journal du serveur de stratégie de bande passante.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Ouverture d’un fichier journal du serveur de stratégie de bande passante.")

Enregistrer et stocker la topologie de réseau CAC au format XML sur le disque : les administrateurs de Lync Server 2013 peuvent enregistrer le fichier de configuration de topologie de réseau CAC au format XML en utilisant l’option **enregistrer une copie de la configuration réseau** , comme illustré ci-dessous. Le fichier de configuration enregistré peut ensuite être utilisé en mode hors connexion à des fins d’affichage graphique.

![Enregistrez la configuration réseau sous forme de fichier XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Enregistrez la configuration réseau sous forme de fichier XML.")

Enregistrez et stockez le diagramme de topologie du réseau CAC au format JPG ou BMP : les administrateurs de Lync Server 2013 peuvent enregistrer la configuration de topologie de réseau CAC dans des formats de fichiers JPG et BMP en utilisant l’option **enregistrer le diagramme de configuration réseau en tant qu’image** , comme illustré ci-dessous.

![Enregistrez la configuration réseau en tant qu’image.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Enregistrez la configuration réseau en tant qu’image.")

**Afficher les données de configuration de la topologie du réseau CAC :** Les administrateurs de Lync Server 2013 peuvent afficher les données de configuration du réseau associées, telles que les régions réseau, les sites réseau, les profils de bande passante et les adresses IP de sous-réseau du site, en utilisant l’option Afficher les données de configuration du réseau, comme illustré ci-dessous.

![Affichage des données de configuration du réseau.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Affichage des données de configuration du réseau.")

**Voir la topologie du réseau CAC dans un style d’arborescence :** Les administrateurs de Lync Server 2013 peuvent afficher les données de configuration du réseau associées dans un style d’affichage d’arborescence graphique à l’aide du panneau de configuration sur le côté gauche de la fenêtre d’outils, comme illustré ci-dessous.

![Afficher les données de configuration du réseau dans une arborescence.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Afficher les données de configuration du réseau dans une arborescence.")

**Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (par exemple, les liens de site à zone, de région à zone et de site à site) :** Les administrateurs de Lync Server 2013 peuvent définir des connecteurs graphiques personnalisés pour les liaisons réseau WAN de configuration réseau CAC en utilisant l’option paramètres, comme illustré ci-dessous. Ceci permet de différencier divers types de liaisons réseau approvisionnées dans la configuration du réseau.

![Définir des connecteurs personnalisés pour la topologie de réseau CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Définir des connecteurs personnalisés pour la topologie de réseau CAC")

**Affichez les informations de site et les stratégies de bande passante approvisionnées du réseau CAC.** Les administrateurs de Lync Server 2013 peuvent afficher les informations relatives à la région du réseau CAC, les informations du site et les informations de configuration de la bande passante CAC en utilisant les options ci-dessous. (Par exemple, cliquez sur **informations** dans une région réseau ou un objet de site réseau.)

![Définition de connecteurs personnalisés pour votre réseau.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Définition de connecteurs personnalisés pour votre réseau.")

</div>

<div>

## <a name="summary"></a>Résumé

Cet outil peut être utile pour les administrateurs de Lync Server 2013 qui aimeraient voir la topologie de réseau CAC pour leur déploiement sous forme graphique.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Response Group Agent Live

L’application Response Group permet aux agents d’accéder à des informations utiles en temps réel via son service web intégré. Aucun affichage graphique de ces données n’est toutefois disponible en dehors de l’application. Pour résoudre ce problème, l’outil Response Group agent pour le kit de ressources techniques permet d’accéder à ces informations de manière simple et graphique, ainsi que des informations sur le logiciel de communications Microsoft Lync 2013 en temps réel, comme la présence d’autres agents.

<div>

## <a name="description"></a>Description

L’application Windows Response Group Agent Live fournit des fonctionnalités de connexion et de déconnexion et donne des informations en temps réel (appartenance aux groupes, nombre actuel d’appels, etc.) aux agents Response Group. Il s’agit d’une version améliorée de la page groupes d’agents (accessible à partir de Lync 2013.

</div>

<div>

## <a name="purpose"></a>Objectif

L’application Response Group place les appels entrants en file d’attente avant de les acheminer vers des groupes d’agents. Pour identifier les appels à traiter de façon appropriée, les agents peuvent accéder à des informations en temps réel sur leurs groupes d’agents (agents disponibles, nombre d’appels en attente dans chaque file d’attente, etc.). Ces informations, à l’origine accessibles via le service Response Group uniquement, sont mises à disposition de façon intuitive par Response Group Agent Live.

<div>

## <a name="features"></a>Fonctionnalités

L’outil Live Response agent agent est intégré au service Response Group et au kit de développement logiciel (SDK) Microsoft Lync 2013. Il fournit aux agents Response Group les informations et fonctionnalités disponibles via le service Response Group (appartenance à des groupes, présence des autres agents, nombre d’appels en attente, etc.).

La figure suivante illustre l’interface principale de Response Group Agent Live.

![Outil en ligne de l’agent Response Group.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Outil en ligne de l’agent Response Group.")

Les trois fonctionnalités principales suivantes sont accessibles aux agents dans Response Group Agent Live :

  - **Se connecter/** déconnecter : Contrairement à la page groupes d’agents (accessible à partir de Lync 2013), l’agent Response Group n’autorise que les agents à se connecter ou se déconnecter de tous les groupes d’agents en même temps. Cette application propose trois méthodes rapides pour la connexion ou la déconnexion des agents :
    
      - Cliquer sur les boutons Sign-in/out (Connexion/Déconnexion) (vert et rouge) dans l’application.
    
      - Cliquer avec le bouton droit sur la barre d’état système, et sélectionner Sign in (Connexion) ou Sign out (Déconnexion).
    
      - Utiliser des raccourcis clavier configurables.

  - **Appartenance à un groupe :** Lorsqu’un groupe d’agent est sélectionné, l’option agent de Response Group affiche la liste des agents de ce groupe dans le volet droit. Si Lync 2013 est en cours d’exécution sur le même ordinateur que cette application, les informations de présence et la carte de visite s’affichent dans l’agent Response Group en direct. Les agents peuvent envoyer un message instantané ou appeler d’autres agents directement depuis là.

  - **Statistiques en temps réel :** Response Group Agent Live fournit des statistiques en temps réel pour tous les groupes d’agents. La fréquence de mise à jour est d’une minute. Lorsqu’un Response Group répond à un appel, un indicateur visuel est ajouté près du nom du groupe et le nombre actuel d’appels placés en file d’attente est indiqué. Pour afficher le délai d’attente le plus long, il suffit de placer le pointeur de la souris sur un groupe.

</div>

</div>

<div>

## <a name="requirements"></a>Configuration requise

Response Group Agent Live nécessite .NET Framework 4.0. Par ailleurs, pour tirer parti des fonctionnalités de présence et de carte de visite, Lync 2013 doit être installé en local (et être en cours d’exécution).

<div>

## <a name="configuration"></a>Configuration

Response Group Agent Live peut être personnalisé selon les préférences individuelles via la boîte de dialogue Options de l’application. L’administrateur peut également définir l’adresse de l’hôte par défaut en modifiant directement la propriété defaultHostAddress du fichier RGAgentLive.exe.config.

La figure suivante illustre la boîte de dialogue Options qui permet aux agents de configurer l’adresse de l’hôte et les raccourcis clavier. Pour accéder à cette boîte de dialogue, il suffit de cliquer sur le bouton Options dans la partie supérieure droite de l’interface principale.

![Boîte de dialogue Options d’agent de Response Group.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Boîte de dialogue Options d’agent de Response Group.")

Les trois paramètres suivants peuvent être personnalisés dans la configuration de Response Group Agent Live :

  - Host address (Adresse de l’hôte) : il s’agit généralement du nom de domaine complet du pool web appartenant au pool d’accueil de l’agent. L’adresse exacte du service Response Group est dérivée automatiquement en arrière-plan à partir de ces informations (en ajoutant le chemin d’accès correct après l’hôte).

  - Shortcuts (Raccourcis) : les raccourcis exacts pour la connexion/déconnexion peuvent être personnalisés. La seule limitation impose aux raccourcis d’inclure la touche du logo Windows (en plus d’une ou plusieurs autres touches).

  - Start with Windows (Démarrer avec Windows) : l’application peut être configurée pour démarrer automatiquement avec Windows.

</div>

</div>

<div>

## <a name="examples"></a>Exemples

La figure suivante illustre l’appel d’un autre agent ou l’envoi d’un message instantané à un autre agent en cliquant avec le bouton droit sur le contact dans le volet droit.

![Passer un appel ou envoyer un message instantané.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Passer un appel ou envoyer un message instantané.")

La figure suivante illustre l’affichage par Response Group Agent Live du nombre actuel d’appels dans la file d’attente et le délai d’attente le plus long parmi tous les appels entrants.

![Affichage des informations de la file d’attente.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Affichage des informations de la file d’attente.")

</div>

<div>

## <a name="summary"></a>Résumé

Les connexion et déconnexion rapides, l’appartenance aux groupes et les statistiques de base en temps réel constituent des fonctionnalités intéressantes de Response Group Agent seulement disponibles en dehors de l’application à partir du service Response Group. À l’aide de l’outil de gestion des ressources de l’agent Response Group, les administrateurs Lync peuvent fournir à leurs agents une application Windows qui leur permet d’effectuer des tâches de manière plus rapide et graphique.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

L’outil de ligne de commande SEFAUtil (activation d’extension secondaire) est un outil de ligne de commande qui permet aux administrateurs de logiciels de communications Microsoft Lync 2013 Server et aux agents de support technique de configurer la sonnerie de délégué, le transfert d’appel, les sonneries simultanées, les appels d’équipe paramètres et cueillette de groupe pour le compte d’un utilisateur de Lync Server 2013. L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. L’outil SEFAUtil permet à l’administrateur d’activer/désactiver/modifier le transfert d’appel ou la sonnerie simultanée pour le compte de l’utilisateur. L’administrateur peut spécifier la cible (sous la forme d’un URI SIP) ou utiliser une cible qui a déjà été publiée par l’utilisateur. Cet outil permet également aux administrateurs d’ajouter ou de supprimer des délégués ou des membres du groupe d’appel d’équipe pour le compte de l’utilisateur. Cet outil est bâti sur le 3,0 de Microsoft Unified Communications Management API (UCMA) et nécessite que les administrateurs créent une application fiable dans le magasin central de gestion pour SEFAUtil

SEFAUtil (activation de la fonctionnalité d’extension secondaire) permet aux administrateurs et aux agents d’assistance technique de Lync Server 2013 de configurer la sonnerie de délégué, le transfert d’appel, la sonnerie simultanée, les paramètres d’appel d’équipe et le prélèvement d’appels de groupe pour le compte d’un utilisateur de Lync Server 2013 . L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.

<div>

## <a name="description"></a>Description

La version actuelle de SEFAUtil n’est qu’un outil en ligne de commande, sans interface utilisateur graphique. Cet outil repose sur le 3,0 de Microsoft Unified Communications Managed API (UCMA). Ses fonctionnalités permettent aux administrateurs et agents du support technique d’effectuer les tâches suivantes :

  - afficher les paramètres de routage des appels d’un utilisateur (transfert d’appel, délégation, sonnerie simultanée, appel d’équipe et prise d’appel de groupe inclus) ;

  - activer/désactiver/modifier les paramètres de transfert d’appel (destination et minuteur d’absence de réponse inclus) ;

  - activer/désactiver/modifier les configurations immédiates de transfert d’appel ;

  - activer/désactiver/modifier les paramètres de délégation ;

  - activer/désactiver/modifier les paramètres d’appel d’équipe ;
    
    <div>
    

    > [!NOTE]  
    > Nouveautés de l’outil SEFAUtil de Lync Server 2013

    
    </div>

  - activer/désactiver/modifier les paramètres de sonnerie simultanée (destination incluse) ;
    
    <div>
    

    > [!NOTE]  
    > Nouveautés de l’outil SEFAUtil de Lync Server 2013

    
    </div>

  - activer/désactiver/modifier les paramètres de prise d’appel de groupe.
    
    <div>
    

    > [!WARNING]  
    > Nouveautés de l’outil SEFAUtil de Lync Server 2013

    
    </div>

Cet outil présente les limitations suivantes :

  - Pris en charge uniquement pour les utilisateurs hébergés dans un pool de serveurs Lync

  - modification en bloc des paramètres de routage des appels de plusieurs utilisateurs non prise en charge.

</div>

<div>

## <a name="output"></a>Sortie

La version actuelle de cet outil génère une sortie dans la fenêtre d’invite de commandes uniquement. Pour plus d’informations, voir la section Exemples plus loin dans ce document.

</div>

<div>

## <a name="purpose"></a>Objectif

Voici certains des principaux scénarios d’utilisation de cet outil :

  - Bob est une direction qui a été déplacée vers la téléphonie de Lync Server. Il dispose d’une délégation sur son système PBX existant. Dans le cadre de la migration vers Lync, l’administrateur est en mesure de configurer le routage de Bob pour refléter sa configuration de délégation existante.

  - En plein déplacement, Alice réalise qu’elle attend un appel important d’un de ses clients. Elle se trouve toutefois à l’hôtel et n’a accès à aucun ordinateur. Elle contacte le support technique pour leur demander de transférer vers son numéro de téléphone portable tous les appels reçus sur son numéro de téléphone professionnel. Les membres du personnel du support technique peuvent effectuer cette opération de configuration pour elle.

  - Les appels reçus par Jean sur son numéro de téléphone professionnel sont transférés vers la messagerie vocale de son téléphone portable lorsqu’il se trouve sur son lieu de travail. Pour autant, tout semble fonctionner correctement dans la plupart des autres endroits. Le technicien du support technique consulte la configuration de routage de Jean et découvre que la sonnerie simultanée est configurée sur le téléphone portable de Jean. Il interroge Jean sur la couverture mobile sur son lieu de travail et parvient à déterminer que la règle de sonnerie simultanée est à l’origine du transfert des appels vers le messagerie vocale du téléphone portable de Jean lorsque sa couverture réseau est médiocre.

  - Michel est un nouvel employé de contoso et il rejoint une nouvelle équipe sur laquelle tous les membres sont configurés pour l’appel d’équipe, lorsque l’application est activée pour Microsoft Lync, l’administrateur est en mesure de définir les paramètres du groupe d’appel d’équipe afin d’inclure tous les nouveaux membres de l’équipe, en plus du un administrateur ajoute Michel en tant que membre du groupe d’appel d’équipe pour chacun des membres de son équipe.

  - Une pratique du service client dépendant du service Ressources humaines de Contoso consiste à offrir un service personnel à tous les appelants dès le premier appel. Tous les membres du service étant assis à proximité les uns des autres, la sonnerie de tous les téléphones en même temps en raison de l’activation de l’appel d’équipe est très perturbant pour le personnel. Pour fournir le meilleur service sans perturber les membres de l’équipe, l’administrateur de Lync tire parti de la fonctionnalité de cueillette des appels de groupe. Il ajoute tous les membres du service à un groupe de prise d’appel et communique le numéro de ce groupe au service. Pierre remarque que le téléphone de Samira sonne, alors que celle-ci s’est absentée, et prend donc l’appel à partir de son propre bureau.

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil SEFAUtil peut seulement être exécuté sur un ordinateur faisant partie d’un pool d’applications approuvées. UCMA 3.0 doit être installé sur cet ordinateur. Pour exécuter l’outil, une application approuvée avec l’ID d’application SEFAUtil doit être créée sur ce pool.

**Création d’une application approuvée pour l’outil SEFAUtil**

1.  L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées. Le cas échéant, l’ajout d’un pool en tant que nouveau pool d’applications approuvé peut être réalisé via Lync Server Management Shell avec l’applet de commande suivante :
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > UCMA 3.0 doit être installé sur les ordinateurs qui seront utilisés pour exécuter l’outil SEFAUtil.

    
    </div>

2.  Une application approuvée doit être définie dans la topologie pour l’outil SEFAUtil. Pour définir SEFAUtil en tant que nouvelle application fiable, utilisez Lync Server Management Shell et exécutez l’applet de commande suivante :
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Un autre port peut être utilisé au besoin.

    
    </div>

3.  Les modifications apportées à la topologie doivent être activées. Il est possible d’activer les changements de topologie via Lync Server Management Shell en exécutant l’applet de commande suivante :
    
        Enable-CsToplogy

4.  Le cas échéant, installez les outils du kit de ressources de Lync Server 2013 sur le serveur qui sera utilisé pour exécuter l’outil SEFAUtil (le serveur doit faire partie d’un pool d’applications approuvé).

5.  Vérifiez que SEFAUtil est correctement exécuté. Pour ce faire, exécutez l’outil à partir d’une invite de commandes de Windows avec des privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement. Par défaut, l’outil se trouve dans la section : "... \\Fichiers\\programme Microsoft Lync Server 2013\\reskit. Pour afficher les paramètres de transfert d’appel d’un utilisateur, utilisez la commande suivante :
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Les paramètres de transfert d’appel de l’utilisateur doivent s’afficher.

<div>

## <a name="group-call-pickup"></a>Prise d’appel de groupe

La collecte d’appels de groupe nécessite une configuration supplémentaire dans Lync Server pour que la fonctionnalité soit entièrement activée. Avant d’affecter les groupes de prise d’appels aux utilisateurs, consultez la documentation sur la prise d’appel de groupe pour connaître les étapes de planification et de déploiement de cette fonctionnalité.

</div>

</div>

<div>

## <a name="examples"></a>Exemples

<div>

## <a name="display-current-call-handling-settings"></a>Afficher les paramètres actuels de gestion des appels

La commande suivante affiche le traitement des appels pour l’utilisateur. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> Cet exemple utilise le commutateur <STRONG>/Server</STRONG> pour spécifier le serveur Lync auquel se connecter.



</div>

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>Définir la destination du transfert d’appel/en cas d’absence de réponse

Cet exemple définit la destination d’appel/non de réponse et le délai de sonnerie. Ici, le commutateur/Server n’est pas fourni ; SEFAUtil tente de découvrir automatiquement le serveur Lync.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>Activer le transfert d’appel immédiatement

Cet exemple active immédiatement le transfert d’appel vers un autre utilisateur.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>Désactiver immédiatement le transfert d’appel

Cet exemple désactivé immédiatement le transfert d’appel.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Ajouter un utilisateur en tant que délégué et définir la sonnerie simultanée des délégués

Cet exemple ajoute un utilisateur en tant que délégué et définit la sonnerie simultanée des délégués.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>Modifier la règle de sonnerie simultanée des délégués

Cet exemple modifie la règle de sonnerie simultanée définie dans l’exemple précédent en règle de sonnerie différée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>Supprimer le délégué

Cet exemple supprime le délégué.

<div>


> [!NOTE]  
> Une fois le dernier délégué supprimé, la sonnerie sur le poste de délégués est désactivée automatiquement.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Ajouter un délégué et définir la règle de transfert d’appel aux délégués

Cet exemple ajoute un délégué et définit la règle de transfert d’appel aux délégués.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Activer la sonnerie simultanée et définir un numéro de destination

Cet exemple active la sonnerie simultanée et définit un numéro de destination pour la sonnerie simultanée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> Pour modifier le numéro de destination de la sonnerie simultanée d’un utilisateur pour lequel la sonnerie simultanée est déjà activée, conservez la commande avec le commutateur /enablesimulring, sans quoi le numéro de destination ne sera pas modifié.



</div>

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>Désactiver la sonnerie simultanée

Cet exemple désactive la sonnerie simultanée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Ajouter un membre d’équipe pour l’appel d’équipe et définir la sonnerie simultanée sur le groupe d’appel d’équipe

Cet exemple ajoute un membre d’équipe au groupe d’appel d’équipe d’un utilisateur et active la sonnerie simultanée sur le groupe d’appel d’équipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> L’ajout d’un membre au groupe d’appel d’équipe d’un utilisateur définit automatiquement les paramètres de sonnerie simultanée des utilisateurs sur la sonnerie simultanée de son groupe d’appel d’équipe.



</div>

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>Supprimer un membre du groupe d’appel d’équipe

Cet exemple supprime un membre d’équipe du groupe d’appel d’équipe d’un utilisateur.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> Si le membre supprimé est le seul du groupe d’appel d’équipe, la sonnerie simultanée du groupe d’appel d’équipe est automatiquement désactivée.



</div>

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>Définir la sonnerie différée sur le groupe d’appel d’équipe

Cet exemple définit la sonnerie différée sur le paramètre d’heure du groupe d’appel d’équipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Activer l’appel d’équipe

Cet exemple active l’appel d’équipe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> S’il n’y a aucun membre dans le groupe d’appel d’équipe de l’utilisateur, l’appel d’équipe ne sera pas activé.



</div>

**Sortie**

</div>

<div>

## <a name="disable-team-call"></a>Désactiver l’appel d’équipe

Cet exemple désactive l’appel d’équipe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Activer la prise d’appel de groupe et affecter un groupe de prise d’appel à un utilisateur

Cet exemple affecte un groupe de prise d’appel à un utilisateur et active la prise d’appel de groupe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>Désactiver la prise d’appel de groupe

Cet exemple désactive la prise d’appel de groupe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe affecté à cet utilisateur n’est pas conservé. Si vous souhaitez ultérieurement réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réaffecter le numéro de groupe avec le commutateur /enablegrouppickup.



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep.ps1

<div>

## <a name="description"></a>Description

SYSPrep. ps1 est un script Windows PowerShell qui installe les conditions préalables de Lync Server 2013 suivantes sur votre ordinateur de système d’exploitation Windows Server 2008.

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express ;

  - Windows Powershell version 3.0

  - Visual C++ 2010 Redistributable

  - Mises à jour d’Internet Information Services

  - Windows Identity Foundation

  - Fichiers principaux de Lync Server 2013

Si le nom du script est semblable à l’outil de préparation du système pour les systèmes d’exploitation Microsoft Windows, ils sont toutefois différents. Ce script installe uniquement les prérequis requis pour Lync Server 2013. Une fois ceux-ci installés, l’outil Windows SYSPrep peut ensuite être utilisé pour créer une image du serveur.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Avant d’exécuter le script SYSPrep. ps1, vous devez copier les fichiers requis vers un dossier local de l’ordinateur du système d’exploitation Windows Server 2008 (par exemple **,\\D : Setup)**. Ce dossier doit également inclure une copie des fichiers 2013 Lync Server, en particulier **Setup. exe.** Les fichiers des logiciels prérequis peuvent être téléchargés aux emplacements suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Logiciels prérequis</th>
<th>Emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .Net Framework 4.5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows Powershell version 3.0</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 Redistributable</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour d’Internet Information Services</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup. exe</p></td>
<td><p>Copier à partir de la version média de Lync Server 2013</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>Paramètre

Le paramètre **–SetupFolder** prend comme argument l’emplacement de répertoire des fichiers prérequis.

</div>

<div>

## <a name="examples"></a>Exemples

Pour exécuter le script SYSPrep. ps1 et installer les prérequis Lync Server 2013, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges :

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration

L’outil de migration annonces du numéro non attribué permet à un administrateur de Lync de déplacer la configuration des numéros non attribués, qui est mise en service par l’application d’annonce à partir d’un serveur ou d’un pool Lync source vers un serveur ou un pool Lync de destination.

<div>

## <a name="description"></a>Description

L’outil Unassigned Number Announcements Migration est un script Windows PowerShell qui déplace la configuration des numéros non attribués pris en charge par l’application d’annonce entre un pool ou un serveur source et un autre pool ou serveur.

Lorsqu’il est exécuté, le script Unassigned Number Announcements Migration effectue les opérations suivantes :

1.  Déplacer tous les fichiers audio utilisés par les annonces de numéros non attribués de l’application d’annonce hébergée sur le pool ou serveur source vers le magasin de fichiers du pool ou serveur de destination.
    
    <div>
    

    > [!NOTE]  
    > les fichiers audio sont supprimés du pool de sources une fois qu’ils sont copiés sur le pool de destination.

    
    </div>

2.  Déplacer les annonces de numéros non attribués configurées pour l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.

3.  Réaffecter toutes les plages de numéros non attribués prises en charge par l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.

Une fois le script correctement exécuté, toutes les plages de numéros affectés prises en charge par l’application d’annonce hébergée dans le pool ou serveur source sont à présent prises en charge avec la même configuration par le pool ou le serveur de destination.

</div>

<div>

## <a name="output"></a>Sortie

Le script **Move-CsAnnouncementConfiguration** indique dans la fenêtre Lync Management Shell à partir de laquelle il a exécuté la réussite ou l’échec de l’opération de migration.

Si l’exécution de l’opération est interrompue par une erreur, les plages de numéros non attribués correctement déplacées vers la destination sont conservées dans la destination sous une forme opérationnelle et le reste des plages de numéros non attribués à migrer sont conservés dans la source sous une forme opérationnelle également. Pour migrer entièrement le reste de la configuration, exécutez à nouveau le script après avoir traité l’erreur.

</div>

<div>

## <a name="purpose"></a>Objectif

Le script Unassigned Number Announcements Migration peut être utilisé dans le cadre des scénarios suivants :

  - **Migration des paramètres de configuration vers une nouvelle version de Lync Server :** Contoso est en train de migrer vers Lync Server 2013 et dans le cadre du processus de migration, l’administrateur du serveur Lync souhaite déplacer la configuration des numéros non attribués servi par l’application de l’annonce à partir du déploiement de Lync Server 2010 vers le nouveau déploiement Lync Server 2013. Pour modifier les paramètres de configuration, l’administrateur du serveur Lync utilise l’outil de migration annonces du numéro non attribué.

  - **Restauration d’un déploiement de Lync server 2013 vers Lync server 2010 :** En raison de facteurs inattendus, contoso doit restaurer la migration vers le nouveau déploiement Lync Server 2013. Pour limiter les perturbations du service, l’administrateur du serveur Lync utilise l’outil de migration annonces de numéros non attribués pour rétablir la configuration du déploiement de Lync Server 2013 sur le déploiement de Lync Server 2010.

  - **Déplacer des données entre des déploiements Lync :** Contoso est en train de remplacer tous les serveurs d’un pool par des serveurs plus récents. Sa stratégie consiste à déployer un nouveau pool Lync Server 2013, à déplacer toutes les données de l’ancien vers le nouveau pool, puis à déconseiller l’ancien pool. Une fois le nouveau pool déployé, l’outil Unassigned Number Announcements Migration est utilisé pour déplacer la configuration de l’ancien pool vers le nouveau.

<div>

## <a name="requirements"></a>Configuration requise

Les principaux éléments de configuration suivants sont requis pour exécuter correctement l’outil :

1.  Le script doit être exécuté à partir d’un ordinateur sur lequel Lync Server 2013 Management Shell est installé.

2.  L’application d’annonce doit être déployée correctement sur les serveurs ou les pools Lync sources et cibles.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Script Move-CsAnnouncementConfiguration.

Le script Move-CsAnnouncementConfiguration nécessite les deux paramètres décrits dans le tableau suivant. 

![Paramètres de déplacement-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Paramètres de déplacement-CsAnnouncementConfiguration.")

</div>

</div>

</div>

<div>

## <a name="examples"></a>Exemples

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>Déplacement de la configuration annonces du numéro non attribué d’un pool Lync Server 2010 vers un pool Lync Server 2013

Dans cet exemple, les annonces de numéro non affectées du pool de destination (Lync Server 2010) sont placées dans la liste de destination (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>Déplacement de la configuration annonces du numéro non attribué d’un pool Lync Server 2013 vers un pool Lync Server 2010

Dans cet exemple, les annonces de numéro non affectées du pool de destination (Lync Server 2013) sont placées dans la liste de destination (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Web Conf Data

L’outil de données Web conf permet à un administrateur de logiciels de communication Lync Server 2013 d’avoir davantage de contrôle sur les données associées aux conférences Web de l’organisateur. Les scénarios incluent la possibilité de supprimer les données de réunion d’un utilisateur spécifique sur la base de critères de date/heure.

<div>

## <a name="description"></a>Description

Cet outil permet aux administrateurs d’effectuer les opérations suivantes :

1.  Rechercher les données de conférence web associées à un utilisateur.

2.  Supprimer les données de conférence web associées à un utilisateur.

3.  Supprimer les données de conférence web associées à un utilisateur antérieures à une date donnée.

4.  Déplacer les données de conférence web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre.

<div>


> [!NOTE]  
> Les outils du kit de ressources pour Lync Server 2010 pris en charge lors du déplacement de toutes les données de conférence Web associées à un utilisateur unique lorsque ce dernier est déplacé d’un pool à un autre. Cette fonctionnalité a été supprimée de cet outil et remplacée par le paramètre  <STRONG>MoveConferenceData</STRONG>. Pour plus d’informations sur ce paramètre, voir l’applet de connexion <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-Csuser</A> .



</div>

L’outil supprime les données de réunion uniquement pour les réunions inactives. Les réunions actives (ou réunions en sessions) ne peuvent pas être supprimées.

Cet outil doit être exécuté à partir d’un ordinateur situé dans le même pool que l’utilisateur cible. L’utilisateur dont les données de contenu de réunion sont gérées par cet outil doit être hébergé dans le même pool d’utilisateurs.

</div>

<div>

## <a name="output"></a>Sortie

L’outil génère des résultats pour chacune des opérations :

  - Si une requête est exécutée, l’outil génère la liste de tous les dossiers de données des réunions inactives organisées par cet utilisateur.

  - En cas de suppression, l’outil génère la liste des dossiers de données de toutes les réunions pour lesquelles les données seront supprimées.

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil doit être exécuté dans le même pool qui héberge actuellement l’organisateur.

L’outil doit être exécuté à l’aide de privilèges d’administrateur avec un accès au magasin de fichiers de contenu.

</div>

<div>

## <a name="examples"></a>Exemples

Le tableau suivant décrit les paramètres (certains d’entre eux sont utilisés dans les exemples).

![Paramètres de l’outil de données Web CONF.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Paramètres de l’outil de données Web CONF.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

L’exemple précédent montre le fonctionnement d’une commande de requête. La sortie d’une telle commande est une liste des dossiers de contenu de réunion affectés par cet outil.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

L’exemple précédent est une commande de suppression. Cette commande supprime les dossiers des réunions inactives pour cet utilisateur.

</div>

<div>

## <a name="summary"></a>Résumé

Cet outil offre aux administrateurs un contrôle plus précis sur les données de réunion de conférence.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
