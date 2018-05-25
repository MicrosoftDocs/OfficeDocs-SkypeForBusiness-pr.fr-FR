---
title: Expanseur des paramètres l’ordinateur Edge
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Pour modifier les propriétés d’un serveur dans un pool de serveurs de périphérie, procédez comme suit :'
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="edge-machine-settings-expander"></a>Expanseur des paramètres l’ordinateur Edge
 
Pour modifier les propriétés d’un serveur dans un pool de serveurs de périphérie, procédez comme suit :
  
**nom interne ou nom de domaine complet** peut être modifié en modifiant le nom de domaine complet (FQDN). Le nom de domaine complet doit correspondre à l’hôte (A) enregistrement de nom de domaine DNS (Domain Name System) et le nom du sujet du certificat à assigner au serveur pour l’interface réseau de périphérie interne. La valeur de **l’adresse IP interne** définit l’adresse IP qui est affectée à l’interface réseau qui est défini comme un réseau interne, par rapport à la conception de réseau de périmètre.
  
Les trois sections de la boîte de dialogue définissent les adresses IP pour la configuration de ce serveur Edge externe. La possibilité de modifier les adresses IP est affectée par le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** sur les paramètres des propriétés au niveau du serveur Edge au niveau du pool.
  
## <a name="sip-access"></a>Accès SIP

Modifier l’adresse IP externe qui est affectée à l’interface réseau pour l’accès protocole SIP (Session Initiation). Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privée.
  
> [!NOTE]
> Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** sur le pool page Paramètres n’est activée, que l’adresse IP pour l’accès SIP sera disponible pour la modification.
  
## <a name="web-conferencing"></a>Conférence web

Modifier l’adresse IP externe qui est affectée à l’interface réseau pour les conférences web. Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privée.
  
## <a name="audiovideo"></a>Audio/vidéo

Modifier l’adresse IP externe qui est affectée à l’interface réseau pour l’audio/vidéo (A / V). Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privée.
  
Le paramètre de **NAT activé l’adresse IP publique** est l’adresse publique utilisée par l’interface externe soit a / V réseau interface ou le serveur de périphérie en général. Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** est activé, cette adresse IP publique est utilisée pour les trois interfaces externes.
  

