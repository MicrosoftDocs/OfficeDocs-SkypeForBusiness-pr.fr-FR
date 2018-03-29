---
title: Associer des rapports de surveillance à une base de données miroir dans Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Résumé : Apprenez à associer des rapports de surveillance à une base de données miroir utilisé par Skype pour Business Server 2015.'
ms.openlocfilehash: 246f16fd54133e2a6cf1e26a8126d0ec546bd686
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server-2015"></a>Associer des rapports de surveillance à une base de données miroir dans Skype pour Business Server 2015
 
**Résumé :** Découvrez comment associer des rapports de surveillance à une base de données miroir utilisé par Skype pour Business Server 2015.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Rapports de surveillance avec une base de données miroir

Si vous configurez une instance miroir pour votre base de données de surveillance, cette base de données miroir prendra la relève en tant que base de données principale en cas de basculement. Toutefois, si vous utilisez Skype pour les rapports de surveillance de serveur Business et si un basculement se produit, vous trouverez que vos rapports de surveillance ne vous connectez pas à la base de données miroir. Et ce, car, lorsque vous installez des rapports de surveillance, vous spécifiez seulement l’emplacement de la base de données principale ; vous devez aussi spécifier l’emplacement de la base de données miroir.
  
Pour que les rapports basculent automatiquement sur la base de données miroir, vous devez ajouter la base de données miroir comme « partenaire de basculement » pour les deux bases de données utilisées par les rapports de surveillance (l’une pour les données d’enregistrement des détails des appels, et l’autre pour les données de la qualité de l’expérience (QoE)). (Notez que cette étape doit être effectuée après l’installation des rapports de surveillance.) Vous pouvez ajouter les informations du partenaire de basculement en modifiant manuellement les valeurs des chaînes de connexion utilisées par ces deux bases de données. Pour cela, procédez comme suit :
  
1. Utilisez Internet Explorer pour ouvrir la page d’accueil de **SQL Server Reporting Services**. L’URL de cette page d’accueil comprend ce qui suit :
    
   - Le préfixe **http:**.
    
   - Le nom de domaine complet (FQDN) de l’ordinateur sur lequel les services de surveillance sont installés (par exemple, **atl-sql-001.litwareinc.com**).
    
   - La chaîne de caractères **/Reports_**.
    
   - Le nom de l’instance de la base de données où les rapports de surveillance sont installés (par exemple, **archinst**).
    
    Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil doit ressembler à ceci :
    
    **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Après avoir accédé à la page d’accueil des services de surveillance, cliquez sur **ServerReports**, puis sur **Reports_Content**. Ce lien vous amènera à la page **Reports_Content** pour le Skype pour les rapports de surveillance Business Server.
    
3. Sur la page **Reports_Content**, cliquez sur la source de données **CDRDB**.
    
4. Sur la page **CDRDB**, sous l’onglet **Propriétés**, recherchez le texte intitulé **Chaîne de connexion**. La chaîne de connexion actuelle a un format similaire à celui-ci :
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Modifiez la chaîne de connexion façon à y inclure le nom du serveur et l’instance de base de données pour la base de données miroir. Par exemple, si le serveur est nommé atl-miroir-001 et que la base de données miroir est dans l’instance archinst, vous devez en plus spécifier la base de données miroir en utilisant cette syntaxe :
    
    Failover Partner=atl-mirror-001\archinst
    
    Votre chaîne de connexion modifiée ressemblera à ceci :
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Après avoir mis à jour la chaîne de connexion, cliquez sur **Appliquer**.
    
7. Sur la page **CDRDB**, cliquez sur le lien **Reports_Content**. Cliquez sur la source de données **QMSDB**, puis modifiez la chaîne de connexion pour la base de données QoE. Par exemple :
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Cliquez sur **Appliquer**.
    
## <a name="see-also"></a>Voir aussi

#### 

[Installer la surveillance des rapports dans Skype pour Business Server 2015](install-monitoring-reports.md)
  
[À l’aide de la surveillance des rapports dans Skype pour Business Server 2015](../../manage/health-and-monitoring/monitoring-reports.md)

