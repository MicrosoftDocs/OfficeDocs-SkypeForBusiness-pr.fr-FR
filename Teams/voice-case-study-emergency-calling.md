---
title: Teams cas Contoso voix
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams cas de voix pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786027"
---
# <a name="contoso-case-study-emergency-calling"></a>Étude de cas Contoso : appels d’urgence

Pour comprendre la disponibilité des appels d’urgence et la terminologie relatives aux appels d’urgence: Adresse de secours, Emplacement, Emplacement d’urgence et Adresse enregistrée, Contoso a examiné Gérer les appels d’urgence et Planifier et configurer les appels d’urgence &mdash; &mdash; [dynamiques.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)

Dans Office 365, un utilisateur d’un plan d’appels est automatiquement activé pour les appels d’urgence. Seuls les utilisateurs aux États-Unis peuvent utiliser des emplacements dynamiques pour router des appels d’urgence. 

Pour le routage direct, Contoso a appris que des configurations supplémentaires sont nécessaires pour router des appels d’urgence et éventuellement pour la connectivité des partenaires. L’administrateur doit configurer la connexion à un fournisseur de services de routage d’urgence (ERSP) (États-Unis) OU configurez le contrôleur de session border Controller (SBC) pour une application ELIN (Emergency Location Identification Number).

Contoso a des bureaux aux États-Unis et en dehors des États-Unis :

- Aux États-Unis, les utilisateurs du plan d’appels Contoso peuvent utiliser des emplacements dynamiques pour router des appels d’urgence. 

- En dehors des États-Unis, Contoso dispose de sites qui utilisent des plans d’appel et de sites connectés à Système téléphonique via un routage direct.

## <a name="emergency-calling-use-cases"></a>Cas d’utilisation des appels d’urgence

Après avoir décidé comment Contoso se connectera Téléphone système informatique, Contoso a identifié les cas d’utilisation des appels d’urgence suivants : 

- [Utilisateur d’un forfait d’appels aux États-Unis](#calling-plan-user-in-the-united-states) 

- [Utilisateur d’un forfait d’appels en dehors des États-Unis](#calling-plan-user-outside-of-the-united-states)

- [Utilisateur qui se connecte à Système téléphonique via un routage direct](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Utilisateur d’un forfait d’appels aux États-Unis  

Des exigences s’offrent à vous lorsque le numéro de téléphone doit être associé à un emplacement d’urgence. Pour comprendre ces exigences, Contoso a examiné les considérations relatives [aux forfaits d’appels.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

En fonction de ces exigences, Contoso a décidé d’associer l’emplacement au numéro de téléphone lorsqu’un numéro est affecté à un utilisateur aux États-Unis.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Utilisateur d’un forfait d’appels en dehors des États-Unis 

Pour comprendre quand un numéro de téléphone doit être associé à un emplacement d’urgence, Contoso a examiné les considérations pour [les plans d’appels.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) En se basant sur les exigences, Contoso a décidé des choses suivantes :  

-  Contoso associe l’emplacement au numéro de téléphone lorsqu’un numéro est affecté à un utilisateur au Canada. 

- Contoso attribue un emplacement d’urgence lorsque le numéro de téléphone est acquis auprès d’Office 365 ou lorsqu’un numéro est transféré à partir d’un autre opérateur ou fournisseur de services. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Utilisateur qui se connecte à Système téléphonique via un routage direct 

Pour planifier le routage d’urgence pour ce cas d’utilisation, Contoso a examiné les considérations en relation avec [le routage direct.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) Étant donné que les utilisateurs du routage direct ne reçoivent pas les appels d’urgence de la même manière que les utilisateurs du plan d’appel, Contoso a dû décider comment fournir les appels d’urgence. Le routage direct peut être connecté à un fournisseur de services de routage d’urgence. Le routage direct peut également avoir un SBC qui inclut un numéro d’identification de l’emplacement d’urgence (ELIN).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Considérations en considérations du fournisseur de services de routage d’urgence

Les fournisseurs de services de routage d’urgence peuvent router automatiquement les appels d’urgence en fonction de l’emplacement de l’appelant.  

- Si un fournisseur de services de routage d’urgence est intégré à un déploiement de routage direct, les appels d’urgence ayant acquis dynamiquement un emplacement sont automatiquement acheminés vers le point de réponse de sécurité publique (PUBLIC Safety Answering Point) de cet emplacement. 

- Les appels d’urgence sans emplacement dynamiquement acquis sont d’abord filés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre d’urgence approprié en fonction de l’emplacement mis à jour. 


#### <a name="elin-considerations"></a>Considérations ELIN

Si une application ELIN SBC est intégrée dans un déploiement de routage direct, des étapes de configuration supplémentaires doivent être nécessaires pour associer les adresses de secours aux numéros de téléphone.  

Contoso a décidé d’utiliser des contrôleurs de session qui incluent des applications ELIN (Emergency Location Identification Number).  

## <a name="security-desk-notification"></a>Notification du service de sécurité

La possibilité d’avertir le service de sécurité lorsqu’un appel d’urgence est passé est disponible pour les plans d’appels Microsoft et Système téléphonique routage direct. Contoso a examiné les détails de la notification du service de sécurité pour déterminer si cette configuration doit être configurée sur leur bureau  

Contoso a décidé d’utiliser la notification de service de sécurité.

## <a name="configuration"></a>Configuration 

Contoso a suivi les étapes de la procédure [Configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md) pour : 

- Affecter des adresses de secours 

- Configurer les paramètres réseau 

- Configurer le service Informations sur l’emplacement 

- Configurer des stratégies d’urgence 

- Activer les utilisateurs et les sites 

- Tester les appels d’urgence 

Une fois les appels d’urgence dynamiques configurés, Contoso doit affecter l’emplacement à l’utilisateur approprié.  

- Pour ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation, Contoso a suivi les étapes de l’étape Ajouter, modifier ou supprimer un emplacement d’urgence [pour votre organisation.](add-change-remove-emergency-location-organization.md)

- Pour créer des bâtiments, des étages et des bureaux, Contoso a suivi les étapes de l’étape Ajouter, modifier ou supprimer un emplacement [d’urgence.](add-change-remove-emergency-place-organization.md) 

- Pour affecter un emplacement d’urgence, Contoso a suivi les étapes de l’affectation ou de la modification d’un emplacement [d’urgence pour un utilisateur.](assign-change-emergency-location-user.md) 

 