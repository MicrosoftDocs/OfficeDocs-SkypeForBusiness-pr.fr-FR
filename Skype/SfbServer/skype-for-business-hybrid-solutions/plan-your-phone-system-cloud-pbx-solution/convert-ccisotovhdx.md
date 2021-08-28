---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: LConvert-CcIsoToVhdx cmdlet crée un fichier de disque dur virtuel de base (VHDX) à l’aide d’un client fourni Windows Server 2012 fichier ISO R2. Le fichier VHDX sera utilisé lors du déploiement de Skype Entreprise Cloud Connector Edition.
ms.openlocfilehash: dcbe1b4939fd99d6200217925bc52b72f6868873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635068"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
LConvert-CcIsoToVhdx cmdlet crée un fichier de disque dur virtuel de base (VHDX) à l’aide d’un client fourni Windows Server 2012 fichier ISO R2. Le fichier VHDX sera utilisé lors du déploiement de Skype Entreprise Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Paramètres

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Requis <br/> |System.String  <br/> | Chemin d’accès Windows Server 2012 fichier ISO R2. <br/> |
|GeneralizeOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si le processus de conversion échoue pendant Windows mise à jour, vous pouvez essayer de configurer un réseau/proxy et de mettre à jour Windows manuellement. Une fois le travail manuel terminé, vous pouvez exécuter cette cmdlet avec le paramètre -GeneralizeOnly et terminera les travaux restants.  <br/> |
|PauseBeforeUpdate  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pour mettre à Windows jour, une configuration manuelle réseau/proxy sur la VM de base peut être nécessaire. Le processus de conversion est suspendu avant Windows mise à jour si ce paramètre est fourni. Une fois la configuration manuelle effectuée, vous pouvez reprendre le processus.  <br/> |
   
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant prépare le fichier VHDX de base à l’aide d’un fichier ISO Windows Server 2012 R2 situé à l’emplacement « C:\Windows_Server_2012_R2-EN-US-x64.ISO » : 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Exemple 2

Si la cmdlet Convert-CcIsoToVhdx échoue pendant Windows mise à jour, c’est probablement en raison d’une configuration réseau/proxy incorrecte. Vous pouvez suivre les instructions du message d’erreur et vous connecter à la machine virtuelle de base pour résoudre le problème et mettre à jour Windows manuellement. Une fois le travail manuel terminé, ré-exécutez l’cmdlet avec le paramètre -GeneralizeOnly pour terminer les travaux restants : 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Exemple 3

Si la configuration manuelle est nécessaire pour mettre Windows jour, vous pouvez utiliser le paramètre -PauseBeforeUpdate. Avec ce paramètre, Cloud Connector sera suspendu avant le Windows de mise à jour. Vous pouvez ensuite terminer la configuration manuelle et reprendre le processus de conversion comme suit :
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

LConvert-CcIsoToVhdx d’entreprise crée d’abord une VM de base, installe certains composants de base dont dépend Cloud Connector, puis installe Windows mises à jour. Enfin, il généralise la machine virtuelle (sysprep) pour obtenir un fichier VHDX de base qui sera utilisé par les machines virtuelles d’une appliance Cloud Connector. 
  
## <a name="input-types"></a>Types d’entrée
<a name="InputTypes"> </a>

Aucun. La cmdlet Convert-CcIsoToVhdx n’accepte pas la saisie de données pipeline. 
  
## <a name="return-types"></a>Types de retour
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

