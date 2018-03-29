---
title: Démarrer-CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: L’applet de commande Start-CcDownload télécharge le Skype pour connecteur de nuage Professionnel & fichier msi de façon synchrone.
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a>Démarrer-CcDownload
 
L’applet de commande Start-CcDownload télécharge le Skype pour connecteur de nuage Professionnel & fichier msi de façon synchrone.
  
Avec connecteur de nuage version 2.0 et ultérieure, vous pouvez également spécifier le paramètre DownloadBitsOnly.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant télécharge les bits du connecteur du nuage et le fichier msi de façon synchrone à partir du site de téléchargement public Cloud connecteur :
  
```
Start-CcDownload
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant télécharge les bits du connecteur du nuage et le fichier msi de façon synchrone à partir d’un site de téléchargement privée :
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Exemple 3

Le troisième exemple télécharge les bits du connecteur du nuage et le fichier msi de façon synchrone à partir d’un site de téléchargement privée.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Si une nouvelle version est disponible sur le site de téléchargement, début-CcDownload télécharger et installer le fichier msi à partir du site de téléchargement et puis télécharger les bits de connecteur de nuage de façon synchrone. S’il n’existe aucune nouvelle version du fichier msi, début-CcDownload télécharge uniquement les bits du connecteur de nuage. Si les bits du connecteur du nuage sont déjà téléchargés, début-CcDownload ne s’exécute pas.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Facultatif <br/> |System.String  <br/> | Site de téléchargement de l’URL complète d’une version spécifique du connecteur du Cloud dans le privé. Utilisez ce paramètre avec prudence — Vérifiez que vous êtes conscient de la version du connecteur de Cloud vous téléchargez. <br/> |
|DownloadBitsOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignorez l’étape pour télécharger et installer le MSI à partir du site de téléchargement, télécharger uniquement les bits du connecteur de nuage.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Start-CcDownload n’accepte pas les entrées de pipeline.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

