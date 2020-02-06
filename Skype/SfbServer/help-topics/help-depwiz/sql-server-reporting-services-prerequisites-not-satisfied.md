---
title: SQL Server Reporting Services (configuration requise non respectée)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.
ms.openlocfilehash: 2c5f58751d03d5c482bd3b9113b764ffe626cec6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823448"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (configuration requise non respectée)

Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées.

Pour résoudre ce problème, assurez-vous qu’un serveur de surveillance est joint au domaine, qu’il est défini dans le générateur de topologie et que la topologie a été publiée. SQL Server Reporting Services doit également être disponible sur SQL Server et installé en tant que fonctionnalité dans la base de données du serveur de surveillance sur SQL Server.

Pour plus d’informations, reportez-vous à la section [installation des rapports de surveillance dans Skype entreprise Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) et déploiement de la [surveillance](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).


