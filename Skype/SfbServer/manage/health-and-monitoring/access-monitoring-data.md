---
title: Accès aux données de surveillance dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Résumé : Découvrez les données d’analyse utilisées dans Skype pour Business Server 2015.'
ms.openlocfilehash: 908ebbff4e88985cdba606098dc5a5ace271e30d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="access-monitoring-data-in-skype-for-business-server-2015"></a><span data-ttu-id="04180-103">Accès aux données de surveillance dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="04180-103">Access monitoring data in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="04180-104">**Résumé :** Obtenir des informations sur les données d’analyse utilisées dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="04180-104">**Summary:** Learn about the monitoring data used in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="04180-p101">Les données de surveillance sont stockées dans deux bases de données SQL Server: LcsCdr pour les données d’enregistrement de détails des appels et QoEMetrics pour les données de qualité de l’expérience. Ces deux bases de données n’ont rien de particulier, les données qu’elles contiennent sont accessibles avec les outils que vous utilisez habituellement pour accéder à et analyser des données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04180-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="04180-107">Un outil que vous envisagez pour l’accès et l’analyse des données d’analyse est la Skype pour les rapports de surveillance Business Server.</span><span class="sxs-lookup"><span data-stu-id="04180-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="04180-108">Ces rapports de surveillance sont un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="04180-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="04180-109">Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE.</span><span class="sxs-lookup"><span data-stu-id="04180-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="04180-110">Surveiller le rapports fournis avec Skype pour Business Server 2015 et peuvent être installés à partir de la Skype pour l’Assistant de déploiement de Business Server une fois Skype pour Business Server a été installé et analyse a été configuré.</span><span class="sxs-lookup"><span data-stu-id="04180-110">Monitoring Reports ship with Skype for Business Server 2015 and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="04180-p103">Comme cela a été indiqué, les rapports de surveillance nécessitent l’utilisation de SQL Server Reporting Service. SQL Server Reporting Service peut être installé en même temps que SQL Server ou ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="04180-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="04180-113">Pour plus d’informations, voir la rubrique [Installer les rapports de surveillance dans Skype pour Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) dans le Skype pour le guide de déploiement d’entreprise serveur 2015.</span><span class="sxs-lookup"><span data-stu-id="04180-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) in the Skype for Business Server 2015 deployment guide.</span></span>
  

