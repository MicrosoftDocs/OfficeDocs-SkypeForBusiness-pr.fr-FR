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
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: La cmdlet Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde du service d’autorité de certification dans le dossier CA sous l’annuaire de partage de sites pour Skype Entreprise, version Cloud Connector.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824290"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
L'Remove-CcCertificationAuthorityFile cmdlet supprime le fichier de sauvegarde du service d’autorité de certification « &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12 » dans le dossier CA sous l’annuaire de partage de sites pour Skype Entreprise, version Cloud Connector. 
  
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
  

