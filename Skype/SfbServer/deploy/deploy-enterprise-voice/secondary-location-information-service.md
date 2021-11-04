---
title: Configurer un service Informations d’emplacement secondaire dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurez une base de données SLS (Secondary Location Source) pour E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 6d42375ddc127bd19a73d64782f4f6840a373b87
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753451"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurer un service Informations d’emplacement secondaire dans Skype Entreprise Server
 
Configurez une base de données SLS (Secondary Location Source) pour E9-1-1 dans Skype Entreprise Server Voix Entreprise. 
  
Skype Entreprise Server fournit une interface de service web que vous pouvez utiliser pour faire pointer le service Informations d’emplacement vers une base de données SLS (Secondary Location Source). L’interface de service web qui se connecte à la base de données SLS doit être conforme au service d’informations d’emplacement WSDL. Si une base de données d’emplacements et une base de données d’emplacements secondaires sont configurées, le service Informations sur l’emplacement interroge d’abord la base de données d’emplacements et, si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client à la base de données SLS. Si l’emplacement existe dans le service SLS, le service Informations d’emplacement renvoie l’emplacement au client. 
  
### <a name="to-configure-a-secondary-location-database"></a>Pour configurer une base de données d’emplacements secondaires

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Exécutez l’applet de commande suivante pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)