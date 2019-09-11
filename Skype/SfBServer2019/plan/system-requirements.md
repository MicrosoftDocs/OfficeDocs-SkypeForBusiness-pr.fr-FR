---
title: Configuration système requise pour Skype entreprise Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 'Résumé : Préparez vos serveurs et votre infrastructure de domaine Skype entreprise Server 2019 à ce sujet. Matériel, système d’exploitation, bases de données, logiciels, toutes les configurations requises et recommandations en matière de certificat, de partage de fichiers et d’Active Directory, sont là pour garantir la réussite de l’installation et du déploiement de votre batterie de serveurs.'
ms.openlocfilehash: e14da71795989356f24d7dc6ae72f94a649011e5
ms.sourcegitcommit: dc151bf4454ddec20db5cd133a42a67599c08d64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2019
ms.locfileid: "36838026"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Configuration système requise pour Skype entreprise Server 2019
 
**Résumé :** Préparez-vous à installer Skype entreprise Server 2019 à l’aide de cette rubrique. Le matériel, le système d’exploitation, les logiciels, les bases de données, les certificats, les direto actives, les DNS et Fileshares sont décrits ici. Toutes les exigences système et recommandations sont disponibles pour garantir la réussite de l’installation et du déploiement de votre batterie de serveurs.
  
Comme vous pouvez le constater, il est possible que vous deviez apporter certaines préparations avant de commencer le déploiement de Skype entreprise Server 2019. Cet article vous guide à travers la procédure de planification comme suit :
  
- [Matériel](system-requirements.md#Hardware)
  
- [Systèmes d’exploitation](system-requirements.md#OS)
  
- [Logiciels](system-requirements.md#Software)

- [Bases de données SQL principales](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [Certificats](system-requirements.md#Certs)
  
- [Partage de fichiers](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Matériel pour Skype entreprise Server 2019
<a name="Hardware"> </a>

Après avoir effectué votre topologie (et si ce n’est pas le cas, vous pouvez consulter la section [notions de base pour Skype entreprise Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), il est temps de réfléchir aux serveurs. Les serveurs 2019 de Skype entreprise Server nécessitent un matériel 64 bits. Nos recommandations pour le matériel sont indiquées ci-dessous. Ces conditions ne sont pas obligatoires, mais elles reflètent les exigences nécessaires aux performances optimales. La documentation de planification des capacités vous aidera à déterminer si vous avez besoin de capacités supérieures, en fonction des circonstances.
  
Matériel recommandé pour les serveurs Standard Edition :

|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Processeur Intel Xeon E5-2673 v3 double processeur, 6 cœurs, 2,4 gigahertz (GHz) ou version ultérieure.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles 2019 de Skype entreprise Server.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 lecteurs de disque dur, ou plus de 10000, avec au moins 72 Go d’espace libre sur le disque dur (deux des disques avec RAID 1 et 6 avec RAID 10).  <br/> OU  <br/> • Lecteurs d’État SSD (SSDs) en mesure d’offrir un espace libre et des performances similaires pour les disques mécaniques 8 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations à double ou à hébergement multiple ne sont **pas** prises en charge pour les serveurs frontaux, les serveurs dorsaux et les serveurs Standard Edition. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez disposer de systèmes de gestion hors-bande tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.  <br/> |


Matériel recommandé pour les serveurs frontaux et les serveurs principaux :
  
|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Processeur Intel Xeon E5-2673 v3 double processeur, 6 cœurs, 2,4 gigahertz (GHz) ou version ultérieure. <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles 2019 de Skype entreprise Server.  <br/> |
|Mémoire  <br/> |64 gigaoctets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 lecteurs de disque dur, ou plus de 10000, avec au moins 72 Go d’espace libre sur le disque dur (deux des disques avec RAID 1 et 6 avec RAID 10).  <br/> OU  <br/> • Lecteurs d’État SSD (SSDs) en mesure d’offrir un espace libre et des performances similaires pour les disques mécaniques 8 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations à double ou à hébergement multiple ne sont **pas** prises en charge pour les serveurs frontaux, les serveurs dorsaux et les serveurs Standard Edition. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez disposer de systèmes de gestion hors-bande tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.  <br/> |
   
Matériel recommandé pour les serveurs de périmètre, serveurs de médiation autonome et directeurs :
  
|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Processeur Intel Xeon E5-2673 v3 double processeur, 6 cœurs, 2,4 gigahertz (GHz) ou version ultérieure.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles 2019 de Skype entreprise Server.  <br/> |
|Mémoire  <br/> |32 gigaoctets.  <br/> |
|Disque  <br/> |SOIT :  <br/> • 4 disques durs de 4 Mo ou plus 10000 avec au moins 72 Go d’espace libre sur le disque (les disques doivent être dans une configuration RAID 1 2x).  <br/> OU  <br/> • Lecteurs d’État SSD (SSDs) en mesure d’offrir un espace libre et des performances similaires pour les disques mécaniques 4 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations à double ou à hébergement multiple ne sont **pas** prises en charge pour les serveurs et les directeurs d’interopérabilité vidéo. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau double port, 1 Gbit/s ou plus (ou deux cartes réseau appariées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et à une adresse IP unique, pour un total de deux paires).  <br/> Sur les serveurs de médiation autonomes, l’installation de cartes d’interface réseau supplémentaires (NIC) permettant de configurer une adresse IP RTC spécifique est prise en charge.  <br/> |


> [!NOTE]
> Quel que soit le rôle du serveur, nous vous conseillons également de consulter les paramètres matériels suivants pour Skype entreprise Server 2019 (cela varie en fonction de la marque du matériel que vous avez acheté, veuillez consulter la documentation du fabricant pour obtenir des informations spécifiques) :
> - La configuration du BIOS doit être définie sur plat à partir de NUMA.
> - Activez l’hyperthreading.
> - Le paramètre de la file d’attente RSS doit être défini sur 8 files d’attente.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Systèmes d’exploitation pour Skype entreprise Server 2019
<a name="OS"> </a>

Lorsque le matériel est en place, vous devez utiliser le système d’exploitation qui vous permet d’installer et d’utiliser correctement Skype entreprise Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Tout ce qui n’est pas le cas des systèmes d’exploitation mentionnés ici ne fonctionne pas correctement ; Veuillez ne pas essayer pour l’installation de Skype entreprise Server 2019. Par exemple, l’option Server Core n’est pas répertoriée et n’est donc pas prise en charge.

> [!NOTE]
> 
> Si vous installez le centre d’administration Windows 2019 sur votre ordinateur Windows Server 2019, il vous invite à entrer un port à écouter. Liklihood vous pouvez choisir le port 443, mais si vous avez installé Skype entreprise Server 2019 sur votre ordinateur, ou si vous avez installé Skype entreprise Server 2019 sur celui-ci, vous devez choisir un autre numéro de port.
> 
>Pourquoi ? Si le centre d’administration Windows 2019 est en cours d’exécution sur le port 443, vous ne pourrez pas vous connecter au serveur à l’aide du panneau de configuration Skype pour les entreprises ou vous ne pourrez pas vous connecter à un service Web interne exécuté sur le serveur (service Web du carnet d’adresses). , Service de découverte automatique, service de tickets d’identification, etc.).  En fait, vous ne pourrez pas vous connecter à l’URL d’un service Web interne. Pour ce faire, vous devez choisir un autre port, ou vous voulez placer le centre d’administration Windows 2019 sur un serveur avec Skype entreprise Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Logiciels qui doivent être installés avant le déploiement de Skype entreprise Server 2019
<a name="Software"> </a>

Vous devrez peut-être installer ou configurer certains éléments pour n’importe quel serveur exécutant Skype entreprise Server 2019. Celles-ci sont répertoriées ci-dessous, suivies d’autres exigences relatives aux rôles de serveur spécifiques.
  
 **Tous les serveurs :**
  
|**Logiciel/rôle**|**Détails**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tous les serveurs Skype entreprise Server requièrent l’installation de Windows PowerShell 3,0.  <br/> • Cela doit être installé par défaut avec Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Services WCF est une **fonctionnalité** qui est installée en tant que fonctionnalité Windows, dans le **Gestionnaire de serveur**, aucun téléchargement n’est nécessaire. <br/> • Vous devez vous assurer que, lorsque vous installez cette fonction ou qu’elle est déjà installée et que vous la Vérifiez, l’option d' **activation http** est également activée et installée, comme suit : <br/> ![Capture d’écran présentant l’option Activation HTTP des fonctionnalités .NET Framework 4.5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Ne vous inquiétez pas si vous obtenez une fenêtre contextuelle supplémentaire indiquant que d’autres éléments doivent être installés pour que l’Activation HTTP puisse être installée. C’est normal ; Cliquez sur OK et continuez. Si vous ne parvenez pas à afficher cette fenêtre contextuelle, vous pouvez supposer que les éléments suivants sont déjà installés et déplacés.  <br/> Microsoft .NET Framework est généralement installé lorsque Windows Server 2016 est installé. Le service Skype entreprise Server nécessite Microsoft .NET Framework 4,7 ou 4,8, donc vous devez probablement le mettre à jour. La mise à jour est disponible [ici](https://support.microsoft.com/en-us/help/3186497/the-net-framework-4-7-offline-installer-for-windows/) .<br/> |
|Media Foundation  <br/> |Pour Windows Server 2016, le runtime du format Windows Media s’installe avec Microsoft Media Foundation.  <br/> Tous les serveurs front-end et les serveurs Standard Edition utilisés pour les conférences requièrent l’exécution du format Windows Media Runtime pour exécuter les fichiers Windows Media audio (. WMA) que les applications de parc d’appels, d’annonce et de groupe de réponse sont lues pour les annonces et la musique.  <br/> |
|Windows Identity Foundation  <br/> |Nous avons besoin de Windows Identity Foundation 3,5 pour prendre en charge les scénarios d’authentification de serveur à serveur pour Skype entreprise Server 2019.  <br/> • Pour Windows Server 2016, vous n’avez rien à télécharger. Ouvrez le **Gestionnaire de serveur** et accédez à l’**Assistant Ajout de rôles et de fonctionnalités**. **Windows Identity Foundation 3.5** est listé sous la section **Fonctionnalités**. S’il est sélectionné, c’est bien. Dans le cas contraire, sélectionnez-le, puis cliquez sur **suivant** pour atteindre le bouton **installer** . <br/> |
|Outils d’administration de serveur distant  <br/> |Outils d’administration de rôles : outils AD DS et AD LDS  <br/> |
   
 **Les serveurs front-end et Standard Edition Server ont également besoin des éléments suivants :**
  
|**Logiciel/rôle**|**Détails**|
|:-----|:-----|
|services Internet (IIS)  <br/> |IIS est requis sur tous les serveurs frontaux, ainsi que sur tous les serveurs Standard Edition, avec les modules suivants sélectionnés :  <br/> • Principales fonctionnalités HTTP : document par défaut, erreurs HTTP, contenu statique  <br/> • Santé et diagnostics : journalisation HTTP, outils de journalisation, suivi  <br/> • Performances : compression de contenu statique, compression de contenu dynamique  <br/> • Sécurité : filtrage des demandes, authentification du mappage de certificat client, authentification Windows  <br/> • Développement d’applications : extensibilité .NET 3,5, extensibilité .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensions ISAPI et filtres ISAPI  <br/> • Outils de gestion : console de gestion IIS, scripts et outils de gestion IIS  <br/> Notez que l’accès anonyme est également nécessaire, mais que vous l’obtenez lorsque vous installez IIS, de sorte que vous n’avez pas d’emplacement pour le sélectionner dans la liste.  <br/> |
|Module d’exécution du format Windows Media  <br/> | Pour Windows Server 2016, vous devez installer la fonctionnalité **Media Foundation** dans le **Gestionnaire de serveur**. Vous pouvez démarrer l’installation de Skype entreprise Server 2019 sans cela, mais vous serez invité à l’installer, puis à redémarrer le serveur avant la poursuite de l’installation de Skype entreprise Server 2019. Nous vous conseillons de le faire à l’avance. <br/> |
|Silverlight  <br/> |Vous pouvez installer la dernière version de Silverlight [ici](https://www.microsoft.com/silverlight/).  <br/> |
   
Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser ceci :
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **Les directeurs ont également besoin des éléments suivants :**
  
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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bases de données principales qui fonctionneront avec Skype entreprise Server 2019
<a name="DBs"> </a>

Lors de l’installation de Skype entreprise Server 2019 Standard Edition, vous avez SQL Server 2016 Express (64-bit Edition).

Skype entreprise Server 2019 Enterprise Edition nécessite SQL Server complet, comme indiqué ci-dessous (seule l’édition 64 bits ; n’utilisez pas les éditions 32 bits) :
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64-bit Edition) et vous devez l’exécuter avec les mises à jour les plus récentes.  <br/> |Microsoft SQL Server 2017 (64-bit Edition) et vous devez l’exécuter avec les mises à jour les plus récentes.  <br/> |
Microsoft SQL Server 2016 (64-bit Edition) et vous devez l’exécuter avec les mises à jour les plus récentes.|
 |

Si vous ne voyez pas l’édition SQL Server que vous voulez utiliser dans la liste, vous ne pouvez pas l’utiliser.
  
> [!NOTE]
> Vous devez également installer SQL Server Reporting Services pour le rôle serveur de surveillance. 
  
### <a name="sql-clustering-and-sql-always-on"></a>Regroupement SQL et SQL toujours activé

Le regroupement SQL avec Skype entreprise Server 2019 est pris en charge. Si vous souhaitez configurer le regroupement SQL, cette opération s’effectue dans SQL Server.
  
Vérifiez que vous disposez d’une configuration active/passive pour le regroupement SQL, qui est prise en charge. Ne partagez pas le nœud passif avec d’autres instances SQL.
  
Vous pouvez avoir ce qui suit pour la mise en cluster du basculement :
  
Deux nœuds :
  
- Microsoft SQL Server 2019 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.
- Microsoft SQL Server 2017 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.
- Microsoft SQL Server 2016 standard (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

Six nœuds :
  
- Microsoft SQL Server 2019 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.
- Microsoft SQL Server 2017 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.
- Microsoft SQL Server 2016 entreprise (64-bit Edition) et nous vous recommandons de l’utiliser avec le dernier Service Pack.

L’application SQL toujours activée est prise en charge et vous pouvez en savoir plus à son sujet dans la [haute disponibilité du serveur principal dans Skype entreprise Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recommandations en matière d’installation serveur supplémentaires :
  
N’installez pas le logiciel client Microsoft Internet Security and Acceleration (ISA) Server ou tout autre logiciel de fournisseurs de services Layers (Winsock Layerd services), ou un logiciel de contrôle de réseau antiviral (ou logiciel antivirus), sur tout serveur principal ou serveur de médiation autonome. Des performances de trafic multimédia médiocres ont été constatées lors de l’installation de ce logiciel.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Bien que la plupart des données de configuration pour les serveurs et les services soient stockées dans le magasin de gestion centralisée de Skype entreprise Server 2019, certaines éléments sont toujours stockés dans Active Directory :
  
|**Objets Active Directory**|**Types d’objets**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions pour Skype entreprise Server 2015 et Lync Server 2013 afin d’assurer la compatibilité descendante avec les versions prises en charge précédentes  <br/> |
|Données  <br/> |URI SIP de l’utilisateur et autres paramètres utilisateur  <br/> |
||Objets de contact pour applications (par exemple, l’application Response Group et l’application attendant)  <br/> |
||Données publiées pour la compatibilité descendante  <br/> |
||Un point de contrôle de service (SCP) pour le magasin de gestion central  <br/> |
||Compte d’authentification Kerberos (objet facultatif de l’ordinateur)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation pour les contrôleurs de domaine

Les systèmes d’exploitation de contrôleur de domaine suivants peuvent être utilisés :
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Le niveau de fonctionnalité du domaine de tout domaine sur lequel vous déployez Skype entreprise Server 2019, ainsi que le niveau fonctionnel de la forêt de n’importe quelle forêt de déploiement de Skype entreprise Server 2019, doit être l’un des éléments suivants :
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Pouvez-vous avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, tant qu’il existe également des contrôleurs de domaine accessibles en écriture.
  
Il est important de savoir que Skype entreprise Server 2019 ne prend pas en charge les domaines à mention unique. Que sont-ils ? Si vous avez un domaine racine appelé contoso. local, cela va être bien. Si vous avez un domaine racine appelé simplement local, il n’y a pas de fonctionnement et il n’est pas pris en charge en conséquence. Ce article de la [base de connaissances](https://support.microsoft.com/kb/300684/en-us)contient quelques informations supplémentaires.
  
Skype entreprise Server 2019 ne supporte pas non plus le changement de nom de domaines. Si vous devez vraiment renommer votre domaine, vous devez désinstaller Skype entreprise Server 2019, effectuer le changement de nom de domaine, puis réinstaller Skype entreprise Server 2019.
  
Enfin, vous avez peut-être affaire à un domaine avec un environnement AD DS verrouillé et c’est possible. Pour plus d’informations sur le déploiement de Skype entreprise Server 2019, vous devez disposer d’un environnement AD DS verrouillé dans la documentation de déploiement.
  
### <a name="ad-topologies"></a>Topologies AD

Les topologies prises en charge dans Skype entreprise Server 2019 sont les suivantes :
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
    
- Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
    
Nous avons des diagrammes et des descriptions qui vous aideront à déterminer quelle topologie vous avez dans votre environnement ou ce que vous devrez configurer avant d’installer Skype entreprise Server 2019. Pour le simplifier, nous avons également une touche :
  
![Il s’agit d’une clé pour les icônes utilisées pour les schémas de topologie Skype Entreprise.](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Schéma d’une forêt Active Directory unique avec un seul domaine](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Ce n’est pas aussi simple que ça. Il s’agit d’une seule forêt de domaine, une topologie commune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Schéma d’une forêt unique avec un arbre unique et plusieurs domaines](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme illustre de nouveau une forêt unique, mais elle a un ou plusieurs domaines enfants aussi (il en existe trois dans cet exemple spécifique). Le domaine dans lequel les utilisateurs sont créés peut être différent de celui sur lequel Skype entreprise Server 2019 est déployé. Est-ce problématique ? Il est important de garder à l’esprit que lorsque vous déployez une grappe frontale Skype entreprise Server, tous les serveurs de ce pool doivent faire partie d’un domaine unique. Vous pouvez bénéficier d’une administration entre domaines via Skype entreprise Server pour la prise en charge de groupes d’administrateurs Windows universels.
  
Dans l’illustration ci-dessus, vous pouvez voir que les utilisateurs d’un domaine sont en mesure d’accéder aux pools de serveurs Skype entreprise du même domaine ou à partir de différents domaines, même s’ils se trouvent dans un domaine enfant.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Schéma d’une forêt unique avec des arbres multiples et des espaces de noms disjoints](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Il est possible que vous disposiez d’une topologie similaire à celle-ci, dans laquelle vous disposez d’une seule forêt, mais que cette forêt comporte plusieurs domaines, avec des espaces de noms distincts. Dans le cas présent, il s’agit d’une bonne illustration, car elle inclut les utilisateurs de trois domaines différents qui accèdent à Skype entreprise Server 2019. Les lignes pleines indiquent qu’elles permettent d’accéder à un pool de serveurs Skype entreprise dans leur propre domaine, tandis qu’un trait en pointillés indique qu’il y a un groupe dans une même arborescence.
  
Comme vous pouvez le voir, les utilisateurs qui se trouvent dans le même domaine, la même arborescence ou même une autre arborescence peuvent accéder aux pools avec succès.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Schéma de forêts multiples dans une topologie de forêts centralisée](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype entreprise Server 2019 prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Si vous n’êtes pas sûr de ce que vous avez, la forêt centrale dans la topologie utilise des objets pour représenter les utilisateurs dans les autres forêts et héberge les comptes d’utilisateurs pour tous les utilisateurs de la forêt.
  
Comment cela fonctionne-t-il ? Un produit de synchronisation d’annuaires (par exemple, Forefront Identity Manager ou FIM) gère les comptes d’utilisateurs de votre organisation tout au long de leur existence. Lorsqu’un compte est créé ou supprimé d’une forêt, ce changement est synchronisé avec le contact correspondant dans la forêt centrale.
  
Pour l’instant, si votre infrastructure publicitaire est en place, le déplacement vers cette topologie peut ne pas être facile, mais si vous en êtes déjà là, ou si vous continuez à planifier son infrastructure de forêt, il peut s’avérer utile. Vous pouvez centraliser votre déploiement de Skype entreprise Server 2019 au sein d’une même forêt, même si les utilisateurs peuvent rechercher, communiquer et afficher la présence d’autres utilisateurs de n’importe quelle forêt. Toutes les mises à jour des contacts utilisateur sont gérées automatiquement à l’aide du logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise
<a name="BKMK_multipleforestopology"> </a>

![Forêts multiples dans un schéma de topologie de forêts de ressources](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Une topologie de forêt de ressources est également prise en charge. C’est là où une forêt est dédiée à l’exécution de vos applications serveur, comme Microsoft Exchange Server et Skype entreprise Server 2019. Cette forêt de ressources héberge également une représentation synchronisée des objets d’utilisateurs actifs, mais aucun compte utilisateur à connexion activée. La forêt de ressources est donc un environnement de services partagés pour les autres forêts dans lesquelles les objets utilisateur résident et ceux-ci ont une relation de confiance au niveau de la forêt avec la forêt de ressources.
  
Notez qu’Exchange Server peut être déployé dans la même forêt de ressources que Skype entreprise Server ou dans une autre forêt.
  
Pour déployer Skype entreprise Server 2019 dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts des utilisateurs (si Microsoft Exchange Server est déjà dans l’environnement, cela peut être fait pour vous). Par exemple, vous avez besoin d’un outil de synchronisation d’annuaires (par exemple, Forefront Identity Manager ou FIM) pour gérer les comptes d’utilisateur par le biais de leur cycle de vie.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à celle décrite dans la rubrique [Plusieurs forêts d’une topologie de forêts de ressources Skype Entreprise avec Exchange Online](system-requirements.md#BKMK_multipleforestopology).
  
Dans cette topologie, il existe une ou plusieurs forêts utilisateur et Skype entreprise Server est déployé dans une forêt de ressources dédiée. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt et configuré pour une connexion hybride avec Exchange Online, ou les services de messagerie peuvent être fournis uniquement par Exchange Online pour les comptes locaux. Aucun diagramme n’est disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt de ressources Skype Entreprise Online et Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Représente deux forêts AD : une forêt d’utilisateurs et une forêt de ressources. Les deux forêts sont liées par une relation de confiance. Elles sont synchronisées avec Office 365 via Azure AD Connect. Tous les utilisateurs peuvent accéder à Skype Entreprise via Office 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Dans ce scénario, il existe plusieurs forêts sur site avec une topologie de forêt de ressources. Il existe une relation d’approbation totale entre les forêts Active Directory. L’outil Azure Active Directory Connect est utilisé pour synchroniser des comptes entre les forêts d’utilisateurs sur site et Office 365.
  
 L’organisation dispose également d’Office 365 et utilise [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) pour synchroniser leurs comptes locaux avec Office 365. Les utilisateurs activés pour Skype entreprise sont activés par le biais d’Office 365 et de Skype entreprise online. Skype entreprise Server n’est pas déployé en local.
  
L’authentification unique est fournie par une batterie de serveurs Active Directory Federation Services située dans la forêt utilisateur.
  
Dans ce scénario, il est pris en charge pour le déploiement d’Exchange en local, d’Exchange Online, d’une solution Exchange hybride ou d’un déploiement Exchange. (Le schéma présente uniquement Exchange en local, mais les autres solutions Exchange sont entièrement prises en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt de ressources et un déploiement hybride de Skype Entreprise 
<a name="BKMK_multipleforestopology"> </a>

Dans ce scénario, il existe un ou plusieurs forêts utilisateurs locales et Skype entreprise est déployé dans une forêt de ressources dédiées et est configuré pour le mode hybride dans Skype entreprise online. Exchange Server peut être déployé sur site dans la même forêt de ressources ou dans une autre forêt et peut être configuré pour une connexion hybride avec Exchange Online. Vous pouvez également fournir des services de messagerie exclusivement via Exchange Online pour les comptes locaux.
  
Pour plus d’informations, reportez-vous à [la rubrique Configuration d’un environnement de forêts multiples pour Skype entreprise hybride](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Pour les raisons suivantes, Skype entreprise Server 2019 nécessite le système DNS :
  
- Ce service permet aux utilisateurs de Skype entreprise Server 2019 de découvrir les serveurs internes ou les pools, ce qui permet des communications serveur à serveur.
    
- DNS permet aux ordinateurs clients de découvrir le pool frontal ou le serveur Standard Edition utilisé pour les transactions SIP.
    
- Il associe des URL simples pour des conférences avec les serveurs hébergeant ces conférences.
    
- Le système DNS permet aux utilisateurs externes et aux ordinateurs clients de se connecter à vos serveurs Edge ou au proxy HTTP inversement pour la messagerie instantanée ou les conférences.
    
- Il permet aux appareils de communications unifiées (UC) qui ne sont pas connectés dans la découverte du pool frontal ou d’un serveur Standard Edition qui exécute le service Web de mise à jour des périphériques pour obtenir des mises à jour et envoyer des journaux.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.
    
- Elle est utilisée dans l’équilibrage de charge DNS.
    
Il est important de noter que Skype entreprise Server 2019 ne prend pas en charge les noms de domaines internationaux (IDNs).
  
Il est très important de noter que le nom de l’ordinateur que vous utilisez est identique à celui configuré sur n’importe quel serveur utilisé par Skype entreprise Server 2019. Plus précisément, nous ne pouvons pas avoir de noms courts dans l’environnement, et doivent avoir des noms de domaine complets pour le générateur de topologie.
  
Cela semble logique pour tout ordinateur déjà joint à un domaine, mais si vous avez un serveur Edge qui n’est pas joint à votre domaine, il est possible qu’il ait un nom court par défaut, sans suffixe de domaine. Pour cela, assurez-vous que ce n’est pas le cas, que ce soit dans DNS ou sur le serveur Edge, ou sur un serveur ou un pool Skype entreprise Server 2019.
  
Ne pas utiliser les caractères ou les traits de soulignement. Les caractères standard (qui sont A-Z, a-z, 0-9 et les traits d’Union) sont pris en charge par les autorités de certification DNS et publique externes (vous devez attribuer des noms de domaine complets à l’élément SN du certificat, il est important de ne pas oublier), il est donc important de ne pas perdre de temps si vous avez des problèmes. ce n’est pas tout à l’esprit du début.
  
Pour en savoir plus sur les exigences du DNS pour le réseau, consultez la section [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) de notre documentation consacrée à la planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des tâches les plus importantes à effectuer avant le déploiement est de vérifier que les certificats sont en ordre. Skype entreprise Server 2019 a besoin d’une infrastructure à clé publique (PKI) pour les connexions TLS (Transport Layer Security) et Mutual Transport Layer Security (MTLS). Fondamentalement, pour communiquer de manière sécurisée, Skype entreprise Server utilise des certificats émis par les autorités de certification (ca).
  
Voici quelques-unes des raisons pour lesquelles Skype entreprise Server 2019 utilise des certificats pour :
  
- Connexions TLS entre clients et serveurs
    
- Connexions MTLS entre serveurs
    
- Fédération utilisant une découverte automatique de DNS des partenaires
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- Discuter avec des applications Web et Outlook Web Access (OWA)
    
Le planning de certification est donc obligatoire. Examinons maintenant la liste de quelques éléments à garder à l’esprit lors de la demande de certificats :
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation. Skype entreprise Server 2019 prend en charge la suite SHA-1 et SHA-2 de tailles synthétiques (224, 256, 384 et 512) et respecte ou dépasse la configuration requise du système d’exploitation.
    
- L’inscription automatique est prise en charge pour les serveurs internes exécutant Skype entreprise Server 2019.
    
- L’enregistrement automatique n’est pas pris en charge par les serveurs Edge Skype entreprise Server 2019.
    
> [!NOTE]
> L’algorithme de signature RSASSA-PSS n’est pas pris en charge et peut entraîner entre autres des erreurs de connexion et de transfert d’appels.  
  
- Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé supérieures ou égales à 2048 sont recommandées.
    
- L’algorithme digest, ou de signature de hachage, par défaut est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
Ce n’est qu’un grand nombre d’entre eux et il existe de nombreux niveaux de confort liés à la demande de certificats d’une autorité de certification. Nous vous offrons quelques conseils supplémentaires ci-dessous pour rendre votre planification aussi simple que possible.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

Vous aurez besoin de certificats pour la plupart de vos serveurs internes, et il est probable que vous les obteniez auprès d’une autorité de certification interne (CA située dans votre domaine). Si vous le souhaitez, vous pouvez demander ces certificats auprès d’une autorité de certification externe (qui se trouve sur Internet). Si vous vous demandez ce que vous devez faire, vous pouvez consulter la liste des [partenaires de certification de communications unifiées](/SkypeForBusiness/certification/services-ssl) .
  
Vous aurez également besoin de certificats lorsque Skype entreprise Server 2019 communiquera avec d’autres applications et serveurs, comme Microsoft Exchange Server. Cela doit évidemment être un certificat que ces autres applications et serveurs peuvent utiliser d’une manière prise en charge. Skype entreprise Server 2019 et d’autres produits Microsoft prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Si cela vous intéresse, nous avons un article de planification supplémentaire pour les appels OAuth et Skype entreprise Server 2019.
  
Skype entreprise Server 2019 inclut également la prise en charge des certificats (sans nécessiter) signés à l’aide de la fonction de hachage de chiffrement SHA-256. Pour favoriser l’accès externe à l’aide de SHA-256, le certificat externe doit être émis par une autorité de certification publique utilisant SHA-256.
  
Pour vous faciliter la tâche, nous avons mis en place la configuration requise pour les certificats pour les serveurs Standard Edition, les pools de front-end et d’autres rôles, dans les tableaux ci-dessous, l’utilisation de contoso.com votre environnement). Il s’agit de tous les certificats de serveur web standard, avec des clés privées qui ne sont pas exportables. Quelques points supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Le nom convivial de chaque certificat doit être unique dans le magasin de l’ordinateur.
    
- Comme pour les exemples de noms ci-dessous, si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, ils doivent être ajoutés au nom de l’objet du certificat.
    
Certificats pour les serveurs Standard Edition :
  
|**Certificat**|**Nom de l’objet/nom usuel**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |Sur les serveurs Standard Edition, le nom de domaine complet du serveur est identique au nom de domaine complet du pool.  <br/> L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web interne (qui est identique au nom de domaine complet du serveur).  <br/> ET  <br/> • Respecter des URL simples  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN =\*. contoso.com  <br/> |Vous ne pouvez pas remplacer le FQDN Web interne dans le générateur de topologie.  <br/> Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant que sous-réseau.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web externes  <br/> ET  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • Respecter les URL simples par domaine SIP  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour serveurs frontaux dans une liste frontale :
  
|**Certificat**|**Nom de l’objet/nom usuel**|**Autre nom du sujet**|**Exemple**|**Commentaires**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool et nom de domaine complet du serveur.  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • Nom de domaine complet (FQDN) Web interne (différent du nom de domaine complet du serveur)  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet (FQDN) du pool Skype entreprise  <br/> ET  <br/> • Respecter des URL simples  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web externes  <br/> ET  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN =\*. contoso.com  <br/> |Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour le directeur :
  
|**Certificat**|**Nom de l’objet/nom usuel**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool de directeurs  <br/> |Nom de domaine complet (FQDN) du réalisateur du pool de réalisateurs.  <br/> Si ce pool est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous aurez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP que vous utilisez).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Si ce pool de directeurs est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous devez également disposer de SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web interne (qui est identique au nom de domaine complet du serveur).  <br/> • Nom de domaine complet du serveur  <br/> • Nom de domaine complet (FQDN) du pool Skype entreprise  <br/> ET  <br/> • Respecter des URL simples  <br/> • URL d’accès à la Conférence rendez-vous  <br/> • URL simple d’administration  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = DIR01. contoso. com SAN =\*. contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN Web externes  <br/> ET  <br/> • Respecter les URL simples par domaine SIP  <br/> • URL d’accès à la Conférence rendez-vous  <br/> OU  <br/> • Entrée générique pour les URL simples  <br/> |Le FQDN Web de Director doit être différent du serveur frontal ou du pool frontal.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificats pour un serveur de médiation autonome :
  
|**Certificat**|**Nom de l’objet/nom usuel**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> Nom de domaine complet du serveur membre du pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificats pour un appareil de branchement survivant (plus précisément, appareil de branchement Survivable 2015 pour Skype entreprise Server 2019) :
  
|**Certificat**|**Nom de l’objet/nom usuel**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appareil  <br/> |SIP. \<sipdomain\> (vous n’avez besoin que d’une seule entrée par domaine SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype entreprise Server 2019 prend en charge l’utilisation d’un **certificat public unique** pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification a/V, qui est fourni par le biais du ou des serveurs de bord. Votre interface interne Edge utilise généralement un certificat privé émis par votre autorité de certification interne, mais si vous le souhaitez, vous pouvez également utiliser un certificat public pour cela, s’il provient d’une autorité de certification approuvée.
  
Votre proxy inverse (RP) utilise également un certificat public et chiffre la communication de votre RP aux clients et du RP aux serveurs internes via HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

Si vous déployez une mobilité et que vous prenez en charge la découverte automatique pour les clients mobiles, vous aurez besoin d’ajouter d’autres inscriptions de nom de sujet sur vos certificats pour prendre en charge les connexions sécurisées à partir des clients mobiles.
  
Pour une découverte automatique des certificats suivants, vous aurez besoin des noms de SAN :
  
- pool de directeurs
    
- pool de serveurs frontaux
    
- Proxy inverse
    
Les spécificités sont répertoriées dans les tableaux ci-dessous.
  
C’est là où un peu de préversion est satisfaisant, mais parfois, vous avez déployé Skype entreprise Server 2019 sans vous soucier du déploiement de la mobilité et celle-ci apparaît plus tard lorsque vous avez déjà des certificats dans votre environnement. La réémission de ces dernières par le biais d’une autorité de certification interne est généralement relativement simple, mais avec les certificats publics d’une autorité de certification publique qui peuvent être un peu plus pricy.
  
Si ce n’est pas le cas, et si vous disposez d’un grand nombre de domaines SIP (ce qui permet d’ajouter des réseaux SANS frais supplémentaires), vous pouvez configurer votre proxy inverse de façon à ce que la demande de service de découverte automatique initiale s’utilise au lieu d’utiliser HTTPs (par défaut). Configuration). Pour plus d’informations, reportez-vous à l’article [plan de mobilité](../../SfbServer/plan-your-deployment/mobility.md) .
  
Conditions requises pour les certificats du pool de réalisateur et du pool frontal :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Vous pouvez également utiliser le SAN\*. \<sipdomain\>
  
Exigences relatives au certificat de proxy inverse (autorité de certification publique)
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Ce SAN doit être attribué au certificat qui est affecté à l’écouteur SSL sur votre proxy inverse.
  
> [!NOTE]
> L’écouteur de proxy inverse va disposer de San pour vos URL de services Web externes. Par exemple, il peut s’agir de SAN = skypewebextpool01. contoso. com et dirwebexternal.contoso.com, si vous avez déployé le directeur (facultatif). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype entreprise Server 2019 peut utiliser le même partage de fichiers pour tout le stockage de fichiers. Gardez à l’esprit ce qui suit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (Direct Attached Storage) ou un réseau de stockage SAN (Storage Area Network), dont un système de fichiers distribués (DFS) et sur une solution RAID (Redundant Array Of Independent Disks) pour les magasins de fichiers. Pour plus d’informations sur le système de fichiers DFS pour Windows Server 2012, consultez [cette page DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Nous vous recommandons d’utiliser un cluster partagé pour le partage de fichiers. Si vous utilisez déjà une version de Windows Server 2012 ou version ultérieure

> [!Note]
> **Pourquoi vous avez la dernière version de Windows ?** Les versions plus anciennes ne disposent pas des autorisations appropriées pour activer toutes les fonctionnalités. Vous pouvez utiliser l’administrateur de cluster pour créer le partage de fichiers. Pour plus d’informations, consultez cet article [du support sur la création de partages de fichiers sur un cluster](https://support.microsoft.com/help/224967) .
    
> [!CAUTION]
> Vous devez savoir que le dispositif de stockage réseau (NAS) ne prend pas en charge le partage de fichiers. Vous devez donc utiliser l’une des options proposées ci-après. Cette limitation du support technique est provoquée par la conception variable d’appareils NAS qui doivent fournir la capacité d’adaptation du système de fichiers à l’ordinateur Windows Server qui accède au système de fichiers partagés des appareils.
  








