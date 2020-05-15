---
title: Configuration système requise pour Skype entreprise Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 'Résumé : Préparez vos serveurs Skype entreprise Server 2019 et votre infrastructure de domaine à l’aide de cette rubrique. Le matériel, le système d’exploitation, les bases de données, les logiciels, toutes les exigences système et les recommandations, ainsi que les informations de certificat DNS, de partage de fichiers et d’Active Directory, sont ici pour vous aider à réussir l’installation et le déploiement de votre batterie de serveurs.'
ms.openlocfilehash: 8bb12fa9f5d0cd0144604f21d311c50f7f63b0f4
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232375"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Configuration système requise pour Skype entreprise Server 2019
 
**Résumé :** Préparez-vous à installer Skype entreprise Server 2019 avec cette rubrique. Le matériel, le système d’exploitation, le logiciel, les bases de données, les certificats, le DNS et Fileshares sont abordés ici. La configuration système requise et les recommandations sont ici pour vous aider à réussir l’installation et le déploiement de votre batterie de serveurs.
  
Comme vous pouvez vous y attendre, certaines préparations doivent être apportées avant de commencer à déployer Skype entreprise Server 2019. Cet article vous guidera dans la planification des opérations suivantes :
  
- [Matériel](system-requirements.md#Hardware)
  
- [Systèmes d’exploitation](system-requirements.md#OS)
  
- [Logiciels](system-requirements.md#Software)

- [Bases de données SQL principales](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [DNS (Domain Name System)](system-requirements.md#DNS)
  
- [Certificats](system-requirements.md#Certs)
  
- [Partage de fichiers](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Matériel pour Skype entreprise Server 2019
<a name="Hardware"> </a>

Une fois que votre topologie est inactive (et si vous ne l’avez pas fait, vous pouvez consulter la rubrique relative aux [concepts de base de la topologie pour Skype entreprise Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), il est temps de réfléchir aux serveurs. Les serveurs Skype entreprise Server 2019 nécessitent un matériel 64 bits. Nos recommandations en matière de matériel sont indiquées ci-dessous. Ces configurations ne sont pas requises, mais elles reflètent les conditions requises pour des performances optimales. Nous disposons d’une documentation sur la planification de la capacité qui vous permettra de déterminer si vous avez besoin de plus de, en fonction de vos circonstances.
  
Matériel recommandé pour les serveurs Standard Edition Server :

|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Intel Xeon E5-double processeur 2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles Skype entreprise Server 2019.  <br/> |
|Mémoire  <br/> |32 gigaoctets (Go).  <br/> |
|Disque  <br/> |ENTRE  <br/> • 8 disques durs 10000 tr/min avec au moins 72 Go d’espace disque disponible (deux des disques utilisant RAID 1 et 6 avec RAID 10).  <br/> OR  <br/> • Disques SSD (Solid State Drive) capables de fournir le même espace libre et des performances similaires sur des disques durs mécaniques de 8 10000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou supérieur (2 cartes réseau peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double ou multi-hébergement ne sont **pas** prises en charge pour les serveurs frontaux, les serveurs principaux et les serveurs Standard Edition. <br/> Dans la mesure où ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel de serveur, vous pouvez avoir des systèmes de gestion hors bande, comme DRAC ou ILO. Ce scénario ne constitue pas un serveur multi-hébergement et est pris en charge.  <br/> |


Matériel recommandé pour les serveurs frontaux et principaux :
  
|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Intel Xeon E5-double processeur 2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur. <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles Skype entreprise Server 2019.  <br/> |
|Mémoire  <br/> |64 gigaoctets (Go).  <br/> |
|Disque  <br/> |ENTRE  <br/> • 8 disques durs 10000 tr/min avec au moins 72 Go d’espace disque disponible (deux des disques utilisant RAID 1 et 6 avec RAID 10).  <br/> OR  <br/> • Disques SSD (Solid State Drive) capables de fournir le même espace libre et des performances similaires sur des disques durs mécaniques de 8 10000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou supérieur (2 cartes réseau peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double ou multi-hébergement ne sont **pas** prises en charge pour les serveurs frontaux, les serveurs principaux et les serveurs Standard Edition. <br/> Dans la mesure où ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel de serveur, vous pouvez avoir des systèmes de gestion hors bande, comme DRAC ou ILO. Ce scénario ne constitue pas un serveur multi-hébergement et est pris en charge.  <br/> |
   
Matériel recommandé pour les serveurs Edge, les serveurs de médiation autonomes et les directeurs :
  
|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Intel Xeon E5-double processeur 2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles Skype entreprise Server 2019.  <br/> |
|Mémoire  <br/> |32 gigaoctets.  <br/> |
|Disque  <br/> |ENTRE  <br/> • au moins 4 disques durs 10000 RPM avec au moins 72 Go d’espace disque disponible (les disques doivent être dans une configuration 2x RAID 1).  <br/> OR  <br/> • Disques SSD (Solid State Drive) capables de fournir le même espace libre et des performances similaires sur des disques durs mécaniques de 4 10000 tr/min.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou supérieur (2 cartes réseau peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations Dual ou multi-hébergement ne sont **pas** prises en charge pour les serveurs et les directeurs d’interopérabilité vidéo. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau à deux ports, 1 Gbits/s ou supérieur (ou deux cartes réseau couplées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et une seule adresse IP, pour un total de deux paires).  <br/> Sur les serveurs de médiation autonomes, l’installation de cartes d’interface réseau (NIC) supplémentaires pour permettre la configuration d’une adresse IP RTC spécifique est prise en charge.  <br/> |


> [!NOTE]
> Quel que soit le rôle de serveur, nous recommandons également les paramètres matériels suivants pour Skype entreprise Server 2019 (cela peut varier en fonction de la marque de matériel que vous avez achetée, reportez-vous à la documentation du fabricant pour obtenir des informations spécifiques) :
> - Config BIOS-doit être défini sur FLAT à partir de NUMA.
> - Activer l’hyperthreading.
> - Le paramètre de file d’attente RSS doit être défini sur 8 queue.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Systèmes d’exploitation pour Skype entreprise Server 2019
<a name="OS"> </a>

Une fois le matériel en place, vous devez installer le système d’exploitation (OS) qui vous permettra d’installer et d’utiliser avec succès Skype entreprise Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Tout élément autre que les systèmes d’exploitation répertoriés ici ne fonctionnera pas correctement ; n’essayez pas d’installer Skype entreprise Server 2019. Par exemple, l’option Server Core n’est pas disponible, et n’est donc pas prise en charge.

> [!NOTE]
> La mise à niveau sur place du système d’exploitation n’est pas prise en charge avec Lync Server 2013. Vous devez déployer un pool distinct et migrer les utilisateurs vers le nouveau pool avec un système d’exploitation différent. Tous les serveurs d’un pool doivent avoir la même version de système d’exploitation.

> [!NOTE]
> 
> Si vous installez le centre d’administration Windows 2019 sur votre ordinateur Windows Server 2019, vous serez invité à indiquer un port d’écoute. Il existe un liklihood vous pouvez choisir le port 443, mais si vous avez installé Skype entreprise Server 2019 sur cet ordinateur ou sur lequel Skype entreprise Server 2019 sera installé, vous devez choisir un autre numéro de port.
> 
>Pourquoi est-ce le cas ? Si le centre d’administration Windows 2019 est exécuté sur le port 443, vous ne pourrez pas vous connecter au serveur à l’aide du panneau de configuration de Skype entreprise et vous ne pourrez pas vous connecter à un service Web interne s’exécutant sur le serveur (service Web de carnet d’adresses, service de découverte automatique, service de ticket Web, etc.).  En fait, vous ne pourrez pas vous connecter à une URL de service Web interne. Choisissez un autre port, dans le cas où vous avez besoin ou vous souhaitez placer le centre d’administration Windows 2019 sur un serveur avec Skype entreprise Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Logiciels devant être installés avant un déploiement de Skype entreprise Server 2019
<a name="Software"> </a>

Certains éléments doivent être installés ou configurés pour n’importe quel serveur exécutant Skype entreprise Server 2019. Ces éléments sont répertoriés ci-dessous, suivis de conditions requises supplémentaires pour des rôles serveur spécifiques.

> [!IMPORTANT]
> Skype entreprise 2019 prend en charge .NET Framework 4,8. 
  
 **Tous les serveurs :**
  
|**Logiciels/rôles**|**Détails**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tous les serveurs Skype entreprise Server nécessitent Windows PowerShell 3,0.  <br/> • Il doit être installé par défaut avec Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Services WCF est une **fonctionnalité** installée en tant que fonctionnalité Windows, sous **Gestionnaire de serveur**, sans aucun téléchargement nécessaire. <br/> • Vous devez vous assurer, lorsque vous installez cette fonctionnalité, ou si elle est déjà installée et que vous l’archivez, que l’option d' **activation http** est également vérifiée et installée, de la manière suivante : <br/> ![Capture d’écran illustrant l’option d’activation HTTP sous les fonctionnalités .NET Framework 4,5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Ne vous inquiétez pas si vous obtenez une fenêtre contextuelle supplémentaire indiquant que d’autres éléments doivent être installés pour que l’activation HTTP soit installée. C’est normal ; Cliquez sur OK et continuez. Si vous n’obtenez pas cette fenêtre contextuelle, vous pouvez supposer que ces éléments sont déjà installés et continuer.  <br/> Microsoft .NET Framework est généralement installé lors de l’installation de Windows Server 2016. Skype entreprise Server requiert Microsoft .NET Framework 4,7 ou 4,8 Cependant, vous auriez probablement besoin de le mettre à jour. Vous trouverez la mise à jour [ici](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Pour Windows Server 2016, le runtime du format Windows Media s’installe avec Microsoft Media Foundation.  <br/> Tous les serveurs frontaux et les serveurs Standard Edition utilisés pour les conférences nécessitent que Windows Media Format Runtime exécute les fichiers audio Windows Media (. WMA) que les applications de parcage d’appel, d’annonce et Response Group jouent pour les annonces et la musique.  <br/> |
|Windows Identity Foundation  <br/> |Nous avons besoin de Windows Identity Foundation 3,5 pour prendre en charge les scénarios d’authentification de serveur à serveur pour Skype entreprise Server 2019.  <br/> • Pour Windows Server 2016, il n’est pas nécessaire de télécharger quoi que ce soit. Ouvrez le **Gestionnaire de serveur**, puis accédez à l' **Assistant Ajouter des rôles et des fonctionnalités**. **Windows Identity Foundation 3,5** est affiché sous la section **features** . Si elle est sélectionnée, vous avez l’habitude. Sinon, sélectionnez-le et cliquez sur **suivant** pour accéder au bouton **installer** . <br/> |
|Outils d'administration de serveur distant  <br/> |Outils d’administration de rôles : services AD DS et AD LDS  <br/> |
   
 **Les serveurs frontaux et le serveur Standard Edition ont également besoin des éléments suivants :**
  
|**Logiciels/rôles**|**Détails**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS est nécessaire sur tous les serveurs frontaux, ainsi que sur tous les serveurs Standard Edition, avec les modules suivants sélectionnés :  <br/> • Fonctionnalités HTTP courantes : document par défaut, erreurs HTTP, contenu statique  <br/> • Intégrité et diagnostics : journalisation HTTP, outils de journalisation, suivi  <br/> • Performances : compression de contenu statique, compression de contenu dynamique  <br/> • Sécurité : filtrage des requêtes, authentification par mappage de certificat client, authentification Windows  <br/> • Développement d’applications : extensibilité .NET 3,5, extensibilité .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensions ISAPI, filtres ISAPI  <br/> • Outils de gestion : console de gestion IIS, scripts et outils de gestion IIS  <br/> Notez que l’accès anonyme est également nécessaire, mais que lorsque vous installez les services Internet (IIS), vous n’avez pas besoin d’un emplacement pour le sélectionner dans la liste.  <br/> |
|Module d’exécution du format Windows Media  <br/> | Pour Windows Server 2016, vous devez installer la fonctionnalité **Media Foundation** dans le **Gestionnaire de serveur**. Vous pouvez commencer votre installation de Skype entreprise Server 2019 sans cela, mais vous serez invité à l’installer, puis à redémarrer le serveur, avant que l’installation de Skype entreprise Server 2019 ne se poursuive. Il est préférable de le faire à l’avance. <br/> |
|Silverlight  <br/> |Vous pouvez installer la dernière version de Silverlight [ici](https://www.microsoft.com/silverlight/).  <br/> |
   
Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser les opérations suivantes :
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bases de données principales qui fonctionneront avec Skype entreprise Server 2019
<a name="DBs"> </a>

Lors de l’installation de Skype entreprise Server 2019 Standard Edition, vous disposez de SQL Server 2016 Express (64 bits Edition).

Skype entreprise Server 2019 Enterprise Edition requiert un serveur SQL complet, comme indiqué ci-dessous (seule édition 64 bits ; n’utilisez pas les éditions 32 bits) :
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (version 64 bits) et vous devez l’exécuter avec les dernières mises à jour.  <br/> |Microsoft SQL Server 2017 (version 64 bits) et vous devez l’exécuter avec les dernières mises à jour.  <br/> |
Microsoft SQL Server 2016 (version 64 bits) et vous devez l’exécuter avec les dernières mises à jour.|
 |

Si vous ne voyez pas l’édition SQL Server que vous souhaitez utiliser répertoriée ici, vous ne pouvez pas l’utiliser.
  
> [!NOTE]
> Vous devez également installer SQL Server Reporting Services pour le rôle serveur de surveillance. 
  
### <a name="sql-clustering-and-sql-always-on"></a>Clustering SQL et SQL Always on

Le clustering SQL avec Skype entreprise Server 2019 est pris en charge. Si vous souhaitez configurer le clustering SQL, cette opération est exécutée dans SQL Server.
  
Assurez-vous que vous disposez d’une configuration active/passive pour le clustering SQL, ce qui est pris en charge. Ne partagez pas le nœud passif avec une autre instance SQL.
  
Vous pouvez disposer des éléments suivants pour le clustering de basculement :
  
Deux nœuds :
  
- Microsoft SQL Server 2019 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.
- Microsoft SQL Server 2017 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.
- Microsoft SQL Server 2016 standard (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

Seize nœuds :
  
- Microsoft SQL Server 2019 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.
- Microsoft SQL Server 2017 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.
- Microsoft SQL Server 2016 Enterprise (64-bit Edition) et nous vous recommandons de l’exécuter avec le dernier Service Pack.

SQL Always on est pris en charge et vous pouvez en savoir plus à ce sujet dans la [haute disponibilité des serveurs principaux dans Skype entreprise server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recommandations pour l’installation d’un serveur supplémentaire :
  
N’installez pas de logiciel client Microsoft Internet Security and Acceleration (ISA) Server ou tout autre logiciel de fournisseur de services en couche (LSP) Winsock (tous les logiciels d’inspection de réseau antivirus ou de pare-feu tiers seraient inclus ici) sur l’un des serveurs frontaux ou des serveurs de médiation autonomes. De mauvaises performances de trafic multimédia ont été constatées lors de l’installation de ce logiciel.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Bien que la plupart des données de configuration des serveurs et des services soient stockées dans le magasin central de gestion de Skype entreprise Server 2019, certaines choses sont toujours stockées dans Active Directory :
  
|**Objets Active Directory**|**Types d’objets**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions pour Skype entreprise Server 2015 et Lync Server 2013, pour assurer la compatibilité descendante avec les versions prises en charge précédentes  <br/> |
|Données  <br/> |URI SIP de l’utilisateur et autres paramètres utilisateur  <br/> |
||Objets contact pour les applications (comme l’application Response Group et l’application de surveillance de conférence)  <br/> |
||Données publiées pour la compatibilité descendante  <br/> |
||Un point de contrôle de service (SCP) pour le magasin central de gestion  <br/> |
||Compte d’authentification Kerberos (un objet ordinateur facultatif)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation des contrôleurs de domaine

Les systèmes d’exploitation de contrôleur de domaine suivants peuvent être utilisés :
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Le niveau fonctionnel de tout domaine sur lequel vous déployez Skype entreprise Server 2019 et le niveau fonctionnel de la forêt dans lequel vous déployez Skype entreprise Server 2019 doivent être l’un des suivants :
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Est-il possible d’avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, tant qu’il existe également des contrôleurs de domaine accessibles en écriture.
  
Il est important de savoir que Skype entreprise Server 2019 ne prend pas en charge les domaines à étiquette unique. Qu’est-ce qu’elles ? Si vous avez un domaine racine nommé contoso. local, cela va être parfait. Si vous disposez d’un domaine racine qui vient d’être nommé local, cela ne fonctionne pas, et n’est pas pris en charge en conséquence. Pour plus d’informations [, consultez cet article de la base de connaissances](https://support.microsoft.com/kb/300684/).
  
Skype entreprise Server 2019 ne prend pas non plus en charge le changement de nom des domaines. Si vous devez vraiment renommer votre domaine, vous devez désinstaller Skype entreprise Server 2019, effectuer le changement de nom de domaine, puis réinstaller Skype entreprise Server 2019.
  
Enfin, vous pouvez être confronté à un domaine avec un environnement AD DS verrouillé, et c’est le bon. Nous avons plus d’informations sur la façon de déployer Skype entreprise Server 2019 dans un environnement AD DS verrouillé dans la documentation de déploiement.
  
### <a name="ad-topologies"></a>Topologies AD

Les topologies prises en charge dans Skype entreprise Server 2019 sont les suivantes :
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts dans une topologie de forêt de ressources Skype entreprise avec Exchange Online
    
- Plusieurs forêts dans une topologie de forêt de ressources avec Skype entreprise Online et Azure Active Directory Connect
    
Nous disposons de diagrammes et de descriptions pour vous aider à déterminer la topologie que vous avez dans votre environnement, ou ce que vous devrez peut-être configurer avant d’installer Skype entreprise Server 2019. Pour simplifier, nous incluons également une clé :
  
![Le est une clé pour les icônes utilisées pour les diagrammes de topologie Skype entreprise](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Diagramme d’une forêt Active Directory unique avec un seul domaine](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Il n’est pas plus facile que cela ; Il s’agit d’une forêt de domaine unique, une topologie commune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Diagramme de forêt unique, d’arborescence unique et de domaines plusieurs](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme montre une seule forêt, encore une fois, mais elle comporte également un ou plusieurs domaines enfants (trois dans cet exemple). Par conséquent, le domaine dans lequel les utilisateurs sont créés peut être différent du domaine dans lequel Skype entreprise Server 2019 est déployé. Pourquoi vous en inquiéter ? N’oubliez pas que lorsque vous déployez un pool frontal Skype entreprise Server, tous les serveurs de ce pool doivent se trouver dans un seul domaine. Vous pouvez utiliser l’administration entre domaines via Skype entreprise Server pour les groupes d’administrateurs universels Windows.
  
Dans le diagramme ci-dessus, vous pouvez voir que les utilisateurs d’un domaine peuvent accéder aux pools Skype entreprise Server à partir du même domaine ou de différents domaines, même si ces utilisateurs se trouvent dans un domaine enfant.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Diagramme à une seule forêt, plusieurs arborescences et espaces de noms disjoints](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Vous avez peut-être une topologie similaire à celle de ce diagramme, où vous avez une forêt, mais au sein de cette forêt, il s’agit de plusieurs domaines avec des espaces de noms AD distincts. Dans ce cas, ce diagramme est une excellente illustration, car il inclut des utilisateurs dans trois domaines différents accédant à Skype entreprise Server 2019. Les lignes pleines indiquent qu’ils accèdent à un pool Skype entreprise Server dans leur propre domaine, tandis qu’une ligne en pointillés indique qu’ils accèdent à un pool dans une autre arborescence.
  
Comme vous pouvez le voir, les utilisateurs dans le même domaine, la même arborescence, ou même une arborescence différente peuvent accéder aux pools.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Plusieurs forêts dans un diagramme de topologie de forêt centrale](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype entreprise Server 2019 prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Si vous n’êtes pas certain de ce que vous avez, la forêt centrale de la topologie utilise des objets pour représenter les utilisateurs dans les autres forêts et héberge des comptes d’utilisateur pour tous les utilisateurs de la forêt.
  
Comment cela fonctionne-t-il ? Un produit de synchronisation d’annuaires (tel que Forefront Identity Manager ou FIM) gère les comptes d’utilisateur de votre organisation tout au long de leur existence. Lorsqu’un compte est créé ou supprimé d’une forêt, cette modification est synchronisée avec le contact correspondant dans la forêt centrale.
  
Clairement, si votre infrastructure AD est en place, le déplacement vers cette topologie n’est peut-être pas facile, mais si vous y êtes déjà, ou si vous planifiez encore votre infrastructure de forêt, il peut s’agir d’un bon choix. Vous pouvez centraliser votre déploiement de Skype entreprise Server 2019 au sein d’une seule forêt, tandis que les utilisateurs peuvent rechercher, communiquer et afficher la présence d’autres utilisateurs dans n’importe quelle forêt. Toutes les mises à jour de contacts de l’utilisateur sont gérées automatiquement avec le logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype entreprise
<a name="BKMK_multipleforestopology"> </a>

![Plusieurs forêts dans un diagramme de topologie de forêt de ressources](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Une topologie de forêt de ressources est également prise en charge ; Il s’agit d’une forêt dédiée à l’exécution de vos applications serveur, comme Microsoft Exchange Server et Skype entreprise Server 2019. Cette forêt de ressources héberge également une représentation synchronisée des objets utilisateur actifs, mais aucun compte d’utilisateur à connexion activée. La forêt de ressources est donc un environnement de services partagés pour les autres forêts dans lesquelles les objets utilisateur résident, et ils ont une relation d’approbation au niveau de la forêt avec la forêt de ressources.
  
Notez qu’Exchange Server peut être déployé dans la même forêt de ressources que Skype entreprise Server ou dans une autre forêt.
  
Pour déployer Skype entreprise Server 2019 dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs (si Microsoft Exchange Server est déjà dans l’environnement, cela peut être fait pour vous). Vous avez ensuite besoin d’un outil de synchronisation d’annuaires (par exemple, Forefront Identity Manager ou FIM) pour gérer les comptes d’utilisateurs tout au long de leur cycle de vie.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype entreprise avec Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à la topologie décrite dans la rubrique [plusieurs forêts dans une topologie de forêt de ressources Skype entreprise](system-requirements.md#BKMK_multipleforestopology).
  
Dans cette topologie, il existe une ou plusieurs forêts d’utilisateurs, et Skype entreprise Server est déployé dans une forêt de ressources dédiée. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt, et configuré pour un environnement hybride avec Exchange Online, ou des services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux. Aucun diagramme n’est disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt de ressources avec Skype entreprise Online et Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Présente deux forêts Active Directory, une forêt utilisateur et une forêt de ressources. Les deux forêts ont une relation d’approbation. Elles sont synchronisées avec Microsoft 365 à l’aide d’Azure AD Connect. Tous les utilisateurs sont activés pour Skype entreprise via Microsoft 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Dans ce scénario, il y a plusieurs forêts en local, avec une topologie de forêt de ressources. Il existe une relation de confiance totale entre les forêts Active Directory. L’outil Azure Active Directory Connect est utilisé pour synchroniser les comptes entre les forêts d’utilisateurs locales et Microsoft 365 ou Office 365.
  
 L’organisation dispose également de Microsoft 365 ou Office 365, et utilise [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) pour synchroniser ses comptes locaux avec Microsoft 365 ou Office 365. Les utilisateurs qui sont activés pour Skype entreprise sont activés via Microsoft 365 ou Office 365 et Skype entreprise online. Skype entreprise Server n’est pas déployé en local.
  
L’authentification unique est fournie par une batterie de serveurs AD FS (Active Directory Federation Services) située dans la forêt de l’utilisateur.
  
Dans ce scénario, il est pris en charge pour déployer Exchange sur site, Exchange Online, une solution Exchange hybride ou ne pas déployer Exchange. (Le diagramme affiche uniquement Exchange sur site, mais les autres solutions Exchange sont également entièrement prises en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt de ressources avec Skype entreprise hybride
<a name="BKMK_multipleforestopology"> </a>

Dans ce scénario, il existe une ou plusieurs forêts d’utilisateurs locales, et Skype entreprise est déployé dans une forêt de ressources dédiée et est configuré pour le mode hybride avec Skype entreprise online. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt, et peut être configuré pour une configuration hybride avec Exchange Online. Par ailleurs, les services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux.
  
Pour plus d’informations, consultez [la rubrique Configure a multi-Forest Environment for Hybrid Skype for Business](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype entreprise Server 2019 requiert DNS, pour les raisons suivantes :
  
- Le DNS permet à Skype entreprise Server 2019 de découvrir les serveurs ou pools internes, ce qui permet des communications de serveur à serveur.
    
- DNS permet aux ordinateurs clients de découvrir le pool frontal ou le serveur Standard Edition qui est utilisé pour les transactions SIP.
    
- Il associe des URL simples aux conférences avec les serveurs hébergeant ces conférences.
    
- DNS permet aux utilisateurs et aux ordinateurs clients externes de se connecter à vos serveurs Edge, ou au proxy inverse HTTP, pour la messagerie instantanée ou les conférences.
    
- Elle permet aux appareils de communications unifiées qui ne sont pas connectés de découvrir le pool frontal ou le serveur Standard Edition qui exécute le service Web de mise à jour des périphériques pour obtenir les mises à jour et les journaux d’envoi.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources de services Web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres de leurs appareils.
    
- Il est utilisé dans l’équilibrage de la charge DNS.
    
Il est important de noter que Skype entreprise Server 2019 ne prend pas en charge les noms de domaine internationaux (IDN).
  
Il est extrêmement important de se souvenir que tout nom de DNS est identique au nom de l’ordinateur configuré sur un serveur utilisé par Skype entreprise Server 2019. Plus précisément, nous ne pouvons pas avoir de noms courts dans l’environnement et vous devez avoir un nom de domaine complet pour le générateur de topologie.
  
Cela semble logique pour tout ordinateur déjà joint à un domaine, mais si vous avez un serveur Edge qui n’est pas joint à votre domaine, il peut avoir la valeur par défaut Short, sans suffixe de domaine. Assurez-vous que ce n’est pas le cas, dans DNS ou sur le serveur Edge, ou sur tout serveur ou pool Skype entreprise Server 2019.
  
N’utilisez pas les caractères Unicode ou les traits de soulignement. Les caractères standard (de A à z, a-z, 0-9 et les traits d’Union) sont pris en charge par les autorités de certification publiques et DNS externes (vous devez affecter des noms de domaine complets dans le certificat, il est important de ne pas oublier), vous pouvez donc vous faire part de nombreux problèmes si vous connaissez ce point à l’esprit depuis le début.
  
Pour plus d’informations sur les exigences DNS pour la mise en réseau, consultez la section [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) de notre documentation de planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des opérations les plus importantes que vous pouvez effectuer avant de procéder au déploiement est de vérifier que vos certificats sont dans l’ordre. Skype entreprise Server 2019 a besoin d’une infrastructure à clé publique (PKI) pour les connexions TLS (Transport Layer Security) et MTLS (Mutual Transport Layer Security). En gros, pour communiquer de manière standardisée de façon standardisée, Skype entreprise Server utilise des certificats émis par des autorités de certification (ca).
  
Voici quelques-unes des choses que Skype entreprise Server 2019 utilise les certificats pour :
  
- Connexions TLS entre clients et serveurs
    
- Connexions MTLS entre serveurs
    
- Fédération à l’aide de la découverte automatique de partenaires via le DNS
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- Communication avec les applications Web et Outlook Web Access (OWA)
    
La planification des certificats est donc obligatoire. À présent, examinons une liste de certaines choses que vous devez garder à l’esprit lors de la demande de certificats :
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide d’un algorithme de signature pris en charge par le système d’exploitation. Skype entreprise Server 2019 prend en charge la suite SHA-1 et SHA-2 de tailles de condensé (224, 256, 384 et 512 bits) et satisfait ou dépasse la configuration requise du système d’exploitation.
    
- L’auto-enregistrement est pris en charge pour les serveurs internes exécutant Skype entreprise Server 2019.
    
- L’enregistrement automatique n’est pas pris en charge pour les serveurs Edge de Skype entreprise Server 2019.
    
> [!NOTE]
> L’utilisation de l’algorithme de signature RSASSA-PSS n’est pas prise en charge et peut entraîner des erreurs de connexion et de transfert d’appel, entre autres problèmes. 
  
- Les longueurs de clés de chiffrement de 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé de 2048 et supérieures sont recommandées.
    
- L’algorithme de chiffrement par défaut, ou signature de hachage, est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
Il s’agit d’un grand nombre de niveaux de confort grâce à la demande de certificats auprès d’une autorité de certification. Nous allons vous donner des conseils supplémentaires ci-dessous pour faciliter votre planification.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

Vous aurez besoin de certificats pour la plupart de vos serveurs internes, et vous les obtiendrez très probablement à partir d’une autorité de certification interne (il s’agit d’une autorité de certification située dans votre domaine). Si vous le souhaitez, vous pouvez demander ces certificats à une autorité de certification externe (située sur Internet). Si vous vous demandez à quelle autorité de certification publique vous devez vous rendre, vous pouvez consulter la liste des [partenaires de certificat de communications unifiées](/SkypeForBusiness/certification/services-ssl) .
  
Vous aurez également besoin de certificats lorsque Skype entreprise Server 2019 communique avec d’autres applications et serveurs, tels que Microsoft Exchange Server. Cela doit être évidemment un certificat que ces autres applications et serveurs peuvent utiliser de manière prise en charge. Skype entreprise Server 2019 et d’autres produits Microsoft prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Si cela vous intéresse, nous disposons d’un article de planification supplémentaire pour OAuth et Skype entreprise Server 2019.
  
Skype entreprise Server 2019 prend également en charge (sans exiger) des certificats signés à l’aide de la fonction de hachage cryptographique SHA-256. Pour prendre en charge l’accès externe à l’aide de l’algorithme SHA-256, le certificat externe doit être émis par une autorité de certification publique à l’aide de l’algorithme SHA-256.
  
Pour simplifier les choses en toute simplicité, nous avons placé les exigences de certificat pour les serveurs Standard Edition, les pools frontaux et d’autres rôles dans les tableaux suivants, avec la contoso.com fictive utilisée pour des exemples (vous utiliserez probablement d’autres éléments pour votre environnement). Il s’agit de tous les certificats de serveur Web standard, avec des clés privées qui ne sont pas exportables. Voici quelques éléments supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) du serveur est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Chaque nom convivial de certificat doit être unique dans le magasin de l’ordinateur.
    
- Conformément aux exemples de noms ci-dessous, si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devez l’ajouter à l’autre nom de sujet du certificat (SAN).
    
Certificats pour les serveurs Standard Edition :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN = SE01. contoso. com ; SAN = SE01. contoso. com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |Sur les serveurs Standard Edition, le nom de domaine complet du serveur est le même que le nom de domaine complet du pool.  <br/> L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web interne (identique au nom de domaine complet du serveur)  <br/> AND  <br/> • Répondre aux URL simples  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = \* . contoso.com  <br/> |Vous ne pouvez pas remplacer le nom de domaine complet Web interne dans le générateur de topologie.  <br/> Si vous avez plusieurs URL simples de réunion, vous devez les inclure toutes en tant que San.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web externe  <br/> AND  <br/> • URL simple d’accès à distance  <br/> • Répondre aux URL simples par domaine SIP  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \* . contoso.com  <br/> |Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour les serveurs frontaux dans un pool frontal :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN = EEpool. contoso. com ; SAN = EEpool. contoso. com ; SAN = ee01. contoso. com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web interne (qui n’est pas le même que le nom de domaine complet du serveur)  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet du pool Skype entreprise  <br/> AND  <br/> • Répondre aux URL simples  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = \* . contoso.com  <br/> |Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web externe  <br/> AND  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \* . contoso.com  <br/> |Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour le directeur :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool directeur  <br/> |Nom de domaine complet (FQDN) du directeur, nom de domaine complet du pool directeur.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous aurez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP dont vous disposez).  <br/> |pool.contoso.com ; SAN = DIR01. contoso. com  <br/> Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web interne (identique au nom de domaine complet du serveur)  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet du pool Skype entreprise  <br/> AND  <br/> • Répondre aux URL simples  <br/> • URL simple d’accès à distance  <br/> • URL simple d’administration  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |SN = DIR01. contoso. com ; SAN = DIR01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = DIR01. contoso. com SAN = \* . contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet Web externe  <br/> AND  <br/> • Répondre aux URL simples par domaine SIP  <br/> • URL simple d’accès à distance  <br/> OR  <br/> • Entrée de caractère générique pour les URL simples  <br/> |Le nom de domaine complet du directeur de site Web externe doit être différent du pool frontal ou du serveur frontal.  <br/> SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = \* . contoso.com  <br/> |
   
Certificats pour le serveur de médiation autonome :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> Nom de domaine complet du serveur membre du pool  <br/> |SN = medsvr-pool.contoso.net ; SAN = medsvr-pool.contoso.net ; SAN = medsvr01. contoso. net  <br/> |
   
Certificats pour Survivable Branch Appliance (en particulier, Survivable Branch Appliance 2015 pour Skype entreprise Server 2019) :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appliance  <br/> |SIP. \< sipdomain \> (vous n’avez besoin que d’une seule entrée par domaine SIP)  <br/> |SN = sba01. contoso. net ; SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype entreprise Server 2019 prend en charge l’utilisation d’un **certificat public unique** pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification a/V, tous assurés via le (s) serveur (s) Edge. Votre interface interne Edge utilisera généralement un certificat privé émis par votre autorité de certification interne, mais si vous le souhaitez, vous pouvez également utiliser un certificat public pour cela, si elle provient d’une autorité de certification approuvée.
  
Votre proxy inverse (RP) doit également utiliser un certificat public et chiffre la communication de votre RP vers les clients et le RP vers les serveurs internes à l’aide du protocole HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

Si vous déployez la mobilité et que vous prenez en charge la découverte automatique pour les clients mobiles, vous devez inclure certaines autres entrées de nom de sujet supplémentaires sur vos certificats afin de prendre en charge les connexions sécurisées à partir des clients mobiles.
  
Vous aurez besoin de noms SAN pour la découverte automatique sur les certificats suivants :
  
- pool directeur
    
- pool frontal
    
- Proxy inverse
    
Les caractéristiques sont répertoriées dans les tableaux ci-dessous.
  
C’est là où une petite planification est intéressante, mais parfois vous avez déployé Skype entreprise Server 2019 sans avoir à déployer la mobilité, et cela se produit plus tard lorsque vous avez déjà des certificats dans votre environnement. Leur réémission via une autorité de certification interne est relativement facile, mais avec des certificats publics provenant d’une autorité de certification publique, qui peuvent être un peu plus pricy.
  
Si c’est ce que vous regardez, et si vous avez un grand nombre de domaines SIP (ce qui rend l’ajout de réseaux SAN plus onéreux), vous pouvez configurer votre proxy inverse de sorte qu’il utilise le protocole HTTP pour la demande de service de découverte automatique initiale, au lieu d’utiliser le protocole HTTPs (configuration par défaut). L’article [plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) contient plus d’informations à ce propos.
  
Conditions requises pour les certificats de pool directeur et de pool frontal :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN = lyncdiscoverinternal. \< sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \< sipdomain\>  <br/> |
   
Vous pouvez également utiliser SAN = \* . \< sipdomain\>
  
Conditions requises pour le certificat de proxy inverse (autorité de certification publique) :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \< sipdomain\>  <br/> |
   
Ce SAN doit être affecté au certificat qui est affecté à l’écouteur SSL sur votre proxy inverse.
  
> [!NOTE]
> Votre écouteur de proxy inverse va avoir des réseaux SAN pour vos URL de services Web externes. Voici quelques exemples : SAN = skypewebextpool01. contoso. com et dirwebexternal.contoso.com, si vous avez déployé le directeur (ce qui est facultatif). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype entreprise Server 2019 peut utiliser le même partage de fichiers pour tout le stockage de fichiers. Vous devez garder les points suivants à l’esprit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (direct Attached Storage) ou un réseau SAN (Storage Area Network), ainsi que sur un système de fichiers distribués (DFS) ainsi qu’un système RAID (Redundant Array of Independent Disks) pour les magasins de fichiers. Pour en savoir plus sur DFS pour Windows Server 2012, consultez [cette page DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Nous vous recommandons d’utiliser un cluster partagé pour le partage de fichiers. Si vous utilisez déjà un, vous devez clusteriser Windows Server 2012 ou version ultérieure

> [!Note]
> **Pourquoi les dernières fenêtres ?** Il est possible que les versions antérieures ne disposent pas des autorisations appropriées pour activer toutes les fonctionnalités. Vous pouvez utiliser l’administrateur de cluster pour créer les partages de fichiers. Pour plus d’informations, consultez cet article de support technique [comment créer des partages de fichiers sur un cluster](https://support.microsoft.com/help/224967) .
    
> [!CAUTION]
> Il est important de comprendre que l’utilisation du stockage rattaché au réseau (NAS) comme partage de fichiers n’est pas prise en charge ; vous pouvez donc utiliser l’une des options indiquées ci-dessus. Cette limitation de prise en charge est causée par la conception variable des périphériques NAS qui doivent fournir une adaptabilité du système de fichiers à l’ordinateur Windows Server qui accède au système de fichiers partagé des appareils.
  







