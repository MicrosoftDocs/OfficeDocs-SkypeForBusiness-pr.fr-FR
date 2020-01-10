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
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: L’applet de connexion Remove-CcCertificationAuthorityFile supprime le fichier de sauvegarde de l’autorité de certification dans le dossier autorité de certification sous le répertoire de partage du site pour Skype entreprise version Cloud Connector.
ms.openlocfilehash: d7036633eaf092130fc6e4acaebda39d04ff17df
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003294"
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
  

