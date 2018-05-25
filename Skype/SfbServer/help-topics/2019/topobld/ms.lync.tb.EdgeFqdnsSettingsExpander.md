---
title: Expanseur des paramètres de noms de domaine complets du serveur Edge
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Pour modifier ou spécifier des paramètres de sécurité externe pour les serveurs de périphérie, vous devez d’abord déterminer si vous utiliserez des adresses IP séparées pour access protocole SIP (Session Initiation), le service Edge de conférence Web et le service Edge Audio/vidéo.
ms.openlocfilehash: 8c686252e4fab89ad08608dceea92f06a3776737
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="edge-server-fqdns-settings-expander"></a>Expanseur des paramètres de noms de domaine complets du serveur Edge
 
Pour modifier ou spécifier les **paramètres externes** des serveurs Edge, vous devez d’abord déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP (Session Initiation Protocol), le service Edge de conférence web et le service Edge audio/vidéo.
  
Si vous envisagez d’utiliser des adresses IP distinctes chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Chaque service doit disposer d’un enregistrement d’hôte DNS (A) correspondant créé à cette fin.
  
Pour chacun des services côté externe, spécifiez un nom de domaine complet (FQDN) et un port associé. Par exemple, pour **Accès SIP**, vous pouvez utiliser sip.contoso.com avec le port 5061 associé.
  
> [!IMPORTANT]
> Si vous sélectionnez des noms de domaine complets distincts pour chaque service côté externe, une valeur de port unique doit être associée à chacun de ces services. Par défaut, le SIP est associé au port 5061/TLS, le service Edge de conférence web, au port 444/TLS et le service Edge de conférence A/V, au port 443/TLS. Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et d’adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent des valeurs configurées initialement. 
  
Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du pool et du port **Accès SIP**, si nécessaire.
  
> [!IMPORTANT]
> Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et des adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent des valeurs configurées initialement. 
  
Pour plus d’informations sur la définition et la configuration des paramètres des services Edge, voir [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).
  

