---
title: Configurer un service informations d’emplacement secondaire dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurer une base de données source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 36bbe6183fa6f4eb086c8676e17c63f63fc994a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006526"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurer un service informations d’emplacement secondaire dans Skype pour Business Server
 
Configurer une base de données source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Enterprise Voice. 
  
Skype pour Business Server fournit une interface de service web que vous pouvez utiliser pour faire pointer le service d’informations sur l’emplacement des bases de données Source d’emplacement secondaire (SLS). L’interface du service web qui se connecte à la base de données SLS doit être conforme à WSDL du service informations d’emplacement. Si une base de données de l’emplacement et la base de données d’emplacements secondaires sont configurés, le service informations d’emplacement tout d’abord interroge la base de données d’emplacement et si aucune correspondance n’est trouvée, envoie la demande d’emplacement à partir du client à la base de données SLS. Si l’emplacement existe dans le SLS, le service informations d’emplacement envoie ensuite l’emplacement sur le client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Pour configurer une base de données d’emplacements secondaires

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

