---
title: Configuration serveur requise pour Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Résumé: Préparez vos serveurs Skype entreprise Server 2015 à ce sujet. Matériel, système d’exploitation, bases de données, logiciels, toutes les exigences système et recommandations sont disponibles pour garantir la réussite de l’installation et du déploiement de votre batterie de serveurs.'
ms.openlocfilehash: 368c719ac4e61b62ab4c52c50433bf6cc996c886
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2019
ms.locfileid: "35758948"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Server requirements for Skype for Business Server 2015
 
**Résumé :** préparez vos serveurs Skype Entreprise Server 2015 grâce à cette rubrique. Le matériel, le système d’exploitation, les bases de données, les logiciels, toute la configuration système requise et les recommandations se trouvent ici afin de vous permettre de réussir l’installation et le déploiement de votre batterie de serveurs.

Si vous recherchez des informations sur la configuration de l’environnement (par exemple, Active Directory, DNS ou certificats), vous pouvez consulter la [configuration environnementale requise pour le document 2015 de Skype entreprise Server](environmental-requirements.md) .
  
Comme vous pouvez le constater, il est possible que vous deviez apporter certaines préparations avant de commencer le déploiement de Skype entreprise Server 2015. Cet article vous guide à travers la procédure de planification comme suit :
  
- [ChiffremMatériel pour Skype Entreprise Server 2015](server-requirements.md#Hardware)
  
- [Systèmes d’exploitation pour Skype entreprise Server 2015](server-requirements.md#OS)
  
- [Bases de données principales compatibles avec Skype Entreprise Server 2015](server-requirements.md#DBs)
  
- [Logiciel à installer avant de procéder à un déploiement de Skype Entreprise Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>ChiffremMatériel pour Skype Entreprise Server 2015
<a name="Hardware"> </a>

Maintenant que vous disposez de votre topologie (et si ce n’est pas le cas, vous pouvez consulter la section [notions de base pour Skype entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), il est temps de réfléchir aux serveurs. Les serveurs 2015 de Skype entreprise Server nécessitent un matériel 64 bits. Nos recommandations pour le matériel sont indiquées ci-dessous. Ces conditions ne sont pas obligatoires, mais elles reflètent les exigences nécessaires aux performances optimales. La documentation de planification des capacités vous aidera à déterminer si vous avez besoin de capacités supérieures, en fonction des circonstances.
  
Configuration matérielle recommandée pour serveurs frontaux, serveurs dorsaux, serveurs Standard Edition et serveurs de chat permanent:
  
|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles 2015 de Skype entreprise Server.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 lecteurs de disque dur, ou plus de 10000, avec au moins 72 Go d’espace libre sur le disque dur (deux des disques avec RAID 1 et 6 avec RAID 10).  <br/> OU  <br/> • Lecteurs d’État SSD (SSDs) en mesure d’offrir un espace libre et des performances similaires pour les disques mécaniques 8 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations à double ou à hébergement multiple ne sont **pas** prises en charge pour les serveurs frontaux, serveurs dorsaux, serveurs Standard Edition et serveurs de chat permanent. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et qu’ils sont utilisés pour la surveillance et la gestion du matériel des serveurs, vous pouvez utiliser des systèmes de gestion hors-bande tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.<br/> |
   
Matériel recommandé pour les serveurs Edge, serveurs de médiation autonomes, serveurs d’interopérabilité et directeurs:
  
|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Biprocesseur 64 bits, quatre cœurs, 2,26 GHz ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles 2015 de Skype entreprise Server.  <br/> |
|Mémoire  <br/> |16 giga-octets.  <br/> |
|Disque  <br/> |SOIT :  <br/> • 4 disques durs de 4 Mo ou plus 10000 avec au moins 72 Go d’espace libre sur le disque (les disques doivent être dans une configuration RAID 1 2x).  <br/> OU  <br/> • Lecteurs d’État SSD (SSDs) en mesure d’offrir un espace libre et des performances similaires pour les disques mécaniques 4 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations à double ou à hébergement multiple ne sont **pas** prises en charge pour les serveurs et les directeurs d’interopérabilité vidéo. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau double port, 1 Gbit/s ou plus (ou deux cartes réseau appariées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et à une adresse IP unique, pour un total de deux paires).  <br/> Sur les serveurs de médiation autonomes, l’installation de cartes d’interface réseau supplémentaires est prise en charge.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Systèmes d’exploitation pour Skype entreprise Server 2015
<a name="OS"> </a>

Lorsque le matériel est en place, vous devez installer des systèmes d’exploitation. Il s’agit du système d’exploitation qui vous permet d’installer et d’utiliser correctement Skype entreprise Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (vous devez disposer de la mise à jour cumulative 9 pour Skype entreprise 9 ou version ultérieure). <br/> |Windows Server 2016 (vous devez disposer de la mise à jour cumulative de Skype entreprise 5 ou version ultérieure). Pour plus d’informations, consultez [KB4015888](https://support.microsoft.com/en-gb/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Système d’exploitation Windows Server 2012 R2 Datacenter avec toutes les mises à jour requises installées.  <br/> |Système d’exploitation Windows Server 2012 R2 Standard avec toutes les mises à jour requises installées.  <br/> |
|Système d’exploitation Windows Server 2012 Datacenter avec toutes les mises à jour requises installées.  <br/> |Système d’exploitation Windows Server 2012 standard avec toutes les mises à jour requises installées.  <br/> |
   
S’il ne figure pas dans cette liste, cela ne fonctionne pas correctement, veuillez ne pas essayer pour les nouvelles installations de Skype entreprise Server 2015.
  
> [!NOTE]
> Il est possible que vous ayez remarqué que Windows Server 2008 R2 ne figure pas dans cette liste. C’est pourquoi nous recommandons Windows Server 2012 R2 pour que tous les nouveaux serveurs soient utilisés pour marketing. Vous devez utiliser Windows Server 2008 R2 uniquement si vous avez des serveurs déjà installés avec Lync Server 2013 et que vous envisagez d’effectuer une mise à niveau sur place de celles-ci. Windows Server 2008 R2 a atteint la fin de la durée de vie du support technique standard sur 1/13/2015 et atteint la fin de son support technique sur 1/14/2020.
  
En plus du dernier Service Pack, vérifiez que les mises à jour suivantes sont installées le cas échéant :
  
- Pour Windows Server 2012, l’article de la Base des connaissances 2858668 doit être installé avant toute mise à niveau. [Téléchargez-le ici](https://support.microsoft.com/en-us/kb/2858668/).
    
- Si vous disposez de Windows Server 2012 R2, installez l’article de la Base des connaissances 2982006 avant toute mise à niveau. [Il est disponible ici](https://support.microsoft.com/en-us/kb/2982006/).
    
- Si vous effectuez une mise à niveau sur une boîte Windows Server 2008 R2 (voir la Note ci-dessus), vous devez alors installer d’abord l’article de la Base des connaissances 2533623. C' [est sur ce lien](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de données principales compatibles avec Skype Entreprise Server 2015
<a name="DBs"> </a>

Lors de l’installation de Skype entreprise Server 2015 Standard Edition, SQL Server 2014 Express (64-bit Edition) est automatiquement installé.
  
Skype entreprise Server 2015 Enterprise Edition est un peu plus compliqué, mais la liste prise en charge est ci-dessous (tout est une édition 64 bits, vous remarquerez qu’il n’est pas possible d’utiliser des éditions 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack. <br/> |Microsoft SQL Server 2017 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack. <br/> |Microsoft SQL Server 2016 entreprise (64-bit Edition) avec Service Pack 1 ou version ultérieure, et vous devez l’exécuter avec la mise à jour cumulative Skype entreprise 7 ou une version ultérieure ([Télécharger la mise à jour cumulative Skype entreprise](https://support.microsoft.com/en-us/help/3061064)).  <br/> |Microsoft SQL Server 2014 entreprise (64-bit Edition) et vous devez exécuter la mise à jour cumulative 6 ou une version ultérieure ([Télécharger la mise à jour cumulative 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.  <br/> |
|Microsoft SQL Server 2019 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack. <br/> |Microsoft SQL Server 2017 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack. <br/> |Microsoft SQL Server 2016 standard (64-bit Edition) avec Service Pack 1 ou version ultérieure, et vous devez l’exécuter avec la mise à jour cumulative Skype entreprise 7 ou une version ultérieure ([Télécharger la mise à jour cumulative Skype entreprise](https://support.microsoft.com/en-us/help/3061064)).  <br/> |Microsoft SQL Server 2014 standard (64-bit Edition) et vous devez exécuter la mise à jour cumulative 6 ou une version ultérieure ([Télécharger la mise à jour cumulative 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.  <br/> |
   
Si vous ne voyez pas l’édition SQL Server que vous voulez utiliser dans la liste, vous ne pouvez pas l’utiliser.
  
> [!NOTE]
> Vous devez également installer SQL Server Reporting Services pour le rôle serveur de surveillance.

### <a name="microsoft-exchange-storage"></a>Stockage Microsoft Exchange
Meeting content files, such as PowerPoint presentations, are archived as attachments. Si vous voulez stocker les données d’archive Skype entreprise avec des données de conformité Exchange, vous devez utiliser Exchange pour votre déploiement Exchange et garantir que la taille de stockage maximale prend en charge le stockage des fichiers de contenu de la réunion. Vous devez déployer Exchange avant de déployer et d’activer l’archivage à l’aide de l’option d’intégration de Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Configuration logicielle et matérielle requise pour l’archivage dans Skype Entreprise Server 2015
  
L’archivage n’est pas un rôle de serveur défini, vous n’avez pas besoin d’installer un serveur distinct pour l’archivage. Les agents de collection de données unifiées sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et chaque serveur Standard Edition Server. Vous devrez activer et publier votre topologie d’archivage en utilisant le générateur de topologie.
    
L’archivage utilise le stockage de fichiers Skype entreprise Server pour stocker temporairement les fichiers de contenu de la réunion, de sorte que vous n’avez pas configuré de magasin de fichiers distinct pour l’archivage.
    
Microsoft Message Queuing n’est pas requis.
    
Vous devez configurer l’infrastructure d’archivage des données. Pour cela, vous devez choisir le stockage Exchange ou d’archivage à l’aide de SQL Server.   Les exigences d’infrastructure d’archivage de Skype entreprise Server sont les mêmes que pour le déploiement de Skype entreprise Server. Pour plus d’informations, reportez-vous [à la configuration requise pour votre environnement Skype entreprise](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Pour prendre en charge les utilisateurs qui ne sont pas hébergés sur des serveurs Exchange, ou si vous ne voulez pas utiliser l’option d’intégration de Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server 64 bits. 
    
Vous devez configurer les plates-formes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, voir la [documentation SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
L’augmentation de la charge pour cause d’archivage peut être importante. Par conséquent, vous devez vous assurer que l’espace disque est approprié pour les serveurs frontaux sur lesquels l’archivage est activé.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Mise en miroir SQL, mise en cluster SQL et SQL Always On

Vous pouvez utiliser la mise en miroir SQL ou la mise en cluster SQL avec Skype entreprise Server 2015. La mise en miroir SQL est configurée par le biais du générateur de topologie Skype entreprise Server. Si vous n’avez pas besoin de configurer le regroupement SQL, c’est le cas dans SQL Server.
  
Vérifiez que vous disposez d’une configuration active/passive pour le regroupement SQL, comme il est pris en charge. Ne partagez pas le nœud passif avec d’autres instances SQL.
  
Vous pouvez avoir ce qui suit pour la mise en cluster du basculement :
  
Deux nœuds :
  
- Microsoft SQL Server 2019 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

- Microsoft SQL Server 2017 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

- Microsoft SQL Server 2016 standard (64-bit Edition) avec Service Pack 1 ou version ultérieure. Nous vous recommandons d’utiliser le dernier Service Pack.

- Microsoft SQL Server 2014 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.
    
-  Microsoft SQL Server 2012 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

Six nœuds :

- Microsoft SQL Server 2019 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

- Microsoft SQL Server 2017 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

- Microsoft SQL Server 2016 entreprise (64-bit Edition) avec Service Pack 1 ou version ultérieure. Nous vous recommandons d’utiliser le dernier Service Pack.
  
- Microsoft SQL Server 2014 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.
    
- Microsoft SQL Server 2012 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

> [!IMPORTANT]
> Pour procéder à la mise à niveau, nous vous conseillons de veiller à ce que SQL Server 2012 SP1 soit installé sur votre serveur frontal avant la mise à niveau. Vous [trouverez ci-dessous un lien](https://www.microsoft.com/en-us/download/details.aspx?id=35575) vers SP1 si vous voulez le télécharger immédiatement.
  
Pour plus d’informations sur la mise en miroir SQL, voir disponibilité du serveur principal dans Skype entreprise Server 2015 sujet. Configurer la gestion des clusters SQL Server pour Skype entreprise Server 2015 comporte les étapes nécessaires pour préparer le regroupement. Il existe également d’autres liens sur la mise en cluster de basculement pour SQL, pour [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)et [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Nouveauté de la version 2015, l’assistance de SQL est toujours activée. Cette prise en charge est prise en charge et vous pouvez en savoir plus à ce propos dans la section [disponibilité du serveur principal de Skype entreprise server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> La mise en miroir SQL est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. Les groupes de disponibilité AlwaysOn, les instances de clusters de basculement AlwaysOn (ICF) et les méthodes de regroupement de relais SQL sont préférés dans Skype entreprise Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Logiciel à installer avant de procéder à un déploiement de Skype Entreprise Server 2015
<a name="Software"> </a>

Vous devrez peut-être installer ou configurer certains éléments pour n’importe quel serveur exécutant Skype entreprise Server 2015, qui apparaît ci-dessous. Après cela, vous devez disposer d’exigences supplémentaires pour des rôles de serveur spécifiques.
  
 **Tous les serveurs :**
  
|**Logiciel/Rôle**|**Détails**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tous les serveurs Skype entreprise Server requièrent l’installation de Windows PowerShell 3,0.  <br/> • Si vous procédez à l’installation sur Windows Server 2012 ou Windows Server 2012 R2, c’est que vous êtes déjà en train de procéder.  <br/> • Si vous effectuez une mise à niveau de Windows Server 2008 R2, vous pouvez télécharger le [Windows Management Framework 3,0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) pour l’obtenir. <br/> **Astuce:** Une fois que vous disposez de la version PowerShell correcte, vérifiez qu’elle est BuildVersion 6.2.9200.0 ou une version ultérieure en accédant à `$PSVersionTable`l’invite PowerShell et en tapant. Vous devriez alors obtenir les informations voulues.  <br/> |
|Microsoft .NET Framework  <br/> |Services WCF est une **fonctionnalité** qui est installée en tant que fonctionnalité Windows, dans le **Gestionnaire de serveur**, aucun téléchargement n’est nécessaire. <br/> • Vous devez vous assurer que, lorsque vous installez cette fonction ou qu’elle est déjà installée et que vous la Vérifiez, l’option d' **activation http** est également activée et installée, comme suit: <br/> ![Capture d’écran montrant l’option d’activation HTTP dans les fonctionnalités .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Ne vous inquiétez pas si vous obtenez une fenêtre contextuelle supplémentaire indiquant que d’autres éléments doivent être installés pour que l’activation http soit installée. C’est normal ; cliquez sur OK et poursuivez. Si vous n’obtenez pas cette fenêtre contextuelle, vous pouvez alors supposer que ces éléments sont déjà installés, et poursuivre.  <br/> Microsoft .NET Framework est généralement installé lorsque Windows Server 2012 R2 ou Windows Server 2016 est installé. Skype entreprise Server fonctionne avec les versions Microsoft .NET Framework suivantes:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 et versions ultérieures (pour Skype entreprise Server en cuivre 5 ou versions ultérieures)  <br/>  .NET Framework 3,5 est susceptible d’être installé par défaut sur votre ordinateur Windows Server 2008 R2 (vérifier clairement avant la mise à niveau), mais il ne se trouve pas sur les serveurs Windows Server 2012/Windows Server 2012 R2 (pour les nouvelles installations). Pour l’ajouter, vous devez disposer d’un accès à votre lecteur d’installation ou à votre média (sur lequel votre serveur Windows a été installé, ou à l’endroit où se trouvent les fichiers d’installation). Ensuite, vous pouvez l’installer en tant que fonctionnalité du gestionnaire de serveur, puis pointez sur le support d’installation (en particulier, le dossier **\sources\sxs** ) lorsque vous y êtes invité, et continuez à l’installer. <br/> |
|Media Foundation  <br/> |Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2 installations du runtime du format Windows Media avec Microsoft Media Foundation.  <br/> Tous les serveurs front-end et les serveurs Standard Edition utilisés pour les conférences requièrent l’exécution du format Windows Media Runtime pour exécuter les fichiers Windows Media audio (. WMA) que les applications de parc d’appels, d’annonce et de groupe de réponse sont lues pour les annonces et la musique.  <br/> |
|Windows Identity Foundation  <br/> |Nous avons besoin de Windows Identity Foundation 3,5 pour prendre en charge les scénarios d’authentification de serveur à serveur pour Skype entreprise Server 2015.  <br/> • Pour Windows Server 2012 et Windows Server 2012 R2, vous n’avez rien à télécharger. Ouvrez le **Gestionnaire de serveur** et accédez à l’**Assistant Ajout de rôles et de fonctionnalités**. **Windows Identity Foundation 3.5** est listé sous la section **Fonctionnalités**. Si ce n’est déjà fait, c’est bon. Sinon, sélectionnez-le et cliquez sur Suivant pour accéder au bouton **Installer**. <br/> |
|Outils d’administration de serveur distant  <br/> |Outils d’administration de rôles : outils AD DS et AD LDS  <br/> |
   
 **Les serveurs front-end et Standard Edition Server ont également besoin des éléments suivants:**
  
|**Logiciel/Rôle**|**Détails**|
|:-----|:-----|
|services Internet (IIS)  <br/> |IIS est requis sur tous les serveurs frontaux, ainsi que sur tous les serveurs Standard Edition, avec les modules suivants sélectionnés:  <br/> • Principales fonctionnalités HTTP: document par défaut, erreurs HTTP, contenu statique  <br/> • Santé et diagnostics: journalisation HTTP, outils de journalisation, suivi  <br/> • Performances: compression de contenu statique, compression de contenu dynamique  <br/> • Sécurité: filtrage des demandes, authentification du mappage de certificat client, authentification Windows  <br/> • Développement d’applications: extensibilité .NET 3,5, extensibilité .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensions ISAPI et filtres ISAPI  <br/> • Outils de gestion: console de gestion IIS, scripts et outils de gestion IIS  <br/> Notez également que l’accès anonyme est également nécessaire, mais que vous l’obtenez lorsque vous installez IIS, de sorte que vous n’avez pas d’emplacement pour le sélectionner dans la liste.  <br/> |
|Module d’exécution du format Windows Media  <br/> | Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2, vous devez installer la fonctionnalité **Media Foundation** dans le gestionnaire de **serveur**. Vous pouvez à présent démarrer votre installation de Skype entreprise Server 2015 sans celle-ci, mais vous serez invité à l’installer, puis à redémarrer le serveur, avant la poursuite de l’installation de Skype entreprise Server 2015. Il vaut donc mieux l’installer au préalable. <br/> |
|Silverlight  <br/> |Vous pouvez installer la dernière version de Silverlight sur [ce lien](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Vous pouvez également activer la navigation dans l’annuaire si vous utilisez un équilibreur de charge. Dans le cas contraire, une page vierge se chargera de l’échec de l’équilibrage de charge. 

Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser ceci :

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> La commande recherche les fichiers sources dans un ordre spécifique. Si vous êtes connecté à internet, la commande aura accès à Windows Update. Si vous n’êtes pas connecté à internet, vous devrez vous assurer que les fichiers source sont accessibles à la commande. Pour plus d’informations sur l’utilisation de PowerShell pour installer des rôles et des fonctionnalités, voir [installer ou désinstaller des rôles, services de rôle ou fonctionnalités](https://technet.microsoft.com/en-us/library/hh831809.aspx) n’oubliez pas d’exécuter de nouveau Windows Update après l’installation des éléments requis, même si vous utilisez la commande PowerShell.

 **Les directeurs ont également besoin des éléments suivants:**
  
IIS, avec les modules suivants sélectionnés :
  
- Fonctionnalités HTTP communes
    
  - Document par défaut
    
  - Erreurs HTTP
    
  - Contenu statique
    
- Intégrité et diagnostics
    
  - Journalisation HTTP
    
  - Outils de journalisation
    
  - Suivi
    
- Performances
    
  - Compression du contenu statique
    
- Sécurité
    
  - Filtrage des demandes
    
  - Authentification par mappage de certificat client
    
  - Authentification Windows
    
- Développement d’applications
    
  - .NET Extensibility 3.5
    
  - .NET Extensibility 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - Extensions ISAPI
    
  - Filtres ISAPI
    
(Si vous vous demandez cela, il s’agit du même module que les serveurs frontaux et les serveurs Standard Edition, avec les outils de compression et de gestion des contenus dynamiques conservés.)
  
Vous trouverez aussi du code PowerShell ci-dessous :
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Les serveurs de chat permanent ont également besoin des éléments suivants:**
  
Message Queuing, appelé aussi MSMQ. Il s’agit d’un composant Windows Server que vous pouvez installer dans la section fonctionnalités du gestionnaire de serveur. Pour en savoir plus, consultez [l’article installation et gestion de Message Queuing](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Dernières pensées :**
  
N’installez pas le logiciel client Microsoft Internet Security and Acceleration (ISA) Server ou tout autre logiciel de fournisseurs de services Layers (Winsock Layerd services), ou un logiciel de contrôle de réseau antiviral (ou logiciel antivirus), sur tout serveur principal ou serveur de médiation autonome. Des performances de trafic multimédia médiocres ont été constatées lors de l’installation de ces logiciels.
  

