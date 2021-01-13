---
title: Accéder aux données de surveillance dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Résumé : Découvrez les données de surveillance utilisées dans Skype Entreprise Server.'
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826544"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="0ba5b-103">Accéder aux données de surveillance dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0ba5b-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="0ba5b-104">**Résumé :** Découvrez les données de surveillance utilisées dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0ba5b-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="0ba5b-p101">Les données de surveillance sont stockées dans deux bases de données SQL Server: LcsCdr pour les données d’enregistrement de détails des appels et QoEMetrics pour les données de qualité de l’expérience. Ces deux bases de données n’ont rien de particulier, les données qu’elles contiennent sont accessibles avec les outils que vous utilisez habituellement pour accéder à et analyser des données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ba5b-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="0ba5b-107">Les rapports de surveillance de Skype Entreprise Server sont un outil que vous devez envisager pour accéder aux données de surveillance et les analyser.</span><span class="sxs-lookup"><span data-stu-id="0ba5b-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="0ba5b-108">Ces rapports de surveillance sont un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="0ba5b-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="0ba5b-109">Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE.</span><span class="sxs-lookup"><span data-stu-id="0ba5b-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="0ba5b-110">Les rapports de surveillance sont produits avec Skype Entreprise Server et peuvent être installés à partir de l’Assistant Déploiement de Skype Entreprise Server après l’installation de Skype Entreprise Server et la configuration de la surveillance.</span><span class="sxs-lookup"><span data-stu-id="0ba5b-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="0ba5b-p103">Comme cela a été indiqué, les rapports de surveillance nécessitent l’utilisation de SQL Server Reporting Service. SQL Server Reporting Service peut être installé en même temps que SQL Server ou ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="0ba5b-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="0ba5b-113">Pour plus d’informations, voir la rubrique Installer des rapports [de surveillance dans Skype Entreprise Server.](../../deploy/deploy-monitoring/install-monitoring-reports.md)</span><span class="sxs-lookup"><span data-stu-id="0ba5b-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

