---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: La cmdlet Register-CcAppliance enregistre les informations d’appliance sur un site PSTN dans une configuration client en ligne. Une appliance doit être inscrite avant de pouvoir être déployée et gérée par le service de gestion Skype Entreprise Cloud Connector Edition de l’appareil.
ms.openlocfilehash: 159e74f91ca26cd0f8bdd214c9cd6ac45b5c1196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589958"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
La cmdlet Register-CcAppliance enregistre les informations d’appliance sur un site PSTN dans une configuration client en ligne. Une appliance doit être inscrite avant de pouvoir être déployée et gérée par le service de gestion Skype Entreprise Cloud Connector Edition de l’appareil.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant enregistre les informations actuelles de l’appliance dans une configuration client en ligne :
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Exemple 2

L’exemple suivant vérifie la configuration pour l’inscription locale sans se connecter à une configuration client en ligne :
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Exemple 3

L’exemple suivant inscrit l’appliance actuelle avec le nom « Appliance1 » sur le site PSTN « Site1 » :
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

Vous devez fournir le nom et le mot de passe du compte d’administrateur client. Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector. 
  
Dans la version 1.4.2 et antérieure, suivez les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur de la VM. 
  
Dans la version 2.0 et les ultérieures, suivez les instructions pour fournir le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.
  
À la fin de l’inscription, redémarrez le service de gestion Cloud Connector et connectez-vous aux services en tant que compte CceService.
  
SiteName combiné au nom de CloudConnector.ini externe du serveur Edge est considéré comme une identité de site PSTN. Si ni le nom de site, ni le FQDN externe du serveur Edge n’ont été utilisés pour inscrire un site, un nouveau site sera créé pour cette appliance dans une configuration de client en ligne. Si une identité de site PSTN est trouvée, un site PSTN utilisera cette identité et l’appliance sera inscrite sur ce site PSTN. 
  
Dans la situation suivante, la cmdlet échoue et indique que Site1 est déjà inscrit : 
  
- SiteName est Site1 et le FQDN externe du serveur Edge est edgserver1.contoso.com. 
    
- Un site PSTN dont le nom de site est Site1 et le nom de edgserver.contoso.com.
    
- Un site PSTN dont le nom de site est NewSite et le nom de edgserver1.contoso.com serveur Edge a été enregistré. 
    
ApplianceName combiné au nom de CloudConnector.ini serveur de médiation est considéré comme une identité appliance. Si ni le nom d’appliance, ni le nom de groupe du serveur de médiation n’ont été utilisés pour inscrire une appliance, une nouvelle appliance est créée dans la configuration du client en ligne. Si l’appliance est déjà inscrite, la cmdlet échoue.
  
Dans la situation suivante, l’cmdlet échoue et indique que l’appliance est déjà inscrite : 
  
- ApplianceName est Appliance1 et le nom de ms1.vdomain.com.
    
- Dans le site PSTN actuel, si une appliance dont le nom est Appliance1 et le nom de domaine complet du serveur de médiation est ms.vdomain.com ou si une appliance dont le nom est NewAppliance et le nom de domaine complet du serveur de médiation ms1.vdomain.com a été inscrite.
    
## <a name="parameters"></a>Paramètres
<a name="DetailedDescription"> </a>

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Facultatif  <br/> |System.String  <br/> |Nom du site PSTN sur lequel l’appliance est inscrite. La valeur par défaut est La valeur SiteName dans le CloudConnector.ini fichier.  <br/> |
|ApplianceName  <br/> |Facultatif  <br/> |System.String  <br/> |Nom de l’appliance actuelle. La valeur par défaut est le nom de l’ordinateur du serveur hôte.  <br/> |
|Local  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Vérifiez les configurations d’inscription localement sans vous connecter à la configuration du client en ligne.  <br/> |
   
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Register-CcAppliance n’accepte pas la saisie de données pipeline.
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Néant
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

