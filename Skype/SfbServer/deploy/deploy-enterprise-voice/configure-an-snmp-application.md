---
title: Configuration d’une application SNMP dans Skype Entreprise Server 2015
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurer une application SNMP pour fonctionner avec E9-1-1 dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 5c10d00e05979c2a3e0efff015da61e5ff2c6ee9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a>Configuration d’une application SNMP dans Skype Entreprise Server 2015
 
Configurer une application SNMP pour fonctionner avec E9-1-1 dans Skype pour Business Server Voix Entreprise. 
  
Skype pour Business Server inclut une interface de service web standard que vous pouvez utiliser pour connecter le service d’informations d’emplacement à des applications SNMP Simple Network Management Protocol () qui correspondent aux adresses MAC par port et de passer des informations. 
  
Si une application SNMP est installée et le service d’informations d’emplacement ne parvient pas à trouver une correspondance dans la base de données de l’emplacement, le service d’informations d’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client. Le service d’informations d’emplacement utilise les informations de port et le switch retournées par l’application SNMP d’interroger la base de données de l’emplacement à nouveau.
  
> [!NOTE]
> Adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Pour configurer l’URL de l’application SNMP

1.  Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Voir aussi

#### 

[Ensemble-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

