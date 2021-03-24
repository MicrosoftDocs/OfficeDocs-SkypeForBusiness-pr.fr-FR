---
title: SQL Server Reporting Services (Invoke)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: Après avoir fourni les informations requises pour le déploiement des rapports du serveur de surveillance à Microsoft SQL Server 2008 R2 ou à Microsoft SQL Server 2012 Report Services, la page Exécuter des commandes affiche un résumé des commandes émises pour installer les rapports sur SQL Server Reporting Services.
ms.openlocfilehash: b861db053a8851b05ce72a08de6dfae39b9d3bfc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096850"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="4df04-103">SQL Server Reporting Services (appeler)</span><span class="sxs-lookup"><span data-stu-id="4df04-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="4df04-104">Après avoir fourni les informations requises pour le déploiement des rapports du serveur de surveillance à Microsoft SQL Server 2008 R2 ou à Microsoft SQL Server 2012 Report Services, la page Exécuter des commandes affiche un résumé des commandes émises pour installer les rapports sur SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="4df04-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="4df04-p101">Passez en revue le résumé des commandes et notez les messages d’erreur ou d’avertissement affichés depuis les commandes. Si un fichier journal est généré, sélectionnez-le dans la liste déroulante sous la fenêtre du résumé et cliquez sur **Afficher le journal** pour afficher le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="4df04-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4df04-107">Pour que les rapports Reporting Services se déploient correctement et accèdent aux rapports une fois le déploiement terminé, vous devez avoir ouvert le port TCP/IP 80 (et éventuellement le port TCP 443 pour SSL, si vous affectez un certificat aux services de rapports) dans le Pare-feu Windows avec fonctions avancées de sécurité sur le SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4df04-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="4df04-108">Pour plus d’informations, voir [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="4df04-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="4df04-109">Après avoir passé en revue le résumé, cliquez sur **Terminer** pour terminer l’installation des rapports dans SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="4df04-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
