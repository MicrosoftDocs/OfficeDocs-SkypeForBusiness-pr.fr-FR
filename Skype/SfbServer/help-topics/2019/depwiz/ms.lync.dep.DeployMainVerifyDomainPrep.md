---
title: Vérifier la réplication dans le domaine
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Pour vérifier la réplication de la préparation du domaine effectuée dans l’étape 1 : préparation du schéma, il est nécessaire d’exécuter une applet de commande à partir de la Skype pour Business Server Management Shell Lync Server Management Shell. Pour exécuter l’applet de commande Windows PowerShell, ouvrez une session un ordinateur qui est un membre du domaine que vous avez préparé et en tant que membre du groupe Admins du domaine. Procédez comme suit :'
ms.openlocfilehash: 8577c3c1e40744154fba8ef886220daf441970b8
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974802"
---
# <a name="verify-replication-in-the-domain"></a>Vérifier la réplication dans le domaine
 
Pour vérifier la réplication de la préparation du domaine effectuée dans **étape 1 : préparer un schéma**, il est nécessaire d’exécuter une applet de commande à partir de la Skype pour Business Server Management Shell Lync Server Management Shell. Pour exécuter l’applet de commande Windows PowerShell, ouvrez une session un ordinateur qui est un membre du domaine que vous avez préparé et en tant que membre du groupe Admins du domaine. Procédez comme suit :
  
1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Dans Windows PowerShell, tapez ce qui suit :
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    Exemple :
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (qui est par défaut avec les déploiements de mise à niveau qui n’ont pas le paramètre global migré vers le conteneur de Configuration), vous définissez un contrôleur de domaine à la racine de votre forêt Active Directory Domain Services. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans Active Directory. 
  
    Si vous omettez le paramètre Domain, le domaine local est utilisé. Cette applet de commande renvoie la valeur **valeurlc_domain_settings_state_ready** si la préparation du domaine a réussi.
    

