---
title: Accéder aux données de surveillance dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Résumé : Découvrez les données de surveillance utilisées dans Skype Entreprise Server.'
ms.openlocfilehash: 49adf9caca82f97b0483743f65c7dea7b0f72a01
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852068"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Accéder aux données de surveillance dans Skype Entreprise Server
 
**Résumé :** Découvrez les données de surveillance utilisées dans Skype Entreprise Server.
  
Les données de surveillance sont stockées dans deux bases de données SQL Server: LcsCdr pour les données d’enregistrement de détails des appels et QoEMetrics pour les données de qualité de l’expérience. Ces deux bases de données n’ont rien de particulier, les données qu’elles contiennent sont accessibles avec les outils que vous utilisez habituellement pour accéder à et analyser des données SQL Server.
  
L’un des outils à prendre en compte pour accéder aux données de surveillance et les analyser est Skype Entreprise Server rapports de surveillance. Ces rapports de surveillance sont un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service. Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE. Les rapports de surveillance sont Skype Entreprise Server et peuvent être installés à partir de l’Assistant Déploiement Skype Entreprise Server une fois Skype Entreprise Server installé et la surveillance configurée.
  
Comme cela a été indiqué, les rapports de surveillance nécessitent l’utilisation de SQL Server Reporting Service. SQL Server Reporting Service peut être installé en même temps que SQL Server ou ultérieurement.
  
Pour plus d’informations, voir la rubrique Installer les rapports de surveillance [dans Skype Entreprise Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

