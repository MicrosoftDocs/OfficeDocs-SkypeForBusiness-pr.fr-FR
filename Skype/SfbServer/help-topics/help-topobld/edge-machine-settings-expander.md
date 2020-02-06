---
title: Développeur des paramètres de l’ordinateur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Pour modifier les propriétés d’un serveur dans une liste de serveurs Edge, procédez comme suit :'
ms.openlocfilehash: 93d8169eaaa6c0ca69b9210addea37ac21a8c5b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820086"
---
# <a name="edge-machine-settings-expander"></a>Développeur des paramètres de l’ordinateur Edge
 
Pour modifier les propriétés d’un serveur dans une liste de serveurs Edge, procédez comme suit :
  
Vous pouvez modifier le **nom interne ou le nom** de domaine complet en modifiant le nom de domaine complet (FQDN). Le nom de domaine complet (FQDN) doit correspondre à l’enregistrement de l’hôte DNS (Domain Name System) et au nom du sujet du certificat attribué au serveur pour l’interface du réseau Edge interne. La valeur de l' **adresse IP interne** définit l’adresse IP qui est affectée à l’interface réseau qui est définie en tant que réseau interne, par rapport à la conception du réseau de périmètre.
  
Les trois sections suivantes de la boîte de dialogue définissent les adresses IP pour la configuration externe de ce serveur Edge. La possibilité de modifier les adresses IP est affectée par le paramètre **autorisez un nom de domaine complet et une adresse IP distincts pour les conférences Web et A/V** sur les paramètres de propriétés au niveau du pool de serveur Edge.
  
## <a name="sip-access"></a>Accès SIP

Modifiez l’adresse IP externe qui est affectée à l’interface réseau pour l’accès au protocole SIP (Session Initiation Protocol). Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.
  
> [!NOTE]
> Si le paramètre **activer le nom de domaine complet et l’adresse IP séparés pour les conférences Web et a/V** sur la page Paramètres du pool est activé, seule l’adresse IP de l’accès SIP sera disponible pour modification.
  
## <a name="web-conferencing"></a>Conférence web

Modifiez l’adresse IP externe qui est affectée à l’interface réseau pour les conférences Web. Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.
  
## <a name="audiovideo"></a>Audio/vidéo

Modifiez l’adresse IP externe qui est affectée à l’interface réseau pour les appels audio/vidéo (A/V). Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.
  
Le paramètre de l' **adresse IP publique activée pour tar** est l’adresse publique utilisée par l’interface externe pour l’interface réseau A/V ou le serveur Edge en général. Si le paramètre **activer le nom de domaine complet et l’adresse IP séparés pour les conférences Web et si a/V** est activé, cette adresse IP publique est utilisée pour les trois interfaces externes.
  

