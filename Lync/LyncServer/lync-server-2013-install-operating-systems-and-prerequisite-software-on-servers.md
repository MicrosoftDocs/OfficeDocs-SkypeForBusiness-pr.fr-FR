---
title: Installer les systèmes d’exploitation et les logiciels prérequis sur les serveurs
description: Installez les systèmes d’exploitation et les logiciels prérequis sur les serveurs.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574130"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Installer les systèmes d’exploitation et les logiciels prérequis sur les serveurs pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-24_

Une fois que vous avez configuré l’infrastructure système et le matériel, vous devez installer les systèmes d’exploitation Windows appropriés et leurs mises à jour, ainsi que les logiciels supplémentaires prérequis sur chaque serveur que vous déployez. Cela inclut chaque rôle serveur Lync Server 2013 et tous les serveurs ou serveurs d’infrastructure supplémentaires exécutant SQL Server qui sont requis pour votre déploiement.

<div>


> [!NOTE]
> Cette section décrit l’installation des systèmes d’exploitation et des logiciels prérequis pour les serveurs internes. Si vous déployez des serveurs Edge pour prendre en charge l’accès des utilisateurs externes, vous devez également installer les systèmes d’exploitation et les logiciels prérequis pour ces serveurs, y compris les serveurs Edge et les serveurs proxy inverses. Pour plus d’informations sur la préparation des serveurs en vue de la prise en charge de l’accès des utilisateurs externes, voir <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the périmètre Network for Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Installer les systèmes d’exploitation Windows sur les serveurs

Sur chaque serveur que vous déployez, installez le système d’exploitation Windows approprié comme suit :

  - **Serveurs exécutant Lync Server 2013**     Pour plus d’informations sur la configuration requise du système d’exploitation pour les serveurs exécutant Lync Server 2013, voir [serveur et outils pris en charge par le système d’exploitation dans Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

  - Serveurs de bases **de données**     Pour plus d’informations sur la configuration requise du système d’exploitation pour les serveurs de bases de données, y compris la base de données principale, la base de données d’archivage et la base de données de surveillance, voir la documentation SQL Server. Pour SQL Server 2012, reportez-vous à la documentation en ligne de SQL Server 2012 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .

<div>


> [!NOTE]
> Si vous installez Lync Server 2013 sur Windows Server &nbsp; 2008 &nbsp; R2 avec SP1, vous devez d’abord installer la mise à jour décrite dans l’article 2646886 de la base de connaissances Microsoft « correctif : corruption de tas survient lorsqu’un module appelle la méthode INSERTENTITYBODY dans IIS 7,5 », at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.<BR>Vous devez également modifier le registre, comme décrit dans l’article de la base de connaissances, les <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">ID d’événement 32402, 61045 sont consignés dans les serveurs frontaux Lync Server 2013 installés dans Windows Server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Installer la mise à jour de Windows sur les serveurs

Installez les mises à jour suivantes à partir de Windows Update sur chaque serveur :

  - **Mise à jour Windows pour les serveurs exécutant Lync Server 2013**     Pour plus d’informations sur les mises à jour de Windows Update requises pour les serveurs Lync Server 2013, reportez-vous à la rubrique [autres logiciels requis pour Lync server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

  - Serveurs de bases **de données**     Pour plus d’informations sur les mises à jour de Windows Update requises pour les serveurs de bases de données, notamment la base de données principale, la base de données d’archivage et la base de données de surveillance, voir la documentation SQL Server 2012. Pour SQL Server 2012, reportez-vous à la documentation en ligne de SQL Server 2012 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Installer les autres logiciels prérequis sur les serveurs

Lync Server 2013 nécessite l’installation des logiciels supplémentaires suivants sur les serveurs :

  - **Logiciels prérequis pour les serveurs exécutant Lync Server 2013**     Les logiciels supplémentaires requis pour les serveurs exécutant Lync Server 2013 dépendent du rôle serveur en cours de déploiement. Pour plus d’informations sur la configuration logicielle requise pour chaque serveur, voir la rubrique relative à la [configuration logicielle requise pour Lync server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.

  - **Windows Identity Foundation**     Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification de serveur à serveur. Pour vérifier qu’elle a déjà été installée sur votre ordinateur, accédez au panneau de configuration, cliquez sur **programmes et fonctionnalités**, **afficher les mises à jour installées**et Regardez sous **Microsoft Windows**. Pour plus d’informations sur l’installation de Windows Identity Foundation, reportez-vous à [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .

  - **Microsoft .NET Framework 4,5**     L’édition 64 bits de Microsoft .NET Framework 4,5 est requise pour Lync Server 2013.

  - **Logiciels prérequis pour les serveurs**     de bases de données Pour plus d’informations sur la mise à jour Windows requise pour les serveurs de bases de données, y compris la base de données principale, la base de données d’archivage et la base de données de surveillance, voir la documentation SQL Server 2012 à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 installe automatiquement Microsoft SQL Server 2012 Express sur chaque serveur Standard Edition et chaque serveur exécutant Lync Server 2013 sur lequel se trouve le magasin de configurations local.

    
    </div>

  - Exécution du format **Windows Media**     Le runtime de format Windows Media doit être installé sur tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels les conférences seront déployées. Le module d’exécution du format Windows Media est nécessaire pour exécuter les fichiers audio Windows Media (.wma) qui sont lus pour les annonces et la musique par les applications de parcage d’appel, d’annonce et Response Group.
    
    <div>
    

    > [!NOTE]
    > Pour Windows Server 2012 et Windows Server 2012 R2, le runtime du format Windows Media s’installe avec Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Pour Windows Server &nbsp; 2008 et Windows server &nbsp; 2008 &nbsp; R2, le runtime du format Windows Media est installé dans le cadre de l’expérience Bureau Windows. Il est recommandé d’installer expérience Bureau Windows avant d’installer Lync Server 2013. Si Lync Server 2013 ne trouve pas ce logiciel sur le serveur, il vous invite à l’installer, puis vous devez redémarrer le serveur pour terminer l’installation.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

