---
title: 'Lync Server 2013 : Vue d’ensemble du déploiement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Vue d’ensemble du déploiement pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

La principale différence entre Lync Server 2013 Enterprise Edition et Lync Server 2013 Standard Edition est que Standard Edition ne prend pas en charge les fonctionnalités de haute disponibilité incluses dans l’édition Enterprise. Pour une disponibilité élevée, vous devez déployer plusieurs serveurs frontaux vers un pool, puis vous pouvez mettre en miroir le serveur exécutant SQL Server. Avec Enterprise Edition, vous pouvez choisir de collocate ou de définir un serveur de médiation autonome. Le serveur de surveillance et l’archivage serveur peuvent utiliser un serveur autonome exécutant SQL Server. Des instances de SQL Server peuvent être exécutées sur le serveur de base de données pour les serveurs frontaux et les pools.

Les serveurs exécutant Lync Server 2013 Standard Edition sont destinés aux organisations plus petites et aux emplacements distants, qui sont retirés géographiquement du déploiement principal de l’organisation. Deux serveurs Standard Edition Server associés à une reprise en cas de sinistre peuvent prendre en charge jusqu’à 5 000 utilisateurs. Vous ne pouvez pas mettre en réserve les serveurs Standard Edition tels que vous pouvez disposer de serveurs frontaux dans l’édition Enterprise. Par ailleurs, la base de données SQL Server utilisée par Standard Edition est un serveur colocalisé exécutant SQL Server Express conçu pour gérer les charges de travail des serveurs Standard Edition. Ce n’est pas dire que tous les rôles doivent résider sur un serveur Standard Edition Server. Vous pouvez disposer de serveurs de médiation autonomes et de serveurs Edge. La base de données SQL Server du magasin de gestion central et aux fins de Lync Server 2013 doit résider sur un serveur Standard Edition Server en tant que serveur exécutant SQL Server. Le serveur de surveillance et le serveur d’archivage utilisent un serveur autonome avec la base de données SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

