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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: L’applet de commande Set-CcExternalCertificateFilePath spécifie le chemin d’accès dans lequel le certificat pour le serveur de médiation ou le serveur Edge est enregistré.
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286984"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
L’applet de commande Set-CcExternalCertificateFilePath spécifie le chemin d’accès dans lequel le certificat pour le serveur de médiation ou le serveur Edge est enregistré.
  
Ce certificat est requis pendant le déploiement ou lors de l’ajout de nouvelles appliances de la version Cloud Connector de Skype Entreprise. La commande permet également d’importer un nouveau certificat pour le serveur de médiation après le déploiement.
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L'exemple suivant configure le chemin d’accès du certificat pour le serveur Edge :
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant configure le chemin d’accès du certificat pour le serveur de médiation :
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Exemple 3

L'exemple suivant met à jour le certificat pour le serveur de médiation :
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Lors du déploiement ou de la modification de la typologie, vous devez spécifier le chemin d’accès pour le certificat du serveur Edge et éventuellement pour le certificat du serveur de médiation. 
  
Le certificat pour le serveur de médiation est requis si TLS est utilisé entre la ou les passerelle(s) et le serveur de médiation. Lorsque vous déployez un dispositif de connexion Cloud et que vous souhaitez déployer le protocole TLS, vous ne pouvez spécifier que le chemin d’accès au certificat qui sera déployé sur le serveur de médiation. Cependant, si vous souhaitez mettre à jour le certificat de médiation sur une appliance déjà déployée, vous devez spécifier le chemin d’accès et le paramètre Importation. Pour voir le chemin d’accès, utilisez l’applet de commande Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
| Cible <br/> | Obligatoire <br/> |System.String  <br/> |Type de chemin d’accès de fichier requis. Les types comprennent :  <br/> Le serveur Edge (défaut)  <br/> Le serveur de médiation  <br/> |
|Importation  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indique que le certificat doit être importé vers le serveur de médiation. Ce paramètre n'est pas requis si vous déployez une appliance pour la première fois. Le paramètre est requis si vous souhaitez changer le certificat existant sur une version déjà déployée.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

L’applet de commande Set-CcExternalCertificateFilePath n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

