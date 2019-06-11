---
title: 'Lync Server 2013: exigences techniques de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Configuration technique requise pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

Les exigences techniques de Lync Server 2013 sont les suivantes:

  - Exigences d’infrastructure.

  - Logiciels requis qui doivent être installés pour l’archivage.

  - Exigences en matière de stockage des données pour l’archivage.

  - Exigences relatives à l’échelle et considérations relatives à votre déploiement d’archivage.

  - Exigences et considérations en matière de performances pour vos bases de données d’archivage.

<div>


> [!NOTE]  
> Les informations de mise à l’échelle et de performance ne sont pas disponibles dans la version 2013 de Lync Server.



</div>

<div>

## <a name="infrastructure-requirements"></a>Exigences d’infrastructure

Les exigences d’infrastructure d’archivage de Lync Server 2013 sont les mêmes que pour le déploiement de Lync Server 2013. Pour plus d’informations, reportez-vous à la rubrique [détermination de votre configuration d’infrastructure requise pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.

</div>

<div>

## <a name="archiving-prerequisites"></a>Archivage requis

Lync Server 2013 simplifie les conditions préalables à l’archivage pour les raisons suivantes:

  - Le serveur d’archivage n’est plus un rôle serveur. Au lieu de cela, les agents de collection de données unifiés s’exécutent sur les serveurs frontaux d’un pool et de serveurs Standard Edition pour capturer les données pour l’archivage, de sorte que vous ne configurez pas des plateformes système distinctes pour l’archivage.

  - L’archivage utilise le stockage de fichiers de Lync Server 2013 pour stocker temporairement les fichiers de contenu de la réunion, de sorte que vous n’avez pas configuré de magasin de fichiers distinct pour l’archivage.

  - Dans Lync Server 2013, Message Queuing n’est pas requis.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Exigences en matière de stockage des données pour l’archivage

Par ailleurs, vous devez configurer l’infrastructure pour le stockage d’archivage. Cela comprend les éléments suivants:

  - **Stockage Microsoft Exchange**. Meeting content files, such as PowerPoint presentations, are archived as attachments. Si vous souhaitez utiliser l’intégration de Microsoft Exchange de sorte que les données d’archive Lync soient stockées avec les données de conformité Exchange, vous devez utiliser Exchange 2013 pour votre déploiement Exchange et garantir que la taille de stockage maximale prend en charge le stockage des fichiers de contenu de la réunion. Si vous déployez l’archivage à l’aide de l’option d’intégration de Microsoft Exchange, les données d’archive Lync sont stockées avec les données de conformité Exchange 2013 uniquement pour les utilisateurs qui sont hébergés sur vos serveurs Exchange 2013. Vous devez déployer Exchange 2013 avant de déployer et d’activer l’archivage à l’aide de l’option d’intégration de Microsoft Exchange. Si vous choisissez d’utiliser le stockage Exchange 2013, vous n’avez pas besoin de déployer des bases de données SQL Server distinctes pour l’archivage, sauf si vous avez des utilisateurs de Lync qui ne sont pas hébergés sur vos serveurs Exchange 2013.

  - **Stockage de base de données SQL Server pour l’archivage**. Pour prendre en charge les utilisateurs qui ne sont pas hébergés sur des serveurs Exchange 2013 ou si vous ne voulez pas utiliser l’option d’intégration de Microsoft Exchange, vous devez déployer le stockage d’archivage à l’aide d’une base de données SQL Server. Lync Server 2013 prend en charge les versions 64 bits suivantes de SQL Server:
    
      - Microsoft SQL Server 2008 R2 entreprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 entreprise
    
      - Microsoft SQL Server 2012 standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express et Microsoft SQL Server 2012 Express ne sont pas pris en charge pour l’archivage. les versions 32 bits de SQL Server ne sont pas prises en charge. Pour plus d’informations et de restrictions concernant SQL Server, voir <A href="lync-server-2013-database-software-support.md">prise en charge de logiciels de base de données dans Lync Server 2013</A> dans la documentation de planification ou dans la documentation sur la prise en charge.

    
    </div>
    
    Vous devez configurer les plates-formes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriés, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données ultérieurement, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, voir le site TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

