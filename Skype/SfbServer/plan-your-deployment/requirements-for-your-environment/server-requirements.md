---
title: Configuration serveur requise pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Résumé : Préparez votre Skype pour les serveurs Business Server 2015 avec cette rubrique. Matériel, système d’exploitation, bases de données, logiciel, tous les la configuration système requise et les recommandations sont ici afin de garantir une installation réussie et le déploiement de votre batterie de serveurs.'
ms.openlocfilehash: 28e9cf9be6f52a5e7f35a2d958832b1f13ada3b0
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Configuration serveur requise pour Skype Entreprise Server 2015
 
**Résumé :** préparez vos serveurs Skype Entreprise Server 2015 grâce à cette rubrique. Le matériel, le système d’exploitation, les bases de données, les logiciels, toute la configuration système requise et les recommandations se trouvent ici afin de vous permettre de réussir l’installation et le déploiement de votre batterie de serveurs.
  
Comme vous pouvez le supposer, il existe certaines préparations à effectuer avant de commencer le déploiement de Skype pour Business Server 2015. Cet article vous guide à travers la procédure de planification comme suit :
  
- [ChiffremMatériel pour Skype Entreprise Server 2015](server-requirements.md#Hardware)
  
- [Systèmes d’exploitation pour Skype pour Business Server 2015](server-requirements.md#OS)
  
- [Bases de données principales compatibles avec Skype Entreprise Server 2015](server-requirements.md#DBs)
  
- [Logiciel à installer avant de procéder à un déploiement de Skype Entreprise Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>ChiffremMatériel pour Skype Entreprise Server 2015
<a name="Hardware"> </a>

Maintenant que vous avez votre topologie vers le bas (et si vous n’avez pas, vous pouvez consulter la rubrique [Concepts de base de topologie pour Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), il est temps de penser aux serveurs. Skype pour les serveurs Business Server 2015 nécessiteront le matériel 64 bits. Nos recommandations pour le matériel sont indiquées ci-dessous. Il n’est pas requise, mais ils reflètent les conditions requises pour des performances optimales. La documentation de planification des capacités vous aidera à déterminer si vous avez besoin de capacités supérieures, en fonction des circonstances.
  
Matériel recommandé pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition Server et serveurs de conversation permanente :
  
|**Composant matériel**|**Recommandé**|
|:-----|:-----|
|Processeur  <br/> |Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour les rôles Business Server 2015.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • Au moins 8 disques durs de 10 000 tr/min avec au moins 72 Go d’espace disque disponible (deux de ces disques utilisant RAID 1 et six autres utilisant RAID 10).   <br/> SOIT  <br/> •	Des disques SSD (Solid State Drives) pouvant fournir le même espace libre et des performances similaires aux 8 unités de disques mécaniques de 10 000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Configurations de doubles ou multi-hébergés sont pris en charge **pas** pour les serveurs frontaux, serveurs principaux, Standard Edition, les serveurs et les serveurs de conversation permanente. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et qu’ils sont utilisés pour la surveillance et la gestion du matériel des serveurs, vous pouvez utiliser des systèmes de gestion hors-bande tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.<br/> |
   
Matériel recommandé pour les serveurs de périphérie, serveurs de médiation autonomes, serveurs d’interopérabilité vidéo et les directeurs :
  
|**Composant matériel**|**Recommandé**|
|:-----|:-----|
|Processeur  <br/> |Biprocesseur 64 bits, quatre cœurs, 2,26 GHz ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour les rôles Business Server 2015.  <br/> |
|Mémoire  <br/> |16 giga-octets.  <br/> |
|Disque  <br/> |SOIT :  <br/> • Au moins 4 disques durs de 10 000 tr/min avec au moins 72 Go d’espace disque disponible (les disques doivent avoir une configuration 2x RAID 1).  <br/> SOIT  <br/> •	Des disques SSD (Solid State Drives) pouvant fournir le même espace libre et des performances similaires aux 4 unités de disques mécaniques de 10 000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Configurations doubles ou multi-hébergés sont **pas** pris en charge pour les serveurs d’interopérabilité vidéo et les directeurs. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau double port, 1 Gbit/s ou plus (ou deux cartes réseau appariées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et à une adresse IP unique, pour un total de deux paires).  <br/> Serveurs de médiation l’installation de cartes d’interface réseau supplémentaire (NIC) pour autoriser la configuration d’une adresse IP PSTN spécifique est pris en charge sur autonome.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Systèmes d’exploitation pour Skype pour Business Server 2015
<a name="OS"> </a>

Une fois que le matériel en place, vous devez installer les systèmes d’exploitation (OS). Il s’agit du système d’exploitation qui vous permet d’installer et utiliser correctement Skype pour Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 R2 Datacenter OS avec toutes les mises à jour installées.  <br/> |Windows Server 2012 R2 Standard OS avec toutes les mises à jour installées.  <br/> |
|Windows Server 2012 Datacenter OS avec toutes les mises à jour installées.  <br/> |Windows Server 2012 Standard OS avec toutes les mises à jour installées.  <br/> |
   
Si elle n’est pas sur cette liste, il ne fonctionnera pas correctement, veuillez n’essayez les nouvelles installations de Skype pour Business Server 2015.
  
> [!NOTE]
> Vous avez peut-être remarqué que Windows Server 2008 R2 ne fait pas partie de cette liste, car nous recommandons Windows Server 2012 R2 pour tous les nouveaux serveurs utilisés pour SFB. Vous devez utiliser Windows Server 2008 R2 uniquement lorsque des serveurs existants avec Lync Server 2013 sont déjà installés et que vous envisagez de les mettre à niveau localement. Windows Server 2008 R2 a atteint la fin du cycle de vie du support principal le 13/01/2015. 
  
En plus du dernier Service Pack, vérifiez que les mises à jour suivantes sont installées le cas échéant :
  
- Pour Windows Server 2012, l’article de la Base des connaissances 2858668 doit être installé avant toute mise à niveau. [Obtenir ici](https://support.microsoft.com/en-us/kb/2858668/).
    
- Si vous disposez de Windows Server 2012 R2, installez l’article de la Base des connaissances 2982006 avant toute mise à niveau. [Elle est trouvée](https://support.microsoft.com/en-us/kb/2982006/).
    
- Si vous effectuez une mise à niveau sur une boîte Windows Server 2008 R2 (voir la Note ci-dessus), vous devez alors installer d’abord l’article de la Base des connaissances 2533623. [Il est à ce lien](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bases de données principales compatibles avec Skype Entreprise Server 2015
<a name="DBs"> </a>

Lorsque vous installez Skype pour 2015 Business Server Standard Edition, vous devez aussi SQL Server 2014 Express (Édition 64 bits) est installée automatiquement ainsi.
  
Skype pour Business Server 2015 Enterprise Edition est un peu plus complexe, mais voici la liste pris en charge (tout est Édition 64 bits, vous pouvez le constater, à ne pas utiliser les éditions 32 bits) :
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2014 Enterprise (Édition 64 bits) et que vous devez exécuter avec Cumulative Update 6 ou version ultérieure ([Télécharger 6 de mise à jour Cumulative](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.  <br/> |Microsoft SQL Server 2008 R2 Enterprise (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.  <br/> |
|Microsoft SQL Server 2014 Standard (Édition 64 bits) et que vous devez exécuter avec Cumulative Update 6 ou version ultérieure ([Télécharger 6 de mise à jour Cumulative](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.  <br/> |Microsoft SQL Server 2008 R2 Standard (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent  <br/> |
   
Si vous ne voyez pas l’édition de SQL Server que vous souhaitez utiliser répertoriés ici, vous ne pouvez pas l’utiliser.
  
> [!NOTE]
> Vous aurez également besoin d’installer SQL Server Reporting Services pour le rôle serveur de surveillance, mais nous avons besoin de connaître que ce n’est pas sur le point d’être pris en charge avec SQL toujours sur jusqu'à post-RTM. 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Mise en miroir SQL, mise en cluster SQL et SQL Always On

Vous êtes en mesure d’utiliser la mise en miroir SQL ou SQL Clustering avec Skype pour Business Server 2015, il est pris en charge. SQL la mise en miroir configurer via la Skype pour le Générateur de topologie Business Server. Si vous êtes l’objectif sur la configuration du Clustering SQL, qui est effectuée dans SQL Server.
  
Assurez-vous que vous avez une configuration actif/passif pour la gestion de clusters SQL, comme c’est ce qui est pris en charge. Ne pas partager le nœud passif avec d’autres instances SQL.
  
Vous pouvez avoir ce qui suit pour la mise en cluster du basculement :
  
Deux nœuds :
  
- Microsoft SQL Server 2014 Standard (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
-  Microsoft SQL Server 2012 Standard (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
- Microsoft SQL Server 2008 R2 Standard (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
Six nœuds :
  
- Microsoft SQL Server 2014 Enterprise (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
- Microsoft SQL Server 2012 Enterprise (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
- Microsoft SQL Server 2008 R2 Enterprise (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
> [!IMPORTANT]
> Mise à niveau, nous souhaitez-vous vous assurer que SQL Server 2012 SP1 installé sur vos serveurs frontaux avoir au moins avant la mise à niveau. [Voici un lien](https://www.microsoft.com/en-us/download/details.aspx?id=35575) vers SP1 si vous souhaitez télécharger immédiatement.
  
Si vous avez besoin lire des informations supplémentaires sur la mise en miroir SQL, nous disposons d’une haute disponibilité de serveur principal dans Skype pour la rubrique Business Server 2015. Configurer le clustering SQL Server pour Skype pour Business Server 2015 intègre les étapes pour l’obtention de clustering prêt. Il existe également davantage des liens sur les clusters de basculement pour SQL, pour [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)et [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> La prise en charge de SQL Always On est une nouveauté de cette version. Il est pris en charge, et vous pouvez en savoir plus sur celui-ci dans la rubrique [serveur principal de haute disponibilité dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Logiciel à installer avant de procéder à un déploiement de Skype Entreprise Server 2015
<a name="Software"> </a>

Il existe certaines choses que vous aurez besoin installer ou configurer pour n’importe quel serveur exécutant Skype pour Business Server 2015, et elles sont répertoriées ci-dessous. Après que sont les autres exigences de rôles de serveur spécifiques.
  
 **Tous les serveurs :**
  
|**Rôle/logiciel**|**Détails**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tous les Skype pour les serveurs Business Server devez Windows PowerShell 3.0 est installé.  <br/> • Si vous effectuez l’installation sur Windows Server 2012 ou Windows Server 2012 R2, vous avez défini, car elle est déjà.  <br/> • Si vous effectuez une mise à niveau sur Windows Server 2008 R2, vous pouvez télécharger le [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) pour l’obtenir. <br/> **Conseil :** Une fois le PowerShell correct de là, confirmez qu’il est BuildVersion 6.2.9200.0 ou ultérieurement en accédant à PowerShell demander et en tapant `$PSVersionTable`. Vous devriez alors obtenir les informations voulues.  <br/> |
|Microsoft .NET Framework  <br/> |Les services WCF est une **fonctionnalité** qui n’a installé en tant qu’une fonctionnalité de Windows, sous **Gestionnaire de serveur**, aucun téléchargement nécessaires. <br/> • Vous devez vous assurer, lorsque vous installez cette fonctionnalité, ou si elle est déjà installée et vous vérifiez sur celui-ci, que l’option **d’Activation HTTP** est également activée et installée, comme suit : <br/> ![Capture d’écran montrant l’option d’Activation HTTP sous les fonctionnalités .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Ne vous inquiétez pas si vous obtenez une fenêtre publicitaire intempestive supplémentaire indiquant que les autres éléments doivent être installés pour l’Activation HTTP à installer. C’est normal ; cliquez sur OK et poursuivez. Si vous n’obtenez pas cette fenêtre contextuelle, vous pouvez alors supposer que ces éléments sont déjà installés, et poursuivre.  <br/> Microsoft .NET Framework est installé généralement lorsque Windows Server 2012 R2 ou Windows Server 2016 est installé. Skype pour Business Server fonctionne avec les versions suivantes de Microsoft .NET Framework :  <br/> • .NET 3.5  <br/> • .NET FRAMEWORK 4.5  <br/> • .NET 4.6.x  <br/> • 4.7 .NET (pour Skype pour Business Server mise à jour Cumulative 5 ou versions ultérieures)  <br/>  .NET framework 3.5 sera probablement installé par défaut sur votre ordinateur Windows Server 2008 R2 (sans aucun doute Vérifiez qu’avant la mise à niveau), mais il ne se trouvent pas sur vos serveurs de Windows Server 2012 et Windows Server 2012 R2 (pour les nouvelles installations). Pour l’ajouter dans, vous devez avoir accès à votre média ou le lecteur d’installation (l’emplacement Windows Server a été installé à partir d’ou où les fichiers d’installation sont maintenant). Poursuivez en l'installant en tant que composant du Gestionnaire de serveur. Pointez ensuite vers le support d'installation (à savoir le dossier **\sources\sxs**) à l'invite du système, puis poursuivez l'installation. <br/> |
|Media Foundation  <br/> |Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2 Windows Media Format Runtime installe avec Microsoft Media Foundation.  <br/> Tous les serveurs Standard Edition et les serveurs frontaux utilisés pour la conférence nécessitent Windows Media Format Runtime exécuter les fichiers Audio Windows Media (.wma) apparaissant dans les applications de parcage d’appel et annonce Response Group pour la musique et des annonces.  <br/> |
|Windows Identity Foundation  <br/> |Nous devons Windows Identity Foundation 3.5 pour prendre en charge des scénarios d’authentification de serveur à serveur pour Skype pour Business Server 2015.  <br/> • Pour Windows Server 2012 et Windows Server 2012 R2, il n’est pas nécessaire de télécharger quoi que ce soit. Ouvrez le **Gestionnaire de serveur** et accédez à l’**Assistant Ajout de rôles et de fonctionnalités**. **Windows Identity Foundation 3.5** est listé sous la section **Fonctionnalités**. Si elle est activée, vous êtes. Sinon, sélectionnez-le et cliquez sur Suivant pour accéder au bouton **Installer**. <br/> |
|Outils d’administration de serveur distant  <br/> |Outils d’administration de rôles : outils AD DS et AD LDS  <br/> |
   
 **Serveur frontal de serveurs frontaux et Standard Edition ont également besoin :**
  
|**Rôle/logiciel**|**Détails**|
|:-----|:-----|
|services Internet (IIS)  <br/> |IIS est requis sur tous les serveurs frontaux, ainsi que tous les serveurs Standard Edition, avec les modules suivants sélectionnés :  <br/> Fonctionnalités HTTP communes • : par défaut des documents, des erreurs HTTP, le contenu statique  <br/> • Santé et Diagnostics : HTTP de journalisation, les outils de journalisation de suivi  <br/> • Les performances : Compression de contenu statique, Compression de contenu dynamique  <br/> • Sécurité : filtrage des demandes, authentification par mappage de certificat Client, l’authentification Windows  <br/> Développement d’applications • : extensibilité .NET 3.5, extensibilité .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, Extensions ISAPI, filtres ISAPI  <br/> Outils de gestion • : Console de gestion IIS, des Scripts de gestion IIS et les outils  <br/> Notez également l’accès anonyme est également nécessaire, mais que vous obtenez lorsque vous installez IIS, sans que vous ayez un emplacement pour le sélectionner dans la liste.  <br/> |
|Module d’exécution du format Windows Media  <br/> | Pour Windows Server 2016, Windows Server 2012 et Windows Server 2012 R2, vous devez installer la fonctionnalité **Media Foundation** dans **Le Gestionnaire de serveur**. Maintenant, vous pouvez lancer votre Skype pour l’installation de Business Server 2015 sans celui-ci, mais vous serez invité à installer, puis redémarrer le serveur, avant le Skype pour Business Server 2015 installer continue. Il vaut donc mieux l’installer au préalable. <br/> |
|Silverlight  <br/> |Vous pouvez installer la dernière version de Silverlight à [ce lien](https://www.microsoft.com/silverlight/).  <br/> |
   
Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser ceci :
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Les directeurs doivent également :**
  
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
    
(Si vous vous demandez, il s’agit du module même définir en tant que les serveurs Standard Edition et les serveurs frontaux, avec la Compression de contenu dynamique et à gauche outils de gestion).
  
Vous trouverez aussi du code PowerShell ci-dessous :
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Serveurs de conversation permanente doivent également :**
  
Message Queuing, appelé aussi MSMQ. Il s’agit d’un composant de Windows Server, et vous pouvez l’installer dans la section fonctionnalités dans le Gestionnaire de serveur. Si vous souhaitez en savoir plus sur ce point, consultez la rubrique [installation et la gestion de Message Queuing](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Dernières pensées :**
  
N’installez tout logiciel client Microsoft Internet Security and Acceleration (ISA) Server ou tout autre logiciel de fournisseurs de services superposés (LSP) Winsock (pare-feux tiers ou des logiciels de contrôle de réseau antivirus serait inclus ici) sur un de vos serveurs frontaux ou les serveurs de médiation autonomes. Les performances du trafic multimédia médiocre a été détectée lors de ce logiciel de l’installation.
  

