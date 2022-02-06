---
title: SQL Server Reporting Services (configuration requise non respectée)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: 'Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.'
---

# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (configuration requise non respectée)

Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.

Pour résoudre ce problème, assurez-vous qu’un serveur de surveillance est joint au domaine, qu’il est défini dans le Générateur de topologies et que la topologie a été publiée. SQL Server Reporting Services doit également être disponible sur le SQL Server et installé en tant que fonctionnalité dans la base de données du serveur de surveillance sur le SQL Server.

Pour plus d’informations, voir [Install Monitoring Reports in Skype Entreprise Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).