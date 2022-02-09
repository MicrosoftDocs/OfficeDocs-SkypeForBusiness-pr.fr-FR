---
title: Server requirements for Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Résumé : Préparez vos serveurs Skype Entreprise Server 2015 avec cette rubrique. Le matériel, le système d’exploitation, les bases de données, les logiciels, la configuration système requise et les recommandations sont là pour garantir une installation et un déploiement réussis de votre batterie de serveurs.'
ms.openlocfilehash: 36b9731602dc5fd753dbc2d0ca54e88cb212c5ad
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398718"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Server requirements for Skype Entreprise Server 2015
 
**Résumé :** Préparez vos Skype Entreprise Server 2015 avec cette rubrique. Le matériel, le système d’exploitation, les bases de données, les logiciels, la configuration système requise et les recommandations sont là pour garantir une installation et un déploiement réussis de votre batterie de serveurs.

Si vous recherchez des exigences environnementales, telles qu’Active Directory, DNS ou des certificats, vous pouvez consulter les exigences en matière d’environnement pour [Skype Entreprise Server 2015](environmental-requirements.md).
  
Comme vous pouvez vous y attendre, il y a quelques préparations à effectuer avant de commencer à déployer Skype Entreprise Server 2015. Cet article vous explique comment planifier les projets suivants :
  
- [Matériel pour Skype Entreprise Server 2015](server-requirements.md#Hardware)
  
- [Systèmes d’exploitation Skype Entreprise Server 2015](server-requirements.md#OS)
  
- [Bases de données principale qui fonctionneront avec Skype Entreprise Server 2015](server-requirements.md#DBs)
  
- [Logiciel à installer avant un déploiement Skype Entreprise Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Matériel pour Skype Entreprise Server 2015
<a name="Hardware"> </a>

Maintenant que vous avez votre topologie en panne (et si vous ne le faites pas, vous pouvez consulter la rubrique Éléments de base de la topologie pour [Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)), il est temps de réfléchir aux serveurs. Skype Entreprise Server 2015 nécessiteront du matériel 64 bits. Nos recommandations en matière de matériel sont ci-dessous. Ce ne sont pas des exigences, mais elles reflètent les exigences nécessaires pour des performances optimales. Nous avons une documentation de planification de la capacité qui vous aidera à déterminer si vous en avez besoin de plus, en fonction de vos circonstances.
  
Matériel recommandé pour les serveurs frontux, les serveurs frontux, les serveurs Édition Standard serveurs et les serveurs de conversation permanente :
  
|Composant matériel|Recommandé|
|:-----|:-----|
|UC   |Bi-processeur 64 bits, hex-core, 2,26 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge Skype Entreprise Server rôles 2015.   |
|Mémoire   |32 gigaoctets (Go).   |
|Disque   |SOIT :  <br/> • 8 disques durs ou plus de 1 0000 TPM avec au moins 72 Go d’espace disque libre (deux disques utilisant RAID 1 et 6 utilisant RAID 10).  <br/> OR  <br/> • Des disques SSD (Solid State Drives) capables de fournir le même espace libre et des performances similaires à 8 disques mécaniques 10000 RPM.   |
|Réseau   |1 carte réseau double port, 1 Gbits/s ou plus (2 cartes réseau peuvent être utilisées, mais elles doivent être liées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double ou multi-accueil  ne sont pas pris en charge pour les serveurs frontaux, les serveurs frontaux, les serveurs Édition Standard serveurs et les serveurs de conversation permanente. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et qu’ils sont utilisés pour surveiller et gérer le matériel serveur, vous pouvez avoir des systèmes de gestion hors bande, tels que DRAC ou ILO. Ce scénario ne constitue pas un serveur multi-accueil et il est pris en charge.   |
   
Matériel recommandé pour les serveurs Edge, les serveurs de médiation autonomes, les serveurs d’interconnexion vidéo et les directeurs :
  
|Composant matériel|Recommandé|
|:-----|:-----|
|UC   |Double processeur 64 bits, quadruple cœur, 2,26 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge Skype Entreprise Server rôles 2015.   |
|Mémoire   |16 gigaoctets.   |
|Disque   |SOIT :  <br/> • 4 disques durs ou plus de 1 0000 TPM avec au moins 72 Go d’espace disque libre (les disques doivent être dans une configuration RAID 1 2x).  <br/> OR  <br/> • Des disques SSD (Solid State Drives) capables de fournir le même espace libre et des performances similaires à 4 disques mécaniques 10000 RPM.   |
|Réseau   |1 carte réseau double port, 1 Gbits/s ou plus (2 cartes réseau peuvent être utilisées, mais elles doivent être liées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double ou multi-accueil **ne sont pas** pris en charge pour les serveurs d’interconnexion vidéo et les directeurs. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau double port, 1 Gbits/s ou plus (ou deux cartes réseau couplées, pour un total de quatre, chaque paire étant associé à une seule adresse MAC et une seule adresse IP, pour un total de deux paires).  <br/> Sur les serveurs de médiation autonomes, l’installation de cartes d’interface réseau supplémentaires pour permettre la configuration d’une adresse IP PSTN spécifique est prise en charge.   |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Systèmes d’exploitation Skype Entreprise Server 2015
<a name="OS"> </a>

Une fois le matériel en place, vous devez installer les systèmes d’exploitation. Voici le système d’exploitation qui vous permettra d’installer et d’utiliser Skype Entreprise Server 2015.
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Windows Server 2019 (vous devez Skype Entreprise mise à jour cumulative 9 ou ultérieure).  |Windows Server 2016 (vous devez Skype Entreprise mise à jour cumulative 5 ou ultérieure. Pour plus d’informations, [consultez la KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))   |
|Windows Server 2012 système d’exploitation R2 Datacenter avec toutes les mises à jour requises installées.   |Windows Server 2012 système d’exploitation R2 Standard avec toutes les mises à jour requises installées.   |
|Windows Server 2012 Datacenter système d’exploitation avec toutes les mises à jour requises installées.   |Windows Server 2012 Standard système d’exploitation avec toutes les mises à jour requises installées.   |
   
S’il ne figure pas dans cette liste, il ne fonctionne pas correctement, veuillez ne pas l’essayer pour les nouvelles installations de Skype Entreprise Server 2015.

> [!NOTE]
> La mise à niveau sur place du système d’exploitation n’est pas prise en charge avec Lync Server 2013. Vous devez déployer un pool distinct et migrer les utilisateurs vers le nouveau pool avec un système d’exploitation différent. Tous les serveurs d’un pool doivent avoir la même version du système d’exploitation.
  
> [!NOTE]
> Vous avez peut-être remarqué Windows Server 2008 R2 ne figure pas dans cette liste. Cela est dû au fait que nous Windows Server 2012 R2 pour tous les nouveaux serveurs à utiliser pour SFB. Vous devez utiliser Windows Server 2008 R2 uniquement lorsque des serveurs existants avec Lync Server 2013 sont déjà installés et que vous avez l’intention de les mettre à niveau sur place. Windows Server 2008 R2 a atteint la fin du cycle de vie du support le 13/01/2015 et prendra fin le 14/14/2020.
  
En plus du Dernier Service Pack, vous devez vous assurer que les mises à jour suivantes sont installées lorsque cela vous semble pertinent :
  
- Par Windows Server 2012, l’article de la 2858668 doit être installé avant une mise à niveau. [Obtenez-le ici](https://support.microsoft.com/kb/2858668/).
    
- Si vous avez Windows Server 2012 R2, installez l’article de la 2982006 avant la mise à niveau. [Il est trouvé ici](https://support.microsoft.com/kb/2982006/).
    
- Si vous faites une mise à niveau sur une zone Windows Server 2008 R2 (voir la remarque ci-dessus), vous pouvez installer l’article de la 2533623 tout d’abord. [Il se place à ce lien](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de données principale qui fonctionneront avec Skype Entreprise Server 2015
<a name="DBs"> </a>


Lors de l’installation Skype Entreprise Server 2015 Édition Standard, SQL Server 2014 Express (édition 64 bits) est également installé automatiquement.
  
Skype Entreprise Server 2015 Êdition Entreprise est un peu plus complexe, mais la liste prise en charge est ci-dessous (tout est en édition 64 bits, vous remarquerez, n’utilisez pas les éditions 32 bits) :
  
|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.  |Microsoft SQL Server 2017 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.  |Microsoft SQL Server 2016 Enterprise (édition 64 bits) avec Service Pack 1 ou version ultérieure, et vous devez l’exécuter avec la mise à jour cumulative Skype Entreprise 7 ou [ultérieure (télécharger](https://support.microsoft.com/help/3061064) Skype Entreprise mise à jour cumulative).   |Microsoft SQL Server 2014 Enterprise (édition 64 bits) et vous devez exécuter la mise à jour cumulative 6 ou ultérieure (télécharger la mise à jour [cumulative 6](https://support.microsoft.com/kb/3031047/)).   |Microsoft SQL Server 2012 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.   |
|Microsoft SQL Server 2019 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.  |Microsoft SQL Server 2017 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.  |Microsoft SQL Server 2016 Standard (édition 64 bits) avec Service Pack 1 ou version ultérieure, et vous devez l’exécuter avec la mise à jour cumulative Skype Entreprise 7 ou [ultérieure (télécharger](https://support.microsoft.com/help/3061064) Skype Entreprise mise à jour cumulative).   |Microsoft SQL Server 2014 Standard (édition 64 bits) et vous devez l’exécuter avec la mise à jour cumulative 6 ou une version ultérieure (télécharger la mise à jour [cumulative 6](https://support.microsoft.com/kb/3031047/)).   |Microsoft SQL Server 2012 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.   |
   
Si vous ne voyez pas l’édition SQL Server que vous souhaitez utiliser répertoriée ici, vous ne pouvez pas l’utiliser.
  
- Vous devrez également installer SQL Server Reporting Services pour le rôle serveur de surveillance.
- Pour un appareil SQL bien connecté, la connexion au Skype Entreprise frontal doit être locale et non sur une liaison à faible vitesse. 
- Le partage SQL back end entre deux pools ou plus n’est pas pris en charge.

### <a name="microsoft-exchange-storage"></a>Stockage Exchange Microsoft
Les fichiers de contenu de réunion, par exemple les présentations PowerPoint, sont archivés sous forme de pièces jointes. Si vous souhaitez stocker des données d’archivage Skype Entreprise avec des données de conformité Exchange, vous devez utiliser Exchange pour votre déploiement Exchange et vous assurer que la taille de stockage maximale prend en charge le stockage des fichiers de contenu de réunion. Vous devez déployer Exchange avant de déployer et d’activer l’archivage à l’aide de l’option d’intégration Exchange Microsoft. 
    
Si vous choisissez d’utiliser le stockage Exchange, vous n’avez pas besoin de déployer des bases de données SQL Server distinctes pour l’archivage, sauf si vous avez des utilisateurs Skype Entreprise qui ne sont pas Exchange serveurs. Si vous déployez l’archivage à l’aide de l’option d’intégration Microsoft Exchange, les données d’archivage Skype Entreprise sont stockées avec les données de conformité Exchange uniquement pour les utilisateurs qui sont Exchange serveurs. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Configuration matérielle et logicielle requise pour l’archivage Skype Entreprise Server 2015
  
L’archivage n’est pas un rôle serveur défini, vous n’avez pas besoin d’installer un serveur distinct pour l’archivage. Les agents de collecte de données unifiées sont installés et activés automatiquement sur Êdition Entreprise pool frontal et chaque Édition Standard serveur. Vous devez activer et publier votre topologie d’archivage à l’aide du Générateur de topologies.
    
L’archivage utilise le Skype Entreprise Server de fichiers pour le stockage temporaire des fichiers de contenu de réunion, vous ne devez donc pas configurer de magasin de fichiers distinct pour l’archivage.
    
Microsoft Message Queuing n’est pas requis.
    
Vous devrez configurer l’infrastructure pour le stockage d’archivage. Cela inclut le choix entre Exchange stockage d’archivage à l’aide SQL Server.   Skype Entreprise Server’infrastructure d’archivage sont les mêmes que pour le déploiement de Skype Entreprise Server. Pour plus d’informations, voir [Requirements for your Skype Entreprise environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Pour prendre en charge les utilisateurs qui ne sont pas dossés sur des serveurs Exchange ou si vous ne souhaitez pas utiliser l’option d’intégration Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server 64 bits. 
    
Vous devez configurer les plateformes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriées, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, lors de la procédure d’installation. Pour plus d’informations sur SQL Server, voir la [documentation SQL Server documentation.](/sql/sql-server/)
    
L’augmentation de la charge pour l’archivage peut être significative. Par conséquent, vous devez vous assurer que l’espace disque est suffisant pour les serveurs frontux sur lesquels l’archivage est activé.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL miroir, SQL clustering et SQL Always On

Vous pouvez utiliser la mise en SQL ou SQL clustering avec Skype Entreprise Server 2015, elle est prise en charge. SQL la mise en miroir est définie par le biais Skype Entreprise Server générateur de topologies. Si vous avez l’intention de SQL clustering de clustering, cette configuration est effectuée SQL Server.
  
Assurez-vous que vous avez une configuration active/passive pour SQL clustering, car c’est ce qui est pris en charge. Ne partagez pas le nœud passif avec d’autres SQL instance.
  
Vous pouvez avoir les conseils suivants pour le clustering deover :
  
Deux nœuds :
  
- Microsoft SQL Server 2019 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

- Microsoft SQL Server 2017 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

- Microsoft SQL Server 2016 Standard (édition 64 bits) avec Service Pack 1 ou version ultérieure. Nous vous recommandons d’être en cours d’exécution avec le dernier Service Pack.

- Microsoft SQL Server 2014 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.
    
-  Microsoft SQL Server 2012 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

Seize nœuds :

- Microsoft SQL Server 2019 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

- Microsoft SQL Server 2017 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

- Microsoft SQL Server 2016 Enterprise (édition 64 bits) avec Service Pack 1 ou version ultérieure. Nous vous recommandons d’être en cours d’exécution avec le dernier Service Pack.
  
- Microsoft SQL Server 2014 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.
    
- Microsoft SQL Server 2012 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

> [!IMPORTANT]
> Pour la mise à niveau, nous voulons vous assurer que vous avez installé au moins SQL Server 2012 SP1 sur vos serveurs frontux avant la mise à niveau. [Voici un lien vers](https://www.microsoft.com/download/details.aspx?id=35575) SP1 si vous souhaitez le télécharger immédiatement.
  
Si vous avez besoin d’en savoir plus sur SQL miroir, nous avons une haute disponibilité de serveur principal dans Skype Entreprise Server 2015. Configurez SQL Server clustering pour Skype Entreprise Server 2015 dispose des étapes nécessaires pour préparer le clustering. Il existe également d’autres liens sur le clustering de SQL, pour [2014](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation), [2012](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110)) et [2008](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)).
  
> [!NOTE]
> La prise en charge de SQL Always On est une nouveauté de la version 2015. Il est pris en charge et vous pouvez en savoir plus à ce sujet dans la haute disponibilité du serveur principal [dans Skype Entreprise Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

> [!NOTE]
> SQL miroir est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de cluster de SQL AlwaysOn et les méthodes de clustering de SQL sont préférés avec Skype Entreprise Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Logiciel à installer avant un déploiement Skype Entreprise Server 2015
<a name="Software"> </a>

Vous devrez installer ou configurer certains éléments pour n’importe quel serveur exécutant Skype Entreprise Server 2015, et ils sont répertoriés ci-dessous. Les autres conditions requises pour des rôles serveur spécifiques sont ensuite requises.

  
 **Tous les serveurs :**
  
|Logiciel/Rôle|Détails|
|:-----|:-----|
|Windows PowerShell 3.0   |Tous Skype Entreprise Server serveurs doivent Windows PowerShell 3.0.  <br/> • Si vous faites l’installation sur Windows Server 2012 ou Windows Server 2012 R2, vous êtes prêt, car il est déjà là.  <br/> • Si vous faites une mise à niveau sur Windows Server 2008 R2, vous pouvez télécharger Windows Management Framework [3.0](https://www.microsoft.com/download/details.aspx?id=34595) pour l’obtenir. <br/> **Conseil :** Une fois que vous avez le powerShell correct sur celui-ci, confirmez qu’il s’agit de BuildVersion 6.2.9200.0 ou version ultérieure en allant à l’invite PowerShell et en tapant `$PSVersionTable`. Les informations dont vous avez besoin doivent alors s’en trouver.   |
|Microsoft .NET Framework   |Les services WCF **sont une fonctionnalité** installée en tant que fonctionnalité Windows, sous **Le Gestionnaire de** serveur, aucun téléchargement n’est nécessaire. <br/> • Vous devez vous assurer, lorsque vous installez cette fonctionnalité, ou si elle est déjà installée et que vous la vérifiez, que l’option **d’activation HTTP** est également cochée et installée, comme suit : <br/> ![Screenshot showing HTTP Activation option under the .NET Framework 4.5 Features.](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Ne vous inquiétez pas si vous obtenez une fenêtre vidéo supplémentaire vous disant que d’autres éléments doivent être installés pour que l’activation HTTP soit installée. C’est normal, cliquez sur OK et allez de l’avant. Si vous n’obtenez pas cette fenêtre pop-up, supposons que ces éléments sont déjà installés et que vous allez de l’avant.  <br/> Microsoft .NET Framework est généralement installé lorsque Windows Server 2012 R2 ou Windows Server 2016 sont installés. Skype Entreprise Server fonctionne avec les versions microsoft .NET Framework suivantes :  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (pour les Skype Entreprise Server cu 5 ou ultérieures)  <br/> • .NET 4.7.2 (pour les Skype Entreprise Server cu 6 ou ultérieures)  <br/>  • .NET 4.8 (pour les Skype Entreprise Server cu 9 ou ultérieures) <br/>  .NET Framework 3.5 sera probablement installé par défaut sur votre ordinateur Windows Server 2008 R2 (assurez-vous de vous en assurer avant la mise à niveau), mais il ne se trouvera pas sur vos serveurs Windows Server 2012/Windows Server 2012 R2 (pour les nouvelles installations). Pour l’ajouter, vous devez accéder à votre lecteur d’installation ou support (l’emplacement d’installation de votre serveur Windows ou l’emplacement d’installation des fichiers). Ensuite, installez-le en tant que fonctionnalité à partir du Gestionnaire de serveur, pointez sur le support d’installation (en particulier le dossier **\sources\sxs** ) lorsque vous l’avez demandé, puis continuez à l’installer.  |
|Media Foundation   |Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2, le runtime Windows format multimédia est installé avec Microsoft Media Foundation.  <br/> Tous les serveurs frontaux et serveurs Édition Standard utilisés pour les conférences nécessitent le runtime du format multimédia Windows pour exécuter les fichiers Windows Media Audio (.wma) lés par les applications Parcage d’appel, Annonce et Response Group pour les annonces et la musique.   |
|Windows Identity Foundation  <br/> |Nous devons Windows Identity Foundation 3.5 pour prendre en charge les scénarios d’authentification de serveur à serveur pour Skype Entreprise Server 2015.  <br/> • Pour Windows Server 2012 et Windows Server 2012 R2, il n’est pas nécessaire de télécharger quoi que ce soit. **Ouvrez le Gestionnaire de** serveur et allez à **l’Assistant Ajout de rôles et de fonctionnalités**. **Windows Identity Foundation 3.5** est répertorié dans la section **Fonctionnalités**. Si elle est vérifiée, vous êtes bon. Sinon, sélectionnez-le et cliquez sur Suivant pour accéder au **bouton** Installer.  |
|Outils d'administration de serveur distant   |Outils d’administration des rôles : outils AD DS et AD LDS   |
   
 **Les serveurs frontux et Édition Standard serveur frontal ont également besoin des ressources nécessaires :**
  
|Logiciel/Rôle|Détails|
|:-----|:-----|
|Internet Information Services (IIS)   |IIS est nécessaire sur tous les serveurs frontaux, ainsi que tous les serveurs Édition Standard, avec les modules suivants sélectionnés :  <br/> • Fonctionnalités HTTP courantes : document par défaut, erreurs HTTP, contenu statique  <br/> • Santé et diagnostics : journalisation HTTP, outils de journalisation, suivi  <br/> • Performances : compression de contenu statique, compression de contenu dynamique  <br/> • Sécurité : filtrage des demandes, authentification par mappage de certificat client, authentification Windows client  <br/> • Développement d’applications : extensibilité .NET 3.5, extensibilité .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, extensions ISAPI, filtres ISAPI  <br/> • Outils de gestion : console de gestion IIS, scripts et outils de gestion IIS  <br/> Nous devons également noter que l’accès anonyme est également nécessaire, mais lorsque vous installez IIS, vous n’avez donc pas d’endroit pour le sélectionner dans la liste.   |
|Module d’exécution du format Windows Media   | Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2, vous devez installer la fonctionnalité **Media Foundation** dans le **Gestionnaire de serveur**. Maintenant, vous pouvez démarrer votre installation Skype Entreprise Server 2015 sans celle-ci, mais vous serez invité à l’installer, puis redémarrez le serveur, avant de poursuivre l’installation de Skype Entreprise Server 2015. Il est préférable de le faire à l’avance.  |
|Silverlight   |Vous pouvez installer la dernière version de Silverlight sur [ce lien](https://www.microsoft.com/silverlight/).   |
   
> [!NOTE] 
> Vous devrez peut-être également activer la navigation dans l’annuaire si vous utilisez un équilibrage de charge. Dans le cas contraire, une page vide se charge, que l’équilibreur de charge peut considérer comme un échec. 

Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser ceci :

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> La commande recherche les fichiers sources dans un ordre spécifique. Si vous êtes en ligne, la commande accède à Windows Update. Toutefois, si vous êtes hors connexion, vous devez vous assurer que les fichiers sources sont disponibles pour la commande. Pour plus d’informations sur l’utilisation de PowerShell pour installer des rôles et des fonctionnalités, voir Installer ou [désinstaller](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) des rôles, des services de rôles ou des fonctionnalités N’oubliez pas d’exécuter Windows Update à nouveau après avoir installé les éléments prérequis, même si vous utilisez la commande PowerShell.

 **Les directeurs doivent également :**
  
IIS, avec les modules suivants sélectionnés :
  
- Fonctionnalités HTTP courantes
    
  - Document par défaut
    
  - Erreurs HTTP
    
  - Contenu statique
    
- État de santé et diagnostics
    
  - Journalisation HTTP
    
  - Outils de journalisation
    
  - Suivi
    
- Performances
    
  - Compression de contenu statique
    
- Sécurité
    
  - Filtrage des demandes
    
  - Authentification par mappage de certificat client
    
  - Authentification Windows
    
- Développement d’applications
    
  - Extensibilité .NET 3.5
    
  - Extensibilité .NET 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI Extension
    
  - Filtres ISAPI
    
(Si vous vous demandez, il s’agit du même module que les serveurs frontaux et les serveurs Édition Standard, avec les outils de compression et de gestion de contenu dynamiques laissés de côté.)
  
Et nous avons également du code PowerShell ci-dessous pour cela :
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Les serveurs de conversation permanente ont également besoin des :**
  
Message Queuing, également appelé MSMQ. Il s’agit d’Windows Server et vous pouvez l’installer dans la section Fonctionnalités du Gestionnaire de serveur. Si vous souhaitez en savoir plus à ce sujet, consultez [l’installation et la gestion de Message Queuing](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11)).
  
 **Dernières idées :**
  
N’installez aucun logiciel client Microsoft Internet Security and Acceleration (ISA) Server, ni aucun autre logiciel Winsock Layered Service Providers (LSP) (n’importe quel pare-feu tiers ou logiciel d’inspection du réseau antivirus serait inclus ici) sur vos serveurs frontaux ou serveurs de médiation autonomes. Des performances médiocres du trafic multimédia ont été vues lors de l’installation de ce logiciel.
