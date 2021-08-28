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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: En savoir plus sur les appels d’urgence, y compris les informations sur les adresses de secours, le routage des appels d’urgence et les appels d’urgence dynamiques.
ms.openlocfilehash: 43ab5bcec3e0831e291ffc28608a1d9c270c1739
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594406"
---
# <a name="manage-emergency-calling"></a>Gestion des appels d’urgence

Cet article décrit des concepts que vous devez connaître pour gérer les appels d’urgence, notamment des informations sur les adresses de secours, les adresses de secours dynamiques et le &mdash; routage des appels d’urgence. Cet article utilise la terminologie suivante :

- **Adresse d’urgence** : adresse municipale à l’adresse physique ou &mdash; street street du site d’activité de votre organisation.

  Par exemple, l’adresse  *12345 North Main Street, Redmond, WA 98052* est utilisée pour router les appels d’urgence vers les autorités de répartition appropriées et aider à trouver l’appelant.

- **Lieu** : généralement l’étage, le bâtiment, l’aile ou le numéro du bureau. L’emplacement est associé à une adresse de secours pour donner un emplacement plus exact dans un bâtiment. Le nombre de lieux associés à une adresse de secours peut être illimité. Par exemple, si votre organisation possède plusieurs bâtiments, vous pouvez inclure les informations d’endroit pour chaque bâtiment et pour chaque étage de chaque bâtiment.  

- **Emplacement d’urgence** : un emplacement est une adresse géographique &mdash; éventuellement disponible. Si votre entreprise possède plusieurs emplacements physiques, il est probable que vous aurez besoin de plusieurs emplacements d’urgence. 

  Lorsque vous créez une adresse de secours, un ID d’emplacement unique est automatiquement créé pour cette adresse.  Si vous ajoutez un emplacement à une adresse de secours, par exemple, si vous ajoutez un étage à une adresse de bâtiment, un ID d’emplacement est créé pour la combinaison de l’adresse de secours et &mdash; &mdash; de l’emplacement.  Dans cet exemple, il y a deux ID d’emplacement : l’un pour l’adresse géographique ; un pour l’adresse civile jointe et l’endroit associé.

  Lorsque vous affectez un emplacement d’urgence à un utilisateur ou un site, il s’agit de cet ID d’emplacement unique associé à l’utilisateur ou au site.

- **Adresse enregistrée** - Adresse d’urgence affectée à chaque utilisateur du plan d’appels on parle parfois d’adresse de secours statique ou d’adresse de l’enregistrement.  (Les adresses enregistrées ne s’appliquent pas aux utilisateurs du routage direct.)

Vous créez des adresses d’urgence pour les utilisateurs d’un plan d’appels à l’aide du Teams d’administration.  

>[!Note]
>La gestion des appels d’urgence varie selon que vous utilisez des plans d’appel Système téléphonique ou Système téléphonique un routage direct pour votre connectivité RSTN. Ces considérations sont décrites dans cet article.

## <a name="emergency-address-validation"></a>Validation d’adresse d’urgence

Pour attribuer une adresse de secours à un utilisateur ou à un identificateur réseau, vous devez vous assurer que l’adresse de secours est marquée comme « validée ».  La validation d’adresse garantit la légitimité de l’adresse et ne peut pas être modifiée une fois qu’elle a été affectée. 

Si vous définissez une adresse de secours à l’aide de la fonctionnalité de recherche de carte d’adresses du Centre d’administration Teams, l’adresse est automatiquement marquée comme validée. Vous ne pouvez pas modifier une adresse de secours validée. Par conséquent, si le format ou la représentation de l’adresse change, vous devez créer une adresse au format mis à jour.


## <a name="emergency-address-geo-codes"></a>Codes géographiques des adresses de secours

Un code géographique (latitude et longitude) peut être associé à chaque adresse de secours. Ces codes géographiques sont utilisés dans certains pays pour aider au routage des appels d’urgence à l’aide d’emplacements dynamiques. 

Si vous définissez une adresse de secours à l’aide de la fonctionnalité de recherche de carte d’adresses du Centre d’administration Teams, le code géographique est automatiquement associé à une adresse de secours. Vous pouvez également associer des codes géographiques à une adresse si vous définissez l’adresse à l’aide de PowerShell. Toutefois, Microsoft recommande de créer des adresses d’urgence pour le plan d’appel à l’aide de la fonctionnalité de recherche de carte du Centre d’administration Teams, qui garantit que les adresses sont formatées, validées et disposent des codes géographiques appropriés.  

>[!Important]
>Pour affecter un emplacement d’urgence à un identificateur réseau pour les appels d’urgence dynamiques, l’adresse de secours doit contenir un code géographique approprié.


## <a name="considerations-for-calling-plans"></a>Considérations pour les forfaits d’appels

Pour savoir si les forfaits d’appels sont disponibles dans votre région, consultez la disponibilité du pays et de [la région pour les forfaits d’appels.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


### <a name="emergency-call-enablement"></a>Enablement d’appel d’urgence

Chaque utilisateur d’un plan d’appels est automatiquement activé pour les appels d’urgence et une adresse d’urgence enregistrée doit être associée à son numéro de téléphone affecté. 

Lorsque l’emplacement doit être associé au numéro de téléphone dépend du pays/de la région :

- Aux États-Unis et au Canada, par exemple, un emplacement d’urgence est nécessaire lorsqu’un numéro est attribué à un utilisateur.

- Pour d’autres pays, comme en Europe, au Moyen Orient et en Afrique (EMEA), un emplacement d’urgence est requis lorsque vous obtenez le numéro de téléphone auprès d’Microsoft 365 ou d’Office 365, ou lorsqu’il est transféré à partir d’un autre opérateur ou fournisseur de services.

### <a name="dynamic-emergency-calling"></a>Appels d’urgence dynamiques

Les appels d’urgence dynamiques pour les plans d’appel Microsoft offrent la possibilité de configurer et de router des appels d’urgence en fonction de l’emplacement actuel du client Teams d’urgence. La possibilité d’assurer un routage automatique vers le point de réponse de sécurité publique approprié (PUBLIC Safety Answering Point) ou d’informer le personnel du service de sécurité varie en fonction du pays d’utilisation de l Teams utilisateur.  

Pour les utilisateurs du plan d’appels, l’emplacement dynamique pour l’acheminement des appels d’urgence est pris en charge uniquement aux États-Unis comme suit. (Pour plus d’informations sur les appels d’urgence dynamiques et le routage direct, voir [Considérations pour le routage direct.](#considerations-for-direct-routing)

- Si un client Teams pour un utilisateur du plan d’appels des États-Unis acquiert dynamiquement une adresse d’urgence aux États-Unis, cette adresse est utilisée pour le routage d’urgence au lieu de l’adresse enregistrée, et l’appel est automatiquement acheminé vers le numéro DUP DANS la zone de service de l’adresse.

- Si un client Teams pour un utilisateur du plan d’appels des États-Unis n’acquiert pas dynamiquement une adresse d’urgence aux États-Unis, l’adresse de secours enregistrée est utilisée pour écranr et router l’appel. Toutefois, l’appel sera filpé pour déterminer si une adresse mise à jour est requise avant de connecter l’appelant au système TÉLÉPHONIQUE APPROPRIÉ.

Aux États-Unis, vous devez configurer l’adresse géographique qui fait partie des emplacements d’urgence affectés aux identificateurs réseau et inclure les &mdash; codes géographiques associés. Pour plus d’informations, voir [Planifier et configurer des appels d’urgence dynamiques.](configure-dynamic-emergency-calling.md)


### <a name="emergency-call-routing"></a>Routage d’appel d’urgence

Lorsqu’un Teams plan d’appels compose un numéro d’urgence, la façon dont l’appel est acheminé vers le centre d’appels PUBLIC dépend des informations suivantes :

- Si l’adresse de secours est déterminée dynamiquement par le Teams client.

- Si l’adresse de secours est l’adresse enregistrée associée au numéro de téléphone de l’utilisateur.

- Le réseau d’appels d’urgence de ce pays.

  **Aux États-Unis :**

  - Si un client Teams est situé dans un emplacement d’urgence dynamique défini par le client, les appels d’urgence en provenance de ce client sont automatiquement acheminés vers le client CENTRE.PUBLIC qui sert cet emplacement géographique. 

  - Si un client Teams n’est pas situé dans un emplacement d’urgence dynamique défini par le client, les appels d’urgence en provenance de ce client sont filpés par un centre d’appels national pour déterminer l’emplacement de l’appelant avant de transférer l’appel vers le centre CENTRE.

  - Si un appelant n’est pas en mesure de mettre à jour son emplacement d’urgence dans le centre de sélection, l’appel est transféré vers le centre de sélection DUP au service de l’adresse enregistrée de l’appelant.

  **Au Canada, en Irlande** et au Royaume-Uni, les appels d’urgence sont d’abord filés pour déterminer l’emplacement actuel de l’utilisateur avant de le connecter au centre d’urgence approprié. 

  **En France, en Allemagne** et en Espagne, les appels d’urgence sont acheminés directement vers le centre de données PUBLIC PUBLIC (PUBLICP) et l’adresse d’urgence associée au numéro, quel que soit l’emplacement de l’appelant.

  **Aux Pays-Bas,** les appels d’urgence sont acheminés directement vers le centre CENTRE DNS pour l’code de la zone locale du numéro, quel que soit l’emplacement de l’appelant.

  **En Australie,** les adresses d’urgence sont configurées et acheminées par le partenaire de l’opérateur.

  **Au Japon, les** appels d’urgence ne sont pas pris en charge.


Pour plus d’informations, consultez :

- [Forfaits d’appel](calling-plan-landing-page.md)

- [Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Considérations pour le routage direct

Si les forfaits d’appels ne sont pas disponibles dans votre région ou si vous voulez conserver votre opérateur existant, vous pouvez envisager un [routage direct.](direct-routing-landing-page.md) Pour plus d’informations, voir [Configurer le routage direct et](direct-routing-configure.md) Gérer les stratégies de [routage des appels d’urgence.](manage-emergency-call-routing-policies.md)

### <a name="emergency-call-enablement-and-configuration"></a>Activer et configuration des appels d’urgence

Vous devez définir des stratégies d’appel d’urgence pour les utilisateurs du routage direct à l’aide d’une stratégie de routage d’appel d’urgence Teams (TeamsEmergencyCallRoutingPolicy) pour définir les numéros d’urgence et leur destination de routage associée. (Notez que les emplacements d’urgence enregistrés ne sont pas pris en charge pour les utilisateurs du routage direct.)

Vous pouvez affecter une stratégie de routage des appels d’urgence à un compte d’Teams d’utilisateur de routage direct, à un site réseau ou aux deux. Lorsqu’un client Teams démarre ou modifie une connexion réseau, Teams effectue une recherche sur le site réseau où se trouve le client comme suit :

- Si une stratégie de routage d’appel d’urgence est associée au site, la stratégie de site est utilisée pour configurer les appels d’urgence.

- Si aucune stratégie de routage des appels d’urgence n’est associée au site, si le client est connecté sur un site non défini, ou si le numéro à composer ne correspond à aucun des numéros d’urgence définis dans la stratégie de routage des appels d’urgence associée au site, la stratégie de routage des appels d’urgence associée au compte d’utilisateur est utilisée pour configurer les appels d’urgence. 

- Si le Teams n’est pas en mesure d’obtenir une stratégie de routage des appels d’urgence, l’utilisateur n’est pas activé pour les appels d’urgence.

### <a name="dynamic-emergency-calling"></a>Appels d’urgence dynamiques

Teams clients pour les utilisateurs du routage direct peuvent acquérir une adresse d’urgence dynamique, qui peut être utilisée pour router dynamiquement les appels en fonction de l’emplacement de l’appelant. Pour plus d’informations, voir [Configurer les appels d’urgence dynamiques.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing"></a>Routage d’appel d’urgence

La stratégie de routage d’appel d’urgence fait référence à une utilisation PSTN en ligne, qui doit avoir la configuration de routage direct appropriée pour router correctement les appels d’urgence vers la ou les passerelles RSTN appropriées. Vous devez notamment vous assurer qu’il existe une chaîne de numérotation d’urgence sur OnlineVoiceRoute. Pour plus d’informations, [voir Configurer le routage direct.](direct-routing-configure.md) 

(Remarque : Teams clients ajoutent le signe « + » devant les numéros d’urgence de la même manière que Skype Entreprise client ; c’est-à-dire, le signe +911. Ce comportement sera modifié dans les mois à venir afin que les Teams d’urgence n’envoient plus de « + » avant le numéro . autrement dit, 911.)

La possibilité de router dynamiquement les appels d’urgence pour les utilisateurs du routage direct varie en fonction du réseau d’appels d’urgence dans un pays donné. Deux solutions sont disponibles :

- Fournisseurs de services de routage d’urgence (États-Unis uniquement) 
- Applications de passerelle ELIN (Emergency Location Identification Number)

#### <a name="emergency-routing-service-providers"></a>Fournisseurs de services de routage d’urgence

Aux États-Unis, il existe de nombreux fournisseurs de services de routage d’urgence certifiés qui peuvent router automatiquement les appels d’urgence en fonction de l’emplacement de l’appelant.

- Si un fournisseur de services de routage d’urgence est intégré à un déploiement de routage direct, les appels d’urgence ayant acquis dynamiquement un emplacement sont automatiquement acheminés vers le point de réponse de sécurité publique (PUBLIC Safety Answering Point) de cet emplacement.

-  Les appels d’urgence sans emplacement dynamiquement acquis sont d’abord filés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre d’urgence approprié en fonction de l’emplacement mis à jour.

Pour plus d’informations, [voir Contrôleurs de session en bordure certifiés pour le routage direct.](direct-routing-border-controllers.md)


#### <a name="emergency-location-identification-number-elin-applications"></a>Applications ELIN (Emergency Location Identification Number)

Les contrôleurs de session border Controller (SBCs) peuvent inclure des applications ELIN (Emergency Location Identification Number). Si une application ELIN SBC est intégrée dans un déploiement de routage direct, vous devez configurer les adresses d’urgence et les numéros de téléphone associés dans l’application ELIN, puis charger les enregistrements ELIN dans la base de données d’appels d’urgence dans le réseau PSTN respectif.  Teams emplacements d’urgence avec un identificateur ELIN doivent correspondre à ceux de l’application ELIN.

Lorsqu’un appel d’urgence ayant été acquis dynamiquement est acheminé vers le SBC approprié, l’application ELIN :

- L’emplacement d’urgence de l’appelant est sondé.
- Fait correspondance l’emplacement à un enregistrement ELIN.
- Remplace le numéro de téléphone de l’appelant par le numéro de téléphone ELIN.
- Route l’appel vers le service CENTRE.PUBLIC (PUBLICP) dans cet emplacement, puis les régulateurs obtiennent l’emplacement à partir de l’enregistrement ELIN chargé.

Lors d’un appel de retour au numéro d’urgence, l’application ELIN fera l’inverse du remplacement de numéro appelé celui de l’appelant d’urgence d’origine. 

Pour plus d’informations, [voir Contrôleurs de session en bordure certifiés pour le routage direct.](direct-routing-border-controllers.md)


## <a name="security-desk-notification"></a>Notification du service de sécurité

La notification du service de sécurité est disponible avec les plans d’appel Microsoft et Système téléphonique routage direct.

Vous utilisez une stratégie d’appel d’urgence Teams (TeamsEmergencyCallingPolicy) pour configurer les personnes devant être informées pendant un appel d’urgence et la manière dont elles sont informées : conversation uniquement, conférence en conférence et mise en sourdine, ou conférence en cours et mise en sourdine, mais avec la possibilité d’activer le son.  Vous pouvez également spécifier un numéro PSTN externe d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence. 

Une stratégie d’appel d’urgence peut être octroyée à un Teams utilisateur, à un site réseau ou aux deux.  Lorsqu’Teams client démarre ou modifie une connexion réseau, Teams effectue une recherche sur le site réseau où se trouve le client :

- Si une stratégie d’appel d’urgence est associée à un site réseau, la stratégie de site est utilisée pour configurer les notifications du service de sécurité.

- Si aucune stratégie d’appel d’urgence n’est associée au site, ou si le client est connecté à un site non indéfini, la stratégie d’appel d’urgence associée au compte d’utilisateur est utilisée pour configurer les notifications du service de sécurité.  

- Si le Teams n’est pas en mesure d’obtenir une stratégie d’appel d’urgence, l’utilisateur n’est pas activé pour recevoir une notification du service de sécurité.

Pendant un appel d’urgence, un service de sécurité est téléphoniquement appelé et l’expérience de l’utilisateur du service de sécurité est contrôlée en fonction de Teams d’appel d’urgence. Une conversation de groupe commence avec chaque membre du service de sécurité, et l’emplacement de l’appelant d’urgence est partagé via une notification de message importante.  Si une option de conférence est configurée dans le cadre de la stratégie, chaque utilisateur du service de sécurité est appelé en outre dans le cadre de la conférence.

    
## <a name="related-topics"></a>Rubriques connexes

- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage d’appel d’urgence ](manage-emergency-call-routing-policies.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Affectation ou modification d’un emplacement d’urgence pour votre utilisateur](assign-change-emergency-location-user.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
