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
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés sous paramètres externes, configurez les éléments suivants :'
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218245"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Développeur des paramètres FQDN du serveur Edge pour Lync Server 2010
 
Pour définir les propriétés sous **paramètres externes**, configurez les éléments suivants :
  
Activez la case à cocher **activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V** si vous voulez définir un nom de domaine complet et une adresse IP distincts pour la conférence Web et l’audio/vidéo.
  
> [!NOTE]
> Si vous choisissez de ne pas activer la case à cocher pour un nom de domaine complet et une adresse IP distincts, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge. Le seul nom de domaine complet à configurer est le nom de domaine complet associé au service Edge d’accès. 
  
Activez la case à cocher le **service Edge a/v est activé pour NAT** si vous voulez que le service Edge a/v utilise une configuration et une adresse IP de traduction d’adresses réseau (NAT).
  
Pour les services Edge activés, tapez un **nom de domaine complet du pool** et un port sous **ports** .
  
- Définissez le nom de domaine complet du pool de **service Edge d’accès** et un port qui identifie le service de manière unique.
    
- Définissez le nom de domaine complet du pool de **service Edge de conférence Web** (si l’option Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et a/V n’est pas sélectionnée) et un port qui identifie de manière unique le service.
    
- Définissez le nom de domaine complet du pool **de service Edge A/v** (si l’option Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et a/V n’est pas sélectionnée) et un port qui identifie de manière unique le service.
    
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

