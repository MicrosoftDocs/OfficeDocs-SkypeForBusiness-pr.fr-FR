---
title: Planifier et gérer les appels d’urgence
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: En savoir plus sur les appels d’urgence, y compris des informations sur les adresses d’urgence, le routage des appels d’urgence et les appels d’urgence dynamiques.
ms.openlocfilehash: 8c2de31aa81ac36338560c9b75d5c7ef27e460f8
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232545"
---
# <a name="manage-emergency-calling"></a>Gérer les appels d’urgence

Cet article décrit les concepts que vous devez connaître pour gérer les appels d’urgence : il inclut des informations sur les adresses d’urgence, les adresses d’urgence dynamiques et le routage des appels d’urgence. Cet article utilise la terminologie suivante :

- **Adresse d’urgence** : adresse postale : adresse physique ou rue d’un lieu d’entreprise pour votre organisation.

  Par exemple, l’adresse *12345 North rue, Redmond, WA 98052* est utilisée pour diriger les appels d’urgence vers les autorités de répartition compétentes et pour faciliter la localisation de l’appelant d’urgence.

- **Emplacement** : il s’agit d’un étage, d’un immeuble, d’une aile ou d’un numéro de bureau. La fonction place est associée à une adresse de secours pour fournir un emplacement plus précis au sein d’un bâtiment. Vous pouvez avoir un nombre illimité de lieux associés à une adresse de secours. Par exemple, si votre organisation possède plusieurs immeubles, il est possible que vous souhaitiez inclure des informations de lieu pour chaque bâtiment et pour chaque étage dans chaque bâtiment.  

- **Emplacement d’urgence** : un emplacement est une adresse postale, à l’endroit facultatif. Si votre entreprise possède plusieurs emplacements physiques, il est probable que vous ayez besoin de plus d’un emplacement d’urgence. 

  Lorsque vous créez une adresse de secours, un ID d’emplacement unique est créé automatiquement pour cette adresse.  Si vous ajoutez un lieu à une adresse de secours (par exemple, si vous ajoutez un étage à une adresse de bâtiment), un ID d’emplacement est créé pour la combinaison de l’adresse de secours et de l’emplacement.  Dans cet exemple, il y a deux ID d’emplacement : l’un pour l’adresse postale ; une pour l’adresse postale jointe et l’emplacement associé.

  Lorsque vous affectez un emplacement d’urgence à un utilisateur ou un site, il s’agit de l’ID d’emplacement unique associé à l’utilisateur ou au site.

- **Adresse enregistrée** : adresse de secours attribuée à chaque utilisateur de plan d’appels ; Il est parfois appelé adresse d’urgence statique ou adresse de l’enregistrement.  (Les adresses inscrites ne s’appliquent pas aux utilisateurs de routage direct.)

Pour créer une adresse d’urgence, vous devez utiliser le centre d’administration Teams.  

>[!Note]
>Il existe certaines différences en matière de gestion des appels d’urgence selon que vous utilisez des plans d’appel de système téléphonique ou de téléphone téléphonique directs pour votre connectivité PSTN. Ces considérations sont décrites dans cet article.

## <a name="emergency-address-validation"></a>Validation d’adresse de secours

Pour attribuer une adresse d’urgence à un utilisateur ou à un identifiant réseau, vous devez vous assurer que l’adresse de secours est marquée comme « validée ».  La validation des adresses garantit que l’adresse est légitime et qu’elle ne peut pas être modifiée après son attribution. 

Si vous définissez une adresse d’urgence à l’aide de la fonctionnalité de recherche de carte d’adresse dans le centre d’administration Teams, l’adresse est automatiquement marquée comme validée. Vous ne pouvez pas modifier une adresse de secours validée. Par conséquent, si le format ou la représentation de l’adresse change, vous devez créer une nouvelle adresse au format mis à jour.


## <a name="emergency-address-geo-codes"></a>Codes géographiques d’adresse de secours

Chaque adresse de secours peut être associée à un code géo (Latitude et longitude). Ces codes géographiques sont utilisés dans certains pays pour faciliter le routage des appels d’urgence avec des emplacements dynamiques. 

Si vous définissez une adresse d’urgence à l’aide de la fonctionnalité de recherche de carte d’adresse dans le centre d’administration Teams, le code géographique est automatiquement associé à une adresse de secours. Vous pouvez également associer des codes géographiques à une adresse si vous définissez l’adresse à l’aide de PowerShell. Toutefois, Microsoft vous recommande de créer des adresses de secours pour les plans d’appels à l’aide de la fonctionnalité de recherche de carte dans le centre d’administration Teams, afin de vous assurer que les adresses sont mises en forme, validées et disposant des codes géographiques appropriés.  

>[!Important]
>Pour attribuer un emplacement d’urgence à un identifiant réseau pour les appels d’urgence dynamiques, l’adresse de secours doit contenir un code géographique approprié.


## <a name="considerations-for-calling-plans"></a>Remarques relatives aux offres d’appels

Pour savoir si des plans d’appel sont disponibles dans votre région, consultez la rubrique [disponibilité du pays et de la région pour les offres d’appels](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).


### <a name="emergency-call-enablement"></a>Activation des appels d’urgence

Chaque utilisateur de plan d’appel est automatiquement activé pour les appels d’urgence et est tenu d’avoir une adresse de secours enregistrée associée à son numéro de téléphone. 

Lorsque l’emplacement doit être associé au numéro de téléphone dépend du pays/de la région :

- Aux États-Unis et au Canada, par exemple, un emplacement d’urgence est requis lorsqu’un numéro est attribué à un utilisateur.

- Pour les autres pays (par exemple, en Europe, Moyen Orient et Afrique (EMEA) : un emplacement d’urgence est requis lorsque vous recevez le numéro de téléphone d’Office 365 ou lorsqu’il est transféré à partir d’un autre fournisseur ou opérateur de services.

### <a name="dynamic-emergency-calling"></a>Appels d’urgence dynamiques

Les appels d’urgence dynamiques pour les plans d’appel Microsoft offrent la possibilité de configurer et d’acheminer les appels d’urgence en fonction de l’emplacement actuel du client Teams. La possibilité de procéder au routage automatique vers le point d’accès à la sécurité publique approprié (PSAPI) ou de notifier le personnel de votre support technique dépend du pays d’utilisation de l’utilisateur de teams.  

Pour les utilisateurs d’un plan d’appels, l’emplacement dynamique pour le routage des appels d’urgence est uniquement pris en charge aux États-Unis comme suit. (Pour plus d’informations sur les appels d’urgence dynamiques et le routage direct, voir [considérations relatives au routage direct](#considerations-for-direct-routing).

- Si un client teams pour une offre d’appels vers les États-Unis acquiert dynamiquement une adresse d’urgence à l’intérieur des États-Unis, cette adresse est utilisée pour le routage d’urgence au lieu de l’adresse enregistrée, et l’appel est automatiquement acheminé vers le PSAPI dans la zone de service de l’adresse.

- Si un client teams pour un membre d’un plan d’appels aux États-Unis n’achète pas dynamiquement une adresse d’urgence aux États-Unis, l’adresse d’urgence enregistrée est utilisée pour vous permettre d’effectuer un écran et de diriger l’appel. Toutefois, l’appel s’affiche pour déterminer si une adresse mise à jour est requise avant de connecter l’appelant au PSAPI approprié.

Aux États-Unis, vous devez configurer l’adresse civique qui fait partie des emplacements d’urgence attribués aux identifiants réseau, et inclure les codes géographiques associés. Pour plus d’informations, reportez-vous à [planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).


### <a name="emergency-call-routing"></a>Routage des appels d’urgence

Lorsque l’utilisateur d’une équipe appelle un numéro d’urgence, le routage de l’appel vers le PSAPI dépend des éléments suivants :

- Si l’adresse de secours est déterminée dynamiquement par le client Teams.

- Si l’adresse de secours correspond à l’adresse enregistrée associée au numéro de téléphone de l’utilisateur.

- Le réseau d’appels d’urgence de ce pays.

  **Aux États-Unis :**

  - Si un client teams se trouve dans un emplacement d’urgence dynamique défini par un client, les appels d’urgence de ce client sont automatiquement routés vers le PSAPI qui dessert cet emplacement géographique. 

  - Si un client Teams ne se trouve pas dans un emplacement d’urgence dynamique défini par le client, les appels d’urgence de ce client sont filtrés par un centre d’appels national pour déterminer l’emplacement de l’appelant avant de transférer l’appel vers le PSAPI qui dessert cet emplacement géographique.

  - Si un appelant n’est pas en mesure de mettre à jour son emplacement d’urgence vers le centre de filtrage, l’appel est transféré vers le PSAPI qui dessert l’adresse d’inscription de l’appelant.

  **Au Canada, en Irlande et au Royaume-Uni, les**appels d’urgence sont d’abord prédéfinis pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de répartition approprié. 

  **En France, en Allemagne et en Espagne**, les appels d’urgence sont dirigés directement vers le PSAPI qui dessert l’adresse d’urgence associée au numéro indépendamment de l’emplacement de l’appelant.

  Aux **Pays-Bas**, les appels d’urgence sont dirigés directement vers le PSAPI pour l’indicatif local du numéro indépendamment de l’emplacement de l’appelant.

  **En Australie**, les adresses de secours sont configurées et routées par le partenaire de transporteur.

  **Au Japon**, les appels d’urgence ne sont pas pris en charge.


Pour plus d’informations, consultez :

- [Forfaits d’appel](calling-plan-landing-page.md)

- [Différents types de numéros de téléphone utilisés pour les appels d’offre](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Conditions générales d’utilisation des appels d’urgence](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Éléments à prendre en compte pour le routage direct

Si les plans d’appel ne sont pas disponibles dans votre région ou si vous souhaitez conserver votre opérateur, envisagez le [routage direct](direct-routing-landing-page.md). Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md) et [gérer les stratégies d’acheminement des appels d’urgence](manage-emergency-call-routing-policies.md).

### <a name="emergency-call-enablement-and-configuration"></a>Activation et configuration des appels d’urgence

Vous devez définir des politiques d’appel d’urgence pour le routage direct des utilisateurs en utilisant le TeamsEmergencyCallRoutingPolicy pour définir des numéros d’urgence et la destination de routage associée. (Notez que les emplacements d’urgence inscrits ne sont pas pris en charge pour les utilisateurs de routage direct.)

Vous pouvez affecter une TeamsEmergencyCallRoutingPolicy à un compte d’utilisateur de routage direct de l’équipe, un site réseau ou les deux. Lorsqu’un client teams démarre ou modifie une connexion réseau, teams effectue une recherche sur le site réseau où se trouve le client comme suit :

- Si un TeamsEmergencyCallRoutingPolicy est associé au site, la stratégie de site est utilisée pour configurer les appels d’urgence.

- S’il n’y a aucun TeamsEmergencyCallRoutingPolicy associé au site, ou si le client est connecté à un site non défini, le TeamsEmergencyCallRoutingPolicy associé au compte d’utilisateur est utilisé pour configurer les appels d’urgence. 

- Si le client Teams ne peut pas obtenir de TeamsEmergencyCallRoutingPolicy, cela signifie que l’utilisateur n’est pas activé pour les appels d’urgence.

### <a name="dynamic-emergency-calling"></a>Appels d’urgence dynamiques

Les clients teams pour le routage direct peuvent acquérir une adresse de secours dynamique, qui peut être utilisée pour acheminer dynamiquement les appels en fonction de l’emplacement de l’appelant. Pour plus d’informations, voir [configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing"></a>Routage des appels d’urgence

Le TeamsEmergencyCallRoutingPolicy fait référence à une utilisation RTC en ligne, qui doit disposer de la configuration de routage directe appropriée pour acheminer correctement les appels d’urgence vers la ou les passerelles RTC appropriées. En particulier, vous devez vous assurer qu’il existe une OnlineVoiceRoute pour la chaîne de numérotation d’urgence. Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md). 

(Remarque : les clients teams peuvent ajouter le signe « + » devant les numéros d’urgence de la même manière que le client Skype entreprise, c’est-à-dire + 911. Ce comportement sera modifié au cours des prochains mois de sorte que les appels d’urgence d’équipes n’envoient plus le numéro « + » précédant le numéro. c’est-à-dire 911.)

La possibilité d’acheminer dynamiquement les appels d’urgence pour les utilisateurs de routage direct varie en fonction du réseau d’appel d’urgence dans un pays donné. Deux solutions sont disponibles :

- Prestataires de services de routage d’urgence (US uniquement) 
- Applications d’identification d’emplacement d’urgence (ELIN)

#### <a name="emergency-routing-service-providers"></a>Prestataires de services de routage d’urgence

Aux États-Unis, de nombreux fournisseurs de services de routage d’urgence (ERSPs) peuvent automatiquement diriger les appels d’urgence en fonction de l’emplacement de l’appelant.

- Si un fournisseur de service de routage d’urgence est intégré à un déploiement de routage directe, les appels d’urgence disposant d’un emplacement d’acquisition dynamique seront automatiquement routés vers le point d’accès de sécurité publique (PSAPI) qui dessert cet emplacement.

-  Les appels d’urgence sans emplacement acquis de manière dynamique sont d’abord prédéfinis pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de répartition approprié en fonction de l’emplacement mis à jour.

Pour plus d’informations, reportez-vous à la rubrique [contrôle de bordure de session certifié pour le routage direct](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-elin-applications"></a>Applications d’identification d’emplacement d’urgence (ELIN)

Les contrôleurs de frontière de session (SBCs) peuvent inclure des applications d’identification d’emplacement d’urgence (ELIN). Si une application SBC ELIN est intégrée à un déploiement de routage direct, vous devez configurer les adresses d’urgence et les numéros de téléphone associés dans l’application ELIN, puis télécharger les enregistrements ELIN dans la base de données d’appel d’urgence du RTC correspondant.  Les emplacements d’urgence des équipes avec un identificateur ELIN doivent correspondre à ceux de l’application ELIN.

Lorsqu’un appel d’urgence avec un emplacement acquis dynamiquement est routé vers l’SBC appropriée, l’application ELIN :

- Analyse l’emplacement d’urgence de l’appelant.
- Correspond à l’emplacement de l’enregistrement ELIN.
- Remplace le numéro d’appel d’urgence par le numéro de téléphone ELIN.
- Route l’appel vers le PSAPI qui dessert cet emplacement, puis les répartiteurs obtiennent l’emplacement à partir de l’enregistrement ELIN téléchargé.

Lors d’un appel vers le numéro d’urgence, l’application ELIN effectue l’opération inverse de la substitution du numéro par l’appelant initial. 

Pour plus d’informations, reportez-vous à la rubrique [contrôle de bordure de session certifié pour le routage direct](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notification du centre de sécurité

La notification du support technique est disponible avec les plans d’appel Microsoft et le routage direct du système téléphonique.

Vous utilisez le TeamsEmergencyCallingPolicy pour configurer les personnes qui doivent être averties lors d’un appel d’urgence et la façon dont elles sont notifiées : discussions uniquement, conférences en ligne et désactivées, ou en mode de conférences et désactivées, mais avec la possibilité d’activer le son.  Vous pouvez également spécifier le numéro RTC externe d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence. 

Un TeamsEmergencyCallingPolicy peut être accordé à un compte d’utilisateur Teams, affecté à un site réseau, ou les deux.  Lorsqu’un client teams démarre ou modifie une connexion réseau, teams effectue une recherche sur le site réseau où se trouve le client :

- Si un TeamsEmergencyCallingPolicy est associé à un site réseau, la stratégie de site est utilisée pour configurer la notification du support technique.

- S’il n’y a aucun TeamsEmergencyCallingPolicy associé au site, ou si le client est connecté à un site non défini, le TeamsEmergencyCallingPolicy associé au compte d’utilisateur est utilisé pour configurer la notification de bureau de sécurité.  

- Si le client teams n’est pas en mesure d’obtenir un TeamsEmergencyCallingPolicy, cela signifie que l’utilisateur n’est pas activé pour la notification Security Desk.

Au cours d’un appel d’urgence, un support technique est retenu dans le cadre de l’appel et l’utilisateur du support technique est contrôlé en fonction du TeamsEmergencyCallingPolicy. Une discussion de groupe est lancée pour chaque membre du support technique et l’emplacement de l’appelant d’urgence est partagé par le biais d’une notification de message importante.  Si une option de conférence est configurée dans le cadre de la stratégie, chaque utilisateur du support technique peut également être appelé dans le cadre de la Conférence.

    
## <a name="related-topics"></a>Sujets associés

- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage des appels d’urgence](manage-emergency-call-routing-policies.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Affectation ou modification d’un emplacement d’urgence pour votre utilisateur](assign-change-emergency-location-user.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
