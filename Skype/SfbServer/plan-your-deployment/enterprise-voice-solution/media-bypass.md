---
title: Plan de contournement de médias dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Décisions nécessaires à la planification d’une dérivation multimédia dans Skype entreprise Server Voice. Inclut l’interaction avec le contrôle d’admission des appels.
ms.openlocfilehash: aed78aa12f593f834bc2c694fec87d5d31e6e47b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802704"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Plan de contournement de médias dans Skype entreprise

Décisions nécessaires à la planification d’une dérivation multimédia dans Skype entreprise Server Voice. Inclut l’interaction avec le contrôle d’admission des appels.

La dérivation multimédia désigne la suppression du serveur de médiation du chemin multimédia dans la mesure du possible pour les appels dont le signalement traverse le serveur de médiation.

La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, les conversions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels. L’évolutivité peut être améliorée, car la suppression du traitement multimédia pour les appels ignorés réduit la charge sur le serveur de médiation. Cette réduction du chargement complète les fonctionnalités du serveur de médiation pour contrôler plusieurs passerelles.

 Dans le cas où un site de succursale ne disposant pas d’un serveur de médiation est connecté à un site central par le biais d’une ou de plusieurs liaisons WAN avec une bande passante restreinte, le contournement de média diminue la bande passante en autorisant les contenus multimédias d’un client sur un site de succursale à circuler directement vers sa passerelle locale sans tout d’abord, le lien réseau étendu doit être transmis à un serveur de médiation sur le site central.

Le fait de soulager le serveur de médiation contre la transformation de média, le contournement de médias risque également de réduire le nombre de serveurs de médiation requis par une infrastructure vocale d’entreprise. En règle générale, essayez d’activer la déviation du trafic multimédia quand cela est possible.

La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.

**Médias et voies de signalisation avec et sans déviation du trafic multimédia**

![Application de connexion de contournement de média CAC vocal](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

La dérivation de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. En règle générale, un pool de serveurs de médiation est déployé sur un site central et contrôle les passerelles dans les sites de succursales. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels PSTN (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Les itinéraires des appels sortants de Skype entreprise Server et les stratégies voix entreprise doivent être correctement configurés de sorte que les appels RTC de clients sur un site de succursale soient routés vers la passerelle appropriée.

Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.

## <a name="planning-your-media-bypass-deployment"></a>Planification de votre déploiement de contournement de média

Une fois que votre structure vocale d’entreprise est en place, il est facile de planifier une dérivation multimédia.

- Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer la déviation du trafic multimédia car il n’est pas nécessaire d’affiner le contrôle.

- Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :

  - Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour la déviation du trafic multimédia.

  - Quels sont les sites bien connectés dans chaque région réseau.

  - Quelle combinaison de déviation du trafic multimédia et de contrôle d’admission des appels est appropriée pour votre réseau.

Lorsque vous activez la déviation du trafic multimédia, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.

Lorsqu’un utilisateur effectue un appel vers le RTC, le serveur de médiation compare l’ID de contournement du sous-réseau du client à l’ID de contournement du sous-réseau de la passerelle. Si les deux ID de contournement concordent, la déviation du trafic multimédia est utilisée pour l’appel. Si les ID de contournement ne correspondent pas, le média de l’appel doit être acheminé via le serveur de médiation.

Lorsqu’un utilisateur reçoit un appel à partir du RTC, le client de l’utilisateur compare son ID de contournement à celui de la passerelle PSTN. Si les deux ID de contournement correspondent, les flux multimédias sont directement de la passerelle au client, en ignorant le serveur de médiation.

Seuls Lync 2010 ou les clients et appareils plus récents prennent en charge les interactions de contournement de média avec un serveur de médiation.

> [!IMPORTANT]
> En plus d’autoriser la déviation du trafic multimédia global, vous devez autoriser la déviation du trafic multimédia individuellement sur chaque jonction PSTN. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction PSTN donnée, la déviation du trafic multimédia ne sera appelée pour aucun appel impliquant cette jonction PSTN. En outre, lorsque la déviation du trafic multimédia est définie sur **Utiliser les informations de site et de région**, vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser la déviation du trafic multimédia. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct.

## <a name="media-bypass-modes"></a>Modes de déviation du trafic multimédia

Vous devez configurer la déviation du trafic multimédia à la fois au niveau global et au niveau de chaque jonction PSTN. Lorsque vous activez la déviation du trafic multimédia au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions**.

As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.

L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la flexibilité de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.

- Le système affecte automatiquement un ID de contournement unique à chaque région.

- Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.

- Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.

- Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.

## <a name="media-bypass-and-call-admission-control"></a>Déviation du trafic multimédia et contrôle d’admission des appels

La déviation du trafic multimédia et le contrôle d’admission des appels fonctionnent conjointement pour gérer le contrôle de la bande passante pour le trafic des données multimédias pendant les appels. La déviation du trafic multimédia facilite le flux des données multimédias sur des liaisons correctement connectées ; le contrôle d’admission des appels, quant à lui, gère le trafic sur les liaisons avec des restrictions de bande passante. Étant donné que la déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement, vous devez tenir compte de l’un lorsque vous planifiez l’utilisation de l’autre. Les combinaisons suivantes sont prises en charge :

- La déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés. La déviation du trafic multimédia doit être définie sur **Utiliser les informations de site et de région**. Ces informations sont les mêmes que celles utilisées pour le contrôle d’admission des appels.

    Si vous activez le contrôle d’admission des appels, vous ne pouvez pas sélectionner **Toujours ignorer** et inversement, car les deux configurations s’excluent mutuellement. C’est-à-dire, qu’une seule configuration s’appliquera à un appel PSTN donné. D’abord, une vérification a lieu pour déterminer si la déviation du trafic multimédia s’applique à l’appel. Si c’est le cas, le contrôle d’admission des appels n’est pas utilisé. Cela est logique, car si la déviation du trafic multimédia peut être appliquée à l’appel, celui-ci utilise par définition une connexion où le contrôle d’admission des appels n’est pas nécessaire. Si la contournement ne peut pas être appliquée à l’appel (c’est-à-dire si les ID de contournement du client et de la passerelle ne correspondent pas), le CAC est appliqué à l’appel.

- Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Toujours ignorer**.

    Dans cette configuration, les sous-réseaux du client et de la jonction sont mappés à un seul ID de contournement, qui est calculé par le système.

- Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Utiliser les informations de site et de région**.

    Lorsque **Utiliser les informations de site et de région** est activé, la vérification pour déterminer si le contournement doit s’appliquer fonctionne essentiellement de la même manière, que le contrôle d’admission des appels soit activé ou non. C’est-à-dire pour tout appel RTC donné, le sous-réseau du client est mappé à un site particulier et l’ID de contournement pour ce sous-réseau est extrait. De même, le sous-réseau de la passerelle est mappé à un site particulier et l’ID de contournement pour ce sous-réseau est extrait. Le contournement aura lieu pour l’appel uniquement si les deux ID de contournement sont identiques. Si ce n’est pas le cas, la déviation du trafic multimédia n’aura pas lieu.

    Même si le contrôle d’admission des appels est désactivé globalement, la stratégie de bande passante doit être définie pour chaque site et liaison si vous voulez utiliser la configuration site-et-région pour décider d’appliquer le contournement ou non. La valeur réelle de la contrainte de bande passante n’a pas d’importance. L’objectif est que le système calcule automatiquement différents ID de contournement à associer à différents emplacements qui ne sont pas correctement connectés. Définir une restriction de bande passante signifie par définition qu’une liaison n’est pas correctement connectée.

- Le contrôle d’admission des appels est activé et la déviation du trafic multimédia n’est pas activée. Cela s’applique uniquement lorsque toutes les passerelles et les PBX IP ne sont pas correctement connectés ou ne remplissent pas toutes les conditions pour la déviation du trafic multimédia. Pour plus d’informations sur les conditions requises pour la déviation du trafic multimédia, reportez-vous à [Requirements for Media Bypass](https://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).

## <a name="technical-requirements"></a>Configuration technique requise

Pour chaque appel au RTC, le serveur de médiation détermine si les éléments multimédias du point de terminaison Skype entreprise de l’origine peuvent être envoyés directement à un homologue du serveur de médiation sans traverser le serveur de médiation. L’homologue peut être une passerelle PSTN, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) associé à la jonction entre le serveur de médiation où l’appel est routé.

La déviation du trafic multimédia peut être utilisée lorsque les conditions suivantes sont remplies :

- Un homologue de serveur de médiation doit prendre en charge les fonctionnalités nécessaires à la dérivation de média multimédia, c’est la possibilité de gérer plusieurs réponses correspondantes (appelées « boîtes de dialogue précoce »). Contactez le fabricant de votre passerelle ou système PBX, ou votre fournisseur ITSP, pour obtenir la valeur du nombre maximal de boîtes de dialogue préliminaires que la passerelle, PBX ou SBC peut accepter.

- Le serveur de médiation doit accepter le trafic multimédia directement depuis les points de terminaison Skype entreprise. De nombreux ITSPs permettent à l’SBC de recevoir le trafic uniquement à partir du serveur de médiation. Contactez votre ITSP pour déterminer si l’SBC accepte le trafic multimédia directement depuis les points de terminaison Skype entreprise.

- Les clients Skype entreprise et un serveur de médiation doivent être bien connectés, ce qui signifie qu’ils se trouvent dans la même région réseau ou sur des sites réseau qui se connectent à la région sur des liens WAN sans contraintes de bande passante.


