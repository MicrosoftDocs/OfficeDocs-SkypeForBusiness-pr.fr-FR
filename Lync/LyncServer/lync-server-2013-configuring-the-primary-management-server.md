---
title: Configuration du serveur d’administration principal
TOCTitle: Configuration du serveur d’administration principal
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204844(v=OCS.15)
ms:contentKeyID: 49297057
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du serveur d’administration principal

 

_**Dernière rubrique modifiée :** 2016-12-08_

Afin de tirer le meilleur parti des nouvelles fonctionnalités d’analyse d’intégrité incluses dans Microsoft Lync Server 2013, les administrateurs doivent d’abord désigner un ordinateur en tant que serveur d’administration principal. Sur cet ordinateur, vous devez ensuite installer System Center Operations Manager 2007 R2 ou System Center Operations Manager 2012. En outre, vous devez installer une version prise en charge de SQL Server qui fonctionnera en tant que base de données primaire Operations Manager. Si vous utilisez System Center Operations Manager 2012, vous pouvez recourir à l’une des versions suivantes de SQL Server pour votre base de données primaire :

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Si vous utilisez System Center Operations Manager 2007 R2, nous vous recommandons d’installer SQL Server 2005 Service Pack 4 ou SQL Server 2008 Service Pack 3. Vous pouvez également utiliser SQL Server 2008 R2 en tant que base de données primaire pour System Center Operations Manager 2007 R2. Pour plus d’informations sur la configuration de SQL Server 2008 R2 afin de l’utiliser avec System Center Operations Manager 2007 R2, voir l’annexe 1 de cette documentation.

Quand vous installez System Center Operations Manager 2012 ou System Center Operations Manager 2007 R2, vous devez installer tous les composants de ce produit, notamment :

  - Base de données opérationnelle

  - Serveur

  - Console

  - Applets de commande Windows PowerShell

  - Console web

  - Création de rapports

  - Data Warehouse

Ces composants et leur installation ne sont pas décrits en détail dans le présent document. Pour plus d’informations sur System Center Operations Manager 2007 R2, voir la documentation d’Operations Manager 2007 R2 à l’adresse [http://go.microsoft.com/fwlink/?linkid=257526\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=257526%26clcid=0x40c) et la documentation de System Center Operations Manager 2012 à l’adresse [http://go.microsoft.com/fwlink/?linkid=257527\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=257527%26clcid=0x40c). Suivez ces instructions, si vous comptez utiliser SQL Server 2005 ou SQL Server 2008 Service Pack 1 pour votre base de données primaire.

Si vous utilisez System Center Operations Manager 2012, vous pouvez recourir à SQL Server 2012 pour votre base de données primaire. Pour plus d’informations sur SQL Server 2012, voir la documentation en ligne de SQL Server 2012 à l’adresse [http://go.microsoft.com/fwlink/?linkid=257528\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=257528%26clcid=0x40c).

N’oubliez pas que vous ne pouvez avoir qu’un seul serveur d’administration principal par déploiement Lync Server. Par ailleurs, bien que vous puissiez utiliser System Center Operations Manager 2012 ou System Center Operations Manager 2007 R2, vous ne pouvez pas exécuter les deux applications simultanément ; vous devez choisir l’une ou l’autre. Par exemple, si vous exécutez System Center Operations Manager 2012, tous vos agents System Center doivent également exécuter System Center Operations Manager 2012. Vous ne pouvez pas avoir certains agents qui exécutent System Center Operations Manager 2012 et d’autres agents qui exécutent System Center Operations Manager 2007 R2.

