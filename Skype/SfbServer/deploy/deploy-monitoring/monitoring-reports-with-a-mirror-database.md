---
title: Associer des rapports de surveillance à une base de données miroir dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Résumé : Découvrez comment associer des rapports de surveillance à une base de données miroir utilisée par Skype Entreprise Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802164"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Associer des rapports de surveillance à une base de données miroir dans Skype Entreprise Server 
 
**Résumé :** Découvrez comment associer des rapports de surveillance à une base de données miroir utilisée par Skype Entreprise Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Surveiller les rapports avec une base de données miroir

Si vous configurez un miroir pour votre base de données de surveillance, cette base de données miroir prendra le relais en tant que base de données primaire en cas de failover. Toutefois, si vous utilisez les rapports de surveillance de Skype Entreprise Server et qu’un échec se produit, il se peut que vous trouviez que vos rapports de surveillance ne se connectent pas à la base de données miroir. En effet, lorsque vous installez les rapports de surveillance, vous spécifiez uniquement l’emplacement de la base de données principale . vous ne spécifiez pas l’emplacement de la base de données miroir.
  
Pour que les rapports de surveillance soient automatiquement mis à jour vers la base de données miroir, vous devez ajouter la base de données miroir en tant que « partenaire deover » aux deux bases de données utilisées par les rapports de surveillance (une base de données pour les données d’enregistrement des détails des appels et l’autre pour les données de qualité de l’expérience (QoE). (Notez que cette étape doit être effectuée après l’installation des rapports de surveillance.) Vous pouvez ajouter les informations du partenaire deover en éditant manuellement les valeurs de chaîne de connexion utilisées par ces deux bases de données. Pour ce faire, procédez de la manière suivante :
  
1. Utilisez Internet Explorer pour ouvrir la page **d’SQL Server Reporting Services.** L’URL de la page d’accueil reporting Services inclut :
    
   - **Préfixe http:**
    
   - Nom de domaine complet (FQDN) de l’ordinateur sur lequel Reporting Services est installé (par exemple, **atl-sql-001.litwareinc.com**).
    
   - Chaîne de **caractères /Reports_**.
    
   - Nom de l’instance de base de données où les rapports de surveillance sont installés (par exemple, **archinst**).
    
     Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil ressemble à ceci :
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Une fois que vous avez accédé à la page d’accueil de Reporting Services, cliquez sur **ServerReports,** puis cliquez **sur Reports_Content**. Cela vous permettra **d’Reports_Content** la page des rapports de surveillance de Skype Entreprise Server.
    
3. Dans la page **Reports_Content,** cliquez sur la source de données **CDRDB.**
    
4. Dans la page **CDRDB, sous** l’onglet **Propriétés,** recherchez la zone de texte « **Chaîne de connexion**». La chaîne de connexion actuelle ressemblera à ceci :
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Modifiez la chaîne de connexion pour inclure le nom du serveur et l’instance de base de données pour la base de données miroir. Par exemple, si le serveur est nommé atl-mirror-001 et que la base de données miroir se trouve dans l’instance archinst, vous devez ajouter pour spécifier la base de données miroir à l’aide de cette syntaxe :
    
    Failover Partner=atl-mirror-001\archinst
    
    Votre chaîne de connexion modifiée ressemblera à ceci :
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Après avoir mis à jour la chaîne de connexion, cliquez sur **Appliquer.**
    
7. Dans la page **CDRDB,** cliquez sur **Reports_Content** lien. Cliquez sur la source de **données QMSDB,** puis modifiez la chaîne de connexion pour la base de données QoE. Par exemple :
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Cliquez sur **Appliquer**.
    
## <a name="see-also"></a>Voir aussi

[Installer des rapports de surveillance dans Skype Entreprise Server](install-monitoring-reports.md)
  
[Utilisation des rapports de surveillance dans Skype Entreprise Server](../../manage/health-and-monitoring/monitoring-reports.md)
