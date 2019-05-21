---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: L’applet de connexion Start-CcDownload télécharge les fichiers bits et le fichier MSI de Skype entreprise version Cloud Connector.
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286942"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
L’applet de connexion Start-CcDownload télécharge les fichiers bits et le fichier MSI de Skype entreprise version Cloud Connector.
  
Avec le Cloud Connector version 2,0 et les versions ultérieures, vous pouvez également spécifier le paramètre DownloadBitsOnly.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple ci-après télécharge les bits et le fichier MSI du Cloud Connector à partir du site de téléchargement public Cloud Connector:
  
```
Start-CcDownload
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant télécharge les fichiers msi et de connexion Cloud à partir d’un site de téléchargement privé:
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Exemple 3

Le troisième exemple télécharge les fichiers msi et de connexion Cloud à partir d’un site de téléchargement privé.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Dans le cas où une nouvelle version est disponible sur le site de téléchargement, Start-CcDownload télécharge et installe le fichier MSI à partir du site de téléchargement, puis télécharge les bits du connecteur Cloud de manière synchrone. S’il n’y a pas de nouvelle version du fichier MSI, Start-CcDownload télécharge uniquement les bits du connecteur Cloud. Si les bits du connecteur Cloud ont déjà été téléchargés, Start-CcDownload ne s’exécute pas.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Facultatif  <br/> |System.String  <br/> | URL complète d’une version spécifique du Cloud Connector dans le site de téléchargement privé. Utilisez ce paramètre avec précaution; Vérifiez quelle version de Cloud Connector vous téléchargez. <br/> |
|DownloadBitsOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignorer l’étape permettant de télécharger et d’installer MSI à partir du site de téléchargement, téléchargez uniquement les bits du connecteur Cloud.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Start-CcDownload n’accepte pas les entrées pipelines.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

