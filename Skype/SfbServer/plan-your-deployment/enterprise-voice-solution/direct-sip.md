---
title: Connexions SIP directes dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Connexions SIP directes sont prises en charge entre Skype pour Business Server et les passerelles PSTN et IP-PBX dans Enterprise Voice.
ms.openlocfilehash: 041009c5299f441e1b0e1a05c2af1e855f13f2b8
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374580"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Connexions SIP directes dans Skype pour Business Server

Connexions SIP directes sont prises en charge entre Skype pour Business Server et les passerelles PSTN et IP-PBX dans Enterprise Voice.

Vous pouvez utiliser des connexions SIP directes pour connecter Skype pour Business Server à un des éléments suivants :

- Un IP-PBX

- Une passerelle PSTN

Pour implémenter une connexion SIP directe, vous suivez essentiellement les mêmes étapes de déploiement comme vous le feriez pour implémenter une jonction SIP. Dans les deux cas, vous implémentez la connexion à l’aide de l’interface externe d’un serveur de médiation. La seule différence est que vous vous connectez jonctions SIP à une entité externe, par exemple une passerelle de ce dernier, et vous connectez connexions SIP directes à une entité interne au sein de votre réseau local, par exemple un IP-PBX ou une passerelle de réseau téléphonique commuté.

## <a name="direct-sip-deployment-options"></a>Options de déploiement SIP direct

### <a name="skype-for-business-server-stand-alone"></a>Skype pour Business Server autonome
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Si votre organisation utilise un des déploiements décrits dans cette section, vous pouvez utiliser Skype pour Business Server en tant que solution de téléphonie unique pour tout ou partie d’une organisation. Cette section décrit les déploiements suivants en détail :

- **Déploiement incrémentiel :** Cette option suppose que vous disposez d’une infrastructure d’autocommutateur privé (PBX) exchange et que vous avez l’intention d’introduire Enterprise Voice de manière incrémentielle à des plus petits groupes ou équipes au sein de votre organisation.

- **Déploiement VoIP uniquement :** cette option suppose que vous envisagez de déployer Enterprise Voice dans un site qui ne dispose pas d’une infrastructure de téléphonie traditionnelle.

#### <a name="incremental-deployment"></a>Déploiement incrémentiel

Dans un déploiement incrémentiel, Skype pour Business Server est la seule solution de téléphonie pour des équipes ou divisions particulières, tandis que le reste des utilisateurs dans une organisation continuent d’utiliser un système PBX. Cette stratégie de déploiement incrémentiel offre un moyen d’introduire la téléphonie IP dans votre entreprise par le biais de programmes pilotes contrôlés. Groupes de travail dont les communications nécessaires sont le mieux servis par les Communications unifiées de Microsoft sont déplacés vers Enterprise Voice, tandis que les autres utilisateurs restent sur le système PBX existant. Groupes de travail supplémentaires peuvent être migrées vers Enterprise Voice, selon vos besoins.

L’option incrémentielle est recommandée si vous avez défini clairement qu’ont des exigences de communication en commun et qui se prêtent à une gestion centralisée de groupes d’utilisateurs. Cette option est également utile si vous avez des équipes ou divisions qui sont dispersées sur des zones géographiques, où les économies sur les frais d’appel longue distances peuvent être considérables. En fait, cette option est utile pour la création d’équipes virtuelles dont les membres peuvent être éparpillés dans le monde. Vous pouvez créer, modifier ou dissoudre ces équipes pour les impératifs de répondre rapidement aux.

La figure suivante illustre la topologie générique pour le déploiement d’Enterprise Voice derrière un système PBX. Il s’agit de la topologie recommandée pour le déploiement incrémentiel.

**Option de déploiement incrémentiel**

![Diagramme d’option de migration départementale](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Si vous vous connectez votre Skype pour le déploiement de Business Server à un partenaire certifié SIP Direct, une passerelle de réseau public commuté entre le serveur de médiation et le système PBX n’est pas requise. Pour une liste de partenaires certifiés de SIP Direct, consultez le [Microsoft Unified Communications programme Open Interoperability](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> Le chemin d’accès aux médias montre cette figure a le contournement de média activé (recommandé). Si vous décidez de désactiver le contournement de média, le chemin d’accès des médias est routé via le serveur de médiation.

Dans cette topologie, des services ou groupes de travail sont activés pour Enterprise Voice. Une passerelle PSTN lie la voix sur IP (VoIP)-extension du groupe de travail vers le système PBX. Les utilisateurs activés pour Enterprise Voice, y compris les travailleurs à distance, de communiquer via le réseau IP. Appels par les utilisateurs d’Enterprise Voice au RTC et aux collaborateurs qui ne sont pas activés pour Enterprise Voice sont routés vers la passerelle PSTN appropriée. À partir de vos collègues sont toujours sur le système PBX ou des appelants sur le réseau RTC, les appels sont routés vers la passerelle PSTN qui transfère les appels Skype pour Business Server pour le routage.

Il existe deux topologies recommandées pour la connexion d’Enterprise Voice à une infrastructure PBX existante pour l’interopérabilité : Enterprise Voice derrière et Enterprise Voice devant le système PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice derrière le système PBX

Lorsque vous déployez voix entreprise derrière le système PBX, tous les appels du réseau téléphonique commuté arrivent sur le système PBX, qui achemine les appels aux utilisateurs d’Enterprise Voice à une passerelle PSTN et les appels vers les utilisateurs PBX vers le système PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice devant le système PBX

Lorsque vous déployez voix entreprise devant le système PBX, tous les appels arrivent sur la passerelle PSTN, qui achemine les appels aux utilisateurs d’Enterprise Voice de Skype pour Business Server et les appels pour les utilisateurs PBX vers le système PBX. Les appels RTC provenant d’utilisateurs Enterprise Voice et PBX sont routés sur le réseau IP vers la passerelle PSTN plus rentable. Le tableau suivant présente les avantages et inconvénients de cette configuration.

**Avantages et inconvénients du déploiement d’Enterprise Voice devant le système PBX**

|**Avantages**|**Inconvénients**|
|:-----|:-----|
|PBX continue de desservir les utilisateurs non activés pour Enterprise Voice.  <br/> |Les passerelles existantes ne peuvent pas prendre en charge les fonctionnalités ou la capacité que vous souhaitez.  <br/> |
|Le système PBX gère tous les dispositifs.  <br/> |Nécessite une jonction de passerelle vers le système PBX et de la passerelle vers le serveur de médiation. Vous devrez peut-être plusieurs jonctions à partir du fournisseur de service.  <br/> |
|Les utilisateurs d’Enterprise Voice conservent les mêmes numéros de téléphone.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Déploiement VoIP uniquement

Enterprise Voice fournit de nouvelles activités, ainsi que de nouveaux sites office pour les entreprises existantes, avec la possibilité d’implémenter une solution VoIP complète sans avoir à se soucier de l’intégration PBX ou impliquer le déploiement importante et la maintenance coûts d’une infrastructure IP-PBX. Cette solution prend en charge les travailleurs sur site et distants.

Dans ce déploiement, tous les appels sont routés sur le réseau IP. Les appels RTC sont routés vers la passerelle PSTN appropriée. Skype pour les professionnels ou Lync Phone Edition sert de téléphone logiciel. Contrôle d’appel distant est indisponible et inutiles, étant donné qu’aucun téléphone PBX pour les utilisateurs au contrôle. La messagerie vocale et services de standard automatique sont disponibles via le déploiement facultatif de Exchange messagerie unifiée (MU).

> [!NOTE]
> Outre l’infrastructure réseau qui est requis pour prendre en charge Skype pour Business Server, un déploiement VoIP uniquement peut utiliser une petite passerelle qualifiée pour prendre en charge des télécopieurs et des périphériques analogiques.

La figure suivante illustre une topologie classique pour un déploiement VoIP uniquement.

**Option de déploiement VoIP uniquement**

![Option de déploiement dans un environnement vierge](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Le chemin d’accès aux médias montre cette figure a le contournement de média activé (recommandé). Si vous décidez de désactiver le contournement de média, le chemin d’accès des médias est routé via le serveur de médiation.

## <a name="pstn-gateway-deployment-options"></a>Options de déploiement de passerelle PSTN

### <a name="pstn-gateways"></a>Passerelles PSTN

Passerelles de réseau téléphonique commuté sont des composants matériels tiers qui traduisent la signalisation et les médias entre l’infrastructure Enterprise Voice et le réseau RTC, directement ou par le biais de la connexion à jonctions SIP. Dans une topologie, la passerelle met fin à la passerelle PSTN. La passerelle est isolée dans son propre sous-réseau et est connectée au réseau d’entreprise par le biais du serveur de médiation.

Une entreprise avec plusieurs sites est généralement déployer une ou plusieurs passerelles sur chaque site. Sites de succursale peuvent se connecter au réseau RTC via une passerelle, soit par un serveur Survivable Branch Appliance, qui combine la passerelle et les serveurs dans une zone unique. Si les sites de succursale utilisent une passerelle, un serveur d’inscriptions et le serveur de médiation sont requis sur site, sauf si la liaison réseau étendu est résistante. Un ou plusieurs serveurs de médiation sont colocalisés sur les serveurs frontaux, peut acheminer les appels pour l’une ou plusieurs passerelles sur chaque site. Il est recommandé que le serveur d’inscriptions, serveur de médiation et passerelle requis sur le site sont déployés en tant qu’un serveur Survivable Branch Appliance.

Déterminer le nombre, la taille et emplacement des passerelles PSTN est peut-être la décision la plus importante et coûteuse que vous devez prendre lors de la planification de votre infrastructure Enterprise Voice.

Voici les principales questions à prendre en compte. N’oubliez pas que les réponses à ces questions sont tous interdépendants

- Les passerelles PSTN combien sont nécessaires ? La réponse dépend du nombre d’utilisateurs, le nombre d’appels simultanés (trafic) et le nombre de sites (chaque site nécessite).

- Quelle taille doit être la passerelles ? La réponse dépend du nombre d’utilisateurs au niveau du site et de la charge du trafic.

- Où les passerelles doivent se trouver ? La réponse dépend en partie de la topologie et en partie de la répartition géographique de votre organisation.

  Vous devez également tenir compte votre passerelle options de topologie (pour plus d’informations, consultez Topologies de passerelles plus loin dans cette rubrique).

#### <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Les serveurs de médiation peut acheminer des appels par le biais de plusieurs passerelles, contrôleurs de frontière de Session (SBC) fournis par les fournisseurs de services de téléphonie Internet, ou une combinaison des deux. En outre, plusieurs serveurs de médiation du pool peuvent interagir avec plusieurs passerelles. L’itinéraire logique entre un serveur de médiation et la passerelle est appelé une jonction. Lorsqu’un utilisateur interne passe un appel RTC, la logique de routage sortante sur le pool frontal choisit la jonction pour acheminer sur Déconnecter toutes les combinaisons possibles qui peuvent être disponibles pour le routage de cet appel particulier. L’équilibrage de charge DNS, si un appel échoue atteindre une passerelle en raison d’un problème avec un serveur de médiation spécifique dans le pool, l’appel sera tentée à nouveau sur un autre serveur de médiation du pool.

Pour plus d’informations sur la planification de plusieurs passerelles, voir [jonction m : n dans Skype pour Business Server](m-n-trunk.md).

Pour plus d’informations sur les autres améliorations apportées au routage sortantes, voir [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologies de passerelles

Lorsque vous examinez les questions fondamentales relatives au déploiement des passerelles, procédez comme suit :

1. Nombre de sites à laquelle vous souhaitez fournir une connectivité PSTN à l’aide d’Enterprise Voice.

2. Évaluer le trafic sur chaque site (nombre d’utilisateurs) et le nombre moyen d’appels par heure et par utilisateur.

3. Déployer une ou plusieurs passerelles sur chaque site pour gérer le trafic prévu.

Avec cette topologie, les appels entre collaborateurs sur chaque site et entre les sites sont routés sur votre intranet. Les appels RTC sont routés sur le réseau IP d’entreprise pour les passerelles qui sont le plus proche de l’emplacement des numéros de destination. Mais que se passe-t-il si votre organisation prend en charge des douzaines ou des centaines ou voire des milliers de sites répartis sur plusieurs continents, comme de nombreuses institutions financières et grandes entreprises ? Dans ce cas, le déploiement d’une passerelle séparée sur chaque site n’est pas pratique.

Pour résoudre ce problème, de nombreuses grandes entreprises préfèrent déployer un ou plusieurs sites centraux téléphonie importants.

Dans cette topologie, plusieurs passerelles de grande taille suffisantes pour contenir la charge anticipée pour les utilisateurs sont déployés sur chaque site central. Tous les appels aux utilisateurs de l’entreprise sont transmis par le fournisseur de services de téléphone de la société à un site central. Logique de routage sur le site central détermine si l’appel doit être routé sur l’intranet ou vers le RTC.

#### <a name="gateway-location"></a>Emplacement de la passerelle

Emplacement de la passerelle peut également déterminer les types de passerelles que vous choisissez et comment ils sont configurés. Il existe des douzaines de protocoles RTC, dont aucun ne sont un standard mondial. Si tous vos passerelles se trouvent dans une pays/région unique, ce n’est pas un problème, mais si vous recherchez des passerelles dans plusieurs pays/régions, chacun doit être configuré en fonction des normes PSTN de ce pays/région. En outre, les passerelles qui sont certifiées pour, par exemple, au Canada, ne peuvent pas être certifiées en Inde, au Brésil ou dans l’Union européenne.

#### <a name="gateway-size-and-number"></a>Nombre et la taille de la passerelle

Les passerelles PSTN, la plupart des organisations considère que le déploiement de la plage de taille supérieure à 2 au maximum de 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par les fournisseurs de services de téléphone). Lors de l’estimation du nombre de ports que requis par votre organisation, procédez comme suit :

- Les organisations avec l’utilisation de la téléphonie est faible (1 appel PSTN par utilisateur et par heure) doivent allouer un port pour 15 utilisateurs. Par exemple, si vous avez 20 utilisateurs, vous avez besoin d’une passerelle dotée de deux ports.

- Les organisations avec une utilisation modérée téléphonie (deux appels PSTN par utilisateur et par heure) doivent allouer un port pour 10 utilisateurs. Par exemple, si vous disposez de 100 utilisateurs, vous avez besoin d’un total de 10 ports alloués sur une ou plusieurs passerelles.

- Les organisations avec une utilisation intensive de téléphonie (trois appels RTC ou plus par utilisateur et par heure) doivent allouer un port pour 5 utilisateurs. Par exemple, si vous avez 47,000 utilisateurs, vous avez besoin d’un total de 9.400 ports alloués sur au moins 10 passerelles de grande taille.

- D’autres ports peuvent être acquis à mesure que le nombre d’utilisateurs ou de la quantité de trafic augmente dans votre organisation.

Pour n’importe quel nombre donné d’utilisateurs à prendre en charge, vous devez choisir de déployer des passerelles de grande taille moins ou petites. En règle générale, un minimum de deux passerelles pour une organisation est recommandé de maintenir la disponibilité en cas d’échec d’une passerelle.

Chaque passerelle PSTN que vous déployez doit avoir au moins un serveur de médiation correspondant.


