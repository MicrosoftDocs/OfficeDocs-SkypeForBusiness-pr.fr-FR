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
description: L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801004"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant permet de télécharger un exemple de fichier de configuration à partir du site Microsoft et de l’écrire dans le répertoire de l’application du dispositif Cloud Connector :
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La version actuelle de Cloud Connector nécessite que vous fournissiez plusieurs paramètres dans le fichier. ini ; par exemple, des paramètres tels que les adresses IP d’ordinateurs virtuels pour les composants Cloud Connector, les noms de composants, les paramètres de passerelle, etc.
  
Lors de l’exécution de cette applet de connexion sur l’ordinateur hôte du Cloud Connector, télécharge un exemple de fichier. ini contenant des exemples de configuration du site Microsoft. L’applet de connexion écrit le fichier dans le répertoire de l’application Cloud Connector. L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Export-CcConfigurationSampleFile n’accepte pas l’entrée redirigée. 
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

