---
title: 'Lync Server 2013 : configuration technique requise pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c388fd04ba7600aa28a142961cd5ac07f63ae7c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Configuration technique requise pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Les exigences techniques relatives à Lync Server 2013 sont les suivantes :

  - Conditions requises pour l’infrastructure.

  - Logiciels prérequis à installer pour l’archivage.

  - Configuration requise pour le stockage des données pour l’archivage.

  - Conditions requises et éléments à prendre en compte concernant la mise à l’échelle pour le déploiement de l’archivage.

  - Conditions requises et éléments à prendre en compte concernant les performances pour les bases de données d’archivage.

<div>


> [!NOTE]  
> Les informations relatives à la mise à l’échelle et aux performances ne sont pas disponibles dans cette version de Lync Server 2013.



</div>

<div>

## <a name="infrastructure-requirements"></a>Conditions requises pour l’infrastructure

Les exigences d’infrastructure d’archivage de Lync Server 2013 sont les mêmes que pour le déploiement de Lync Server 2013. Pour plus d’informations, reportez-vous à la rubrique [Determining Your infrastructure Requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.

</div>

<div>

## <a name="archiving-prerequisites"></a>Conditions requises pour l’archivage

Lync Server 2013 rationalise les conditions préalables à l’archivage pour les raisons suivantes :

  - Le serveur d’archivage n’est plus un rôle serveur. À la place, les agents de collecte de données unifiées s’exécutent sur les serveurs frontaux dans un pool et les serveurs Standard Edition pour capturer les données pour l’archivage, afin de ne pas avoir à configurer des plateformes système séparées pour l’archivage.

  - L’archivage utilise le stockage de fichiers Lync Server 2013 pour le stockage temporaire des fichiers de contenu de réunion, de sorte que vous ne configurez pas de magasin de fichiers distinct pour l’archivage.

  - Dans Lync Server 2013, la mise en file d’attente des messages n’est pas obligatoire.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Configuration requise pour le stockage des données pour l’archivage

Vous devez en plus configurer l’infrastructure pour le stockage de l’archivage. Cela comprend le ou les éléments suivants :

  - **Stockage Microsoft Exchange**. Les fichiers de contenu de réunion, par exemple les présentations PowerPoint, sont archivés sous forme de pièces jointes. Si vous souhaitez utiliser l’intégration de Microsoft Exchange de sorte que les données d’archive Lync soient stockées avec les données de conformité d’Exchange, vous devez utiliser Exchange 2013 pour votre déploiement Exchange et vous assurer que la taille de stockage maximale prend en charge le stockage des fichiers de contenu de réunion. Si vous déployez l’archivage à l’aide de l’option d’intégration de Microsoft Exchange, les données d’archivage Lync sont stockées avec des données de conformité Exchange 2013 uniquement pour les utilisateurs hébergés sur vos serveurs Exchange 2013. Vous devez déployer Exchange 2013 avant de déployer et d’activer l’archivage à l’aide de l’option d’intégration de Microsoft Exchange. Si vous choisissez d’utiliser le stockage Exchange 2013, il n’est pas nécessaire de déployer des bases de données SQL Server distinctes pour l’archivage, sauf si vous avez des utilisateurs Lync qui ne sont pas hébergés sur vos serveurs Exchange 2013.

  - **Stockage de base de données SQL Server pour l’archivage**. Pour prendre en charge les utilisateurs qui ne sont pas hébergés sur des serveurs Exchange 2013 ou si vous ne souhaitez pas utiliser l’option d’intégration de Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server. Lync Server 2013 prend en charge les versions 64 bits suivantes de SQL Server :
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 entreprise
    
      - Microsoft SQL Server 2012 standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express et Microsoft SQL Server 2012 Express ne sont pas pris en charge pour l’archivage. les versions 32 bits de SQL Server ne sont pas prises en charge. Pour plus d’informations sur la configuration requise et les restrictions liées à SQL Server, voir <A href="lync-server-2013-database-software-support.md">Database Software support in Lync Server 2013</A> dans la documentation de planification ou dans la documentation de prise en charge.

    
    </div>
    
    Vous devez configurer les plateformes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriées, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, voir SQL Server TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

