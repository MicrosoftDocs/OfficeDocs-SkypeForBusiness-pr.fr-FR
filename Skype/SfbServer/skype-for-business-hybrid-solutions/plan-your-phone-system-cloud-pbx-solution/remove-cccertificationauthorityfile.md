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
description: L’applet de connexion Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde de l’autorité de certification dans le dossier autorité de certification sous le répertoire de partage du site pour Skype entreprise version Cloud Connector.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824290"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
L’applet de connexion Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde du&lt;service&gt;de l’autorité de certification « SiteRootDirectory \CA\SfB CCE. p12 » dans le dossier ca sous le répertoire de partage de site pour Skype entreprise version Cloud Connector. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

Dans l’exemple suivant, le fichier de sauvegarde du service&lt;de&gt;l’autorité de certification « SiteRootDirectory \CA\SfB CCE. P12 » est supprimé dans le dossier ca sous le répertoire de partage du site :
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Remove-CcCertificationAuthorityFile n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

