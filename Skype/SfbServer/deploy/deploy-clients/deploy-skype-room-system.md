---
title: Vue d’ensemble du déploiement pour le système de salle de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: En savoir plus sur la façon de déployer Skype salle système, une réunion solution salle consistant intégrée de configuration matérielle et logicielle optimisée pour joindre Skype pour les réunions d’entreprise.
ms.openlocfilehash: a985a209c63d6d0262db42fb07f78133960444ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020471"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a>Planification du déploiement pour le système de salle Skype dans Skype pour les entreprises
 
En savoir plus sur la façon de déployer Skype salle système, une réunion solution salle consistant intégrée de configuration matérielle et logicielle optimisée pour joindre Skype pour les réunions d’entreprise.
  
> [!NOTE]
> À des fins de ce contenu, Skype pour les entreprises actives système salle, Crestron RL, et Polycom CX8000 sera désigné en tant que système de salle Skype. 

> [!NOTE]
> Systèmes de salle Skype v2 est un produit différents avec des dépendances différents et des procédures de déploiement. Pour plus d’informations sur les systèmes de salle Skype v2, voir [planifier Skype salle systèmes v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md).
  
 Système de salle de Skype est un Skype pour le client de communications unifiées entreprise qui a été optimisée pour Skype pour les réunions d’entreprise dans les salles de conférence physique.
  
Le client du système de salle Skype a été développé à partir de la Skype pour client d’entreprise à l’aide de la Skype pour Business SDK. Le Skype pour client d’entreprise s’exécute en arrière-plan en mode d’interface utilisateur supprimé partiel. Le Skype pour client d’entreprise contrôle la galerie de vidéos et de la phase de contenu à l’écran au début de la salle. Le client du système de salle Skype offre une expérience de console sur l’affichage du bureau pour contrôler les réunions. Système de salle Skype fournit : 
  
- De rejoindre une réunion en appuyant sur un seul bouton
    
- De configurer automatiquement une galerie de vidéos multi-vues : 
    
- De disposer d’un tableau blanc tactile à l’écran, à l’avant de la salle 
    
- D’intégrer un calendrier pour l’accès aux réunions planifiées
    
- De partager et faire basculer du contenu 
    
Ce document vous guide tout au long de la mise en service du système de salle Skype dans Skype pour Business Server et Exchange Server. Voir aussi le Guide d’Installation Skype salle système fournie par votre administrateur, qui vous guide à travers la configuration de l’appliance PC et périphériques dans la salle de réunion. 
  
## <a name="prerequisites"></a>Conditions requises

Voici la configuration requise pour le système de salle de Skype : 
  
- Un compte Exchange de boîte aux lettres de ressources pour faciliter la planification dans le calendrier pour les salles de réunion, avec service AutoDiscover activé sur Exchange Server (2013 de préférence).
    
- Skype un compte système métier Skype salle sur un Skype pour le pool de serveurs de l’entreprise (Édition Standard ou entreprise).
    
- Une application de client Skype salle système PC avec tous les logiciels requis installés. Le PC applicatif doit exécuter le système d’exploitation Windows 7 Embedded Standard. Ce matériel est fourni par les partenaires OEM avec tous les périphériques (affichage, caméra, micro, haut-parleurs).
    
- Si vous décidez de participer à l’application du système de salle Skype PC à un domaine des Services de domaine Active Directory (AD DS), vous devez spécifier les paramètres de stratégie de groupe qui n’a pas été interfèrent avec Skype salle système. Sinon, vous pouvez conserver ce PC applicatif dans le groupe de travail. 
    
- Droits d’utilisateur appropriés pour exécuter les applets de commande spécifiés dans ce document. Les applets de commande CsMeetingRoom sont modélisés d’après l’applet de commande CsUser. Par conséquent, tous les rôles de contrôle d’accès basé sur un rôle (RBAC) requis pour exécuter l’applet de commande CsUser s’appliquent également aux applets de commande CsMeetingRoom. 
    
## <a name="supported-topologies"></a>Topologies prises en charge

Le tableau suivant indique l’interopérabilité des clients Skype salle système entre les différents déploiements de Skype pour les topologies Business et Exchange sur site ou dans le nuage : 
  

|**Topologie**|**AD**|**Skype Entreprise**|**Exchange**|
|:-----|:-----|:-----|:-----|
|En local  <br/> |En local  <br/> |En local  <br/> |En local  <br/> |
|Office 365 plusieurs clients (O365MT)  <br/> |En ligne  <br/> |En ligne  <br/> |En ligne  <br/> |
|Office 365 dédié  <br/> (Contactez votre fournisseur de services)  <br/> |En local  <br/> |En ligne  <br/> |En ligne  <br/> |
|Hybride (domaine fractionné)  <br/> Non prise en charge  <br/> |En local  <br/> En local  <br/> En local  <br/> |En local  <br/> En ligne  <br/> En ligne  <br/> |En ligne  <br/> En ligne  <br/> En local  <br/> |
   
Les versions antérieures à Lync Server 2013 sont partiellement prises en charge. Dans ces scénarios, Skype salle système peuvent participer à Skype pour des conférences (ceux qui sont planifiés par les utilisateurs hébergés sur Lync Server 2010) dans la mesure où les conférences sont « publics », ce qui signifie que les conférences ne sont pas personnalisé pour un accès restreint. 
  
Système de salle de Skype ne peuvent pas être hébergé sur une version de serveur Lync antérieures à Lync Server 2013. Lorsqu’un système de salle Skype ne peut pas se connecter à Exchange pour récupérer les paramètres du calendrier, par exemple, lorsqu’il n’existe aucune boîte aux lettres Exchange configuré pour le compte de système de salle Skype ou Exchange n’est pas accessible--Conférence maintenant et conférence ad hoc fonctionne, mais rejoindre une réunion planifiée ne le pourront pas. 
  
Le tableau suivant indique la prise en charge du client de système de salle Skype avec les versions d’Exchange Server : 
  

|**Exchange**|**En local**|**En ligne**|**Hybride**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |Oui (une seule forêt)  <br/> |N/A  <br/> |N/A  <br/> |
|Exchange 2013  <br/> |Oui (prise en charge de plusieurs forêts disponible pour Exchange 2013 CU6 et versions ultérieures)  <br/> |Oui  <br/> |Oui  <br/> |
|Exchange 2016  <br/> |Oui (plusieurs forêts prise en charge disponible)  <br/> |Oui  <br/> |Oui  <br/> |
   

