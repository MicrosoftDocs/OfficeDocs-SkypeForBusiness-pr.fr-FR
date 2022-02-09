---
title: Configurer une application SNMP dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurez une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: ba46f1d079cbf41df5cf14743520299215cdb1bd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403498"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurer une application SNMP dans Skype Entreprise Server
 
Configurez une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype Entreprise Server Voix Entreprise. 
  
Skype Entreprise Server inclut une interface de service web standard que vous pouvez utiliser pour connecter le service Informations d’emplacement aux applications SNMP (Simple Network Management Protocol) qui correspondent aux adresses MAC avec les informations de port et de commutateur. 
  
Si une application SNMP est installée et que le service Informations d’emplacement ne parvient pas à trouver de correspondance dans la base de données d’emplacements, le service Informations sur l’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client. Le service Informations d’emplacement utilise ensuite les informations de port et de commutateur renvoyées par l’application SNMP pour interroger à nouveau la base de données d’emplacements.
  
> [!NOTE]
> Les adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Pour configurer l’URL de l’application SNMP

1.  Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
2. Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)