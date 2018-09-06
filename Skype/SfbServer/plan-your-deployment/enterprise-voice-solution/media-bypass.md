---
title: Planification du contournement de média dans Skype pour les entreprises
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Les décisions nécessaires à la planification pour le média de contournement dans Skype pour Business Server Enterprise Voice. Inclut l’interaction avec le contrôle d’admission des appels.
ms.openlocfilehash: 3b96455884c46b5c387e909806b5811e95be09bf
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245075"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planification du contournement de média dans Skype pour les entreprises

Les décisions nécessaires à la planification pour le média de contournement dans Skype pour Business Server Enterprise Voice. Inclut l’interaction avec le contrôle d’admission des appels.

Le contournement de média fait référence à la suppression du serveur de médiation dans le chemin d’accès des médias autant que possible pour les appels dont la signalisation traverse le serveur de médiation.

La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, les conversions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels. L’évolutivité peut être améliorée, car la suppression de supports de traitement pour les appels ignorés réduit la charge sur le serveur de médiation. Cette réduction de la charge complète de la capacité du serveur de médiation pour contrôler plusieurs passerelles.

 Lorsqu’un site de succursale sans un serveur de médiation est connecté à un site central par un ou plusieurs liaisons réseau étendu à bande passante restreinte, le contournement de média réduit les besoins en bande passante en autorisant le média à partir d’un client sur un site de succursale directement à la passerelle locale sans tout d’abord avoir flux WAN lier à un serveur de médiation sur le site central et sauvegarder.

En libérant le serveur de médiation du traitement multimédia, le contournement de média peut également réduire le nombre de serveurs de médiation qui requiert une infrastructure Enterprise Voice. En règle générale, essayez d’activer la déviation du trafic multimédia quand cela est possible.

La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.

**Médias et voies de signalisation avec et sans déviation du trafic multimédia**

![Application de connexion de contournement de média CAC vocal](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

Le contournement de média est utile lorsque vous souhaitez réduire le nombre de serveurs de médiation déployés. En règle générale, un pool de serveurs de médiation sera déployé sur un site central, et il contrôle passerelles sur les sites de succursale. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels PSTN (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Skype pour les stratégies Enterprise Voice et les itinéraires d’appels sortants Business Server doit être configuré correctement afin que les appels PSTN à partir de clients sur un site de succursale sont routés vers la passerelle appropriée.

Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.

## <a name="planning-your-media-bypass-deployment"></a>Planification de votre déploiement de contournement de média

Une fois votre structure Enterprise Voice, la planification du contournement de média est simple.

- Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer la déviation du trafic multimédia car il n’est pas nécessaire d’affiner le contrôle.

- Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :

  - Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour la déviation du trafic multimédia.

  - Quels sont les sites bien connectés dans chaque région réseau.

  - Quelle combinaison de déviation du trafic multimédia et de contrôle d’admission des appels est appropriée pour votre réseau.

Lorsque vous activez la déviation du trafic multimédia, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.

Lorsqu’un utilisateur effectue un appel vers la passerelle PSTN, le serveur de médiation compare l’ID de contournement du sous-réseau client avec l’ID de contournement du sous-réseau passerelle. Si les deux ID de contournement concordent, la déviation du trafic multimédia est utilisée pour l’appel. Si le contournement de média ID ne correspondent pas, média pour l’appel doit passer par le serveur de médiation.

Lorsqu’un utilisateur reçoit un appel à partir de la passerelle PSTN, le client de l’utilisateur compare son ID de contournement à celle de la passerelle PSTN. Si les deux correspondance d’ID de contournement, les données multimédias transitent directement à partir de la passerelle pour le client, sans passer par le serveur de médiation.

Uniquement Lync 2010 ou plus récente des clients et périphériques prend en charge les interactions de déviation du trafic multimédia avec un serveur de médiation.

> [!IMPORTANT]
> En plus d’autoriser la déviation du trafic multimédia global, vous devez autoriser la déviation du trafic multimédia individuellement sur chaque jonction PSTN. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction PSTN donnée, la déviation du trafic multimédia ne sera appelée pour aucun appel impliquant cette jonction PSTN. En outre, lorsque la déviation du trafic multimédia est définie sur **Utiliser les informations de site et de région**, vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser la déviation du trafic multimédia. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct.

## <a name="media-bypass-modes"></a>Modes de déviation du trafic multimédia

Vous devez configurer la déviation du trafic multimédia à la fois au niveau global et au niveau de chaque jonction PSTN. Lorsque vous activez la déviation du trafic multimédia au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions**.

Comme son nom l’indique, signifie **Toujours ignorer** que contournement sont tentées pour tous les appels PSTN. **Toujours ignorer** est utilisée pour les déploiements où il n’est pas nécessaire pour activer le contrôle d’admission des appels, ni est il nécessaire de spécifier les informations de configuration détaillées concernant l’heure multimédia contournement de média. En outre, **Toujours ignorer** est utilisée lorsqu’il existe une connectivité totale entre les clients et passerelles PSTN. Dans cette configuration, tous les sous-réseaux sont mappés à un et qu’un seul ID de contournement, qui est calculé par le système.

L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la flexibilité de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.

- Le système affecte automatiquement un ID de contournement unique à chaque région.

- Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.

- Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.

- Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.

## <a name="media-bypass-and-call-admission-control"></a>Déviation du trafic multimédia et contrôle d’admission des appels

La déviation du trafic multimédia et le contrôle d’admission des appels fonctionnent conjointement pour gérer le contrôle de la bande passante pour le trafic des données multimédias pendant les appels. La déviation du trafic multimédia facilite le flux des données multimédias sur des liaisons correctement connectées ; le contrôle d’admission des appels, quant à lui, gère le trafic sur les liaisons avec des restrictions de bande passante. Étant donné que la déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement, vous devez tenir compte de l’un lorsque vous planifiez l’utilisation de l’autre. Les combinaisons suivantes sont prises en charge :

- La déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés. La déviation du trafic multimédia doit être définie sur **Utiliser les informations de site et de région**. Ces informations sont les mêmes que celles utilisées pour le contrôle d’admission des appels.

    Si vous activez le contrôle d’admission des appels, vous ne pouvez pas sélectionner **Toujours ignorer** et inversement, car les deux configurations s’excluent mutuellement. C’est-à-dire, qu’une seule configuration s’appliquera à un appel PSTN donné. D’abord, une vérification a lieu pour déterminer si la déviation du trafic multimédia s’applique à l’appel. Si c’est le cas, le contrôle d’admission des appels n’est pas utilisé. Cela est logique, car si la déviation du trafic multimédia peut être appliquée à l’appel, celui-ci utilise par définition une connexion où le contrôle d’admission des appels n’est pas nécessaire. Si le contournement de média ne peut pas être appliqué à l’appel (autrement dit, si du client et la passerelle de contournement ID ne correspondent pas), puis CAC est appliquée à l’appel.

- Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Toujours ignorer**.

    Dans cette configuration, les sous-réseaux du client et de la jonction sont mappés à un seul ID de contournement, qui est calculé par le système.

- Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Utiliser les informations de site et de région**.

    Lorsque **Utiliser les informations de site et de région** est activé, la vérification pour déterminer si le contournement doit s’appliquer fonctionne essentiellement de la même manière, que le contrôle d’admission des appels soit activé ou non. Autrement dit, pour un appel RTC donné, le sous-réseau du client est mappé sur un site particulier, et l’ID de contournement pour ce sous-réseau est extraite. De même, sous-réseau de la passerelle est mappé sur un site particulier, et l’ID de contournement pour ce sous-réseau est extraite. Le contournement aura lieu pour l’appel uniquement si les deux ID de contournement sont identiques. Si ce n’est pas le cas, la déviation du trafic multimédia n’aura pas lieu.

    Même si le contrôle d’admission des appels est désactivé globalement, la stratégie de bande passante doit être définie pour chaque site et liaison si vous voulez utiliser la configuration site-et-région pour décider d’appliquer le contournement ou non. La valeur réelle de la contrainte de bande passante ou son modalité n’a aucune importance. L’objectif est que le système calcule automatiquement différents ID de contournement à associer à différents emplacements qui ne sont pas correctement connectés. Définir une restriction de bande passante signifie par définition qu’une liaison n’est pas correctement connectée.

- Le contrôle d’admission des appels est activé et la déviation du trafic multimédia n’est pas activée. Cela s’applique uniquement lorsque toutes les passerelles et les PBX IP ne sont pas correctement connectés ou ne remplissent pas toutes les conditions pour la déviation du trafic multimédia. Pour plus d’informations sur la configuration requise pour le contournement de média, voir [Configuration requise pour le contournement de média](https://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).

## <a name="technical-requirements"></a>Configuration technique requise

Pour chaque appel à la passerelle PSTN, le serveur de médiation détermine si les supports depuis la Skype pour le point de terminaison Business d’origine peuvent être envoyés directement à un homologue du serveur de médiation sans parcourir le serveur de médiation. L’homologue peut être une passerelle PSTN, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) associé à la jonction entre le serveur de médiation où l’appel est routé.

La déviation du trafic multimédia peut être utilisée lorsque les conditions suivantes sont remplies :

- Un homologue du serveur de médiation doit prendre en charge les fonctionnalités nécessaires pour le contournement de média, la plus importante en cours la possibilité de gérer plusieurs réponses dirigées (appelés « boîtes de dialogue préliminaires »). Contactez le fabricant de votre passerelle ou système PBX, ou votre fournisseur ITSP, pour obtenir la valeur du nombre maximal de boîtes de dialogue préliminaires que la passerelle, PBX ou SBC peut accepter.

- L’homologue du serveur de médiation doit accepter le trafic multimédia directement à partir de Skype pour systèmes d’extrémité Business. ITSPs nombreux autoriser leur SBC recevoir le trafic uniquement à partir du serveur de médiation. Contactez votre fournisseur ITSP pour déterminer si son SBC accepte le trafic multimédia directement à partir de Skype pour systèmes d’extrémité Business.

- Skype pour les clients d’entreprise et un serveur de médiation entre homologues doivent être bien connectés, ce qui signifie que qu’ils se trouvent soit dans la même région de réseau ou au réseau de sites qui se connectent à la région via des liaisons réseau étendu qui lie n’ont aucune contrainte de bande passante


