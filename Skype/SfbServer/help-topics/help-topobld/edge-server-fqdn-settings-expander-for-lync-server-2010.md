---
title: Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés sous Paramètres externes, configurez les paramètres suivants :'
ms.openlocfilehash: 763fed345ec3d53496be216dbd94e26825c2766b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828917"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
 
Pour définir les propriétés sous **Paramètres externes,** configurez les paramètres suivants :
  
Activez la case à cocher Activer un **FQDN** et une adresse IP distincts pour la conférence web et activez la case à cocher A/V si vous souhaitez définir des adresses IP et un FQDN de pool distincts pour la conférence web et l’audio/vidéo.
  
> [!NOTE]
> Si vous choisissez de ne pas cocher la case pour des adresses IP et des noms de noms distincts, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge. Le seul nom de domaine complet à configurer est le nom de domaine complet associé au service Edge d’accès. 
  
Activez la case à cocher nat pour le **service Edge A/V** si vous souhaitez que le service Edge A/V utilise une adresse IP de traduction d’adresses réseau (NAT) et une configuration.
  
Pour les services Edge activés, tapez un **FQDN** de pool et un port sous **Ports**
  
- Définissez le FQDN du pool de **services Edge** d’accès et un port qui identifie le service de manière unique.
    
- Définissez le FQDN du pool de **services Edge** de conférence web (si vous activez un FQDN et une adresse IP distincts pour la conférence web et qu’A/V n’est pas sélectionné) et un port qui identifie le service de manière unique.
    
- Définissez le FQDN du pool de **services Edge A/V** (si vous activez un FQDN et une adresse IP distincts pour la conférence web et qu’A/V n’est pas sélectionné) et un port qui identifie le service de manière unique.
    
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

