---
title: Configuration système requise pour Skype pour Business Server 2019
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 'Résumé : Préparez votre Skype Business Server 2019 serveurs et l’infrastructure de domaine avec cette rubrique. Configuration matérielle, du système d’exploitation, bases de données, logiciel, tous les la configuration système requise et recommandations, ainsi que les certificats DNS, partage de fichiers et informations Active Directory, sont ici afin de garantir une installation réussie et le déploiement de votre batterie de serveurs.'
ms.openlocfilehash: a5422f52e9158d01f821c0a2abd051917fbed7b1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375126"
---
# <a name="server-requirements-for-skype-for-business-server-2019"></a>Configuration du serveur pour Skype pour Business Server 2019

[!INCLUDE [disclaimer](../disclaimer.md)]


 
**Résumé :** Préparer l’installation Skype pour Business Server 2019 avec cette rubrique. Matériel, système d’exploitation, logiciel, bases de données, les certificats, Active Directory, DNS et partages sont abordées ici. Les configuration système requise et les recommandations sont ici afin de garantir une installation réussie et le déploiement de votre batterie de serveurs.
  
Comme vous pouvez le supposer, il existe certaines préparations à effectuer avant de commencer le déploiement de Skype pour Business Server 2019. Cet article vous guide à travers la procédure de planification comme suit :
  
- [Configuration matérielle](system-requirements.md#Hardware)
  
- [Systèmes d’exploitation](system-requirements.md#OS)
  
- [Logiciels](system-requirements.md#Software)

- [Bases de données SQL principale](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [Certificats](system-requirements.md#Certs)
  
- [Partage de fichiers](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Matériel pour Skype pour Business Server 2019
<a name="Hardware"> </a>

Une fois que vous avez votre topologie vers le bas (et si vous n’avez pas, vous pouvez consulter la rubrique [Concepts de base de topologie pour Skype pour Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), il est temps de penser aux serveurs. Skype pour les serveurs Business Server 2019 requièrent du matériel 64 bits. Nos recommandations pour le matériel sont indiquées ci-dessous. Il n’est pas requise, mais ils reflètent les conditions requises pour des performances optimales. La documentation de planification des capacités vous aidera à déterminer si vous avez besoin de capacités supérieures, en fonction des circonstances.
  
Matériel recommandé pour les serveurs Standard Edition :

|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour Business Server 2019 rôles.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • Au moins 8 disques durs de 10 000 tr/min avec au moins 72 Go d’espace disque disponible (deux de ces disques utilisant RAID 1 et six autres utilisant RAID 10).   <br/> SOIT  <br/> •	Des disques SSD (Solid State Drives) pouvant fournir le même espace libre et des performances similaires aux 8 unités de disques mécaniques de 10 000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations doubles ou multi-hébergés sont **pas** serveurs pris en charge pour les serveurs frontaux, serveurs principaux et Standard Edition. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez avoir hors de gestion des systèmes, tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.  <br/> |


Matériel recommandé pour les serveurs frontaux et serveurs principaux :
  
|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieur. <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour Business Server 2019 rôles.  <br/> |
|Mémoire  <br/> |64 gigaoctets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • Au moins 8 disques durs de 10 000 tr/min avec au moins 72 Go d’espace disque disponible (deux de ces disques utilisant RAID 1 et six autres utilisant RAID 10).   <br/> SOIT  <br/> •	Des disques SSD (Solid State Drives) pouvant fournir le même espace libre et des performances similaires aux 8 unités de disques mécaniques de 10 000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Configurations de doubles ou multi-hébergés sont pris en charge **pas** pour les serveurs frontaux, serveurs principaux, Standard Edition, les serveurs et les serveurs de conversation permanente. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez avoir hors de gestion des systèmes, tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.  <br/> |
   
Matériel recommandé pour les serveurs de périphérie, les serveurs de médiation autonomes et les directeurs :
  
|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour Business Server 2019 rôles.  <br/> |
|Mémoire  <br/> |16 giga-octets.  <br/> |
|Disque  <br/> |SOIT :  <br/> • Au moins 4 disques durs de 10 000 tr/min avec au moins 72 Go d’espace disque disponible (les disques doivent avoir une configuration 2x RAID 1).  <br/> SOIT  <br/> •	Des disques SSD (Solid State Drives) pouvant fournir le même espace libre et des performances similaires aux 4 unités de disques mécaniques de 10 000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Configurations doubles ou multi-hébergés sont **pas** pris en charge pour les serveurs d’interopérabilité vidéo et les directeurs. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau double port, 1 Gbit/s ou plus (ou deux cartes réseau appariées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et à une adresse IP unique, pour un total de deux paires).  <br/> Sur les serveurs de médiation autonome, l’installation de cartes d’interface réseau supplémentaire (NIC) pour autoriser la configuration d’une adresse IP PSTN spécifique est pris en charge.  <br/> |


> [!NOTE]
> Quel que soit le rôle de serveur, nous vous recommandons également les paramètres matériels suivants pour Skype pour Business Server 2019 (Cela peut varier en fonction de la marque de matériel acheté, que reportez-vous à la documentation du fabricant pour caractéristiques) :
> - Configuration BIOS - doit être définie sur plat NUMA.
> - Activer l’Hyperthreading.
> - Le paramètre de file d’attente RSS doit être défini à 8 de file d’attente.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Systèmes d’exploitation pour Skype pour Business Server 2019
<a name="OS"> </a>

Une fois que le matériel en place, vous devrez le système d’exploitation install (OS) qui vous permet d’installer et utiliser correctement Skype pour Business Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2016 <br/> ||
||
   
Autre que Windows Server 2016 ne fonctionne pas correctement. n’essayez il pour les installations de Skype pour Business Server 2019.
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Logiciel qui doit être installé avant un Skype pour le déploiement de Business Server 2019
<a name="Software"> </a>

Il existe certaines choses que vous aurez besoin installer ou configurer pour n’importe quel serveur exécutant Skype pour Business Server 2019. Ils sont répertoriés ci-dessous, suivi par les autres exigences de rôles de serveur spécifiques.
  
 **Tous les serveurs :**
  
|**Rôle/logiciel**|**Détails**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tous les Skype pour les serveurs Business Server devez Windows PowerShell 3.0 est installé.  <br/> • Ce doit être installé par défaut avec Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Les services WCF est une **fonctionnalité** qui n’a installé en tant qu’une fonctionnalité de Windows, sous **Gestionnaire de serveur**, aucun téléchargement nécessaires. <br/> • Vous devez vous assurer, lorsque vous installez cette fonctionnalité, ou si elle est déjà installée et vous vérifiez sur celui-ci, que l’option **d’Activation HTTP** est également activée et installée, comme suit : <br/> ![Capture d’écran présentant l’option Activation HTTP des fonctionnalités .NET Framework 4.5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Ne vous inquiétez pas si vous obtenez une fenêtre contextuelle supplémentaire indiquant que d’autres éléments doivent être installés pour que l’Activation HTTP puisse être installée. C’est normal ; Cliquez sur OK et continuez. Si vous n’obtenez cette indépendante, vous pouvez supposer les éléments sont déjà installés et continuez.  <br/> Microsoft .NET Framework est généralement installé lors de l’installation de Windows Server 2016. Skype pour Business Server fonctionne avec les versions suivantes de Microsoft .NET Framework :  <br/> • .NET 3.5  <br/> • .NET FRAMEWORK 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 <br/> |
|Media Foundation  <br/> |Pour Windows Server 2016, Windows Media Format Runtime installe avec Microsoft Media Foundation.  <br/> Tous les serveurs Standard Edition et les serveurs frontaux utilisés pour la conférence nécessitent Windows Media Format Runtime exécuter les fichiers Audio Windows Media (.wma) apparaissant dans les applications de parcage d’appel et annonce Response Group pour la musique et des annonces.  <br/> |
|Windows Identity Foundation  <br/> |Nous devons Windows Identity Foundation 3.5 pour prendre en charge des scénarios d’authentification de serveur à serveur pour Skype pour Business Server 2019.  <br/> • Pour Windows Server 2016, il n’est pas nécessaire de télécharger quoi que ce soit. Ouvrez le **Gestionnaire de serveur** et accédez à l’**Assistant Ajout de rôles et de fonctionnalités**. **Windows Identity Foundation 3.5** est listé sous la section **Fonctionnalités**. Si elle est activée, vous êtes. Dans le cas contraire, sélectionnez-le, puis cliquez sur **suivant** pour atteindre le bouton **installer** . <br/> |
|Outils d’administration de serveur distant  <br/> |Outils d’administration de rôles : outils AD DS et AD LDS  <br/> |
   
 **Serveur frontal de serveurs frontaux et Standard Edition ont également besoin :**
  
|**Rôle/logiciel**|**Détails**|
|:-----|:-----|
|services Internet (IIS)  <br/> |IIS est requis sur tous les serveurs frontaux, ainsi que tous les serveurs Standard Edition, avec les modules suivants sélectionnés :  <br/> Fonctionnalités HTTP communes • : par défaut des documents, des erreurs HTTP, le contenu statique  <br/> • Santé et Diagnostics : HTTP de journalisation, les outils de journalisation de suivi  <br/> • Les performances : Compression de contenu statique, Compression de contenu dynamique  <br/> • Sécurité : filtrage des demandes, authentification par mappage de certificat Client, l’authentification Windows  <br/> Développement d’applications • : extensibilité .NET 3.5, extensibilité .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, Extensions ISAPI, filtres ISAPI  <br/> Outils de gestion • : Console de gestion IIS, des Scripts de gestion IIS et les outils  <br/> Notez que l’accès anonyme est également nécessaire, mais que vous obtenez lorsque vous installez IIS, sans que vous ayez un emplacement pour le sélectionner dans la liste.  <br/> |
|Module d’exécution du format Windows Media  <br/> | Pour Windows Server 2016, vous devez installer la fonctionnalité **Media Foundation** dans **Le Gestionnaire de serveur**. Vous pouvez lancer votre Skype pour l’installation de Business Server 2019 sans cela, mais vous serez invité à installer, puis redémarrer le serveur, avant le Skype pour Business Server 2019 installer continue. Il est préférable de le faire à l’avance. <br/> |
|Silverlight  <br/> |Vous pouvez installer la version la plus récente de Silverlight [ici](https://www.microsoft.com/silverlight/).  <br/> |
   
Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser ceci :
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bases de données principale qui fonctionneront avec Skype pour Business Server 2019
<a name="DBs"> </a>

Lorsque vous installez Skype pour 2019 Business Server Standard Edition, vous aurez SQL Server 2016 Express (Édition 64 bits).

Skype pour Business Server 2019 Enterprise Edition nécessite complète de SQL Server, comme indiqué ci-dessous (seule édition 64 bits ; n’utilisez pas éditions 32 bits) :
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2016/2017 Enterprise (Édition 64 bits) et vous devez exécuter avec les dernières mises à jour et de groupes de disponibilité AlwaysOn.  <br/> ||
 |
   
Si vous ne voyez pas l’édition de SQL Server que vous souhaitez utiliser répertoriés ici, vous ne pouvez pas l’utiliser.
  
> [!NOTE]
> Vous devez également installer SQL Server Reporting Services pour le rôle serveur de surveillance. 
  
### <a name="sql-clustering-and-sql-always-on"></a>Clustering SQL et toujours sur SQL

Gestion de clusters SQL avec Skype pour Business Server 2019 est pris en charge. Si vous souhaitez définir le Clustering SQL, qui est effectuée dans SQL Server.
  
Vérifiez que vous avez une configuration actif/passif de Clustering SQL, qui est pris en charge. Ne pas partager le nœud passif avec d’autres instances SQL.
  
Vous pouvez avoir ce qui suit pour la mise en cluster du basculement :
  
Deux nœuds :
  
- Microsoft SQL Server 2016/2017 Standard (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
Six nœuds :
  
- Microsoft SQL Server 2016/2017 Enterprise (Édition 64 bits) et nous vous recommandons de s’exécuter avec le service pack le plus récent.
    
Nous aurons un article, la configuration de SQL Server clustering pour Skype pour Business Server 2019, que les étapes pour l’obtention de clustering prêt.
 
SQL Always On est pris en charge, et vous pouvez en savoir plus sur celui-ci dans le [serveur principal de haute disponibilité dans Skype pour Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recommandations pour l’installation serveur supplémentaires :
  
N’installez tout logiciel client Microsoft Internet Security and Acceleration (ISA) Server ou tout autre logiciel de fournisseurs de services superposés (LSP) Winsock (pare-feux tiers ou des logiciels de contrôle de réseau antivirus serait inclus ici) sur un de vos serveurs frontaux ou les serveurs de médiation autonomes. Les performances du trafic multimédia médiocre a été constaté lorsque ce logiciel est installé.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Bien que les données de configuration pour les serveurs et services sont stockée dans le Skype pour le magasin de gestion centrale Business Server 2019, certains éléments sont toujours stockés dans Active Directory :
  
|**Objets Active Directory**|**Types d’objets**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions pour Skype pour Business Server 2015 et Lync Server 2013, pour conserver la compatibilité descendante avec les précédentes versions prises en charge  <br/> |
|Données  <br/> |URI SIP de l’utilisateur et autres paramètres utilisateur  <br/> |
||Objets contact pour les applications (telles que l’application Response Group et l’application intendant Conférence)  <br/> |
||Données publiées pour la compatibilité descendante  <br/> |
||Un service point de contrôle (SCP) pour le magasin Central de gestion  <br/> |
||Compte d’authentification Kerberos (un objet ordinateur facultatif)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation pour les contrôleurs de domaine

Les systèmes d’exploitation de contrôleur de domaine suivants peuvent être utilisées :
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Le niveau fonctionnel du domaine de n’importe quel domaine que vous déployez Skype pour Business Server 2019 dans et le niveau fonctionnel de forêt de n’importe quelle forêt que vous déployez Skype pour Business Server 2019, doivent être une des options suivantes :
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Pouvez-vous avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, tant que cet emplacement sont également des contrôleurs de domaine accessibles en écriture disponibles.
  
Il est important de savoir que Skype pour Business Server 2019 ne prennent en charge une seule partie des domaines. Que sont-ils ? Si vous avez un domaine racine intitulé contoso.local, qui va être précise. Si vous avez un domaine racine nommé simplement local, qui est incorrect, et n’est pas accepté par conséquent. Un peu plus à ce sujet a été écrit [dans cet article de la Base de connaissances](https://support.microsoft.com/kb/300684/en-us).
  
Skype pour Business Server 2019 également ne prend en charge les domaines du changement de nom. Si vous devez renommer votre domaine, vous aurez besoin pour désinstaller Skype pour Business Server 2019, effectuez le changement de nom de domaine, puis réinstaller Skype pour Business Server 2019.
  
Enfin, vous pouvez être confronté à un domaine avec un environnement de domaine Active Directory verrouillé, et qui est bien. Nous avons plus d’informations sur le déploiement Skype pour Business Server 2019 dans un environnement de domaine Active Directory verrouillé dans la documentation de déploiement.
  
### <a name="ad-topologies"></a>Topologies AD

Topologies prises en charge dans Skype pour Business Server 2019 sont les suivants :
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
    
- Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
    
Nous disposons des diagrammes et des descriptions pour vous aider à déterminer quelle topologie que vous avez dans votre environnement, ou que vous devrez peut-être configurer avant d’installer Skype pour Business Server 2019. Pour plus de simplicité, nous incluons une clé :
  
![Il s’agit d’une clé pour les icônes utilisées pour les schémas de topologie Skype Entreprise.](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Schéma d’une forêt Active Directory unique avec un seul domaine](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Il n’obtient pas plus facile que cela ; Il s’agit d’une forêt de domaine unique, une topologie courante.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Schéma d’une forêt unique avec un arbre unique et plusieurs domaines](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme illustre de nouveau une forêt unique, mais elle a un ou plusieurs domaines enfants aussi (il en existe trois dans cet exemple spécifique). Le domaine que les utilisateurs sont créés dans peut être différent du domaine Skype pour Business Server 2019 est déployé. Est-ce problématique ? Il est important de noter que lorsque vous déployez un Skype pour Business Server un pool frontal, tous les serveurs de ce pool doivent se trouver dans un seul domaine. Vous pouvez avoir administration inter-domaines via Skype pour Business Server prennent en charge des groupes d’administrateurs universels Windows.
  
Dans le diagramme ci-dessus, vous pouvez voir que les utilisateurs d’un domaine sont en mesure d’accéder aux Skype pour les pools Business Server dans le même domaine ou dans des domaines différents, même si ces utilisateurs sont dans un domaine enfant.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Schéma d’une forêt unique avec des arbres multiples et des espaces de noms disjoints](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Vous pouvez avoir une topologie semblable à ce diagramme, où vous avez une forêt, mais au sein de la forêt plusieurs domaines, avec des espaces de noms Active Directory distincts. Dans ce cas, ce diagramme est une bonne illustration, parce qu’il inclut des utilisateurs dans des domaines différents trois accès à Skype pour Business Server 2019. Traits continus indiquent qu’ils accédez à un Skype pour le pool de serveurs de l’entreprise dans leur propre domaine, tandis qu’une ligne en pointillés ils vont entièrement à un pool dans un arbre différent.
  
Comme vous pouvez le constater, les utilisateurs dans le même domaine, l’arborescence de la même ou même un arbre différent peuvent accéder pools avec succès.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Schéma de forêts multiples dans une topologie de forêts centralisée](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype pour Business Server 2019 ne prend en charge plusieurs forêts configurées dans une topologie à forêt centrale. Si vous n’êtes pas certain c’est ce que vous devez, la topologie de la forêt centrale utilise des objets dans ce pour représenter des utilisateurs dans les autres forêts et les comptes d’utilisateur hôtes pour tous les utilisateurs de la forêt.
  
Comment cela fonctionne-t-il ? Un produit de synchronisation d’annuaires (tels que Forefront Identity Manager ou FIM) gère les comptes d’utilisateurs de votre organisation tout au long de leur existence. Lorsqu’un compte est créé ou supprimé d’une forêt, ce changement est synchronisé avec le contact correspondant dans la forêt centrale.
  
De toute évidence, si votre infrastructure Active Directory est en place, déplacement vers cette topologie peuvent ne pas être facile, mais si vous êtes déjà y, ou encore planification votre infrastructure de la forêt, il peut être un choix judicieux. Vous pouvez centraliser votre Skype pour le déploiement d’entreprise Server 2019 dans une forêt unique, alors que les utilisateurs peuvent rechercher, communiquer et afficher la présence des autres utilisateurs dans n’importe quelle forêt. Toutes les mises à jour des contacts utilisateur sont gérées automatiquement à l’aide du logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise
<a name="BKMK_multipleforestopology"> </a>

![Forêts multiples dans un schéma de topologie de forêts de ressources](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Une topologie de forêt de ressources est également pris en charge ; Il est où une forêt est consacrée à vos applications serveur, telles que Microsoft Exchange Server et Skype pour Business Server 2019 en cours d’exécution. Cette forêt de ressources héberge également une représentation synchronisée des objets d’utilisateurs actifs, mais aucun compte utilisateur à connexion activée. La forêt de ressources est donc un environnement de services partagés pour les autres forêts dans lesquelles les objets utilisateur résident et ceux-ci ont une relation de confiance au niveau de la forêt avec la forêt de ressources.
  
Notez que Exchange Server peuvent être déployé dans la même forêt de ressources que Skype pour Business Server ou dans une forêt différente.
  
Pour déployer Skype pour Business Server 2019 dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs (si Microsoft Exchange Server est déjà dans l’environnement, il peut être fait pour vous). Vous avez besoin d’un outil de synchronisation d’annuaires (tels que Forefront Identity Manager ou FIM) pour gérer les comptes d’utilisateurs par le biais de leur cycle de vie.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à celle décrite dans la rubrique [Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online](system-requirements.md#BKMK_multipleforestopology).
  
Dans cette topologie, il existe un ou plusieurs forêts d’utilisateurs, et Skype pour Business Server est déployé dans une forêt de ressources dédié. Exchange Server peut être déployé localement dans la même forêt de ressources ou d’une autre forêt et configuré pour l’environnement hybride avec Exchange Online ou les services de messagerie peuvent être fournis en mode exclusif par Exchange Online pour les comptes locaux. Aucun diagramme n’est disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Représente deux forêts AD : une forêt d’utilisateurs et une forêt de ressources. Les deux forêts sont liées par une relation de confiance. Elles sont synchronisées avec Office 365 via Azure AD Connect. Tous les utilisateurs peuvent accéder à Skype Entreprise via Office 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Dans ce scénario, il existe plusieurs forêts sur site avec une topologie de forêt de ressources. Il existe une relation d’approbation totale entre les forêts Active Directory. L’outil Azure Active Directory Connect est utilisé pour synchroniser des comptes entre les forêts d’utilisateurs sur site et Office 365.
  
 L’organisation a Office 365 et utilise [Azure Active Directory se connecter](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect) pour synchroniser leurs comptes locaux avec Office 365. Les utilisateurs activés pour Skype pour les entreprises sont activées via Office 365 et Skype pour Business en ligne. Skype pour Business Server n’est pas déployés en local.
  
Ouverture de session d’authentification unique est fournie par une batterie de serveurs Active Directory Federation Services situé dans la forêt de l’utilisateur.
  
Dans ce scénario, il est pris en charge pour déployer Exchange local, Exchange Online, une solution Exchange hybride, ou de ne pas du tout de déploiement d’Exchange. (Le schéma présente uniquement Exchange en local, mais les autres solutions Exchange sont entièrement prises en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt de ressources et un déploiement hybride de Skype Entreprise 
<a name="BKMK_multipleforestopology"> </a>

Dans ce scénario, il existe un ou plusieurs locaux forêts d’utilisateurs et Skype pour les entreprises est déployé dans une forêt de ressources dédiées et est configuré pour le mode hybride avec Skype pour Business Online. Exchange Server peut être déployé localement dans la même forêt de ressources ou d’une autre forêt et peut être configuré pour l’environnement hybride avec Exchange Online. Vous pouvez également des services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux.
  
Pour plus d’informations, consultez [configurer un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype pour Business Server 2019 nécessite le système DNS, pour les raisons suivantes :
  
- DNS permet de Skype pour Business Server 2019 découvrir les serveurs internes ou des pools, autorisant les communications de serveur à serveur.
    
- DNS permet aux clients de machines à détecter le pool frontal ou un serveur Standard Edition server utilisé pour les transactions SIP.
    
- Il associe des URL simples pour des conférences avec les serveurs hébergeant ces conférences.
    
- DNS permet aux utilisateurs externes et les ordinateurs clients pour se connecter à vos serveurs de périphérie, ou le proxy inverse HTTP, pour la messagerie instantanée (IM) ou de conférence.
    
- Il vous permet de communications unifiées (UC) périphériques qui ne sont pas connectés de détecter le pool frontal ou un serveur Standard Edition server qui exécute le service web de mise à jour de périphérique pour obtenir des mises à jour et envoyer des journaux.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.
    
- Il est utilisé dans l’équilibrage de charge DNS.
    
Il est important de noter que Skype pour Business Server 2019 ne prennent en charge les noms de domaine internationaux (IDN).
  
Et il est très important de n’oubliez pas que n’importe quel nom dans le système DNS est identique au nom d’ordinateur configuré sur n’importe quel serveur utilisé par Skype pour Business Server 2019. Plus précisément, nous ne peut pas avoir des noms de short dans l’environnement et doit avoir des noms de domaine complets pour le Générateur de topologie.
  
Cela semble qu’il serait logique pour n’importe quel ordinateur déjà relié à un domaine, mais si vous avez un serveur Edge qui n’est pas lié à votre domaine, elle peut avoir un nom court, avec aucun suffixe de domaine par défaut. Assurez-vous que qui n’est pas le cas, dans le système DNS ou sur le serveur de périphérie, ou n’importe quel Skype pour Business Server 2019 serveur ou pool, dans notre exemple.
  
Sans aucun doute n’utilisez pas les caractères Unicode ni trait de soulignement. Des caractères standard (qui sont A-Z, a-z, 0-9 et tirets) sont pris en charge par les DNS externes et les autorités de certification publique (vous devez attribuer des noms de domaine complets pour le nom de service dans le certificat, il est important de garder à l’esprit), de sorte que vous aurez de rechange vous-même un grand nombre de difficultés si vous nommez Par conséquent, à partir du début.
  
Pour en savoir plus sur les exigences du DNS pour le réseau, consultez la section [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) de notre documentation consacrée à la planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des tâches les plus importantes à effectuer avant le déploiement est de vérifier que les certificats sont en ordre. Skype pour Business Server 2019 a besoin d’une infrastructure à clé publique (PKI) pour le transport layer security (TLS) et les connexions mutual transport layer security (MTLS). En fait, pour sécuriser les communications d’une manière standardisée, Skype pour Business Server utilise des certificats émis par des autorités de certification (CA).
  
Voici certaines des choses que Skype pour Business Server 2019 utilise des certificats pour :
  
- Connexions TLS entre clients et serveurs
    
- Connexions MTLS entre serveurs
    
- À l’aide de la détection DNS automatique des partenaires de fédération
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- En train de parler à Outlook Web Access (OWA) et les applications web
    
Planification de certificat est indispensable. À présent, examinons une liste de certaines des choses que vous devez garder à l’esprit lors de la demande de certificats :
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation. Skype pour Business Server 2019 prend en charge le SHA-1 et SHA-2 suite du résumé dimensionne (224, 256, 384 et 512 bits) et est conforme ou dépasse la configuration système d’exploitation requise.
    
- L’inscription automatique est prise en charge pour les serveurs internes exécutant Skype pour Business Server 2019.
    
- L’inscription automatique n’est pas pris en charge pour Skype pour les serveurs de périphérie 2019 Business Server.
    
> [!NOTE]
> L’algorithme de signature RSASSA-PSS n’est pas pris en charge et peut entraîner entre autres des erreurs de connexion et de transfert d’appels.  
  
- Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé supérieures ou égales à 2048 sont recommandées.
    
- L’algorithme digest, ou de signature de hachage, par défaut est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
C’est un lot à prendre en compte et un certain nombre de niveaux de confort à demander des certificats à partir d’une autorité de certification. Nous vous donnerons des indications supplémentaires ci-dessous pour rendre votre planification aussi simple que possible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

Vous aurez besoin des certificats pour la plupart de vos serveurs internes, et le plus souvent, vous obtenez les à partir d’une autorité de certification interne (qui est une autorité de certification située dans votre domaine). Si vous le souhaitez, vous pouvez demander ces certificats à partir d’une autorité de certification externe (celui situé sur Internet). Si vous vous demandez quels autorité de certification publique vous devez atteindre, vous pouvez extraire la liste des [partenaires de certificat de Communications unifiées](https://support.microsoft.com/kb/929395/en-us) .
  
Vous aurez également besoin des certificats lorsque Skype pour Business Server 2019 communique avec les autres applications et serveurs, telle que Microsoft Exchange Server. Ceci, bien évidemment, devrez être un certificat que ces autres applications et serveurs peuvent utiliser de façon pris en charge. Skype pour Business Server 2019 et d’autres produits Microsoft prend en charge le protocole Open Authorization (OAuth) pour l’autorisation et authentification de serveur à serveur. Si vous êtes intéressé par cela, nous avons un article de planification supplémentaire pour OAuth et Skype Business Server 2019.
  
Skype pour Business Server 2019 prend également en charge (sans nécessiter) certificats signés à l’aide de la fonction de hachage cryptographique SHA-256. Pour favoriser l’accès externe à l’aide de SHA-256, le certificat externe doit être émis par une autorité de certification publique utilisant SHA-256.
  
Pour simplifier les choses simples, nous avons créé les certificats requis pour les serveurs Standard Edition Server, pools frontaux et d’autres rôles, dans les tableaux suivants, avec le contoso.com fictive utilisée pour obtenir des exemples (probablement à utiliser un autre pour votre environnement). Il s’agit de tous les certificats de serveur web standard, avec des clés privées qui ne sont pas exportables. Quelques points supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Le nom convivial de chaque certificat doit être unique dans le magasin de l’ordinateur.
    
- Selon les exemples de noms ci-dessous, si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, ils doivent être ajoutés à l’autorité Subject Alternative nom (SAN).
    
Certificats pour les serveurs Standard Edition Server :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=se01.contoso.com ; SAN=se01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |Sur les serveurs Standard Edition Server, le nom de domaine complet du serveur est le même que le nom de domaine complet du pool.  <br/> L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> Web interne • nom de domaine complet (qui est le même que le nom de domaine complet du serveur)  <br/> ET  <br/> • Les URL simples meet  <br/> • Rendez-vous des URL simples  <br/> • D’administration simples  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=se01.contoso.com ; SAN=se01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com ; SAN=Admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com ; SAN=se01.contoso.com ; SAN =\*. contoso.com  <br/> |Vous ne pouvez pas remplacer le nom de domaine complet dans le Générateur de topologie de site web interne.  <br/> Si vous avez plusieurs URL simples Meet, vous devez inclure tous les comme SAN.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Domaine complet web externe  <br/> ET  <br/> • Rendez-vous des URL simples  <br/> • Les URL simples meet par domaine SIP  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=se01.contoso.com ; SAN=webcon01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com ; SAN=webcon01.contoso.com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL simples Meet, vous devez inclure tous les noms de sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour les serveurs frontaux dans un pool frontal :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=eepool.contoso.com ; SAN=eepool.contoso.com ; SAN=ee01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> Web interne • nom de domaine complet (qui n’est pas le même que le nom de domaine complet du serveur)  <br/> • FQDN du serveur  <br/> • Skype pour le pool d’entreprise nom de domaine complet  <br/> ET  <br/> • Les URL simples meet  <br/> • Rendez-vous des URL simples  <br/> • D’administration simples  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=ee01.contoso.com ; SAN=ee01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com ; SAN=Admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com ; SAN=ee01.contoso.com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL simples Meet, vous devez inclure tous les noms de sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Domaine complet web externe  <br/> ET  <br/> • Rendez-vous des URL simples  <br/> • D’administration simples  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=ee01.contoso.com ; SAN=webcon01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com ; SAN=webcon01.contoso.com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL simples Meet, vous devez inclure tous les noms de sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour le directeur :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool de directeurs  <br/> |Nom de domaine complet du directeur, nom de domaine complet du pool directeur.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et stricte correspondance DNS est requise dans la stratégie de groupe, vous aurez également besoin des entrées pour sip.sipdomain (pour chaque domaine SIP que vous avez).  <br/> |pool.contoso.com associé ; SAN=dir01.contoso.com  <br/> Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et la correspondance DNS stricte est requise dans la stratégie de groupe, également nécessaires ; SAN=SIP.fabrikam.com  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> Web interne • nom de domaine complet (qui est le même que le nom de domaine complet du serveur)  <br/> • FQDN du serveur  <br/> • Skype pour le pool d’entreprise nom de domaine complet  <br/> ET  <br/> • Les URL simples meet  <br/> • Rendez-vous des URL simples  <br/> • D’administration simples  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |SN=dir01.contoso.com ; SAN=dir01.contoso.com ; SAN=Meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com ; SAN=Admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com ; SAN=dir01.contoso.com SAN =\*. contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Domaine complet web externe  <br/> ET  <br/> • Les URL simples meet par domaine SIP  <br/> • Rendez-vous des URL simples  <br/> OU  <br/> • Une entrée de caractère générique pour les URL simples  <br/> |Le nom de domaine complet du directeur externe web doit être différent à partir du pool frontal ou un serveur frontal.  <br/> SN=dir01.contoso.com ; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com ; SAN=Meet.fabrikam.com ; SAN=Dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com ; SAN=directorwebcon01.contoso.com SAN =\*. contoso.com  <br/> |
   
Certificats pour le serveur de médiation autonome :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> Nom de domaine complet du serveur membre du pool  <br/> |SN = medsvr-pool.contoso.net ; SAN = medsvr-pool.contoso.net ; SAN=medsvr01.contoso .net  <br/> |
   
Certificats pour les Survivable Branch Appliance (plus précisément, Survivable Branch le matériel 2015 pour Skype pour Business Server 2019) :
  
|**Certificat**|**Nom du sujet nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appareil  <br/> |SIP. \<sipdomain\> (vous avez besoin qu’une seule entrée par domaine SIP)  <br/> |SN=sba01.contoso .net ; SAN=SIP.contoso.com ; SAN=SIP.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype pour Business Server 2019 prend en charge l’utilisation d’un **seul certificat public** interfaces externes des Edge de conférence web et accès plus A / service d’authentification V, qui est fourni par le biais du ou des serveurs Edge. L’interface interne Edge l'on utilise généralement un certificat privé émis par votre autorité de certification interne, mais si vous préférez, vous pouvez utiliser un certificat public pour cela, s’il s’agit d’une autorité de certification approuvée.
  
Votre proxy inverse (RP) utilise également un certificat public et chiffre la communication de votre RP aux clients et du RP aux serveurs internes via HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

Si vous déployez la mobilité et que vous êtes en charge la découverte automatique pour les clients mobiles, vous aurez besoin d’inclure certaines entrées de l’autre nom du sujet supplémentaires sur vos certificats pour prendre en charge les connexions sécurisées à partir des clients mobiles.
  
Vous avez besoin des noms de réseau SAN pour la découverte automatique sur les certificats suivants :
  
- pool de directeurs
    
- Pool de serveurs frontaux
    
- Proxy inverse
    
Les caractéristiques sont répertoriés dans les tableaux ci-dessous.
  
C’est là un peu de planification préalable est correcte, mais parfois vous avez déployé Skype pour Business Server 2019 sans ayant l’intention de déployer la mobilité, et qui s’affiche ultérieurement lorsque vous disposez déjà de certificats dans votre environnement. Les relance par le biais d’une autorité de certification interne est généralement assez facile, mais avec des certificats publics à partir d’une autorité de certification publique, qui peut être un peu plus pricy.
  
Si c’est ce que vous cherchez à, et si vous disposez d’un grand nombre de domaines SIP (qui fera ajoute SAN plus onéreux), vous pouvez configurer votre serveur proxy inverse pour utiliser le protocole HTTP pour la demande initiale de Autodiscover Service, au lieu d’utiliser le protocole HTTPS (qui est la valeur par défaut configuration). L’article [Plan pour la mobilité](../../SfbServer/plan-your-deployment/mobility.md) a plus d’informations.
  
Configuration requise du certificat pool directeur et le pool frontal :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Vous pouvez également utiliser SAN =\*. \<sipdomain\>
  
Exigences relatives au certificat de proxy inverse (autorité de certification publique)
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Ce SAN doit être attribué au certificat qui est affecté à l’écouteur SSL sur votre proxy inverse.
  
> [!NOTE]
> Votre écouteur de proxy inverse sur le point d’avoir SAN pour votre URL de Services Web externes. Il peut s’agir SAN=skypewebextpool01.contoso.com et dirwebexternal.contoso.com, si vous avez déployé le directeur (qui est facultatif). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype pour Business Server 2019 peut utiliser le même partage de fichiers pour le stockage de tous les fichiers. Gardez à l’esprit ce qui suit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (Direct Attached Storage) ou un réseau de stockage SAN (Storage Area Network), dont un système de fichiers distribués (DFS) et sur une solution RAID (Redundant Array Of Independent Disks) pour les magasins de fichiers. Pour plus d’informations sur DFS pour Windows Server 2012, consultez la rubrique [cette page DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Nous vous recommandons d’un cluster partagé pour le partage de fichiers. Si vous utilisez, vous devez de cluster Windows Server 2012 ou Windows Server 2012 R2. Pourquoi Windows le plus récent ? Les versions antérieures n’est peut-être pas les autorisations pour activer toutes les fonctionnalités. Vous pouvez utiliser l’administrateur de Cluster pour créer les partages de fichiers, et cet article de la [Création d’un Cluster](https://support.microsoft.com/en-us/help/224967) KB vous aider avec les détails.
    
> [!CAUTION]
> Vous devez savoir que le dispositif de stockage réseau (NAS) ne prend pas en charge le partage de fichiers. Vous devez donc utiliser l’une des options proposées ci-après. 
  








