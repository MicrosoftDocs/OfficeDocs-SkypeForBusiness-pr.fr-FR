---
title: 'Lync Server 2013 : vue d’ensemble du déploiement'
description: 'Lync Server 2013 : vue d’ensemble du déploiement.'
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
ms.openlocfilehash: 5bb3bac4261783a765b64ab2e81adb107599496b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575750"
---
# <a name="deployment-overview-for-lync-server-2013"></a>Vue d’ensemble du déploiement pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-12_

La différence principale entre Lync Server 2013 Enterprise Edition et Lync Server 2013 Standard Edition réside dans le fait que Standard Edition ne prend pas en charge les fonctionnalités de haute disponibilité incluses dans Enterprise Edition. Pour la haute disponibilité, vous devez déployer plusieurs serveurs frontaux dans un pool, puis mettre en miroir le serveur exécutant SQL Server. Avec Enterprise Edition, vous pouvez choisir de colocaliser ou de définir un serveur de médiation autonome. Le serveur de surveillance et le serveur d’archivage peuvent utiliser un serveur autonome exécutant SQL Server. Ou, les instances de SQL Server peuvent être exécutées sur le serveur de base de données pour les pools et les serveurs frontaux.

Les serveurs exécutant Lync Server 2013 Standard Edition sont conçus pour des organisations de plus petite taille et des emplacements distants, qui sont retirés géographiquement du déploiement principal de l’organisation. Deux serveurs Standard Edition Server réunis pour le basculement en cas de catastrophe peuvent prendre en charge jusqu’à 5 000 utilisateurs. Vous ne pouvez pas regrouper les serveurs Standard Edition comme vous pouvez les serveurs frontaux dans Enterprise Edition. De plus, la base de données SQL Server utilisée par Standard Edition est un serveur colocalisé exécutant SQL Server Express qui est conçu pour gérer les charges de travail de serveur Standard Edition. Cela ne signifie pas que tous les rôles doivent résider sur un serveur Standard Edition. Vous pouvez avoir des serveurs de médiation autonomes et des serveurs Edge. La base de données SQL Server pour le magasin central de gestion et pour les besoins de Lync Server 2013 doit résider sur le serveur Standard Edition colocalisé avec le serveur exécutant SQL Server. Le serveur de surveillance et le serveur d’archivage utilisent un serveur autonome avec la base de données SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

