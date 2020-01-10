---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: L’applet de commande Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector. L’utilisateur prépare ce certificat.
ms.openlocfilehash: 7a471b0e4258728bfaa50558aab54955346b457c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003374"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
L’applet de commande Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Skype Entreprise, version Cloud Connector. L’utilisateur prépare ce certificat.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le chemin d’accès du certificat pour le serveur Edge :
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant montre le certificat pour le serveur de médiation :
  
```powershell
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
  

