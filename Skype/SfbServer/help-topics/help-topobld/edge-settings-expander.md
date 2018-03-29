---
title: Expanseur des paramètres du pool de serveurs Edge
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Pour modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples, vous disposez des sections suivantes :'
ms.openlocfilehash: 5e9e916283bf36e0d81af41477920ba19e13e9a8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-settings-expander"></a>Expanseur des paramètres du pool de serveurs Edge
 
Pour modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples, vous disposez des sections suivantes :
  
- Paramètres généraux
    
- Paramètres de sélection du tronçon suivant
    
- Configuration du serveur Edge
    
## 

### <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du pool interne pour le pool de serveurs Edge. Modifiez le nom de domaine complet du pool pour changer ce paramètre.
  
Activez la case à cocher **Activer la fédération pour ce pool de bord (Port 5061)** si vous allez configurer la fédération avec un Lync Server 2013, partenaire de Microsoft Lync Server 2010 ou Microsoft Office Communications Server 2007 R2.
  
Sélectionnez **Activer la fédération XMPP pour ce pool Edge** pour activer la fédération XMPP.
  
Spécifiez le numéro de port pour **Port de réplication de configuration interne (HTTPS)**.
  
### <a name="next-hop-selection-settings"></a>Paramètres de sélection du tronçon suivant

Pour configurer ou modifier le **pool du tronçon suivant** utilisé par les serveurs Edge pour communiquer avec l’infrastructure interne, sélectionnez un directeur, un pool directeur, un serveur frontal ou un pool de serveurs frontaux dans la zone de liste déroulante. Uniquement des directeurs ou frontaux qui ont été configurés dans le Générateur de topologies s’affiche pour la sélection.
  
### <a name="edge-server-configuration"></a>Configuration du serveur Edge

Pour modifier ou spécifier des paramètres pour les **paramètres externes** des serveurs Edge, vous devez déterminer si vous allez utiliser des adresses IP distinctes pour l’accès SIP, la conférence web et le service audio/vidéo.
  
Si vous envisagez d’utiliser des adresses IP distinctes chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Un enregistrement d’hôte DNS (A) doit avoir été créé pour chaque service.
  
Pour chaque service externe, vous spécifiez un nom de domaine complet et un port associé. Par exemple, l’**accès SIP** utilise SIP.contoso.com avec le port 5061 associé.
  
> [!IMPORTANT]
> Si vous sélectionnez des noms de domaine complets distincts pour chaque service externe, chacun de ces services doit être associé à une valeur de port unique. Par défaut, le SIP utilise le port 5061/TLS, le service Edge de conférence web, le port 444/TLS et le serveur de conférence A/V, le port 443/TLS. Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et des adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent de valeurs configurées initialement. 
  
Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du pool et du port **Accès SIP**, si nécessaire.
  
> [!IMPORTANT]
> Si vous apportez des modifications à l’un de ces paramètres, y compris en utilisant un nom de domaine complet et des adresses IP ou des ports distincts, vous devez mettre à jour tous les autres services qui dépendent des valeurs configurées initialement. 
  
### 

Pour plus d’informations sur la définition et la configuration des paramètres pour les Services de bord, consultez [Définition de votre topologie de bord](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).
  

