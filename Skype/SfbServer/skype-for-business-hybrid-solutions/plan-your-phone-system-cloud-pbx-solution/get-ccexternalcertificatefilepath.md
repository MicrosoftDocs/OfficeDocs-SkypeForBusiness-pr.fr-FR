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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: La cmdlet Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier de certificat externe pour le Skype Entreprise Cloud Connector Edition déploiement. L’utilisateur prépare ce certificat.
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622036"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
La cmdlet Get-CcExternalCertificateFilePath renvoie le chemin d’accès du fichier de certificat externe pour le Skype Entreprise Cloud Connector Edition déploiement. L’utilisateur prépare ce certificat.
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le chemin d’accès du certificat pour le serveur Edge :
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant montre le jeu de certificats pour le serveur de médiation :
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pendant le déploiement ou lors de la modification de la topologie, vous devez spécifier le chemin d’accès du certificat du serveur Edge et, éventuellement, du serveur de médiation. Le certificat pour le serveur de médiation est requis si TLS est utilisé entre la ou les passerelles et le serveur de médiation. Pour modifier le chemin d’accès, utilisez Set-CcExternalCertificateFilePath cmdlet.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|Cible  <br/> |Facultatif  <br/> | System.Management.Automation.SwitchParameter <br/> |Type de chemin d’accès au fichier demandé. Les types sont les suivants :  <br/> EdgeServer (par défaut)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

La cmdlet Get-CcExternalCertificateFilePath n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

La commande renvoie un chemin d’accès au fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

