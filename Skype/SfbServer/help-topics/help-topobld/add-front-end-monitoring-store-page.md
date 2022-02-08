---
title: Page Ajouter un magasin d’analyse frontal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Vous pouvez définir le magasin SQL Server pour la surveillance en configurant les propriétés suivantes :'
ms.openlocfilehash: c8d42a9b5deea557909a961d304a0508907c8c58
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391266"
---
# <a name="add-front-end-monitoring-store-page"></a>Page Ajouter un magasin d’analyse frontal
 
Vous pouvez **définir le magasin SQL Server pour la surveillance** en configurant les propriétés suivantes :
  
- **Surveillance SQL Server magasin :** sélectionnez un SQL Server de domaine complet (et éventuellement une instance) dans la liste.
    
    Cliquez **sur Nouveau** pour créer une définition SQL Server FQDN et éventuellement un nom d’instance pour le magasin du serveur de surveillance.
    
- Activez **la case à SQL Server la** mise en miroir du magasin si vous souhaitez ajouter la mise en miroir de base de données pour le serveur de surveillance.
    
    Sélectionnez un **Miroir du magasin SQL Server de surveillance** existant dans la liste.
    
    Cliquez **sur Nouveau** pour créer une définition SQL Server FQDN et éventuellement un nom d’instance pour le magasin miroir.
    
- Si vous avez sélectionné Activer la **mise en miroir** du magasin SQL Server, vous pouvez éventuellement sélectionner Utiliser le témoin de mise en miroir SQL Server pour activer le **failover** automatique afin de sélectionner un magasin de témoins de mise en miroir SQL Server dans la liste.
    
    Cliquez **sur Nouveau** pour créer une définition SQL Server FQDN et éventuellement un nom d’instance pour le magasin témoin de mise en miroir.
    
Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.
  
Après avoir défini les options de cette boîte de dialogue, cliquez sur **Suivant** pour poursuivre la configuration.
  
Cliquez sur **Annuler** pour ignorer toutes les modifications et quitter l’Assistant.
  
Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.
  
## <a name="see-also"></a>Voir aussi

[Associer un magasin d’analyse à un pool frontal dans Skype Entreprise Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
