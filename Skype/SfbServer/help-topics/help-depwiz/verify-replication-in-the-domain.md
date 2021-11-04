---
title: Vérifier la réplication dans le domaine
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Pour vérifier la réplication de la préparation du domaine réalisée à l’étape 1 : Préparer le schéma, il est nécessaire d’exécuter une cmdlet à partir de Skype Entreprise Server Management Shell Lync Server Management Shell. Pour exécuter la cmdlet Windows PowerShell, connectez-vous à un ordinateur membre du domaine que vous avez préparé et membre du groupe Administrateurs du domaine. Procédez comme suit :'
ms.openlocfilehash: 195fff7628f9c0cdd52efe7dada2fc94d4e16cfe
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772570"
---
# <a name="verify-replication-in-the-domain"></a>Vérifier la réplication dans le domaine
 
Pour vérifier la réplication de la préparation du domaine réalisée à l’étape **1**: Préparer le schéma, il est nécessaire d’exécuter une cmdlet à partir de Skype Entreprise Server Management Shell Lync Server Management Shell. Pour exécuter la cmdlet Windows PowerShell, connectez-vous à un ordinateur membre du domaine que vous avez préparé et membre du groupe Administrateurs du domaine. Procédez comme suit :
  
1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Dans Windows PowerShell, tapez ce qui suit :
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    Par exemple :
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (ce qui est typique des déploiements de mise à niveau pour lesquels le paramètre global n’a pas été migré vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt des services de domaine Active Directory. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous définissez tout contrôleur de domaine de la forêt. Si vous ne spécifiez pas ce paramètre, la cmdlet suppose que les paramètres sont stockés dans le conteneur de configuration et fait référence à n’importe quel contrôleur de domaine dans Active Directory. 
  
    Si vous omettez le paramètre Domain, le domaine local est utilisé. Cette cmdlet renvoie la valeur **LC_DOMAIN_SETTINGS_STATE_READY** si la préparation du domaine a réussi.
    

