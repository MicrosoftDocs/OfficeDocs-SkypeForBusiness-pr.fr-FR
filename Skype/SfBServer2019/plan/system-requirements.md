---
title: System requirements for Skype Entreprise Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Résumé : Préparez vos serveurs Skype Entreprise Server 2019 et votre infrastructure de domaine avec cette rubrique. Le matériel, le système d’exploitation, les bases de données, les logiciels, la configuration système requise et les recommandations, ainsi que le DNS de certificat, le partage de fichiers et les informations Active Directory, sont là pour garantir une installation et un déploiement réussis de votre batterie de serveurs.'
ms.openlocfilehash: d5714c5606c69d6aba0befa03a6556a5da8ab443
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728363"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>System requirements for Skype Entreprise Server 2019
 
**Résumé :** Préparez-vous à installer Skype Entreprise Server 2019 avec cette rubrique. Le matériel, le système d’exploitation, les logiciels, les bases de données, les certificats, Active Diretory, DNS et les partages de fichiers sont abordés ici. Toutes les exigences système et recommandations sont là pour garantir une installation et un déploiement réussis de votre batterie de serveurs.
  
Comme vous pouvez vous y attendre, il y a quelques préparations à effectuer avant de commencer le déploiement Skype Entreprise Server 2019. Cet article vous explique comment planifier les projets suivants :
  
- [Matériel](system-requirements.md#Hardware)
  
- [Systèmes d’exploitation](system-requirements.md#OS)
  
- [Logiciels](system-requirements.md#Software)

- [Bases de données SQL principale](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [DNS (Domain Name System)](system-requirements.md#DNS)
  
- [Certificats](system-requirements.md#Certs)
  
- [Partage de fichiers](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Matériel pour Skype Entreprise Server 2019
<a name="Hardware"> </a>

Une fois votre topologie en panne (et si ce n’est pas le cas, consultez la rubrique Informations de base sur la topologie pour [Skype Entreprise Server 2019),](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) il est temps de réfléchir aux serveurs. Skype Entreprise Server 2019 nécessitent du matériel 64 bits. Nos recommandations en matière de matériel sont ci-dessous. Ce ne sont pas des exigences, mais elles reflètent les exigences nécessaires pour des performances optimales. Nous avons une documentation de planification de la capacité qui vous aidera à déterminer si vous en avez besoin de plus, en fonction de vos circonstances.
  
Matériel recommandé pour les Édition Standard serveurs :

|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype Entreprise Server 2019.  <br/> |
|Mémoire  <br/> |32 gigaoctets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 disques durs ou plus de 1 0000 TPM avec au moins 72 Go d’espace disque libre (deux disques utilisant RAID 1 et 6 utilisant RAID 10).  <br/> OU  <br/> • Des disques SSD (Solid State Drives) capables de fournir le même espace libre et des performances similaires à 8 disques mécaniques 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou plus (2 cartes réseau peuvent être utilisées, mais elles doivent être liées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double  ou multi-accueil ne sont pas pris en charge pour les serveurs frontaux, les serveurs frontaux et les serveurs Édition Standard serveurs. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et qu’ils sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez avoir des systèmes de gestion hors bande, tels que DRAC ou ILO. Ce scénario ne constitue pas un serveur multi-accueil et il est pris en charge.  <br/> |


Matériel recommandé pour les serveurs frontux et les serveurs frontux :
  
|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur. <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype Entreprise Server 2019.  <br/> |
|Mémoire  <br/> |64 gigaoctets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 disques durs ou plus de 1 0000 TPM avec au moins 72 Go d’espace disque libre (deux disques utilisant RAID 1 et 6 utilisant RAID 10).  <br/> OU  <br/> • Des disques SSD (Solid State Drives) capables de fournir le même espace libre et des performances similaires à 8 disques mécaniques 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou plus (2 cartes réseau peuvent être utilisées, mais elles doivent être liées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double  ou multi-accueil ne sont pas pris en charge pour les serveurs frontaux, les serveurs frontaux et les serveurs Édition Standard serveurs. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et qu’ils sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez avoir des systèmes de gestion hors bande, tels que DRAC ou ILO. Ce scénario ne constitue pas un serveur multi-accueil et il est pris en charge.  <br/> |
   
Matériel recommandé pour les serveurs Edge, les serveurs de médiation autonomes et les directeurs :
  
|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype Entreprise Server 2019.  <br/> |
|Mémoire  <br/> |32 gigaoctets.  <br/> |
|Disque  <br/> |SOIT :  <br/> • 4 disques durs ou plus de 1 0000 MPM avec au moins 72 Go d’espace disque libre (les disques doivent être dans une configuration RAID 1 2x).  <br/> OU  <br/> • Disques SSD (Solid State Drive) capables de fournir le même espace libre et des performances similaires à 4 disques mécaniques 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou plus (2 cartes réseau peuvent être utilisées, mais elles doivent être liées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double ou multi-accueil ne **sont** pas pris en charge pour les serveurs d’interopation vidéo et les directeurs. <br/> Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau double port, 1 Gbits/s ou plus (ou deux cartes réseau couplées, pour un total de quatre, chaque paire étant associé à une seule adresse MAC et une seule adresse IP, pour un total de deux paires).  <br/> Sur les serveurs de médiation autonomes, l’installation de cartes d’interface réseau supplémentaires pour permettre la configuration d’une adresse IP PSTN spécifique est prise en charge.  <br/> |


> [!NOTE]
> Quel que soit le rôle serveur, nous vous recommandons également les paramètres matériels suivants pour Skype Entreprise Server 2019 (cela peut varier en fonction de la marque de matériel que vous avez achetée. Pour plus d’informations, reportez-vous à la documentation du fabricant) :
> - Config BIOS : doit être définie sur FLAT à partir de NUMA.
> - Activez l’hyperthreading.
> - Le paramètre de file d’attente RSS doit être définie sur 8 files d’attente.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Systèmes d’exploitation Skype Entreprise Server 2019
<a name="OS"> </a>

Une fois le matériel en place, vous devez installer le système d’exploitation qui vous permettra d’installer et d’utiliser correctement Skype Entreprise Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Tout autre que les systèmes d’exploitation répertoriés ici ne fonctionne pas correctement ; N’essayez pas d’installer Skype Entreprise Server 2019. Par exemple, l’option Server Core n’est pas répertoriée et n’est donc pas prise en charge.

> [!NOTE]
> La mise à niveau sur place du système d’exploitation n’est pas prise en charge avec Lync Server 2013. Vous devez déployer un pool distinct et migrer les utilisateurs vers le nouveau pool avec un système d’exploitation différent. Tous les serveurs d’un pool doivent avoir la même version du système d’exploitation.

> [!NOTE]
> 
> Si vous installez Windows Admin Center 2019 sur votre ordinateur Windows Server 2019, il vous invitera à écouter un port. Vous pouvez choisir le port 443, mais si Skype Entreprise Server 2019 est installé sur cet ordinateur ou si Skype Entreprise Server 2019 est installé dessus, vous devez choisir un autre numéro de port.
> 
>Pourquoi est-ce le cas ? Si Windows Admin Center 2019 est en cours d’exécution sur le port 443, vous ne serez pas en mesure de vous connecter au serveur à l’aide du Panneau de Skype Entreprise, ni de vous connecter à un service web interne s’exécutant sur le serveur (service web de carnet d’adresses, service de découverte automatique, service WebTicket, etc.).  En fait, vous ne pourrez pas vous connecter à une URL de service Web interne. Choisissez un autre port si vous avez besoin ou souhaitez placer Windows Admin Center 2019 sur un serveur Skype Entreprise Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Logiciel à installer avant un déploiement Skype Entreprise Server 2019
<a name="Software"> </a>

Vous devrez installer ou configurer certains éléments pour n’importe quel serveur exécutant Skype Entreprise Server 2019. Celles-ci sont répertoriées ci-dessous, suivies d’exigences supplémentaires pour des rôles serveur spécifiques.

> [!IMPORTANT]
> Skype For Business 2019 prend en charge .Net Framework 4.8. 
  
 **Tous les serveurs :**
  
|**Logiciel/rôle**|**Détails**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tous Skype Entreprise Server serveurs doivent Windows PowerShell 3.0.  <br/> • Il doit être installé par défaut avec Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Les services WCF sont une fonctionnalité installée en tant que fonctionnalité Windows, sous Le Gestionnaire de serveur **,** initialement aucun téléchargement n’est nécessaire.  <br/> • Vous devez vous assurer, lorsque vous installez cette fonctionnalité, ou si elle est déjà installée et que vous l’activez, que l’option **d’activation HTTP** est également cochée et installée, comme ceci : <br/> ![Capture d’écran montrant l’option d’activation HTTP .NET Framework fonctionnalités 4.5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Ne vous inquiétez pas si vous obtenez une fenêtre vidéo supplémentaire vous disant que d’autres éléments doivent être installés pour que l’activation HTTP soit installée. C’est normal . cliquez sur OK et allez de l’avant. Si vous n’obtenez pas cette fenêtre fenêtre, vous pouvez supposer que ces éléments sont déjà installés et continuer.  <br/> Microsoft .NET Framework est généralement installé lorsque Windows Server 2016 est installé. Skype Entreprise Server nécessite microsoft .NET Framework 4.7 ou 4.8, vous devrez probablement le mettre à jour. Vous trouverez la mise à jour [ici.](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Par Windows Server 2016, le Windows du format multimédia s’installe avec Microsoft Media Foundation.  <br/> Tous les serveurs frontaux et serveurs Édition Standard utilisés pour les conférences nécessitent le runtime du format multimédia Windows pour exécuter les fichiers Windows Media Audio (.wma) lés par les applications Parcage d’appel, Annonce et Response Group pour les annonces et la musique.  <br/> |
|Windows Identity Foundation  <br/> |Nous devons Windows Identity Foundation 3.5 pour prendre en charge les scénarios d’authentification de serveur à serveur pour Skype Entreprise Server 2019.  <br/> • Pour Windows Server 2016, il n’est pas nécessaire de télécharger quoi que ce soit. Ouvrez **le Gestionnaire de** serveur et allez à l’Assistant Ajout de **rôles et de fonctionnalités.** **Windows Identity Foundation 3.5** est répertorié dans la section **Fonctionnalités.** Si elle est sélectionnée, vous êtes bon. Sinon, sélectionnez-le et **cliquez sur Suivant** pour accéder au **bouton** Installer. <br/> |
|Outils d'administration de serveur distant  <br/> |Outils d’administration des rôles : outils AD DS et AD LDS  <br/> |
   
 **Les serveurs frontux et Édition Standard serveur frontal ont également besoin des ressources nécessaires :**
  
|**Logiciel/rôle**|**Détails**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS est nécessaire sur tous les serveurs frontaux, ainsi que tous les serveurs Édition Standard, avec les modules suivants sélectionnés :  <br/> • Fonctionnalités HTTP courantes : document par défaut, erreurs HTTP, contenu statique  <br/> • Santé et diagnostics : journalisation HTTP, outils de journalisation, suivi  <br/> • Performances : compression de contenu statique, compression de contenu dynamique  <br/> • Sécurité : filtrage des demandes, authentification par mappage de certificat client, authentification Windows client  <br/> • Développement d’applications : extensibilité .NET 3.5, extensibilité .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, extensions ISAPI, filtres ISAPI  <br/> • Outils de gestion : Console de gestion IIS, scripts et outils de gestion IIS  <br/> Notez que l’accès anonyme est également nécessaire, mais que vous l’obtenez lors de l’installation d’IIS, vous n’avez donc pas d’endroit pour le sélectionner dans la liste.  <br/> |
|Module d’exécution du format Windows Media  <br/> | Pour Windows Server 2016, vous devez installer la fonctionnalité **Media Foundation** dans le Gestionnaire **de serveur.** Vous pouvez en fait démarrer votre installation Skype Entreprise Server 2019 sans cela, mais vous serez invité à l’installer, puis à redémarrer le serveur, avant de poursuivre l’installation de Skype Entreprise Server 2019. Il est préférable de le faire à l’avance. <br/> |
|Silverlight  <br/> |Vous pouvez installer la dernière version de Silverlight [ici.](https://www.microsoft.com/silverlight/)  <br/> |
   
Pour vous aider, voici un exemple de script PowerShell que vous pouvez exécuter pour automatiser ceci :
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **Les directeurs ont également besoin des :**
  
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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bases de données principale qui fonctionneront avec Skype Entreprise Server 2019
<a name="DBs"> </a>

Lors de l’installation Skype Entreprise Server 2019 Édition Standard, vous aurez SQL Server 2016 Express (édition 64 bits).

Skype Entreprise Server 2019 Êdition Entreprise nécessite une SQL Server complète, comme indiqué ci-dessous (édition 64 bits uniquement ; n’utilisez pas les éditions 32 bits) :
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (édition 64 bits) et vous devez exécuter avec les dernières mises à jour.  <br/> |Microsoft SQL Server 2017 (édition 64 bits) et vous devez exécuter avec les dernières mises à jour.  <br/> |
Microsoft SQL Server 2016 (édition 64 bits) et vous devez exécuter avec les dernières mises à jour.|
 |

Si vous ne voyez pas l’édition SQL Server que vous souhaitez utiliser répertoriée ici, vous ne pouvez pas l’utiliser.
  
> [!NOTE]
> Vous devez également installer SQL Server Reporting Services pour le rôle serveur de surveillance. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL Clustering et SQL Always On

SQL Le clustering avec Skype Entreprise Server 2019 est pris en charge. Si vous souhaitez configurer SQL clustering, cette mise à jour est effectuée SQL Server.
  
Assurez-vous que vous avez une configuration active/passive pour SQL clustering, qui est pris en charge. Ne partagez pas le nœud passif avec d’autres SQL instance.
  
Vous pouvez avoir les conseils suivants pour le clustering deover :
  
Deux nœuds :
  
- Microsoft SQL Server 2019 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.
- Microsoft SQL Server 2017 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.
- Microsoft SQL Server 2016 Standard (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

Seizième :
  
- Microsoft SQL Server 2019 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.
- Microsoft SQL Server 2017 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.
- Microsoft SQL Server 2016 Enterprise (édition 64 bits) et nous vous recommandons de l’exécution avec le dernier Service Pack.

SQL Always On est pris en charge et vous pouvez en savoir plus à ce sujet dans la haute disponibilité du serveur principal [Skype Entreprise Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recommandations supplémentaires sur l’installation du serveur :
  
N’installez aucun logiciel client Microsoft Internet Security and Acceleration (ISA) Server, ni aucun autre logiciel winsock layered service providers (LSP) (tout pare-feu tiers ou logiciel d’inspection du réseau antivirus serait inclus ici) sur vos serveurs frontaux ou serveurs de médiation autonomes. Des performances médiocres du trafic multimédia ont été vues lors de l’installation de ce logiciel.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Bien que la plupart des données de configuration pour les serveurs et les services soient stockées dans le magasin central de gestion Skype Entreprise Server 2019, certains éléments sont toujours stockés dans Active Directory :
  
|**Objets Active Directory**|**Types d’objets**|
|:-----|:-----|
|Extensions de schéma  <br/> |Extensions de l’objet utilisateur  <br/> |
||Extensions pour Skype Entreprise Server 2015 et Lync Server 2013, afin de maintenir la compatibilité ascendante avec les versions précédentes pris en charge  <br/> |
|Données  <br/> |URI SIP utilisateur et autres paramètres utilisateur  <br/> |
||Objets contact pour les applications (comme l’application Response Group et le application Assistant de conférence)  <br/> |
||Données publiées pour la compatibilité ascendante  <br/> |
||Un point de contrôle de service (SCP) pour le magasin central de gestion  <br/> |
||Compte d’authentification Kerberos (un objet ordinateur facultatif)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Système d’exploitation pour contrôleurs de domaine

Les systèmes d’exploitation contrôleur de domaine suivants peuvent être utilisés :
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Le niveau fonctionnel de domaine de n’importe quel domaine dans Skype Entreprise Server 2019 et le niveau fonctionnel de forêt de n’importe quelle forêt dans Skype Entreprise Server 2019, doivent être l’un des suivants :
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Pouvez-vous avoir des contrôleurs de domaine en lecture seule dans ces environnements ? Bien sûr, tant que des contrôleurs de domaine accessibles en ligne sont également disponibles.
  
Il est important de savoir que Skype Entreprise Server 2019 ne prend pas en charge les domaines en une seule partie. Qu'est-ce que c'est ? Si vous avez un domaine racine étiqueté contoso.local, cela va être correct. Si vous avez un domaine racine qui vient d’être nommé local, cela ne fonctionne pas et n’est donc pas pris en charge. Un peu plus d’informations à ce sujet ont été [écrites dans cet article de la Base de connaissances.](https://support.microsoft.com/kb/300684/)
  
Skype Entreprise Server 2019 ne prend pas en charge le changement de nom des domaines. Si vous devez vraiment renommer votre domaine, vous devrez désinstaller Skype Entreprise Server 2019, renommer le domaine, puis réinstaller Skype Entreprise Server 2019.
  
Enfin, il se peut que vous traitiez un domaine avec un environnement AD DS verrouillé, ce qui est normal. Nous avons plus d’informations sur la façon de déployer Skype Entreprise Server 2019 dans un environnement AD DS verrouillé dans la documentation de déploiement.
  
### <a name="ad-topologies"></a>AD Topologies

Les topologies Skype Entreprise Server 2019 sont les Skype Entreprise Server les plus pris en charge :
  
- Forêt unique avec domaine unique
    
- Forêt unique avec un arbre unique et plusieurs domaines
    
- Forêt unique avec plusieurs arbres et des espaces de noms disjoints
    
- Plusieurs forêts dans une topologie de forêt centrale
    
- Plusieurs forêts dans une topologie de forêt de ressources
    
- Plusieurs forêts dans une topologie de Skype Entreprise ressource avec des Exchange Online
    
- Plusieurs forêts dans une topologie de forêt ressource avec Skype Entreprise Online et Azure Active Directory Connecter
    
Nous avons des diagrammes et des descriptions pour vous aider à déterminer la topologie dont vous avez besoin dans votre environnement ou ce que vous devrez peut-être configurer avant d’installer Skype Entreprise Server 2019. Pour des raisons de simplicité, nous insérons également une clé :
  
![Il s’agit d’une clé pour les icônes utilisées pour Skype Entreprise de topologie.](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Forêt unique avec domaine unique

![Diagramme d’une forêt unique Active Directory avec un seul domaine.](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Cela n’est pas plus simple . Il s’agit d’une forêt de domaine unique, une topologie commune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Forêt unique avec un arbre unique et plusieurs domaines

![Diagramme de domaines à forêt unique, à arborescence unique et à mutiple.](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Ce diagramme montre une forêt unique, encore une fois, mais il possède également un ou plusieurs domaines enfants (il en existe trois dans cet exemple spécifique). Le domaine dans Skype Entreprise Server 2019 est déployé. Pourquoi vous vous inquiétez ? Il est important de se souvenir que lorsque vous déployez un pool frontal Skype Entreprise Server, tous les serveurs de ce pool doivent se trouver dans un seul domaine. Vous pouvez avoir une administration entre domaines via Skype Entreprise Server prise en charge Windows groupes d’administrateurs universels.
  
Dans le diagramme ci-dessus, vous pouvez voir que les utilisateurs d’un domaine peuvent accéder aux pools de Skype Entreprise Server à partir du même domaine ou de domaines différents, même si ces utilisateurs sont dans un domaine enfant.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Forêt unique avec plusieurs arbres et des espaces de noms disjoints

![Diagramme d’une forêt unique, de plusieurs forêts et d’espaces de noms disjoints.](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Vous pouvez avoir une topologie semblable à ce diagramme, où vous avez une forêt, mais dans cette forêt se trouve plusieurs domaines, avec des espaces de noms AD distincts. Dans ce cas, ce diagramme est une bonne illustration, car il inclut des utilisateurs dans trois domaines différents qui accèdent Skype Entreprise Server 2019. Les lignes pleines indiquent qu’ils accèdent à un pool Skype Entreprise Server dans leur propre domaine, tandis qu’une ligne en pointillé indique qu’ils accèdent à un pool dans une arborescence totalement différente.
  
Comme vous pouvez le constater, les utilisateurs du même domaine, de la même arborescence ou même d’une autre arborescence peuvent accéder aux pools avec succès.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Plusieurs forêts dans une topologie de forêt centrale

![Plusieurs forêts dans un diagramme de topologie de forêt centrale.](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype Entreprise Server 2019 prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Si vous n’êtes pas sûr de ce que vous avez, la forêt centrale de la topologie utilise des objets dans celle-ci pour représenter les utilisateurs des autres forêts et héberge des comptes d’utilisateurs pour tous les utilisateurs de la forêt.
  
Comment cela fonctionne-t-il ? Un produit de synchronisation d’annuaires (tel que Forefront Identity Manager ou FIM) gère les comptes d’utilisateurs de votre organisation tout au long de leur existence. Lorsqu’un compte est créé ou supprimé d’une forêt, cette modification est synchronisée avec le contact correspondant dans la forêt centrale.
  
Clairement, si votre infrastructure AD est en place, le passage à cette topologie peut ne pas être facile, mais si vous y êtes déjà ou si vous planifiez encore votre infrastructure de forêt, cela peut être un bon choix. Vous pouvez centraliser votre déploiement Skype Entreprise Server 2019 au sein d’une forêt unique, tandis que les utilisateurs peuvent rechercher, communiquer et afficher la présence d’autres utilisateurs dans n’importe quelle forêt. Toutes les mises à jour des contacts utilisateur sont gérées automatiquement avec le logiciel de synchronisation.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Plusieurs forêts dans une topologie de Skype Entreprise ressource
<a name="BKMK_multipleforestopology"> </a>

![Plusieurs forêts dans un diagramme de topologie de forêt de ressources.](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Une topologie de forêt de ressources est également prise en charge ; C’est là qu’une forêt est dédiée à l’exécution de vos applications serveur, comme Microsoft Exchange Server et Skype Entreprise Server 2019. Ces forêts de ressources hébergent également une représentation synchronisée des objets utilisateur actifs, mais pas de comptes d’utilisateurs connectés. La forêt de ressources est donc un environnement de services partagés pour d’autres forêts dans lesquelles résident des objets utilisateur, et ils ont une relation de confiance au niveau de la forêt avec la forêt de ressources.
  
Notez Exchange Server peuvent être déployés dans la même forêt de ressources que Skype Entreprise Server ou dans une autre forêt.
  
Pour déployer Skype Entreprise Server 2019 dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs (si Microsoft Exchange Server se trouve déjà dans l’environnement, cela peut être fait pour vous). Vous avez ensuite besoin d’un outil de synchronisation d’annuaires (comme Forefront Identity Manager ou FIM) pour gérer les comptes d’utilisateurs tout au long de leur cycle de vie.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts dans une topologie de Skype Entreprise ressource avec des Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Cette topologie est similaire à la topologie décrite dans plusieurs forêts dans une topologie de forêt Skype Entreprise [ressource.](system-requirements.md#BKMK_multipleforestopology)
  
Dans cette topologie, il existe une ou plusieurs forêts d’utilisateurs et Skype Entreprise Server est déployé dans une forêt de ressources dédiée. Exchange Server peuvent être déployés en local dans la même forêt de ressources ou dans une autre forêt et configurés pour un déploiement hybride avec Exchange Online, ou les services de messagerie peuvent être fournis exclusivement par Exchange Online pour les comptes locaux. Il n’existe aucun diagramme disponible pour cette topologie.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Plusieurs forêts dans une topologie de forêt ressource avec Skype Entreprise Online et Azure Active Directory Connecter
<a name="BKMK_multipleforestopology"> </a>

![Affiche deux forêts AD, une forêt d’utilisateurs et une forêt de ressources. Les deux forêts ont une relation d’confiance. Ils sont synchronisés avec les Microsoft 365 à l’aide d’Azure AD Connecter. Tous les utilisateurs sont activés pour la Skype Entreprise via Microsoft 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Avec ce scénario, il existe plusieurs forêts en local, avec une topologie de forêt ressource. Il existe une relation de confiance totale entre les forêts Active Directory. L Azure Active Directory Connecter est utilisé pour synchroniser les comptes entre les forêts d’utilisateurs locaux et les Microsoft 365 ou Office 365.
  
 L’organisation dispose également Microsoft 365 ou Office 365 et utilise [Azure Active Directory Connecter](/azure/active-directory/connect/active-directory-aadconnect) pour synchroniser ses comptes locaux avec Microsoft 365 ou Office 365. Les utilisateurs activés pour Skype Entreprise sont activés via Microsoft 365 ou Office 365 et Skype Entreprise Online. Skype Entreprise Server n’est pas déployé en local.
  
L’authentification unique est fournie par une batterie des services de fédération Active Directory située dans la forêt d’utilisateurs.
  
Dans ce scénario, il est pris en charge pour déployer Exchange sur site, Exchange Online, une solution Exchange hybride ou ne pas déployer de Exchange du tout. (Le diagramme montre uniquement Exchange local, mais les autres solutions Exchange sont également entièrement pris en charge.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Plusieurs forêts dans une topologie de forêt ressource avec des Skype Entreprise
<a name="BKMK_multipleforestopology"> </a>

Dans ce scénario, il existe une ou plusieurs forêts d’utilisateurs locaux, et Skype Entreprise est déployé dans une forêt de ressources dédiée et est configuré pour le mode hybride avec Skype Entreprise Online. Exchange Server peuvent être déployés en local dans la même forêt de ressources ou dans une autre forêt et peuvent être configurés pour un déploiement hybride avec Exchange Online. Sinon, les services de messagerie peuvent être fournis exclusivement Exchange Online pour les comptes locaux.
  
Pour plus d’informations, [voir Configure a multi-forest environment for hybrid Skype Entreprise](../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype Entreprise Server 2019 nécessite DNS, pour les raisons suivantes :
  
- DNS permet à Skype Entreprise Server 2019 de découvrir des serveurs ou des pools internes, ce qui permet des communications de serveur à serveur.
    
- DNS permet aux ordinateurs clients de découvrir le pool frontal ou le serveur Édition Standard utilisé pour les transactions SIP.
    
- Il associe des URL simples pour les conférences aux serveurs hébergeant ces conférences.
    
- DNS permet aux utilisateurs externes et aux ordinateurs clients de se connecter à vos serveurs Edge, ou au proxy inverse HTTP, pour la messagerie instantanée ou la conférence.
    
- Il permet aux périphériques de communications unifiées qui ne sont pas connectés de découvrir le pool frontal ou le serveur Édition Standard qui exécute le service web de mise à jour des périphériques pour obtenir des mises à jour et envoyer des journaux.
    
- L’utilisation de DNS permet aux clients mobiles de découvrir automatiquement les ressources des services web sans obliger les utilisateurs à entrer manuellement des URL dans leurs paramètres d’appareil.
    
- Il est utilisé dans l’équilibrage de charge DNS.
    
Il est important de noter que Skype Entreprise Server 2019 ne prend pas en charge les noms de domaine internationaux (IDN).
  
Et il est extrêmement important de ne pas oublier que tout nom dans le DNS doit être identique au nom d’ordinateur configuré sur n’importe quel serveur utilisé par Skype Entreprise Server 2019. Plus précisément, nous ne pouvons pas avoir de noms courts dans l’environnement et nous devons avoir des FQDN pour le Générateur de topologies.
  
Cela semble logique pour tout ordinateur déjà joint à un domaine, mais si vous avez un serveur Edge qui n’est pas joint à votre domaine, il peut avoir par défaut un nom court, sans suffixe de domaine. Assurez-vous que ce n’est pas le cas, que ce soit dans DNS ou sur le serveur Edge, ou n’importe quel serveur ou pool Skype Entreprise Server 2019, d’ailleurs.
  
N’utilisez absolument pas de caractères Unicode ni de traits de soulignement. Les caractères standard (A-Z, a-z, 0-9 et tirets) sont pris en charge par le DNS externe et les autorités de certification publiques (vous devrez affecter des noms de domaine complets au nom de domaine complet dans le certificat, il est important de le mémoriser). Vous éviterez donc beaucoup de problèmes si vous donnez ce nom à l’esprit dès le début.
  
Pour en savoir plus sur les exigences DNS relatives à la mise en réseau, consultez la section [Mise](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) en réseau de notre documentation de planification.
  
## <a name="certificates"></a>Certificats
<a name="Certs"> </a>

L’une des choses les plus importantes que vous pouvez faire avant de déployer est de vous assurer que vos certificats sont en ordre. Skype Entreprise Server 2019 a besoin d’une infrastructure à clé publique (PKI) pour les connexions TLS (Transport Layer Security) et MTLS (Mutual Transport Layer Security). Fondamentalement, pour communiquer en toute sécurité de manière normalisée, Skype Entreprise Server utilise des certificats émis par les autorités de certification.
  
Voici quelques-uns des éléments pour Skype Entreprise Server 2019 utilise des certificats pour :
  
- Connexions TLS entre les clients et les serveurs
    
- Connexions MTLS entre serveurs
    
- Fédération à l’aide de la découverte automatique de partenaires via le DNS
    
- Accès des utilisateurs distants à la messagerie instantanée
    
- Accès des utilisateurs externes aux sessions audio/vidéo (AV), au partage d’application et aux conférences
    
- Parler aux applications web et Outlook Web Access (OWA)
    
La planification des certificats est donc un must. Examinons maintenant une liste de certains éléments que vous devez garder à l’esprit lors de la demande de certificats :
  
- Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).
    
- Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).
    
- Tous les certificats doivent être signés à l’aide d’un algorithme de signature pris en charge par le système d’exploitation. Skype Entreprise Server 2019 prend en charge la suite sha-1 et SHA-2 de tailles de condensé (224, 256, 384 et 512 bits) et répond ou dépasse la exigences du système d’exploitation.
    
- L’inscription automatique est prise en charge pour les serveurs internes Skype Entreprise Server 2019.
    
- L’inscription automatique n’est pas prise en charge Skype Entreprise Server serveurs Edge 2019.
    
> [!NOTE]
> L’utilisation de l’algorithme de signature RSASSA-PSS n’est pas pris en compte et peut entraîner des erreurs sur les problèmes de connexion et de forwarding d’appel, entre autres problèmes. 
  
- Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont pris en charge. Des longueurs clés de 2 048 et plus sont recommandées.
    
- L’algorithme de chiffrement par défaut, ou de signature de hachage, est RSA. Les algorithmes ECDH_P256, ECDH_P384 et ECDH_P521 sont également pris en charge.
    
Cela fait beaucoup à réfléchir, et il existe différents niveaux de confort avec la demande de certificats auprès d’une cae. Nous vous fournirons des conseils supplémentaires ci-dessous pour faciliter autant que possible votre planification.
  
### <a name="certificates-for-your-internal-servers"></a>Certificats pour vos serveurs internes

Vous aurez besoin de certificats pour la plupart de vos serveurs internes et, le plus probablement, vous les aurez auprès d’une ca interne (c’est-à-dire une ca située dans votre domaine). Si vous le souhaitez, vous pouvez demander ces certificats à une ca externe (une située sur Internet). Si vous vous demandez à quelle ca publique vous devez vous rendre, vous pouvez consulter la liste des partenaires de [certificats de communications](../../SfbPartnerCertification/certification/services-ssl.md) unifiées.
  
Vous aurez également besoin de certificats lorsque Skype Entreprise Server 2019 communiquera avec d’autres applications et serveurs, tels que Microsoft Exchange Server. Il s’agit évidemment d’un certificat que ces autres applications et serveurs peuvent utiliser de manière prise en charge. Skype Entreprise Server 2019 et d’autres produits Microsoft utilisent le protocole Open Authorization (OAuth) pour l’authentification et l’autorisation de serveur à serveur. Si cela vous intéresse, nous avons un article de planification supplémentaire pour OAuth et Skype Entreprise Server 2019.
  
Skype Entreprise Server 2019 inclut également la prise en charge (sans nécessiter) de certificats signés à l’aide de la fonction de hachage de chiffrement SHA-256. Pour prendre en charge l’accès externe à l’aide de SHA-256, le certificat externe doit être émis par une ca publique utilisant SHA-256.
  
Pour des raisons simples, nous avons placé les certificats requis pour les serveurs Édition Standard, les pools frontux et d’autres rôles dans les tableaux suivants, avec le contoso.com fictif utilisé pour des exemples (vous utiliserez probablement autre chose pour votre environnement). Ce sont tous des certificats de serveur web standard, avec des clés privées non exportables. Voici quelques éléments supplémentaires à noter :
  
- L’utilisation améliorée de la clé (EKU) du serveur est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.
    
- Chaque nom convivial de certificat doit être unique dans le magasin d’ordinateurs.
    
- Selon les exemples de noms ci-dessous, si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, ils doivent être ajoutés à l’autre nom de l’objet (SAN) du certificat.
    
Certificats pour Édition Standard serveurs :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |FQDN du pool et FQDN du serveur  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |Sur Édition Standard serveurs, le nom deqdn du serveur est le même que celui du pool.  <br/> L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN web interne (qui est identique au nom de groupe du serveur)  <br/> AND  <br/> • Rencontrez des URL simples  <br/> • URL simple de numérotation  <br/> • URL simple d’administration  <br/> OU  <br/> • Une entrée générique pour les URL simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Vous ne pouvez pas remplacer le FQDN web interne dans le Générateur de topologies.  <br/> Si vous avez plusieurs URL simples Meet, vous devez les inclure toutes comme DESN.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN web externe  <br/> AND  <br/> • URL simple de numérotation  <br/> • Rencontrez des URL simples par domaine SIP  <br/> OU  <br/> • Une entrée générique pour les URL simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour les serveurs frontaux dans un pool frontal :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |FQDN du pool et FQDN du serveur  <br/> Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.  <br/> Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.  <br/> |
|Web interne  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • FQDN web interne (qui n’est PAS le même que le nom de groupe du serveur)  <br/> • FQDN du serveur  <br/> • Skype Entreprise FQDN du pool  <br/> AND  <br/> • Rencontrez des URL simples  <br/> • URL simple de numérotation  <br/> • URL simple d’administration  <br/> OU  <br/> • Une entrée générique pour les URL simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
|Web externe  <br/> |Nom de domaine complet du pool  <br/> |Pour chaque élément suivant :  <br/> • FQDN web externe  <br/> AND  <br/> • URL simple de numérotation  <br/> • URL simple d’administration  <br/> OU  <br/> • Une entrée générique pour les URL simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.  <br/> Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.  <br/> |
   
Certificats pour le directeur :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |pool directeur  <br/> |FQDN du directeur, FQDN du pool directeur.  <br/> Si ce pool est le serveur d’accès automatique pour les clients et que la correspondance DNS stricte est requise dans la stratégie de groupe, vous aurez également besoin d’entrées pour sip.sipdomain (pour chaque domaine SIP dont vous avez).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.  <br/> |
|Web interne  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN web interne (qui est identique au nom de groupe du serveur)  <br/> • FQDN du serveur  <br/> • Skype Entreprise FQDN du pool  <br/> AND  <br/> • Rencontrez des URL simples  <br/> • URL simple de numérotation  <br/> • URL simple d’administration  <br/> OU  <br/> • Une entrée générique pour les URL simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web externe  <br/> |Nom de domaine complet du serveur  <br/> |Pour chaque élément suivant :  <br/> • FQDN web externe  <br/> AND  <br/> • Rencontrez des URL simples par domaine SIP  <br/> • URL simple de numérotation  <br/> OU  <br/> • Une entrée générique pour les URL simples  <br/> |Le FQDN web externe du directeur doit être différent du pool frontal ou du serveur frontal.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Utilisation d’un certificat de caractère générique :  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificats pour le serveur de médiation autonome :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet du pool  <br/> |Nom de domaine complet du pool  <br/> FQDN du serveur membre du pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificats pour le Survivable Branch Appliance (en particulier, Survivable Branch Appliance 2015 pour Skype Entreprise Server 2019) :
  
|**Certificat**|**Nom du sujet/nom commun**|**Autre nom du sujet**|**Exemple**|
|:-----|:-----|:-----|:-----|
|Par défaut  <br/> |Nom de domaine complet de l’appliance  <br/> |SIP.\<sipdomain\> (Vous n’avez besoin que d’une seule entrée par domaine SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificats pour l’accès des utilisateurs externes (Edge)

Skype Entreprise Server 2019 prend en charge l’utilisation d’un certificat **public** unique pour les interfaces externes Edge d’accès et de conférence web, ainsi que le service d’authentification A/V, qui est fourni via les serveurs Edge. Votre interface interne Edge utilise généralement un certificat privé émis par votre ca interne, mais si vous préférez, vous pouvez également utiliser un certificat public s’il est émis par une cae de confiance.
  
Votre proxy inverse (RP) va également utiliser un certificat public et chiffre la communication entre votre rp et les clients, ainsi que la rp vers les serveurs internes à l’aide du protocole HTTP (ou plus précisément, TLS sur HTTP).
  
### <a name="certificates-for-mobility"></a>Certificats pour la mobilité

Si vous déployez la mobilité et que vous prisez en charge la découverte automatique pour les clients mobiles, vous devrez inclure des entrées supplémentaires d’autres noms de sujet sur vos certificats pour prendre en charge les connexions sécurisées à partir des clients mobiles.
  
Vous aurez besoin de noms SAN pour la découverte automatique sur les certificats suivants :
  
- pool directeur
    
- pool frontal
    
- Proxy inverse
    
Les spécificités sont répertoriées dans les tableaux ci-dessous.
  
C’est là qu’une petite planification préalable est bonne, mais parfois, vous avez déployé Skype Entreprise Server 2019 sans avoir l’intention de déployer la mobilité, et cela se présente plus tard lorsque vous avez déjà des certificats dans votre environnement. Leur réédité via une cae interne est généralement assez simple, mais avec des certificats publics d’une ca publique, cela peut être un peu plus pricy.
  
Si c’est ce que vous regardez et si vous avez un grand nombre de domaines SIP (ce qui rendrait l’ajout de SANS plus coûteux), vous pouvez configurer votre proxy inverse pour utiliser HTTP pour la demande initiale du service de découverte automatique, au lieu d’utiliser HTTPS (qui est la configuration par défaut). [L’article Plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) (Planifier la mobilité) présente davantage d’informations à ce sujet.
  
Exigences relatives aux certificats de pool directeur et de pool frontal :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique interne  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL du service de découverte automatique externe  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Vous pouvez également utiliser SAN= \* .\<sipdomain\>
  
Conditions requises pour le certificat de proxy inverse (CA publique) :
  
|**Description**|**Entrée SAN**|
|:-----|:-----|
|URL du service de découverte automatique externe  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Ce SAN doit être affecté au certificat affecté à l’écoute SSL sur votre proxy inverse.
  
> [!NOTE]
> Votre listener de proxy inverse va avoir des réseaux sans pour vos URL de services web externes. San=skypewebextpool01.contoso.com et dirwebexternal.contoso.com sont des exemples si vous avez déployé le directeur (facultatif). 
  
## <a name="file-share"></a>Partage de fichiers
<a name="Fileshare"> </a>

Skype Entreprise Server 2019 peut utiliser le même partage de fichiers pour tout le stockage de fichiers. Vous devez garder les choses suivantes à l’esprit :
  
- Un partage de fichiers doit se trouver sur un stockage DAS (Direct Attached Storage) ou un réseau san (storage area network), ce qui inclut le système de fichiers distribués (DFS), ainsi qu’un tableau redondant de disques indépendants (RAID) pour les magasins de fichiers. Pour en savoir plus sur DFS pour Windows Server 2012, consultez [cette page DFS.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- Nous recommandons un cluster partagé pour le partage de fichiers. Si vous en utilisez déjà un, vous devez regrouper des Windows Server 2012 ou des versions ultérieures

> [!Note]
> **Pourquoi la dernière Windows ?** Il se peut que les versions antérieures ne disposent pas des autorisations permettant d’activer toutes les fonctionnalités. Vous pouvez utiliser l’administrateur de cluster pour créer les partages de fichiers. Pour plus d’informations, voir cet article de support sur la création de partages de fichiers sur un [cluster.](https://support.microsoft.com/help/224967)
    
> [!CAUTION]
> Vous devez savoir que l’utilisation du stockage connecté au réseau (NAS) en tant que partage de fichiers n’est pas prise en charge. Utilisez donc l’une des options répertoriées ci-dessus. Cette limitation de prise en charge est due à la conception variable des périphériques NAS qui doivent fournir une capacité d’adaptation du système de fichiers à l’ordinateur Windows Server qui accède au système de fichiers partagé des appareils.
