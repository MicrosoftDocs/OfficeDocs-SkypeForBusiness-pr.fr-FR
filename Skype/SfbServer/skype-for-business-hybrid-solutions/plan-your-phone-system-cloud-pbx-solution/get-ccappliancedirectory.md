---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire. '
ms.openlocfilehash: bcd80018b2286865945638f66c13e4c5198346dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891482"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire.  
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actif où sont stockés les fichiers de configuration et machine virtuelle des composants de nuage connecteur :
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Get-CcApplianceDirectory indique où tous les fichiers de configuration et les ordinateurs virtuels, des journaux et les certificats externes sont stockées pour la solution de nuage connecteur.
  
Chaque appliance nuage connecteur comporte quatre composants : serveur de médiation, magasin Central de gestion, serveur de périphérie et un contrôleur de domaine. Le dossier par défaut est C:\Users\%userprofile%\CloudConnector\ApplianceRoot. Vous pouvez modifier ce dossier en utilisant l'applet de commande Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Get-CCApplianceDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

La commande renvoie un chemin d’accès de fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

