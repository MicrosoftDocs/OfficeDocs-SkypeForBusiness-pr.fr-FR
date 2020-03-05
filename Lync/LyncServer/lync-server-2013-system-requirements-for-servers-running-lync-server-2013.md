---
title: 'Lync Server 2013 : configuration système requise pour les serveurs exécutant Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0affd2d951d437a930bc7f210e0878e2978f8731
ms.sourcegitcommit: 5fbb57c5f0692afcb8e65516c63b96814f51ca65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417579"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Configuration système requise pour les serveurs exécutant Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-24_

<div>


> [!NOTE]
> Pour plus d’informations sur la configuration matérielle requise, consultez la rubrique <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync Server 2013</A>.



</div>

Les serveurs Standard Edition et Enterprise Edition partagent la même configuration logicielle requise.

Les serveurs exécutant Lync Server 2013, Enterprise Edition sont destinés aux grandes organisations en tant que déploiement organisationnel principal. Le serveur Enterprise Edition est conçu pour établir une échelle d’environ 80 000 utilisateurs hébergés par pool. Les serveurs exécutant Lync Server 2013, Standard Edition, sont conçus pour des organisations plus petites et des emplacements distants du déploiement principal de l’organisation. Une paire de serveurs Standard Edition Server peut prendre en charge jusqu’à 5 000 utilisateurs.. Pour plus d’informations sur les différences entre les serveurs Standard Edition Server et les serveurs Enterprise Edition, voir [Deployment Overview for Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Installation du système d’exploitation

<div>


> [!IMPORTANT]
> Lync Server 2013 est disponible uniquement dans une édition 64 bits, qui nécessite un matériel 64 bits et une édition 64 bits du système d’exploitation Windows Server. Une édition 32 bits de Lync Server 2013 n’est pas disponible dans cette version.



</div>

Les serveurs Standard Edition et Enterprise Edition peuvent utiliser l’une des méthodes suivantes :

  - Windows Server 2008 R2 SP1 ou Service Pack le plus récent

  - Windows Server 2012

  - Windows Server 2012 R2

Installez le logiciel du système d’exploitation sur le serveur Standard Edition ou le serveur frontal Enterprise Edition. Appliquez toutes les dernières mises à jour pour que le système d’exploitation réponde aux standards de votre organisation en matière de mise à jour. Pour plus d’informations sur la configuration requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

> [!NOTE] 
> La mise à niveau sur place du système d’exploitation n’est pas prise en charge avec Lync Server 2013.  Vous devez déployer un pool distinct et migrer les utilisateurs vers le nouveau pool avec un système d’exploitation différent.

<div>


> [!NOTE]
> Pour que Lync Server 2013 fonctionne sur Windows Server 2012 R2, vous devrez peut-être modifier la valeur d’une clé de Registre dans Windows Server. Cette modification peut être nécessaire pour que les certificats fonctionnent correctement et que les clients puissent s’inscrire auprès d’un Survivable Branch Appliances. Pour plus d’informations, <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>reportez-vous à.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Logiciels supplémentaires pour Lync Server 2013

Outre les mises à jour requises pour le système d’exploitation, Lync Server 2013 nécessite des rôles, des fonctionnalités et des logiciels de système d’exploitation pour fonctionner. Pour plus d’informations sur les logiciels supplémentaires qui doivent être installés avant la publication de votre topologie et l’installation de Lync Server 2013, reportez-vous à la rubrique [autres logiciels requis pour Lync server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Logiciels supplémentaires requis pour tous les rôles serveur

Sur tous les rôles serveur, vous devez également vous assurer que les interfaces de ligne de commande Windows PowerShell 3,0 et Microsoft .NET Framework 4,5 sont installées.

En outre, l’interface de ligne de commande Windows PowerShell 3,0 et Microsoft .NET Framework 4,5 sont requises sur tout ordinateur sur lequel vous allez exécuter les outils d’administration Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 nécessite l’installation de Windows PowerShell 3,0 sur chaque ordinateur qui prendra part à votre topologie Lync Server. Pour plus d’informations sur l’installation de Windows PowerShell 3,0, voir [Installing Windows powershell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]
> Sur Windows Server&nbsp;2008&nbsp;R2 avec SP1, l’interface de ligne de commande Windows PowerShell 3,0 ne peut pas être installée avant l’installation de Microsoft .NET Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lorsque vous installez Microsoft .NET Framework 4,5 sur des serveurs qui exécuteront Lync Server 2013 sur Windows Server 2012 ou Windows Server 2012 R2, vous devez effectuer une étape supplémentaire. Après avoir installé .NET Framework 4,5, utilisez le gestionnaire de serveur pour installer l’activation HTTP.

**Pour installer .NET 4,5 HTTP activation sur Windows Server 2012 ou Windows Server 2012 R2**

1.  Dans le menu **Démarrer** , cliquez sur **programmes**, sur **Outils d’administration**, puis sur gestionnaire de **serveur**.

2.  Dans le gestionnaire de serveur, sous **Résumé des fonctionnalités**, sélectionnez **Ajouter des fonctionnalités**.

3.  Développez **.NET Framework 4,5**.

4.  Sélectionnez **activation WCF** si elle n’est pas déjà sélectionnée. Ensuite, sélectionnez **activation http**.

5.  Cliquez sur **suivant** et suivez les invites pour terminer l’installation.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

