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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: La cmdlet Start-CcDownload télécharge les bits et le fichier msi de la version Cloud Connector de Skype Entreprise de manière synchrone.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824178"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
La cmdlet Start-CcDownload télécharge les bits et le fichier msi de la version Cloud Connector de Skype Entreprise de manière synchrone.
  
Avec Cloud Connector version 2.0 et versions ultérieures, vous pouvez également spécifier le paramètre DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant télécharge les bits et le fichier msi Cloud Connector de manière synchrone à partir du site de téléchargement public Cloud Connector :
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant télécharge les bits et le fichier msi Cloud Connector de manière synchrone à partir d’un site de téléchargement privé :
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Exemple 3

Le troisième exemple télécharge les bits et le fichier msi Cloud Connector de manière synchrone à partir d’un site de téléchargement privé.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

S’il existe une nouvelle version disponible sur le site de téléchargement, Start-CcDownload télécharge et installe le fichier msi à partir du site de téléchargement, puis télécharge les bits Cloud Connector de manière synchrone. S’il n’existe aucune nouvelle version du fichier msi, Start-CcDownload téléchargera uniquement les bits Cloud Connector. Si les bits Cloud Connector sont déjà téléchargés, Start-CcDownload ne s’exécute pas.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Facultatif <br/> |System.String  <br/> | URL complète d’une version spécifique de Cloud Connector dans le site de téléchargement privé. Utilisez ce paramètre avec précaution, assurez-vous de connaître la version de Cloud Connector que vous téléchargez. <br/> |
|DownloadBitsOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignorez l’étape de téléchargement et d’installation de MSI à partir du site de téléchargement, téléchargez uniquement les bits Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Start-CcDownload n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

