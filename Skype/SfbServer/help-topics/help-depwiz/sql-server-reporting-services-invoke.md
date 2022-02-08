---
title: SQL Server Reporting Services (Invoke)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: Après avoir fourni les informations requises pour le déploiement des rapports du serveur de surveillance à Microsoft SQL Server 2008 R2 ou à Microsoft SQL Server 2012 Report Services, la page Exécuter des commandes affiche un résumé des commandes émises pour installer les rapports sur le SQL Server Reporting Services .
ms.openlocfilehash: eaf75612ca0ef735edc208f86e07d71bd48db078
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388502"
---
# <a name="sql-server-reporting-services-invoke"></a>SQL Server Reporting Services (appeler)
 
Après avoir fourni les informations requises pour le déploiement des rapports du serveur de surveillance à Microsoft SQL Server 2008 R2 ou à Microsoft SQL Server 2012 Report Services, la page Exécuter des commandes affiche un résumé des commandes émises pour installer les rapports sur le SQL Server Reporting Services .
  
Passez en revue le résumé des commandes et notez les messages d’erreur ou d’avertissement affichés depuis les commandes. Si un fichier journal est généré, sélectionnez-le dans la liste déroulante sous la fenêtre du résumé et cliquez sur **Afficher le journal** pour afficher le fichier journal.
  
> [!IMPORTANT]
> Pour que les rapports Reporting Services se déploient correctement et accèdent aux rapports une fois le déploiement terminé, vous devez avoir ouvert le port TCP/IP 80 (et éventuellement le port TCP 443 pour SSL, si vous affectez un certificat aux services de rapports) dans le pare-feu Windows avec fonctions avancées de sécurité sur le SQL Server. Pour plus d’informations, voir [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.
  
Après avoir passé en revue le résumé, cliquez sur **Terminer** pour terminer l’installation des rapports sur le SQL Server Reporting Services.
