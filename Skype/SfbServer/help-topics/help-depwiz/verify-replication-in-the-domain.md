---
title: Vérifier la réplication dans le domaine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Pour vérifier la réplication de la préparation du domaine accomplie à l’étape 1 : préparer le schéma, il est nécessaire d’exécuter une cmdlet à partir de Skype entreprise Server Management Shell Lync Server Management Shell. Pour exécuter l’applet de cmdlet Windows PowerShell, connectez-vous à un ordinateur membre du domaine que vous avez préparé et en tant que membre du groupe administrateurs de domaine. Procédez comme suit :'
ms.openlocfilehash: add0434223dcd4f08256adbdcc207ee6be4df1b8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687367"
---
# <a name="verify-replication-in-the-domain"></a>Vérifier la réplication dans le domaine
 
Pour vérifier la réplication de la préparation du domaine accomplie à l' **étape 1 : préparer le schéma**, il est nécessaire d’exécuter une cmdlet à partir de Skype entreprise Server Management Shell Lync Server Management Shell. Pour exécuter l’applet de cmdlet Windows PowerShell, connectez-vous à un ordinateur membre du domaine que vous avez préparé et en tant que membre du groupe administrateurs de domaine. Procédez comme suit :
  
1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Dans Windows PowerShell, tapez les informations suivantes :
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Exemple :
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (qui est généralement utilisé avec des déploiements de mise à niveau pour lesquels le paramètre global n’a pas été migré vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt de services de domaine Active Directory (AD DS). Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans Active Directory. 
  
    Si vous omettez le paramètre Domain, le domaine local est utilisé. Cette applet de commande renvoie la valeur **LC_DOMAIN_SETTINGS_STATE_READY**, si la préparation du domaine a réussi.
    

