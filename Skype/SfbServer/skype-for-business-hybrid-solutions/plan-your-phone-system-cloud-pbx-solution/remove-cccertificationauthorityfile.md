---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: LRemove-CcCertificationAuthorityFile cmdlet supprime le fichier de sauvegarde du service d’autorité de certification dans le dossier de l’autorité de certification sous l’annuaire de partage de sites pour Skype Entreprise Cloud Connector Edition.
ms.openlocfilehash: 93141fee2ab2bf5af4ac826f4926523bd26e9e45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624986"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
L'Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde du service d’autorité de certification « &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12 » dans le dossier CA situé sous l’annuaire de partage de sites pour Skype Entreprise Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant supprime le fichier de sauvegarde du service d’autorité de certification « &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12 » dans le dossier CA sous l’annuaire de partage de sites :
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Remove-CcCertificationAuthorityFile n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

