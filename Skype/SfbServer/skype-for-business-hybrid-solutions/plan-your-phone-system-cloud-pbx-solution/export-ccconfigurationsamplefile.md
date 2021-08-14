---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: La cmdlet Export-CcConfigurationSampleFile exporte un exemple Skype Entreprise Cloud Connector Edition fichier de configuration (.ini) vers l’annuaire d’appliances d’une appliance Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: f59e93cf241ca762dcb41cf23d617017a62581b453cb84cebc915b1703f5a019
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326260"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
La cmdlet Export-CcConfigurationSampleFile exporte un exemple Skype Entreprise Cloud Connector Edition fichier de configuration (.ini) vers l’annuaire d’appliances d’une appliance Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant télécharge un exemple de fichier de configuration à partir du site Microsoft et l’écrit dans l’annuaire d’appliances de l’appliance Cloud Connector :
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La version actuelle de Cloud Connector nécessite que vous fournissiez plusieurs paramètres dans le fichier .ini; par exemple, les paramètres tels que les adresses IP des machines virtuelles pour les composants Cloud Connector, les noms des composants, les paramètres de passerelle, etc.
  
Cette cmdlet, lorsqu’elle est exécuté sur l’ordinateur hôte de Cloud Connector, télécharge un exemple de fichier .ini avec des exemples de configuration à partir du site Microsoft. L’cmdlet écrit le fichier dans l’annuaire d’appliances de l’appliance Cloud Connector. Le répertoire de l’appliance est spécifié à l’aide Set-CcApplianceDirectory cmdlet.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Export-CcConfigurationSampleFile n’accepte pas la saisie de données pipeline. 
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Néant
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

