---
title: Planifier et gérer les appels d’urgence
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
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
description: Découvrez les appels d’urgence, y compris les informations sur les adresses d’urgence, le routage des appels d’urgence et les appels d’urgence dynamiques.
ms.openlocfilehash: 2118bfd3f380ac5e5e2773f1f4ccdc703332893a
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606563"
---
# <a name="manage-emergency-calling"></a>Gérer les appels d’urgence

Cet article décrit les concepts que vous devez connaître pour gérer les appels&mdash;d’urgence, notamment des informations sur les adresses d’urgence, les adresses d’urgence dynamiques et le routage des appels d’urgence. Cet article utilise la terminologie suivante :

- **Adresse d’urgence** : adresse civique de l’adresse&mdash;physique ou postale d’un lieu d’affaires pour votre organisation.

  Par exemple, l’adresse *12345 North Main Street, Redmond, WA 98052* est utilisée pour acheminer les appels d’urgence aux autorités de répartition appropriées et pour aider à localiser l’appelant d’urgence.

- **Emplacement** : généralement un étage, un bâtiment, une aile ou un numéro de bureau. L’emplacement est associé à une adresse d’urgence pour donner un emplacement plus précis au sein d’un bâtiment. Vous pouvez avoir un nombre illimité d’emplacements associés à une adresse d’urgence. Par exemple, si votre organisation a plusieurs bâtiments, vous souhaiterez peut-être inclure des informations de lieu pour chaque bâtiment et chaque étage de chaque bâtiment.

- **Emplacement d’urgence** : un emplacement est une adresse&mdash;civique avec un emplacement facultatif. Si votre entreprise a plusieurs emplacements physiques, il est probable que vous aurez besoin de plusieurs emplacements d’urgence.

  Lorsque vous créez une adresse d’urgence, un ID d’emplacement unique est automatiquement créé pour cette adresse. Si vous ajoutez un emplacement à une adresse&mdash;d’urgence, par exemple, si vous ajoutez un étage à une adresse&mdash;de bâtiment, un ID d’emplacement est créé pour la combinaison de l’adresse d’urgence et du lieu.  Dans cet exemple, il y aura deux ID d’emplacement : un pour l’adresse civique ; pour l’adresse civique jointe et le lieu associé.

  Lorsque vous affectez un emplacement d’urgence à un utilisateur ou à un site, il s’agit de cet ID d’emplacement unique associé à l’utilisateur ou au site.

- **Adresse inscrite** : adresse d’urgence affectée à chaque utilisateur. Une adresse inscrite est parfois appelée adresse d’urgence statique ou adresse d’enregistrement. (Actuellement, les adresses inscrites ne sont pas prises en charge pour le routage direct. Revenez bientôt à la recherche des mises à jour.)

>[!Note]
>Il existe certaines différences dans la façon dont vous gérez les appels d’urgence, selon que vous utilisez des forfaits d’appels Microsoft, Operator Connect, Fournisseur de connectivité mobile (préversion publique) ou le routage direct pour votre [connectivité RTC](pstn-connectivity.md). Ces considérations sont décrites dans cet article.

## <a name="emergency-address-validation"></a>Validation d’adresse d’urgence

Pour affecter une adresse d’urgence à un utilisateur ou à un identificateur réseau, vous devez vous assurer que l’adresse d’urgence est marquée comme « validée ». La validation d’adresse garantit que l’adresse est légitime et qu’elle ne peut pas être modifiée après son affectation.

Si vous définissez une adresse d’urgence à l’aide de la fonctionnalité de recherche de carte d’adresses dans le Centre d’administration Teams, l’adresse est automatiquement marquée comme validée. Étant donné que vous ne pouvez pas modifier une adresse&mdash;d’urgence validée si le format ou la représentation de l’adresse change, vous devez créer une adresse avec le format mis à jour.

## <a name="emergency-address-geo-codes"></a>Codes géographiques d’adresse d’urgence

Un code géographique (latitude et longitude) peut être associé à chaque adresse d’urgence. Ces codes géographiques sont utilisés dans certains pays pour faciliter le routage des appels d’urgence avec des emplacements dynamiques.

Si vous définissez une adresse d’urgence à l’aide de la fonctionnalité de recherche de carte d’adresses dans le Centre d’administration Teams, le code géographique est automatiquement associé à une adresse d’urgence. Vous pouvez également associer des codes géographiques à une adresse si vous définissez l’adresse à l’aide de PowerShell.

Microsoft vous recommande de créer des adresses d’urgence à l’aide de la fonctionnalité de recherche de carte dans le Centre d’administration Teams, ce qui garantit que les adresses sont mises en forme, validées et ont les codes géographiques appropriés.

>[!Important]
>Pour affecter un emplacement d’urgence à un identificateur réseau pour les appels d’urgence dynamiques, l’adresse d’urgence doit contenir un code géographique approprié.

## <a name="considerations-for-calling-plans"></a>Considérations relatives aux forfaits d’appels

Les sections suivantes décrivent comment gérer les appels d’urgence pour les utilisateurs du plan d’appel Microsoft. Pour savoir si les forfaits d’appels Microsoft constituent la bonne solution pour votre entreprise, consultez les [options de connectivité RTC](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-calling-plans"></a>Activation des appels d’urgence pour les forfaits d’appels

Chaque utilisateur du plan d’appel est automatiquement activé pour les appels d’urgence et doit avoir une adresse d’urgence inscrite associée à son numéro de téléphone affecté.

Lorsque l’emplacement est associé au numéro de téléphone dépend du pays/de la région :

- Dans le États-Unis et au Canada, par exemple, un emplacement d’urgence est requis lorsqu’un numéro est attribué à un utilisateur.

- Pour d’autres pays&mdash;comme l’Europe, le Moyen-Orient et l’Afrique (EMEA),&mdash; un emplacement d’urgence est requis lorsque vous obtenez le numéro de téléphone de Microsoft 365 ou lorsqu’il est transféré à partir d’un autre fournisseur de services ou opérateur.

### <a name="dynamic-emergency-calling-for-calling-plans"></a>Appels d’urgence dynamiques pour les forfaits d’appels

Les appels d’urgence dynamiques pour les forfaits d’appels permettent de configurer et de router les appels d’urgence en fonction de l’emplacement actuel du client Teams. La possibilité d’effectuer un routage automatique vers le point de réponse de sécurité publique approprié (PSAP) ou d’informer le personnel du bureau de sécurité varie en fonction du pays d’utilisation de l’utilisateur Teams.

L’emplacement dynamique pour le routage des appels d’urgence est pris en charge dans le États-Unis comme suit.

- Si un client Teams pour un États-Unis forfait d’appels acquiert dynamiquement une adresse d’urgence dans le États-Unis, cette adresse est utilisée pour le routage d’urgence au lieu de l’adresse inscrite, et l’appel est automatiquement routée vers le PSAP dans la zone de service de l’adresse.

- Si un client Teams pour un utilisateur de plan d’appel États-Unis n’acquiert pas dynamiquement d’adresse d’urgence dans le États-Unis, l’adresse d’urgence inscrite est utilisée pour faciliter l’écran et l’acheminement de l’appel. Toutefois, l’appel est filtré pour déterminer si une adresse mise à jour est requise avant de connecter l’appelant au psap approprié.

L’emplacement dynamique pour le routage des appels d’urgence est pris en charge au Canada comme dans le États-Unis à l’exception suivante : tous les appels d’urgence seront examinés à l’échelle nationale avant d’être transférés au PSAP.

Pour plus d’informations, consultez [Planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-calling-plans"></a>Routage des appels d’urgence pour les forfaits d’appels

Lorsqu’un utilisateur du plan d’appel Teams compose un numéro d’urgence, la façon dont l’appel est acheminé vers le psap dépend des éléments suivants :

- Indique si l’adresse d’urgence est déterminée dynamiquement par le client Teams.

- Indique si l’adresse d’urgence est l’adresse inscrite associée au numéro de téléphone de l’utilisateur.

- Le réseau d’appel d’urgence de ce pays.

Par exemple :

**Dans le États-Unis :**

- Si un client Teams se trouve à un emplacement d’urgence dynamique défini par le locataire, les appels d’urgence de ce client sont automatiquement acheminés vers le PSAP qui dessert cet emplacement géographique.

- Si un client Teams n’est pas situé à un emplacement d’urgence dynamique défini par le locataire, les appels d’urgence de ce client sont filtrés par un centre d’appels national pour déterminer l’emplacement de l’appelant avant de transférer l’appel vers le PSAP qui dessert cet emplacement géographique.

- Si un appelant d’urgence ne parvient pas à mettre à jour son emplacement d’urgence vers le centre de dépistage, l’appel est transféré vers le PSAP qui dessert l’adresse enregistrée de l’appelant.

**Au Canada, en Irlande et au Royaume-Uni, les** appels d’urgence sont d’abord examinés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de répartition approprié.

**En France, en Allemagne et en Espagne**, les appels d’urgence sont acheminés directement vers le PSAP qui dessert l’adresse d’urgence associée au numéro, quel que soit l’emplacement de l’appelant.

**Aux Pays-Bas, les** appels d’urgence sont acheminés directement vers le PSAP pour l’indicatif régional du numéro, quel que soit l’emplacement de l’appelant.

**En Australie**, les adresses d’urgence sont configurées et routées par le partenaire opérateur.

**Au Japon**, les appels d’urgence ne sont pas pris en charge.

Pour plus d’informations, consultez :

- [Forfaits d’appel](calling-plan-landing-page.md)
- [Configurer des forfaits d'appels](set-up-calling-plans.md)
- [Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Considérations relatives à Operator Connect

Les sections suivantes décrivent comment gérer les appels d’urgence pour les utilisateurs Operator Connect. Pour savoir si Operator Connect est la solution appropriée pour votre entreprise, consultez les [options de connectivité RTC](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-operator-connect"></a>Activation des appels d’urgence pour Operator Connect

Chaque utilisateur Operator Connect est automatiquement activé pour les appels d’urgence. Les appels d’urgence sont acheminés automatiquement vers le transporteur Operator Connect pour un numéro donné.

La possibilité pour un administrateur client de définir l’adresse inscrite d’un utilisateur Operator Connect dépend des fonctionnalités affectées au numéro lorsque l’opérateur les charge dans un inventaire de clients. En fonction de ce paramètre, l’administrateur client peut ou non être requis&mdash;ou en mesure&mdash;de définir, modifier ou supprimer l’emplacement d’urgence d’un utilisateur.

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Appel d’urgence dynamique pour Operator Connect

Les appels d’urgence dynamiques pour Operator Connect permettent de configurer et de router les appels d’urgence en fonction de l’emplacement actuel du client Teams. La possibilité d’effectuer un routage automatique vers le point de réponse de sécurité publique approprié (PSAP) ou d’informer le personnel du bureau de sécurité varie en fonction du pays d’utilisation de l’utilisateur Teams.

L’emplacement dynamique pour le routage des appels d’urgence est pris en charge dans le États-Unis comme suit.

- Si un client Teams pour un États-Unis’utilisateur acquiert dynamiquement une adresse d’urgence dans le États-Unis, cette adresse est utilisée pour le routage d’urgence au lieu de l’adresse inscrite, et l’appel est automatiquement routée vers le PSAP dans la zone de service de l’adresse.

- Si un client Teams pour un États-Unis utilisateur n’acquiert pas dynamiquement d’adresse d’urgence dans le États-Unis, l’adresse d’urgence inscrite est utilisée pour faciliter l’écran et le routage de l’appel. Toutefois, l’appel est filtré pour déterminer si une adresse mise à jour est requise avant de connecter l’appelant au psap approprié.

L’emplacement dynamique pour le routage des appels d’urgence est pris en charge au Canada comme dans le États-Unis, à l’exception des exceptions suivantes : tous les appels d’urgence seront examinés à l’échelle nationale avant d’être transférés au PSAP.

Pour plus d’informations, consultez [Planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-operator-connect"></a>Routage des appels d’urgence pour Operator Connect

Lorsqu’un utilisateur Teams Operator Connect compose un numéro d’urgence, la façon dont l’appel est acheminé vers le psap dépend des éléments suivants :

- Indique si l’adresse d’urgence est déterminée dynamiquement par le client Teams.

- Indique si l’adresse d’urgence est l’adresse inscrite associée au numéro de téléphone de l’utilisateur.

- Le réseau d’appel d’urgence de ce pays.

- Dans les États-Unis et au Canada, le routage dynamique fait partie du service du transporteur. Vous n’avez pas besoin de vous procurer ce service auprès d’un autre fournisseur de services.

- Si un client Teams se trouve à un emplacement d’urgence dynamique défini par le locataire :
  - Dans le États-Unis, les appels d’urgence de ce client sont automatiquement acheminés vers le PSAP qui dessert cet emplacement géographique.
  - Au Canada, tous les appels d’urgence seront examinés par un centre d’appels national avant de transférer l’appel au PSAP qui dessert cet emplacement géographique.

- Si un client Teams n’est pas situé à un emplacement d’urgence dynamique défini par le locataire, les appels d’urgence de ce client sont filtrés par un centre d’appels national pour déterminer l’emplacement de l’appelant avant de transférer l’appel vers le PSAP qui dessert cet emplacement géographique.

- Si un appelant d’urgence ne parvient pas à mettre à jour son emplacement d’urgence vers le centre de dépistage, l’appel est transféré vers le PSAP qui dessert l’adresse enregistrée de l’appelant.

## <a name="considerations-for-operator-connect-mobile"></a>Considérations relatives à Fournisseur de connectivité mobile

Les sections suivantes décrivent comment gérer les appels d’urgence pour Fournisseur de connectivité mobile utilisateurs. Pour savoir si Fournisseur de connectivité mobile est la solution adaptée à votre entreprise, consultez les [options de connectivité RTC](pstn-connectivity.md).

**Fournisseur de connectivité mobile est une préversion publique.**

### <a name="emergency-call-enablement-for-operator-connect-mobile"></a>Activation des appels d’urgence pour Fournisseur de connectivité mobile

Chaque Fournisseur de connectivité mobile utilisateur est automatiquement activé pour les appels d’urgence. Les appels d’urgence sont acheminés automatiquement vers le transporteur Fournisseur de connectivité mobile pour un numéro donné.

La possibilité pour un administrateur client de définir l’adresse inscrite pour un utilisateur Fournisseur de connectivité mobile dépend des fonctionnalités affectées au numéro lorsque l’opérateur les charge dans un inventaire de clients. En fonction de ce paramètre, l’administrateur client peut ou non être requis ou en mesure de définir, modifier ou supprimer l’emplacement d’urgence d’un utilisateur.

Lorsque des appels sont effectués via le numéroteur natif du smartphone compatible SIM, votre opérateur peut utiliser les coordonnées géographiques ou la tour de cellule qui gère l’appel à un emplacement d’urgence approximatif pour obtenir de l’aide.

### <a name="dynamic-emergency-calling-for-operator-connect-mobile"></a>Appels d’urgence dynamiques pour Fournisseur de connectivité mobile

Les appels d’urgence dynamiques pour Operator Connect permettent de configurer et de router les appels d’urgence en fonction de l’emplacement actuel du client Teams. La possibilité d’effectuer un routage automatique vers le point de réponse de sécurité publique approprié (PSAP) ou d’informer le personnel du bureau de sécurité varie en fonction du pays d’utilisation de l’utilisateur Teams.

L’emplacement dynamique pour le routage des appels d’urgence est pris en charge dans le États-Unis comme suit.

- Si un client Teams pour un États-Unis’utilisateur acquiert dynamiquement une adresse d’urgence dans le États-Unis, cette adresse est utilisée pour le routage d’urgence au lieu de l’adresse inscrite, et l’appel est automatiquement routée vers le PSAP dans la zone de service de l’adresse.

- Si un client Teams pour un États-Unis utilisateur n’acquiert pas dynamiquement d’adresse d’urgence dans le États-Unis, l’adresse d’urgence inscrite est utilisée pour faciliter l’écran et le routage de l’appel. Toutefois, l’appel est filtré pour déterminer si une adresse mise à jour est requise avant de connecter l’appelant au psap approprié.

L’emplacement dynamique pour le routage des appels d’urgence est pris en charge au Canada comme dans le États-Unis, à l’exception des exceptions suivantes : tous les appels d’urgence seront examinés à l’échelle nationale avant d’être transférés au PSAP.

Pour plus d’informations, consultez [Planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-operator-connect-mobile"></a>Routage des appels d’urgence pour Fournisseur de connectivité mobile

Lorsqu’un utilisateur Teams Fournisseur de connectivité mobile compose un numéro d’urgence à l’aide d’un client Microsoft Teams, la façon dont l’appel est acheminé vers le PSAP dépend des éléments suivants :

- Indique si l’adresse d’urgence est déterminée dynamiquement par le client Teams.

- Indique si l’adresse d’urgence est l’adresse inscrite associée au numéro de téléphone de l’utilisateur.

- Le réseau d’appel d’urgence de ce pays.

- Dans les États-Unis et au Canada, le routage dynamique fait partie du service du transporteur. Vous n’avez pas besoin de vous procurer ce service auprès d’un autre fournisseur de services.

- Si un client Teams se trouve à un emplacement d’urgence dynamique défini par le locataire :
  - Dans le États-Unis, les appels d’urgence de ce client sont automatiquement acheminés vers le PSAP qui dessert cet emplacement géographique.
  - Au Canada, tous les appels d’urgence seront examinés par un centre d’appels national avant de transférer l’appel au PSAP qui dessert cet emplacement géographique.

- Si un client Teams n’est pas situé à un emplacement d’urgence dynamique défini par le locataire, les appels d’urgence de ce client sont filtrés par un centre d’appels national pour déterminer l’emplacement de l’appelant avant de transférer l’appel vers le PSAP qui dessert cet emplacement géographique.

- Si un appelant d’urgence ne parvient pas à mettre à jour son emplacement d’urgence vers le centre de dépistage, l’appel est transféré vers le PSAP qui dessert l’adresse enregistrée de l’appelant.

Votre opérateur mobile gère tous les appels d’urgence effectués par le biais de votre SIM-Enabled numéroteur natif de smartphone et peut utiliser plusieurs technologies pour déterminer l’emplacement d’urgence approximatif pour obtenir de l’aide, comme les coordonnées géographiques ou les tours de cellule qui gèrent l’appel, etc. Contactez votre opérateur pour plus d’informations.


## <a name="considerations-for-direct-routing"></a>Considérations relatives au routage direct

Les sections suivantes décrivent comment gérer les appels d’urgence pour les utilisateurs de routage direct. Pour savoir si le routage direct est la solution appropriée pour votre entreprise, consultez les [options de connectivité RTC](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-direct-routing"></a>Activation des appels d’urgence pour le routage direct

Pour le routage direct, vous devez définir des stratégies d’appel d’urgence pour les utilisateurs à l’aide d’une [stratégie de routage des appels d’urgence Teams](manage-emergency-call-routing-policies.md) pour définir les numéros d’urgence et leur destination de routage associée. (Actuellement, les emplacements d’urgence enregistrés ne sont pas pris en charge pour les utilisateurs de routage direct.)

Vous pouvez affecter une stratégie de routage des appels d’urgence à un compte d’utilisateur de routage direct, à un site réseau ou aux deux. Lorsqu’un client Teams démarre ou modifie une connexion réseau, Teams effectue une recherche sur le site réseau où se trouve le client comme suit :

- Si une stratégie de routage des appels d’urgence est associée au site, la stratégie de site est utilisée pour configurer les appels d’urgence.

- Si aucune stratégie de routage des appels d’urgence n’est associée au site, si le client est connecté à un site non défini ou si le numéro composé ne correspond à aucun des numéros d’urgence définis dans la stratégie de routage des appels d’urgence associée au site, la stratégie de routage des appels d’urgence associée au compte d’utilisateur est utilisée pour configurer les appels d’urgence.

- Si le client Teams ne parvient pas à obtenir une stratégie de routage des appels d’urgence, l’utilisateur n’est pas activé pour les appels d’urgence.

### <a name="dynamic-emergency-calling-for-direct-routing"></a>Appel d’urgence dynamique pour le routage direct

Les appels d’urgence dynamiques pour le routage direct permettent de configurer et de router les appels d’urgence en fonction de l’emplacement actuel du client Teams. La possibilité d’effectuer un routage automatique vers le point de réponse de sécurité publique approprié (PSAP) ou d’informer le personnel du bureau de sécurité varie en fonction du pays d’utilisation de l’utilisateur Teams.

Pour les utilisateurs de routage direct, l’emplacement dynamique pour le routage des appels d’urgence est pris en charge uniquement dans le États-Unis comme suit :

- Si un client Teams pour un utilisateur de routage direct États-Unis acquiert dynamiquement une adresse d’urgence dans le États-Unis, cette adresse est utilisée pour le routage d’urgence et l’appel est automatiquement routée vers le PSAP dans la zone de service de l’adresse.

- Si un client Teams pour un utilisateur de routage direct États-Unis n’acquiert pas dynamiquement d’adresse d’urgence dans le États-Unis, l’appel est filtré pour déterminer si une adresse mise à jour est requise avant de connecter l’appelant au psap approprié.

L’emplacement dynamique pour le routage des appels d’urgence est pris en charge au Canada comme dans le États-Unis à l’exception suivante : tous les appels d’urgence seront examinés à l’échelle nationale avant d’être transférés au PSAP.

Pour plus d’informations, consultez [Configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-direct-routing"></a>Routage des appels d’urgence pour le routage direct

La stratégie de routage des appels d’urgence pour le routage direct fait référence à une utilisation rtc en ligne, qui doit avoir la configuration de routage direct appropriée pour acheminer correctement les appels d’urgence vers la ou les passerelles RTC appropriées. En particulier, vous devez vous assurer qu’il existe un OnlineVoiceRoute pour la chaîne de numérotation d’urgence. Pour plus d’informations, consultez [Configurer le routage direct](direct-routing-configure.md).

> [!NOTE]
> Les clients Teams n’ajoutent plus la connexion « + » devant les numéros d’urgence ; autrement dit, +911. Par conséquent, les appels d’urgence Teams n’envoieront plus de « + » avant le numéro 911. Assurez-vous que vos modèles de routage vocal reflètent ce changement.

La possibilité de router dynamiquement les appels d’urgence pour les utilisateurs de routage direct varie en fonction du réseau d’appels d’urgence au sein d’un pays donné. Deux solutions sont disponibles :

- [Fournisseurs de services de routage d’urgence (États-Unis uniquement)](#emergency-routing-service-providers)
- [Applications numéro d’identification d’emplacement d’urgence](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Fournisseurs de services de routage d’urgence

Dans le États-Unis, il existe de nombreux fournisseurs certifiés de services de routage d’urgence (ERSP) qui peuvent acheminer automatiquement les appels d’urgence en fonction de l’emplacement de l’appelant.

- Si un fournisseur de services de routage d’urgence est intégré à un déploiement de routage direct, les appels d’urgence avec un emplacement acquis dynamiquement sont automatiquement acheminés vers le point de réponse de sécurité publique (PSAP) qui dessert cet emplacement.

- Les appels d’urgence sans emplacement acquis dynamiquement sont d’abord filtrés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de distribution approprié en fonction de l’emplacement mis à jour.

Pour plus d’informations, consultez [Contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).

#### <a name="emergency-location-identification-number-applications"></a>Applications numéro d’identification d’emplacement d’urgence

Les contrôleurs de frontière de session (SBC) peuvent inclure des applications ELIN (Emergency Location Identification Number). Si une application ELIN SBC est intégrée à un déploiement de routage direct, vous devez configurer les adresses d’urgence et les numéros de téléphone associés dans l’application ELIN, puis charger les enregistrements ELIN dans la base de données d’appel d’urgence dans le RTC respectif. Les emplacements d’urgence Teams avec un identificateur ELIN doivent correspondre à ceux de l’application ELIN.

Lorsqu’un appel d’urgence avec un emplacement acquis dynamiquement est acheminé vers le SBC approprié, l’application ELIN :

- Analyse l’emplacement d’urgence de l’appelant.
- Correspond à l’emplacement d’un enregistrement ELIN.
- Remplace le numéro de l’appelant d’urgence par le numéro de téléphone ELIN.
- Achemine l’appel vers le psap qui dessert cet emplacement, puis les répartiteurs obtiennent l’emplacement à partir de l’enregistrement ELIN chargé.

Lors d’un rappel au numéro d’urgence, l’application ELIN effectue la substitution inverse du numéro appelé à celui de l’appelant d’urgence d’origine.

Pour plus d’informations, consultez [Contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).

## <a name="security-desk-notification"></a>Notification du bureau de sécurité

La notification du bureau de sécurité est disponible avec les plans d’appel Microsoft, Operator Connect et le routage direct.

Vous utilisez une stratégie d’appel d’urgence Teams (TeamsEmergencyCallingPolicy) pour configurer les personnes qui doivent être notifiées lors d’un appel d’urgence et la façon dont elles sont averties : conversation uniquement, conférences entrantes et désactivées, ou conférences entrantes et désactivées, mais avec la possibilité de désactiver le son. Vous pouvez également spécifier un numéro PSTN externe d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence. Notez que la partie RTC n’est pas autorisée à activer le son.

Une stratégie d’appel d’urgence peut être accordée à un compte d’utilisateur Teams, affecté à un site réseau, ou les deux.  Lorsqu’un client Teams démarre ou modifie une connexion réseau, Teams effectue une recherche sur le site réseau où se trouve le client :

- Si une stratégie d’appel d’urgence est associée à un site réseau, la stratégie de site est utilisée pour configurer la notification du service de sécurité.

- Si aucune stratégie d’appel d’urgence n’est associée au site, ou si le client est connecté à un site non défini, la stratégie d’appel d’urgence associée au compte d’utilisateur est utilisée pour configurer la notification du service de sécurité.

- Si le client Teams ne parvient pas à obtenir une stratégie d’appel d’urgence, l’utilisateur n’est pas activé pour la notification du bureau de sécurité.

Lors d’un appel d’urgence, un service de sécurité est téléconférence dans l’appel et l’expérience de l’utilisateur du bureau de sécurité est contrôlée en fonction de la stratégie d’appel d’urgence Teams. Une conversation de groupe est démarrée avec chaque membre du bureau de sécurité, et l’emplacement de l’appelant d’urgence est partagé via une notification de message importante.  Si une option de conférence est configurée dans le cadre de la stratégie, chaque utilisateur du bureau de sécurité est également appelé dans le cadre de la conférence.

### <a name="custom-emergency-disclaimer"></a>Exclusion de responsabilité d’urgence personnalisée

Les administrateurs ont la possibilité d’ajouter une bannière personnalisée dans le locataire pour que leurs utilisateurs puissent activer E911. Les utilisateurs peuvent ignorer la bannière lorsqu’ils confirment leur adresse, et la bannière réapparaît lorsque Teams est redémarré. Pour activer cette fonctionnalité, vous devez définir l’exclusion de responsabilité du **service d’urgence** sous la stratégie d’appel d’urgence Teams et entrer un message de chaîne à afficher aux utilisateurs. Ce champ est facultatif lors de la configuration d’une stratégie personnalisée, et le champ de chaîne est limité à 250 caractères.

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage des appels d’urgence ](manage-emergency-call-routing-policies.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Affecter ou modifier un emplacement d’urgence pour votre utilisateur](assign-change-emergency-location-user.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
