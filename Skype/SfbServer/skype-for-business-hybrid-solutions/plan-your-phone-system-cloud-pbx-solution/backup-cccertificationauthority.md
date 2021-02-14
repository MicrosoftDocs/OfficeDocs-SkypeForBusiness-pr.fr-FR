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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: LBackup-CcCertificationAuthority cmdlet sauvegarde le service d’autorité de certification Skype Entreprise, version Cloud Connector, dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803804"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
LBackup-CcCertificationAuthority cmdlet sauvegarde le service d’autorité de certification Skype Entreprise, version Cloud Connector, dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant sauvegarde le service d’autorité de certification dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites :
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La sauvegarde de l’autorité de certification peut être utile si vous envisagez de redéployer une appliance Cloud Connector avec le même certificat en cas d’urgence, ou si vous souhaitez déplacer l’appliance vers un nouveau matériel. La commande enregistre la copie du service d’autorité de certification Cloud Connector du serveur AD vers « \< SiteRootDirectory \> \CA\SfB CCE Root.p12 ».
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Backup-CcCertificationAuthority n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

