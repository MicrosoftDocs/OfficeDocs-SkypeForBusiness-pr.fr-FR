---
title: Expanseur des paramètres nom de domaine complet du serveur Edge Server pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés sous paramètres externes, configurez les options suivantes :'
ms.openlocfilehash: d925da792e2c2c296707a99d6a4ae6b29c0545a9
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375607"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expanseur des paramètres nom de domaine complet du serveur Edge Server pour Lync Server 2010
 
Pour définir les propriétés sous **paramètres externes**, configurez les options suivantes :
  
Sélectionnez le **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** case à cocher si vous souhaitez définir distincts IP et nom complet du Pool des adresses pour la conférence web et audio/vidéo.
  
> [!NOTE]
> Si vous choisissez de n’activez ne pas la case à cocher pour les adresses IP et le nom de domaine complet distinctes, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur Edge. Le seul nom de domaine complet qui consiste à configurer est le nom de domaine complet associé au service Edge d’accès. 
  
Sélectionnez le **A V Edge service / NAT activé** case à cocher si vous souhaitez A / adresse IP de traduction (NAT) et la configuration d’adresses service V Edge à utiliser un réseau.
  
Pour les services Edge activés, vous tapez un **Nom complet du Pool** et un port sous **Ports**
  
- Définir le nom complet du Pool de **service Edge d’accès** et un port qui identifie le service.
    
- Définir le nom complet du Pool de **service Edge de conférence Web** (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie le service.
    
- Définir le **A / V Edge service** nom complet du Pool (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie de manière unique le service.
    
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  

