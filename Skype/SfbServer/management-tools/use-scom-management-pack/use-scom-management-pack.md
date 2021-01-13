---
title: Gérer Skype Entreprise Server 2015 à l’aide du pack d’administration SCOM
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Résumé : Découvrez comment configurer votre infrastructure Skype Entreprise Server 2015 pour qu’elle fonctionne avec System Center Operations Manager.'
ms.openlocfilehash: cfb48338d4022c1de7c5944f66d72e58dd8b403d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814844"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Gérer Skype Entreprise Server 2015 à l’aide du pack d’administration SCOM
 
**Résumé :** Découvrez comment configurer votre infrastructure Skype Entreprise Server 2015 pour qu’elle fonctionne avec System Center Operations Manager.
  
Dans un monde idéal, vous ne rencontreriez jamais de problèmes avec Skype Entreprise Server 2015. Toutefois, Skype Entreprise Server peut être affecté par des facteurs externes, par exemple des pannes réseau et matérielles. À l’aide des packs d’administration Skype Entreprise Server 2015, vous pouvez identifier et résoudre les problèmes potentiels de manière proactive. De cette façon, les packs d’administration de Skype Entreprise Server 2015 étendent les fonctionnalités de System Center Operations Manager.
  
Ces informations ont été écrites sur la base de la version 9319.0 du logiciel de communication Du Pack de surveillance pour Skype Entreprise Server 2015.
  
## <a name="configuration-overview"></a>Vue d’ensemble de la configuration

 Pour configurer votre infrastructure Skype Entreprise Server 2015 afin qu’elle fonctionne avec System Center Operations Manager, vous devez :
  
Identifiez [et configurez le serveur de gestion principal.](configure-the-primary.md) Pour ce faire, vous devez installer System Center Operations Manager 2012 SP1 ou R2. 
  
 Identifiez [et configurez les ordinateurs Skype Entreprise Server qui seront surveillés.](configure-computers-to-monitor.md) Pour surveiller un ordinateur Skype Entreprise Server à l’aide de System Center Operations Manager, vous devez installer les fichiers de l’agent System Center Operations Manager et configurer chaque serveur pour qu’il agisse en tant que proxy. 
  
 Identifiez [et installez et configurez les nodes de l’observeur.](watcher-nodes.md) Les numéros d’observation sont des ordinateurs qui exécutent régulièrement des transactions synthétiques Skype Entreprise Server , c’est-à-dire des applets de Windows PowerShell qui vérifient que les composants clés de Skype Entreprise Server, tels que la possibilité de se connecter au système ou d’échanger des messages instantanés, fonctionnent comme prévu. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Prise en charge du serveur d’administration racine et de l’agent System Center Operations Manager

Les packs d’administration peuvent être utilisés avec System Center Operations Manager 2007 R2 (64 bits) (pris en charge à des fins de migration uniquement) ou System Center Operations Manager 2012 SP1 &amp; R2 (64 bits) ou System Center Operations Manager 2016 (64 bits). Le tableau suivant indique les configurations prise en charge pour les packs d’administration pour Skype Entreprise Server 2015 : 
  
|Configuration|Pris en charge ?|
|:-----|:-----|
|Système d’exploitation Windows Server 2008 R2  <br/> Système d’exploitation Windows Server 2012 R2  <br/> |Oui. À la fois sur le serveur Skype Entreprise Server 2015 et sur les serveurs de transaction synthétique.  <br/> |
|Serveurs en cluster  <br/> |Non prise en charge.  <br/> |
|Surveillance sans agent  <br/> |Non prise en charge.  <br/> |
|Environnement virtuel  <br/> |Oui.  <br/> |
|Rôles serveur joints au domaine  <br/> |Tous les rôles serveur Skype Entreprise Server 2015 internes doivent être joints au domaine.  <br/> |
|Rôles serveur autonomes  <br/> |Les serveurs Edge Skype Entreprise Server 2015 ne doivent pas nécessairement être joints à un domaine.  <br/> |
|Limitations de topologie  <br/> |Tous les rôles serveur dans un déploiement doivent être surveillés à partir du même groupe de gestion Operations Manager.  <br/> |
|Nœud d’observation des transactions synthétiques  <br/> |La surveillance de la disponibilité des scénarios avec un nœud d’analyse des transactions synthétiques est prise en charge (configuration supplémentaire requise). Les nodes de l’observeur ne doivent pas obligatoirement être joints au domaine.  <br/> |
   
Le tableau suivant indique la capacité et la exigences du système d’exploitation pour un nœud d’watcher de transaction synthétique :
  
|Composant matériel|Spécification minimale|
|:-----|:-----|
|UC  <br/> |Un des processeurs suivants :  <br/> Processeur 64 bits, quadruple cœur, 2,33 GHz ou supérieur  <br/> Processeur 64 bits 2 voies, bi cœur, 2,33 GHz ou supérieur  <br/> |
|Mémoire  <br/> |8 Go  <br/> |
|Système d’exploitation  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Réseau  <br/> |1 carte réseau à 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Conditions préalables

Pour exécuter un nœud d’observation de transaction synthétique, vous devez d’abord installer les opérations suivantes :
  
- System Center Operations Manager Agent 
    
-  Microsoft .NET Framework 4.5
    
- Fichiers d’installation principaux de Skype Entreprise Server (OcsCore.msi) et UCMA (Unified Communications Managed API) (les versions doivent correspondre à la version WatcherNode.msi Skype Entreprise Server)
    
## <a name="files-in-this-monitoring-pack"></a>Fichiers dans ce pack d’analyse

Le pack d’analyse pour Skype Entreprise Server 2015 inclut les fichiers suivants :
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Nouveautés

Les fonctionnalités suivantes sont nouvelles dans les packs d’administration de Skype Entreprise Server 2015.

- **Modifications apportées à la mise à jour de [septembre 2019](https://www.microsoft.com/en-in/download/details.aspx?id=47364)** Certains caractères spéciaux ont été supprimés de certaines alertes. Dans certains cas, des caractères spéciaux interfèrent avec la fonctionnalité de notification du canal de commande SCOM.

- **Découverte automatique pour la signature du client** Les applications clientes qui se connectent à Skype Entreprise Server 2015 détectent souvent automatiquement le serveur à qui se connecter. Les transactions synthétiques peuvent désormais vérifier que la découverte automatique est configurée correctement.
    
- **Intervalles d’exécuter des transactions synthétiques personnalisées** Pour simplifier le processus de mise en place des nodes watcher, les transactions synthétiques peuvent partager des comptes d’utilisateur. Cela ralentit la fréquence à laquelle les tests sont exécutés à mesure que les tests sont sérialisés afin d’éviter les conflits. Par défaut, les transactions synthétiques s’exécutent toutes les 15 minutes pour s’assurer que tous les tests ont le temps de s’exécuter. Les administrateurs qui choisissent d’utiliser plus d’utilisateurs ou moins de tests par utilisateur peuvent désormais réduire l’intervalle d’utilisation.
    
- **Transaction synthétique Video Interop Services** Les clients qui migrent vers Skype Entreprise Server 2015 à partir d’autres solutions de fournisseur souhaitent souvent continuer à utiliser les périphériques de téléconférence vidéo (VTC) de ces autres fournisseurs. Video Interop Server est un nouveau rôle serveur Skype Entreprise Server 2015 qui permet aux clients de continuer à utiliser des VTC Cisco dans leurs salles de conférence en se connectant à Cisco CUCM via une connexion SIP vidéo. Cette fonctionnalité ajoute également une transaction synthétique pour vérifier que le serveur d’opation vidéo est en cours d’opération et qu’il peut gérer les connexions entrantes sur une connexion SIP vidéo.
    
- **Transaction synthétique de conférence de partage d’application** La validation de scénario de bout en bout pour les conférences de partage d’application est désormais prise en charge.
    
## <a name="monitoring-scenarios"></a>Scénarios de surveillance

Le pack d’administration Skype Entreprise Server 2015 tire parti d’une variété de fonctionnalités pour vous aider à détecter et diagnostiquer les problèmes. Ces fonctionnalités offrent une visibilité en temps réel de l’état d’un environnement Skype Entreprise Server 2015.
  
|Scénario de surveillance|Description|
|:-----|:-----|
|Transactions synthétiques  <br/> | Windows PowerShell cmdlets pour tester et garantir la haute disponibilité des scénarios tels que la signature, la présence, la messagerie instantanée et les conférences pour les utilisateurs. <br/> Les transactions synthétiques peuvent être exécutés à partir de n’importe quel emplacement géographique, y compris à l’intérieur de l’entreprise, en dehors de l’entreprise et dans les succursales.  <br/> En cas d’échec d’une transaction synthétique, des journaux HTML sont créés pour vous aider à déterminer la nature exacte de l’échec. Cela inclut la compréhension de l’action qui a échoué, de la latence de chaque action, de la ligne de commande utilisée pour exécuter le test et de l’erreur spécifique qui s’est produite.  <br/> |
|Alertes de fiabilité des appels  <br/> |Les enregistrements des détails des appels écrits par les serveurs Skype Entreprise Server 2015 reflètent si les utilisateurs peuvent se connecter à un appel ou pourquoi un appel est interrompu. Les alertes de fiabilité des appels interrogent la base de données d’appels pour produire des alertes qui indiquent quand un grand nombre d’utilisateurs sont en situation de problèmes de connectivité pour les appels d’égal à égal ou la fonctionnalité de conférence de base.  <br/> La couverture de scénario inclut les appels audio, la messagerie instantanée d’égal à égal et d’autres fonctionnalités de conférence.  <br/> |
|Alertes de qualité des médias  <br/> |Requêtes de base de données qui se rapportent aux rapports de qualité de l’expérience (QoE) publiés par les clients Skype Entreprise Server 2015 à la fin de chaque appel. Ces requêtes produisent des alertes qui identifient les scénarios où les utilisateurs sont les plus susceptibles d’être compromis par la qualité des médias pendant les appels et les conférences. Les données reposent sur des mesures clés, telles que la latence et la perte de paquets, qui contribuent directement à la qualité de l’expérience utilisateur.  <br/> |
|Alertes d’état des composants  <br/> |Les composants serveur individuels lèvent des alertes via les journaux des événements et les compteurs de performances pour indiquer les conditions de défaillance qui peuvent avoir une incidence significative sur les scénarios utilisateur. Ces alertes indiquent diverses conditions, telles que les services qui ne fonctionnent pas, les taux d’échec élevés, la latence des messages élevée ou les problèmes de connectivité.  <br/> |
|Surveillance de l’état des dépendances  <br/> |Skype Entreprise Server peut échouer pour diverses raisons externes. Le pack d’administration surveille et collecte des données pour les dépendances externes critiques qui peuvent indiquer des problèmes graves. Ces dépendances incluent la disponibilité des services Internet (IIS) et le processeur des serveurs utilisés pour Skype Entreprise Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Priorité des alertes

Les alertes sont classées dans les catégories suivantes : 
  
 **Alertes à priorité élevée :** Ces alertes indiquent les conditions qui provoquent des pannes de service pour de grands groupes d’utilisateurs et nécessitent une action immédiate. Les pannes détectées par les transactions synthétiques et les services hors connexion (tels que la conférence audio/vidéo Skype Entreprise Server) sont considérées comme des alertes de haute priorité. En revanche, une défaillance de composant sur un seul ordinateur n’est pas une alerte de haute priorité. Skype Entreprise Server 2015 dispose de fonctionnalités de haute disponibilité intégrées pour ces situations, par exemple, plusieurs serveurs frontaux derrière des équilibreurs de charge.
  
 **Alertes de priorité moyenne :** Ces alertes indiquent des conditions qui affectent un sous-ensemble d’utilisateurs ou indiquent des problèmes de qualité des appels, par exemple, des défaillances de composants, la latence de l’établissement des appels ou une qualité audio moindre dans les appels. Les alertes de cette catégorie sont avec état (autrement dit, la nature de l’alerte change en fonction de l’état de la connexion réseau.) Par exemple, si les heures d’établissement des appels indiquent une latence mais reviennent à un seuil normal, cette alerte de priorité moyenne est automatiquement résolue dans System Center Operations Manager et les administrateurs n’ont pas besoin d’agir. Les alertes qui ne peuvent pas être résolues automatiquement sont généralement traitées par les administrateurs le même jour oué.
  
 **Autres alertes :** Ces alertes sont générées à partir de composants qui peuvent affecter un utilisateur ou un sous-ensemble spécifique d’utilisateurs. Par exemple, une alerte classique serait que le service de carnet d’adresses n’a pas pu l'® Active Directory® Domain Services (AD DS) pour l’utilisateur : testuser@contoso.com. Les administrateurs peuvent traiter ces alertes chaque fois qu’ils disposent de temps.
  
### <a name="synthetic-transactions"></a>Transactions synthétiques

Les packs d’administration Skype Entreprise Server 2015 offrent une couverture accrue pour les alertes par le biais de transactions synthétiques. Les transactions synthétiques sont Windows PowerShell cmdlets intégrées au pack d’administration Operations Manager pour tester des scénarios utilisateur de bout en bout. Lorsque vous désignez un serveur pour exécuter des transactions synthétiques, ces cmdlets sont déclenchées régulièrement par le pack d’administration. Les échecs résultant d’une transaction synthétique génèrent une alerte avec état. Voici les transactions synthétiques prise en charge pour Skype Entreprise Server 2015 :
  


|Transactions synthétiques prise en charge pour l’inscription, la présence et les contacts|||
|:-----|:-----|:-----|
|1   <br/> |Inscription (connexion utilisateur)  <br/> |Lync Server 2010 disponible et au-delà  <br/> |
|2   <br/> |Service de carnet d’adresses (téléchargement de fichiers)  <br/> |Lync Server 2010 disponible et au-delà  <br/> |
|3   <br/> |Requête web du carnet d’adresses  <br/> |Lync Server 2010 disponible et au-delà  <br/> |
|4   <br/> |Présence  <br/> |Lync Server 2010 disponible et au-delà  <br/> |
|5   <br/> |Magasin de contacts unifié  <br/> |Lync Server 2013 disponible et au-delà  <br/> |
||||   

|Transactions synthétiques prise en charge pour les services D’égal à égal|||
|:-----|:-----|:-----|
|6   <br/> |Messagerie instantanée D’égal à égal  <br/> |Disponible dans Lync Server 2010 et au-delà  <br/> |
|7   <br/> |Vidéo audio d’égal à égal  <br/> |Disponible dans Lync Server 2010 et au-delà  <br/> |
|8   <br/> |Message instantané D’égal à égal MCX (mobile)  <br/> |Disponible dans la version de septembre 2011 de Lync Server 2010 pour Skype Entreprise 2015  <br/> |
 
> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.


|Transactions synthétiques prise en charge pour les conférences et la conversation permanente|||
|:-----|:-----|:-----|
|9   <br/> |Conférence audio-vidéo  <br/> |Disponible dans Lync Server 2010 et au-delà  <br/> |
|10   <br/> |Conférence de données  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|11   <br/> |Conférence par message instantané  <br/> |Disponible dans Lync Server 2010 et au-delà  <br/> |
|12   <br/> | Conversation permanente <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|13   <br/> |Rejoindre Lanceur (réunions prévues)  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|14   <br/> |Conférences téléphoniques  <br/> |Nouveautés de Skype Entreprise Server 2015  <br/> |
|15   <br/> |Conférence de partage d’application  <br/> |Nouveautés de Skype Entreprise Server 2015  <br/> |
|16   <br/> |Conférence UCWA (rejoindre une réunion web)  <br/> |Nouveautés de Skype Entreprise Server 2015  <br/> |
||||

|Transactions synthétiques prise en charge pour les dépendances de réseau et de partenaire|||
|:-----|:-----|:-----|
|17   <br/> |Connectivité Edge AV  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|18   <br/> |Connectivité de messagerie unifiée Exchange de connectivité Edge ANTIVIRUS (messagerie vocale)  <br/> |Disponible dans Lync Server 2013 et au-delà  <br/> |
|19  <br/> |Appel PSTN D’égal à égal  <br/> |Disponible dans Lync Server 2010 et au-delà  <br/> |
|20  <br/> |Messagerie instantanée XMPP (fédération)  <br/> |Disponible dans Lync Server 2013 et Skype Entreprise 2015  <br/> |
| 21  <br/> |Serveur d’interopérabilité vidéo (VIS)  <br/> |Nouveautés de Skype Entreprise Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Comment l’état d’health rolls up

Le tableau suivant indique l’état d’état d’état des objets du pack d’analyse Skype Entreprise Server.
  
|Management Pack, objet|Description|
|:-----|:-----|
|Déploiement de Skype Entreprise Server  <br/> |Représente le déploiement de Skype Entreprise Server 2015 dans l’organisation.  <br/> |
|Site Skype Entreprise Server  <br/> |Représente différents emplacements géographiques où les services sont déployés.  <br/> |
|Pool de serveurs Skype Entreprise  <br/> |Pool (au sein d’un site) qui fournit des services de communication, tels que la messagerie instantanée et les conférences, aux utilisateurs. Applicable aux pools frontux, aux pools edge et aux pools directeurs, même s’il n’existe qu’un seul ordinateur dans un pool donné.  <br/> |
|Rôle Skype Entreprise Server  <br/> |Rôle serveur qui héberge le service Skype Entreprise Server.  <br/> |
|Service Skype Entreprise Server  <br/> |Représente une fonctionnalité déployée sur un ordinateur spécifique (par exemple, le service utilisateur sur fp01.contoso.com).  <br/> |
|Composant Skype Entreprise Server  <br/> |Composant du service (par exemple, le composant téléchargement du carnet d’adresses fait partie du service Web).  <br/> |
|Skype Entreprise Server Pool Watcher  <br/> |Instance de transactions synthétiques en cours d’exécution sur un pool.  <br/> |
|Skype Entreprise Server Registrar Watcher  <br/> |Instance de transactions synthétiques qui s’exécutent sur un pool de bureaux d’inscriptions.  <br/> |
|Skype for Business Server User Services Pool Watcher  <br/> |Instance de transactions synthétiques qui s’exécutent sur un pool de services d’utilisateurs.  <br/> |
|Skype Entreprise Server Voice Pool Watcher  <br/> |Instance de transactions synthétiques qui s’exécutent sur un pool de voix.  <br/> |
|Skype Entreprise Server Port Watcher  <br/> |Instance de vérifications de port en cours d’exécution sur un pool.  <br/> |
|Simple URL Watcher  <br/> |Effectue une analyse HTTPS des URL simples configurées dans un déploiement.  <br/> |
   
![SCOM Rollup](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un pool Skype Entreprise Server peut contenir plusieurs systèmes Skype Entreprise Server individuels (avec plusieurs rôles Skype Entreprise Server, service Skype Entreprise Server et composant Skype Entreprise Server). Par conséquent, la défaillance d’un serveur ou d’un composant individuel est moins critique pour l’état global du pool Skype Entreprise Server, car d’autres serveurs du même pool peuvent fournir le service d’application au client. L’état d’santé est resserra sur un pourcentage pour le pool Skype Entreprise Server. 
  
L’watcher du pool Skype Entreprise Server effectue des transactions synthétiques sur un pool Skype Entreprise Server. Les échecs consécutifs d’une ou de plusieurs transactions synthétiques (processus appelé intervalle d’interrogation consécutif) relaient l’état d’état d’état critique au niveau du pool (pire de toute transaction synthétique), comme illustré dans le diagramme suivant. 
  
![Interrogation consécutive de l’opération de déploiement SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Meilleure pratique : créer un pack d’administration pour les personnalisations

Par défaut, Operations Manager enregistre toutes les personnalisations, telles que les remplacements dans le pack d’administration par défaut. En tant que meilleure pratique, vous devez créer un pack d’administration distinct pour chaque pack d’administration sealed que vous souhaitez personnaliser. 
  
Lorsque vous créez un pack d’administration pour stocker les paramètres personnalisés d’un pack d’administration sealed, nous vous recommandons d’nommer le nouveau pack d’administration de manière appropriée, par exemple « Personnalisations de Skype Entreprise Server 2015 ». 
  
La création d’un pack d’administration pour le stockage des personnalisations de chaque pack d’administration sealed facilite l’exportation des personnalisations d’un environnement de test vers un environnement de production. Cela facilite également la suppression d’un pack d’administration, car vous devez supprimer toutes les dépendances avant de pouvoir supprimer un pack d’administration. Si les personnalisations de tous les packs d’administration sont enregistrées dans le pack d’administration par défaut et que vous devez supprimer un seul pack d’administration, vous devez d’abord supprimer le pack d’administration par défaut, qui supprime également les personnalisations d’autres packs d’administration. 
  
## <a name="links"></a>Liens

Les liens suivants vous connectent à des informations sur les tâches courantes associées aux packs d’analyse System Center 2012 :
  
- [Cycle de vie du pack d’administration](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Comment importer un pack d’administration dans Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Comment remplacer une règle ou un moniteur](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Comment créer un compte Exécuter en tant que dans Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Gestion des comptes et des profils d’exécuter en tant que](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Comment exporter un pack d’administration Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Comment supprimer un pack d’administration Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
Les liens suivants vous connectent à des informations sur les tâches courantes associées aux packs d’analyse System Center 2007 :
  
- [Administration du cycle de vie du pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Comment importer un pack d’administration dans Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Comment surveiller l’utilisation de remplacements](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [How to Create a Run As Account in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Comment modifier un profil d’exécuter en tant que existant](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Comment exporter des personnalisations de pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Comment supprimer un pack d’administration](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Pour des questions sur Operations Manager et les packs d’analyse, consultez le forum de la [communauté System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Une ressource utile est le blog [de System Center Operations Manager 2013,](https://opsmgrunleashed.wordpress.com/) qui contient des billets « Par exemple » pour des packs d’analyse spécifiques.
  
Pour plus d’informations sur Operations Manager, consultez les blogs suivants : 
  
- [Blog de l’équipe Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog OpsMgr de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Thoughts on OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Yézy](https://rburri.wordpress.com/)
    
- [Espace de gestion BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toutes les informations et le contenu des sites autres que Microsoft sont fournis par le propriétaire ou les utilisateurs du site web. Microsoft n’offre aucune garantie, express, implicite ou statutaire, concernant les informations de ce site web. 
  
## <a name="see-also"></a>Voir aussi

[Outils de gestion Skype Entreprise Server 2015](../../management-tools/management-tools.md)
