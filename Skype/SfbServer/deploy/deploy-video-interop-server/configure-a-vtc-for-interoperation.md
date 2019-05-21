---
title: Configurer une VTC pour l’interopérabilité avec Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Résumé: configurez les appareils VTC pour qu’ils fonctionnent avec Skype entreprise Server.'
ms.openlocfilehash: 460ac0a301ee9c9b2cb5bb1b4ca4c1aaf6ee4825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302790"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurer une VTC pour l’interopérabilité avec Skype entreprise Server
 
**Résumé:** Configurez les appareils VTC pour fonctionner avec Skype entreprise Server.
  
Vous devez effectuer les procédures de personnalisations de configuration suivantes pour chaque VTC qui sera connecté à Skype entreprise par le biais d’une passerelle SIP et de Cisco Unified Communications Manager (CallManager ou CUCM).
  
Les paramètres décrits ici s’entendent uniquement comme exemples de la manière dont CUCM peut être configuré pour fonctionner avec un VIS. Il est possible d’utiliser d’autres paramètres et/ou de prévoir d’autres utilisations de la fonctionnalité CUCM pour obtenir le même résultat. Nous ne faisons aucune recommandation quant à la meilleure configuration possible pour un scénario en particulier.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurer un périphérique de vidéoconférence (VTC) enregistré avec le CUCM

1. Connectez-vous à l’appareil Cisco VTC et accédez à configuration\>-configuration du\>système-approvisionnement.
    
2. Vérifiez les paramètres suivants (et corrigez-les si nécessaire) : 
    
   |**Paramètre**|**Paramètre recommandé**|
   |:-----|:-----|
   |Mode de mise en service  <br/> | CUCM <br/> |
   |Adresse de l’ExternalManager  <br/> | Nom de domaine complet du CUCM <br/> |
   | Domaine ExternalManager <br/> |Domaine de CUCM  <br/> |
   
3. Accédez à configuration-\>configuration du système\>-réseau.
    
4. Vérifiez les paramètres suivants (et corrigez-les si nécessaire) : 
    
   |**Paramètre**|**Paramètre recommandé**|
   |:-----|:-----|
   |Nom du domaine DNS  <br/> | Nom du domaine du CUCM <br/> |
   |Adresse du serveur DNS 1  <br/> | Votre adresse de serveur DNS souhaitée <br/> |
   
5. Accédez à configuration-\>configuration du système\>-services réseau. Assurez-vous que le mode H.323 est désactivé et que le mode SIP est activé. 
    
6. Ces options sont activées automatiquement lorsque le point de terminaison est enregistré avec le CUCM. Vérifiez les paramètres suivants (et corrigez-les si nécessaire) : 
    
   |**Paramètre**|**Paramètre recommandé**|
   |:-----|:-----|
   |Mode H.323  <br/> | Désactivé <br/> |
   |Mode HTTP  <br/> | Activé <br/> |
   | Mode SIP <br/> | Activé <br/> |
   |Mode Telnet  <br/> | Activé <br/> |
   |WelcomeText  <br/> | Activé <br/> |
   |Mode XMLAPI  <br/> | Activé <br/> |
   
7. Accédez à configuration-\>configuration du système\>-SIP.
    
8. Vérifiez les paramètres suivants (et corrigez-les si nécessaire) : 
    
   |**Paramètre**|**Paramètre recommandé**|
   |:-----|:-----|
   |Profile 1 - DefaultTransport  <br/> | TCP <br/> |
   |Profile 1 - Outbound  <br/> | Désactivé <br/> |
   |Profil 1-TlsVerify  <br/> | Activé <br/> |
   |Profile 1 - Type  <br/> | Cisco <br/> |
   |Profile 1 - URI  <br/> | Automatiquement attribué à l’enregistrement du CUCM <br/> |
   |Proxy 1 - Adresse  <br/> |Le nom de l’hôte du CUCM  <br/> |
   
Le périphérique de vidéoconférence est désormais configuré pour l’interopérabilité. Avant d’utiliser le service, il vous reste certaines étapes à effectuer au niveau du CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurer les périphériques de vidéoconférence sur le CUCM

1. Connectez-vous à CUCM et accédez à administration Cisco Unified\>cm-\>appareil-\>recherche de téléphone. 
    
2. Sélectionnez le périphérique de vidéoconférence (VTC) à configurer. Vérifiez les paramètres suivants sur l’écran Configuration du téléphone et corrigez-les si nécessaire. Une fois ces paramètres modifiés ou vérifiés, cliquez sur **Enregistrer**.
    
   |**Paramètre**|**Paramètre recommandé**|
   |:-----|:-----|
   |Informations sur l’appareil - exemple de bouton de téléphone  <br/> | C40 de codec de téléprésence Cisco standard <br/> |
   |Informations sur l’appareil - profil commun de téléphone  <br/> | Profil commun de téléphone standard <br/> |
   |Informations sur l’appareil - espace de recherche  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations sur l’appareil - espace de recherche AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations sur l’appareil - liste des groupes de ressources médias  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informations spécifiques de protocole - profil de sécurité de l’appareil  <br/> | C40 de codec de présence Cisco <br/> |
   |Informations spécifiques de protocole - espace de recherche du réacheminement  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations spécifiques au protocole-ABONNez-vous à l’espace de recherche  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations spécifiques sur le protocole - profil SIP  <br/> | Profil SIP standard pour point de terminaison Telepresence <br/> |
   
3. Une fois la configuration de vidéoconférence enregistrée, accédez à l’écran de configuration de l’appareil. Dans la partie supérieure de l’écran, dans le groupe Association, cliquez sur l’association pour l’interopérabilité vidéo. Vous accédez à l’écran Configuration des numéros du répertoire. 
    
4. Vérifiez les paramètres suivants (et corrigez-les si nécessaire) : 
    
    Effectuez les changements dans les informations de numéros du répertoire et dans les paramètres de numéros du répertoire.
    
   |**Paramètre**|**Paramètre recommandé**|
   |:-----|:-----|
   | Informations des numéros du répertoire - cloisonnement de l’itinéraire <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Paramètres des numéros du répertoire - espace de recherche  <br/> | CSS_SfBVideoInterop <br/> |
   |Paramètres de niveau d’accès confidentiel et d’autres parties MLPP - espace de recherche MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Ligne 1 sur l’écran de l’appareil (ID d’appelant)  <br/> | Comme souhaité <br/> |
   |Ligne 1 sur l’appareil-affichage ASCII (ID d’appelant)  <br/> | Comme souhaité <br/> |
   
5. Lorsque vous avez terminé, remontez en haut de l’écran et sélectionnez **Enregistrer**. 
    
La configuration est désormais terminée pour ce périphérique de vidéoconférence. Reproduisez ces étapes pour les autres périphériques de vidéoconférence dans votre entreprise.

