---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: L’applet de commande Register-CcAppliance enregistre les informations de l’appliance vers un site RTC dans une configuration client en ligne. Une appliance doit être enregistrée avant d’être déployée et gérée par le service de gestion de Skype Entreprise, version Cloud Connector.
ms.openlocfilehash: e753f92c84b880da6aac060b65726bda5f9ba1ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892272"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
L’applet de commande Register-CcAppliance enregistre les informations de l’appliance vers un site RTC dans une configuration client en ligne. Une appliance doit être enregistrée avant d’être déployée et gérée par le service de gestion de Skype Entreprise, version Cloud Connector.
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant enregistre les informations de l’appliance actuelle dans une configuration de client en ligne :
  
```
Register-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant vérifie la configuration d’enregistrement local sans connexion à une configuration de client en ligne :
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant enregistre l’appliance actuelle sous le nom « Appliance1 » sur le site RTC « Site1 » :
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Vous devez fournir le mot de passe et le nom du compte d'administrateur du client. Utiliser le compte que vous avez créé pour la gestion en nuage connecteur en ligne. 
  
Dans la version 1.4.2 et version antérieure, suivez les instructions pour fournir le mot de passe de certificat externe, le mot de passe d’administration en mode sans échec, mot de passe d’administration de domaine et le mot de passe d’administration ordinateur virtuel. 
  
Dans la version 2.0 et versions ultérieures, suivez les instructions pour fournir le mot de passe de certificat externe, CceService mot de passe et le mot de passe CABackupFile.
  
À la fin de l’inscription, redémarrez le service de gestion en nuage connecteur et ouvrez une session sur les services en tant que compte CceService.
  
Le nom du site combiné au nom de domaine complet (FQDN) externe du serveur Edge dans le fichier CloudConnector.ini est considéré comme une identité du site RTC. Si ni le nom du site ni le FQDN externe du serveur Edge n’ont été utilisés pour inscrire un site, un nouveau site est créé pour cette appliance dans une configuration de client en ligne. Si une identité de site RTC est trouvée, un site RTC utilise cette identité et l’appliance est enregistrée sur ce site RTC.  
  
Dans la situation suivante, l’applet de commande échoue et indique que le Site1 est déjà inscrit :  
  
- Le nom du site est Site1 et le nom de domaine complet (FQDN) externe du serveur Edge est edgserver1.contoso.com.  
    
- Un site RTC dont le nom est Site1 et le nom de domaine complet (FQDN) externe du serveur Edge est edgserver.contoso.com.
    
- Un site RTC dont le nom est NewSite et le nom de domaine complet (FQDN) externe du serveur Edge est edgserver1.contoso.com a été inscrit.  
    
Le nom de l'appliance combiné au nom de domaine complet (FQDN) du serveur de médiation dans le fichier CloudConnector.ini est considéré comme une identité de l’appliance. Si ni le nom de l'appliance ni le nom de domaine complet (FQDN) du serveur de médiation n’ont été utilisés pour inscrire une appliance, une nouvelle appliance est créée dans la configuration de client en ligne. Si l’appliance est déjà inscrite, l’applet de commande échoue.
  
Dans la situation suivante, l’applet de commande échoue et indique que l’appliance est déjà inscrite :  
  
- Le nom de l'appliance est Appliance1 et le nom de domaine complet (FQDN) du serveur de médiation est ms1.vdomain.com.
    
- Dans le site RTC actuel, si une appliance dont le nom est Appliance1 et le nom de domaine complet (FQDN) du serveur de médiation est ms.vdomain.com ou une appliance dont le nom est NewAppliance et le FQDN du serveur de médiation est ms1.vdomain.com a été inscrit.
    
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Facultatif   <br/> |System.String  <br/> |Nom du site RTC sur lequel l’appliance est inscrite. La valeur par défaut est la valeur SiteName dans le fichier CloudConnector.ini.   <br/> |
|ApplianceName  <br/> |Facultatif   <br/> |System.String  <br/> |Nom de l’appliance actuelle. La valeur par défaut est le nom de l’ordinateur du serveur hôte.  <br/> |
|Local  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Vérification des configurations d’inscription locale sans connexion à la configuration du client en ligne.  <br/> |
   
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Register-CcAppliance n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

