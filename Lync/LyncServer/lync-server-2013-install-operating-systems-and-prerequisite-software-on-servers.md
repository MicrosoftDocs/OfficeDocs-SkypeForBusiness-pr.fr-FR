---
title: "Lync Server 2013 : Inst. des syst. d’expl. et des log. prérequis sur les serv."
TOCTitle: Installation des systèmes d’exploitaition et des logiciels prérequis sur les serveurs
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398103(v=OCS.15)
ms:contentKeyID: 49296120
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des systèmes d’exploitaition et des logiciels prérequis sur les serveurs pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Une fois que vous avez configuré l’infrastructure système et le matériel, vous devez installer les systèmes d’exploitation Windows appropriés et leurs mises à jour, ainsi que les logiciels supplémentaires prérequis sur chaque serveur que vous déployez. Cela inclut chaque rôle serveur Lync Server 2013 et tout serveur d’infrastructure et serveur exécutant SQL Server requis pour le déploiement.

> [!NOTE]  
> Cette section décrit l’installation des systèmes d’exploitation et des logiciels prérequis pour les serveurs internes. Si vous déployez des serveurs Edge pour prendre en charge les utilisateurs externes, vous devez installer les systèmes d’exploitation et les logiciels prérequis pour ces serveurs, notamment des serveurs Edge et des serveurs proxy inverses. Pour plus d’informations sur la préparation des serveurs pour prendre en charge les utilisateurs externes, reportez-vous à <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Préparation de l’installation des serveurs sur le réseau de périmètre pour Lync Server 2013</a> dans la documentation du déploiement.

## Installer les systèmes d’exploitation Windows sur les serveurs

Sur chaque serveur que vous déployez, installez le système d’exploitation Windows approprié :

  - **Serveurs exécutant Lync Server 2013**   Pour plus d’informations sur les systèmes d’exploitation requis pour les serveurs exécutant Lync Server 2013, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

  - **Serveurs de base de données**   Pour plus d’informations sur les systèmes d’exploitation requis pour les serveurs de base de données, notamment la base de données principale, la base de données d’archivage et la base de données de surveillance, consultez la documentation de SQL Server. Pour SQL Server 2012, consultez la documentation en ligne de SQL Server 2012 à l’adresse [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x40c).

> [!NOTE]  
> Si vous installez Lync Server 2013 sur Windows Server 2008 R2 avec SP1, vous devez d’abord installer la mise à jour décrite dans l’article 2646886 de la base de connaissances Microsoft, « FIX: L’endommagement du tas se produit lorsqu’un module appelle la méthode InsertEntityBody dans les services Internet (IIS) 7.5 », à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=3052&amp;clcid=0x40C</a>.<br />
Vous devez aussi modifier le Registre comme indiqué dans l’article de la Base de connaissances, <a href="http://go.microsoft.com/fwlink/p/?linkid=506893">ID d’événement 32402, 61045 sont enregistrés dans les serveurs Lync Server 2013 Front-End qui sont installés dans Windows Server 2012 R2</a>.

## Installer la mise à jour de Windows Update sur les serveurs

Installez les mises à jour suivantes à partir de Windows Update sur chaque serveur :

  - **Mises à jour de Windows pour les serveurs exécutant Lync Server 2013**   Pour plus d’informations sur les mises à jour de Windows Update requises pour les serveurs exécutant Lync Server 2013, reportez-vous à [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

  - **Serveurs de bases de données**   Pour en savoir plus sur les mises à jour de Windows Update requises pour les serveurs de bases de données, notamment le serveur de la base de données principale, de la base de données d’archivage et de la base de données de surveillance, consultez la documentation de SQL Server 2012. Pour SQL Server 2012, consultez la documentation en ligne de SQL Server 2012 à l’adresse [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x40c).

## Installer les autres logiciels prérequis sur les serveurs

Lync Server 2013 requiert l’installation des logiciels supplémentaires suivants sur les serveurs :

  - **Logiciels prérequis pour les serveurs exécutant Lync Server 2013**   Les logiciels prérequis supplémentaires pour les serveurs exécutant Lync Server 2013 varient selon le rôle serveur déployé. Pour plus d’informations sur les logiciels spécifiques requis pour chaque serveur, reportez-vous à [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

  - **Windows Identity Foundation**   Lync Server 2013 requiert l’installation de Windows Identity Foundation pour la prise en charge des scénarios d’authentification serveur à serveur. Pour vérifier que ce logiciel est déjà installé sur votre ordinateur, dans le Panneau de configuration, cliquez sur **Programmes et fonctionnalités** , **Afficher les mises à jour installées** et vérifiez qu’il figure sous **Microsoft Windows** . Pour plus d’informations sur l’installation de Windows Identity Foundation, reportez-vous à [http://go.microsoft.com/fwlink/?linkid=204657\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=204657%26clcid=0x40c).

  - **Microsoft .NET Framework 4.5**   L’édition 64 bits de Microsoft .NET Framework 4.5 est requise pour Lync Server 2013.

  - **Logiciels prérequis pour les serveurs de bases de données**   Pour en savoir plus sur les mises à jour Windows requises pour les serveurs de base de données, notamment le serveur de la base de données principale, de la base de données d’archivage et de la base de données de surveillance, consultez la documentation de SQL Server 2012 à l’adresse [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x40c).
    
    > [!NOTE]  
    > Lync Server 2013 installe automatiquement Microsoft SQL Server 2012 Express sur chaque serveur Standard Edition et chaque serveur exécutant Lync Server 2013 sur lequel se trouve le magasin de configuration local.

  - **Module d’exécution du format Windows Media**   Le module d’exécution du format Windows Media doit être installé sur tous les serveurs frontaux et les serveurs Standard Edition sur lesquels le service de conférence sera déployé. Le module d’exécution du format Windows Media est requis pour exécuter les fichiers Windows Media Audio (.wma) que les applications de parcage d’appel, d’annonce et Response Group exécutent pour les annonces et la musique.
    
    > [!NOTE]  
    > Pour Windows Server 2012 et Windows Server 2012 R2, le module d’exécution du format Windows Media s’installe avec Microsoft Media Foundation.    
    > [!NOTE]  
    > Pour Windows Server 2008 et Windows Server 2008 R2, le module d’exécution du format Windows Media est installé en même temps que l’expérience Bureau Windows. Il est conseillé d’installer l’expérience Bureau Windows avant d’installer Lync Server 2013. Si Lync Server 2013 ne trouve pas ce logiciel sur le serveur, vous serez invité à l’installer, puis vous devrez redémarrer le serveur pour terminer l’installation.
