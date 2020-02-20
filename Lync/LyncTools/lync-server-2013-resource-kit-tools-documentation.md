---
title: Documentation sur les outils du kit de ressources Lync Server 2013
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
ms.openlocfilehash: 046e29fcec697a1ac073833e6b73c7bfe15fb8ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Documentation sur les outils du kit de ressources Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-09_

Cette rubrique décrit les outils qui font partie du kit de ressources Lync Server 2013, y compris l’objectif de chaque outil, ainsi que des exemples de son utilisation. Les outils du kit de ressources Lync Server 2013 facilitent les tâches de routine pour les administrateurs qui déploient et gèrent Lync Server 2013. Par exemple, l’outil **Web conf Data** peut être utilisé pour contrôler facilement les données téléchargées par les utilisateurs au cours d’une réunion en ligne. L’outil **SEFAUtil** peut être utilisé pour configurer le transfert d’appel de délégué et la réponse pour les utilisateurs. Nous encourageons les administrateurs informatiques à utiliser ces outils pour gérer plus efficacement Lync Server 2013.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installation des outils du kit de ressources

Pour installer les outils du kit de ressources Lync Server 2013, téléchargez **OCSReskit. msi**. Vous pouvez télécharger le programme d’installation des outils du kit de ressources [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429)à partir du centre de téléchargement à l’adresse.

Exécutez **OCSResKit. msi** pour effectuer une installation simple. Le fichier. msi installe tous les outils dans le chemin d’accès suivant : **%\\Program Files% Microsoft\\Lync Server 2013 reskit**. Les outils qui sont des fichiers exécutables autonomes se trouvent dans ce dossier. Les outils qui ont également des fichiers se trouvent dans leurs propres sous-dossiers.

</div>

<div>

## <a name="supported-environments"></a>Environnements pris en charge

Pour des performances optimales, les outils du kit de ressources Lync Server 2013 doivent être installés dans le même environnement et avec les mêmes spécifications que celles requises pour Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Vue d’ensemble des outils du kit de ressources

La liste suivante décrit les outils fournis dans le kit de ressources de Lync Server 2013. Une description de chaque outil, notamment les conditions requises et l’utilisation de l’exemple, est décrite dans la section suivante.

  - ABSConfig

  - Moniteur de service de stratégie de bande passante

  - Analyseur d’utilisation de la bande passante

  - Appeler Parkometer

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Afficheur de configuration réseau

  - Response Group agent Live

  - SEFAUtil

  - SYSPrep. ps1

  - Migration des annonces de numéros non attribués

  - Données Web CONF

</div>

<div>

## <a name="absconfig"></a>ABSConfig

L’outil de configuration du service de carnet d’adresses (ABSConfig) est un outil d’administration qui permet aux administrateurs de personnaliser la configuration du service de carnet d’adresses dans Lync Server 2013. Cet outil permet également aux administrateurs Lync Server 2013 de restaurer les paramètres par défaut du service de carnet d’adresses.

<div>

## <a name="description"></a>Description

ABSConfig est une application d’interface utilisateur graphique qui permet aux administrateurs de configurer les attributs des services de domaine Active Directory associés au service de carnet d’adresses.

Les principaux scénarios de l’outil sont les suivants :

  - Permettre aux administrateurs de mapper les attributs des services de domaine Active Directory aux attributs de Lync Server 2013.

  - Pour permettre aux administrateurs de spécifier l’attribut des services de domaine Active Directory à inclure ou exclure dans les fichiers du service de carnet d’adresses.

  - Pour permettre aux administrateurs de restaurer les paramètres par défaut du service de carnet d’adresses.

L’outil ABSConfig peut être démarré à l’aide du fichier absConfig. exe. L’outil s’ouvre sur l’onglet **configurer les attributs** . Ce tableau comporte des options permettant de mapper les attributs des services de domaine Active Directory avec les champs d’attribut de Lync Server 2013 et de spécifier les utilisateurs à inclure ou à exclure dans les fichiers du service de carnet d’adresses en fonction de filtres d’attributs spécifiques. Elle comporte également des options permettant de personnaliser la valeur du numéro de téléphone à inclure dans le fichier de carnet d’adresses. L’option restaurer les paramètres **par défaut** permet aux administrateurs de restaurer les valeurs par défaut des paramètres du service de carnet d’adresses.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Modifications à partir de Lync Server 2010

Dans l’outil de configuration ABS de Lync Server 2013, les attributs (lignes) peuvent être supprimés en désactivant la case à cocher « Activer » pour l’attribut. Cela équivaut à supprimer la ligne dans Lync Server 2010.

<div>


> [!NOTE]  
> La case à cocher Activer se trouve dans la colonne la plus à droite ; vous devrez peut-être faire défiler la liste vers la droite pour voir la colonne



</div>

</div>

<div>

## <a name="output"></a>Output

ABSConfig stocke la configuration du service de carnet d’adresses dans la base de données.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>Objectif

ABSConfig offre un moyen rapide et simple de personnaliser le service de carnet d’adresses Lync Server 2013.

</div>

<div>

## <a name="requirements"></a>Configuration requise

<div>

## <a name="computer"></a>Ordinateur

ABSConfig ne peut être exécuté qu’à partir d’un ordinateur joint à un domaine sur lequel Lync Server 2013 est installé. Dans le cas de Lync Server 2013, Enterprise Edition, cet outil peut être exécuté sur tous les serveurs frontaux pour lesquels le service de carnet d’adresses est activé lors de l’installation.

</div>

<div>

## <a name="network"></a>Réseau

L’ordinateur doit être en mesure de se connecter au pool frontal et à la base de données principale.

</div>

<div>

## <a name="software"></a>Logiciels

Les composants logiciels suivants doivent être installés avant d’exécuter l’outil ABSConfig :

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>Utilisateurs

Administrateurs disposant des autorisations nécessaires pour mettre à jour le déploiement de Lync Server 2013.

</div>

</div>

<div>

## <a name="examples"></a>Exemples

ABSConfig peut être démarré en tapant **ABSConfig. exe** à une invite de commandes. L’interface utilisateur de l’outil ABSConfig est illustrée ci-dessous.

![L’outil ABSConfig. exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "L’outil ABSConfig. exe.")

</div>

<div>

## <a name="summary"></a>Résumé

L’outil ABSConfig fournit aux administrateurs un outil rapide et facile à utiliser pour personnaliser le service de carnet d’adresses Lync Server 2013.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Moniteur de service de stratégie de bande passante

L’outil Moniteur de service de stratégie de bande passante permet aux administrateurs d’afficher la liste des éléments suivants :

1.  Tous les services de stratégie de bande passante Lync Server 2013 configurés (authentification et cœur) dans la topologie

2.  Les connexions que chaque service effectue à d’autres services de stratégie de bande passante et aux serveurs Edge

3.  Tous les liens configurés dans le document de configuration réseau et l’utilisation de la bande passante en temps réel comme indiqué par chacun des services de stratégie de bande passante

<div>

## <a name="description"></a>Description

L’outil Moniteur de service de stratégie de bande passante est implémenté en tant qu’application basée sur une interface utilisateur graphique. Les administrateurs démarrent l’outil en exécutant PDPMonUI. exe.

Lorsque l’outil démarre, il tente de découvrir la liste des services de stratégie de bande passante dans la topologie. Une fois la mise à jour initiale terminée, le volet à gauche de la fenêtre est renseigné avec une liste de services qui sont regroupés par les clusters auxquels ils appartiennent.

Lorsque les administrateurs sélectionnent un service de stratégie de bande passante particulier, le volet de droite affiche les informations relatives à ce service particulier. Ce volet comporte également deux onglets principaux qui affichent des informations.

<div>

## <a name="machine-info-tab"></a>Onglet Infos ordinateur

L’onglet **infos ordinateur** affiche les détails du service de stratégie de bande passante sélectionné et la liste et l’état de toutes les connexions établies par le service de stratégie de bande passante sélectionné à d’autres services.

</div>

<div>

## <a name="topology-info-tab"></a>Onglet informations sur la topologie

L’onglet **informations sur la topologie** affiche une liste de tous les liens configurés dans les paramètres de configuration du réseau. Pour chaque lien, la capacité de bande passante audio et vidéo est affichée. En outre, la bande passante actuellement utilisée est affichée, à la fois en Kbits/s et en pourcentage de la capacité. L’outil utilise un codage en couleurs pour mettre en surbrillance les liens dont l’utilisation est proche de la capacité, ce qui permet aux administrateurs d’isoler rapidement ces liens.

<div>


> [!NOTE]  
> Si l’outil Moniteur de service de stratégie de bande passante rencontre une défaillance lorsqu’il se connecte à l’un des services de stratégie de bande passante configurés, les informations des onglets <STRONG>infos ordinateur</STRONG> et informations sur la <STRONG>topologie</STRONG> ne seront pas renseignées. Toutefois, il est possible que l’outil se connecte à l’origine, mais perd sa connexion au service. Dans ce cas, les administrateurs peuvent voir des informations périmées. Il existe un <STRONG>dernier horodatage mis à jour</STRONG> sur chacun des onglets qui permet aux administrateurs de savoir quand les données ont été mises à jour pour un service de stratégie de bande passante particulier.



</div>

</div>

</div>

<div>

## <a name="output"></a>Output

Il n’y a pas de sortie de ligne de commande ; la sortie du programme est contenue dans l’interface utilisateur graphique principale.

</div>

<div>

## <a name="purpose"></a>Objectif

L’objectif de l’outil Moniteur de service de stratégie de bande passante est de permettre aux administrateurs de visualiser l’état de chacun des services de stratégie de bande passante définis dans la topologie. En outre, les administrateurs peuvent voir l’utilisation de la bande passante en temps réel pour tous les liens définis dans le document de configuration du réseau.

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil Moniteur de service de stratégie de bande passante doit être exécuté sur un ordinateur qui fait partie de la topologie Lync Server.

</div>

<div>

## <a name="summary"></a>Résumé

L’outil Moniteur de service de stratégie de bande passante peut être une ressource précieuse pour les administrateurs afin qu’ils puissent inspecter l’état de tous les services de stratégie de bande passante dans la topologie, et plus important, ils peuvent obtenir une utilisation en temps réel de la bande passante pour les liens qui sont défini dans les paramètres de configuration réseau.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Analyseur d’utilisation de la bande passante

L’analyseur d’utilisation de la bande passante est un outil qui crée des rapports sur les différentes vues de la consommation de bande passante par les points de terminaison UC sur les liaisons de réseau étendu dans le réseau d’entreprise. Ces rapports peuvent être utilisés pour comprendre le modèle de consommation de bande passante actuel et pour faciliter la planification de la capacité de bande passante.

<div>

## <a name="description"></a>Description

L’analyseur d’utilisation de la bande passante est implémenté en tant qu’application basée sur une interface utilisateur graphique. Cet outil génère des rapports spécifiquement pour l’utilisation audio sur le réseau et vous aide à planifier la capacité. Elle effectue également une itération sur la capacité de bande passante affectée à différents liens.

</div>

<div>

## <a name="output"></a>Output

Bandwidth utilization Analyzer fournit des tracés graphiques de la capacité de bande passante et de l’utilisation de l’audio pour toutes les liaisons de réseau étendu configurées dans le système.

</div>

<div>

## <a name="purpose"></a>Objectif

Dans tout déploiement vocal et vidéo, il est essentiel de surveiller et de comprendre la tendance de l’utilisation de la bande passante du trafic multimédia sur le réseau d’entreprise. L’outil d’analyse de l’utilisation de la bande passante permet à un administrateur d’atteindre le même objectif. Cet outil effectue les opérations suivantes :

  - Génère des rapports spécifiques pour l’utilisation audio sur le réseau

  - Permet une planification et une itération de capacité plus efficaces sur la capacité de bande passante affectée à différents liens

Bandwidth utilization Analyzer peut générer des placettes graphiques de capacité de bande passante et de rapports d’utilisation ; Il s’agit des éléments suivants :

  - Toutes les liaisons de réseau étendu dans le réseau d’entreprise

  - Filtré par les liaisons WAN sélectionnées qui ont été choisies

  - Filtrés par des liaisons de réseau étendu ayant dépassé la capacité de liaison

  - Filtrés par des liaisons de réseau étendu qui ont été sous-utilisant la bande passante approvisionnée

  - Filtrer par les liaisons de réseau étendu qui ont atteint des niveaux critiques (une utilisation de bande passante supérieure à 90% de la capacité de bande passante de la liaison de réseau étendu)

  - Filtré par type de lien WAN — liaisons de sites réseau, liens interrégionaux et liens au sein d’un site

  - Filtré par région réseau

<div>

## <a name="applications"></a>Applications

L’analyseur d’utilisation de la bande passante comporte les deux applications suivantes (outils) :

  - **WanLinkLogCollector. exe**   cet outil permet à son utilisateur d’entrer les informations requises.

  - **BandwidthUtilizationAnalyzer. xlsm**  un rapport de logiciel de feuille de calcul Microsoft Excel est automatiquement lancé par WanLinkLogCollector. exe. Cette application permet à l’utilisateur d’appliquer des filtres au rapport, comme indiqué plus loin dans cet article.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phases de l’utilisation de l’analyseur d’utilisation de la bande passante

Il existe deux phases lors de l’utilisation de l’analyseur d’utilisation de la bande passante :

  - Collecter les journaux, qui sont exécutés à l’aide de WanLinkLogCollector. exe

  - Personnaliser des rapports, qui est effectué à l’aide de BandwidthUtilizationAnalyzer. xlsm

<div>


> [!IMPORTANT]  
> Il est vivement recommandé que BandwidthUtilizationAnalyzer. xlsm ne soit pas lancé manuellement par les utilisateurs finaux.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Démarrage de l’analyseur d’utilisation de la bande passante

Démarrez WanLinkLogCollector. exe à l’invite de commandes ou à l’aide de l’Explorateur Windows.

**Utilisation de WanLinkLogCollector. exe**

Il existe trois étapes à suivre pour utiliser WanLinkLogCollector. exe :

1.  **Journaliser la chronologie**   indiquez la chronologie pour laquelle le rapport doit être généré.

2.  **Spécifier que les répertoires**   de fichiers fournissent des informations sur l’emplacement des fichiers

3.  **Collecter les journaux et lancer la visionneuse**  de rapports exécuter la commande pour générer le rapport

<div>

## <a name="step-1---log-the-timeline"></a>Étape 1 : journalisation de la chronologie

La journalisation de la chronologie permet à l’utilisateur de l’outil de spécifier les éléments suivants, comme illustré dans la figure ci-dessous.

1.  **Date de début** Il s’agit de la date de début de la chronologie pour laquelle le rapport doit être généré ; par exemple, le 1er août 2010.

2.  **Date de fin** Il s’agit de la date de fin de la chronologie pour laquelle le rapport doit être généré ; par exemple, le 30 septembre 2010.
    
    ![Dates de début et de fin dans l’utilisation de la bande passante](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Dates de début et de fin dans l’utilisation de la bande passante")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>Étape 2 : spécification des répertoires de fichiers

Les répertoires de fichiers suivants peuvent être spécifiés par l’utilisateur comme indiqué.

  - **Emplacement des fichiers journaux du serveur** Emplacement du dossier dans lequel sont stockés les journaux du serveur de stratégie de bande passante. Il s’agit généralement \<\>\\\<du choix du\>\\AppServerFiles\\PDP.

  - **Emplacement de stockage des fichiers temporaires** Emplacement du fichier temporaire dans lequel les fichiers intermédiaires sont stockés pendant la génération du rapport.

![Répertoires de fichiers dans l’utilisation de la bande passante anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Répertoires de fichiers dans l’utilisation de la bande passante anal")

<div>


> [!NOTE]  
> Assurez-vous qu’un accès suffisant aux journaux du serveur et au dossier de magasin de fichiers temporaire est fourni à l’utilisateur de l’outil.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Étape 3 : collecte des journaux et démarrage de la visionneuse de rapports

Pour collecter les journaux et démarrer la visionneuse de rapports, cliquez sur **exécuter** comme indiqué ci-dessous. Cette étape collecte les données requises.

![Collecte de données dans l’utilisation de la bande passante](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecte de données dans l’utilisation de la bande passante")

Une fois la validation d’entrée réussie, le message ci-dessous s’affiche.

![Enregistre la notification collectée dans la bande passante utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Enregistre la notification collectée dans la bande passante utili")

Cliquez sur **OK**. BandwidthUtilizationAnalyzer. xlsm démarre automatiquement. Suivez les instructions indiquées dans la boîte de message. Pour plus d’informations, reportez-vous **à utilisation de BandwidthUtilizationAnalyzer. xlsm** dans la section suivante.

</div>

<div>


**Utilisation de BandwidthUtilizationAnalyzer. xlsm**

1.  Lorsque BandwidthUtilizationAnalyzer. xlsm démarre automatiquement, cliquez sur **Actualiser** comme indiqué ci-dessous.
    
    ![BandwidthUtilizationAnalyzer. xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer. xlsm")

2.  Lors de l’ouverture d’un dossier de fichiers, sélectionnez Consolidated. csv à partir de l’emplacement spécifié dans la zone de message, comme indiqué ci-dessous. Il indique également l’emplacement sous la forme **C :\\Temp**.
    
    ![Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.")

3.  Cliquez sur **Importer**.

4.  Le tracé graphique est généré automatiquement. Elle est disponible lorsque le pointeur de travail en arrière-plan disparaît.
    
    ![Application de filtres en mode état.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres en mode état.")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>Application de filtres à l’affichage de rapport

Les filtres qui peuvent être appliqués à l’affichage de rapport comme indiqué ci-dessous sont décrits comme suit :

![Application de filtres en mode état.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres en mode état.")

1.  **Name (nom** ) Filtrer par liaisons WAN (le filtre se trouve sur le côté droit du graphique). Le préfixe indique les types de liens suivants : consultez la zone vertical (bleu) :
    
      - **Site S** Liaison WAN entre un site réseau et une région réseau
    
      - **Est inter-site** La liaison de réseau étendu entre deux sites réseau
    
      - **R inter-région** La liaison de réseau étendu entre deux régions réseau

2.  **Limite dépassée** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante est supérieure à la capacité de bande passante

3.  **Niveaux critiques** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante atteint 90% ou plus de la capacité de bande passante

4.  **Sous-utilisés** Filtrer par des liaisons de réseau étendu dont l’utilisation de la bande passante est inférieure à 25% de la capacité de bande passante

5.  **Type de liaison** Filtrez les types de liaisons de réseau étendu suivants :
    
      - Type de **site réseau**
    
      - Type **inter-sites**
    
      - Type **de lien entre les régions**

6.  **Région** Filtrer par région réseau

Les figures suivantes présentent les filtres décrits précédemment.

Filtrez par **nom**. Sélectionnez la liste des liens à afficher dans le graphique.

![Filtrage par nom dans BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrage par nom dans BandwidthUtilizationAnalyzer.")

Filtre par **limite dépassée**. Sélectionnez **true** pour appliquer le filtre.

![Filtrage par limite dépassée.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrage par limite dépassée.")

Filtrer par **niveaux critiques**. Sélectionnez **true** pour appliquer le filtre.

![Filtrage par niveaux critiques.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrage par niveaux critiques.")

Filtrer par **sous-utilisé**. Sélectionnez **true** pour appliquer le filtre.

![Filtrage par sous-utilisé.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrage par sous-utilisé.")

Filtre par **type de lien**. Sélectionnez le ou les types à afficher.

![Filtrage par type de lien.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrage par type de lien.")

Filtrez par **région**. Sélectionnez la liste des régions dont les liens doivent être affichés.

![Filtrage par région.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrage par région.")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Configuration requise

  - .NET Framework 3,5

  - Microsoft Excel 2010 ou Excel 2007

</div>

<div>

## <a name="summary"></a>Résumé

L’analyseur d’utilisation de la bande passante permet de tracer l’utilisation de la bande passante audio pour le trafic UC sur le réseau. Cet outil peut également être utilisé pour signaler l’utilisation de la bande passante vidéo sur le réseau.

</div>

</div>

<div>

## <a name="call-parkometer"></a>Appeler Parkometer

Call Parkometer est une application en ligne de commande qui fournit un accès facile à la base de données des orbites de parcage d’appel.

<div>

## <a name="description"></a>Description

Call Parkometer est un outil permettant de suivre les appels actuellement parqués. Il collecte également des statistiques sur les orbites et l’utilisation du serveur de parcage d’appel (CPS). Cet outil de ligne de commande fournit à la fois un accès en lecture et en écriture à la base de données SQL Server d’orbites CPS à partir d’un ordinateur local ou connecté à distance.

Toutes les options s’excluent mutuellement. La syntaxe de la ligne de commande est la suivante :

  - paramètre **– o** : répertorie toutes les plages d’orbites configurées pour ce pool.

  - paramètre **– n** : répertorie toutes les orbites actuellement utilisées dans ce pool. Les informations affichées sont les suivantes :
    
      - URI (Uniform Resource Identifier) SIP du parqué et parqueur.
    
      - Nom d’hôte du CPS dans lequel l’appel est parqué.
    
      - Horodatage du moment où l’appel a été parqué.

  - **– paramètre f** — indique le nombre d’orbites libres actuellement dans le pool.

  - **paramètre – \<r\> n** : répertorie \<les\> n derniers appels parqués. Les informations affichées sont les suivantes :
    
      - URI SIP du parcage.
    
      - URI SIP parqueur.
    
      - Nom d’hôte du CPS sur lequel l’appel a été parqué.
    
      - Horodatage de l’extraction ou de la suppression de l’appel.

  - paramètre **-\<t\> n** -test de réservation d’une orbite dans la base de données pour afficher le caractère aléatoire des numéros d’orbite attribués.

</div>

<div>

## <a name="output"></a>Output

En fonction des paramètres d’entrée spécifiés à l’invite de commandes, appelez Parkometer affiche la sortie suivante :

  - Toutes les plages d’orbites configurées pour ce pool

  - Appels actuellement parqués

  - Nombre d’orbites libres (disponibles)

  - Appels parqués récemment

  - Orbites réservées pour le test des valeurs d’orbite uniforme et aléatoire

</div>

<div>

## <a name="purpose"></a>Objectif

L’objectif de l’outil CPS est de fournir un accès à la base de données CPS à partir de la ligne de commande. L’administrateur peut consulter l’utilisation de CPS et déterminer le nombre d’orbites affectées à un pool.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Il n’y a aucune condition requise si cet outil est exécuté sur le même ordinateur que celui qui exécute CPS. Si cet outil est exécuté sur un ordinateur distant, la base de données SQL Server utilisée par Lync Server 2013 doit être configurée pour autoriser l’accès à distance. Call Parkometer doit être configuré avec une chaîne de connexion de base de données SQL Server pour se connecter au serveur SQL Server du pool. Cette chaîne de connexion de base de données SQL Server est définie dans le fichier de configuration, **parkometer. exe. config**. Il doit être placé dans le même répertoire que celui où se trouve parkometer. exe. Le fichier XML suivant est un exemple de fichier parkometer. exe. config. Les paramètres qui doivent être configurés sont le nom d’utilisateur (par\\exemple, administrateur mondomaine), le mot de passe (par exemple, monmotdepasse) et le nom d’hôte (par exemple, monserveur).

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

Plages d’orbites déployées : le paramètre – o répertorie toutes les plages d’orbites configurées pour ce pool, comme indiqué

![Plages d’orbites dans l’appel Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Plages d’orbites dans l’appel Parkometer.")

Appels actuellement parqués : le paramètre – n répertorie toutes les orbites actuellement utilisées sur ce pool, comme illustré ci-dessous.

![Appels actuellement parqués dans Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Appels actuellement parqués dans Call Parkometer.")

Nombre d’orbites libres : le paramètre – f indique le nombre d’orbites libres actuellement dans le pool, comme indiqué

![Orbites libres dans l’appel Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Orbites libres dans l’appel Parkometer.")

Appels parqués récemment : le paramètre – \<r\> n répertorie \<les\> n derniers appels parqués, comme indiqué

![Appels parqués récemment dans Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Appels parqués récemment dans Call Parkometer.")

Réservation d’orbites de test : \<le\> paramètre – t n teste la réservation d’une orbite dans la base de données, comme illustré

![Testez les réservations d’orbites dans Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testez les réservations d’orbites dans Call Parkometer.")

</div>

<div>

## <a name="summary"></a>Résumé

Call Parkometer est un outil de ligne de commande qui fournit des informations détaillées sur le serveur de parcage d’appel.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

L’outil Kit de ressources de CleanupStorageServiceData permet de supprimer des données orphelines de la base de données utilisée par le service de stockage Lync Server (LYSS). Une des fonctions du service de stockage est de mettre en mémoire tampon les communications entre Lync Server et différents points de terminaison de stockage de données principales, tels que SQL Server et Exchange.

<div>

## <a name="description"></a>Description

Pour prendre en charge la haute disponibilité, LYSS accepte et enregistre temporairement des copies des données sur plusieurs serveurs frontaux dans le pool, et supprime ces données une fois qu’il a été remis à son emplacement de stockage à long terme. Il existe des situations inhabituelles pouvant se produire pendant une opération normale, lorsqu’un serveur peut se bloquer ou rencontrer un problème de traitement et que certaines données risquent de ne pas être nettoyées correctement. Ces données sont inoffensives, mais elles consomment des ressources de traitement limitées. Une grande part de la maintenance des données requises normale est automatisée, mais cet outil permet l’identification et la suppression sûres de ces données orphelines lorsque la suppression automatique n’est pas possible. L’utilisation de cet outil est indiquée lorsqu’une alerte de System Center Operations Manager (SCOM) de surveillance de l’intégrité est générée, qui demande à l’administrateur de supprimer les données inutiles des bases de données LYSS locales dans le pool. Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui a déclenché l’alerte. Les détails de l’événement contiendront des informations sur la quantité de données orphelines contenues sur le serveur frontal et sont déclenchés lorsque ces données dépassent certains seuils préalablement définis.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources Lync Server 2013. L’outil s’exécute sur des ordinateurs liés à un domaine sur lesquels Lync Server et Lync Server 2013 Management Shell sont installés. L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux dans le pool. Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée. Cette base de données est utilisée par l’outil CleanupStorageServiceData pour obtenir les détails de connexion nécessaires pour communiquer avec le service de routage Lync Server. Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’une autorisation en lecture/écriture sur le partage de fichiers auquel ils souhaitent écrire le journal de sortie. En outre, cet outil dépend du pool en état stable. En essence, cela signifie que chaque serveur frontal doit être opérationnel et que l’instance SQL Server LYNCLOCAL et la base de données LYSS doivent pouvoir être connectées, et que chaque groupe de routage doit disposer d’un ensemble complet de 1 serveur frontal principal et de deux serveurs frontaux secondaires. ervers.

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

DBAnalyze est un outil de ligne de commande qui aide les administrateurs à rassembler des rapports d’analyse sur les bases de données Lync Server 2013. DBAnalyze présente les modes suivants : diagnostic, données utilisateur, Conférence, MCU et fragmentation de disque :

  - **Le mode**   diagnostic crée un rapport qui inclut des informations sur les tables (nombre d’enregistrements, fragmentation, taille des données, taille de l’index), tailles des fichiers de données et des fichiers journaux, date de la dernière sauvegarde, répartition des contacts entre les serveurs exécutant Microsoft Office Communications Server, nombre moyen d’autorisations, de contacts, de conteneurs, d’abonnements, de publications, de points de terminaison par utilisateur, de personnes mal hébergées, utilisateurs ne pouvant pas être routés Conférences, conférences actives et version de la base de données.
    
    <div>
    

    > [!NOTE]  
    > L’exécution du mode diagnostic peut affecter les performances du serveur.

    
    </div>

  - Le **mode**  de données utilisateur signale les données de contact, de conteneur, d’abonnement, de publication, d’autorisation et de groupe de contacts pour un utilisateur spécifié ou pour les utilisateurs qui disposent de cet utilisateur dans leur liste de contacts et d’autorisations. Ce mode signale également les données récapitulatives des conférences auxquelles un utilisateur est organisé ou auquel il est invité.

  - **Le mode**   Conférence fournit des informations détaillées sur une conférence spécifique, notamment tous les détails de l’heure de planification de la Conférence, la liste des types de médias autorisés pour la Conférence, les MCU actifs (unités de contrôle multipoint), la liste des participants actifs et l’état de signalisation de chaque participant.

  - **Décoder l’ID**  de réunion décode un ID de réunion PSTN (réseau téléphonique commuté) spécifié par le commutateur **/pstnid** mais ne se connecte pas au serveur principal pour obtenir des informations détaillées.

  - **Resolve Conference**   décode un ID de réunion PSTN spécifié par le commutateur **/pstnid** et affiche des informations sur la Conférence indiquée par l’ID.

  - **Le mode**  MCU signale l’ID, le type de média, l’URL, l’état de la pulsation, la charge de conférence et la charge des participants pour chaque MCU du pool.

  - **Le mode**  de fragmentation de disque affiche l’état de fragmentation de tous les disques.

Cet outil permet de diagnostiquer divers problèmes ou d’aider les administrateurs à planifier la capacité. Par exemple, si la plupart des utilisateurs hébergés sur le serveur A choisissent les utilisateurs hébergés sur le serveur B comme contacts, l’administrateur peut déplacer les utilisateurs sur le serveur A vers le serveur B afin de réduire le trafic entre les serveurs.

</div>

<div>

## <a name="output"></a>Output

Cet outil génère des rapports prédéfinis sur la base de données Lync Server 2013. **Chemin d’accès :** %\\ProgramFiles% Microsoft Lync\\Server 2013 reskit

</div>

<div>

## <a name="purpose"></a>Objectif

Pour installer DbAnalyze. exe, copiez-le dans un dossier local, puis exécutez l’outil. Pour utiliser l’outil, exécutez la commande suivante à partir de la ligne de commande.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Les descriptions des options de ligne de commande sont présentées ci-dessous.

![Options de ligne de commande pour DbAnalyze. exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Options de ligne de commande pour DbAnalyze. exe.")

</div>

<div>

## <a name="requirements"></a>Configuration requise

**Ordinateur** DBAnalyze ne peut être exécuté qu’à partir d’un ordinateur joint à un domaine sur lequel Lync Server 2013 est installé.

**Réseau** L’ordinateur doit être en mesure de se connecter à la base de données principale.

**Logiciels** Les composants logiciels Lync Server 2013 doivent être installés avant d’exécuter DBAnalyze.

**Les utilisateurs** Le tableau ci-dessous montre les administrateurs qui disposent des autorisations nécessaires pour accéder aux bases de données Lync Server 2013.

![Tableau des autorisations pour DbAnalyze. exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tableau des autorisations pour DbAnalyze. exe.")

<div>


> [!NOTE]  
> Un compte d’administrateur local est requis pour le mode <STRONG>/Report : Disk</STRONG> .



</div>

</div>

<div>

## <a name="examples"></a>Exemples

Voici des exemples de commandes valides de DbAnalyze. exe :

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>Résumé

DBAnalyzer fournit aux administrateurs un moyen rapide et simple d’analyser les bases de données Lync Server 2013.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

L’outil Kit de ressources ImportStorageServiceData permet de réimporter les données de point de terminaison et de file d’attente qui ont été vidées du service de stockage (LYSS) dans le service de stockage.

<div>

## <a name="description"></a>Description

Les données vidées du service de stockage ont pu être automatiques (périodiques) en fonction de l’état des éléments de file d’attente ou de la taille de la base de données. Cela peut être dû à l’invocation manuelle de la cmdlet de basculement du pool ou à la cmdlet StorageServiceFullFlush (appelée par l’applet de commande de basculement du pool). Notez que les données ne doivent idéalement pas être réimportées si l’une des bases de données du service de stockage (LYSS) sur les serveurs frontaux se trouve au-dessus du niveau normal, car cela entraînera probablement une plus grande exportation des données. De plus, tous les problèmes susceptibles d’avoir contribué à l’augmentation de la file d’attente du service de stockage doivent d’abord être résolus (par exemple, des erreurs de point de terminaison Exchange, des problèmes réseau ou d’autres problèmes).

**Scénario 1 :** lors du basculement de pool, les fichiers peuvent être vidés du service de stockage pour chaque serveur frontal. Une fois le basculement terminé, l’outil doit être exécuté pour réimporter les données.

**Scénario 2 :** les données sont vidées automatiquement chaque jour ou en réponse à une base de données de service de stockage dépassant certains seuils de taille (par exemple 60%, 80%, 90% complet). Les données vidées automatiquement doivent être régulièrement réimportées par l’administrateur. Dans la situation ci-dessus, si le Pack SCOM de surveillance n’est pas déployé, il existe des événements pour le service de stockage Lync Server concernant les données vidées du service de stockage. Les ID d’événement de 32075 (opération de vidage complète est démarré), 32076 (vidage complet terminé), 32082 (maintenance de niveau de maintenance démarré), 32083 (vidage du niveau de maintenance terminé), 32089 (vidage dû à la fin de la base de données). Remarque ces ID d’événement correspondent à la version RTM. Lorsqu’un administrateur voit ces événements, cela signifie qu’il existe des fichiers qui ont été vidés. Ces données doivent régulièrement être importées à l’aide de cet outil, par exemple une fois par semaine.

Pour la version de service en ligne, si le Pack SCOM à analyse d’intégrité pour Lync Server est déployé, il existe de nouvelles alertes pouvant être déclenchées, qui demandent à l’administrateur de réimporter les données vidées dans le service de stockage. Il y aura un événement correspondant dans le journal des événements sur le serveur frontal qui a déclenché l’alerte. L’événement fournira une description du chemin d’accès parent sous lequel se trouvent les fichiers de données vidés, ainsi que le nombre de fichiers correspondant aux critères d’alerte. Le critère d’alerte est qu’il y a des fichiers X ou plus sous le chemin d’accès parent en particulier dont la version est d’au moins Y jours (où X et Y sont prédéfinis dans le StorageService, mais qui peuvent être remplacés en modifiant le fichier APPCONFIG.) Deux exemples d’événements pouvant déclencher l’alerte d’intégrité sont indiqués ci-dessous, la différence étant le chemin d’accès parent. Une possibilité se trouve sous le partage de fichiers de service Web, tandis que l’autre peut être le répertoire de données d’application local de chaque serveur frontal. (par exemple c :\\ProgramData\\Microsoft\\Lync Server\\StorageService). L’administrateur exécutera ensuite cet outil reskit.

Cet outil augmentera la charge d’UC et d’e/s sur le serveur frontal sur lequel il est exécuté, ainsi que d’autres serveurs frontaux, dans la situation où les données ne sont pas détenues par le serveur frontal sur lequel l’outil est exécuté. Nous vous recommandons d’exécuter cet outil lorsque les serveurs frontaux ne sont pas fortement sollicités par le processeur et la charge d’e/s, par exemple en dehors des heures de pointe. Deuxièmement, cet outil peut 2 à 3 minutes pour importer un fichier de données. Gardez cela à l’esprit lorsque vous évaluez la durée d’exécution de l’outil. Le fichier journal détaillé généré par l’outil apparaît par défaut sur le magasin de fichiers. Supprimez-le s’il n’y a aucune erreur signalée, car le fichier journal peut utiliser des dizaines de Mo ou plus.

![Exemples d’événements du journal des événements du serveur de stockage.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Exemples d’événements du journal des événements du serveur de stockage.")

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources Lync Server 2013. L’outil s’exécute sur des ordinateurs liés à un domaine sur lesquels Lync Server et Lync Server Management Shell sont installés. L’outil utilise une cmdlet de Management Shell pour identifier tous les serveurs frontaux du pool. Deuxièmement, l’outil doit être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée. Cette base de données est utilisée par l’outil pour récupérer l’emplacement du partage de fichiers WebService pour le pool. De plus, avant d’utiliser l’outil, chaque serveur frontal doit d’abord activer la communication à distance Windows PowerShell à l’aide de **Enable-PSRemoting** sur chaque serveur frontal, ainsi que la machine à partir de laquelle l’outil est exécuté. Dans le cas contraire, les commandes Windows PowerShell distantes à partir de cet outil échoueront. La communication à distance Windows PowerShell peut être désactivée sur tous les serveurs frontaux du pool une fois terminé. Enfin, le compte ou les informations d’identification appelant l’outil doivent disposer d’une autorisation en lecture/écriture sur le partage de fichiers WebPart pour le pool sur lequel ils exécutent cet outil. Dans le cas contraire, l’outil échoue avec des erreurs d’autorisation d’e/s.

<div>


> [!NOTE]  
> Sur Windows Server 2012, la communication à distance Windows PowerShell est activée par défaut, mais pas avec le système d’exploitation Windows Server 2008.



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

L’outil LCSSync permet de déployer le logiciel de communication Lync Server 2013 dans un environnement à forêts multiples. Cet outil permet de synchroniser les utilisateurs et les groupes de différentes forêts d’utilisateurs en tant qu’objet de contact des services de domaine Active Directory avec une forêt centrale où Lync Server 2013 est installé.

<div>

## <a name="description"></a>Description

LCSSync utilise les objets de contact des services de domaine Active Directory synchronisés dans la forêt centrale pour activer les utilisateurs pour Lync Server. Pour fournir une connexion unique, le compte d’utilisateur principal doit être mappé à l’objet contact des services de domaine Active Directory dans la forêt centrale pour Lync Server 2013. Cet outil permet d’effectuer ce mappage. Cet outil fournit des modèles pour la création d’agents de gestion dans le serveur Microsoft Identity Integration Server.

</div>

<div>

## <a name="summary"></a>Résumé

L’outil LCSSync permet de déployer Lync Server dans un environnement à forêts multiples.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

L’outil LookupUserConsole affiche des informations de routage Lync Server internes sur des utilisateurs spécifiques. Ces informations peuvent être utiles au support technique de Microsoft pour diagnostiquer les problèmes de déploiement et de routage.

<div>

## <a name="description"></a>Description

L’exécution de LookupUserConsole. exe ouvre une invite de commandes qui accepte les adresses SIP et tente d’afficher les informations de routage internes de Lync Server qui les concernent. Tapez **Exit** pour quitter l’outil LookupUserConsole.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources Lync Server 2013. L’outil s’exécute sur des ordinateurs liés à un domaine sur lesquels Lync Server est installé

</div>

<div>

## <a name="examples"></a>Exemples

C :\\Program Files\\Microsoft Lync Server 2013\\reskit\>LookupUserConsole. exe

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

L’outil MSTurnPing permet à un administrateur du logiciel de communications Microsoft Lync Server 2013 de vérifier l’état des serveurs exécutant les services d’authentification audio/vidéo et audio/vidéo, ainsi que les serveurs qui exécutent les services de stratégie de bande passante dans la topologie.

<div>

## <a name="description"></a>Description

L’outil MSTurnPing permet à un administrateur du logiciel de communication Lync Server 2013 de vérifier l’état des serveurs exécutant les services d’authentification audio/vidéo et audio/vidéo, ainsi que les serveurs qui exécutent des services de stratégie de bande passante dans la topologie.

L’outil permet à l’administrateur d’effectuer les tests suivants :

1.  Test du serveur Edge a/V : l’outil effectue des tests sur tous les serveurs Edge A/V de la topologie en procédant comme suit :
    
      - Vérification que le service d’authentification audio/vidéo de Lync Server est démarré et peut émettre des informations d’identification correctes.
    
      - Vérification que le service Edge audio/vidéo de Lync Server est démarré et peut allouer correctement les ressources sur le serveur Edge externe.

2.  Test du service de stratégie de bande passante : l’outil effectue des tests sur tous les serveurs qui exécutent les services de stratégie de bande passante dans la topologie en procédant comme suit :
    
      - Vérifier que le service de stratégie de bande passante Lync Server (authentification) est démarré et peut émettre des informations d’identification appropriées.
    
      - Vérification que le service de stratégie de bande passante Lync Server (Core) est démarré et peut effectuer la vérification de bande passante.

Cet outil doit être exécuté à partir d’un ordinateur qui fait partie de la topologie et sur lequel le magasin local est installé.

</div>

<div>

## <a name="output"></a>Output

L’outil renvoie les résultats de chacune des opérations.

  - Si le test **AudioVideoEdgeServer** est effectué, les sorties de l’outil sont les suivantes :
    
      - Les résultats des tests des ordinateurs qui fournissent le service d’authentification audio/vidéo Lync Server dans la topologie.
    
      - Les résultats des tests des ordinateurs qui fournissent le service Edge audio/vidéo Lync Server dans la topologie

  - Si le test **BandwidthPolicyServer** est effectué, les sorties de l’outil sont les suivantes :
    
      - Les résultats des tests des ordinateurs qui fournissent le service de stratégie de bande passante Lync Server (authentification) dans la topologie.
    
      - Les résultats des tests des ordinateurs qui fournissent le service de stratégie de bande passante Lync Server (Core) dans la topologie.

</div>

<div>

## <a name="requirements"></a>Configuration requise

  - Cet outil doit être exécuté à partir d’un ordinateur qui se trouve dans la topologie et qui a le magasin local.

  - L’outil doit être exécuté en tant qu’administrateur ayant accès au magasin local.

</div>

<div>

## <a name="examples"></a>Exemples

Voici un exemple de l’entrée d’outil.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>Résumé

Cet outil peut être une ressource précieuse pour les administrateurs Lync Server 2013 qui souhaitent vérifier l’état des serveurs qui exécutent les services de stratégie de bande passante et audio/vidéo.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Afficheur de configuration réseau

La visionneuse de configuration réseau peut être utilisée par les administrateurs de logiciels de communication Microsoft Lync Server 2013 pour afficher la topologie de réseau de contrôle d’admission des appels (CAC) pour une entreprise qui est configurée pour autoriser les sessions de communication en temps réel, telles que les communications vocales ou les appels vidéo en fonction de la capacité de bande passante spécifiée. Les administrateurs de Lync Server 2013 définissent les stratégies de contrôle d’admission des stratégies qui sont appliquées par les services de stratégie de bande passante installés avec Lync Server 2013.

<div>

## <a name="description"></a>Description

La visionneuse de configuration réseau (NetworkConfigurationViewer. exe) permet aux administrateurs d’effectuer les tâches suivantes :

  - Chargez et affichez la topologie de réseau CAC à partir d’un déploiement Lync Server 2013 dans un format graphique.

  - Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal de serveur de stratégie de bande passante dans un format graphique.

  - Enregistrez et stockez la topologie de réseau CAC au format XML sur le disque.

  - Enregistrer et stocker le diagramme de topologie réseau CAC au format JPG ou BMP.

  - Afficher les données de configuration de la topologie réseau CAC.

  - Afficher la topologie du réseau CAC sous la forme d’un style d’affichage arborescent.

  - Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (par exemple, liaisons de site à région, de région à région et de site à site).

  - Afficher les informations de site, les informations de région et les stratégies de bande passante et les liaisons réseau configurées pour la topologie du réseau CAC.

</div>

<div>

## <a name="purpose"></a>Objectif

Afficher les liens de topologie du réseau CAC d’entreprise dans une interface graphique.

</div>

<div>

## <a name="examples"></a>Exemples

**Chargez et affichez la topologie de réseau CAC à partir d’un déploiement Lync Server 2013 dans un format graphique :** Les administrateurs Lync Server 2013 peuvent charger et afficher la configuration de la topologie du réseau CAC sur n’importe quel ordinateur Lync Server 2013 à l’aide de l’option **Télécharger la configuration réseau** , comme illustré dans la figure ci-dessous. L’outil ne parviendra pas à télécharger ou à afficher une configuration de ce type lorsqu’il est déployé sur un ordinateur qui n’a pas de connectivité avec le magasin de configurations Lync.

![Téléchargement de la configuration réseau.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Téléchargement de la configuration réseau.")

**Chargez et affichez la topologie de réseau CAC à partir d’un fichier journal de serveur de stratégie de bande passante dans un format graphique :** Les serveurs de stratégie de bande passante Lync Server 2013 enregistrent la topologie de réseau CAC dans le cadre du mécanisme de journalisation sous l’emplacement de partage de fichiers de Lync Server 2013. Les administrateurs Lync Server peuvent afficher ce type de fichier dans un format graphique à l’aide de l’option **ouvrir la configuration du réseau** , comme indiqué ci-dessous.

![Ouverture d’un fichier journal du serveur de stratégie de bande passante.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Ouverture d’un fichier journal du serveur de stratégie de bande passante.")

Enregistrer et stocker la topologie de réseau CAC au format XML sur le disque : les administrateurs Lync Server 2013 peuvent enregistrer le fichier de configuration de la topologie réseau CAC au format XML à l’aide de l’option **enregistrer une copie de la configuration réseau** , comme indiqué ci-dessous. Le fichier de configuration enregistré peut ensuite être utilisé hors connexion à des fins d’affichage graphique.

![Enregistrement de la configuration réseau sous forme de fichier XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Enregistrement de la configuration réseau sous forme de fichier XML.")

Enregistrer et stocker le diagramme de topologie réseau CAC au format JPG ou BMP : les administrateurs Lync Server 2013 peuvent enregistrer la configuration de la topologie du réseau CAC dans un format graphique (formats de fichiers JPG et BMP) à l’aide de l’option **enregistrer le diagramme de configuration réseau en tant qu’image** , comme illustré ci-dessous.

![Enregistrement de la configuration réseau en tant qu’image.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Enregistrement de la configuration réseau en tant qu’image.")

**Afficher les données de configuration de la topologie réseau CAC :** Les administrateurs Lync Server 2013 peuvent afficher les données de configuration du réseau, telles que les régions réseau, les sites réseau, les profils de bande passante et les adresses IP de sous-réseau de site dans un format textuel à l’aide de l’option Afficher les données de configuration réseau, comme indiqué ci-dessous.

![Affichage des données de configuration réseau.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Affichage des données de configuration réseau.")

**Afficher la topologie du réseau CAC sous forme d’arborescence :** Les administrateurs de Lync Server 2013 peuvent afficher les données de configuration du réseau associées dans un style d’affichage de l’arborescence graphique en utilisant le panneau de configuration du côté gauche de la fenêtre outil, comme illustré ci-dessous.

![Affichage des données de configuration réseau dans une arborescence.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Affichage des données de configuration réseau dans une arborescence.")

**Définissez des connecteurs personnalisés pour les liens de topologie de réseau CAC (tels que les liens de site à région, région à région et de site à site) :** Les administrateurs Lync Server 2013 peuvent définir des connecteurs graphiques personnalisés pour la configuration du réseau CAC WAN Links à l’aide de l’option paramètres, comme illustré ci-dessous. Cela permet de différencier les différents types de liaisons réseau configurées dans la configuration réseau.

![Définir des connecteurs personnalisés pour la topologie du réseau CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Définir des connecteurs personnalisés pour la topologie du réseau CAC")

**Afficher les informations de site, les informations de région et les stratégies de bande passante de mise en service de la topologie réseau CAC :** Les administrateurs Lync Server 2013 peuvent afficher les informations relatives à la région réseau CAC, les informations de site et les informations de configuration de la bande passante CAC à l’aide des options indiquées ci-dessous. (Par exemple, cliquez sur **info** dans une région réseau ou un objet de site réseau.)

![Définition de connecteurs personnalisés pour votre réseau.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Définition de connecteurs personnalisés pour votre réseau.")

</div>

<div>

## <a name="summary"></a>Résumé

Cet outil peut être une ressource précieuse pour les administrateurs Lync Server 2013 qui voudraient afficher la topologie de réseau CAC pour leur déploiement dans un format graphique.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Response Group agent Live

L’application Response Group offre aux agents la possibilité d’accéder à des informations en temps réel utiles à l’aide de son service Web intégré. Malheureusement, aucune vue graphique de ces données n’est disponible en dehors de l’application. L’outil Response Group agent Live Resource Kit résout ce problème en fournissant un moyen simple et graphique d’accéder à ces informations, améliorés par des informations logicielles de communication en temps réel de Microsoft Lync 2013, telles que la présence d’autres agents.

<div>

## <a name="description"></a>Description

Response Group agent Live est une application Windows qui fournit des fonctionnalités de connexion et de déconnexion, ainsi que des informations en temps réel (telles que l’appartenance à un groupe et le nombre actuel d’appels) aux agents Response Group. Il s’agit d’une version améliorée de la page groupes d’agents (accessible à partir de Lync 2013.

</div>

<div>

## <a name="purpose"></a>Objectif

L’application Response Group place en file d’attente les appels entrants, puis les achemine vers les groupes d’agents. Pour prendre des décisions éclairées concernant les appels à traiter, les agents peuvent accéder aux informations en temps réel sur leurs groupes d’agents, telles que les autres agents disponibles et le nombre d’appels en attente dans chaque file d’attente. Ces informations, initialement accessibles uniquement par le biais du service Response Group, sont mises à disposition de manière intuitive par Response Group agent Live.

<div>

## <a name="features"></a>Fonctionnalités

L’outil Response Group agent Live est basé sur le service Response Group et le kit de développement logiciel (SDK) Microsoft Lync 2013. Il fournit aux agents Response Group les informations et les fonctionnalités disponibles auprès du service Response Group (par exemple, l’appartenance à un groupe, la présence d’autres agents et le nombre d’appels en attente).

La figure ci-dessous illustre l’interface principale de Response Group agent Live.

![Outil Response Group agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Outil Response Group agent Live.")

Les trois fonctionnalités principales suivantes sont disponibles pour les agents dans Response Group agent Live :

  - **Connexion/déconnexion :** Contrairement à la page des groupes d’agents (accessible à partir de Lync 2013), Response Group agent Live autorise uniquement les agents à se connecter ou à déconnecter tous les groupes d’agents en même temps. Cette application propose trois méthodes rapides pour la connexion et la déconnexion des agents :
    
      - Cliquez sur le bouton se connecter/déconnecter (vert et rouge) dans l’application.
    
      - Cliquez avec le bouton droit sur l’icône de la barre d’état système, puis sélectionnez se connecter ou se déconnecter.
    
      - Utilisation de raccourcis clavier configurables.

  - **Appartenance au groupe :** Lorsqu’un groupe d’agents est sélectionné, Response Group agent Live affiche la liste des agents de ce groupe dans le volet de droite. Si Lync 2013 est exécuté sur le même ordinateur que cette application, les informations de présence et la carte de visite s’affichent dans l’agent Response Group agent Live. Les agents peuvent envoyer un message instantané ou appeler d’autres agents directement à partir de là.

  - **Statistiques en temps réel :** Response Group agent Live fournit des statistiques en temps réel pour tous les groupes d’agents. La fréquence de mise à jour est d’une minute. Lorsqu’un groupe Response Group répond à un appel, un indicateur visuel est ajouté en regard du nom du groupe avec le nombre actuel d’appels en file d’attente. La suspension du pointeur sur un groupe affiche également le temps d’attente le plus long.

</div>

</div>

<div>

## <a name="requirements"></a>Configuration requise

Response Group agent Live requiert .NET Framework 4,0. En outre, pour tirer parti des fonctionnalités de présence et de carte de visite, Lync 2013 doit être installé localement (et être en cours d’exécution).

<div>

## <a name="configuration"></a>Configuration

Response Group agent Live peut être personnalisé en fonction des préférences individuelles à l’aide de la boîte de dialogue Options de l’application. En outre, l’administrateur peut définir l’adresse hôte par défaut en modifiant directement la propriété defaultHostAddress du fichier RGAgentLive. exe. config.

La figure ci-dessous illustre la boîte de dialogue Options que les agents peuvent utiliser pour configurer l’adresse hôte et les touches de raccourci. Pour accéder à cette boîte de dialogue, cliquez sur le bouton options en haut à droite de l’interface principale.

![Boîte de dialogue Options de l’agent Response Group.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Boîte de dialogue Options de l’agent Response Group.")

Les trois paramètres suivants peuvent être personnalisés dans la configuration de Response Group agent Live :

  - Adresse de l’hôte : il s’agit généralement du nom de domaine complet du pool de l’agent. L’adresse exacte du service Response Group est automatiquement dérivée en arrière-plan à partir de ces informations (en ajoutant le chemin d’accès approprié après l’hôte).

  - Raccourcis : les raccourcis exacts de connexion/déconnexion peuvent être personnalisés. La seule limitation est que les deux raccourcis doivent contenir la clé « Windows logo » (en plus d’au moins une autre clé).

  - Démarrez avec Windows : l’application peut être configurée pour démarrer automatiquement avec Windows.

</div>

</div>

<div>

## <a name="examples"></a>Exemples

La figure ci-dessous illustre comment appeler ou envoyer un message instantané à un autre agent en cliquant avec le bouton droit sur le contact dans le volet de droite.

![Passer un appel ou envoyer un message instantané.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Passer un appel ou envoyer un message instantané.")

La figure ci-dessous illustre la manière dont Response Group agent Live affiche le nombre actuel d’appels dans la file d’attente et le délai d’attente le plus long parmi tous les appels entrants.

![Affichage des informations de file d’attente.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Affichage des informations de file d’attente.")

</div>

<div>

## <a name="summary"></a>Résumé

La connexion et la déconnexion rapides, l’appartenance à un groupe et les statistiques en temps réel de base sont des fonctionnalités intéressantes de l’agent Response Group qui ne sont disponibles qu’en dehors de l’application à partir du service Response Group. Avec l’outil Response Group agent Live Resource Kit, les administrateurs Lync peuvent fournir à leurs agents une application Windows qui leur permet d’effectuer des tâches de manière plus rapide et graphique.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (Secondary Extension Feature activation) est un outil de ligne de commande qui permet aux administrateurs de logiciels de communications Microsoft Lync Server 2013 et aux agents de support technique de configurer la sonnerie des délégués, le transfert d’appel, la sonnerie simultanée, l’appel d’équipe paramètres et prise d’appel de groupe pour le compte d’un utilisateur Lync Server 2013. L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. L’outil SEFAUtil permet à l’administrateur d’activer/de désactiver/modifier le transfert d’appel ou de sonner simultanément au nom de l’utilisateur. L’administrateur peut spécifier la cible (sous la forme d’un URI SIP) ou utiliser une cible qui a déjà été publiée par l’utilisateur. Cet outil permet également aux administrateurs d’ajouter ou de supprimer des délégués ou des membres du groupe d’appel d’équipe au nom de l’utilisateur. Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3,0 et exige que les administrateurs créent une application approuvée dans le magasin central de gestion pour SEFAUtil

SEFAUtil (activation de la fonctionnalité d’extension secondaire) permet aux administrateurs et aux agents de support technique Lync Server 2013 de configurer la sonnerie de délégué, le transfert d’appel, la sonnerie simultanée, les paramètres d’appel d’équipe et la prise d’appel de groupe pour le compte d’un utilisateur Lync Server 2013 . Cet outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.

<div>

## <a name="description"></a>Description

La version actuelle de SEFAUtil n’est qu’un outil de ligne de commande ; Il n’y a pas d’interface utilisateur graphique de prise en charge. Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3,0. Les fonctionnalités de cet outil permettent aux administrateurs et aux agents du support technique d’effectuer les opérations suivantes :

  - Afficher tous les paramètres de routage des appels d’un utilisateur (inclut le transfert d’appels, la délégation, la sonnerie simultanée, l’appel d’équipe et la prise d’appel de groupe)

  - Activer/désactiver/modifier le paramètre de transfert d’appel (y compris la destination et le minuteur de non-réponse)

  - Activer/désactiver/modifier les configurations immédiates de transfert d’appel

  - Activer/désactiver/modifier les paramètres de délégation

  - Activer/désactiver/modifier les paramètres du groupe d’appel d’équipe
    
    <div>
    

    > [!NOTE]  
    > Nouveauté de l’outil SEFAUtil de Lync Server 2013

    
    </div>

  - Activer/désactiver/modifier les paramètres de sonnerie simultanée (il s’agit de la destination)
    
    <div>
    

    > [!NOTE]  
    > Nouveauté de l’outil SEFAUtil de Lync Server 2013

    
    </div>

  - Activer/désactiver/modifier les paramètres de prise d’appel de groupe
    
    <div>
    

    > [!WARNING]  
    > Nouveauté de l’outil SEFAUtil de Lync Server 2013

    
    </div>

Cet outil présente les limitations suivantes :

  - Pris en charge uniquement pour les utilisateurs hébergés dans un pool Lync Server

  - La modification en bloc des paramètres de routage des appels pour plusieurs utilisateurs n’est pas prise en charge

</div>

<div>

## <a name="output"></a>Output

La version actuelle de cet outil fournit uniquement des résultats dans la fenêtre d’invite de commandes. Pour plus d’informations, consultez la section exemples plus loin dans ce document.

</div>

<div>

## <a name="purpose"></a>Objectif

Voici quelques-uns des principaux scénarios dans lesquels cet outil peut être utilisé :

  - Bob est un cadre qui a été déplacé vers la téléphonie Lync Server. Il dispose d’une délégation sur son système PBX existant. Dans le cadre de la migration vers Lync, l’administrateur peut configurer le routage de Bob afin de refléter sa configuration de délégation préexistante.

  - Alice se rend compte qu’elle attend un appel important de la part de l’un de ses clients. Toutefois, elle se trouve dans un hôtel et n’a pas accès à un ordinateur. Elle appelle le support technique et demande à son numéro de téléphone mobile tous les appels effectués sur son numéro de travail. Le personnel du support technique peut effectuer la configuration en son nom.

  - Les appels de Jean vers son numéro de travail accédant à sa messagerie vocale mobile chaque fois qu’il travaille ; Toutefois, les choses semblent fonctionner correctement dans la plupart des autres emplacements. Le technicien du service d’assistance peut consulter la configuration de routage de Joe et se dévoiler que Joe a une sonnerie simultanée configurée sur son téléphone mobile. Le technicien demande à Joe la couverture mobile au niveau de son bureau et est en mesure de déterminer que la règle de sonnerie simultanée est ce qui provoque l’accès des appels à la messagerie vocale mobile de Jean quand sa couverture réseau est médiocre.

  - Mike est un nouvel employé chez contoso et il rejoint une nouvelle équipe sur laquelle tous les membres sont configurés pour l’appel d’équipe, lorsqu’il est activé pour Microsoft Lync, l’administrateur est en mesure de définir ses paramètres de groupe d’appels d’équipe afin d’inclure tous ses nouveaux membres d’équipe, en outre, le l’administrateur ajoute Mike en tant que membre du groupe d’appel d’équipe pour chacun des membres de son équipe.

  - Une pratique de service clientèle dans le département des ressources humaines de contoso est de fournir un service personnel à tous les appelants depuis le premier appel. Étant donné que tous les membres du service se sont très proches l’un de l’autre, le fait que tous les téléphones sonnent en même temps avec l’appel d’équipe est très gênant pour l’équipe. Pour fournir le meilleur service sans interrompre les membres de l’équipe, l’administrateur Lync tire parti de la fonctionnalité de prise d’appel de groupe. L’administrateur ajoute tous les membres du service à un groupe de collecte et communique au service le numéro du groupe de collecte. Lorsque Samantha est absent de son bureau, Jean remarque son sonnerie et il répond à l’appel de son bureau.

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées. UCMA 3,0 doit être installé sur cet ordinateur. Pour exécuter l’outil, une nouvelle application approuvée avec l’ID d’application SEFAUtil doit être créée sur ce pool.

**Création d’une application approuvée pour l’outil SEFAUtil**

1.  L’outil SEFAUTil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées. Si nécessaire, l’ajout d’un pool en tant que nouveau pool d’applications approuvées peut être réalisé via Lync Server Management Shell avec l’applet de commande suivante :
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > UCMA 3,0 doit être installé sur tout ordinateur qui sera utilisé pour exécuter l’outil SEFAUtil.

    
    </div>

2.  Une application approuvée doit être définie dans la topologie pour l’outil SEFAUtil. Pour définir SEFAUtil en tant que nouvelle application approuvée, utilisez Lync Server Management Shell et exécutez l’applet de commande suivante :
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Un autre port peut être utilisé si nécessaire.

    
    </div>

3.  Les modifications de la topologie doivent être activées. L’activation des modifications de la topologie peut être réalisée via Lync Server Management Shell en exécutant l’applet de commande suivante :
    
        Enable-CsToplogy

4.  Si nécessaire, installez les outils du kit de ressources Lync Server 2013 dans le serveur qui sera utilisé pour exécuter l’outil SEFAUtil (le serveur doit faire partie d’un pool d’applications approuvées).

5.  Vérifiez que le SEFAUtil s’exécute correctement. Pour ce faire, exécutez l’outil à partir d’une invite de commande Windows avec des privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement. Par défaut, l’outil se trouve dans : "... \\Fichiers\\programme Microsoft Lync Server 2013\\reskit». Pour afficher les paramètres de transfert d’appel d’un utilisateur, utilisez la commande suivante :
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Les paramètres de transfert d’appel de l’utilisateur doivent être affichés.

<div>

## <a name="group-call-pickup"></a>Prise d’appel de groupe

La prise d’appel de groupe nécessite une configuration supplémentaire dans Lync Server pour que la capacité soit entièrement activée. Avant d’affecter des groupes de collecte aux utilisateurs, reportez-vous à la documentation du produit de prise d’appel de groupe pour les étapes de planification et de déploiement de cette fonctionnalité.

</div>

</div>

<div>

## <a name="examples"></a>Exemples

<div>

## <a name="display-current-call-handling-settings"></a>Afficher les paramètres de gestion des appels actifs

La commande suivante affiche le traitement des appels pour l’utilisateur. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> Cet exemple utilise le commutateur <STRONG>/Server</STRONG> pour spécifier le serveur Lync auquel se connecter.



</div>

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>Définir la destination de transfert d’appel/pas de réponse

Cet exemple montre comment définir la destination de transfert d’appel/de réponse et le retard de l’anneau. Ici, le commutateur/Server n’est pas fourni ; SEFAUtil tente de découvrir automatiquement le serveur Lync.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>Activer le transfert d’appel immédiatement

Cet exemple active immédiatement le transfert d’appel à un autre utilisateur.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>Désactiver immédiatement le transfert d’appel

Cet exemple désactive immédiatement le transfert d’appel.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Ajouter un utilisateur en tant que délégué et configurer la sonnerie simultanée des délégués

Cet exemple ajoute un utilisateur en tant que délégué et configure la sonnerie simultanée des délégués.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>Modifier la règle de sonnerie simultanée des délégués

Cet exemple montre comment remplacer la règle de sonnerie simultanée définie dans l’exemple précédent par la règle de sonnerie différée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Résultat**

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
> Lorsque le dernier délégué est supprimé, la sonnerie de délégué est automatiquement désactivée.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Ajouter un délégué et configurer la règle appeler-transférer aux délégués

Cet exemple ajoute un délégué et configure la règle appeler-forward to delegates.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Activer la sonnerie simultanée et définir un numéro de destination

Cet exemple montre comment activer la sonnerie simultanée et définir un numéro de destination de sonnerie simultanée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> Pour modifier le numéro de destination de la sonnerie simultanée d’un utilisateur pour lequel la sonnerie simultanée est déjà activée, conservez la commande avec le commutateur/enablesimulring, sinon le numéro de destination ne sera pas modifié.



</div>

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>Désactiver la sonnerie simultanée

Cet exemple montre comment désactiver la sonnerie simultanée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Ajouter un membre d’équipe pour Team-Call et configurer la sonnerie simultanée pour le groupe membres d’appel d’équipe

Cet exemple ajoute un membre d’équipe au groupe d’appel d’équipe d’un utilisateur et active la sonnerie simultanée pour le groupe d’appel d’équipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> L’ajout d’un membre au groupe d’appel d’équipe d’un utilisateur bascule automatiquement la simultanée de sonnerie simultanée des utilisateurs vers sonnerie simultanée son groupe d’appel d’équipe.



</div>

**Résultat**

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
> Si le membre supprimé est le seul membre du groupe d’appel d’équipe, la sonnerie simultanée du groupe d’appel d’équipe est automatiquement désactivée.



</div>

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>Définir la sonnerie différée sur le groupe d’appel d’équipe

Cet exemple montre comment modifier la sonnerie différée en définissant le paramètre de l’heure du groupe d’appels d’équipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Activer l’appel d’équipe

Cet exemple montre comment activer un appel d’équipe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> Si le groupe d’appel d’équipe de l’utilisateur ne possède pas de membres, Team-Call n’est pas activé.



</div>

**Résultat**

</div>

<div>

## <a name="disable-team-call"></a>Désactiver l’appel d’équipe

Cet exemple désactive l’appel d’équipe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Résultat**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Activer la prise d’appel de groupe et attribuer un groupe de prise d’appel à un utilisateur

Cet exemple attribue un groupe de prise d’appel à un utilisateur et active la prise d’appel de groupe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Résultat**

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
> Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe qui a été attribué à l’utilisateur n’est pas conservé. Si vous souhaitez ensuite réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réaffecter le numéro de groupe avec le commutateur/enablegrouppickup.



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep. ps1

<div>

## <a name="description"></a>Description

SYSPrep. ps1 est un script Windows PowerShell qui installe les éléments suivants de Lync Server 2013 Prerequisites sur votre système d’exploitation Windows Server 2008.

  - Microsoft .NET Framework 4,5

  - Microsoft SQL Server Express

  - Windows PowerShell version 3,0

  - Visual C++ 2010 Redistributable

  - Mises à jour de Internet Information Server

  - Windows Identity Foundation

  - Fichiers principaux Lync Server 2013

Bien que le nom du script soit semblable à l’outil de préparation du système pour les systèmes d’exploitation Microsoft Windows, ils sont différents. Ce script installe uniquement les composants requis pour Lync Server 2013. Une fois ces éléments prérequis installés, l’outil SYSPrep Windows peut ensuite être utilisé pour créer une image du serveur.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Avant d’exécuter le script SYSPrep. ps1, vous devez copier les fichiers prérequis dans un dossier local sur l’ordinateur du système d’exploitation Windows Server 2008 (par exemple **, D :\\Setup)**. Ce dossier doit également inclure une copie des fichiers Lync Server 2013, notamment **Setup. exe.** Les fichiers prérequis peuvent être téléchargés à partir des emplacements suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Conditions préalables</th>
<th>L’emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .NET Framework 4,5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell version 3,0</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 Redistributable</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour de Internet Information Server</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup. exe</p></td>
<td><p>Copier à partir du support Lync Server 2013</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>Paramètre

Le paramètre **– SetupFolder** prend comme argument l’emplacement du répertoire des fichiers prérequis

</div>

<div>

## <a name="examples"></a>Exemples

Pour exécuter le script SYSPrep. ps1 et installer les éléments prérequis de Lync Server 2013, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges :

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Migration des annonces de numéros non attribués

L’outil de migration des annonces de numéros non attribués permet à un administrateur Lync de déplacer la configuration des numéros non attribués qui est desservi par l’application d’annonce à partir d’un serveur ou d’un pool Lync source vers un pool ou serveur Lync de destination.

<div>

## <a name="description"></a>Description

L’outil de migration des annonces de numéros non attribués est un script Windows PowerShell qui déplace la configuration des numéros non attribués Serviced par l’application d’annonce d’un serveur source ou d’un pool vers un autre serveur ou pool.

Lorsqu’il est exécuté, le script de migration des annonces de numéros non attribués effectue les opérations suivantes :

1.  Déplacez tous les fichiers audio utilisés par les annonces de numéros non attribués de l’application d’annonce hébergée dans le serveur ou le pool source vers le magasin de fichiers du serveur ou du pool de destination.
    
    <div>
    

    > [!NOTE]  
    > les fichiers audio sont supprimés du pool source une fois qu’ils sont copiés dans le pool de destination.

    
    </div>

2.  Déplacez toutes les annonces de numéros non attribués configurées pour l’application d’annonce hébergée dans le serveur ou le pool source vers le serveur ou le pool de destination.

3.  Réaffectez toutes les plages de numéros non attribués qui sont desservies par l’application d’annonce hébergée dans le serveur ou le pool source au serveur ou au pool de destination.

Une fois le script exécuté correctement, toutes les plages de numéros non attribués qui ont été gérées par l’application d’annonce hébergée dans le serveur ou le pool source seront désormais gérées avec la même configuration par le serveur ou le pool de destination.

</div>

<div>

## <a name="output"></a>Output

Le script **Move-CsAnnouncementConfiguration** indique dans la fenêtre Lync Management Shell où il est exécuté la réussite ou l’échec de l’opération de migration.

Si l’exécution de l’opération est interrompue par une erreur, les plages de numéros non attribués qui ont été déplacées vers la destination resteront dans la destination sous une forme opérationnelle et le reste des plages de numéros non attribués à migrer restera dans source également dans un formulaire opérationnel. Pour effectuer une migration complète du reste de la configuration, réexécutez le script après avoir remédié à l’erreur.

</div>

<div>

## <a name="purpose"></a>Objectif

Le script de migration des annonces de numéros non attribués peut être utilisé dans les trois scénarios suivants :

  - **Migration des paramètres de configuration vers une nouvelle version de Lync Server :** Contoso est en train de migrer vers Lync Server 2013 et, dans le cadre du processus de migration, l’administrateur Lync Server souhaite déplacer la configuration des numéros non attribués Serviced par l’application d’annonce depuis le déploiement de Lync Server 2010 vers le nouveau déploiement Lync Server 2013. Pour déplacer les paramètres de configuration, l’administrateur de Lync Server utilise l’outil de migration annonces de numéros non attribués.

  - **Restauration d’un déploiement de Lync server 2013 vers Lync server 2010 :** En raison de facteurs inattendus, contoso doit restaurer la migration vers le nouveau déploiement Lync Server 2013. Pour minimiser les interruptions du service, l’administrateur Lync Server utilise l’outil de migration des annonces de numéros non attribués pour restaurer la configuration du déploiement Lync Server 2013 vers le déploiement Lync Server 2010.

  - **Transfert de données entre les déploiements Lync :** Contoso est en train de remplacer tous les serveurs d’un pool par des serveurs plus récents. Leur stratégie est le déploiement d’un nouveau pool Lync Server 2013, le déplacement de toutes les données de l’ancien vers le nouveau, puis la désactivation de l’ancien pool. Une fois le nouveau pool déployé, l’outil de migration annonces de numéros non attribués est utilisé pour déplacer la configuration de l’ancien pool vers le nouveau.

<div>

## <a name="requirements"></a>Configuration requise

Les conditions principales requises pour exécuter correctement l’outil sont les suivantes :

1.  Le script doit être exécuté à partir d’un ordinateur sur lequel Lync Server 2013 Management Shell est installé.

2.  L’application d’annonce doit être déployée avec succès dans les pools ou serveurs de Lync source et de destination.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Script Move-CsAnnouncementConfiguration

Le script Move-CsAnnouncementConfiguration nécessite les deux paramètres décrits dans le tableau ci-dessous.

![Paramètres Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Paramètres Move-CsAnnouncementConfiguration.")

</div>

</div>

</div>

<div>

## <a name="examples"></a>Exemples

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>Transfert de la configuration des annonces de numéros non attribués à partir d’un pool Lync Server 2010 vers un pool Lync Server 2013

Cet exemple montre comment déplacer les annonces de numéros non attribués du pool source (Lync Server 2010) vers le pool de destination (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>Transfert de la configuration des annonces de numéros non attribués à partir d’un pool Lync Server 2013 vers un pool Lync Server 2010

Cet exemple montre comment déplacer les annonces de numéros non attribués du pool source (Lync Server 2013) vers le pool de destination (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Données Web CONF

L’outil Web conf Data permet à un administrateur du logiciel de communication Lync Server 2013 de contrôler davantage les données associées aux conférences Web d’un organisateur. Les scénarios incluent la possibilité de supprimer les données de réunion d’un utilisateur spécifique en fonction de critères de date et d’heure.

<div>

## <a name="description"></a>Description

Cet outil permet à l’administrateur d’effectuer les opérations suivantes :

1.  Rechercher toutes les données de conférence Web associées à un utilisateur unique.

2.  Supprimer toutes les données de conférence Web associées à un utilisateur unique.

3.  Supprimer toutes les données de conférence Web associées à un seul utilisateur antérieur à une date donnée.

4.  Déplacer toutes les données de conférence Web associées à un seul utilisateur lorsque cet utilisateur est déplacé d’un pool vers un autre.

<div>


> [!NOTE]  
> Les outils du kit de ressources pour Lync Server 2010 prennent en charge le déplacement de toutes les données de conférence Web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre. Cette fonctionnalité est désormais déconseillée de cet outil en faveur du paramètre <STRONG>MoveConferenceData</STRONG> . Pour plus d’informations sur ce paramètre, voir la cmdlet <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-Csuser</A> .



</div>

L’outil supprime les données de réunion uniquement pour les réunions inactives. Les réunions actives (ou les réunions en session) ne peuvent pas être supprimées.

Cet outil doit être exécuté à partir d’un ordinateur qui se trouve dans le même pool que l’utilisateur cible. L’utilisateur dont les données de contenu de réunion sont gérées par cet outil doit être hébergé dans le même pool d’utilisateurs.

</div>

<div>

## <a name="output"></a>Output

Cet outil renvoie les résultats de chacune des opérations :

  - Si une requête est exécutée, l’outil génère la liste de tous les dossiers de données de réunion inactifs qui ont cet utilisateur comme organisateur.

  - Si une suppression est effectuée, l’outil génère la liste de tous les dossiers de données de réunion dont les données seront supprimées.

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil doit être exécuté dans le même pool que l’organisateur.

L’outil doit être exécuté en utilisant les privilèges d’administrateur pour accéder au magasin de fichiers de contenu.

</div>

<div>

## <a name="examples"></a>Exemples

Le tableau suivant décrit les paramètres, dont certains sont utilisés dans les exemples.

![Paramètres de l’outil Web conf Data.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Paramètres de l’outil Web conf Data.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

L’exemple précédent illustre le fonctionnement d’une commande de requête. La sortie de cette commande serait une liste de tous les dossiers de contenu de réunion qui seraient affectés par cet outil.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

Le précédent est un exemple de commande Delete. La commande Supprimer supprime tous les dossiers de réunion inactifs de cet utilisateur.

</div>

<div>

## <a name="summary"></a>Résumé

Cet outil peut être une ressource précieuse pour les administrateurs qui ont besoin d’un contrôle plus précis sur les données de réunion de conférence.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
