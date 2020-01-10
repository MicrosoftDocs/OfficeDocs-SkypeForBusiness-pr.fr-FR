---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: L’applet de commande Switch-CcVersion déconnecte l’application en cours d’exécution et bascule vers une nouvelle appliance déployée ou Backup.
ms.openlocfilehash: 157d1b677cc6c63d7707c9e1633cd8b6e3ad5927
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003154"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
L’applet de commande Switch-CcVersion déconnecte l’application en cours d’exécution et bascule vers une nouvelle appliance déployée ou Backup. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant drainne les services de l’application en cours d’exécution, puis bascule vers une nouvelle application de déploiement ou de sauvegarde :
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant drainne les services de l’application en cours d’exécution et arrête les services de force en cas d’échec du drainage des services. La commande bascule alors vers une nouvelle appliance déployée ou de sauvegarde :
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de connexion Switch-CcVersion draine les services de connecteur Cloud sur le serveur de médiation et le serveur Edge. Tous les appels en cours seront exécutés, mais les nouveaux appels seront rejetés par l’appliance. Après le vidage, l’applet de connexion déconnecte l’application en cours d’exécution des réseaux d’entreprise et Internet, éteint toutes les machines virtuelles appartenant à l’application, puis connecte l’appareil de sauvegarde aux réseaux d’entreprise et Internet.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Facultatif <br/> |System.Management.Automation.SwitchParameter  <br/> | Arrête les services de force en cas d’échec du drainage des services. <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

