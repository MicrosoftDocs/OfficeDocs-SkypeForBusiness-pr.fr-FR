---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: L'applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification de la version Cloud Connector de Skype Entreprise sur un fichier et l'enregistre dans le dossier AC sous l’annuaire de sites.
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003024"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
L'applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification de la version Cloud Connector de Skype Entreprise sur un fichier et l'enregistre dans le dossier AC sous l’annuaire de sites.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant sauvegarde le service d’autorité de certification sur un fichier et l’enregistre dans un dossier AC sous l’annuaire de sites :
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La sauvegarde d’une autorité de certification peut être utile si vous envisagez de redéployer un appareil Cloud Connector avec le même certificat en cas de sinistre, ou si vous voulez déplacer l’appareil vers un nouveau matériel. La commande enregistre la copie du service de certification de certification Cloud du serveur AD pour «\<SITEROOTDIRECTORY\>\CA\SfB CCE root. P12 ».
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Backup-CcCertificationAuthority n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

