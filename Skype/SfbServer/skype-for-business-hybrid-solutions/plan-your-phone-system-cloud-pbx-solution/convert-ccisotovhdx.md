---
title: Convert-CcIsoToVhdx
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 9bf27e7161a3d5c74cc972df12246c36226be8cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Paramètres

|**Paramètre**|**Obligatoire**|**Type de**|**Description**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obligatoire <br/> |System.String  <br/> | Le chemin d’accès vers le fichier ISO de Windows Server 2012 R2.  <br/> |
|GeneralizeOnly  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Si le processus de conversion échoue pendant la mise à jour de Windows, vous pouvez essayer de configurer un réseau/proxy et mettre à jour Manuellement Windows. Après avoir effectué le travail manuel, vous pouvez exécuter cette applet de commande avec le paramètre GeneralizeOnly qui terminera les tâches à accomplir.   <br/> |
|PauseBeforeUpdate  <br/> |Facultatif  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pour mettre à jour Windows, certaines configurations manuelles réseau/proxy configuration peuvent être nécessaires sur les machines virtuelles de base. Le processus de conversion va être suspendu avant la mise à jour de Windows si ce paramètre est fourni. Après avoir effectué la configuration manuelle, vous pouvez reprendre le processus.   <br/> |
   
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant prépare le fichier VHDX de base en utilisant un fichier ISO de Windows Server 2012 R2 situé dans "C:\Windows_Server_2012_R2-EN-US-x64.ISO":  
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Exemple 2

En cas de défaillance de l’applet de commande Convert-CcIsoToVhdx au cours de la mise à jour de Windows, il est probablement dû à la configuration du réseau/proxy incorrect. Vous pouvez suivre les instructions dans le message d'erreur et vous connecter à la machine virtuelle de base pour corriger le problème et mettre à jour manuellement Windows. Après avoir effectué les tâches manuelles, exécutez à nouveau l’applet de commande à l’aide du paramètre GeneralizeOnly afin de terminer les tâches à accomplir : 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Exemple 3

Si la configuration manuelle est nécessaire pour mettre à jour Windows, vous pouvez utiliser le paramètre -PauseBeforeUpdate. Avec ce paramètre, le connecteur de nuage s’interrompt avant le processus de mise à jour de Windows. Vous pouvez ensuite terminer la configuration manuelle et achever le processus de conversion de la manière suivante :
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de commande Convert-CcIsoToVhdx crée une base de que machine virtuelle installe tout d’abord, certains composants de base que connecteur de nuage dépend et puis installe les mises à jour Windows. Enfin, il généralise l’ordinateur virtuel (sysprep) pour obtenir un fichier VHDX de base qui sera utilisé par les ordinateurs virtuels d’un appareil de connecteur de nuage. 
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Convert-CcIsoToVhdx n’accepte pas l’entrée redirigée. 
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

Aucun
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

Aucun
  

