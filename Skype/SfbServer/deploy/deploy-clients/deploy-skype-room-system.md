---
title: Déploiement de Skype Room System dans Skype Entreprise Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: En savoir plus sur la façon de déployer Skype espace système, une réunion solution de pièce composée d’intégré de matériel et de logiciels qui est optimisé pour rejoindre Skype pour les réunions d’entreprise.
ms.openlocfilehash: 11cbae1cdbdd0585a2ea67625179ee7862309723
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-system-in-skype-for-business-server"></a>Déploiement de Skype Room System dans Skype Entreprise Server
 
En savoir plus sur la façon de déployer Skype espace système, une réunion solution de pièce composée d’intégré de matériel et de logiciels qui est optimisé pour rejoindre Skype pour les réunions d’entreprise.
  
> [!NOTE]
> Pour les besoins de ce contenu, Skype pour professionnels pour SMART espace système, Crestron RL, et Polycom CX8000 sera appelé système de salle de Skype. 
  
 Système de chambre de Skype est un Skype pour client de communications unifiées Business qui a été optimisé pour Skype pour les réunions d’entreprise dans les salles de conférence physique.
  
Le client du système de salle de Skype a été développé à partir de la Skype pour client d’entreprise à l’aide de la Skype pour le Kit de développement de Business. Le Skype pour client d’entreprise s’exécute en arrière-plan en mode d’interface utilisateur supprimé partiel. Le Skype pour client d’entreprise contrôle la Galerie vidéo et la phase de contenu à l’écran à l’avant de la pièce. Le client Skype espace système fournit une expérience de la console sur l’écran du bureau pour contrôler les réunions. Système de chambre Skype fournit : 
  
- De rejoindre une réunion en appuyant sur un seul bouton
    
- De configurer automatiquement une galerie de vidéos multi-vues : 
    
- De disposer d’un tableau blanc tactile à l’écran, à l’avant de la salle 
    
- D’intégrer un calendrier pour l’accès aux réunions planifiées
    
- De partager et faire basculer du contenu 
    
Ce document vous guide tout au long de la mise en service du système de salle Skype dans Skype pour Business Server et Exchange Server. Consultez également le Guide d’Installation de Skype espace système fournis par votre administrateur, qui vous guide dans la configuration du matériel PC et les périphériques dans la salle de réunion. 
  
## <a name="prerequisites"></a>Conditions requises

Voici la configuration requise pour le système de salle de Skype : 
  
- Un compte Exchange de boîte aux lettres de ressources pour faciliter la planification dans le calendrier pour les salles de réunion, avec service AutoDiscover activé sur Exchange Server (2013 de préférence).
    
- Skype un compte Business Skype espace système sur un Skype pour le pool de serveur d’entreprise (Édition Standard ou entreprise).
    
- Une application de client Skype espace système PC avec tous les logiciels requis installés. Le PC applicatif doit exécuter le système d’exploitation Windows 7 Embedded Standard. Ce matériel est fourni par les partenaires OEM avec tous les périphériques (affichage, caméra, micro, haut-parleurs).
    
- Si vous décidez de joindre la solution matérielle-logicielle Skype espace système PC à un domaine des Services de domaine Active Directory (AD DS), vous devez spécifier les paramètres de stratégie de groupe qui n’interfèrent pas avec le système de salle de Skype. Sinon, vous pouvez conserver ce PC applicatif dans le groupe de travail. 
    
- Droits d’utilisateur appropriés pour exécuter les applets de commande spécifiés dans ce document. Les applets de commande CsMeetingRoom sont modélisés d’après l’applet de commande CsUser. Par conséquent, tous les rôles de contrôle d’accès basé sur un rôle (RBAC) requis pour exécuter l’applet de commande CsUser s’appliquent également aux applets de commande CsMeetingRoom. 
    
## <a name="supported-topologies"></a>Topologies prises en charge

Le tableau suivant indique l’interopérabilité du client Skype espace système entre les différents déploiements de Skype pour les professionnels et l’échange de topologies, sur site ou dans le nuage : 
  

|**Topologie**|**AD**|**Skype Entreprise**|**Exchange**|
|:-----|:-----|:-----|:-----|
|En local  <br/> |En local  <br/> |En local  <br/> |En local  <br/> |
|Office 365 mutualisée (O365MT)  <br/> |En ligne  <br/> |En ligne  <br/> |En ligne  <br/> |
|Office 365 dédié  <br/> (Contactez votre fournisseur de services)  <br/> |En local  <br/> |En ligne  <br/> |En ligne  <br/> |
|Hybride (domaine fractionné)  <br/> Non prise en charge  <br/> |En local  <br/> En local  <br/> En local  <br/> |En local  <br/> En ligne  <br/> En ligne  <br/> |En ligne  <br/> En ligne  <br/> En local  <br/> |
   
Les versions antérieures à Lync Server 2013 sont partiellement prises en charge. Dans ces scénarios, Skype espace système peut participer Skype pour des conférences (celles qui sont prévues par les utilisateurs hébergés sur Lync Server 2010) tant que les conférences sont « publics », c'est-à-dire les conférences ne sont pas personnalisés à accès restreint. 
  
Skype salle de système ne peut pas être à hébergement sur une version de serveur Lync antérieures à Lync Server 2013. Lorsqu’un système de salle Skype ne peut pas se connecter à Exchange à récupérer les paramètres de calendrier--par exemple, lorsqu’il n’y a aucune boîte aux lettres Exchange configuré pour le compte système local de Skype ou Exchange ne sont pas accessibles : Conférence maintenant et les conférences ad hoc fonctionnera, mais joint une réunion planifiée ne sera pas. 
  
Le tableau suivant indique la prise en charge du client Skype espace système avec les versions d’Exchange Server : 
  

|**Exchange**|**Dans les locaux**|**En ligne**|**Hybride**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Oui (une seule forêt)  <br/> |N/A  <br/> |N/A  <br/> |
|Exchange 2013  <br/> |Oui (prise en charge de plusieurs forêts disponible pour Exchange 2013 CU6 et versions ultérieures)  <br/> |Oui  <br/> |Oui  <br/> |
|Exchange 2016  <br/> |Oui (plusieurs forêts prise en charge disponible)  <br/> |Oui  <br/> |Oui  <br/> |
   

