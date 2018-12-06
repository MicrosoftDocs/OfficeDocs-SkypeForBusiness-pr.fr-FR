---
title: "Lync Server 2013 : Conf. syst. Req. pr les serv. exécutant Lync Server 2013"
TOCTitle: Configuration système requise pour les serveurs exécutant Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398588(v=OCS.15)
ms:contentKeyID: 49297793
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration système requise pour les serveurs exécutant Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

> [!NOTE]  
> Pour plus d’informations sur les conditions matérielles requises, reportez-vous à <a href="lync-server-2013-server-hardware-platforms.md">Plateformes matérielles de serveur pour Lync Server 2013</a>.

Les serveurs Standard Edition et Enterprise Edition partagent la même configuration logicielle requise.

Les serveurs qui exécutent Lync Server 2013, Enterprise Edition sont conçus pour les organisations de grande taille en tant que déploiement d’organisation principal. Le serveur Enterprise Edition est conçu pour s’étendre jusqu’à environ 80 000 utilisateurs hébergés par pool. Les serveurs qui exécutent Lync Server 2013, Standard Edition sont conçus pour les organisations plus petites et les emplacements distants du déploiement d’organisation principal. Deux serveurs Standard Edition peuvent prendre en charge jusqu’à 5 000 utilisateurs. Pour plus d’informations sur les différences entre les serveurs Standard Edition et Enterprise Edition, reportez-vous à [Vue d’ensemble du déploiement pour Lync Server 2013](lync-server-2013-deployment-overview.md).

## Installation du système d’exploitation

> [!IMPORTANT]  
> Lync Server 2013 est uniquement disponible en édition 64 bits, ce qui nécessite du matériel 64 bits et une édition 64 bits du système d’exploitation Windows Server. Il n’est pas possible d’utiliser une édition 32 bits de Lync Server 2013 avec cette version.

Les serveurs Standard Edition et Enterprise Edition peuvent utiliser n’importe lequel des systèmes d’exploitation suivants :

  - Windows Server 2008 R2 SP1 ou dernier Service Pack

  - Windows Server 2012

  - Windows Server 2012 R2

Installez le logiciel du système d’exploitation sur le serveur Standard Edition ou le serveur frontal Enterprise Edition. Appliquez toutes les dernières mises à jour pour que le système d’exploitation respecte les normes de votre organisation en matière de mise à jour. Pour plus d’informations sur les systèmes d’exploitation requis, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

> [!NOTE]  
> Pour que Lync Server 2013 fonctionne sur Windows Server 2012 R2, vous devrez peut-être modifier la valeur d’une clé du registre Windows Server. Cette modification est parfois nécessaire pour garantir le bon fonctionnement des certificats et pour que les clients s’enregistrent auprès de serveurs Survivable Branch Appliance. Pour plus d’informations, reportez-vous à la rubrique <a href="http://support.microsoft.com/kb/2901554" class="uri">http://support.microsoft.com/kb/2901554</a>.

## Logiciels supplémentaires pour Lync Server 2013

En plus des mises à jour requises pour le système d’exploitation, Lync Server 2013 requiert des rôles de système d’exploitation, des fonctionnalités et des logiciels supplémentaires pour fonctionner. Pour plus d’informations sur les logiciels supplémentaires que vous devez installer avant de publier votre topologie et d’installer Lync Server 2013, reportez-vous à [Autre configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

## Logiciels supplémentaires requis pour tous les rôles serveur

Sur tous les rôles serveur, vous devez également vérifier que interface de ligne de commande Windows PowerShell 3.0 et Microsoft .NET Framework 4.5 sont installés.

En outre, interface de ligne de commande Windows PowerShell 3.0 et Microsoft .NET Framework 4.5 sont requis sur tout ordinateur sur lequel vous allez exécuter les outils d’administration Lync Server.

## Windows PowerShell 3.0

Lync Server 2013 requiert que vous installiez Windows PowerShell 3.0 sur chaque ordinateur faisant partie de votre topologie Lync Server. Pour plus d’informations sur l’installation de Windows PowerShell 3.0, reportez-vous à [Installation de Windows PowerShell 3.0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

> [!NOTE]  
> Sur Windows Server 2008 R2 avec SP1, il n’est pas possible d’installer interface de ligne de commande Windows PowerShell 3.0 avant d’installer Microsoft .NET Framework 4.5.

## Microsoft .NET Framework 4.5

Si vous installez Microsoft .NET Framework 4.5 sur des serveurs qui exécuteront Lync Server 2013 sur Windows Server 2012 ou Windows Server 2012 R2, vous devez effectuer une étape supplémentaire : une fois l’installation de .NET Framework 4.5 terminée, installez la fonctionnalité Activation HTTP à l’aide du Gestionnaire de serveur.

**Pour installer la fonctionnalité Activation HTTP de .NET Framework 4.5 sur Windows Server 2012 ou Windows Server 2012 R2**

1.  Dans le menu **Démarrer** , cliquez sur **Programmes** , sur **Outils d’administration** , puis sur **Gestionnaire de serveur**.

2.  Dans le Gestionnaire de serveur, sous **Résumé des fonctionnalités** , sélectionnez **Ajouter des fonctionnalités**.

3.  Développez **.NET Framework 4.5**.

4.  Sélectionnez **Activation de Windows Communication Foundation** si vous ne l’avez pas encore fait, puis sélectionnez **Activation HTTP**.

5.  Cliquez sur **Suivant** et suivez les instructions affichées pour terminer l’installation.

