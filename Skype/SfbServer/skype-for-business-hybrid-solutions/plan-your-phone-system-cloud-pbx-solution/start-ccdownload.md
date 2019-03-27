---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: L’applet de commande Start-CcDownload télécharge le Skype pour bits Édition nuage connecteur et fichier msi de façon synchrone.
ms.openlocfilehash: cc157825df75a4534422cb0a2fd07abb0ae0daea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893837"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
L’applet de commande Start-CcDownload télécharge le Skype pour bits Édition nuage connecteur et fichier msi de façon synchrone.
  
Avec le nuage connecteur version 2.0 et versions ultérieure, vous pouvez également spécifier le paramètre DownloadBitsOnly.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant télécharge les bits nuage connecteur et le fichier msi de façon synchrone à partir du site de téléchargement public nuage connecteur :
  
```
Start-CcDownload
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant télécharge les bits nuage connecteur et le fichier msi de façon synchrone à partir d’un site de téléchargement privée :
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Exemple 3

Le troisième exemple télécharge les bits nuage connecteur et le fichier msi de façon synchrone à partir d’un site de téléchargement privée.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si une nouvelle version est disponible dans le site de téléchargement, Start-CcDownload télécharger et installer le fichier msi à partir du site de téléchargement et puis le télécharger sur le nuage connecteur de façon synchrone. S’il n’existe aucune nouvelle version du fichier msi, Start-CcDownload télécharge les fichiers binaires dans le nuage connecteur uniquement. Si les fichiers binaires dans le nuage connecteur sont déjà téléchargés, Start-CcDownload ne s’exécute pas.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Facultatif  <br/> |System.String  <br/> | Site de téléchargement de l’URL complète d’une version spécifique du nuage connecteur privées. Utilisez ce paramètre avec précaution, vérifiez que vous avez pris connaissance de la version du nuage connecteur télécharger. <br/> |
|DownloadBitsOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignorez l’étape pour télécharger et installer MSI à partir du site de téléchargement, télécharger uniquement les bits de nuage connecteur.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Start-CcDownload n’accepte pas la saisie de données redirigées.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

