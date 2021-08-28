---
title: Expanseur des paramètres de l’ordinateur Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: "Pour modifier les propriétés d'un serveur dans un pool de serveurs Edge, procédez comme suit :"
ms.openlocfilehash: 88437d5a39dd913844dd47798e60d5eb935c1a76
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604923"
---
# <a name="edge-machine-settings-expander"></a>Expandeur des paramètres de l’ordinateur Edge
 
Pour modifier les propriétés d'un serveur dans un pool de serveurs Edge, procédez comme suit :
  
Le **nom interne ou nom de domaine complet** peut être changé en modifiant le nom de domaine complet (FQDN). Le nom de domaine complet doit correspondre à l’enregistrement DNS A (hôte), et au nom du sujet du certificat assigné au serveur pour l’interface réseau Edge interne. La valeur de l’**Adresse IP interne** définit l’adresse IP assignée à l’interface réseau définie comme réseau interne, en fonction de la conception du réseau de périmètre.
  
Les trois sections suivantes de la boîte de dialogue définissent les adresses IP pour la configuration externe de ce serveur Edge. La possibilité de modifier les adresses IP est influencée par le paramètre **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo** dans les paramètres Propriétés au niveau du pool de serveurs Edge.
  
## <a name="sip-access"></a>Accès SIP

Modifier l'adresse IP externe assignée à l'interface réseau pour l'accès SIP (Session Initiation Protocol). Cette adresse IP peut être soit une adresse IP publique, soit une adresse dans la plage d'adresses IP privées.
  
> [!NOTE]
> Si le paramètre **Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V** est activé sur la page des paramètres du pool, seule l'adresse IP pour l'accès SIP est modifiable.
  
## <a name="web-conferencing"></a>Conférence web

Modifiez l’adresse IP externe assignée à l’interface réseau pour la conférence web. Cette adresse IP peut être soit une adresse IP publique, soit une adresse dans la plage d’adresses IP privées.
  
## <a name="audiovideo"></a>Audio/Vidéo

Modifiez l’adresse IP externe assignée à l’interface réseau pour l’audio/vidéo (A/V). Cette adresse IP peut être soit une adresse IP publique, soit une adresse dans la plage d’adresses IP privées.
  
Le paramètre **Adresse IP publique compatible avec NAT utilisée** est l’adresse publique utilisée par l’interface externe soit pour l’interface réseau A/V, soit pour le serveur Edge en général. Si le paramètre **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo** est activé, cette adresse IP publique est utilisée pour ces trois interfaces externes.
  

