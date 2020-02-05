---
title: Configurer une application SNMP dans Skype entreprise Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurer une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: fd8db117f590343d3e2f5a0194a0f6d8c3bcfb39
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768137"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurer une application SNMP dans Skype entreprise Server
 
Configurer une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype entreprise Server Voice. 
  
Skype entreprise Server inclut une interface de service Web standard que vous pouvez utiliser pour connecter le service d’information d’emplacement aux applications SNMP (simple Network Management Protocol) qui correspondent aux adresses MAC et aux informations sur les ports et aux commutateurs. 
  
Si une application SNMP est installée et que le service des informations de géolocalisation ne trouve pas de correspondance dans la base de données de localisation, le service d’information d’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client. Le service d’information d’emplacement utilise alors le port et les informations de commutation renvoyées par l’application SNMP pour interroger de nouveau la base de données d’emplacement.
  
> [!NOTE]
> Les adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Pour configurer l’URL de l’application SNMP

1.  Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

