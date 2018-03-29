---
title: Contour Machine paramètres Expander
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
description: 'Pour modifier les propriétés d’un serveur dans un pool de serveurs Edge, effectuez les opérations suivantes :'
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a>Contour Machine paramètres Expander
 
Pour modifier les propriétés d’un serveur dans un pool de serveurs Edge, effectuez les opérations suivantes :
  
**nom interne ou le nom de domaine complet** peut être modifié en modifiant le nom de domaine pleinement qualifié (FQDN). Le nom de domaine complet doit correspondre à l’hôte (A) enregistrement de Domain Name System (DNS) et le nom du sujet du certificat affecté au serveur de l’interface réseau de bord interne. La valeur de **l’adresse IP interne** définit l’adresse IP qui est assignée à l’interface réseau qui est défini comme un réseau interne, par rapport à la conception du réseau de périmètre.
  
Les trois sections de la boîte de dialogue définissent les adresses IP pour la configuration externe de ce serveur de transport Edge. La possibilité de modifier les adresses IP est affectée par le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** au niveau du pool sur les paramètres des propriétés au niveau du serveur Edge.
  
## <a name="sip-access"></a>Accès SIP

Modifier l’adresse IP externe qui est affectée à l’interface réseau pour l’accès de Session Initiation Protocol (SIP). Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.
  
> [!NOTE]
> Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** sur le pool de page Paramètres est activé, seuls l’adresse IP pour un accès SIP sont disponible pour l’édition.
  
## <a name="web-conferencing"></a>Conférence web

Modifier l’adresse IP externe qui est affectée à l’interface réseau pour la conférence web. Cette adresse IP peut être soit une adresse IP publique ou une adresse dans la plage d’adresses IP privées.
  
## <a name="audiovideo"></a>Audio/vidéo

Modifier l’adresse IP externe est affectée à l’interface réseau pour audio/vidéo (A / V). Cette adresse IP peut être soit une adresse IP publique ou une adresse dans la plage d’adresses IP privées.
  
Le paramètre de **NAT activé adresse IP publique** est l’adresse publique utilisée par l’interface externe de l’A / V réseau interface ou le serveur de transport Edge en général. Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** est activée, cette adresse IP publique est utilisée pour toutes les interfaces externes trois.
  

