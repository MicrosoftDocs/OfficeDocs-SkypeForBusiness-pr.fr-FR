---
title: 'Lync Server 2013 : Configuration système requise pour les serveurs exécutant Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Configuration système requise pour les serveurs exécutant Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-07-24_

<div>


> [!NOTE]  
> Pour plus d’informations sur la configuration matérielle requise, voir <A href="lync-server-2013-server-hardware-platforms.md">plates-formes matérielles pour Lync server 2013</A>.



</div>

Les serveurs Standard Edition et Enterprise Edition partagent les mêmes exigences logicielles.

Les serveurs exécutant Lync Server 2013 Enterprise Edition sont destinés aux grandes organisations comme déploiement principal de l’organisation. Le serveur Enterprise Edition est conçu pour être mis à niveau vers approximativement 80 000 utilisateurs familiaux par pool. Les serveurs exécutant Lync Server 2013 Standard Edition sont destinés aux organisations plus petites et aux endroits distants du déploiement principal de l’organisation. Une paire de serveurs Standard Edition peut prendre en charge jusqu’à 5 000 utilisateurs. Pour plus d’informations sur les différences entre les serveurs Standard Edition et les serveurs Enterprise Edition, voir [vue d’ensemble du déploiement pour Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Installation du système d’exploitation

<div>


> [!IMPORTANT]  
> Lync Server 2013 est disponible uniquement dans une édition 64 bits, qui nécessite une version matérielle 64 bits et une édition en 64 bits du système d’exploitation Windows Server. Une édition 32 bits de Lync Server 2013 n’est pas disponible dans cette version.



</div>

Les éditions standard du serveur et Enterprise Edition peuvent utiliser l’une des méthodes suivantes:

  - Windows Server 2008 R2 SP1 ou le dernier Service Pack

  - Windows Server 2012

  - Windows Server 2012 R2

Installez le logiciel du système d’exploitation sur le serveur frontal Standard Edition Server ou Enterprise Edition. Appliquez toutes les mises à jour afin de faire en sorte que le système d’exploitation dispose de la dernière mise à jour et du niveau de mise à jour requis conformément aux normes de votre organisation. Pour plus d’informations sur la configuration requise, reportez-vous à la [prise en charge des systèmes d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.

<div>


> [!NOTE]  
> Pour que Lync Server 2013 fonctionne sur Windows Server 2012 R2, il est possible que vous deviez modifier la valeur d’une clé de Registre dans Windows Server. Ce changement est susceptible d’être nécessaire pour le bon fonctionnement des certificats et permettre aux clients de s’inscrire à des appareils distants. Pour plus d’informations, <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>reportez-vous à.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Logiciels supplémentaires pour Lync Server 2013

Outre les mises à jour requises pour le système d’exploitation, Lync Server 2013 nécessite le fonctionnement des rôles, fonctionnalités et logiciels du système d’exploitation. Pour plus d’informations sur les logiciels supplémentaires qui doivent être installés avant de publier votre topologie et d’installer Lync Server 2013, voir [configuration logicielle requise pour Lync server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Logiciel supplémentaire nécessaire pour tous les rôles de serveur

Sur tous les rôles de serveur, vous devez également vous assurer que l’interface de ligne de commande Windows PowerShell 3,0 et Microsoft .NET Framework 4,5 sont installés.

Par ailleurs, l’interface de ligne de commande Windows PowerShell 3,0 et Microsoft .NET Framework 4,5 sont nécessaires sur tout ordinateur sur lequel vous allez exécuter les outils d’administration de Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 nécessite l’installation de Windows PowerShell 3,0 sur les ordinateurs qui participeront à la topologie de votre serveur Lync. Pour plus d’informations sur l’installation de Windows PowerShell 3,0, voir [installation de Windows powershell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]  
> Sur Windows Server&nbsp;2008&nbsp;R2 avec SP1, l’interface de ligne de commande Windows PowerShell 3,0 ne peut pas être installée avant l’installation de Microsoft .NET Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lorsque vous installez Microsoft .NET Framework 4,5 sur des serveurs exécutant Lync Server 2013 sur Windows Server 2012 ou Windows Server 2012 R2, vous devez effectuer une étape supplémentaire. Après avoir installé .NET Framework 4,5, utilisez le gestionnaire de serveur pour installer l’activation HTTP.

**Pour installer l’activation HTTP de .NET 4,5 sur Windows Server 2012 ou Windows Server 2012 R2**

1.  Dans le menu **Démarrer** , cliquez sur **programmes**, sur **Outils d’administration**, puis sur gestionnaire de **serveur**.

2.  Dans le gestionnaire de serveur, sous **fonctionnalités récapitulatives**, sélectionnez **Ajouter des fonctionnalités**.

3.  Développez **.NET Framework 4,5**.

4.  Sélectionnez **activation WCF** si ce n’est pas déjà fait. Ensuite, sélectionnez **activation http**.

5.  Cliquez sur **suivant** et suivez les invites pour terminer l’installation.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

