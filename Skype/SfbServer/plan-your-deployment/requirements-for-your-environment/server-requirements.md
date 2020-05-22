---
title: Configuration requise pour le serveur pour Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Résumé : Préparez vos serveurs Skype entreprise Server 2015 avec cette rubrique. Matériel, système d’exploitation, bases de données, logiciel, toutes les exigences système et les recommandations sont ici pour vous aider à réussir l’installation et le déploiement de votre batterie de serveurs.'
ms.openlocfilehash: 02ccebca4eebef84638992dd88ba45040e733d19
ms.sourcegitcommit: b1f7f1435c5e72c2eea4069fbb0bea29b197cb80
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342454"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Configuration requise pour le serveur pour Skype entreprise Server 2015
 
**Résumé :** Préparez vos serveurs Skype entreprise Server 2015 avec cette rubrique. Matériel, système d’exploitation, bases de données, logiciel, toutes les exigences système et les recommandations sont ici pour vous aider à réussir l’installation et le déploiement de votre batterie de serveurs.

Si vous recherchez des exigences environnementales, telles qu’Active Directory, le DNS ou des certificats, vous pouvez consulter la [configuration environnementale requise pour le document Skype entreprise Server 2015](environmental-requirements.md) .
  
Comme vous pouvez vous y attendre, certaines préparations doivent être apportées avant de commencer à déployer Skype entreprise Server 2015. Cet article vous guidera dans la planification des opérations suivantes :
  
- [Matériel pour Skype entreprise Server 2015](server-requirements.md#Hardware)
  
- [Systèmes d’exploitation pour Skype entreprise Server 2015](server-requirements.md#OS)
  
- [Bases de données principales qui fonctionneront avec Skype entreprise Server 2015](server-requirements.md#DBs)
  
- [Logiciels devant être installés avant un déploiement de Skype entreprise Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Matériel pour Skype entreprise Server 2015
<a name="Hardware"> </a>

Maintenant que vous disposez de votre topologie (et si ce n’est pas le cas, vous pouvez consulter la rubrique relative aux [concepts de base de la topologie pour Skype entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), il est temps de réfléchir aux serveurs. Les serveurs Skype entreprise Server 2015 nécessitent un matériel 64 bits. Nos recommandations en matière de matériel sont indiquées ci-dessous. Ces configurations ne sont pas requises, mais elles reflètent les conditions requises pour des performances optimales. Nous disposons d’une documentation sur la planification de la capacité qui vous permettra de déterminer si vous avez besoin de plus de, en fonction de vos circonstances.
  
Matériel recommandé pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition et les serveurs de conversation permanente :
  
|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |biprocesseur de 64 bits, hex-Core, 2,26 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles Skype entreprise Server 2015.  <br/> |
|Mémoire  <br/> |32 gigaoctets (Go).  <br/> |
|Disque  <br/> |ENTRE  <br/> • 8 disques durs 10000 tr/min avec au moins 72 Go d’espace disque disponible (deux des disques utilisant RAID 1 et 6 avec RAID 10).  <br/> OR  <br/> • Disques SSD (Solid State Drive) capables de fournir le même espace libre et des performances similaires sur des disques durs mécaniques de 8 10000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou supérieur (2 cartes réseau peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations double ou multi-résidents ne sont **pas** prises en charge pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition Server et les serveurs de conversation permanente. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel de serveur, vous pouvez disposer de systèmes de gestion hors bande, comme DRAC ou ILO. Ce scénario ne constitue pas un serveur multi-hébergement et est pris en charge.  <br/> |
   
Matériel recommandé pour les serveurs Edge, les serveurs de médiation autonomes, les serveurs d’interopérabilité vidéo et les directeurs :
  
|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Double processeur 64 bits, quadruple cœur, 2,26 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles Skype entreprise Server 2015.  <br/> |
|Mémoire  <br/> |16 gigaoctets.  <br/> |
|Disque  <br/> |ENTRE  <br/> • au moins 4 disques durs 10000 RPM avec au moins 72 Go d’espace disque disponible (les disques doivent être dans une configuration 2x RAID 1).  <br/> OR  <br/> • Disques SSD (Solid State Drive) capables de fournir le même espace libre et des performances similaires sur des disques durs mécaniques de 4 10000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou supérieur (2 cartes réseau peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations Dual ou multi-hébergement ne sont **pas** prises en charge pour les serveurs et les directeurs d’interopérabilité vidéo. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau à deux ports, 1 Gbits/s ou supérieur (ou deux cartes réseau couplées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et une seule adresse IP, pour un total de deux paires).  <br/> Sur les serveurs de médiation autonomes, l’installation de cartes d’interface réseau (NIC) supplémentaires pour permettre la configuration d’une adresse IP RTC spécifique est prise en charge.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Systèmes d’exploitation pour Skype entreprise Server 2015
<a name="OS"> </a>

Une fois le matériel en place, vous devez installer les systèmes d’exploitation (OS). Voici le système d’exploitation qui vous permettra d’installer et d’utiliser avec succès Skype entreprise Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (vous avez besoin de la mise à jour cumulative 9 de Skype entreprise ou version ultérieure). <br/> |Windows Server 2016 (vous avez besoin de la mise à jour cumulative 5 de Skype entreprise ou version ultérieure. Pour plus d’informations, consultez la [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)(en anglais)  <br/> ||
|Système d’exploitation Windows Server 2012 R2 Datacenter avec toutes les mises à jour requises installées.  <br/> |Windows Server 2012 R2 Standard OS avec toutes les mises à jour requises installées.  <br/> |
|Windows Server 2012 Datacenter OS avec toutes les mises à jour requises installées.  <br/> |Windows Server 2012 standard OS avec toutes les mises à jour requises installées.  <br/> |
   
S’il ne figure pas sur cette liste, il ne fonctionnera pas correctement, veuillez ne pas le tester pour les nouvelles installations de Skype entreprise Server 2015.

> [!NOTE]
> La mise à niveau sur place du système d’exploitation n’est pas prise en charge avec Lync Server 2013. Vous devez déployer un pool distinct et migrer les utilisateurs vers le nouveau pool avec un système d’exploitation différent. Tous les serveurs d’un pool doivent avoir la même version de système d’exploitation.
  
> [!NOTE]
> Vous avez peut-être remarqué que Windows Server 2008 R2 ne figure pas sur cette liste. En effet, nous vous recommandons d’utiliser Windows Server 2012 R2 pour tous les nouveaux serveurs pour SFB. Vous devez utiliser Windows Server 2008 R2 uniquement lorsque vous disposez de serveurs existants où Lync Server 2013 est déjà installé, et que vous avez l’intention d’effectuer une mise à niveau sur place. Windows Server 2008 R2 a atteint la fin du cycle de vie de support standard le 1/13/2015 et atteindra la fin de son cycle de vie sur 1/14/2020.
  
Outre le Service Pack le plus récent, vous devez vous assurer que les mises à jour suivantes sont installées, le cas échéant :
  
- Pour Windows Server 2012, l’article 2858668 de la base de connaissances doit être installé avant une mise à niveau. [Obtenez-le ici](https://support.microsoft.com/kb/2858668/).
    
- Si vous disposez de Windows Server 2012 R2, installez l’article 2982006 de la base de connaissances avant de procéder à la mise à niveau. [Elle se trouve ici](https://support.microsoft.com/kb/2982006/).
    
- Si vous effectuez une mise à niveau sur une zone Windows Server 2008 R2 (voir la remarque ci-dessus), vous devez d’abord installer l’article 2533623 de la base de connaissances. [Il se trouve à ce lien](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de données principales qui fonctionneront avec Skype entreprise Server 2015
<a name="DBs"> </a>


Lors de l’installation de Skype entreprise Server 2015 Standard Edition, vous disposez également de SQL Server 2014 Express (64-bit Edition) automatiquement installé.
  
Skype entreprise Server 2015 Enterprise Edition est un peu plus compliqué, mais la liste prise en charge est ci-dessous (tout est l’édition 64 bits, vous remarquerez que vous n’utilisez pas les éditions 32 bits) :
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack. <br/> |Microsoft SQL Server 2017 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack. <br/> |Microsoft SQL Server 2016 entreprise (version 64 bits) avec Service Pack 1 ou version ultérieure, et vous devez l’exécuter avec la mise à jour cumulative 7 ou ultérieure de Skype entreprise ([Télécharger la mise à jour cumulative de Skype entreprise](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (64-bit Edition) et vous devez l’exécuter avec la mise à jour cumulative 6 ou une version ultérieure ([Télécharger la mise à jour cumulative 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.  <br/> |
|Microsoft SQL Server 2019 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack. <br/> |Microsoft SQL Server 2017 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack. <br/> |Microsoft SQL Server 2016 standard (version 64 bits) avec Service Pack 1 ou version ultérieure, et vous devez l’exécuter avec la mise à jour cumulative 7 ou ultérieure de Skype entreprise ([Télécharger la mise à jour cumulative de Skype entreprise](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 standard (64-bit Edition) et vous devez l’exécuter avec la mise à jour cumulative 6 ou une version ultérieure ([Télécharger la mise à jour cumulative 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.  <br/> |
   
Si vous ne voyez pas l’édition SQL Server que vous souhaitez utiliser répertoriée ici, vous ne pouvez pas l’utiliser.
  
- Vous devrez également installer SQL Server Reporting Services pour le rôle serveur de surveillance.
- Pour une dorsale SQL correctement connectée, la connexion au serveur frontal Skype entreprise doit être locale, et non un lien à basse vitesse. 
- Le partage des terminaisons SQL entre deux pools ou plus n’est pas pris en charge.

### <a name="microsoft-exchange-storage"></a>Stockage Microsoft Exchange
Les fichiers de contenu de réunion, par exemple les présentations PowerPoint, sont archivés sous forme de pièces jointes. Si vous souhaitez stocker des données d’archivage Skype entreprise avec des données de conformité Exchange, vous devez utiliser Exchange pour votre déploiement Exchange et vous assurer que la taille de stockage maximale prend en charge le stockage des fichiers de contenu de réunion. Vous devez déployer Exchange avant de déployer et d’activer l’archivage à l’aide de l’option d’intégration de Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Configuration matérielle et logicielle requise pour l’archivage dans Skype entreprise Server 2015
  
L’archivage n’est pas un rôle de serveur défini, vous n’avez pas besoin d’installer un serveur distinct pour l’archivage. Les agents de collecte de données unifiée sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et tous les serveurs Standard Edition. Vous devrez activer et publier votre topologie d’archivage à l’aide du générateur de topologie.
    
L’archivage utilise le stockage de fichiers Skype entreprise Server pour le stockage temporaire des fichiers de contenu de réunion, de sorte que vous ne configurez pas de magasin de fichiers distinct pour l’archivage.
    
Microsoft Message Queuing n’est pas obligatoire.
    
Vous devrez configurer l’infrastructure pour l’archivage du stockage. Cela inclut le choix entre Exchange ou le stockage d’archivage à l’aide de SQL Server.   Les conditions requises pour l’infrastructure d’archivage de Skype entreprise Server sont les mêmes que pour le déploiement de Skype entreprise Server. Pour plus d’informations, reportez-vous [à la rubrique Configuration requise pour votre environnement Skype entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Pour prendre en charge les utilisateurs qui ne sont pas hébergés sur des serveurs Exchange, ou si vous ne souhaitez pas utiliser l’option d’intégration de Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server 64 bits. 
    
Vous devez configurer les plateformes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriées, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, lors de la procédure d’installation. Pour plus d’informations sur SQL Server, reportez-vous à la [documentation SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
L’augmentation de la charge pour l’archivage peut être importante. Par conséquent, vous devez vous assurer que l’espace disque est suffisant pour les serveurs frontaux sur lesquels l’archivage est activé.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Mise en miroir SQL, clustering SQL et SQL Always on

Vous pouvez utiliser la mise en miroir SQL ou le clustering SQL avec Skype entreprise Server 2015, elle est prise en charge. La mise en miroir SQL est configurée via le générateur de topologie Skype entreprise Server. Si vous avez l’intention de configurer le clustering SQL, cela se fait dans SQL Server.
  
Assurez-vous que vous disposez d’une configuration active/passive pour le clustering SQL, car cela est pris en charge. Ne partagez pas le nœud passif avec une autre instance SQL.
  
Vous pouvez disposer des éléments suivants pour le clustering de basculement :
  
Deux nœuds :
  
- Microsoft SQL Server 2019 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

- Microsoft SQL Server 2017 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

- Microsoft SQL Server 2016 standard (édition 64 bits) avec Service Pack 1 ou version ultérieure. Nous vous recommandons de l’exécuter avec le Service Pack le plus récent.

- Microsoft SQL Server 2014 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.
    
-  Microsoft SQL Server 2012 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

Seize nœuds :

- Microsoft SQL Server 2019 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

- Microsoft SQL Server 2017 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

- Microsoft SQL Server 2016 entreprise (version 64 bits) avec Service Pack 1 ou version ultérieure. Nous vous recommandons de l’exécuter avec le Service Pack le plus récent.
  
- Microsoft SQL Server 2014 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.
    
- Microsoft SQL Server 2012 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

> [!IMPORTANT]
> Pour la mise à niveau, vous devez vous assurer que sur vos serveurs frontaux, vous disposez au minimum de SQL Server 2012 SP1 installé avant la mise à niveau. [Voici un lien](https://www.microsoft.com/download/details.aspx?id=35575) vers SP1 si vous voulez le télécharger immédiatement.
  
Si vous devez en savoir plus sur la mise en miroir SQL, nous disposons d’une haute disponibilité du serveur principal dans Skype entreprise Server 2015. Configure SQL Server clustering for Skype for Business Server 2015 présente les étapes à suivre pour préparer le clustering. Il existe également d’autres liens sur le clustering de basculement pour SQL, [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)et [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Une nouveauté de la version 2015 est la prise en charge de SQL Always on. Elle est prise en charge et vous pouvez en savoir plus à ce sujet dans la rubrique [haute disponibilité des serveurs principaux dans Skype entreprise server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de basculement AlwaysOn (ICF) et les méthodes de clustering de basculement SQL sont préférés avec Skype entreprise Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Logiciels devant être installés avant un déploiement de Skype entreprise Server 2015
<a name="Software"> </a>

Vous devrez installer ou configurer pour n’importe quel serveur exécutant Skype entreprise Server 2015 et ceux-ci sont répertoriés ci-dessous. Une fois ces conditions requises pour des rôles serveur spécifiques.

  
 **Tous les serveurs :**
  
|**Logiciels/rôles**|**Détails**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tous les serveurs Skype entreprise Server nécessitent Windows PowerShell 3,0.  <br/> • Si vous effectuez l’installation sur Windows Server 2012 ou Windows Server 2012 R2, c’est que vous l’avez déjà fait.  <br/> • Si vous effectuez une mise à niveau sur Windows Server 2008 R2, vous pouvez télécharger [Windows Management Framework 3,0](https://www.microsoft.com/download/details.aspx?id=34595) pour l’obtenir. <br/> **Conseil :** Une fois que vous avez correctement PowerShell, vérifiez qu’il est BuildVersion 6.2.9200.0 ou une version ultérieure en accédant à l’invite PowerShell et en tapant `$PSVersionTable` . Cela doit afficher les informations dont vous avez besoin.  <br/> |
|Microsoft .NET Framework  <br/> |Services WCF est une **fonctionnalité** installée en tant que fonctionnalité Windows, sous **Gestionnaire de serveur**, aucun téléchargement nécessaire. <br/> • Vous devez vous assurer, lorsque vous installez cette fonctionnalité, ou si elle est déjà installée et que vous l’archivez, que l’option d' **activation http** est également vérifiée et installée, comme suit : <br/> ![Capture d’écran illustrant l’option d’activation HTTP sous les fonctionnalités .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) Ne vous inquiétez pas si vous obtenez une fenêtre contextuelle supplémentaire indiquant que d’autres éléments doivent être installés pour que l’activation HTTP soit installée. C’est normal, cliquez sur OK et poursuivez. Si vous n’obtenez pas cette fenêtre contextuelle, supposez que ces éléments sont déjà installés et continuez.  <br/> Microsoft .NET Framework est généralement installé lorsque Windows Server 2012 R2 ou Windows Server 2016 sont installés. Skype entreprise Server fonctionne avec les versions de Microsoft .NET Framework suivantes :  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (pour les versions de mise à jour cumulative 5 ou ultérieures de Skype entreprise Server)  <br/> • .NET 4.7.2 (pour les versions de mise à jour cumulative 6 ou versions ultérieures de Skype entreprise Server)  <br/>  • .NET 4,8 (versions CU 9 ou versions ultérieures de Skype entreprise Server) <br/>  .NET Framework 3,5 sera probablement installé par défaut sur votre ordinateur Windows Server 2008 R2 (vérifiez bien que vous devez être sûr avant de procéder à la mise à niveau), mais il ne figure pas sur vos serveurs Windows Server 2012/Windows Server 2012 R2 (pour les nouvelles installations). Pour l’ajouter dans, vous aurez besoin d’un accès à votre lecteur ou à votre support d’installation (le lieu à partir duquel votre serveur Windows a été installé ou sur lequel les fichiers d’installation sont maintenant). Ensuite, installez-le en tant que fonctionnalité dans le gestionnaire de serveur et pointez sur le support d’installation (en particulier le dossier **\sources\sxs** ) lorsque vous y êtes invité, puis continuez à l’installer. <br/> |
|Media Foundation  <br/> |Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2, le runtime du format Windows Media est installé avec Microsoft Media Foundation.  <br/> Tous les serveurs frontaux et les serveurs Standard Edition utilisés pour les conférences nécessitent que Windows Media Format Runtime exécute les fichiers audio Windows Media (. WMA) que les applications de parcage d’appel, d’annonce et Response Group jouent pour les annonces et la musique.  <br/> |
|Windows Identity Foundation  <br/> |Nous avons besoin de Windows Identity Foundation 3,5 pour prendre en charge les scénarios d’authentification de serveur à serveur pour Skype entreprise Server 2015.  <br/> • Pour Windows Server 2012 et Windows Server 2012 R2, il n’est pas nécessaire de télécharger quoi que ce soit. Ouvrez le **Gestionnaire de serveur**, puis accédez à l' **Assistant Ajouter des rôles et des fonctionnalités**. **Windows Identity Foundation 3,5** est affiché sous la section **features** . Si elle est activée, c’est tout à fait. Sinon, sélectionnez-le et cliquez sur suivant pour accéder au bouton **installer** . <br/> |
|Outils d'administration de serveur distant  <br/> |Outils d’administration de rôles : services AD DS et AD LDS  <br/> |
   
 **Les serveurs frontaux et le serveur Standard Edition ont également besoin des éléments suivants :**
  
|**Logiciels/rôles**|**Détails**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS est nécessaire sur tous les serveurs frontaux, ainsi que sur tous les serveurs Standard Edition, avec les modules suivants sélectionnés :  <br/> • Fonctionnalités HTTP courantes : document par défaut, erreurs HTTP, contenu statique  <br/> • Intégrité et diagnostics : journalisation HTTP, outils de journalisation, suivi  <br/> • Performances : compression de contenu statique, compression de contenu dynamique  <br/> • Sécurité : filtrage des requêtes, authentification par mappage de certificat client, authentification Windows  <br/> • Développement d’applications : extensibilité .NET 3,5, extensibilité .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensions ISAPI, filtres ISAPI  <br/> • Outils de gestion : console de gestion IIS, scripts et outils de gestion IIS  <br/> Nous devons également noter que l’accès anonyme est également nécessaire, mais vous obtenez que lorsque vous installez les services Internet (IIS), vous n’avez pas besoin d’un emplacement pour le sélectionner dans la liste.  <br/> |
|Module d’exécution du format Windows Media  <br/> | Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2, vous devez installer la fonctionnalité **Media Foundation** dans le gestionnaire de **serveur**. À présent, vous pouvez démarrer votre installation de Skype entreprise Server 2015 sans celle-ci, mais vous serez invité à l’installer, puis à redémarrer le serveur, avant la poursuite de l’installation de Skype entreprise Server 2015. Il est préférable de le faire à l’avance. <br/> |
|Silverlight  <br/> |Vous pouvez installer la dernière version de Silverlight à [ce lien](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Vous devrez peut-être également activer la navigation dans les répertoires si vous utilisez un équilibreur de charge. Sinon, une page vierge chargera le programme d’équilibrage de la charge qui pourrait prendre en compte une défaillance. 

Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser les opérations suivantes :

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> La commande recherche les fichiers sources dans un ordre spécifique. Si vous êtes en ligne, la commande accède à Windows Update. Toutefois, si vous êtes en mode hors connexion, vous devez vous assurer que les fichiers sources sont disponibles pour la commande. Pour plus d’informations sur l’utilisation de PowerShell pour installer des rôles et des fonctionnalités, voir [installer ou désinstaller des rôles, des services de rôle ou des fonctionnalités](https://technet.microsoft.com/library/hh831809.aspx) n’oubliez pas d’exécuter de nouveau Windows Update après avoir installé les éléments prérequis, même si vous utilisez la commande PowerShell.

 **Les directeurs ont également besoin des éléments suivants :**
  
IIS, avec les modules suivants sélectionnés :
  
- Fonctionnalités HTTP courantes
    
  - Document par défaut
    
  - Erreurs HTTP
    
  - Contenu statique
    
- État de santé et diagnostics
    
  - Journalisation HTTP
    
  - Outils de journalisation
    
  - Analyzer
    
- Performances
    
  - Compression de contenu statique
    
- Sécurité
    
  - Filtrage des demandes
    
  - Authentification par mappage de certificat client
    
  - Authentification Windows
    
- Développement d’applications
    
  - Extensibilité .NET 3,5
    
  - Extensibilité .NET 4.5
    
  - ASP.NET 3,5
    
  - ASP.NET 4,5
    
  - Extension ISAPI
    
  - Filtres ISAPI
    
(Si vous vous y demandez, il s’agit du même ensemble de modules que les serveurs frontaux et Standard Edition, les outils de compression et de gestion de contenu dynamiques étant laissés.)
  
Voici quelques exemples de code PowerShell :
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Les serveurs de conversation permanente ont également besoin des éléments suivants :**
  
Mise en file d’attente des messages, qui est également appelée MSMQ. Il s’agit d’un composant de serveur Windows et vous pouvez l’installer sous la section fonctionnalités dans le gestionnaire de serveur. Si vous souhaitez en savoir plus à ce sujet, consultez la rubrique [installation et gestion de Message Queuing](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Dernière idée :**
  
N’installez pas de logiciel client Microsoft Internet Security and Acceleration (ISA) Server ou tout autre logiciel de fournisseur de services en couche (LSP) Winsock (tous les logiciels d’inspection de réseau antivirus ou de pare-feu tiers seraient inclus ici) sur l’un des serveurs frontaux ou des serveurs de médiation autonomes. De mauvaises performances de trafic multimédia ont été constatées lorsque ce logiciel est installé.
  

