---
title: SQL Server Reporting Services (configuration requise non respectée)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.
ms.openlocfilehash: 6da0c7439d59676429781b209ab52c90e64f5588
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878465"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="99592-104">SQL Server Reporting Services (configuration requise non respectée)</span><span class="sxs-lookup"><span data-stu-id="99592-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="99592-p102">Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.</span><span class="sxs-lookup"><span data-stu-id="99592-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="99592-107">Pour résoudre ce problème, assurez-vous que vous disposez d’un serveur de surveillance lié au domaine, qu’elle est définie dans le Générateur de topologie, et que la topologie a été publiée.</span><span class="sxs-lookup"><span data-stu-id="99592-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="99592-108">SQL Server Reporting Services doit également être disponibles sur le serveur SQL Server et installé en tant que fonctionnalité dans la base de données du serveur de surveillance sur le serveur SQL.</span><span class="sxs-lookup"><span data-stu-id="99592-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="99592-109">Pour plus d’informations, voir [Installer des rapports de surveillance dans Skype pour Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) et [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="99592-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


