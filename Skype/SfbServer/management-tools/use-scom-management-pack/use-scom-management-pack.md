---
title: Gérer Skype entreprise Server 2015 à l’aide d’un pack d’administration SCOM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Résumé : Découvrez comment configurer votre infrastructure Skype entreprise Server 2015 pour qu’elle fonctionne avec System Center Operations Manager.'
ms.openlocfilehash: 06297ba7e0ab70e7046fc2f3db189275cc90f9d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005939"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Gérer Skype entreprise Server 2015 à l’aide d’un pack d’administration SCOM
 
**Résumé :** Découvrez comment configurer votre infrastructure Skype entreprise Server 2015 pour qu’elle fonctionne avec System Center Operations Manager.
  
Dans un monde idéal, vous ne rencontrerez jamais de problèmes avec Skype entreprise Server 2015. Toutefois, Skype entreprise Server peut être affecté par des facteurs externes (par exemple, des pannes de réseau et des défaillances matérielles). À l’aide des packs d’administration de Skype entreprise Server 2015, vous pouvez identifier et résoudre les problèmes potentiels de manière proactive. De cette façon, les packs d’administration de Skype entreprise Server 2015 étendent les fonctionnalités de System Center Operations Manager.
  
Ces informations ont été rédigées en fonction de la version 9319,0 du pack d’analyse pour le logiciel de communication de Skype entreprise Server 2015.
  
## <a name="configuration-overview"></a>Vue d’ensemble de la configuration

 Pour configurer votre infrastructure Skype entreprise Server 2015 de sorte qu’elle fonctionne avec System Center Operations Manager, vous devez effectuer les trois opérations suivantes :
  
Identifiez et [configurez le serveur d’administration principal](configure-the-primary.md). Pour ce faire, vous devez installer System Center Operations Manager 2012 SP1 ou R2. 
  
 Identifiez et [configurez les ordinateurs Skype entreprise Server qui seront surveillés](configure-computers-to-monitor.md). Pour surveiller un ordinateur Skype entreprise Server à l’aide de System Center Operations Manager, vous devez installer les fichiers de l’agent System Center Operations Manager et configurer chaque serveur comme proxy. 
  
 Identifier et [installer et configurer les nœuds observateur](watcher-nodes.md). Les nœuds observateurs sont des ordinateurs qui exécutent régulièrement des transactions synthétiques Skype entreprise Server : les applets de commande Windows PowerShell qui vérifient les composants clés de Skype entreprise Server, comme la possibilité de se connecter au système ou la possibilité d’échanger des éléments instantanés. les messages fonctionnent comme prévu. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Prise en charge du serveur d’administration racine de System Center Operations Manager et de l’agent

Les packs d’administration peuvent être utilisés avec System Center Operations Manager 2007 R2 (64 bits) (pris en charge uniquement à des fins de migration) ou &amp; System Center Operations Manager 2012 SP1 r2 (64 bits) ou System Center Operations Manager 2016 (64 bits). Le tableau suivant indique les configurations prises en charge pour les packs d’administration de Skype entreprise Server 2015 : 
  
|Configuration|Pris en charge ?|
|:-----|:-----|
|Système d’exploitation Windows Server 2008 R2  <br/> Système d’exploitation Windows Server 2012 R2  <br/> |Oui. Sur le serveur Skype entreprise Server 2015 et sur les nœuds observateur de transactions synthétiques.  <br/> |
|Serveurs en cluster  <br/> |Non prise en charge.  <br/> |
|Analyse sans agent  <br/> |Non prise en charge.  <br/> |
|Environnement virtuel  <br/> |Oui.  <br/> |
|Rôles de serveur associés à un domaine  <br/> |Tous les rôles serveur internes de Skype entreprise Server 2015 doivent être liés à un domaine.  <br/> |
|Rôles serveur autonomes  <br/> |Les serveurs Edge Skype entreprise Server 2015 ne doivent pas obligatoirement être liés à un domaine.  <br/> |
|Limitations de la topologie  <br/> |Tous les rôles serveur d’un déploiement doivent être surveillés à partir du même groupe d’administration Operations Manager.  <br/> |
|Nœud observateur de transactions synthétiques  <br/> |Surveillance de la disponibilité des scénarios avec un nœud observateur de transactions synthétiques est pris en charge (configuration supplémentaire requise). Les nœuds observateurs ne doivent pas obligatoirement être liés à un domaine.  <br/> |
   
Le tableau suivant indique la configuration requise pour le système d’exploitation et la capacité pour un nœud observateur de transactions synthétiques :
  
|Composant matériel|Spécification minimale|
|:-----|:-----|
|UC  <br/> |Un des processeurs suivants :  <br/> processeur 64 bits, quadruple cœur, 2,33 GHz ou supérieur  <br/> processeur double cœur 64 bits, 2 cœurs, 2,33 GHz ou supérieur  <br/> |
|Mémoire  <br/> |8 Go  <br/> |
|Système d’exploitation  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Réseau  <br/> |1 carte réseau à 1 Gbits/s  <br/> |
   
## <a name="prerequisites"></a>Conditions préalables

Pour exécuter un nœud observateur de transactions synthétiques, vous devez d’abord installer les éléments suivants :
  
- Agent System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Fichiers d’installation principaux de Skype entreprise Server (OcsCore. msi) et Unified Communications Managed API (UCMA) (les versions doivent correspondre à la version de Skype entreprise Server WatcherNode. msi)
    
## <a name="files-in-this-monitoring-pack"></a>Fichiers dans ce pack de surveillance

Le pack d’analyse pour Skype entreprise Server 2015 comprend les fichiers suivants :
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode. msi
    
## <a name="whats-new"></a>Nouveautés

Les fonctionnalités suivantes sont nouvelles dans les packs d’administration de Skype entreprise Server 2015.

- **Modifications apportées [à la mise à jour 2019 sept](https://www.microsoft.com/en-in/download/details.aspx?id=47364) ** Certaines alertes ont eu des caractères spéciaux supprimés. Dans certains cas, des caractères spéciaux interfèrent avec la fonctionnalité de notification de canal de commande SCOM.

- **Découverte automatique pour la connexion du client** Les applications clientes qui se connectent à Skype entreprise Server 2015 découvrent souvent automatiquement le serveur auquel se connecter. Les transactions synthétiques prennent désormais en charge la vérification de la configuration correcte de la découverte automatique.
    
- **Intervalles d’exécution de transaction synthétique personnalisés** Pour simplifier le processus de configuration des nœuds observateur, les transactions synthétiques peuvent partager des comptes d’utilisateur. Cela ralentit la fréquence à laquelle les tests sont exécutés lorsque les tests sont sérialisés afin d’éviter les conflits. Par défaut, les transactions synthétiques sont exécutées toutes les 15 minutes pour s’assurer que tous les tests ont le temps de s’exécuter. Les administrateurs qui choisissent d’utiliser plus d’utilisateurs ou moins de tests par utilisateur peuvent désormais réduire l’intervalle d’exécution.
    
- **Transaction synthétique des services d’interopérabilité vidéo** Les clients qui effectuent une migration vers Skype entreprise Server 2015 à partir d’autres solutions de fournisseur souhaitent souvent continuer à utiliser les appareils de visioconférence (VTC) de ces autres fournisseurs. Le serveur d’interopérabilité vidéo est un nouveau rôle de serveur Skype entreprise Server 2015 qui permet aux clients de continuer à utiliser Cisco VTC dans leurs salles de conférence en se connectant à Cisco CUCM via une jonction SIP vidéo. Cette fonctionnalité ajoute également une transaction synthétique pour vous aider à vérifier que le serveur d’interopérabilité vidéo fonctionne et peut gérer les connexions entrantes sur une jonction SIP vidéo.
    
- **Transaction synthétique de conférence de partage d’application** La validation des scénarios de bout en bout pour les conférences de partage d’applications est désormais prise en charge.
    
## <a name="monitoring-scenarios"></a>Scénarios de surveillance

Le pack d’administration de Skype entreprise Server 2015 tire parti d’un grand nombre de fonctionnalités pour vous aider à détecter et à diagnostiquer les problèmes. Ces fonctionnalités permettent une visibilité en temps réel de l’intégrité d’un environnement Skype entreprise Server 2015.
  
|Scénario de surveillance|Description|
|:-----|:-----|
|Transactions synthétiques  <br/> | Applets de commande Windows PowerShell pour tester et garantir une haute disponibilité des scénarios tels que la connexion, la présence, la messagerie instantanée et la Conférence pour les utilisateurs. <br/> Les transactions synthétiques peuvent être exécutées à partir de n’importe quel lieu géographique, y compris à l’intérieur de l’entreprise, en dehors de l’entreprise et des succursales.  <br/> Lorsqu’une transaction synthétique échoue, des journaux HTML sont créés pour vous aider à déterminer la nature exacte de l’échec. Cela inclut la compréhension de l’action qui a échoué, de la latence de chaque action, de la ligne de commande utilisée pour exécuter le test et de l’erreur spécifique qui s’est produite.  <br/> |
|Alertes de fiabilité des appels  <br/> |Les enregistrements des détails des appels écrits par les serveurs Skype entreprise Server 2015 indiquent si les utilisateurs peuvent se connecter à un appel ou la raison pour laquelle un appel est terminé. Les alertes de fiabilité des appels interrogent la base de données CDR pour générer des alertes indiquant quand un grand nombre d’utilisateurs rencontraient des problèmes de connectivité pour les appels P2P ou les fonctionnalités de conférence de base.  <br/> La couverture de scénario inclut des appels audio, la messagerie instantanée P2P et d’autres fonctionnalités de conférence.  <br/> |
|Alertes de qualité des médias  <br/> |Requêtes de base de données qui examinent les rapports de qualité de l’expérience publiés par les clients Skype entreprise Server 2015 à la fin de chaque appel. Ces requêtes produisent des alertes qui identifient les scénarios dans lesquels les utilisateurs ont le plus de chances de bénéficier de la qualité des médias compromis pendant les appels et les conférences. Les données sont basées sur des mesures clés, telles que la latence et la perte de paquets, qui contribuent directement à la qualité de l’expérience utilisateur.  <br/> |
|Alertes d’intégrité des composants  <br/> |Les composants serveur individuels déclenchent des alertes via les journaux des événements et les compteurs de performance pour indiquer les conditions d’échec pouvant affecter de manière significative les scénarios utilisateur. Ces alertes indiquent plusieurs conditions, telles que les services qui ne sont pas exécutés, les taux d’échec élevés, la latence de messages élevée ou les problèmes de connectivité.  <br/> |
|Surveillance de l’intégrité des dépendances  <br/> |Skype entreprise Server peut échouer pour diverses raisons externes. Le pack d’administration analyse et collecte des données pour les dépendances externes critiques pouvant indiquer des problèmes sérieux. Ces dépendances incluent la disponibilité des services IIS (Internet Information Services) et l’unité centrale des serveurs utilisés pour Skype entreprise Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Hiérarchisation des alertes

Les alertes sont classées selon les catégories suivantes : 
  
 **Alertes à priorité élevée :** Ces alertes indiquent les conditions qui provoquent des pannes de service pour les grands groupes d’utilisateurs et nécessitent une action immédiate. Les pannes détectées par les transactions synthétiques et les services hors ligne (par exemple, Skype entreprise Server audioconférence/conférence vidéo) sont considérées comme des alertes à priorité élevée. En revanche, une défaillance d’un composant sur un seul ordinateur n’est pas une alerte à priorité élevée. Skype entreprise Server 2015 possède des fonctionnalités de haute disponibilité intégrées pour ces situations, par exemple, plusieurs serveurs frontaux derrière des programmes d’équilibrage de charge.
  
 **Alertes de priorité moyenne :** Ces alertes indiquent les conditions qui affectent un sous-ensemble d’utilisateurs ou indiquent des problèmes de qualité des appels (par exemple, des défaillances de composants, la latence dans un établissement d’appel ou une qualité audio inférieure dans les appels). Les alertes de cette catégorie sont avec état (autrement dit, la nature des modifications d’alerte en fonction de l’état de la connexion réseau). Par exemple, si les heures d’établissement d’appel indiquent une latence, mais renvoient ensuite à un seuil normal, cette alerte de priorité moyenne est résolue automatiquement dans System Center Operations Manager et les administrateurs n’ont pas besoin de prendre des mesures. Les alertes qui ne peuvent pas être résolues automatiquement sont généralement adressées par les administrateurs à la même journée de travail.
  
 **Autres alertes :** Ces alertes sont générées à partir de composants susceptibles d’affecter un utilisateur spécifique ou un sous-ensemble d’utilisateurs. Par exemple, une alerte type est que le service de carnet d’adresses n’a pas pu analyser l’entrée AD DS (Active Directory® Domain Services) pour user : testuser@contoso.com. Les administrateurs peuvent résoudre ces alertes chaque fois qu’elles disposent d’un temps disponible.
  
### <a name="synthetic-transactions"></a>Transactions synthétiques

Les packs d’administration de Skype entreprise Server 2015 fournissent une couverture accrue des alertes par le biais de transactions synthétiques. Les transactions synthétiques sont des applets de commande Windows PowerShell intégrées dans le pack d’administration d’Operations Manager pour tester des scénarios utilisateur de bout en bout. Lorsque vous désignez un serveur pour exécuter des transactions synthétiques, ces applets de commande sont déclenchées régulièrement par le pack d’administration. Les échecs résultant d’une transaction synthétique génèrent une alerte avec état. Voici les transactions synthétiques prises en charge pour Skype entreprise Server 2015 :
  


|Transactions synthétiques prises en charge pour l’inscription, la présence et les contacts|||
|:-----|:-----|:-----|
|1   <br/> |Inscription (ouverture de session utilisateur)  <br/> |Lync Server 2010 disponible et versions ultérieures  <br/> |
|2   <br/> |Service de carnet d’adresses (téléchargement de fichier)  <br/> |Lync Server 2010 disponible et versions ultérieures  <br/> |
|3   <br/> |Requête web du carnet d’adresses  <br/> |Lync Server 2010 disponible et versions ultérieures  <br/> |
|4   <br/> |Présence  <br/> |Lync Server 2010 disponible et versions ultérieures  <br/> |
|5   <br/> |Magasin de contacts unifié  <br/> |Lync Server 2013 disponible et versions ultérieures  <br/> |
||||   

|Transactions synthétiques prises en charge pour les services P2P|||
|:-----|:-----|:-----|
|6   <br/> |Messagerie instantanée P2P  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|7   <br/> |Vidéo audio P2P  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|8   <br/> |Message instantané d’égal à égal MCX (mobile)  <br/> |Disponible dans la version 2011 de Lync Server 2010 vers Skype entreprise 2015  <br/> |
 
> [!NOTE]
> La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.


|Transactions synthétiques prises en charge pour les conférences et la conversation permanente|||
|:-----|:-----|:-----|
|9   <br/> |Audioconférence  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|10   <br/> |Conférence de données  <br/> |Disponible dans Lync Server 2013 et versions ultérieures  <br/> |
|a4  <br/> |Conférence par messagerie instantanée  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|12  <br/> | Conversation permanente <br/> |Disponible dans Lync Server 2013 et versions ultérieures  <br/> |
|kg  <br/> |Lanceur de participation (réunions planifiées)  <br/> |Disponible dans Lync Server 2013 et versions ultérieures  <br/> |
|14   <br/> |Conférence rendez-vous  <br/> |Nouveauté de Skype entreprise Server 2015  <br/> |
|15   <br/> |Conférence de partage d’application  <br/> |Nouveauté de Skype entreprise Server 2015  <br/> |
|16   <br/> |Conférence UCWA (participation à une réunion Web)  <br/> |Nouveauté de Skype entreprise Server 2015  <br/> |
||||

|Transactions synthétiques prises en charge pour les dépendances de réseau et de partenaire|||
|:-----|:-----|:-----|
|17   <br/> |Connectivité de serveur Edge AV  <br/> |Disponible dans Lync Server 2013 et versions ultérieures  <br/> |
|18   <br/> |Connectivité du serveur Edge AV-connectivité de messagerie unifiée Exchange  <br/> |Disponible dans Lync Server 2013 et versions ultérieures  <br/> |
|neuf  <br/> |Appel d’égal à égal PSTN  <br/> |Disponible dans Lync Server 2010 et versions ultérieures  <br/> |
|vingtaine  <br/> |Messagerie instantanée XMPP (Fédération)  <br/> |Disponible dans Lync Server 2013 et Skype entreprise 2015  <br/> |
|21  <br/> |Serveur d’interopérabilité vidéo  <br/> |Nouveauté de Skype entreprise Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Fonctionnement de l’intégrité

Le tableau suivant indique l’état d’intégrité des objets pour le pack d’analyse Skype entreprise Server.
  
|Objet de Pack d’administration|Description|
|:-----|:-----|
|Déploiement de Skype entreprise Server  <br/> |Représente le déploiement de Skype entreprise Server 2015 dans l’organisation.  <br/> |
|Site Skype entreprise Server  <br/> |Représente différents emplacements géographiques où les services sont déployés.  <br/> |
|Pool Skype entreprise Server  <br/> |Un pool (au sein d’un site) qui fournit des services de communication, tels que la messagerie instantanée et la Conférence, aux utilisateurs. Applicable aux pools frontaux, pools de serveurs Edge et pools directeurs, même s’il n’y a qu’un seul ordinateur dans un pool donné.  <br/> |
|Rôle de serveur Skype entreprise  <br/> |Rôle serveur qui héberge le service Skype entreprise Server.  <br/> |
|Service Skype entreprise Server  <br/> |Représente une fonctionnalité déployée sur un ordinateur spécifique (par exemple, le service utilisateur sur fp01.contoso.com).  <br/> |
|Composant Skype entreprise Server  <br/> |Un composant du service (par exemple, le composant de téléchargement du carnet d’adresses fait partie du service Web).  <br/> |
|Observateur de pool Skype entreprise Server  <br/> |Instance de transactions synthétiques exécutées sur un pool.  <br/> |
|Skype entreprise Server Registrar Watcher  <br/> |Instance de transactions synthétiques qui s’exécutent sur un pool de serveurs d’inscriptions.  <br/> |
|Observateur de pool de services d’utilisateurs Skype entreprise Server  <br/> |Instance de transactions synthétiques qui s’exécutent sur un pool de services d’utilisateurs.  <br/> |
|Observateur de pool de communications vocales de Skype entreprise Server  <br/> |Instance de transactions synthétiques qui s’exécutent sur un pool de communications vocales.  <br/> |
|Observateur de ports Skype entreprise Server  <br/> |Une instance des contrôles de port exécutés sur un pool.  <br/> |
|Observateur d’URL simple  <br/> |Effectue un sondage HTTPs des URL simples configurées dans un déploiement.  <br/> |
   
![Correctif SCOM](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un pool Skype entreprise Server peut contenir plusieurs systèmes Skype entreprise Server individuels (avec plusieurs rôles Skype entreprise Server, le service Skype entreprise Server et le composant Skype entreprise Server). Par conséquent, la défaillance d’un serveur ou d’un composant individuel est moins essentielle à l’intégrité globale du pool Skype entreprise Server, car les autres serveurs du même pool peuvent fournir le service d’application au client. L’intégrité est reportée sur un niveau de pourcentage vers le pool Skype entreprise Server. 
  
Le observateur de pool Skype entreprise Server effectue des transactions synthétiques par rapport à un pool Skype entreprise Server. Une ou plusieurs transactions synthétiques ayant échoué (processus connu sous le nom d’intervalle d’interrogation consécutif) cumulent l’état d’intégrité critique au niveau du pool (le pire de toute transaction synthétique), comme illustré dans le diagramme suivant. 
  
![Interrogation consécutive du correctif SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Meilleure pratique : créer un pack d’administration pour les personnalisations

Par défaut, Operations Manager enregistre toutes les personnalisations, telles que les substitutions dans le pack d’administration par défaut. Il est recommandé de créer un pack d’administration distinct pour chaque pack d’administration scellé que vous souhaitez personnaliser. 
  
Lorsque vous créez un pack d’administration pour le stockage des paramètres personnalisés pour un pack d’administration scellé, nous vous recommandons de nommer le nouveau pack d’administration de manière appropriée, par exemple « personnalisations de Skype entreprise Server 2015 ». 
  
La création d’un nouveau pack d’administration pour le stockage des personnalisations de chaque pack d’administration scellé facilite l’exportation des personnalisations d’un environnement de test vers un environnement de production. Cela permet également de supprimer plus facilement un pack d’administration, car vous devez supprimer toutes les dépendances avant de pouvoir supprimer un pack d’administration. Si des personnalisations de tous les packs d’administration sont enregistrées dans le pack d’administration par défaut et que vous devez supprimer un seul pack d’administration, vous devez d’abord supprimer le pack d’administration par défaut, ce qui entraîne également la suppression des personnalisations apportées aux autres packs d’administration. 
  
## <a name="links"></a>Liens

Les liens suivants vous permettent d’accéder à des informations sur les tâches courantes associées aux packs de surveillance System Center 2012 :
  
- [Cycle de vie du pack d’administration](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Procédure d’importation d’un pack d’administration dans Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Comment remplacer une règle ou un moniteur](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Procédure de création d’un compte exécuter en tant que dans Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Gestion des comptes et des profils d’exécution](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Procédure d’exportation d’un pack d’administration Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Procédure de suppression d’un pack d’administration Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
Les liens suivants vous permettent d’accéder à des informations sur les tâches courantes associées aux packs de surveillance System Center 2007 :
  
- [Administration du cycle de vie du pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Procédure d’importation d’un pack d’administration dans Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Procédure d’analyse à l’aide de remplacements](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Procédure de création d’un compte exécuter en tant que dans Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Procédure de modification d’un profil d’exécution existant](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Procédure d’exportation des personnalisations de packs d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Procédure de suppression d’un pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Pour plus d’informations sur Operations Manager and Monitoring packs, consultez le Forum de la [communauté System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Une ressource utile est le blog de [System Center Operations Manager non restreint](https://opsmgrunleashed.wordpress.com/) , qui contient des publications « par exemple » pour des packs de surveillance spécifiques.
  
Pour plus d’informations sur Operations Manager, consultez les blogs suivants : 
  
- [Blog de l’équipe Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog d’Operations Manager de kevin Holman’s](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Réflexions sur Operations Manager](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de blog Raphael Burri](https://rburri.wordpress.com/)
    
- [Espace de gestion de Bwren’s Management Space](https://blogs.technet.com/brianwren/default.aspx)
    
- [Gestionnaire d’opérations + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toutes les informations et le contenu sur les sites non-Microsoft sont fournis par le propriétaire ou les utilisateurs du site Web. Microsoft exclut toute garantie, expresse, implicite ou légale, en ce qui concerne les informations sur ce site Web. 
  
## <a name="see-also"></a>Voir aussi

[Outils de gestion de Skype entreprise Server 2015](../../management-tools/management-tools.md)
