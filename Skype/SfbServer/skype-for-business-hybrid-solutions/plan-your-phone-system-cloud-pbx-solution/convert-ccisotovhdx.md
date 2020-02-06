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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802424"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Paramètres

|**Paramètre**|**Obligatoire**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obligatoire <br/> |System.String  <br/> | Le chemin d’accès vers le fichier ISO de Windows Server 2012 R2.  <br/> |
|GeneralizeOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si le processus de conversion échoue pendant la mise à jour de Windows, vous pouvez essayer de configurer un réseau/proxy et mettre à jour Manuellement Windows. Après avoir effectué le travail manuel, vous pouvez exécuter cette applet de commande avec le paramètre GeneralizeOnly qui terminera les tâches à accomplir.   <br/> |
|PauseBeforeUpdate  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pour mettre à jour Windows, certaines configurations manuelles réseau/proxy configuration peuvent être nécessaires sur les machines virtuelles de base. Le processus de conversion va être suspendu avant la mise à jour de Windows si ce paramètre est fourni. Après avoir effectué la configuration manuelle, vous pouvez reprendre le processus.   <br/> |
   
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant prépare le fichier VHDX de base en utilisant un fichier ISO de Windows Server 2012 R2 situé dans "C:\Windows_Server_2012_R2-EN-US-x64.ISO":  
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Exemple 2

Si l’applet de connexion Convert-CcIsoToVhdx échoue lors de la mise à jour de Windows, il est probable qu’il n’y a pas de configuration réseau/proxy incorrecte. Vous pouvez suivre les instructions dans le message d'erreur et vous connecter à la machine virtuelle de base pour corriger le problème et mettre à jour manuellement Windows. Après avoir effectué les tâches manuelles, exécutez à nouveau l’applet de commande à l’aide du paramètre GeneralizeOnly afin de terminer les tâches à accomplir : 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Exemple 3

Si la configuration manuelle est nécessaire pour mettre à jour Windows, vous pouvez utiliser le paramètre -PauseBeforeUpdate. Ce paramètre permet de suspendre le Cloud Connector avant le processus Windows Update. Vous pouvez ensuite terminer la configuration manuelle et achever le processus de conversion de la manière suivante :
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de connexion Convert-CcIsoToVhdx crée d’abord un VM de base, installe certains composants de base dont dépend le Cloud Connector, puis installe les mises à jour Windows. Enfin, il généralise l’ordinateur virtuel (Sysprep) pour obtenir un fichier VHDX de base qui sera utilisé par les machines virtuelles d’un appareil de connecteur Cloud. 
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Convert-CcIsoToVhdx n’accepte pas l’entrée redirigée. 
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucune
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

