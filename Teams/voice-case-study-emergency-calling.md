---
title: Étude de cas de voix contoso teams
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
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786027"
---
# <a name="contoso-case-study-emergency-calling"></a>Étude de cas contoso : appels d’urgence

Pour mieux comprendre la disponibilité des appels d’urgence et la terminologie liée aux appels d’urgence &mdash; , au lieu, à l’emplacement d’urgence et à l’adresse enregistrée que contoso a &mdash; examiné gérer les appels d' [urgence](what-are-emergency-locations-addresses-and-call-routing.md) et [planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

Dans Office 365, un utilisateur de plan d’appel est automatiquement activé pour les appels d’urgence. Toutefois, seuls les utilisateurs de plan d’appels aux États-Unis peuvent utiliser des emplacements dynamiques pour le routage des appels d’urgence. 

Pour le routage direct, Contoso a appris qu’une configuration supplémentaire est nécessaire pour acheminer les appels d’urgence et éventuellement pour la connectivité des partenaires. L’administrateur doit configurer la connexion à un fournisseur de services de routage d’urgence (ERSP) (États-Unis) ou configurer le contrôleur de bordure de session (SBC) pour une application de type ELIN (Emergency location identification).

Contoso dispose de bureaux aux États-Unis et hors des États-Unis :

- Aux États-Unis, les utilisateurs du plan d’appel de contoso peuvent utiliser des emplacements dynamiques pour le routage des appels d’urgence. 

- Hors des États-Unis, contoso dispose de sites qui utilisent des plans d’appel et des sites qui sont connectés au système téléphonique via le routage direct.

## <a name="emergency-calling-use-cases"></a>Cas d’utilisation des appels d’urgence

Après avoir décidé du mode de connexion de contoso au système téléphonique, Contoso a identifié les cas d’utilisation des appels d’urgence suivants : 

- [Utilisateur de plan d’appels aux États-Unis](#calling-plan-user-in-the-united-states) 

- [Utilisateur de plan d’appel hors des États-Unis](#calling-plan-user-outside-of-the-united-states)

- [Utilisateur qui se connecte au système téléphonique via le routage direct](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Utilisateur de plan d’appels aux États-Unis  

La configuration requise pour le numéro de téléphone à un emplacement d’urgence est requise. Pour mieux comprendre ces exigences, nous avons examiné les considérations en matière [de contoso pour les offres d’appels](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans). 

Sur la base de ces exigences, Contoso a décidé d’associer l’emplacement avec le numéro de téléphone lorsqu’un numéro est attribué à un utilisateur aux États-Unis.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Utilisateur de plan d’appel hors des États-Unis 

Pour savoir à quel moment un numéro de téléphone doit être associé à un emplacement d’urgence, [les considérations relatives aux offres d’appels](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)sont examinées par contoso. Selon la configuration requise, Contoso a déterminé les éléments suivants :  

-  Contoso associe l’emplacement avec le numéro de téléphone lorsque le numéro est attribué à un utilisateur au Canada. 

- Contoso affectera un emplacement d’urgence lorsque le numéro de téléphone sera acquis auprès d’Office 365 ou qu’un numéro sera transféré à partir d’un autre fournisseur ou opérateur de services. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Utilisateur qui se connecte au système téléphonique via le routage direct 

Pour planifier le routage d’urgence pour ce cas d’utilisation, des [considérations relatives au routage direct](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)sont examinées par contoso. Dans la mesure où les utilisateurs de routage direct ne reçoivent pas les appels d’urgence de la même manière que les utilisateurs d’un plan d’appels, Contoso a décidé de fournir les appels d’urgence. Le routage direct peut être connecté à un fournisseur de services de routage d’urgence (ERSP). Le routage direct peut également avoir un SBC incluant un numéro d’identification d’emplacement d’urgence (ELIN).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Considérations relatives au fournisseur de services de routage d’urgence (ERSP)

Les fournisseurs de services de routage d’urgence (ERSPs) peuvent diriger automatiquement les appels d’urgence en fonction de l’emplacement de l’appelant.  

- Si un fournisseur de service de routage d’urgence est intégré à un déploiement de routage directe, les appels d’urgence disposant d’un emplacement d’acquisition dynamique seront automatiquement routés vers le point d’accès de sécurité publique (PSAPI) qui dessert cet emplacement. 

- Les appels d’urgence sans emplacement acquis de manière dynamique sont d’abord prédéfinis pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de répartition approprié en fonction de l’emplacement mis à jour. 


#### <a name="elin-considerations"></a>ELIN considérations

Si une application SBC ELIN est intégrée à un déploiement de routage direct, des étapes de configuration supplémentaires doivent se produire pour associer les adresses d’urgence aux numéros de téléphone.  

Contoso a décidé d’utiliser des contrôleurs de frontière de session qui incluent des applications d’identification d’emplacement d’urgence (ELIN).  

## <a name="security-desk-notification"></a>Notification du centre de sécurité

La possibilité de notifier le support technique lors de la mise en place d’un appel d’urgence est disponible pour les plans d’appel Microsoft et le routage direct du système téléphonique. Contoso a examiné les détails dans la notification du support technique pour déterminer si cela doit être configuré au bureau.  

Contoso a décidé d’utiliser la notification du support technique.

## <a name="configuration"></a>Configuration 

Contoso a suivi les étapes décrites dans [configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md) pour : 

- Attribution d’adresses de secours 

- Configurer les paramètres réseau 

- Configurer le service d’information d’emplacement 

- Configurer des stratégies d’urgence 

- Activer les utilisateurs et les sites 

- Tester les appels d’urgence 

Une fois les appels d’urgence dynamiques configurés, Contoso a besoin d’affecter l’emplacement à l’utilisateur approprié.  

- Pour ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation, Contoso a suivi les étapes décrites dans [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)

- Pour créer des lieux de bâtiment, de planchers et de bureaux, Contoso a suivi les étapes décrites dans [Ajouter, modifier ou supprimer un emplacement pour un emplacement d’urgence](add-change-remove-emergency-place-organization.md) . 

- Pour attribuer un emplacement d’urgence, Contoso a suivi les étapes décrites dans [affecter ou modifier un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md). 

 