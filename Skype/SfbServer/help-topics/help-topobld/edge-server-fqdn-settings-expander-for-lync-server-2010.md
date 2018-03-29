---
title: Edge Server FQDN paramètres Expander pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés de paramètres externe, vous devez configurer les éléments suivants :'
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Edge Server FQDN paramètres Expander pour Lync Server 2010
 
Pour définir les propriétés de **paramètres externe**, vous devez configurer les éléments suivants :
  
Sélectionnez le **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** case à cocher si vous souhaitez définir différents FQDN du Pool et IP adresses pour la conférence web et audio/vidéo.
  
> [!NOTE]
> Si vous choisissez pour ne pas sélectionner la case à cocher pour les adresses IP et de nom de domaine complet séparés, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur de transport Edge. Le seul nom de domaine pleinement qualifié qui consiste à configurer est le nom de domaine complet associé au service Edge d’accès. 
  
Sélectionnez le **A / V Edge service NAT activé** case à cocher si vous souhaitez que le A / service V Edge d’utiliser un réseau adresse adresse IP de la traduction (NAT) et la configuration.
  
Pour les services de bord activés, vous tapez un **Nom de domaine complet Pool** et un port sous **Ports**
  
- Définir le nom de domaine complet Pool **service Edge d’accès** et d’un port qui identifie le service.
    
- Définir le nom de domaine complet de **serveur Edge de conférence Web service** Pool (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie le service.
    
- Définir la **A / V Edge service** FQDN du Pool (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie le service.
    
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  

