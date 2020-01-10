---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: L’applet de commande Get-CcApplianceLogDirectory affiche l’annuaire actuel regroupant les journaux de l’appliance de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003394"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
L’applet de commande Get-CcApplianceLogDirectory affiche l’annuaire actuel regroupant les journaux de l’appliance de la version Cloud Connector de Skype Entreprise.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actuel dans lequel sont stockés les journaux de l’appliance actuelle du connecteur Cloud :
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de connexion Get-CcApplianceLogDirectory affiche le répertoire actuel dans lequel se trouvent les journaux pour un appareil de connecteur Cloud. Le dossier par défaut est\%C:\Users UserProfile%\CloudConnector\ApplianceRoot\Logs. 
  
Vous pouvez modifier l’annuaire en utilisant l’applet de commande Set-CcApplianceDirectory.  
  
Remarque : Il n’existe aucune applet de commande qui change uniquement l’emplacement du dossier de journal sans modifier l’annuaire d’appliances.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Get-CcApplianceLogDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Cette commande renvoie un chemin d’accès.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

