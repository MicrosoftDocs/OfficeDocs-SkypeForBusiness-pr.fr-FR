---
title: Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés sous paramètres externes, configurez ce qui suit :'
ms.openlocfilehash: 95e55625ec698d8762832e812a79547daf4d2bcf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820056"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
 
Pour définir les propriétés sous **paramètres externes**, configurez ce qui suit :
  
Activez les cases à cocher **activer les nom de domaine complet et adresse IP pour les conférences Web et A/V** , si vous voulez définir un nom de domaine complet et des adresses IP distincts pour les conférences Web et les appels audio/vidéo.
  
> [!NOTE]
> Si vous choisissez de ne pas activer la case à cocher pour les adresses IP et FQDN distinctes, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge. Le seul nom de domaine complet à configurer est le FQDN associé au service Edge d’accès. 
  
Activez la case à cocher **un service Edge a/v est compatible NAT** si vous souhaitez que le service Edge a/v utilise une configuration et une adresse IP de traduction d’adresses réseau (NAT).
  
Pour les services Edge activés, vous tapez un **nom de domaine complet (FQDN) de pool** et un port sous **ports** .
  
- Définissez le nom de domaine complet du pool de **services Edge d’accès** et un port qui identifie de manière unique le service.
    
- Définissez le nom de domaine complet (FQDN) du pool de **services de conférence Web** (si vous ne sélectionnez pas d’adresse IP et de FQDN séparés pour les conférences Web et si a/V n’est pas sélectionné) et un port qui identifie de manière unique le service.
    
- Définissez le nom de domaine complet (FQDN) du pool **de services A/v** (si vous ne sélectionnez pas d’adresse IP et de FQDN séparés pour les conférences Web et si a/V n’est pas sélectionné) et un port qui identifie de manière unique le service.
    
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  

