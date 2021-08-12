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
description: La cmdlet Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification Skype Entreprise Cloud Connector Edition dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites.
ms.openlocfilehash: abf94977abe2a0c3548b549ae0101ae399e124769eaaa9f05aabf203c69656a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282956"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
La cmdlet Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification Skype Entreprise Cloud Connector Edition dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites.
  
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

La sauvegarde de l’autorité de certification peut être utile si vous envisagez de redéployer une appliance Cloud Connector avec le même certificat en cas d’urgence, ou si vous souhaitez déplacer l’appliance vers un nouveau matériel. La commande enregistre la copie du service d’autorité de certification Cloud Connector du serveur AD vers « \<SiteRootDirectory\> \CA\SfB CCE Root.p12 ».
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Backup-CcCertificationAuthority n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Néant
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

