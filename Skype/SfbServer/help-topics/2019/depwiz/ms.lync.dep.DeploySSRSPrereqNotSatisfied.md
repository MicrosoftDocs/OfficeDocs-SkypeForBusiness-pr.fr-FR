---
title: SQL Server Reporting Services (configuration requise non respectée)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.
ms.openlocfilehash: 12aa64658f655ce4e991f7e2d51e4388f4501c0d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993654"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="dce1e-104">SQL Server Reporting Services (configuration requise non respectée)</span><span class="sxs-lookup"><span data-stu-id="dce1e-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>
 
<span data-ttu-id="dce1e-p102">Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.</span><span class="sxs-lookup"><span data-stu-id="dce1e-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span> 
  
<span data-ttu-id="dce1e-107">Pour résoudre ce problème, assurez-vous que vous disposez d’un serveur de surveillance lié au domaine, qu’elle est définie dans le Générateur de topologie, et que la topologie a été publiée.</span><span class="sxs-lookup"><span data-stu-id="dce1e-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="dce1e-108">SQL Server Reporting Services doit également être disponibles sur le serveur SQL Server et installé en tant que fonctionnalité dans la base de données du serveur de surveillance sur le serveur SQL.</span><span class="sxs-lookup"><span data-stu-id="dce1e-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span> 
  
<span data-ttu-id="dce1e-109">Pour plus d’informations, voir [Installer des rapports de surveillance dans Skype pour Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) et [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="dce1e-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>
  

