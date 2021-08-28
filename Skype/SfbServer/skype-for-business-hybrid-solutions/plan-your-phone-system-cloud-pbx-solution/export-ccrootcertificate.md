---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: La cmdlet Export-CcRootCertificate exporte le certificat d’ac racine vers un fichier local sur Skype Entreprise Cloud Connector Edition serveur hôte.
ms.openlocfilehash: e00041088af39bf6f11abd5309ff293bd37bf38f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624996"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
La cmdlet Export-CcRootCertificate exporte le certificat d’ac racine vers un fichier local sur Skype Entreprise Cloud Connector Edition serveur hôte. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le paramètre Path comme chemin d’accès du répertoire, et non comme chemin d’accès de fichier. Il génère le fichier c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

LExport-CcRootCertificate cmdlet vous permet d’enregistrer les certificats racine et intermédiaires dans un chemin d’accès de fichier. Cela peut être utile en cas de scénario de récupération d’urgence. 
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Requis  <br/> |System.String  <br/> |Chemin d’accès au fichier où le certificat sera stocké.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Export-CcRootCertificate n’accepte pas la saisie de données pipeline. 
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

