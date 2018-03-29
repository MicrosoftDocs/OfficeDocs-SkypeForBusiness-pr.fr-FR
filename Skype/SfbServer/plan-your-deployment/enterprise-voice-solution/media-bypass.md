---
title: Planification de la déviation du trafic multimédia dans Skype Entreprise 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Ignorent les décisions nécessaires à la planification pour le média dans Skype pour Business Server Voix Entreprise. Inclut l’interaction avec le contrôle d’admission des appels.
ms.openlocfilehash: 75a0a2ec2f4575881abcecad210314e1fdeda7d5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-media-bypass-in-skype-for-business-2015"></a>Planification de la déviation du trafic multimédia dans Skype Entreprise 2015
 
Ignorent les décisions nécessaires à la planification pour le média dans Skype pour Business Server Voix Entreprise. Inclut l’interaction avec le contrôle d’admission des appels.
  
Le contournement de média fait référence à la suppression du serveur de médiation du chemin multimédia dès que possible pour les appels dont la signalisation parcourt le serveur de médiation.
  
La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, les conversions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels. L’évolutivité peut être améliorée, car l’élimination du support de traitement des appels ignorées réduit la charge sur le serveur de médiation. Cette réduction de la charge complète de la capacité du serveur de médiation pour contrôler plusieurs passerelles. 
  
 Dans le cas où un site de la succursale sans un serveur de médiation est connecté à un site central par un ou plusieurs liens WAN avec une bande passante limitée, le contournement de média réduit le besoin en bande passante en autorisant des médias à partir d’un client à un site de la succursale à circuler directement vers sa passerelle locale sans tout d’abord avoir à circuler à travers le WAN créer un lien vers un serveur de médiation sur le site central et la sauvegarder.
  
En déchargeant le département à partir de traitement des médias, le serveur de médiation, le contournement de média peut également réduire le nombre de serveurs de médiation nécessitant une infrastructure de Voix Entreprise. En règle générale, essayez d’activer la déviation du trafic multimédia quand cela est possible.
  
La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.
  
**Ignorent les supports et voies de signalisation avec et sans support**

![Application de connexion de contournement de média CAC vocal](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)
  
Le contournement de média est utile lorsque vous souhaitez réduire le nombre de serveurs de médiation déployés. En général, un pool de serveur de médiation est déployé sur un site central, et il contrôle les passerelles sur les sites des succursales. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels PSTN (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Skype pour Business Server appel sortant itinéraires et les stratégies de Voix Entreprise doit être correctement configuré afin que les appels RTPC à partir de clients sur un site de la succursale sont acheminées vers la passerelle appropriée.
  
Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.
  
## <a name="planning-your-media-bypass-deployment"></a>Planification de votre déploiement de contournement de média

Une fois votre structure de Voix Entreprise est en place, planification pour contournent les médias est simple.
  
- Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer la déviation du trafic multimédia car il n’est pas nécessaire d’affiner le contrôle.
    
- Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :
    
  - Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour la déviation du trafic multimédia.
    
  - Quels sont les sites bien connectés dans chaque région réseau.
    
  - Quelle combinaison de déviation du trafic multimédia et de contrôle d’admission des appels est appropriée pour votre réseau.
    
Lorsque vous activez la déviation du trafic multimédia, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.
  
Lorsqu’un utilisateur effectue un appel vers le RTC, le serveur de médiation compare l’ID de contournement du sous-réseau client avec l’ID de contournement du sous-réseau passerelle. Si les deux ID de contournement concordent, la déviation du trafic multimédia est utilisée pour l’appel. Si le contournement de codes ne correspondent pas, support pour l’appel doit passer par le serveur de médiation.
  
Lorsqu’un utilisateur reçoit un appel de RTC, le client de l’utilisateur compare son ID de contournement à celle de la passerelle RTC. Si les deux ignorer la correspondance d’ID, media passe directement à partir de la passerelle vers le client, en contournant le serveur de médiation.
  
Seuls Lync 2010 ou plus récent les clients et périphériques prennent en charge les interactions de contournement media avec un serveur de médiation.
  
> [!IMPORTANT]
> En plus d’autoriser la déviation du trafic multimédia global, vous devez autoriser la déviation du trafic multimédia individuellement sur chaque jonction PSTN. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction PSTN donnée, la déviation du trafic multimédia ne sera appelée pour aucun appel impliquant cette jonction PSTN. En outre, lorsque la déviation du trafic multimédia est définie sur **Utiliser les informations de site et de région**, vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser la déviation du trafic multimédia. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct. 
  
## <a name="media-bypass-modes"></a>Modes de déviation du trafic multimédia

Vous devez configurer la déviation du trafic multimédia à la fois au niveau global et au niveau de chaque jonction PSTN. Lorsque vous activez la déviation du trafic multimédia au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions**. 
  
Comme son nom l’indique, **Toujours contourner** les moyens de contourner va être tentées pour tous les appels RTPC. **Toujours ignorer** est utilisée pour les déploiements où il est inutile d’activer le contrôle d’admission appel, ni est il nécessaire de spécifier des informations de configuration détaillées concernant l’heure média ignorer. En outre, **Toujours ignorer** est utilisé lorsqu’il existe une connectivité totale entre les clients et les passerelles RTPC. Dans cette configuration, tous les sous-réseaux sont mappés à un, et un seul ignorer ID, qui est calculée par le système.
  
L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la flexibilité de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.
  
- Le système affecte automatiquement un ID de contournement unique à chaque région.
    
- Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.
    
- Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.
    
- Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.
    
## <a name="media-bypass-and-call-admission-control"></a>Déviation du trafic multimédia et contrôle d’admission des appels

La déviation du trafic multimédia et le contrôle d’admission des appels fonctionnent conjointement pour gérer le contrôle de la bande passante pour le trafic des données multimédias pendant les appels. La déviation du trafic multimédia facilite le flux des données multimédias sur des liaisons correctement connectées ; le contrôle d’admission des appels, quant à lui, gère le trafic sur les liaisons avec des restrictions de bande passante. Étant donné que la déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement, vous devez tenir compte de l’un lorsque vous planifiez l’utilisation de l’autre. Les combinaisons suivantes sont prises en charge :
  
- La déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés. La déviation du trafic multimédia doit être définie sur **Utiliser les informations de site et de région**. Ces informations sont les mêmes que celles utilisées pour le contrôle d’admission des appels.
    
    Si vous activez le contrôle d’admission des appels, vous ne pouvez pas sélectionner **Toujours ignorer** et inversement, car les deux configurations s’excluent mutuellement. C’est-à-dire, qu’une seule configuration s’appliquera à un appel PSTN donné. D’abord, une vérification a lieu pour déterminer si la déviation du trafic multimédia s’applique à l’appel. Si c’est le cas, le contrôle d’admission des appels n’est pas utilisé. Cela est logique, car si la déviation du trafic multimédia peut être appliquée à l’appel, celui-ci utilise par définition une connexion où le contrôle d’admission des appels n’est pas nécessaire. Si Ignorer ne peut pas être appliqué à l’appel (autrement dit, si le contournement de la passerelle et du client ID ne correspondent pas), CAC est appliquée à l’appel.
    
- Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Toujours ignorer**.
    
    Dans cette configuration, les sous-réseaux du client et de la jonction sont mappés à un seul ID de contournement, qui est calculé par le système.
    
- Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Utiliser les informations de site et de région**.
    
    Lorsque **Utiliser les informations de site et de région** est activé, la vérification pour déterminer si le contournement doit s’appliquer fonctionne essentiellement de la même manière, que le contrôle d’admission des appels soit activé ou non. Autrement dit, pour tout appel RTC donné, le sous-réseau du client est mappé sur un site particulier, et l’ID de contournement de ce sous-réseau est extraite. De même, les sous-réseau de la passerelle sont mappé sur un site particulier, et l’ID de contournement de ce sous-réseau est extraite. Le contournement aura lieu pour l’appel uniquement si les deux ID de contournement sont identiques. Si ce n’est pas le cas, la déviation du trafic multimédia n’aura pas lieu.
    
    Même si le contrôle d’admission des appels est désactivé globalement, la stratégie de bande passante doit être définie pour chaque site et liaison si vous voulez utiliser la configuration site-et-région pour décider d’appliquer le contournement ou non. La valeur réelle de la contrainte de la bande passante ou ses modalité n’a aucune importance. L’objectif est que le système calcule automatiquement différents ID de contournement à associer à différents emplacements qui ne sont pas correctement connectés. Définir une restriction de bande passante signifie par définition qu’une liaison n’est pas correctement connectée.
    
- Le contrôle d’admission des appels est activé et la déviation du trafic multimédia n’est pas activée. Cela s’applique uniquement lorsque toutes les passerelles et les PBX IP ne sont pas correctement connectés ou ne remplissent pas toutes les conditions pour la déviation du trafic multimédia. Pour plus d’informations sur la configuration requise pour le contournement de média, consultez [Configuration requise pour Media Bypass](http://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).
    
## <a name="technical-requirements"></a>Configuration technique requise

Pour chaque appel au RTC, le serveur de médiation détermine si les supports depuis la Skype pour point de terminaison Business d’origine peuvent être envoyés directement à un homologue de serveur de médiation sans parcourir le serveur de médiation. L’homologue peut être une passerelle PSTN, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) associé à la jonction entre le serveur de médiation où l’appel est routé.
  
La déviation du trafic multimédia peut être utilisée lorsque les conditions suivantes sont remplies :
  
- Un homologue de serveur de médiation doit prendre en charge les fonctionnalités nécessaires pour le contournement de média, la plus importante étant la capacité à gérer plusieurs réponses comprenant des branches (appelées « boîtes de dialogue anticipées »). Contactez le fabricant de votre passerelle ou système PBX, ou votre fournisseur ITSP, pour obtenir la valeur du nombre maximal de boîtes de dialogue préliminaires que la passerelle, PBX ou SBC peut accepter.
    
- L’homologue de serveur de médiation doit accepter le trafic de media directement à partir de Skype pour les points de terminaison Business. ITSPs de permettent leur colonie d’abeilles simulée recevoir uniquement le trafic du serveur de médiation. Contactez votre ITSP pour déterminer si ses SBC accepte le trafic des médias directement à partir de Skype pour les points de terminaison Business.
    
- Skype pour les clients d’entreprise et un serveur de médiation homologue doit être bien connecté, c'est-à-dire qu’ils se trouvent soit dans la même région de réseau ni au réseau les sites qui se connectent à la région sur WAN des liens qui n’ont aucune contrainte de bande passante
    

