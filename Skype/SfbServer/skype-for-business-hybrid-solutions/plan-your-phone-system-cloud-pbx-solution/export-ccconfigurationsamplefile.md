---
title: Exportation-CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a>Exportation-CcConfigurationSampleFile
 
L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant télécharge un exemple de fichier de configuration à partir du site de Microsoft et l’écrit dans le répertoire de la solution matérielle-logicielle de la solution matérielle-logicielle connecteur de nuage :
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La version actuelle de connecteur de Cloud vous demande de fournir plusieurs paramètres dans le fichier .ini. par exemple, des paramètres, tels que les adresses IP des ordinateurs virtuels pour les composants du connecteur du nuage, noms de composants, paramètres de la passerelle et ainsi de suite.
  
Cette applet de commande, lorsqu’il est exécuté sur l’ordinateur hôte du connecteur du nuage, télécharge un exemple de fichier .ini avec des exemples de configuration à partir du site Microsoft. L’applet de commande écrit le fichier dans le répertoire de la solution matérielle-logicielle de la solution matérielle-logicielle connecteur de nuage. L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Export-CcConfigurationSampleFile n’accepte pas l’entrée redirigée. 
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Ensemble-CcApplianceDirectory](set-ccappliancedirectory.md)
  

