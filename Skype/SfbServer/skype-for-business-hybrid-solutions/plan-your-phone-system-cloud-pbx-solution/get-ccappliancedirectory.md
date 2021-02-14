---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: La cmdlet Get-CcApplianceDirectory récupère l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont stockés dans ce répertoire.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800844"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
La cmdlet Get-CcApplianceDirectory récupère l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichiers de déploiement sont stockés dans ce répertoire. 
  
Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actuel dans lequel les fichiers de configuration et de machine virtuelle des composants Cloud Connector sont stockés :
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

LGet-CcApplianceDirectory cmdlet indique où tous les fichiers de configuration et de machine virtuelle, journaux et certificats externes sont stockés pour l’appliance Cloud Connector.
  
Chaque appliance Cloud Connector possède quatre composants : serveur de médiation, magasin central de gestion, serveur Edge et contrôleur de domaine. Le dossier par défaut est C:\Users \% userprofile%\CloudConnector\ApplianceRoot. Vous pouvez modifier ce dossier à l’aide Set-CCApplianceDirectory cmdlet.
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Get-CCApplianceDirectory n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

La commande renvoie un chemin d’accès au fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

