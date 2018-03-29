---
title: Configuration d’un service Informations d’emplacement secondaire dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurer une base de données de la source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 03de4369b8473142e7a76e3698bb9fe7f129d546
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>Configuration d’un service Informations d’emplacement secondaire dans Skype Entreprise Server 2015
 
Configurer une base de données de la source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Voix Entreprise. 
  
Skype pour Business Server fournit une interface de service web que vous pouvez utiliser pour le service d’informations d’emplacement à une base de données de la Source d’emplacement secondaire (SLS). L’interface de service web qui se connecte à la base de données SLS doit se conformer au service d’informations de l’emplacement WSDL. Si une base de données de l’emplacement et la base de données du site secondaire sont configurés, le service d’informations d’emplacement tout d’abord interroge la base de données de l’emplacement et si aucune correspondance n’est trouvée, envoie la demande de l’emplacement à partir du client à la base de données SLS. Si l’emplacement existe dans le contrat SLS, le service d’informations d’emplacement envoie ensuite l’emplacement au client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Pour configurer une base de données d’emplacements secondaires

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Voir aussi

#### 

[Ensemble-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

