---
title: Configurer une application SNMP dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurer une application SNMP pour fonctionner avec E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 528caaa4db89630cc1818eb8f4a470146093d883
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890716"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurer une application SNMP dans Skype pour Business Server
 
Configurer une application SNMP pour fonctionner avec E9-1-1 dans Skype pour Business Server Enterprise Voice. 
  
Skype pour Business Server inclut une interface de service web standard que vous pouvez utiliser pour se connecter le service informations d’emplacement aux applications SNMP Simple Network Management Protocol () qui correspondent à des adresses MAC aux ports et commutateurs. 
  
Si une application SNMP est installée et le service informations d’emplacement ne parvient pas à trouver une correspondance dans la base de données d’emplacement, le service informations d’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client. Le service informations d’emplacement utilise ensuite les informations de port et de commutateur renvoyées par l’application SNMP pour interroger la base de données d’emplacement à nouveau.
  
> [!NOTE]
> Adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Pour configurer l’URL de l’application SNMP

1.  Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Voir aussi

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

