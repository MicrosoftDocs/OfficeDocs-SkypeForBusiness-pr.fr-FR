---
title: Configurer un VTC pour l’interopération avec Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Résumé : Configurez les périphériques VTC pour qu’ils fonctionnent Skype Entreprise Server.'
ms.openlocfilehash: 1165b4bf569701d71a435a4162ef9feb9ef3018f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594678"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Configurer un VTC pour l’interopération avec Skype Entreprise Server
 
**Résumé :** Configurez les périphériques VTC pour qu’ils fonctionnent Skype Entreprise Server.
  
Vous devrez effectuer les procédures de personnalisation de configuration suivantes pour chaque VTC qui se connectera au serveur VIS Skype Entreprise via une connexion SIP et une passerelle vidéo Cisco Unified Communications Manager (CallManager, ou CUCM).
  
Les paramètres décrits ici ne sont destinés qu’à des exemples de la façon dont CUCM peut être configuré pour fonctionner avec un VIS. D’autres paramètres et/ou utilisations d’autres fonctionnalités CUCM peuvent également être utilisés pour obtenir le même résultat. Aucune recommandation n’est implicite quant à la configuration optimale pour un scénario particulier.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Configurer un VTC enregistré avec CUCM

1. Connectez-vous à l’appareil Cisco VTC et accédez à Configuration - Configuration du système \> - \> Approvisionnement.
    
2. Vérifiez les paramètres suivants, en corrigeant selon vos besoins : 
    
   |**Parameter**|**Valeur recommandée**|
   |:-----|:-----|
   |Mode d’approvisionnement  <br/> | CUCM <br/> |
   |Adresse externalmanager  <br/> | FQDN de CUCM <br/> |
   | Domaine ExternalManager <br/> |Domaine CUCM  <br/> |
   
3. Accédez à Configuration - \> Configuration du système - \> Réseau.
    
4. Vérifiez les paramètres suivants, en corrigeant selon vos besoins : 
    
   |**Parameter**|**Valeur recommandée**|
   |:-----|:-----|
   |Nom de domaine DNS  <br/> | Nom de domaine CUCM <br/> |
   |Adresse du serveur DNS 1  <br/> | votre adresse de serveur DNS souhaitée <br/> |
   
5. Accédez à Configuration - \> Configuration du système - Services \> réseau. Assurez-vous que le mode H.323 est désactivé et que le mode SIP est allumé. 
    
6. Ces options sont définies automatiquement lorsque le point de terminaison est enregistré avec CUCM. Vérifiez les paramètres suivants, en corrigeant selon vos besoins : 
    
   |**Parameter**|**Valeur recommandée**|
   |:-----|:-----|
   |H.323 Mode  <br/> | Désactivé <br/> |
   |HTTP Mode  <br/> | Activé <br/> |
   | SIP Mode <br/> | Activé <br/> |
   |Telnet Mode  <br/> | Activé <br/> |
   |WelcomeText  <br/> | Activé <br/> |
   |XMLAPI Mode  <br/> | Activé <br/> |
   
7. Accédez à Configuration - \> Configuration système \> - SIP.
    
8. Vérifiez les paramètres suivants, en corrigeant selon vos besoins : 
    
   |**Parameter**|**Valeur recommandée**|
   |:-----|:-----|
   |Profil 1 - DefaultTransport  <br/> | TCP <br/> |
   |Profil 1 - Sortant  <br/> | Désactivé <br/> |
   |Profil 1 - TlsVerify  <br/> | Activé <br/> |
   |Profil 1 - Type  <br/> | Cisco <br/> |
   |Profil 1 - URI  <br/> | Affecté automatiquement lors de l’inscription CUCM <br/> |
   |Proxy 1 - Adresse  <br/> |Nom d’hôte du CUCM  <br/> |
   
Le VTC est maintenant configuré pour l’interopération. Avant que le service puisse commencer, il existe des étapes finales à effectuer côté CUCM.
### <a name="configure-vtc-devices-on-cucm"></a>Configurer des périphériques VTC sur CUCM

1. Connectez-vous au CUCM et accédez à Administration CM unifiée Cisco \> - Appareil - \> Téléphone- \> Rechercher. 
    
2. Sélectionnez l’appareil VTC à configurer. Vérifiez les paramètres suivants sur l’écran Téléphone configuration, en corrigeant selon vos besoins. Une fois ces paramètres modifiés ou vérifiés, cliquez sur **Enregistrer.**
    
   |**Parameter**|**Valeur recommandée**|
   |:-----|:-----|
   |Informations sur l’appareil : Téléphone bouton  <br/> | Standard Cisco Telepresence Codec C40 <br/> |
   |Informations sur l’appareil - Profil Téléphone courant  <br/> | Profil d’Téléphone courant standard <br/> |
   |Informations sur l’appareil : espace de recherche d’appel  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations sur l’appareil : espace de recherche d’appel AAR  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations sur l’appareil - Liste des groupes de ressources multimédias  <br/> | MRGL_SfBVideoInterop <br/> |
   |Informations spécifiques au protocole : profil de sécurité de l’appareil  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Informations spécifiques au protocole : réroutage de l’espace de recherche d’appel  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations spécifiques au protocole : espace de recherche d’appel SUBSCRIBE  <br/> | CSS_SfBVideoInterop <br/> |
   |Informations spécifiques au protocole - Profil SIP  <br/> | Profil SIP standard pour le point de terminaison de téléprésence <br/> |
   
3. Une fois la configuration VTC enregistrée, accédez à l’écran Téléphone configuration de l’appareil. En haut de l’écran du groupe Association, cliquez sur l’association pour l’interop vidéo. L’écran Configuration du numéro d’annuaire s’affiche. 
    
4. Vérifiez les paramètres suivants, en corrigeant selon vos besoins : 
    
    A effectuer les modifications appropriées comme indiqué dans les informations de numéro de répertoire et le numéro de Paramètres.
    
   |**Parameter**|**Valeur recommandée**|
   |:-----|:-----|
   | Informations sur le numéro de répertoire - Partition de l’itinéraire <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Numéro d’annuaire Paramètres - Appel de l’espace de recherche  <br/> | CSS_SfBVideoInterop <br/> |
   |Alternate Party and Confidential Access Level Paramètres - MLPP Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Ligne 1 sur l’appareil - Affichage (ID de l’appelant)  <br/> | Comme vous le souhaitez <br/> |
   |Ligne 1 sur l’appareil - Affichage ASCII (ID de l’appelant)  <br/> | Comme vous le souhaitez <br/> |
   
5. Lorsque vous avez terminé, faites défiler vers le haut de l’écran et appuyez sur **Enregistrer.** 
    
La configuration est maintenant terminée pour cet appareil VTC. Vous devrez répéter ce processus pour les autres périphériques VTC de votre entreprise.

