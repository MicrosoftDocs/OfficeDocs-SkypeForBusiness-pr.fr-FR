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
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: L’applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification Skype Entreprise Cloud Connector Edition dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous le répertoire de partage de sites.
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675456"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

L’applet de commande Backup-CcCertificationAuthority sauvegarde le service d’autorité de certification Skype Entreprise Cloud Connector Edition dans un fichier. L’applet de commande l’enregistre également dans le dossier de l’autorité de certification sous le répertoire de partage de sites.

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>Paramètres

Aucun

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant sauvegarde le service d’autorité de certification dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous le répertoire de partage de sites :

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

La sauvegarde de l’autorité de certification peut être utile si vous envisagez de redéployer une appliance Cloud Connector avec le même certificat. Par exemple :

- Récupération d’urgence.
- Déplacez l’appliance vers le nouveau matériel.

La commande enregistre la copie du service d’autorité de certification Cloud Connector à partir du serveur AD dans `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`.

## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. L’applet de commande Backup-CcCertificationAuthority n’accepte pas l’entrée pipelineée.

## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun

## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  