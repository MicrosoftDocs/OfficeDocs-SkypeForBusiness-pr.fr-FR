---
title: Set-CcExternalCertificateFilePath
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
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: LSet-CcExternalCertificateFilePath cmdlet spécifie le chemin d’accès où le certificat pour le serveur de médiation ou le serveur Edge est stocké.
ms.openlocfilehash: b8555d3a3c6770481e1a66f79fd4a1060d3d9936
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615520"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
LSet-CcExternalCertificateFilePath cmdlet spécifie le chemin d’accès où le certificat pour le serveur de médiation ou le serveur Edge est stocké.
  
Ce certificat est requis lors du déploiement ou lors de l’ajout de nouvelles appliances Skype Entreprise Cloud Connector Edition. La commande permet également d’importer un nouveau certificat pour le serveur de médiation après le déploiement.
  
Cette cmdlet s’applique Skype Entreprise Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant définit le chemin d’accès du certificat pour le serveur Edge :
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant définit le chemin d’accès du certificat pour le serveur de médiation :
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant met à jour le certificat pour le serveur de médiation :
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Pendant le déploiement ou lors de la modification de la topologie, vous devez spécifier le chemin d’accès pour le certificat de serveur Edge et éventuellement pour le certificat de serveur de médiation. 
  
Le certificat pour le serveur de médiation est requis si TLS doit être utilisé entre la ou les passerelles et le serveur de médiation. Lorsque vous déployez une appliance Cloud Connector et que vous souhaitez déployer TLS, vous ne pouvez spécifier que le chemin d’accès au certificat qui sera déployé sur le serveur de médiation. Toutefois, si vous souhaitez mettre à jour le certificat de médiation sur une appliance déjà déployée, vous devez spécifier le chemin d’accès et le paramètre -Import. Pour voir le chemin d’accès, utilisez Get-CCExternalCertificateFilePath cmdlet.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Cible <br/> | Requis <br/> |System.String  <br/> |Type de chemin d’accès au fichier demandé. Les types sont les suivants :  <br/> EdgeServer (par défaut)  <br/> MediationServer  <br/> |
|Importation  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indique que le certificat doit être importé sur le serveur de médiation. Ce paramètre n’est pas nécessaire si vous déployez une appliance pour la première fois. Le paramètre est obligatoire si vous souhaitez modifier le certificat existant sur une version déjà déployée.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

La cmdlet Set-CcExternalCertificateFilePath n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

