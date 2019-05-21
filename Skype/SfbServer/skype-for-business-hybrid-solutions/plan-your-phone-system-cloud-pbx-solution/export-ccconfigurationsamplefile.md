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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: 440253bc6b9c4e980a6f7ac4aae0c82ebad05660
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287378"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant permet de télécharger un exemple de fichier de configuration à partir du site Microsoft et de l’écrire dans le répertoire de l’application du dispositif Cloud Connector:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La version actuelle de Cloud Connector nécessite que vous fournissiez plusieurs paramètres dans le fichier. ini; par exemple, des paramètres tels que les adresses IP d’ordinateurs virtuels pour les composants Cloud Connector, les noms de composants, les paramètres de passerelle, etc.
  
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
  

