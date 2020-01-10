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
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: "L'applet de commande Export-CcRootCertificate exporte le certificat de l'AC racine dans un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise. "
ms.openlocfilehash: 90eadb257d91a05c05fabbfe1db84b8160ad4a7c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003414"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
L'applet de commande Export-CcRootCertificate exporte le certificat de l'AC racine dans un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise.  
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L'exemple suivant définit le paramètre Path en tant que chemin de répertoire, non chemin de fichier. Il génère le fichier c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L'applet de commande Export-CcRootCertificate permet d'enregistrer les certificats racine et intermédiaires sur le chemin de fichier. Ceci peut être utile en cas de récupération d’urgence.  
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |Obligatoire  <br/> |System.String  <br/> |Chemin de fichier dans lequel le certificat est stocké.   <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L'applet de commande Export-CcRootCertificate n'accepte pas l'entrée redirigée.  
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

