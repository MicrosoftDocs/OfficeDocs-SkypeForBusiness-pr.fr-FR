---
title: Gérer les Skype pour Business Server 2019 à l’aide du pack d’administration SCOM
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/26/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Découvrez comment configurer votre Skype pour infrastructure Business Server 2019 pour travailler avec System Center Operations Manager.'
ms.openlocfilehash: 89aeb18f896510dd251519b8a4fb618012d7e222
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26536024"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Gérer les Skype pour Business Server 2019 à l’aide du pack d’administration SCOM
 
**Résumé :** Découvrez comment configurer votre Skype pour infrastructure Business Server 2019 pour travailler avec System Center Operations Manager.
  
Dans l’idéal, vous le feriez jamais rencontrez des problèmes avec Skype pour Business Server 2019. Toutefois, Skype pour Business Server peut être affectée par des facteurs externes — par exemple, réseau tombe en panne et défaillances matérielles. À l’aide de Skype Business Server 2019 Packs d’administration, vous pouvez identifier et résoudre les problèmes potentiels de manière proactive. De cette façon, le Skype pour les Packs d’administration Business Server 2019 étendre les fonctionnalités de System Center Operations Manager.
  
Ces informations a été rédigé en fonction de la version 9319.0 du module de surveillance pour Skype pour le logiciel de communication Business Server 2019.
  
## <a name="configuration-overview"></a>Vue d’ensemble de la configuration

 Pour configurer votre Skype pour infrastructure Business Server 2019 pour travailler avec System Center Operations Manager, vous devez effectuer trois opérations :
  
Identifier et [Configure the Primary Management Server](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md). Pour ce faire, vous devez installer System Center Operations Manager 2012 SP1 ou R2. 
  
 Identifier et [configurer le Skype pour les ordinateurs Business Server qui seront surveillés](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md). Pour analyser un Skype pour ordinateur Business Server à l’aide de System Center Operations Manager, vous devez installer les fichiers de l’agent System Center Operations Manager et configurer chaque serveur d’agir en tant que proxy. 
  
 Identifier et [installer et configurer des nœuds observateurs](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md). Nœuds observateurs sont des ordinateurs qui exécutent régulièrement Skype pour les transactions synthétiques Business Server — applets de commande Windows PowerShell vérifier cette clé Skype pour les composants Business Server, tels que la possibilité de se connecter au système ou de la capacité d’échanger instantanée messages, fonctionnent comme prévu. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Serveur d’administration System Center Operations Manager racine et prise en charge de l’Agent

Les Packs d’administration peuvent être utilisés avec System Center Operations Manager 2007 R2 (64 bits) (pris en charge uniquement à des fins de Migration) ou System Center Operations Manager 2012 SP1 &amp; R2 (64 bits). Le tableau suivant indique les configurations prises en charge pour les Packs d’administration pour Skype pour Business Server 2019 : 
  
|**Configuration**|**Prise en charge ?**|
|:-----|:-----|
|système d’exploitation Windows Server 2008 R2  <br/> Système d’exploitation Windows Server 2012 R2  <br/> |Oui. Ces deux éléments sur Skype pour serveur Business Server 2019 et nœuds Observateur de transaction synthétique.  <br/> |
|Serveurs en cluster  <br/> |Non pris en charge.  <br/> |
|Surveillance sans agent  <br/> |Non prise en charge.  <br/> |
|Environnement virtuel  <br/> |Oui.  <br/> |
|Rôles serveur liés au domaine  <br/> |Tous les Skype interne pour les rôles de serveur Business Server 2019 doit correspondre à un domaine.  <br/> |
|Rôles serveur autonomes  <br/> |Skype pour les serveurs de périphérie 2019 Business Server ne sont pas nécessaires pour être joint au domaine.  <br/> |
|Limitations de la topologie  <br/> |Tous les rôles serveur d’un déploiement doivent être surveillés à partir du même groupe d’administration Operations Manager.  <br/> |
|Nœud observateur de transactions synthétiques  <br/> |La surveillance de la disponibilité des scénarios avec un nœud observateur de transactions synthétiques est prise en charge (configuration supplémentaire nécessaire). Les nœuds observateurs n’ont pas besoin d’être associés à un domaine.  <br/> |
   
Le tableau ci-dessous détaille la capacité et la configuration de système d’exploitation requises pour un nœud observateur de transactions synthétiques :
  
|**Composant matériel**|**Spécification minimale**|
|:-----|:-----|
|Processeur  <br/> |L’un des éléments suivants :  <br/> Processeur 64 bits, quadruple cœur 2,33 GHz ou supérieur  <br/> Processeur 64 bits à deux voies, double cœur, 2,33 GHz ou supérieur  <br/> |
|Mémoire  <br/> |8 Go  <br/> |
|Système d’exploitation  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Réseau  <br/> |1 carte réseau 1 Gbits/s  <br/> |
   
## <a name="prerequisites"></a>Conditions requises

Pour exécuter un nœud observateur de transaction synthétique, vous devez d’abord installer les éléments suivants :
  
- Agent de System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Skype pour Unified Communications Managed API (UCMA) et les fichiers d’installation Business Server principaux (OcsCore.msi) (versions doivent correspondre la Skype pour la version Business Server WatcherNode.msi)
    
## <a name="files-in-this-monitoring-pack"></a>Fichiers contenus dans ce pack de surveillance

Le Pack d’analyse pour Skype pour Business Server 2019 comprend les fichiers suivants :
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Nouveautés

Les fonctionnalités suivantes sont une nouveauté dans Skype pour les Packs d’administration Business Server 2019.
  
- **Découverte automatique pour la connexion de clients** Les applications clientes que vous ouvrez une session dans Skype pour Business Server 2019 souvent automatiquement détecter le serveur pour vous connecter à. Les transactions synthétiques prennent maintenant en charge la vérification de la configuration appropriée de la découverte automatique.
    
- **Transactions synthétiques personnalisé exécutée intervalles** Pour simplifier le processus de nœuds Observateur de paramétrage, les transactions synthétiques peuvent partager des comptes d’utilisateurs. Cela ralentit la fréquence d’exécution des tests dans la mesure où les tests sont sérialisés pour éviter les conflits. Par défaut, les transactions synthétiques sont exécutées toutes les 15 minutes pour que tous les tests aient le temps de s’exécuter. Les administrateurs qui choisissent d’utiliser plus d’utilisateurs ou moins de tests par utilisateur peuvent désormais réduire également l’intervalle d’exécution.
    
- **Transaction synthétique de Services d’interopérabilité vidéo** Les clients qui migrent vers Skype pour Business Server 2019 à partir d’autres solutions de fournisseurs souvent volonté de continuer à utiliser les périphériques de téléconférence vidéo (VTCs) à partir de ces autres fournisseurs. Serveur d’interopérabilité vidéo est un nouveau Skype pour le rôle de serveur Business Server 2019 qui permet aux clients de continuer à utiliser Cisco VTCs dans leurs salles de conférence en se connectant à Cisco CUCM via une jonction SIP vidéo. Cette fonctionnalité ajoute également une transaction synthétique afin de vérifier que le serveur d’interopérabilité vidéo (VIS) peut gérer les connexions entrantes sur une jonction SIP vidéo.
    
- **Transaction synthétique de conférence de partage d’applications** La validation de scénario de bout en bout des conférences de partage d’applications est désormais prise en charge.
    
## <a name="monitoring-scenarios"></a>Scénarios de surveillance

Le Skype pour le Pack d’administration Business Server 2019 s’appuie sur une variété de fonctionnalités pour vous aider à détecter et diagnostiquer les problèmes. Ces fonctionnalités fournissent l’intégrité d’un Skype pour environnement Business Server 2019 de visibilité en temps réel.
  
|**Scénario de surveillance**|**Description**|
|:-----|:-----|
|Transactions synthétiques  <br/> | Applets de commande Windows PowerShell pour tester et garantir une haute disponibilité des scénarios tels que la connexion de présence, messagerie instantanée et de conférence pour les utilisateurs. <br/> Les transactions synthétiques peuvent être exécutées à partir de n’importe quel emplacement géographique dans l’entreprise, en dehors de l’entreprise et dans les succursales.  <br/> Lorsqu’une transaction synthétique échoue, des journaux HTML sont créés pour vous aider à déterminer la nature exacte de l’échec. Cela inclut des informations sur l’action qui a échoué, la latence de chaque action, la ligne de commande à partir de laquelle a été exécuté le test ainsi que l’erreur spécifique rencontrée.  <br/> |
|Alertes de fiabilité des appels  <br/> |Des détails des appels (CDR) écrits par Skype pour les serveurs de 2019 Business Server reflètent si les utilisateurs sont en mesure de se connecter à un appel ou pourquoi un appel est terminé. Les alertes de fiabilité des appels analysent la base de données des enregistrements des détails des appels afin de générer des alertes qui s’affichent lorsque de nombreux utilisateurs rencontrent des problèmes de connectivité liés à des appels d’égal à égal ou à des fonctionnalités de conférence de base.  <br/> Les scénarios incluent notamment les appels audio, les messages instantanés d’égal à égal et d’autres fonctionnalités de conférence.  <br/> |
|Alertes de qualité des médias  <br/> |Requêtes de base de données examiner les rapports de qualité de l’expérience (QoE) publiés par Skype pour les clients Business Server 2019 à la fin de chaque appel. Ces requêtes génèrent des alertes qui avertissent que les utilisateurs des scénarios signalés risquent d’être confrontés à une dégradation de la qualité des médias lors des appels et des conférences. Les données sont établies à partir de mesures clés, telles que la latence et la perte de paquets, qui s’avèrent décisives pour le niveau de qualité de l’expérience utilisateur.  <br/> |
|Alertes d’intégrité des composants  <br/> |Les composants serveur déclenchent des alertes via les journaux des événements et les compteurs de performances. Ces alertes signalent les conditions d’échec qui peuvent avoir un impact sérieux sur un ou plusieurs scénarios utilisateur. Elles peuvent également indiquer diverses autres conditions d’échec, parmi lesquelles l’arrêt de services, des taux d’échec élevés ou des problèmes de connectivité.  <br/> |
|Analyse d’intégrité de dépendance  <br/> |Skype pour Business Server peut échouer pour différentes raisons externes. Le pack d’administration analyse et collecte les données relatives à certaines dépendances externes critiques, qui peuvent révéler des problèmes majeurs. Ces dépendances incluent la disponibilité d’Internet Information Services (IIS) et de l’UC des serveurs utilisés pour Skype pour Business Server.  <br/> |
   
### <a name="alert-prioritization"></a>Priorisation des alertes

Les alertes sont classées selon les catégories suivantes : 
  
 **Des alertes de haute priorité :** Ces alertes indiquent les conditions qui provoquent des interruptions de service pour les grands groupes d’utilisateurs et d’intervention immédiate. Pannes détectés par les transactions synthétiques et des services en mode hors connexion (tels que Skype pour les services de conférence Audio/vidéo Business Server) associées à des alertes de haute priorité. En revanche, une défaillance d’un composant sur un ordinateur unique n’est pas une alerte de priorité élevée. Skype pour Business Server 2019 a des fonctionnalités de haute disponibilité intégrées pour ces situations — par exemple, plusieurs serveurs frontaux derrière équilibreurs de charge.
  
 **Des alertes de priorité moyenne :** Ces alertes indiquent les conditions qui affectent un sous-ensemble d’utilisateurs ou indiquent des problèmes dans la qualité des appels — par exemple, les échecs de composant, latence dans l’établissement d’un appel ou qualité audio dans les appels. Les alertes dans cette catégorie sont dynamique (autrement dit, la nature des modifications de l’alerte basé sur l’état de la connexion réseau.) Par exemple, si appel établissement fois indiquent la latence mais puis revenir à un seuil normal, cette alerte priorité moyenne serait résolu automatique dans System Center Operations Manager et administrateurs n’est pas nécessaire de prendre des mesures. Alertes qui ne peuvent pas être résolues automatique sont généralement traités par les administrateurs sur le même jour ouvré.
  
 **Autres alertes :** ces alertes concernent des composants susceptibles d’affecter un ou plusieurs utilisateurs. Par exemple, une alerte type peut signaler que le service de carnet d’adresses n’a pas pu analyser l’entrée AD DS ( Active Directory® Domain Services) de l’utilisateur« testuser@contoso.com ». Les administrateurs peuvent corriger ces alertes lorsqu’ils ont le temps.
  
### <a name="synthetic-transactions"></a>Transactions synthétiques

Skype pour les Packs d’administration Business Server 2019 offrent une couverture accrue des alertes par le biais de transactions synthétiques. Les transactions synthétiques sont intégrées dans le pack d’administration Operations Manager pour tester les scénarios impliquant des utilisateurs de bout en bout des applets de commande Windows PowerShell. Lorsque vous désignez un serveur pour exécuter des transactions synthétiques, ces applets de commande sont déclenchées régulièrement par le pack d’administration. Échecs résultant d’une transaction synthétique génèrent une alerte d’état. Voici les transactions synthétiques pris en charge pour Skype pour Business Server 2019 :
  
**Transactions synthétiques prises en charge pour l’inscription, la présence et les contacts**

||||
|:-----|:-----|:-----|
|1  <br/> |Inscription (connexion de l’utilisateur)  <br/> |Lync Server 2010 disponibles et au-delà  <br/> |
|2  <br/> |Service de carnet d’adresses (téléchargement de fichier)  <br/> |Lync Server 2010 disponibles et au-delà  <br/> |
|3  <br/> |Recherche web du carnet d’adresses  <br/> |Lync Server 2010 disponibles et au-delà  <br/> |
|4  <br/> |Présence  <br/> |Lync Server 2010 disponibles et au-delà  <br/> |
|5  <br/> |Magasin de contacts unifié  <br/> |Lync Server 2013 disponibles et au-delà  <br/> |
   
**Transactions synthétiques prises en charge pour les services d’égal à égal**

||||
|:-----|:-----|:-----|
|6  <br/> |Messagerie instantanée d’égal à égal  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|7  <br/> |Appels audio/vidéo d’égal à égal  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|8  <br/> |Messagerie instantanée d’égal à égal MCX (mobile)  <br/> |Disponible dans la version de septembre 2011 de Lync Server 2010 pour Skype pour Business 2019  <br/> |
 
> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
**Transactions synthétiques prises en charge pour les conférences et la conversation permanente**

||||
|:-----|:-----|:-----|
|9  <br/> |Conférence audio-vidéo  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
| 10  <br/> |Conférence de données  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|11  <br/> |Conférence par messages instantanés  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|12  <br/> | Conversation permanente <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|13  <br/> |Lanceur de participation (réunions planifiées)  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|14  <br/> |Conférence rendez-vous  <br/> |Disponible dans Skype pour Business Server 2015 et au-delà <br/> |
|15  <br/> |Conférence de partage d’applications  <br/> |Disponible dans Skype pour Business Server 2015 et au-delà <br/> |
|16  <br/> |Conférence UCWA (participation à une réunion web)  <br/> |Disponible dans Skype pour Business Server 2015 et au-delà <br/> |
   
**Transactions synthétiques prises en charge pour les dépendances de réseau et de partenaires**

||||
|:-----|:-----|:-----|
|17  <br/> |Connectivité Edge A/V  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|18  <br/> |Connectivité de messagerie unifiée Exchange de la connectivité Edge A/V (messagerie vocale)  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|19  <br/> |Appels d’égal à égal PSTN  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|20  <br/> |Messagerie instantanée XMPP (fédération)  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|21  <br/> |Serveur VIS (Video Interop Server)  <br/> |Disponible dans Skype pour Business Server 2015 et au-delà  <br/> |
   
## <a name="how-health-rolls-up"></a>Comment se présente l’intégrité

Le tableau suivant indique les États d’intégrité des objets le Skype pour Business Server pack d’analyse.
  
|**Objet du pack d’administration**|**Description**|
|:-----|:-----|
|Skype pour le déploiement de serveur d’entreprise  <br/> |Représente le déploiement de Skype pour Business Server 2019 dans l’organisation.  <br/> |
|Skype pour Site Business Server  <br/> |Représente différents emplacements géographiques où les services sont déployés.  <br/> |
|Skype pour le Pool de serveurs d’entreprise  <br/> |Pool (au sein d’un site) qui fournit des services de communications, tels que la messagerie instantanée et les conférences, aux utilisateurs. Applicable aux pools frontaux, pools de serveurs Edge et pools directeurs, même si un pool donné ne comporte qu’un seul ordinateur.  <br/> |
|Skype pour le rôle de serveur d’entreprise  <br/> |Rôle de serveur qui héberge Skype pour le Service Business Server.  <br/> |
|Skype pour le Service Business Server  <br/> |Représente une fonctionnalité déployée sur un ordinateur spécifique (par exemple, service utilisateur sur fp01.contoso.com).  <br/> |
|Skype pour le composant de serveur d’entreprise  <br/> |Composant du service (par exemple, le composant de téléchargement de carnet d’adresses est un composant du Service Web).  <br/> |
|Skype pour Business Server Pool Observateur  <br/> |Instance de transactions synthétiques s’exécutant sur un pool.  <br/> |
|Skype pour Business Server du serveur d’inscriptions Observateur  <br/> |Instance de transactions synthétiques s’exécutant sur un pool de serveurs d’inscriptions.  <br/> |
|Skype pour Observateur de Pool des Services Business Server utilisateur  <br/> |Instance de transactions synthétiques s’exécutant sur un pool de services utilisateurs.  <br/> |
|Skype pour Business Server voix Pool Observateur  <br/> |Instance de transactions synthétiques s’exécutant sur un pool Voix.  <br/> |
|Skype pour le Port du serveur Business Observateur  <br/> |Instance de vérifications de port s’exécutant sur un pool.  <br/> |
|Observateur d’URL simple  <br/> |Effectue une analyse HTTPS des URL simples configurées dans le cadre d’un déploiement.  <br/> |
   
![Déploiement SCOM](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un Skype pour le pool de serveurs d’entreprise peut contenir plusieurs Skype individuel pour les systèmes Business Server (avec plusieurs de Skype pour Business Server role, Skype pour le service Business Server et Skype pour le composant serveur d’entreprise). Par conséquent, l’échec d’un serveur spécifique ou d’un composant est moins importante de l’état général de la Skype pour le pool de serveurs d’entreprise, car les autres serveurs dans le même pool peuvent fournir le service d’application au client. L’état de santé est reportés sur un niveau de pourcentage pour le Skype pour le pool de serveurs d’entreprise. 
  
Le Skype pour Business Server Pool Observateur effectue les transactions synthétiques par rapport à un Skype pour le pool de serveurs d’entreprise. Les échecs consécutifs d’une ou de plusieurs transactions synthétiques (un processus appelé intervalle d’interrogation consécutif) cumuleront l’état d’intégrité critique au niveau du pool (le pire de toute transaction synthétique), comme illustré dans le diagramme suivant. 
  
![Interrogation consécutive du déploiement SCOM](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Meilleure pratique : création d’un pack d’administration pour les personnalisations

Par défaut, Operations Manager enregistre toutes les personnalisations, telles que les remplacements dans le pack d’administration par défaut. Il est recommandé de créer un pack d’administration distinct pour chaque pack d’administration scellé que vous souhaitez personnaliser. 
  
Lorsque vous créez un pack d’administration pour le stockage des paramètres personnalisés pour un pack d’administration sealed, nous vous recommandons d’affectation de noms le nouveau pack d’administration de façon appropriée, tel que « Skype pour des personnalisations Business Server 2019 ».
  
La création d’un nouveau pack d’administration pour le stockage des personnalisations de chaque pack d’administration scellé facilite l’exportation des personnalisations d’un environnement de test vers un environnement de production. Elle facilite également la suppression d’un pack d’administration, car vous devez supprimer toutes les dépendances avant de pouvoir supprimer un pack d’administration. Si les personnalisations de tous les packs d’administration sont enregistrées dans le pack d’administration par défaut et que vous devez supprimer un seul pack d’administration, vous devez d’abord supprimer le pack d’administration par défaut, ce qui supprimera également les personnalisations des autres packs d’administration. 
  
## <a name="links"></a>Liens

Les liens suivants vous permettent d’accéder à des informations sur les tâches courantes associées aux packs de surveillance System Center 2012 :
  
- [Cycle de vie du pack d’administration](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Comment faire pour importer un Pack d’administration Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Comment faire pour remplacer une règle ou un moniteur ](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Comment faire pour créer une série de tests en tant que compte dans Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Gestion des comptes et des profils d’identification](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Comment faire pour exporter un Pack d’administration Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Comment faire pour supprimer un Pack d’administration Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Les liens suivants vous permettent d’accéder à des informations sur les tâches courantes associées aux packs de surveillance System Center 2007 :
  
- [Administration du cycle de vie des packs d’administration](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Procédure d’importation d’un pack d’administration dans Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Procédure d’analyse à l’aide de remplacements](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Procédure de création d’un compte d’identification dans Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Procédure de modification d’un profil d’identification existant](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Procédure d’exportation des personnalisations de packs d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Procédure de suppression d’un pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Pour toute question relative à Operations Manager et aux packs de surveillance, consultez le [forum de la communauté System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Une ressource utile est le blog de [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) , qui contient les publications « Par exemple » pour les packs de surveillance spécifiques.
  
Pour plus d’informations sur Operations Manager, reportez-vous aux blogs suivants : 
  
- [Blog de l’équipe Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman’s OpsMgr Blog](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Thoughts on OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Raphael Burri](https://rburri.wordpress.com/)
    
- [BWren’s Management Space](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toutes les informations et le contenu figurant sur des sites non-Microsoft sont fournis par le propriétaire ou les utilisateurs de ces sites web. Microsoft exclut toute garantie expresse, implicite ou légale concernant les informations qu’ils contiennent. 
  
## <a name="see-also"></a>Voir aussi

[Skype Business Server 2019 des outils de gestion](../management-tools-2019.md)
