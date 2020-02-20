---
title: 'Lync Server 2013 : configuration du serveur d’administration principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68fc10ba0457b0ad29f6f3850c1d7056d27fd24d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Configuration du serveur d’administration principal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-19_

Pour tirer pleinement parti des nouvelles fonctionnalités d’analyse d’intégrité incluses dans les administrateurs de Microsoft Lync Server 2013, vous devez d’abord désigner un ordinateur qui agira en tant que serveur d’administration principal ; sur cet ordinateur, vous devez ensuite installer System Center Operations Manager 2007 R2 ou System Center Operations Manager 2012. En outre, vous devez installer une version prise en charge de SQL Server pour qu’elle fonctionne en tant que base de données principale Operations Manager. Si vous utilisez System Center Operations Manager 2012, vous pouvez utiliser l’une des versions suivantes de SQL Server comme base de données principale :

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Si vous utilisez System Center Operations Manager 2007 R2, il est recommandé d’installer SQL Server 2005 Service Pack 4 ou SQL Server 2008 Service Pack 3. Vous pouvez également utiliser SQL Server 2008 R2 comme base de données principale pour System Center Operations Manager 2007 R2. Voir l’annexe 1 de cette documentation pour plus d’informations sur la configuration de SQL Server 2008 R2 pour qu’elle fonctionne avec System Center Operations Manager 2007 R2.

Lorsque vous installez System Center Operations Manager 2012 ou System Center Operations Manager 2007 R2, vous devez installer tous les composants de ce produit, notamment :

  - Base de données opérationnelle

  - Serveur

  - Console

  - Applets de commande Windows PowerShell

  - Console web

  - Reporting

  - Data Warehouse

Ces composants et leur installation ne sont pas décrits en détail dans le présent document. Pour plus d’informations sur System Center Operations Manager 2007 R2, reportez-vous <https://go.microsoft.com/fwlink/p/?linkid=257526> à la documentation Operations Manager 2007 R2 à <https://go.microsoft.com/fwlink/p/?linkid=257527>l’adresse et à la documentation de System center Operations Manager 2012 à l’adresse. Suivez ces instructions si vous envisagez d’utiliser SQL Server 2005 ou SQL Server 2008 Service Pack 1 comme base de données principale.

Si vous utilisez System Center Operations Manager 2012, vous pouvez utiliser SQL Server 2012 comme base de données principale. Pour plus d’informations sur SQL Server 2012, reportez-vous à [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)la documentation en ligne de sql Server 2012 à l’adresse.

N’oubliez pas que vous ne pouvez avoir qu’un seul serveur de gestion principal par déploiement Lync Server. En outre, si vous pouvez utiliser System Center Operations Manager 2012 ou System Center Operations Manager 2007 R2, vous ne pouvez pas exécuter simultanément les deux applications, mais vous devez choisir l’une ou l’autre. Par exemple, si vous exécutez System Center Operations Manager 2012, tous vos agents System Center doivent également exécuter System Center Operations Manager 2012. Certains agents ne peuvent pas exécuter System Center Operations Manager 2012 et d’autres agents exécutant System Center Operations Manager 2007 R2.

</div>

<span> </span>

</div>

</div>

</div>

