---
title: Configurer un service d’information d’emplacement secondaire dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurez une base de données de source d’emplacement secondaire (SLS) pour E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 28168bb10017ccc1e56ce26bb5a88629f19aff41
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767077"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurer un service d’information d’emplacement secondaire dans Skype entreprise Server
 
Configurez une base de données de source d’emplacement secondaire (SLS) pour E9-1-1 dans Skype entreprise Server Voice. 
  
Skype entreprise Server fournit une interface de service Web que vous pouvez utiliser pour faire pointer le service d’information d’emplacement vers une base de données de source d’emplacement secondaire (SLS). L’interface de service Web qui se connecte à la base de données SLS doit être conforme au WSDL. S’il s’agit d’une base de données d’emplacement et d’une base de données d’emplacement secondaire configurées, le service des informations d’emplacement interroge d’abord la base de données de localisation, et si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client vers la base de données SLS. Si l’emplacement existe dans le dossier SLS, le service d’information sur l’emplacement est alors renvoyé à l’emplacement du client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Pour configurer une base de données d’emplacements secondaires

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

