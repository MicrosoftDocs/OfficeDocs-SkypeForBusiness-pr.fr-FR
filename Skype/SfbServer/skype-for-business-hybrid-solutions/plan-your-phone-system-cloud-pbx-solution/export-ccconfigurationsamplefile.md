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
description: La cmdlet Export-CcConfigurationSampleFile exporte un exemple de fichier de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’équipements d’une appliance Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801004"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
La cmdlet Export-CcConfigurationSampleFile exporte un exemple de fichier de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’équipements d’une appliance Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
  
Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
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

La version actuelle de Cloud Connector nécessite que vous fournissiez plusieurs paramètres dans le fichier .ini . par exemple, les paramètres tels que les adresses IP des machines virtuelles pour les composants Cloud Connector, les noms des composants, les paramètres de passerelle, etc.
  
Cette cmdlet, lorsqu’elle est exécuté sur l’ordinateur hôte de Cloud Connector, télécharge un exemple de fichier .ini avec des exemples de configuration à partir du site Microsoft. L’cmdlet écrit le fichier dans l’annuaire d’appliances de l’appliance Cloud Connector. Le répertoire de l’appliance est spécifié à l’aide Set-CcApplianceDirectory cmdlet.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Export-CcConfigurationSampleFile n’accepte pas la saisie de données pipeline. 
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

