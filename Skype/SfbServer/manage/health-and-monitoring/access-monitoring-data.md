---
title: Accéder aux données d’analyse dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Résumé: Obtenez des informations sur les données de surveillance utilisées dans Skype entreprise Server.'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303885"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Accéder aux données d’analyse dans Skype entreprise Server
 
**Résumé:** En savoir plus sur les données de surveillance utilisées dans Skype entreprise Server.
  
Les données de surveillance sont stockées dans deux bases de données SQL Server: LcsCdr pour les données d’enregistrement de détails des appels et QoEMetrics pour les données de qualité de l’expérience. Ces deux bases de données n’ont rien de particulier, les données qu’elles contiennent sont accessibles avec les outils que vous utilisez habituellement pour accéder à et analyser des données SQL Server.
  
L’un des outils que vous devez prendre en compte lors de l’accès aux données de surveillance et de leur analyse est le rapport de surveillance de Skype entreprise Server. Ces rapports de surveillance sont un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service. Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE. Les rapports d’analyse livrés avec Skype entreprise Server peuvent être installés à partir de l’Assistant Déploiement de Skype entreprise Server après l’installation et la surveillance de Skype entreprise Server.
  
Comme cela a été indiqué, les rapports de surveillance nécessitent l’utilisation de SQL Server Reporting Service. SQL Server Reporting Service peut être installé en même temps que SQL Server ou ultérieurement.
  
Pour plus d’informations, reportez-vous à la rubrique [installer les rapports de surveillance dans Skype entreprise Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

