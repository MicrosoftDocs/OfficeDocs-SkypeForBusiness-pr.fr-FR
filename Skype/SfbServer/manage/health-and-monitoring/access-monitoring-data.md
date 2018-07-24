---
title: Accès aux données dans Skype de surveillance pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Résumé : Découvrez les données de surveillance utilisées dans Skype pour Business Server.'
ms.openlocfilehash: 4bd7d7c55f2d041d1bd3d80cf056544cd5bf5ee1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986585"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Accès aux données dans Skype de surveillance pour Business Server
 
**Résumé :** Obtenir des informations sur les données de surveillance utilisées dans Skype pour Business Server.
  
Les données de surveillance sont stockées dans deux bases de données SQL Server: LcsCdr pour les données d’enregistrement de détails des appels et QoEMetrics pour les données de qualité de l’expérience. Ces deux bases de données n’ont rien de particulier, les données qu’elles contiennent sont accessibles avec les outils que vous utilisez habituellement pour accéder à et analyser des données SQL Server.
  
Un outil, que vous devez prendre en compte d’accès et d’analyse des données de surveillance est le Skype pour les rapports de surveillance Business Server. Ces rapports de surveillance sont un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service. Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE. Rapports de surveillance livrées avec Skype pour Business Server et peuvent être installés à partir de la Skype pour l’Assistant de déploiement Business Server après Skype pour Business Server a été installé et de surveillance a été configuré.
  
Comme cela a été indiqué, les rapports de surveillance nécessitent l’utilisation de SQL Server Reporting Service. SQL Server Reporting Service peut être installé en même temps que SQL Server ou ultérieurement.
  
Pour plus d’informations, consultez la rubrique [Installer les rapports de surveillance dans Skype pour Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

