---
title: Gestion de Skype Entreprise Server 2015 à l’aide d’un pack d’administration SCOM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Résumé : Découvrez comment configurer votre infrastructure 2015 de Skype entreprise Server pour qu’elle fonctionne avec System Center Operations Manager.'
ms.openlocfilehash: 5622b09b3d55b4d0d3a3fe026f66b28e3c4be75e
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "36824547"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Gestion de Skype Entreprise Server 2015 à l’aide d’un pack d’administration SCOM
 
**Résumé :** Apprenez à configurer votre infrastructure 2015 de Skype entreprise Server pour qu’elle fonctionne avec System Center Operations Manager.
  
Idéalement, vous ne rencontrez jamais de problèmes avec Skype entreprise Server 2015. Toutefois, Skype entreprise Server peut être affecté par des facteurs extérieurs (par exemple, des blocages réseau et des pannes matérielles). L’utilisation de Skype entreprise Server 2015 Management packs vous permet d’identifier les problèmes potentiels de manière proactive et de les corriger. De cette façon, les packs d’administration 2015 de Skype entreprise Server étendent les capacités de System Center Operations Manager.
  
Ces informations ont été rédigées en fonction de la version 9319,0 du Pack de surveillance pour le logiciel de communication de Skype entreprise Server 2015.
  
## <a name="configuration-overview"></a>Vue d’ensemble de la configuration

 Pour configurer votre infrastructure 2015 de Skype entreprise Server pour qu’elle fonctionne avec System Center Operations Manager, vous devez effectuer les trois opérations suivantes :
  
Identifiez et [configurez le serveur de gestion principal](configure-the-primary.md). Pour cela, vous devez installer System Center Operations Manager 2012 SP1 ou R2. 
  
 Identifiez et [configurez les ordinateurs du serveur Skype entreprise qui seront surveillés](configure-computers-to-monitor.md). Pour surveiller un ordinateur Skype entreprise Server à l’aide de System Center Operations Manager, vous devez installer les fichiers de l’agent System Center Operations Manager et configurer chaque serveur pour qu’il serve de proxy. 
  
 Identifier et [installer et configurer les nœuds d’observation](watcher-nodes.md); Les nœuds d’observation sont des ordinateurs qui exécutent périodiquement des transactions synthétiques de Skype entreprise Server : les applets de contrôle Windows PowerShell qui vérifient les principaux composants de Skype entreprise Server, comme la possibilité de se connecter au système ou la possibilité d’échanger des fichiers instantanés. les messages fonctionnent comme prévu. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Support technique du serveur de gestion racine et de l’agent System Center Operations Manager

Les packs de gestion peuvent être utilisés avec System Center Operations Manager 2007 R2 (64 bits) (pris en charge à des fins de migration uniquement) ou &amp; System Center Operations Manager 2012 SP1 R2 (64-bit) ou le gestionnaire d’opérations de system Center 2016 (64-bit). Le tableau suivant indique les configurations prises en charge pour les packs de gestion de Skype entreprise Server 2015 : 
  
|Configuration|Pris en charge ?|
|:-----|:-----|
|Système d’exploitation Windows Server 2008 R2  <br/> Système d’exploitation Windows Server 2012 R2  <br/> |Oui. Les nœuds du serveur et de l’observateur de transactions synthétiques de Skype entreprise Server 2015.  <br/> |
|Serveurs en cluster  <br/> |Non pris en charge.  <br/> |
|Surveillance sans agent  <br/> |Non prise en charge.  <br/> |
|Environnement virtuel  <br/> |Oui.  <br/> |
|Rôles serveur liés au domaine  <br/> |Tous les rôles serveur internes Skype entreprise Server 2015 doivent être joints au domaine.  <br/> |
|Rôles serveur autonomes  <br/> |Les serveurs Edge de Skype entreprise Server 2015 ne doivent pas nécessairement être liés à un domaine.  <br/> |
|Limitations de la topologie  <br/> |Tous les rôles serveur d’un déploiement doivent être surveillés à partir du même groupe d’administration Operations Manager.  <br/> |
|Nœud observateur de transactions synthétiques  <br/> |La surveillance de la disponibilité des scénarios avec un nœud observateur de transactions synthétiques est prise en charge (configuration supplémentaire nécessaire). Les nœuds observateurs n’ont pas besoin d’être associés à un domaine.  <br/> |
   
Le tableau ci-dessous détaille la capacité et la configuration de système d’exploitation requises pour un nœud observateur de transactions synthétiques :
  
|Composant matériel|Spécification minimale|
|:-----|:-----|
|Processeur  <br/> |L’un des éléments suivants :  <br/> Processeur 64 bits, quadruple cœur 2,33 GHz ou supérieur  <br/> Processeur 64 bits à deux voies, double cœur, 2,33 GHz ou supérieur  <br/> |
|Mémoire  <br/> |8 Go  <br/> |
|Système d’exploitation  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Réseau  <br/> |1 carte réseau 1 Gbits/s  <br/> |
   
## <a name="prerequisites"></a>Conditions requises

Pour exécuter un nœud observateur de transaction synthétique, vous devez d’abord installer les éléments suivants :
  
- Agent System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Les fichiers d’installation principaux de Skype entreprise Server (OcsCore. msi) et l’API gérée de communications unifiées (UCMA) (versions doivent correspondre à la version de Skype entreprise Server WatcherNode. msi)
    
## <a name="files-in-this-monitoring-pack"></a>Fichiers contenus dans ce pack de surveillance

Le pack d’analyse de Skype entreprise Server 2015 inclut les fichiers suivants :
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Nouveautés

Les fonctionnalités suivantes sont nouvelles dans les packs d’administration 2015 de Skype entreprise Server.

- **Modification de la [mise à jour 2019 de septembre](https://www.microsoft.com/en-in/download/details.aspx?id=47364) ** Certaines alertes comportent des caractères spéciaux supprimés. Dans certains cas, des caractères spéciaux interfèrent à la fonctionnalité de notification de canal de commandes SCOM.

- **Découverte automatique pour la connexion au client** Les applications clientes qui se connectent à Skype entreprise Server 2015 découvrent souvent automatiquement le serveur pour s’y connecter. Les transactions synthétiques prennent maintenant en charge la vérification de la configuration appropriée de la découverte automatique.
    
- **Intervalles d’exécution de transactions synthétiques personnalisés** Pour simplifier le processus de configuration des nœuds d’observation, les transactions synthétiques peuvent partager des comptes d’utilisateurs. Cela ralentit la fréquence d’exécution des tests dans la mesure où les tests sont sérialisés pour éviter les conflits. Par défaut, les transactions synthétiques sont exécutées toutes les 15 minutes pour que tous les tests aient le temps de s’exécuter. Les administrateurs qui choisissent d’utiliser plus d’utilisateurs ou moins de tests par utilisateur peuvent désormais réduire également l’intervalle d’exécution.
    
- **Transaction synthétique de services d’interopérabilité de vidéo** Les clients qui migrent vers Skype entreprise Server 2015 à partir d’autres solutions de fournisseurs souhaitent souvent continuer à utiliser les appareils de visioconférence vidéo (VTCs) de ces autres fournisseurs. Le serveur Video Interop est un nouveau rôle de serveur Skype entreprise Server 2015 qui permet aux clients de continuer à utiliser Cisco VTCs dans leurs salles de conférence en se connectant à Cisco CUCM via un câble SIP vidéo. Cette fonctionnalité ajoute également une transaction synthétique afin de vérifier que le serveur d’interopérabilité vidéo (VIS) peut gérer les connexions entrantes sur une jonction SIP vidéo.
    
- **Transaction synthétique de conférence de partage d’applications** La validation de scénario de bout en bout des conférences de partage d’applications est désormais prise en charge.
    
## <a name="monitoring-scenarios"></a>Scénarios de surveillance

Le pack d’administration 2015 de Skype entreprise Server exploite plusieurs fonctionnalités pour vous aider à détecter et à diagnostiquer des problèmes. Ces fonctionnalités offrent une visibilité en temps réel sur l’état d’un environnement 2015 de Skype entreprise Server.
  
|Scénario de surveillance|Description|
|:-----|:-----|
|Transactions synthétiques  <br/> | Cmdlets Windows PowerShell permettant de tester et de garantir une haute disponibilité des scénarios tels que la connexion, la présence, la messagerie instantanée et les conférences pour les utilisateurs. <br/> Les transactions synthétiques peuvent être exécutées à partir de n’importe quel emplacement géographique dans l’entreprise, en dehors de l’entreprise et dans les succursales.  <br/> Lorsqu’une transaction synthétique échoue, des journaux HTML sont créés pour vous aider à déterminer la nature exacte de l’échec. Cela inclut des informations sur l’action qui a échoué, la latence de chaque action, la ligne de commande à partir de laquelle a été exécuté le test ainsi que l’erreur spécifique rencontrée.  <br/> |
|Alertes de fiabilité des appels  <br/> |Les enregistrements des détails des appels écrits par les serveurs 2015 de Skype entreprise Server indiquent si les utilisateurs sont en mesure de se connecter à un appel ou de mettre fin à un appel. Les alertes de fiabilité des appels analysent la base de données des enregistrements des détails des appels afin de générer des alertes qui s’affichent lorsque de nombreux utilisateurs rencontrent des problèmes de connectivité liés à des appels d’égal à égal ou à des fonctionnalités de conférence de base.  <br/> Les scénarios incluent notamment les appels audio, les messages instantanés d’égal à égal et d’autres fonctionnalités de conférence.  <br/> |
|Alertes de qualité des médias  <br/> |Les requêtes de base de données qui examinent les rapports de qualité de l’expérimentation (QoE) publiés par Skype entreprise Server 2015 clients à la fin de chaque appel. Ces requêtes génèrent des alertes qui avertissent que les utilisateurs des scénarios signalés risquent d’être confrontés à une dégradation de la qualité des médias lors des appels et des conférences. Les données sont établies à partir de mesures clés, telles que la latence et la perte de paquets, qui s’avèrent décisives pour le niveau de qualité de l’expérience utilisateur.  <br/> |
|Alertes d’intégrité des composants  <br/> |Les composants serveur déclenchent des alertes via les journaux des événements et les compteurs de performances. Ces alertes signalent les conditions d’échec qui peuvent avoir un impact sérieux sur un ou plusieurs scénarios utilisateur. Elles peuvent également indiquer diverses autres conditions d’échec, parmi lesquelles l’arrêt de services, des taux d’échec élevés ou des problèmes de connectivité.  <br/> |
|Analyse d’intégrité de dépendance  <br/> |Skype entreprise Server peut échouer pour diverses raisons externes. Le pack d’administration analyse et collecte les données relatives à certaines dépendances externes critiques, qui peuvent révéler des problèmes majeurs. Ces dépendances incluent la disponibilité d’Internet Information Services (IIS) et le processeur des serveurs utilisés pour Skype entreprise Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Priorisation des alertes

Les alertes sont classées selon les catégories suivantes : 
  
 **Alertes de priorité élevée :** Ces alertes indiquent des conditions qui engendrent des interruptions de service pour des groupes d’utilisateurs de grande taille et nécessitent une action immédiate. Les pannes détectées par les transactions synthétiques et les services hors connexion (par exemple, les conférences audio/vidéo de Skype entreprise Server) sont éligibles en tant qu’alertes à priorité élevée. En revanche, une erreur de type composant sur un seul ordinateur n’est pas une alerte de priorité élevée. Skype entreprise Server 2015 inclut des fonctionnalités haute disponibilité intégrées dans ces situations (par exemple, plusieurs serveurs frontaux derrière des équilibreurs de charge).
  
 **Alertes de priorité moyenne :** Ces alertes indiquent des conditions qui affectent un sous-ensemble d’utilisateurs ou qui indiquent des problèmes de qualité d’appel (par exemple, échecs de composants, latence dans l’établissement d’un appel ou qualité audio dans les appels). Les alertes de cette catégorie sont à la fois portées (autrement dit, la nature de l’alerte change en fonction de l’état de la connexion réseau.) Par exemple, si les heures d’établissement d’un appel indiquent une latence, mais que vous revenez à un seuil normal, cette alerte de priorité moyenne serait corrigée automatiquement dans System Center Operations Manager et les administrateurs n’ont pas besoin d’entreprendre une action. Les alertes qui ne peuvent pas être corrigées automatiquement sont généralement adressées par des administrateurs le même jour ouvrable.
  
 **Autres alertes :** ces alertes concernent des composants susceptibles d’affecter un ou plusieurs utilisateurs. Par exemple, une alerte type peut signaler que le service de carnet d’adresses n’a pas pu analyser l’entrée AD DS ( Active Directory® Domain Services) de l’utilisateur« testuser@contoso.com ». Les administrateurs peuvent corriger ces alertes lorsqu’ils ont le temps.
  
### <a name="synthetic-transactions"></a>Transactions synthétiques

Les packs d’administration de Skype entreprise Server 2015 garantissent une meilleure couverture des alertes par le biais de transactions synthétiques. Les transactions synthétiques sont intégrées dans le pack d’administration Operations Manager pour tester des scénarios utilisateur de bout en bout. Lorsque vous désignez un serveur pour exécuter des transactions synthétiques, celles-ci sont déclenchées périodiquement par le pack d’administration. Les échecs résultant d’une transaction synthétique génèrent une alerte avec état. Voici les transactions synthétiques prises en charge pour Skype entreprise Server 2015 :
  


|Transactions synthétiques prises en charge pour l’inscription, la présence et les contacts|||
|:-----|:-----|:-----|
|1  <br/> |Inscription (connexion de l’utilisateur)  <br/> |Disponible Lync Server 2010 et les versions ultérieures  <br/> |
|deuxième  <br/> |Service de carnet d’adresses (téléchargement de fichier)  <br/> |Disponible Lync Server 2010 et les versions ultérieures  <br/> |
|3  <br/> |Recherche web du carnet d’adresses  <br/> |Disponible Lync Server 2010 et les versions ultérieures  <br/> |
|4  <br/> |Présence  <br/> |Disponible Lync Server 2010 et les versions ultérieures  <br/> |
|5  <br/> |Magasin de contacts unifié  <br/> |Disponible Lync Server 2013 et les versions ultérieures  <br/> |
||||   

|Transactions synthétiques prises en charge pour les services d’égal à égal|||
|:-----|:-----|:-----|
|6  <br/> |Messagerie instantanée d’égal à égal  <br/> |Disponible dans Lync Server 2010 et les versions ultérieures  <br/> |
|7  <br/> |Appels audio/vidéo d’égal à égal  <br/> |Disponible dans Lync Server 2010 et les versions ultérieures  <br/> |
|version8  <br/> |Messagerie instantanée d’égal à égal MCX (mobile)  <br/> |Disponible dans la version 2011 de Lync Server 2010 vers Skype entreprise 2015  <br/> |
 
> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.


|Transactions synthétiques prises en charge pour les conférences et la conversation permanente|||
|:-----|:-----|:-----|
|09  <br/> |Conférence audio-vidéo  <br/> |Disponible dans Lync Server 2010 et les versions ultérieures  <br/> |
|0,10  <br/> |Conférence de données  <br/> |Disponible dans Lync Server 2013 et les versions ultérieures  <br/> |
|27,9  <br/> |Conférence par messages instantanés  <br/> |Disponible dans Lync Server 2010 et les versions ultérieures  <br/> |
|midi  <br/> | Conversation permanente <br/> |Disponible dans Lync Server 2013 et les versions ultérieures  <br/> |
|n°13  <br/> |Lanceur de participation (réunions planifiées)  <br/> |Disponible dans Lync Server 2013 et les versions ultérieures  <br/> |
|14  <br/> |Conférence rendez-vous  <br/> |Nouveautés de Skype entreprise Server 2015  <br/> |
|0,15  <br/> |Conférence de partage d’applications  <br/> |Nouveautés de Skype entreprise Server 2015  <br/> |
|Seiz  <br/> |Conférence UCWA (participation à une réunion web)  <br/> |Nouveautés de Skype entreprise Server 2015  <br/> |
||||

|Transactions synthétiques prises en charge pour les dépendances de réseau et de partenaires|||
|:-----|:-----|:-----|
|Play  <br/> |Connectivité Edge A/V  <br/> |Disponible dans Lync Server 2013 et les versions ultérieures  <br/> |
|19  <br/> |Connectivité de messagerie unifiée Exchange de la connectivité Edge A/V (messagerie vocale)  <br/> |Disponible dans Lync Server 2013 et les versions ultérieures  <br/> |
|19,6  <br/> |Appels d’égal à égal PSTN  <br/> |Disponible dans Lync Server 2010 et les versions ultérieures  <br/> |
|CX3-20  <br/> |Messagerie instantanée XMPP (fédération)  <br/> |Disponible dans Lync Server 2013 et Skype entreprise 2015  <br/> |
|vingt  <br/> |Serveur VIS (Video Interop Server)  <br/> |Nouveautés de Skype entreprise Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Comment se présente l’intégrité

Le tableau suivant indique les États d’intégrité des objets du pack d’analyse Skype entreprise Server.
  
|Objet du pack d’administration|Description|
|:-----|:-----|
|Déploiement de Skype entreprise Server  <br/> |Représente le déploiement de Skype entreprise Server 2015 au sein de l’organisation.  <br/> |
|Site Skype entreprise Server  <br/> |Représente différents emplacements géographiques où les services sont déployés.  <br/> |
|Liste de serveurs Skype entreprise Server  <br/> |Pool (au sein d’un site) qui fournit des services de communications, tels que la messagerie instantanée et les conférences, aux utilisateurs. Applicable aux pools frontaux, pools de serveurs Edge et pools directeurs, même si un pool donné ne comporte qu’un seul ordinateur.  <br/> |
|Rôle du serveur Skype entreprise  <br/> |Un rôle serveur qui héberge le service Skype entreprise Server.  <br/> |
|Service Skype entreprise Server  <br/> |Représente une fonctionnalité déployée sur un ordinateur spécifique (par exemple, service utilisateur sur fp01.contoso.com).  <br/> |
|Composant Skype entreprise Server  <br/> |Composant du service (par exemple, le composant de téléchargement de carnet d’adresses est un composant du Service Web).  <br/> |
|Observateur de pools de serveurs Skype entreprise  <br/> |Instance de transactions synthétiques s’exécutant sur un pool.  <br/> |
|Skype entreprise Server Registrar Watcher  <br/> |Instance de transactions synthétiques s’exécutant sur un pool de serveurs d’inscriptions.  <br/> |
|Service d’observation du pool de services d’utilisateurs Skype entreprise Server  <br/> |Instance de transactions synthétiques s’exécutant sur un pool de services utilisateurs.  <br/> |
|Observateur de la liste vocale Skype entreprise Server  <br/> |Instance de transactions synthétiques s’exécutant sur un pool Voix.  <br/> |
|Observateur de port Skype entreprise Server  <br/> |Instance de vérifications de port s’exécutant sur un pool.  <br/> |
|Observateur d’URL simple  <br/> |Effectue une analyse HTTPS des URL simples configurées dans le cadre d’un déploiement.  <br/> |
   
![Déploiement SCOM](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un pool Skype entreprise Server peut contenir plusieurs systèmes Skype entreprise Server individuels (avec plusieurs rôles Skype entreprise Server, un service Skype entreprise Server et un composant Skype entreprise Server). Par conséquent, l’échec d’un serveur ou composant individuel est moins essentiel pour l’état global du pool de serveurs Skype entreprise, car d’autres serveurs dans le même pool peuvent fournir le service d’application au client. Le niveau de progression sera cumulé sur le pool Skype entreprise Server. 
  
Le surveillant de pool Skype entreprise Server effectue des transactions synthétiques sur un pool de serveurs Skype entreprise. Les échecs consécutifs d’une ou de plusieurs transactions synthétiques (un processus appelé intervalle d’interrogation consécutif) cumuleront l’état d’intégrité critique au niveau du pool (le pire de toute transaction synthétique), comme illustré dans le diagramme suivant. 
  
![Interrogation consécutive du déploiement SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Meilleure pratique : création d’un pack d’administration pour les personnalisations

Par défaut, Operations Manager enregistre toutes les personnalisations, telles que les remplacements dans le pack d’administration par défaut. Il est recommandé de créer un pack d’administration distinct pour chaque pack d’administration scellé que vous souhaitez personnaliser. 
  
Lorsque vous créez un pack d’administration en vue du stockage de paramètres personnalisés pour un pack d’administration scellé, nous vous recommandons de nommer le nouveau pack d’administration de façon appropriée, par exemple « Personnalisations Skype Entreprise Server 2015 ». 
  
La création d’un nouveau pack d’administration pour le stockage des personnalisations de chaque pack d’administration scellé facilite l’exportation des personnalisations d’un environnement de test vers un environnement de production. Elle facilite également la suppression d’un pack d’administration, car vous devez supprimer toutes les dépendances avant de pouvoir supprimer un pack d’administration. Si les personnalisations de tous les packs d’administration sont enregistrées dans le pack d’administration par défaut et que vous devez supprimer un seul pack d’administration, vous devez d’abord supprimer le pack d’administration par défaut, ce qui supprimera également les personnalisations des autres packs d’administration. 
  
## <a name="links"></a>Liens

Les liens suivants vous permettent d’accéder à des informations sur les tâches courantes associées aux packs de surveillance System Center 2012 :
  
- [Cycle de vie d’un pack de gestion](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Importation d’un pack d’administration dans Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Remplacer une règle ou un moniteur](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Création d’un compte exécuter en tant que dans Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Gestion de l’exécution en tant que comptes et profils](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Exportation d’un pack d’administration Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Comment supprimer un pack d’administration Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Les liens suivants vous permettent d’accéder à des informations sur les tâches courantes associées aux packs de surveillance System Center 2007 :
  
- [Gestion du cycle de vie d’un pack de gestion](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Importation d’un pack d’administration dans Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Surveiller au moyen de remplacements](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Création d’un compte exécuter en tant que dans Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Comment modifier une exécution en tant que profil](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Comment exporter des personnalisations du pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Suppression d’un pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Pour plus d’informations sur Operations Manager et les packs de surveillance, voir le Forum de la [communauté Operations Manager System Center](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Une ressource utile est le blog d' [Operations Manager de System Center Operations Manager](https://opsmgrunleashed.wordpress.com/) , lequel contient des publications « par exemple » pour des packages d’analyse spécifiques.
  
Pour plus d’informations sur Operations Manager, reportez-vous aux blogs suivants : 
  
- [Blog de l’équipe Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog d’Operations Manager de kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Réflexions sur Operations Manager](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de raphael Burri](https://rburri.wordpress.com/)
    
- [Espace de gestion de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [OPS Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toutes les informations et le contenu figurant sur des sites non-Microsoft sont fournis par le propriétaire ou les utilisateurs de ces sites web. Microsoft exclut toute garantie expresse, implicite ou légale concernant les informations qu’ils contiennent. 
  
## <a name="see-also"></a>Voir aussi

[Outils de gestion de Skype entreprise Server 2015](../../management-tools/management-tools.md)
