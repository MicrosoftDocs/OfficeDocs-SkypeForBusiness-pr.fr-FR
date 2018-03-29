---
title: SQL Server Reporting Services (configuration requise non respectée)
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
ms.openlocfilehash: e55310f8767daa7fc2be42e97ee4b3e368d158a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (configuration requise non respectée)
 
Si aucun serveur de surveillance n’est déployé dans votre infrastructure, cette page s’affiche. Elle indique que les conditions requises pour le déploiement d’un serveur de surveillance ne sont pas respectées. 
  
Pour résoudre ce problème, assurez-vous que vous disposez d’un serveur de surveillance est joint au domaine, qu’elle est définie dans le Générateur de topologies, et que la topologie a été publiée. SQL Server Reporting Services doit également être disponibles sur le SQL Server et installé comme une fonction dans la base de données Monitoring Server sur le SQL Server. 
  
Pour plus d’informations, consultez [installer surveillance dans Skype pour Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) et [Déploiement de surveillance](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).
  

