---
title: SQL Server Reporting Services (configuration requise non respectée)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.
ms.openlocfilehash: 36b9270f5046c1bd784d87c10f41a64dfcc41e2e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387202"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (configuration requise non respectée)

Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.

Pour résoudre ce problème, assurez-vous qu’un serveur de surveillance est joint au domaine, qu’il est défini dans le Générateur de topologies et que la topologie a été publiée. SQL Server Reporting Services doit également être disponible sur le SQL Server et installé en tant que fonctionnalité dans la base de données du serveur de surveillance sur le SQL Server.

Pour plus d’informations, [voir Install Monitoring Reports in Skype Entreprise Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).