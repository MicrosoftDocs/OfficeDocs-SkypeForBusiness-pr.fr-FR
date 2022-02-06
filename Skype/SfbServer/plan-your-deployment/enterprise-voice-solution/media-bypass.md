---
title: Planifier le contournement de média dans Skype Entreprise
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Décisions nécessaires à la planification du contournement de média dans Skype Entreprise Server Voix Entreprise. Inclut l’interopérabilité avec le contrôle d’admission des appels (CAC).
---

# <a name="plan-for-media-bypass-in-skype-for-business"></a>Planifier le contournement de média dans Skype Entreprise

Décisions nécessaires à la planification du contournement de média dans Skype Entreprise Server Voix Entreprise. Inclut l’interopérabilité avec le contrôle d’admission des appels (CAC).

Le contournement de média fait référence à la suppression du serveur de médiation du chemin d’accès des médias, dans la mesure du possible, pour les appels dont la signalisation traverse le serveur de médiation.

Le contournement de média peut améliorer la qualité de la voix en diminuant la latence, les traductions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels. L’extensibilité peut être améliorée du fait que l’élimination du traitement multimédia pour les appels contournés réduit la charge sur le serveur de médiation. Cette réduction de la charge complète la capacité du serveur de médiation à contrôler plusieurs passerelles.

 Lorsqu’un site de succursale sans serveur de médiation est connecté à un site central par une ou plusieurs liaisons WAN avec bande passante limitée, le contournement de média réduit les besoins en bande passante en permettant aux médias d’un client d’un site de succursale de circuler directement vers sa passerelle locale sans avoir à traverser la liaison wan vers un serveur de médiation sur le site central et vers l’arrière.

En réduisant le traitement multimédia au serveur de médiation, le contournement de média peut également réduire le nombre de serveurs de médiation dont une infrastructure Voix Entreprise a besoin. En règle générale, essayez d’activer le contournement de média quand cela est possible.

La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans contournement de média.

**Médias et voies de signalisation avec et sans contournement de média**

![Application de la connexion de contournement de média CAC vocal.](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

Le contournement de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. Un pool de serveurs de médiation est généralement déployé sur un site central et contrôle des passerelles sur des sites de succursale. L’activation du contournement de média permet aux médias de passer des appels PSTN (Public Switched Telephone Network) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Skype Entreprise Server les itinéraires d’appels sortants et les stratégies de Voix Entreprise doivent être correctement configurés afin que les appels PSTN des clients d’un site de succursale soient acheminés vers la passerelle appropriée.

Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.

## <a name="planning-your-media-bypass-deployment"></a>Planification de votre déploiement de déviation du réseau multimédia

Une fois votre Voix Entreprise en place, la planification du contournement de média est simple.

- Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer le contournement de média car il n’est pas nécessaire d’affiner le contrôle.

- Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :

  - Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour le contournement de média.

  - Quels sont les sites bien connectés dans chaque région réseau.

  - Quelle combinaison de contournement de média et de contrôle d’admission des appels est appropriée pour votre réseau.

Lorsque vous activez le contournement de média, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.

Lorsqu’un utilisateur effectue un appel vers le réseau téléphonique téléphonique public (PSTN), le serveur de médiation compare l’ID de contournement du sous-réseau client à l’ID de contournement du sous-réseau de passerelle. Si les deux ID de contournement concordent, le contournement de média est utilisé pour l’appel. Si les ID de contournement ne correspondent pas, le média de l’appel doit passer par le serveur de médiation.

Lorsqu’un utilisateur reçoit un appel du PSTN, le client de l’utilisateur compare son ID de contournement à celui de la passerelle PSTN. Si les deux ID de contournement correspondent, le média circule directement de la passerelle vers le client, en contournant le serveur de médiation.

Seuls les clients et périphériques Lync 2010 ou plus nouveaux supportent les interactions de déviation du média avec un serveur de médiation.

> [!IMPORTANT]
> En plus d’autoriser le contournement de média global, vous devez autoriser le contournement de média individuellement sur chaque jonction RTC. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction RTC donnée, le contournement de média ne sera invoqué pour aucun appel impliquant cette jonction RTC. En outre, lorsque le contournement de média est défini sur **Utiliser les informations de site et de région**, vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser le contournement de média. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct.

## <a name="media-bypass-modes"></a>Modes de contournement de média

Vous devez configurer le contournement de média à la fois au niveau global et au niveau de chaque jonction PSTN. Lorsque vous activez le contournement de média au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions**.

L’option **Toujours ignorer** engendre une tentative de contournement pour tous les appels PSTN. Cette option s’applique aux déploiements au sein desquels il n’est pas nécessaire d’activer le contrôle d’admission des appels ou pour lesquels il n’est pas nécessaire de spécifier des informations de configuration détaillées sur les tentatives de contournement de média. De plus, **Toujours ignorer** est utilisée lorsque la connectivité entre les clients et les passerelles PSTN est satisfaisante. Dans cette configuration, les sous-réseaux sont mappés à un seul ID de contournement, qui est calculé par le système.

L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la souplesse de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.

- Le système affecte automatiquement un ID de contournement unique à chaque région.

- Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.

- Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.

- Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.

## <a name="media-bypass-and-call-admission-control"></a>Contournement de média et contrôle d’admission des appels

Le contournement de média et le contrôle d’admission des appels (CAC) fonctionnent ensemble pour gérer le contrôle de bande passante pour les médias d’appel. La déviation du trafic multimédia facilite le flux multimédia sur les liaisons bien connectées . Le contrôle d’acc s gère le trafic sur les liaisons avec des contraintes de bande passante. Étant donné que le contournement de média et le service Cac s’excluent mutuellement, vous devez en tenir compte lors de la planification de l’autre. Les combinaisons suivantes sont pris en charge :

- Le cac et le contournement de média sont tous deux activés. La déviation du média doit être définie pour **utiliser les informations de site et de région**. Ces informations de site et de région sont identiques à celles utilisées pour le cac.

    Si vous activez le service Cac, vous ne pouvez pas sélectionner **Always Bypass**, et vice versa, car les deux configurations s’excluent mutuellement. Autrement dit, une seule des deux s’applique à un appel PSTN donné. Tout d’abord, une vérification est réalisée pour déterminer si la déviation du média s’applique à l’appel. Si c’est le cas, le cac n’est pas utilisé. Cela est logique, car si un appel est éligible pour le contournement, il s’agit par définition d’utiliser une connexion où le cac n’est pas nécessaire. Si le contournement ne peut pas être appliqué à l’appel (c’est-à-dire, si les ID de contournement du client et de la passerelle ne correspondent pas), le service Cac est appliqué à l’appel.

- Cac not enabled and Media Bypass set to **Always Bypass**.

    Dans cette configuration, les sous-réseaux client et de la trunk sont tous deux mappés sur un seul ID de contournement, qui est calculé par le système.

- Cac not enabled and Media Bypass set to **Use Site and Region Information**.

    Lorsque **l’utilisation des informations** de site et de région est activée, la détermination du contournement fonctionne essentiellement de la même manière, que le service CAC soit activé ou non. Autrement dit, pour tout appel PSTN donné, le sous-réseau du client est mappé à un site particulier et l’ID de contournement de ce sous-réseau est extrait. De même, le sous-réseau de la passerelle est mappé à un site particulier et l’ID de contournement de ce sous-réseau est extrait. Ce n’est que si les deux ID de contournement sont identiques que le contournement se produit pour l’appel. S’ils ne sont pas identiques, le contournement de média ne se produit pas.

    Même si le contrôle d’accès au client est désactivé globalement, une stratégie de bande passante doit être définie pour chaque site et lien si vous souhaitez utiliser la configuration de site et de région pour contrôler la décision de contournement. La valeur réelle de la contrainte de bande passante ou de sa modalité n’a pas d’importance. L’objectif final est que le système calcule automatiquement différents ID de contournement à associer à différents paramètres régionaux qui ne sont pas bien connectés. La définition d’une contrainte de bande passante par définition signifie qu’un lien n’est pas bien connecté.

- Le cac est activé et le contournement de média n’est pas activé. Cela s’applique uniquement lorsque toutes les passerelles et IP-PBXs ne sont pas bien connectées ou ne répondent pas aux autres exigences de déviation du média. Pour plus d’informations sur les conditions requises pour le contournement de média, voir [Requirements for Media Bypass](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-media-bypass).

## <a name="technical-requirements"></a>Exigences techniques

Pour chaque appel au PSTN, le serveur de médiation détermine si le média du point de terminaison Skype Entreprise d’origine peut être envoyé directement à un homologue de serveur de médiation sans passer par le serveur de médiation. L’homologue peut être une passerelle PSTN, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) associé à la jonction entre le serveur de médiation où l’appel est routé.

Le contournement de média peut être utilisé lorsque les conditions suivantes sont remplies :

- Un homologue de serveur de médiation doit prendre en charge les fonctionnalités nécessaires pour le contournement de média, la plus importante étant la capacité à gérer plusieurs réponses bifurcations (appelées « boîtes de dialogue anticipées »). Contactez le fabricant de votre passerelle ou système PBX, ou votre fournisseur ITSP, pour obtenir la valeur du nombre maximal de boîtes de dialogue préliminaires que la passerelle, PBX ou SBC peut accepter.

- L’homologue du serveur de médiation doit accepter le trafic multimédia directement à partir Skype Entreprise terminaison. De nombreux itsps autorisent leur SBC à recevoir du trafic uniquement à partir du serveur de médiation. Contactez votre itsp pour déterminer si son SBC accepte le trafic multimédia directement à partir Skype Entreprise terminaison.

- Skype Entreprise clients et un homologue de serveur de médiation doivent être bien connectés, ce qui signifie qu’ils sont situés dans la même région réseau ou sur des sites réseau qui se connectent à la région sur des liaisons wan sans contrainte de bande passante