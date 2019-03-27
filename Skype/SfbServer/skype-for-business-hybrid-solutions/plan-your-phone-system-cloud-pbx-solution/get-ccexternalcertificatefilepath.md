---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: L’applet de commande Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector. L’utilisateur prépare ce certificat.
ms.openlocfilehash: 997b5d7a39decf11a19c307f4e7a7b439069441f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882585"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
L’applet de commande Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector. L’utilisateur prépare ce certificat.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le chemin d’accès du certificat pour le serveur Edge :
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant montre le certificat pour le serveur de médiation :
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pendant le déploiement ou la modification de la typologie, vous devez spécifier le chemin d’accès pour le certificat du serveur Edge et éventuellement pour le serveur de médiation. Le certificat pour le serveur de médiation est obligatoire si TLS est utilisé entre la passerelle et le serveur de médiation. Pour changer le chemin d’accès, utilisez l’applet de commande Set-CcExternalCertificateFilePath.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Cible  <br/> |Facultatif  <br/> | System.Management.Automation.SwitchParameter <br/> |Type de chemin d’accès de fichier requis. Les types comprennent :  <br/> Le serveur Edge (défaut)  <br/> Le serveur de médiation  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

L’applet de commande Get-CcExternalCertificateFilePath n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

La commande renvoie un chemin d’accès de fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

