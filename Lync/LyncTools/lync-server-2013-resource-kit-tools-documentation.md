---
title: Documentation sur les outils du Kit de ressources techniques Lync Server 2013
TOCTitle: Documentation sur les outils du Kit de ressources techniques Lync Server 2013
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945604(v=OCS.15)
ms:contentKeyID: 52056521
ms.date: 09/29/2014
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Documentation sur les outils du Kit de ressources techniques Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-01-09_

Cette rubrique décrit les outils du kit de ressources Lync Server 2013, notamment leur objectif, et donne des exemples de leur utilisation. Les outils du Kit de ressources Lync Server 2013 simplifient l’exécution des tâches de routine pour les administrateurs qui déploient et gèrent Lync Server 2013. Par exemple, l’outil **Web Conf Data** permet de contrôler aisément les données téléchargées par les utilisateurs au cours d’une réunion en ligne. L’outil **SEFAUtil** permet de définir le transfert des appels de délégué et le répondeur automatique pour les utilisateurs. Nous encourageons les administrateurs à utiliser ces outils pour gérer Lync Server 2013 plus efficacement.

## Installation des outils du kit de ressources

Pour installer les outils du Kit de ressources Lync Server 2013, téléchargez **OCSReskit.msi**. Vous pouvez télécharger le programme d’installation des outils du kit de ressources à partir du Centre de téléchargement à l’adresse [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).

Exécutez **OCSResKit.msi** pour effectuer une installation simple. Le fichier .msi installe tous les outils dans le chemin d’accès suivant : **%Program Files%\\Microsoft Lync Server 2013\\ResKit**. Les outils exécutables autonomes se trouvent dans ce dossier. Les outils ayant également des fichiers se trouvent dans leur propre sous-dossier.

## Environnements pris en charge

Pour des performances optimales, les outils du Kit de ressources Lync Server 2013 doivent être installés dans le même environnement et avec les mêmes spécifications que Lync Server 2013.

## Présentation des outils du kit de ressources

La liste suivante décrit les outils fournis dans le kit de ressources Lync Server 2013. Une description de chaque outil (configuration requise et exemple d’utilisation compris) est incluse dans la section suivante.

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

## ABSConfig

L’outil d’administration ABSConfig (Address Book Service Configuration) permet aux administrateurs de personnaliser la configuration du service de carnet d’adresses dans Lync Server 2013. Il leur permet également de restaurer les paramètres par défaut du service de carnet d’adresses.

## Description

L’application à interface utilisateur graphique ABSConfig permet aux administrateurs de configurer les attributs des services de domaine Active Directory liés au service de carnet d’adresses.

Les principaux scénarios suivants s’appliquent à l’outil :

  - permettre aux administrateurs de mapper les attributs des services de domaine Active Directory et de Lync Server 2013 ;

  - permettre aux administrateurs de spécifier un attribut des services de domaine Active Directory à inclure dans les fichiers du service de carnet d’adresses ou à exclure de ceux-ci ;

  - permettre aux administrateurs de restaurer les paramètres par défaut du service de carnet d’adresses.

L’outil ABSConfig peut être démarré à l’aide du fichier absConfig.exe. Il s’ouvre dans l’onglet **Configure Attributes (Configurer les attributs)**. Les options de cet onglet permettent de mapper les attributs des services de domaine Active Directory et les champs d’attribut pour Lync Server 2013, et de spécifier les utilisateurs à inclure dans les fichiers du service de carnet d’adresses ou à exclure de ceux-ci sur la base de filtres d’attribut spécifiques. D’autres options permettent de personnaliser la valeur du numéro de téléphone à inclure dans le fichier de carnet d’adresses. L’option **Restore Defaults (Paramètres par défaut)** permet aux administrateurs des restaurer les valeurs par défaut des paramètres du service de carnet d’adresses.

## Changements par rapport à Lync Server 2010

Dans l’outil Lync Server 2013 ABS Configuration, les attributs (lignes) peuvent être supprimés en désactivant la case à cocher Enable (Activer) correspondante. Cela revient à supprimer la ligne dans Lync Server 2010.

> [!NOTE]
> La case à cocher Enable (Activer) se trouve dans la première colonne à droite. Vous devrez peut-être faire défiler la page vers la droite pour afficher la colonne.


## Sortie

ABSConfig stocke la configuration du service de carnet d’adresses dans la base de données.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

## Objectif

ABSConfig permet de personnaliser le service de carnet d’adresses de Lync Server 2013 de façon rapide et simple.

## Configuration requise

## Ordinateur

ABSConfig peut seulement être exécuté à partir d’un ordinateur lié au domaine sur lequel Lync Server 2013 est installé. Dans le cas de Lync Server 2013 Enterprise Edition, cet outil peut être exécuté sur un serveur frontal sur lequel le service de carnet d’adresses est activé lors de l’installation.

## Réseau

L’ordinateur doit pouvoir se connecter au pool frontal et à la base de données principale.

## Logiciels

Les composants logiciels suivants doivent être installés avant d’exécuter l’outil ABSConfig :

  - Microsoft Lync Server 2013

## Utilisateurs

Administrateurs autorisés à mettre à jour le déploiement Lync Server 2013.

## Exemples

ABSConfig peut être démarré en tapant **ABSConfig.exe** dans une invite de commandes. L’interface utilisateur de l’outil ABSConfig se présente comme suit :

![Outil ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Outil ABSConfig.exe.")

## Résumé

L’outil ABSConfig permet aux administrateurs de personnaliser le service de carnet d’adresses de Lync Server 2013 de façon rapide et simple.

## Bandwidth Policy Service Monitor

L’outil Bandwidth Policy Service Monitor permet aux administrateurs d’afficher la liste des éléments suivants :

1.  services de stratégie de bande passante (authentification et principal) Lync Server 2013 configurés dans la topologie ;

2.  connexions effectuées par chaque service aux autres services de stratégie de bande passante et aux serveurs Edge ;

3.  liaisons configurées dans le document de configuration du réseau et utilisation de la bande passante en temps réel, telle que signalée par les services de stratégie de bande passante individuels.

## Description

L’outil Bandwidth Policy Service Monitor est implémenté sous la forme d’une application à interface utilisateur graphique. Les administrateurs démarrent l’outil en exécutant PDPMonUI.exe.

Lorsque l’outil démarre, il tente de découvrir la liste des services de stratégie de bande passante dans la topologie. Une fois la mise à jour initiale effectuée, le volet à gauche de la fenêtre est renseigné avec une liste de services regroupés selon les clusters auxquels ils appartiennent.

Lorsque les administrateurs sélectionnent un service de stratégie de bande passante particulier, le volet à droite affiche les informations relatives à ce service particulier. Ce volet inclut également deux onglets principaux qui affichent des informations.

## Onglet Machine Info (Informations sur l’ordinateur)

L’onglet **Machine Info (Informations sur l’ordinateur)** donne des informations sur le service de stratégie de bande passante sélectionné, ainsi que la liste et l’état des connexions effectuées par le service de stratégie de bande passante sélectionné aux autres services.

## Onglet Topology Info (Informations sur la topologie)

L’onglet **Topology Info (Informations sur la topologie)** affiche la liste des liaisons configurées dans les paramètres de configuration du réseau. Pour chaque liaison, la capacité de bande passante audio et vidéo est indiquée. La bande passante actuellement utilisée est également indiquée, en Kbps et en pourcentage de la capacité. L’outil utilise des couleurs pour mettre en valeur les liaisons dont l’utilisation atteint presque la capacité maximale afin que les administrateurs puissent les isoler rapidement.

> [!NOTE]
> Si l’outil Bandwidth Policy Service Monitor rencontre des défaillances lorsqu’il se connecte aux services de stratégie de la bande passante configurés, aucune information n’apparaît sous les onglets <strong>Machine Info (Informations sur l’ordinateur)</strong> et <strong>Topology Info (Informations sur la topologie)</strong>. Il est toutefois possible que l’outil se connecte avant de perdre la connexion au service. En pareil cas, les administrateurs peuvent voir des informations obsolètes. Les onglets incluent des informations d’horodatage (<strong>Last Updated (Dernière mise à jour)</strong>) qui permettent aux administrateurs de voir les date/heure de la dernière mise à jour des données pour un service de stratégie de bande passante particulier.


## Sortie

Il n’y a aucune sortie de ligne de commande. La sortie du programme apparaît dans l’interface utilisateur graphique principale.

## Objectif

L’outil Bandwidth Policy Service Monitor permet aux administrateurs de consulter l’état des services de stratégie de bande passante définis dans la topologie. Ils peuvent également voir l’utilisation de la bande passante en temps réel pour toutes les liaisons définies dans le document de configuration du réseau.

## Configuration requise

L’outil Bandwidth Policy Service Monitor doit être exécuté sur un ordinateur appartenant à la topologie Lync Server.

## Résumé

L’outil Bandwidth Policy Service Monitor est utile pour contrôler l’état des services de stratégie de bande passante dans la topologie et connaître l’utilisation de la bande passante en temps réel pour les liaisons définies dans les paramètres de configuration du réseau.

## Bandwidth Utilization Analyzer

L’outil Bandwidth Utilization Analyzer crée des rapports sur divers affichages de la consommation de bande passante par les points de terminaison d’UC entre les liaisons de réseau étendu dans le réseau d’entreprise. Ces rapports permettent d’identifier le modèle actuel de consommation de la bande passante et de planifier la capacité de bande passante.

## Description

Bandwidth Utilization Analyzer est implémenté sous la forme d’une application à interface utilisateur graphique. Cet outil génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau et constitue une aide pour planifier la capacité. Il traite également la capacité de bande passante affectée aux diverses liaisons par itération.

## Sortie

Bandwidth Utilization Analyzer offre une représentation graphique de la capacité de bande passante et de l’utilisation de la bande passante audio pour les liaisons de réseau étendu configurées dans le système.

## Objectif

Dans tous les déploiements voix et vidéo, il est essentiel de surveiller et comprendre les tendances d’utilisation de la bande passante par le trafic multimédia au sein du réseau de l’entreprise. L’outil Bandwidth Utilization Analyzer permet aux administrateurs d’y parvenir. L’outil effectue les opérations suivantes :

  - génère des rapports spécifiques sur l’utilisation de la bande passante audio dans le réseau ;

  - permet de planifier la capacité de façon plus efficace et de traiter la capacité de bande passante affectée aux diverses liaisons par itération.

Bandwidth Utilization Analyzer peut générer une représentation graphique des rapports sur la capacité et l’utilisation de la bande passante, comme suit :

  - liaisons de réseau étendu au sein du réseau d’entreprise ;

  - filtrage des liaisons de réseau étendues sélectionnées ;

  - filtrage des liaisons de réseau étendu ayant dépassé leur capacité ;

  - filtrage des liaisons de réseau étendu ayant sous-utilisé la bande passante approvisionnée ;

  - filtrage des liaisons de réseau étendu ayant atteint des niveaux critiques (utilisation de la bande passante supérieure à 90 % de la capacité de bande passante de la liaison de réseau étendu) ;

  - filtrage selon le type de liaison de réseau étendu (liaisons réseau-site, liaisons inter-régions et liaisons au sein d’un site) ;

  - filtrage par région réseau.

## Applications

Bandwidth Utilization Analyzer inclut les deux applications (outils) suivantes :

  - **WanLinkLogCollector.exe**   Cet outil permet de saisir les informations utiles.

  - **BandwidthUtilizationAnalyzer.xlsm**  Un rapport Microsoft Excel est généré automatiquement par WanLinkLogCollector.exe. Cette application permet à l’utilisateur d’appliquer des filtres au rapport, comme indiqué plus loin dans cet article.

## Phases d’utilisation de Bandwidth Utilization Analyzer

L’utilisation de Bandwidth Utilization Analyzer implique deux phases :

  - collecte des journaux, effectuée à l’aide de WanLinkLogCollector.exe ;

  - personnalisation des rapports, effectuée à l’aide de BandwidthUtilizationAnalyzer.xlsm.

> [!IMPORTANT]
> Il est recommandé que BandwidthUtilizationAnalyzer.xlsm ne soit pas démarré manuellement par les utilisateurs finaux.


## Démarrage de Bandwidth Utilization Analyzer

Démarrez WanLinkLogCollector.exe dans une invite de commandes ou à l’aide de l’Explorateur Windows.

**Utilisation de WanLinkLogCollector.exe**

L’utilisation de WanLinkLogCollector.exe implique trois étapes :

1.  **Définition de la chronologie**   Indiquez la chronologie pour laquelle le rapport doit être généré.

2.  **Définition des répertoires de fichiers**   Indiquez les informations relatives à l’emplacement des fichiers.

3.  **Collecte des journaux et démarrage de la visionneuse de rapports**  Exécutez la commande pour générer le rapport.

## Étape 1 - Définition de la chronologie

La définition de la chronologie permet à l’utilisateur de l’outil de spécifier les éléments suivants, comme indiqué dans la figure suivante.

1.  **Date de début** Date de début de la chronologie pour laquelle le rapport doit être généré (par exemple, 1er août 2010).

2.  **Date de fin** Date de fin de la chronologie pour laquelle le rapport doit être généré (par exemple, 30 septembre 2010).
    
    ![Dates de début et de fin de l’utilisation de la bande passante A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Dates de début et de fin de l’utilisation de la bande passante A")  

## Étape 2 - Définition des répertoires de fichiers

Les répertoires de fichiers suivants peuvent être spécifiés par l’utilisateur, comme indiqué.

  - **Emplacement des fichiers journaux du serveur** Dossier de stockage des journaux de serveur de la stratégie de bande passante (généralement \<serveur de fichiers\>\\\<serveur frontal\>\\AppServerFiles\\PDP.

  - **Emplacement de stockage des fichiers temporaires** Emplacement des fichiers temporaires dans lequel les fichiers intermédiaires sont stockés pendant la génération du rapport.

![Répertoires de fichiers dans Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Répertoires de fichiers dans Bandwidth Utilization Anal")

> [!NOTE]
> Vérifiez que l’utilisateur de l’outil dispose d’un accès suffisant aux journaux de serveur et au dossier du magasin des fichiers temporaires.


## Étape 3 - Collecte des journaux et démarrage de la visionneuse de rapports

Pour collecter les journaux et démarrer la visionneuse de rapports, cliquez sur **Execute (Exécuter)** comme indiqué ci-dessous. Cette opération permet de collecter les données requises.

![Collecte de données d’analyse de l’utilisation de la bande passante](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecte de données d’analyse de l’utilisation de la bande passante")

Une fois le contenu saisi validé, le message suivant apparaît.

![Notifications sur les journaux collectés dans Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Notifications sur les journaux collectés dans Bandwidth Utili")

Cliquez sur **OK (OK)**. BandwidthUtilizationAnalyzer.xlsm démarre automatiquement. Suivez les instructions du message. Pour plus d’informations, voir **Utilisation de BandwidthUtilizationAnalyzer.xlsm** dans la section suivante.


**Utilisation de BandwidthUtilizationAnalyzer.xlsm**

1.  Une fois BandwidthUtilizationAnalyzer.xlsm démarré automatiquement, cliquez sur **Refresh (Actualiser)**, comme indiqué ci-dessous.
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  Si un dossier de fichiers est ouvert, sélectionnez consolidated.csv à l’emplacement spécifié dans le message, comme indiqué ci-dessous. L’emplacement du répertoire **C:\\Temp** est également indiqué.
    
    ![Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Ouverture d’un dossier dans BandwidthUtilizationAnalyzer.")

3.  Cliquez sur **Import (Importer)**.

4.  La représentation graphique est générée automatiquement. Elle est disponible lorsque le pointeur de traitement en arrière-plan disparaît.
    
    ![Application de filtres à l’affichage du rapport.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres à l’affichage du rapport.")

## Application de filtres à l’affichage du rapport

Les filtres suivants peuvent être appliqués à l’affichage du rapport :

![Application de filtres à l’affichage du rapport.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Application de filtres à l’affichage du rapport.")

1.  **Name (Nom)** Filtrage des liaisons de réseau étendu (le filtre apparaît dans la partie droite du graphique). Le préfixe représente les types de liaisons suivants (voir l’encadré bleu vertical) :
    
      - **S Site (S (site))** Liaison de réseau étendu entre un site réseau et une région réseau
    
      - **IS Inter-Site (IS (intersite))** Liaison de réseau étendu entre deux sites réseau
    
      - **R Inter-Region (R (inter-régions))** Liaison de réseau étendu entre deux régions réseau

2.  **Exceeded limit (Limite dépassée)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est supérieure à la capacité de bande passante

3.  **Critical levels (Niveaux critiques)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante a atteint 90 % ou plus de la capacité de bande passante

4.  **Under-utilized (Sous-utilisé)** Filtrage des liaisons de réseau étendu pour lesquelles l’utilisation de la bande passante est inférieure à 25 % de la capacité de bande passante

5.  **Link type (Type de liaison)** Filtrage des types de liaisons de réseau étendu suivants :
    
      - **Network site (Site réseau)**
    
      - **Inter-site (Intersite)**
    
      - **Inter-Region (Inter-régions)**

6.  **Region (Région)** Filtrage de la région réseau

Les figures suivantes montrent les filtres décrits précédemment.

Filtrage sur **Name (Nom)**. Sélectionnez la liste des liaisons devant être affichées dans le graphique.

![Filtrage sur Name (Nom) dans BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtrage sur Name (Nom) dans BandwidthUtilizationAnalyzer.")

Filtrage sur **Exceeded limit (Limite dépassée)**. Sélectionnez **True** pour appliquer le filtre.

![Filtrage sur Exceeded limit (Limite dépassée).](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtrage sur Exceeded limit (Limite dépassée).")

Filtrage sur **Critical levels (Niveaux critiques)**. Sélectionnez **True** pour appliquer le filtre.

![Filtrage sur Critical Levels (Niveaux critiques).](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtrage sur Critical Levels (Niveaux critiques).")

Filtrage sur **Under utilized (Sous-utilisé)**. Sélectionnez **True** pour appliquer le filtre.

![Filtrage sur Under Utilized (Sous-utilisé).](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtrage sur Under Utilized (Sous-utilisé).")

Filtrage sur **Link Type (Type de liaison)**. Sélectionnez le ou les types devant être affichés.

![Filtrage sur Link Type (Type de lien).](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtrage sur Link Type (Type de lien).")

Filtrage sur **Region (Région)**. Sélectionnez la liste des régions pour lesquelles afficher les liaisons.

![Filtrage sur (Region) Région.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtrage sur (Region) Région.")

## Configuration requise

  - .NET Framework 3.5

  - Microsoft Excel 2010 ou Excel 2007

## Résumé

Bandwidth Utilization Analyzer permet de représenter l’utilisation de la bande passante audio pour le trafic des communications unifiées dans le réseau. Il permet également de créer des rapports sur l’utilisation de la bande passante vidéo dans le réseau.

## Call Parkometer

L’application en ligne de commande Call Parkometer permet d’accéder facilement à la base de données des orbites de parcage d’appel.

## Description

L’outil Call Parkometer permet de suivre les appels actuellement parqués. Il collecte également des statistiques sur les orbites et l’utilisation du serveur de parcage d’appel. Il offre un accès en lecture et en écriture à la base de données SQL Server des orbites du serveur de parcage d’appel à partir d’un ordinateur connecté localement ou à distance.

Toutes les options s’excluent mutuellement. La syntaxe suivante est appliquée à la ligne de commande :

  - Paramètre **–o** : répertorie toutes les plages d’orbites configurées pour ce pool.

  - Paramètre **–n** : répertorie toutes les orbites actuellement utilisées dans ce pool. Les informations suivantes sont affichées :
    
      - URI (Uniform Resource Identifier) SIP du parqué et du parqueur.
    
      - Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.
    
      - Date/heure du parcage de l’appel.

  - Paramètre **–f** : indique le nombre d’orbites actuellement libres dans le pool.

  - Paramètre **–r \<n\>** : répertorie les derniers \<n\> appels parqués. Les informations suivantes sont affichées :
    
      - URI SIP du parqué.
    
      - URI SIP du parqueur.
    
      - Nom d’hôte du serveur de parcage d’appel sur lequel l’appel est parqué.
    
      - Date/heure de récupération ou d’abandon de l’appel.

  - Paramètre **-t\<n\>** : teste la réservation d’une orbite dans la base de données pour démontrer l’affectation aléatoire des numéros d’orbite.

## Sortie

Selon les paramètres d’entrée spécifiés dans l’invite de commandes, l’outil Call Parkometer affiche la sortie suivante :

  - plages d’orbites configurées pour ce pool ;

  - appels actuellement parqués ;

  - nombre d’orbites libres (disponibles) ;

  - appels parqués récemment ;

  - orbites réservées pour le test des valeurs d’orbite uniformes et aléatoires.

## Objectif

L’outil CPS vie à fournir un accès par ligne de commande à la base de données du serveur de parcage d’appel. L’administrateur peut consulter l’utilisation du serveur de parcage d’appel et déterminer le nombre d’orbites affectées à un pool.

## Configuration requise

Aucune configuration n’est requise si cet outil est exécuté sur l’ordinateur qui exécute le serveur de parcage d’appel. S’il est exécuté sur un ordinateur distant, la base de données SQL Server utilisée par Lync Server 2013 doit être configurée pour autoriser l’accès à distance. Call Parkometer doit être configuré avec une chaîne de connexion de la base de données SQL Server pour se connecter à la base de données SQL Server du pool. Cette chaîne de connexion à la base de données SQL Server est définie dans le fichier de configuration (**parkometer.exe.config**). Elle doit être placée dans le répertoire dans lequel se trouve parkometer.exe. Le fichier XML suivant est un exemple de fichier parkometer.exe.config. Les paramètres de nom d’utilisateur (par exemple, mon\_domaine\\Administrateur), de mot de passe (par exemple, mon\_mot\_de\_passe) et de nom d’hôte (par exemple, mon\_serveur) doivent être configurés.

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

## Exemples

Plages d’orbites déployées : le paramètre –o répertorie les plages d’orbites configurées pour ce pool

![Plages d’orbites dans Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Plages d’orbites dans Call Parkometer.")

Appels actuellement parqués : le paramètre –n répertorie les orbites actuellement utilisées sur ce pool

![Appels actuellement parqués dans Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Appels actuellement parqués dans Call Parkometer.")

Nombre d’orbites libres : le paramètre –f indique le nombre d’orbites actuellement libres dans le pool

![Orbites libres dans Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Orbites libres dans Call Parkometer.")

Appels parqués récemment : le paramètre –r \<n\> répertorie les \<n\> derniers appels parqués

![Appels parqués récemment dans Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Appels parqués récemment dans Call Parkometer.")

Test de réservation d’orbite : le paramètre –t \<n\> teste la réservation d’une orbite dans la base de données

![Test de réservation d’orbite dans Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test de réservation d’orbite dans Call Parkometer.")

## Résumé

L’outil en ligne de commande Call Parkometer fournit des informations détaillées sur le serveur de parcage d’appel.

## CleanupStorageServiceData

L’outil de kit de ressources CleanupStorageServiceData permet de supprimer les données orphelines de la base de données utilisée par le service de stockage Lync Server. Ce service assure notamment la mise en mémoire tampon des communications entre Lync Server et plusieurs points de terminaison de stockage principal des données, tels que SQL Server et Exchange.

## Description

Pour prendre en charge la haute disponibilité, le service de stockage Lync Server accepte et enregistre temporairement des copies des données sur plusieurs serveurs frontaux du pool. Il supprime ensuite les données une fois qu’elles ont été remises à leur emplacement de stockage final. Des situations inhabituelles peuvent survenir dans le cadre d’un fonctionnement par ailleurs normal (blocage d’un serveur ou problème de traitement) et empêcher le nettoyage correct de certaines données. Ces données ne présentent aucun danger, mais sollicitent certaines ressources de traitement. Si la majeure partie des opérations requises de maintenance des données sont automatisées, cet outil permet toutefois d’identifier et de supprimer ces données orphelines lorsqu’il est impossible de les supprimer automatiquement. Il est recommandé d’utiliser cet outil en cas d’alerte System Center Operations Manager (SCOM) relative à la surveillance de l’intégrité demandant à l’administrateur de supprimer les données inutiles dans les bases de données locales du service de stockage Lync Server du pool. Un événement correspondant est consigné dans le journal des événement du serveur frontal à l’origine de l’alerte. Les détails de l’événement incluent des informations sur la quantité de données orphelines contenues sur le serveur frontal. L’événement est déclenché lorsque les données dépassent certains seuils prédéfinis.

## Configuration requise

Installez les outils du Kit de ressources Lync Server 2013. L’outil est exécuté sur les ordinateurs liés au domaine sur lesquels Lync Server et Lync Server 2013 Management Shell sont installés. Il utilise une applet de commande du Management Shell pour identifier tous les serveurs frontaux du pool. Il doit ensuite être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée. Cette base de données est utilisée par l’outil CleanupStorageServiceData pour obtenir les détails de connexion requis pour communiquer avec le service de routage Lync Server. Enfin, le compte ou les informations d’identification invoquant l’outil doivent avoir des autorisations en lecture/écriture sur le partage de fichiers sur lequel le journal de sortie doit être écrit. Par ailleurs, le pool doit être dans un état stable. Chaque serveur frontal doit donc être en état de fonctionner, il doit être possible de se connecter à l’instance SQL Server LYNCLOCAL et à la base de données du service de stockage Lync Server, et chaque groupe de routage doit inclure un ensemble complet incluant un serveur frontal principal et deux serveurs frontaux secondaires.

## Exemples

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe

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

## DBAnalyze

## Description

L’outil en ligne de commande DBAnalyze permet aux administrateurs de rassembler des rapports d’analyse sur les bases de données Lync Server 2013. DBAnalyze inclut les modes suivants : diagnostic, données des utilisateurs, conférence, unités de contrôle multipoint et fragmentation des disques :

  - **Diagnostic mode (Mode Diagnostic)**   Crée un rapport incluant des informations sur les tables (nombre d’enregistrements, fragmentation, taille des données et taille d’index), la taille des fichiers de données et des fichiers journaux, l’heure de la dernière sauvegarde, la répartition des contacts entre les serveurs exécutant Microsoft Office Communications Server, le nombre moyen d’autorisations, les contacts, les conteneurs, les abonnements, les publications, les points de terminaison par utilisateur, les éventuels utilisateurs hébergés de façon incorrecte, les utilisateurs ne pouvant pas être acheminés, le nombre moyen de conférences organisées par utilisateur, les conférences planifiées, les conférences actives et la version des bases de données.
    
    > [!NOTE]
    > L’exécution du mode Diagnostic peut affecter les performances des serveurs.


  - **User data mode (Mode Données des utilisateurs)**   Transmet des données relatives au contact, au conteneur, à l’abonnement, à la publication, à l’autorisation et au groupe de contacts pour un utilisateur spécifié ou pour des utilisateurs ayant cet utilisateur dans leurs listes de contacts et d’autorisations. Ce mode transmet également des données résumées sur les conférences organisées par un utilisateur ou auxquelles il est invité.

  - **Conference mode (Mode Conférence)**   Transmet des données détaillées sur une conférence spécifique (heure planifiée, liste des invités, liste des types de média autorisés, unités de contrôle multipoint actives, liste des participants actifs, état de signalisation des participants).

  - **Decode Meeting ID (Décodage de l’ID de réunion)**  Décode un ID de réunion PSTN spécifié par le commutateur **/pstnid** sans se connecter au serveur principal pour obtenir des informations détaillées.

  - **Resolve conference (Résolution d’une conférence)**   Décode un ID de réunion PSTN spécifié par le commutateur **/pstnid** et affiche des informations sur la conférence indiquée par l’ID.

  - **MCUs mode (Mode Unités de contrôle multipoint)**  Indique l’ID, le type de média, l’URL, le statut de pulsation, la charge des conférences et la charge des participants pour chaque unité de contrôle multipoint du pool.

  - **Disk fragmentation mode (Mode Fragmentation des disques)**  Affiche le statut de fragmentation des disques.

Cet outil permet de diagnostiquer plusieurs problèmes ou de planifier la capacité. Par exemple, si la plupart des utilisateurs hébergés sur un serveur A définissent des utilisateurs hébergés sur le serveur B comme contacts, l’administrateur peut déplacer les utilisateurs du serveur A vers le serveur B afin de réduire le trafic entre les serveurs.

## Sortie

Cet outil génère des rapports prédéfinis sur la base de données Lync Server 2013. **Chemin d’accès** : %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit

## Objectif

Pour installer Dbanalyze.exe, copiez-le dans un dossier local, puis exécutez l’outil. Pour utiliser l’outil, exécutez la commande suivante à partir d’une ligne de commande : `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`. Les options de ligne de commande sont décrites ci-dessous.

![Option de ligne de commande pour Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Option de ligne de commande pour Dbanalyze.exe.")

## Configuration requise

**Ordinateur** DBAnalyze peut seulement être exécuté à partir d’un ordinateur lié au domaine sur lequel Lync Server 2013 est installé.

**Réseau** L’ordinateur doit pouvoir se connecter à la base de données principale.

**Logiciels** Les composants logiciels Lync Server 2013 doivent être installés avant d’exécuter DBAnalyze.

**Utilisateurs**Le tableau suivant indique les administrateurs ayant les autorisations nécessaires pour accéder aux bases de données Lync Server 2013.

![Tableau d’autorisations pour Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tableau d’autorisations pour Dbanalyze.exe.")

> [!NOTE]
> Un compte d’administrateur local est nécessaire pour le mode <strong>/report:disk</strong>.


## Exemples

Les exemples suivants constituent des commandes Dbanalyze.exe correctes :

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

## Résumé

DBAnalyzer permet aux administrateurs d’analyser les bases de données Lync Server 2013 de façon simple et rapide.

## ImportStorageServiceData

L’outil de kit de ressources ImportStorageServiceData permet de réimporter les données de file d’attente et de point de terminaison éliminées du service de stockage Lync Server dans le service de stockage.

## Description

L’élimination de données du service de stockage peut être automatique (périodique) selon le statut des éléments de file d‘attente ou la taille de la base de données. Elle peut survenir suite à l’invocation manuelle de l’applet de commande de basculement du pool ou StorageServiceFullFlush (invoquée par l’applet de commande de basculement du pool). Dans l’idéal, les données ne doivent pas être réimportées si la taille des bases de données du service de stockage Lync Server sur les serveurs frontaux est supérieure au niveau normal, car ce faisant, il est probable que davantage de données soient exportées à nouveau. Par ailleurs, les problèmes susceptibles d’avoir créé les erreurs à l’origine du développement de la file d’attente du service de stockage doivent d’abord être résolus (par exemple, erreurs de point de terminaison Exchange, problèmes réseau ou autres problèmes).

**Scénario 1 :** lors du basculement du pool, les fichiers peuvent être éliminés du service de stockage de chaque serveur frontal. Une fois le basculement terminé, l’outil doit être exécuté pour réimporter les données.

**Scénario 2 :** les données sont éliminées automatiquement chaque jour ou suite au dépassement de certains seuils de taille par la base de données du service de stockage (par exemple, 60 %, 80 %, 90 % de remplissage). Ces données éliminées automatiquement doivent être régulièrement réimportées par l’administrateur. Dans la situation exposée plus haut, si le pack SCOM de surveillance de l’intégrité n’est pas déployé, des événements relatifs à l’élimination de données du service de stockage Lync Server sont consignés. Les ID d’événement 32075 (démarrage du vidage complet), 32076 (fin du vidage complet), 32082 (démarrage du vidage de niveau maintenance), 32083 (fin du vidage de niveau maintenance), 32089 (vidage effectué à cause du remplissage de la base de données). Notez que ces ID d’événement correspondent à la version finale. Lorsqu’un administrateur voit ces événements, des fichiers ont été éliminés. Ces données doivent être régulièrement réimportées à l’aide de cet outil (par exemple, une fois par semaine).

Pour la version du service en ligne, si le pack SCOM de surveillance de l’intégrité pour Lync Server est déployé, de nouvelles alertes invitant l’administrateur à réimporter les données éliminées dans le service de stockage peuvent être déclenchées. Un événement correspondant est consigné dans le journal des événements du serveur frontal à l’origine de l’alerte. Il décrit le chemin d’accès parent sous lequel se trouvent les données éliminées, et indique le nombre de fichiers correspondant aux critères de l’alerte, à savoir que X fichiers ou plus sous le chemin d‘accès parent particulier ont au moins Y jours (les valeurs X et Y prédéfinies dans le service de stockage peuvent être remplacées en changeant le fichier APPCONFIG). Deux exemples d’événement pouvant déclencher l’alerte d‘intégrité sont inclus plus loin. Ils se distinguent par leur chemin d’accès parent, une possibilité étant sous le partage de fichiers du service web, l’autre possibilité étant le répertoire local de données de l’application de chaque serveur frontal (par exemple, c:\\ProgramData\\Microsoft\\Lync Server\\StorageService). L’administrateur exécute ensuite cet outil de kit de ressources.

Cet outil augmente la charge processeur et d’E/S sur le serveur frontal sur lequel il est exécuté, ainsi que sur les autre serveurs frontaux, si les données n’appartiennent pas au serveur frontal sur lequel l’outil est exécuté. Il est recommandé d’exécuter cet outil lorsque les serveurs frontaux ne sont pas soumis à une charge processeur et d’E/S importante, par exemple en dehors des heures de pointe. Deuxièmement, cet outil peut prendre 2 à 3 minutes pour importer un fichier de données. Vous devez garder cette information à l’esprit lorsque vous cherchez à estimer le délai d’exécution de l’outil. Le fichier journal détaillé généré par l’outil apparaît par défaut dans le magasin de fichiers. Supprimez-le si aucune erreur n’est signalée, car la taille de celui-ci peut atteindre plusieurs Mo, voire davantage.

![Exemple d’événements du journal des événements du serveur de stockage.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Exemple d’événements du journal des événements du serveur de stockage.")

## Configuration requise

Installez les outils du Kit de ressources Lync Server 2013. L’outil est exécuté sur les ordinateurs liés au domaine sur lesquels Lync Server et Lync Server Management Shell sont installés. Il utilise une applet de commande du Management Shell pour identifier tous les serveurs frontaux du pool. Il doit ensuite être exécuté à partir d’un ordinateur du pool sur lequel la base de données **RtcLocal** est installée. Cette base de données est utilisée par l’outil pour récupérer l’emplacement du partage de fichiers WEBSERVICE du pool. Avant d’utiliser l’outil, la communication à distance Windows PowerShell doit d’abord être activée à l’aide de **Enable-PSRemoting** sur chaque serveur frontal, ainsi que sur l’ordinateur sur lequel l’outil est exécuté, sans quoi les commandes Windows PowerShell distantes de cet outil échoueront. La communication à distance Windows PowerShell peut être désactivée sur tous les serveurs frontaux du pool lorsque vous avez terminé d’utiliser l’outil. Enfin, le compte ou les informations d’identification invoquant l’outil doivent avoir des autorisations en lecture/écriture sur le partage de fichiers WEBSERVICE du pool sur lequel ils exécutent cet outil, sans quoi l’outil échouera en raison d’erreurs relatives aux autorisations d’E/S.

> [!NOTE]
> La communication à distance Windows PowerShell est activée par défaut sur Windows Server 2012, mais pas sur le système d’exploitation Windows Server 2008.


## Exemples

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

## LCSSync

L’outil LCSSync permet de déployer le logiciel de communication Lync Server 2013 dans un environnement à plusieurs forêts. Il permet de synchroniser des utilisateurs et des groupes issus de différentes forêts d’utilisateur sous la forme d’un objet contact Services de domaine Active Directory avec une forêt centrale dans laquelle Lync Server 2013 est installé.

## Description

LCSSync utilise les objets contact Services de domaine Active Directory dans la forêt centrale pour activer Lync Server pour les utilisateurs. Pour fournir l’authentification unique, le compte de l’utilisateur principal doit être mappé à l’objet contact Services de domaine Active Directory dans la forêt centrale pour Lync Server 2013. Cet outil aide à effectuer l’opération de mappage. Il fournit des modèles pour la création des agents de gestion dans Microsoft Identity Integration Server.

## Résumé

L’outil LCSSync permet de déployer Lync Server dans un environnement à plusieurs forêts.

## LookupUserConsole

L’outil LookupUserConsole affiche des informations de routage Lync Server interne sur des utilisateurs spécifiques. Ces informations peuvent être utiles au personnel du support technique Microsoft dans le cadre du diagnostic des problèmes de déploiement et de routage.

## Description

L‘exécution de LookupUserConsole.exe ouvre une invite de commandes qui accepte les adresses SIP et tente d’afficher les informations de routage Lync Server interne les concernant. Tapez **exit** pour quitter l’outil LookupUserConsole.

## Configuration requise

Installez les outils du Kit de ressources Lync Server 2013. L’outil est exécuté sur les ordinateurs liés au domaine sur lesquels Lync Server est installé.

## Exemples

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe

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

## MsTurnPing

L’outil MSTurnPing permet aux administrateurs du logiciel de communication Microsoft Lync Server 2013 de consulter l’état des serveurs exécutant les services Edge Audio/Vidéo et d’authentification Audio/Vidéo, ainsi que les serveurs exécutant les services de stratégie de bande passante dans la topologie.

## Description

L’outil MSTurnPing permet aux administrateurs du logiciel de communication Lync Server 2013 de consulter l’état des serveurs exécutant les services Edge Audio/Vidéo et d’authentification Audio/Vidéo, ainsi que les serveurs exécutant les services de stratégie de bande passante dans la topologie.

L’outil permet d’effectuer les tests suivants :

1.  Test des serveurs Edge A/V : l’outil effectue des tests sur tous les serveurs Edge A/V dans la topologie comme suit :
    
      - Il vérifie que le service d’authentification Audio/Vidéo Lync Server est démarré et peut émettre des informations d’identification correctes.
    
      - Il vérifie que le service Edge Audio/Vidéo Lync Server est démarré et peut allouer des ressources sur le serveur Edge externe correctement.

2.  Test des services de stratégie de bande passante : l’outil effectue des tests sur tous les serveurs exécutant les services de stratégie de bande passante dans la topologie comme suit :
    
      - Il vérifie que le service de stratégie de bande passante (authentification) Lync Server est démarré et peut émettre des informations d’identification correctes.
    
      - Il vérifie que le service de stratégie de bande passante (principal) Lync Server est démarré et peut contrôler la bande passante correctement.

Cet outil doit être exécuté à partir d’un ordinateur qui fait partie de la topologie et sur lequel le magasin local est installé.

## Sortie

L’outil génère des résultats pour chacune des opérations.

  - Pour le test **AudioVideoEdgeServer**, l’outil génère les résultats suivants :
    
      - résultats du test des ordinateurs exécutant le service d’authentification Audio/Vidéo Lync Server dans la topologie ;
    
      - résultats du test des ordinateurs exécutant le service Edge Audio/Vidéo Lync Server dans la topologie ;

  - Pour le test **BandwidthPolicyServer**, l’outil génère les résultats suivants :
    
      - résultats du test des ordinateurs exécutant le service de stratégie de bande passante (authentification) Lync Server dans la topologie ;
    
      - résultats du test des ordinateurs exécutant le service de stratégie de bande passante (principal) Lync Server dans la topologie ;

## Configuration requise

  - Cet outil doit être exécuté à partir d’un ordinateur de la topologie sur lequel le magasin local est installé.

  - L’outil doit être exécuté par un administrateur ayant accès au magasin local.

## Exemples

Voici un exemple de saisie pour l’outil.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

## Résumé

Cet outil permet aux administrateurs Lync Server 2013 de vérifier le statut des serveurs exécutant les services de stratégie de bande passante audio/vidéo.

## Network Configuration Viewer

Network Configuration Viewer permet aux administrateurs Microsoft Lync Server 2013 de consulter la topologie réseau de contrôle d’admission des appels (CAC) d’une entreprise approvisionnée pour autoriser les sessions de communication en temps réel, tels que les appels audio et vidéo sur la base d’une capacité de bande passante spécifiée. Les administrateurs Lync Server 2013 définissent les stratégies de contrôle d’admission des appels qui sont appliquées par les services de stratégie de bande passante installés avec Lync Server 2013.

## Description

Network Configuration Viewer (NetworkConfigurationViewer.exe) permet aux administrateurs d’effectuer les tâches suivantes :

  - charger et afficher la topologie réseau de contrôle d’admission des appels d’un déploiement Lync Server 2013 dans un format graphique ;

  - charger et afficher la topologie réseau de contrôle d’admission des appels à partir d‘un fichier journal de serveur de stratégie de bande passante dans un format graphique ;

  - enregistrer et stocker la topologie réseau de contrôle d’admission des appels dans un format XML sur le disque ;

  - enregistrer et stocker le diagramme de la topologie réseau de contrôle d’admission des appels au format JPG ou BMP ;

  - afficher les données de configuration de la topologie réseau de contrôle d’admission des appels ;

  - afficher la topologie réseau de contrôle d’admission des appels dans une arborescence ;

  - définir des connecteurs personnalisés pour les liaisons de la topologie réseau de contrôle d’admission des appels (par exemple, liaisons site-région, région-région et site-site) ;

  - afficher les informations de site, informations de région, stratégies de bande passante et liaisons réseau approvisionnées de la topologie réseau de contrôle d’admission des appels.

## Objectif

Afficher les liaisons de la topologie réseau de contrôle d’admission des appels dans une interface graphique.

## Exemples

**Charger et afficher la topologie réseau de contrôle d’admission des appels d’un déploiement Lync Server 2013 dans un format graphique** : les administrateurs Lync Server 2013 peuvent charger et afficher la configuration de topologie réseau de contrôle d’admission des appels sur un ordinateur Lync Server 2013 à l’aide de l’option **Download Network Configuration (Télécharger la configuration du réseau)**, comme indiqué dans la figure ci-dessous. L’outil ne parviendra pas à télécharger ou afficher une telle configuration si celle-ci est déployée sur un ordinateur sans connectivité au magasin de configuration Lync.

![Téléchargement de la configuration réseau.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Téléchargement de la configuration réseau.")

**Charger et afficher la topologie réseau de contrôle d’admission des appels à partir d‘un fichier journal de serveur de stratégie de bande passante dans un format graphique :** les serveurs de stratégie de bande passante Lync Server 2013 enregistrent la topologie réseau de contrôle d’admission des appels dans le cadre du mécanisme de journalisation sous l’emplacement du partage de fichiers Lync Server 2013. Les administrateurs Lync peuvent afficher ce fichier dans un format graphique à l’aide de l’option **Open Network Configuration (Ouvrir la configuration du réseau)**.

![Ouverture d’un fichier journal de serveur de stratégie de bande passante.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Ouverture d’un fichier journal de serveur de stratégie de bande passante.")

Enregistrer et stocker la topologie réseau de contrôle d’admission des appels dans un format XML sur le disque : les administrateurs Lync Server 2013 peuvent enregistrer le fichier de configuration de la topologie réseau de contrôle d’admission des appels dans un format XML à l’aide de l’option **Save a copy of Network Configuration (Enregistrer une copie de la configuration du réseau)**. Le fichier de configuration enregistré peut ensuite être utilisé en mode hors connexion à des fins d’affichage graphique.

![Enregistrement de la configuration réseau en tant que fichier XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Enregistrement de la configuration réseau en tant que fichier XML.")

Enregistrer et stocker le diagramme de la topologie réseau de contrôle d’admission des appels au format JPG ou BMP : les administrateurs Lync Server 2013 peuvent enregistrer la configuration de la topologie réseau de contrôle d’admission des appels dans un format graphique (formats JPG et BMP) à l’aide de l’option **Save Network Configuration diagram as picture (Enregistrer le diagramme de configuration du réseau en tant qu’image)**.

![Enregistrement de la configuration réseau en tant qu’image.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Enregistrement de la configuration réseau en tant qu’image.")

**Afficher les données de configuration de la topologie réseau de contrôle d’admission des appels :** les administrateurs Lync Server 2013 peuvent afficher les données de configuration du réseau liées (régions réseau, sites réseau, profils de bande passante, adresse IP des sous-réseau, etc.) dans un format textuel à l’aide de l’option View Network Configuration data (Afficher les données de configuration du réseau).

![Affichage des données de configuration réseau.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Affichage des données de configuration réseau.")

**Afficher la topologie réseau de contrôle d’admission des appels dans une arborescence :** les administrateurs Lync Server 2013 peuvent afficher les données de configuration du réseau liées dans une arborescence graphique à l’aide du panneau de configuration dans la partie gauche de la fenêtre de l’outil.

![Affichage des données de configuration réseau dans une arborescence.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Affichage des données de configuration réseau dans une arborescence.")

**Définir des connecteurs personnalisés pour les liaisons de la topologie réseau de contrôle d’admission des appels (par exemple, liaisons site-région, région-région et site-site) :** les administrateurs Lync Server 2013 peuvent définir des connecteurs graphiques personnalisés pour les liaisons de réseau étendu de la configuration réseau de contrôle d’admission des appels à l’aide de l’option Settings (Paramètres). Ceci permet de différencier divers types de liaisons réseau approvisionnées dans la configuration du réseau.

![Définition de connecteurs personnalisés pour la topologie de réseau CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Définition de connecteurs personnalisés pour la topologie de réseau CAC")

**Afficher les informations de site, informations de région et stratégies de bande passante approvisionnées de la topologie réseau de contrôle d’admission des appels :** les administrateurs Lync Server 2013 peuvent afficher les informations de région réseau de contrôle d’admission des appels, informations de site et informations d’approvisionnement de la bande passante de contrôle d’admission des appels à l’aide des options ci-dessous (par exemple, ils peuvent cliquer sur **Info (Informations)** dans un objet de région réseau ou de site réseau.)

![Définition de connecteurs personnalisés pour votre réseau.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Définition de connecteurs personnalisés pour votre réseau.")

## Résumé

Cet outil permet aux administrateurs Lync Server 2013 d’afficher la topologie réseau de contrôle d’admission des appels pour leur déploiement dans un format graphique.

## Response Group Agent Live

L’application Response Group permet aux agents d’accéder à des informations utiles en temps réel via son service web intégré. Aucun affichage graphique de ces données n’est toutefois disponible en dehors de l’application. L’outil de kit de ressources Response Group Agent Live résout ce problème en offrant un accès simple et graphique à ces informations, enrichi avec les informations en temps réel de Microsoft Lync 2013, telles que les informations de présence des autres agents.

## Description

L’application Windows Response Group Agent Live fournit des fonctionnalités de connexion et de déconnexion et donne des informations en temps réel (appartenance aux groupes, nombre actuel d’appels, etc.) aux agents Response Group. Il s’agit d’une version améliorée de la page Groupes d’agents (accessible dans Lync 2013).

## Objectif

L’application Response Group place les appels entrants en file d’attente avant de les acheminer vers des groupes d’agents. Pour identifier les appels à traiter de façon appropriée, les agents peuvent accéder à des informations en temps réel sur leurs groupes d’agents (agents disponibles, nombre d’appels en attente dans chaque file d’attente, etc.). Ces informations, à l’origine accessibles via le service Response Group uniquement, sont mises à disposition de façon intuitive par Response Group Agent Live.

## Fonctionnalités

L’outil Response Group Agent Live est basé sur le service Response Group et le Kit de développement logiciel (SDK) Microsoft Lync 2013. Il fournit aux agents Response Group les informations et fonctionnalités disponibles via le service Response Group (appartenance à des groupes, présence des autres agents, nombre d’appels en attente, etc.).

La figure suivante illustre l’interface principale de Response Group Agent Live.

![L’outil Response Group Agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "L’outil Response Group Agent Live.")

Les trois fonctionnalités principales suivantes sont accessibles aux agents dans Response Group Agent Live :

  - **Connexion/déconnexion :** contrairement à la page Groupes d’agents (accessible dans Lync 2013), Response Group Agent Live permet aux seuls agents de se connecter ou déconnecter de tous les groupes d’agents en une fois, de trois façons :
    
      - Cliquer sur les boutons Sign-in/out (Connexion/Déconnexion) (vert et rouge) dans l’application.
    
      - Cliquer avec le bouton droit sur la barre d’état système, et sélectionner Sign in (Connexion) ou Sign out (Déconnexion).
    
      - Utiliser des raccourcis clavier configurables.

  - **Appartenance aux groupes :** lorsqu’un groupe d’agents est sélectionné, Response Group Agent Live affiche la liste des agents de ce groupe dans le volet droit. Si Lync 2013 est exécuté sur le même ordinateur que cette application, les informations de présence et la carte de visite sont affichées dans Response Group Agent Live. Les agents peuvent envoyer un message instantané aux autres agents ou les appeler à partir de cet emplacement.

  - **Statistiques en temps réel :** Response Group Agent Live fournit des statistiques en temps réel pour tous les groupes d’agents. La fréquence de mise à jour est d’une minute. Lorsqu’un Response Group répond à un appel, un indicateur visuel est ajouté près du nom du groupe et le nombre actuel d’appels placés en file d’attente est indiqué. Pour afficher le délai d’attente le plus long, il suffit de placer le pointeur de la souris sur un groupe.

## Configuration requise

Response Group Agent Live nécessite .NET Framework 4.0. Pour utiliser les fonctionnalités de présence et de carte de visite, Lync 2013 doit également être installé localement (et être exécuté).

## Configuration

Response Group Agent Live peut être personnalisé selon les préférences individuelles via la boîte de dialogue Options de l’application. L’administrateur peut également définir l’adresse de l’hôte par défaut en modifiant directement la propriété defaultHostAddress du fichier RGAgentLive.exe.config.

La figure suivante illustre la boîte de dialogue Options qui permet aux agents de configurer l’adresse de l’hôte et les raccourcis clavier. Pour accéder à cette boîte de dialogue, il suffit de cliquer sur le bouton Options dans la partie supérieure droite de l’interface principale.

![La boîte de dialogue Options de l’outil Response Group Agent Live.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "La boîte de dialogue Options de l’outil Response Group Agent Live.")

Les trois paramètres suivants peuvent être personnalisés dans la configuration de Response Group Agent Live :

  - Host address (Adresse de l’hôte) : il s’agit généralement du nom de domaine complet du pool web appartenant au pool d’accueil de l’agent. L’adresse exacte du service Response Group est dérivée automatiquement en arrière-plan à partir de ces informations (en ajoutant le chemin d’accès correct après l’hôte).

  - Shortcuts (Raccourcis) : les raccourcis exacts pour la connexion/déconnexion peuvent être personnalisés. La seule limitation impose aux raccourcis d’inclure la touche du logo Windows (en plus d’une ou plusieurs autres touches).

  - Start with Windows (Démarrer avec Windows) : l’application peut être configurée pour démarrer automatiquement avec Windows.

## Exemples

La figure suivante illustre l’appel d’un autre agent ou l’envoi d’un message instantané à un autre agent en cliquant avec le bouton droit sur le contact dans le volet droit.

![Effectuer un appel ou envoyer un message instantané.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Effectuer un appel ou envoyer un message instantané.")

La figure suivante illustre l’affichage par Response Group Agent Live du nombre actuel d’appels dans la file d’attente et le délai d’attente le plus long parmi tous les appels entrants.

![Affichage des informations sur la file d’attente.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Affichage des informations sur la file d’attente.")

## Résumé

Les connexion et déconnexion rapides, l’appartenance aux groupes et les statistiques de base en temps réel constituent des fonctionnalités intéressantes de Response Group Agent seulement disponibles en dehors de l’application à partir du service Response Group. L’outil de kit de ressources Response Group Agent Live permet aux administrateurs Lync de fournir à leurs agents une application Windows pour effectuer leurs tâches rapidement, dans une interface graphique.

## SEFAUtil

L’outil en ligne de commande SEFAUtil (secondary extension feature activation) permet aux administrateurs du logiciel de communication Microsoft Lync Server 2013 et aux agents de support technique de configurer la sonnerie sur le poste de délégués, le transfert d’appel, la sonnerie simultanée, les paramètres d’appel d’équipe et la prise d’appel de groupe au nom d’un utilisateur Lync Server 2013. L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. L’outil SEFAUtil permet aux administrateurs d’activer/désactiver/modifier le transfert d’appel ou la sonnerie simultanée au nom de l’utilisateur. L’administrateur peut spécifier la cible (sous la forme d’un URI SIP) ou utiliser une cible déjà publiée par l’utilisateur. Cet outil permet également aux administrateurs d’ajouter ou de supprimer des délégués ou des membres d’un groupe d’appel d’équipe au nom de l’utilisateur. Il est basé sur Microsoft Unified Communications Managed API (UCMA) 3.0 et nécessite que les administrateurs créent une application approuvée dans le magasin central de gestion pour SEFAUtil.

SEFAUtil (secondary extension feature activation) permet aux administrateurs Lync Server 2013 et agents de support technique de configurer la sonnerie sur le poste de délégués, le transfert des appels, la sonnerie simultanée, les paramètres d’appel d’équipe et la prise d’appel de groupe au nom d’un utilisateur Lync Server 2013. L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier.

## Description

La version actuelle de SEFAUtil n’est qu’un outil en ligne de commande, sans interface utilisateur graphique. Cet outil est basé sur Microsoft Unified Communications Managed API (UCMA) 3.0. Ses fonctionnalités permettent aux administrateurs et agents du support technique d’effectuer les tâches suivantes :

  - afficher les paramètres de routage des appels d’un utilisateur (transfert d’appel, délégation, sonnerie simultanée, appel d’équipe et prise d’appel de groupe inclus) ;

  - activer/désactiver/modifier les paramètres de transfert d’appel (destination et minuteur d’absence de réponse inclus) ;

  - activer/désactiver/modifier les configurations immédiates de transfert d’appel ;

  - activer/désactiver/modifier les paramètres de délégation ;

  - activer/désactiver/modifier les paramètres d’appel d’équipe ;
    
    > [!NOTE]
    > Nouveauté de l’outil Lync Server 2013 SEFAUtil


  - activer/désactiver/modifier les paramètres de sonnerie simultanée (destination incluse) ;
    
    > [!NOTE]
    > Nouveauté de l’outil Lync Server 2013 SEFAUtil


  - activer/désactiver/modifier les paramètres de prise d’appel de groupe.
    
    > [!WARNING]
    > Nouveauté de l’outil Lync Server 2013 SEFAUtil


Cet outil présente les limitations suivantes :

  - prise en charge pour les seuls utilisateurs hébergés dans un pool Lync Server ;

  - modification en bloc des paramètres de routage des appels de plusieurs utilisateurs non prise en charge.

## Sortie

La version actuelle de cet outil génère une sortie dans la fenêtre d’invite de commandes uniquement. Pour plus d’informations, voir la section Exemples plus loin dans ce document.

## Objectif

Voici certains des principaux scénarios d’utilisation de cet outil :

  - Membre du personnel d’encadrement, Robert a été migré vers la téléphonie Lync Server. Il dispose d’une délégation sur son système PBX existant. Dans le cadre de la migration vers Lync, l’administrateur peut configurer le routage de Robert de façon à refléter sa configuration de délégation préexistante.

  - En plein déplacement, Alice réalise qu’elle attend un appel important d’un de ses clients. Elle se trouve toutefois à l’hôtel et n’a accès à aucun ordinateur. Elle contacte le support technique pour leur demander de transférer vers son numéro de téléphone portable tous les appels reçus sur son numéro de téléphone professionnel. Les membres du personnel du support technique peuvent effectuer cette opération de configuration pour elle.

  - Les appels reçus par Jean sur son numéro de téléphone professionnel sont transférés vers la messagerie vocale de son téléphone portable lorsqu’il se trouve sur son lieu de travail. Pour autant, tout semble fonctionner correctement dans la plupart des autres endroits. Le technicien du support technique consulte la configuration de routage de Jean et découvre que la sonnerie simultanée est configurée sur le téléphone portable de Jean. Il interroge Jean sur la couverture mobile sur son lieu de travail et parvient à déterminer que la règle de sonnerie simultanée est à l’origine du transfert des appels vers le messagerie vocale du téléphone portable de Jean lorsque sa couverture réseau est médiocre.

  - Nouvel employé de Contoso, Michel rejoint une équipe au sein de laquelle tous les membres sont configurés pour l’appel d’équipe. Lors de l’activation de Microsoft Lync, l’administrateur peut définir les paramètres de son groupe d’appel d’équipe afin d’inclure tous les nouveaux membres. Par ailleurs, il ajoute Michel en tant que membre du groupe d’appel d’équipe pour chacun des membres de son équipe.

  - Une pratique du service client dépendant du service Ressources humaines de Contoso consiste à offrir un service personnel à tous les appelants dès le premier appel. Tous les membres du service étant assis à proximité les uns des autres, la sonnerie de tous les téléphones en même temps en raison de l’activation de l’appel d’équipe est très perturbant pour le personnel. Pour offrir un service optimal sans perturbation pour les membres de l’équipe, l’administrateur Lync utilise la fonctionnalité de prise d’appel de groupe. Il ajoute tous les membres du service à un groupe de prise d’appel et communique le numéro de ce groupe au service. Pierre remarque que le téléphone de Samira sonne, alors que celle-ci s’est absentée, et prend donc l’appel à partir de son propre bureau.

## Configuration requise

L’outil SEFAUtil peut seulement être exécuté sur un ordinateur faisant partie d’un pool d’applications approuvées. UCMA 3.0 doit être installé sur cet ordinateur. Pour exécuter l’outil, une application approuvée avec l’ID d’application SEFAUtil doit être créée sur ce pool.

**Création d’une application approuvée pour l’outil SEFAUtil**

1.  L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées. Au besoin, l’ajout d’un pool en tant que nouveau pool d’applications approuvées peut être effectué via Lync Server Management Shell à l’aide de l’applet de commande suivante :
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    > [!NOTE]
    > UCMA 3.0 doit être installé sur les ordinateurs qui seront utilisés pour exécuter l’outil SEFAUtil.


2.  Une application approuvée doit être définie dans la topologie pour l’outil SEFAUtil. Pour définir SEFAUtil en tant que nouvelle application approuvée, utilisez Lync Server Management Shell et exécutez l’applet de commande suivante :
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    > [!NOTE]
    > Un autre port peut être utilisé au besoin.


3.  Les modifications apportées à la topologie doivent être activées. Pour ce faire, exécutez l’applet de commande suivante dans Lync Server Management Shell :
    
        Enable-CsToplogy

4.  Au besoin, installez les outils du kit de ressources Lync Server 2013 sur le serveur qui sera utilisé pour exécuter l’outil SEFAUtil (le serveur doit faire partie d’un pool d’applications approuvées).

5.  Vérifiez que SEFAUtil est correctement exécuté. Pour ce faire, exécutez l’outil à partir d’une invite de commandes de Windows avec des privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement. Par défaut, l’outil est situé dans : « …\\Program Files\\Microsoft Lync Server 2013\\Reskit ». Pour afficher les paramètres de transfert d’appel d’un utilisateur, utilisez la commande suivante :
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Les paramètres de transfert d’appel de l’utilisateur doivent s’afficher.

## Prise d’appel de groupe

L’activation complète de la fonctionnalité de prise d’appel de groupe nécessite des étapes de configuration supplémentaires dans Lync Server. Avant d’affecter les groupes de prise d’appels aux utilisateurs, consultez la documentation sur la prise d’appel de groupe pour connaître les étapes de planification et de déploiement de cette fonctionnalité.

## Exemples

## Afficher les paramètres actuels de gestion des appels

La commande suivante affiche le traitement des appels pour l’utilisateur : `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`.

> [!NOTE]
> Cet exemple utilise le commutateur <strong>/server</strong> pour spécifier le serveur Lync Server auquel se connecter.


**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

## Définir la destination du transfert d’appel/en cas d’absence de réponse

Cet exemple définit la destination du transfert d’appel/en cas d’absence de réponse et le délai de sonnerie. Le commutateur /server n’est pas fourni ici. SEFAUtil tente de découvrir automatiquement le serveur Lync Server.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

## Activer le transfert d’appel immédiatement

Cet exemple active immédiatement le transfert d’appel vers un autre utilisateur.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

## Désactiver immédiatement le transfert d’appel

Cet exemple désactivé immédiatement le transfert d’appel.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Ajouter un utilisateur en tant que délégué et définir la sonnerie simultanée des délégués

Cet exemple ajoute un utilisateur en tant que délégué et définit la sonnerie simultanée des délégués.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

## Modifier la règle de sonnerie simultanée des délégués

Cet exemple modifie la règle de sonnerie simultanée définie dans l’exemple précédent en règle de sonnerie différée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

## Supprimer le délégué

Cet exemple supprime le délégué.

> [!NOTE]
> Une fois le dernier délégué supprimé, la sonnerie sur le poste de délégués est désactivée automatiquement.


    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Ajouter un délégué et définir la règle de transfert d’appel aux délégués

Cet exemple ajoute un délégué et définit la règle de transfert d’appel aux délégués.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

## Activer la sonnerie simultanée et définir un numéro de destination

Cet exemple active la sonnerie simultanée et définit un numéro de destination pour la sonnerie simultanée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

> [!NOTE]
> Pour modifier le numéro de destination de la sonnerie simultanée d’un utilisateur pour lequel la sonnerie simultanée est déjà activée, conservez la commande avec le commutateur /enablesimulring, sans quoi le numéro de destination ne sera pas modifié.


**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

## Désactiver la sonnerie simultanée

Cet exemple désactive la sonnerie simultanée.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Ajouter un membre d’équipe pour l’appel d’équipe et définir la sonnerie simultanée sur le groupe d’appel d’équipe

Cet exemple ajoute un membre d’équipe au groupe d’appel d’équipe d’un utilisateur et active la sonnerie simultanée sur le groupe d’appel d’équipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

> [!NOTE]
> L’ajout d’un membre au groupe d’appel d’équipe d’un utilisateur définit automatiquement les paramètres de sonnerie simultanée des utilisateurs sur la sonnerie simultanée de son groupe d’appel d’équipe.


**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

## Supprimer un membre du groupe d’appel d’équipe

Cet exemple supprime un membre d’équipe du groupe d’appel d’équipe d’un utilisateur.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

> [!NOTE]
> Si le membre supprimé est le seul du groupe d’appel d’équipe, la sonnerie simultanée du groupe d’appel d’équipe est automatiquement désactivée.


**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Définir la sonnerie différée sur le groupe d’appel d’équipe

Cet exemple définit la sonnerie différée sur le paramètre d’heure du groupe d’appel d’équipe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

## Activer l’appel d’équipe

Cet exemple active l’appel d’équipe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

> [!NOTE]
> S’il n’y a aucun membre dans le groupe d’appel d’équipe de l’utilisateur, l’appel d’équipe ne sera pas activé.


**Sortie**

## Désactiver l’appel d’équipe

Cet exemple désactive l’appel d’équipe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Activer la prise d’appel de groupe et affecter un groupe de prise d’appel à un utilisateur

Cet exemple affecte un groupe de prise d’appel à un utilisateur et active la prise d’appel de groupe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Sortie**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

## Désactiver la prise d’appel de groupe

Cet exemple désactive la prise d’appel de groupe pour un utilisateur donné.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

> [!NOTE]
> Lorsque vous désactivez la prise d’appel de groupe pour un utilisateur, le numéro de groupe affecté à cet utilisateur n’est pas conservé. Si vous souhaitez ultérieurement réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réaffecter le numéro de groupe avec le commutateur /enablegrouppickup.


    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

## SYSPrep.ps1

## Description

Le script Windows PowerShell SYSPrep.ps1 installe les logiciels prérequis Lync Server 2013 suivants sur votre ordinateur système d’exploitation Windows Server 2008.

  - Microsoft .Net Framework 4.5 ;

  - Microsoft SQL Server Express ;

  - Windows Powershell version 3.0 ;

  - Visual C++ 2010 Redistributable ;

  - mises à jour d’Internet Information Services ;

  - Windows Identity Foundation ;

  - fichiers principaux de Lync Server 2013.

Si le nom du script est semblable à l’outil de préparation du système pour les systèmes d’exploitation Microsoft Windows, ils sont toutefois différents. Ce script installe uniquement les logiciels prérequis pour Lync Server 2013. Une fois ceux-ci installés, l’outil Windows SYSPrep peut ensuite être utilisé pour créer une image du serveur.

## Configuration requise

Avant d’exécuter le script SYSPrep.ps1, vous devez copier les fichiers des logiciels prérequis dans un dossier local sur l’ordinateur système d’exploitation Windows Server 2008 (par exemple, **D:\\Setup)**. Ce dossier doit également inclure une copie des fichiers Lync Server 2013, notamment **Setup.exe.** Les fichiers des logiciels prérequis peuvent être téléchargés aux emplacements suivants :


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
<td><p>http://www.microsoft.com/fr-fr/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows Powershell version 3.0</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 Redistributable</p></td>
<td><p>http://www.microsoft.com/fr-fr/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour d’Internet Information Services</p></td>
<td><p>http://www.microsoft.com/fr-fr/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/fr-fr/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Fichier Setup.exe de Lync Server 2013</p></td>
<td><p>Copier à partir du média Lync Server 2013</p></td>
</tr>
</tbody>
</table>


## Paramètre

Le paramètre **–SetupFolder** prend comme argument l’emplacement de répertoire des fichiers prérequis.

## Exemples

Pour exécuter le script SYSPrep.ps1 et installer les logiciels prérequis pour Lync Server 2013, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges :

    ./SysPrep.PS1 -SetupFolder D:\Setup

## Unassigned Number Announcements Migration

L’outil Unassigned Number Announcements Migration permet aux administrateurs Lync de déplacer la configuration des numéros non attribués pris en charge par l’application d’annonce entre un pool ou un serveur Lync Server source et un pool ou un serveur Lync Server de destination.

## Description

L’outil Unassigned Number Announcements Migration est un script Windows PowerShell qui déplace la configuration des numéros non attribués pris en charge par l’application d’annonce entre un pool ou un serveur source et un autre pool ou serveur.

Lorsqu’il est exécuté, le script Unassigned Number Announcements Migration effectue les opérations suivantes :

1.  Déplacer tous les fichiers audio utilisés par les annonces de numéros non attribués de l’application d’annonce hébergée sur le pool ou serveur source vers le magasin de fichiers du pool ou serveur de destination.
    
    > [!NOTE]
    > Les fichiers audio sont supprimés du pool source une fois qu’ils sont copiés sur le pool de destination.


2.  Déplacer les annonces de numéros non attribués configurées pour l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.

3.  Réaffecter toutes les plages de numéros non attribués prises en charge par l’application d’annonce hébergée dans le pool ou serveur source vers le pool ou serveur de destination.

Une fois le script correctement exécuté, toutes les plages de numéros affectés prises en charge par l’application d’annonce hébergée dans le pool ou serveur source sont à présent prises en charge avec la même configuration par le pool ou le serveur de destination.

## Sortie

Le script **Move-CsAnnouncementConfiguration** indique dans la fenêtre Lync Management Shell depuis laquelle il est exécuté le succès ou l’échec de l’opération de migration.

Si l’exécution de l’opération est interrompue par une erreur, les plages de numéros non attribués correctement déplacées vers la destination sont conservées dans la destination sous une forme opérationnelle et le reste des plages de numéros non attribués à migrer sont conservés dans la source sous une forme opérationnelle également. Pour migrer entièrement le reste de la configuration, exécutez à nouveau le script après avoir traité l’erreur.

## Objectif

Le script Unassigned Number Announcements Migration peut être utilisé dans le cadre des scénarios suivants :

  - **Migration des paramètres de configuration vers une nouvelle version de Lync Server :** Contoso est en en plein processus de migration vers Lync Server 2013. Dans le cadre de cette opération, l’administrateur Lync Server souhaite déplacer la configuration des numéros non affectés pris en charge par l’application d’annonce entre le déploiement Lync Server 2010 et le nouveau déploiement Lync Server 2013. Pour déplacer les paramètres de configuration, l’administrateur Lync Server utilise l’outil Unassigned Number Announcements Migration.

  - **Restauration d’un déploiement de Lync Server 2013 vers Lync Server 2010 :** en raison d’impondérables, Contoso doit annuler la migration vers le nouveau déploiement Lync Server 2013. Pour minimiser l’interruption du service, l’administrateur Lync Server utilise l’outil Unassigned Number Announcements Migration pour restaurer la configuration du déploiement Lync Server 2013 vers le déploiement Lync Server 2010.

  - **Déplacement de données entre des déploiements Lync :** Contoso est en train de remplacer tous les serveurs d’un pool par de nouveaux serveurs. Leur stratégie consiste à déployer un nouveau pool Lync Server 2013, déplacer toutes les données de l’ancien pool vers le nouveau, puis supprimer l’ancien pool. Une fois le nouveau pool déployé, l’outil Unassigned Number Announcements Migration est utilisé pour déplacer la configuration de l’ancien pool vers le nouveau.

## Configuration requise

Les principaux éléments de configuration suivants sont requis pour exécuter correctement l’outil :

1.  Le script doit être exécuté à partir d’un ordinateur sur lequel Lync Server 2013 Management Shell est installé.

2.  L’application d’annonce doit être correctement déployée dans les pools ou serveurs Lync Server sources et de destination.

## Script Move-CsAnnouncementConfiguration

Le script Move-CsAnnouncementConfiguration nécessite les deux paramètres décrits dans le tableau suivant.

![Paramètres Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Paramètres Move-CsAnnouncementConfiguration.")

## Exemples

## Déplacement de la configuration des annonces de numéros non attribués entre un pool Lync Server 2010 et un pool Lync Server 2013

Cet exemple déplace les annonces de numéros non attribués entre un pool source (Lync Server 2010) et un pool de destination (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

## Déplacement de la configuration des annonces de numéros non attribués entre un pool Lync Server 2013 et un pool Lync Server 2010

Cet exemple déplace les annonces de numéros non attribués entre un pool source (Lync Server 2013) et un pool de destination (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

## Web Conf Data

L’outil Web Conf Data permet aux administrateurs du logiciel de communication Lync Server 2013 de contrôler davantage les données associées aux conférences web d’un organisateur. Les scénarios incluent la possibilité de supprimer les données de réunion d’un utilisateur spécifique sur la base de critères de date/heure.

## Description

Cet outil permet aux administrateurs d’effectuer les opérations suivantes :

1.  Rechercher les données de conférence web associées à un utilisateur.

2.  Supprimer les données de conférence web associées à un utilisateur.

3.  Supprimer les données de conférence web associées à un utilisateur antérieures à une date donnée.

4.  Déplacer les données de conférence web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre.

> [!NOTE]
> Les outils du Kit de ressources pour Lync Server 2010 prenaient en charge le déplacement des données de conférence web associées à un utilisateur lorsque celui-ci est déplacé d’un pool vers un autre. Cette fonctionnalité a été supprimée de cet outil et remplacée par le paramètre <strong>MoveConferenceData</strong>. Pour plus d’informations sur ce paramètre, voir l’applet de commande <a href="https://technet.microsoft.com/fr-fr/library/gg398528(v=ocs.15)">Move-CsUser</a>.


L’outil supprime les données de réunion uniquement pour les réunions inactives. Les réunions actives (ou réunions en sessions) ne peuvent pas être supprimées.

Cet outil doit être exécuté à partir d’un ordinateur situé dans le même pool que l’utilisateur cible. L’utilisateur dont les données de contenu de réunion sont gérées par cet outil doit être hébergé dans le même pool d’utilisateurs.

## Sortie

L’outil génère des résultats pour chacune des opérations :

  - Si une requête est exécutée, l’outil génère la liste de tous les dossiers de données des réunions inactives organisées par cet utilisateur.

  - En cas de suppression, l’outil génère la liste des dossiers de données de toutes les réunions pour lesquelles les données seront supprimées.

## Configuration requise

L’outil doit être exécuté dans le même pool qui héberge actuellement l’organisateur.

L’outil doit être exécuté à l’aide de privilèges d’administrateur avec un accès au magasin de fichiers de contenu.

## Exemples

Le tableau suivant décrit les paramètres (certains d’entre eux sont utilisés dans les exemples).

![Paramètres de l’outil Web Conf Data.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Paramètres de l’outil Web Conf Data.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

L’exemple précédent montre le fonctionnement d’une commande de requête. La sortie d’une telle commande est une liste des dossiers de contenu de réunion affectés par cet outil.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

L’exemple précédent est une commande de suppression. Cette commande supprime les dossiers des réunions inactives pour cet utilisateur.

## Résumé

Cet outil offre aux administrateurs un contrôle plus précis sur les données de réunion de conférence.

