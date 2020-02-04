---
title: Page Ajouter un magasin d’analyse frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Pour définir la gestion SQL Server Store, vous devez configurer les propriétés suivantes :'
ms.openlocfilehash: 67da608f8f20f838c980640a2b6785c0ebb25fb1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685157"
---
# <a name="add-front-end-monitoring-store-page"></a>Page Ajouter un magasin d’analyse frontal
 
Pour **définir la gestion SQL Server Store** , vous devez configurer les propriétés suivantes :
  
- **Surveiller SQL Server Store**: sélectionnez un nom de domaine complet SQL Server (et éventuellement une instance) dans la liste.
    
    Cliquez sur **nouveau** pour créer une nouvelle définition de nom de domaine complet SQL Server et éventuellement sur un nom d’instance pour le magasin du serveur de surveillance.
    
- Activez la case à cocher **activer la mise en miroir du magasin SQL Server** si vous souhaitez ajouter la mise en miroir de la base de données pour le serveur de surveillance.
    
    Sélectionnez une **image miroir SQL Server Store** existante dans la liste.
    
    Cliquez sur **nouveau** pour créer une nouvelle définition de nom de domaine complet SQL Server et éventuellement sur le nom d’instance du magasin en miroir.
    
- Si vous avez sélectionné **activer la mise en miroir du magasin SQL Server**, sélectionnez éventuellement **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner un magasin témoin de mise en miroir SQL Server dans la liste.
    
    Cliquez sur **nouveau** pour créer une nouvelle définition de nom de domaine complet SQL Server et éventuellement sur le nom d’instance du magasin témoin de mise en miroir.
    
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Cliquez sur **suivant** lorsque vous avez fini d’entrer les options de cette boîte de dialogue pour poursuivre la configuration.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et arrêter l’Assistant.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.
  
## <a name="see-also"></a>Voir aussi

[Association d’un magasin de surveillance à un pool frontal dans Skype Entreprise Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
