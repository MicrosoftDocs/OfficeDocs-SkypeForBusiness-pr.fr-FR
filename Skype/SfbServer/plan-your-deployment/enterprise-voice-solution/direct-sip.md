---
title: Connexions SIP directes dans Skype entreprise Server
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
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Les connexions SIP directes sont prises en charge entre Skype entreprise Server et les deux passerelles RTC et IP-PBX dans voix entreprise.
ms.openlocfilehash: 1948e08d63aed9d49c70443a386adce6dc65f78e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803054"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Connexions SIP directes dans Skype entreprise Server

Les connexions SIP directes sont prises en charge entre Skype entreprise Server et les deux passerelles RTC et IP-PBX dans voix entreprise.

Vous pouvez utiliser des connexions SIP directes pour connecter Skype entreprise Server à l’un des éléments suivants :

- Un PBX IP

- Passerelle RTC

Pour implémenter une connexion SIP directe, vous devez suivre les mêmes étapes de déploiement que dans le cadre de l’implémentation d’un Trunk SIP. Dans les deux cas, vous implémentez la connexion à l’aide de l’interface externe d’un serveur de médiation. La seule différence réside dans le fait que vous connectez des lignes SIP à une entité externe, telle qu’une passerelle ITSP et que vous connectez des connexions SIP directes à une entité interne au sein de votre réseau local (par exemple, un PBX IP ou une passerelle RTC (réseau téléphonique commuté).

## <a name="direct-sip-deployment-options"></a>Options de déploiement SIP direct

### <a name="skype-for-business-server-stand-alone"></a>Skype entreprise Server en autonome
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Si votre organisation utilise l’un des déploiements décrits dans cette section, vous pouvez utiliser Skype entreprise Server en tant que solution de téléphonie unique pour une partie ou l’ensemble d’une organisation. Cette section décrit en détail les déploiements suivants :

- **Déploiement incrémentiel :** Cette option part du principe que vous disposez d’une infrastructure PBX (Private Branch Exchange) existante et que vous envisagez d’introduire une voix entreprise de façon incrémentielle pour des groupes ou équipes plus petits au sein de votre organisation.

- **Déploiement VoIP uniquement :** cette option suppose que vous envisagez le déploiement d’Enterprise Voice sur un site ne disposant pas d’une infrastructure de téléphonie classique.

#### <a name="incremental-deployment"></a>Déploiement incrémental

Par le biais du déploiement incrémentiel, Skype entreprise Server est la seule solution de téléphonie pour les équipes ou services individuels, tandis que les autres utilisateurs d’une organisation continuent à utiliser un PBX. Cette stratégie de déploiement incrémental fournit un moyen d’introduire la téléphonie IP dans votre entreprise par le biais de programmes pilotes contrôlés. Les groupes de travail dont les besoins en matière de communication sont les plus appropriés par le biais de communications unifiées Microsoft sont déplacés vers voix entreprise, tandis que d’autres utilisateurs restent sur le système PBX existant. Vous pouvez migrer des groupes de travail supplémentaires vers Enterprise Voice, selon les besoins.

L’option incrémental est recommandée si vous avez clairement défini des groupes d’utilisateurs présentant des exigences de communication en commun et qui se prêtent à une gestion centralisée. Cette option est également utile si vous avez des équipes ou des services qui se propagent sur des zones géographiques larges, pour lesquelles l’économie des tarifs de grande distance peut être importante. En fait, cette option est utile pour créer des équipes virtuelles dont les membres pourront être disséminés dans le monde entier. Vous pouvez créer, modifier ou disperser le de telles équipes en réponse rapide au changement de configuration de votre entreprise.

La figure suivante illustre la topologie générique pour le déploiement de la voix entreprise derrière un PBX. Il s’agit de la topologie recommandée pour le déploiement incrémentiel.

**Option de déploiement incrémental**

![Diagramme d’option de migration départementale](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Si vous connectez votre déploiement Skype entreprise Server à un partenaire SIP direct certifié, une passerelle RTC (réseau téléphonique commuté) entre le serveur de médiation et le PBX n’est pas nécessaire. Pour obtenir la liste des partenaires SIP directs certifiés, reportez-vous au [programme Microsoft Unified Communications Open Interoperability](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> Le chemin d’accès multimédia indiqué dans cette figure est associé au contournement de média activé (configuration recommandée). Si vous choisissez de désactiver le contournement multimédia, le chemin multimédia est routé par le biais du serveur de médiation.

Dans cette topologie, les services ou groupes de travail sélectionnés sont activés pour voix entreprise. Une passerelle RTC relie le groupe de travail VoIP au système PBX. Les utilisateurs qui sont activés pour voix entreprise, y compris les travailleurs distants, communiquent sur le réseau IP. Les appels d’utilisateurs vocaux d’entreprise vers le RTC et aux collègues qui ne sont pas activés pour voix entreprise sont routés vers la passerelle RTC appropriée. Les appels provenant de collègues qui se trouvent toujours sur le système PBX ou à partir des appelants sur le RTC sont routés vers la passerelle RTC, qui transfère les appels à Skype entreprise Server pour le routage.

Il existe deux configurations recommandées pour la connexion de voix entreprise à une infrastructure PBX existante pour l’interopérabilité : voix entreprise derrière le PBX et voix entreprise en face du PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Voix entreprise à l’arrière-plan PBX

Lorsque Enterprise Voice est déployé derrière le système PBX, tous les appels à partir du RTC arrivent au PBX, ce qui achemine les appels vers une passerelle RTC et les appels vers des utilisateurs PBX vers le PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Voix entreprise en face du PBX

Lorsque Enterprise Voice est déployé devant le PBX, tous les appels arrivent sur la passerelle RTC, qui achemine les appels pour les utilisateurs voix entreprise vers Skype entreprise Server et appelle le PBX pour les utilisateurs PBX. Les appels vers le RTC provenant des utilisateurs de voix et de PBX entreprise sont routés via le réseau IP vers la passerelle RTC la plus économique. Le tableau suivant répertorie les avantages et inconvénients de cette configuration.

**Avantages et inconvénients du déploiement d’Enterprise Voice en face du PBX**

|**Inconvénients**|**Liés**|
|:-----|:-----|
|Le système PBX répond toujours aux utilisateurs non activés pour voix entreprise.  <br/> |Les passerelles existantes risquent de ne pas prendre en charge les fonctionnalités ou capacités de votre choix.  <br/> |
|Le système PBX gère tous les appareils antérieurs.  <br/> |Il est nécessaire de disposer d’un Trunk de la passerelle au PBX et de la passerelle au serveur de médiation. Il est possible que vous ayez besoin de plus de circuits auprès du prestataire de services.  <br/> |
|Les utilisateurs voix entreprise conservent les mêmes numéros de téléphone.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Déploiement VoIP uniquement

Enterprise Voice offre de nouvelles entreprises ainsi que de nouveaux sites Office pour les entreprises existantes, avec la possibilité d’implémenter une solution VoIP complète sans avoir à vous soucier de l’intégration PBX ou induire le déploiement et la maintenance importants. coûts d’une infrastructure PBX IP. Cette solution prend en charge les travailleurs sur site et distants.

Dans ce déploiement, tous les appels sont routés via le réseau IP. Les appels vers le RTC sont routés vers la passerelle RTC appropriée. Skype entreprise ou Lync Phone Edition fait office de téléphone. Le contrôle d’appel distant n’est pas disponible et n’est pas nécessaire, car il n’y a pas de téléphone PBX pour le contrôle des utilisateurs. Les services de messagerie vocale et de standard automatique sont disponibles par le biais du déploiement facultatif de la messagerie unifiée Exchange (UM).

> [!NOTE]
> Outre l’infrastructure réseau qui est requise pour la prise en charge de Skype entreprise Server, un déploiement VoIP uniquement peut utiliser une petite passerelle qualifiée pour prendre en charge les télécopieurs et les appareils analogiques.

La figure suivante illustre une topologie classique pour un déploiement VoIP uniquement.

**Option de déploiement VoIP uniquement**

![Option de déploiement dans un environnement vierge](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Le chemin d’accès multimédia indiqué dans cette figure est associé au contournement de média activé (configuration recommandée). Si vous choisissez de désactiver le contournement multimédia, le chemin multimédia est routé par le biais du serveur de médiation.

## <a name="pstn-gateway-deployment-options"></a>Options de déploiement de la passerelle RTC

### <a name="pstn-gateways"></a>Passerelles RTC

Les passerelles de réseau téléphonique commuté (PSTN) sont des composants matériels tiers qui convertissent le signalement et le contenu multimédia entre l’infrastructure vocale d’entreprise et le RTC, directement ou par le biais d’une connexion de lignes SIP. Dans chaque topologie, la passerelle arrête le RTC. La passerelle est isolée dans son propre sous-réseau et est connectée au réseau d’entreprise par le biais du serveur de médiation.

En règle générale, une entreprise avec plusieurs sites déploie une ou plusieurs passerelles sur chaque site. Les sites de succursale peuvent se connecter au RTC par le biais d’une passerelle ou d’une unité de branchement survivant qui combine les passerelles et les serveurs dans une seule boîte. Si les sites de succursales utilisent une passerelle, un serveur d’inscription et de médiation sont requis sur le site, sauf si la liaison WAN est résiliente. Un ou plusieurs serveurs de médiation, qui sont colocalisés sur des serveurs frontaux, peuvent router les appels pour les passerelles d’une ou plusieurs sur chaque site. Nous vous recommandons d’utiliser le Bureau d’enregistrement, le serveur de médiation et la passerelle requis sur le site comme une unité de branchement Survivable.

Le nombre, la taille et l’emplacement des passerelles RTC est peut-être la décision la plus importante et onéreuse lors de la planification de l’infrastructure vocale de votre entreprise.

Voici les principales questions à prendre en considération. Gardez à l’esprit que les réponses à ces questions sont interdépendantes.

- Combien de passerelles RTC sont-elles nécessaires ? La réponse dépend du nombre d’utilisateurs, du nombre d’appels simultanés (chargement du trafic) et du nombre de sites (chaque site en nécessite une).

- Quelle est la taille des passerelles ? La réponse dépend du nombre d’utilisateurs au niveau du site et du chargement du trafic.

- Où se trouvent les passerelles ? La réponse dépend en partie de la topologie et en partie de la distribution géographique de votre organisation.

  Vous devez également tenir compte des options de topologie de votre passerelle (pour plus de détails, voir topologies de passerelle plus loin dans cette rubrique).

#### <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Les serveurs de médiation peuvent acheminer les appels par le biais de plusieurs passerelles, contrôleurs de frontière de session (SBCs) fournis par des fournisseurs de services de téléphonie Internet ou d’une combinaison des deux. Par ailleurs, plusieurs serveurs de médiation du pool peuvent interagir avec plusieurs passerelles. L’itinéraire logique défini entre un serveur de médiation et une passerelle est appelé Trunk. Lorsqu’un utilisateur interne place un appel RTC, la logique de routage sortante du pool frontal détermine le Trunk à transférer au-delà de toutes les combinaisons possibles qui peuvent être disponibles pour le routage d’un appel particulier. En cas d’équilibrage de la charge DNS, si un appel ne parvient pas à accéder à une passerelle en raison d’un problème lié à un serveur de médiation particulier dans le pool, l’appel est répété vers un autre serveur de médiation du pool.

Pour plus d’informations sur la planification de plusieurs passerelles, reportez-vous à la rubrique [M :N Trunk dans Skype entreprise Server](m-n-trunk.md).

Pour plus d’informations sur les autres améliorations du routage sortant, voir [itinéraires d’appel](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologies de passerelle

Lorsque vous prenez en considération les questions fondamentales du déploiement de la passerelle, procédez comme suit :

1. Déterminez les sites pour lesquels vous souhaitez fournir une connectivité PSTN en utilisant Enterprise Voice.

2. Évaluez le trafic sur chaque site (nombre d’utilisateurs et nombre moyen d’appels par heure par utilisateur).

3. Déploiement d’une ou plusieurs passerelles sur chaque site pour gérer le trafic anticipé.

Avec cette topologie, les appels entre les travailleurs sur chaque site et entre les sites sont tous routés par le biais de votre intranet. Les appels vers le RTC sont routés via le réseau IP d’entreprise vers les passerelles les plus proches de l’emplacement des numéros de destination. Mais si votre organisation prend en charge des douzaines ou des centaines, voire des milliers de sites disséminés sur un ou plusieurs continents, le nombre d’institutions financières et d’autres grandes entreprises est important. Dans ce cas, le déploiement d’une passerelle séparée sur chaque site n’est pas pratique.

Pour résoudre ce problème, de nombreuses entreprises de grande taille préfèrent le déploiement d’un ou de plusieurs sites centraux de téléphonie de grande taille.

Dans cette topologie, plusieurs passerelles de grande taille suffisantes pour s’adapter à la charge d’utilisateurs prévue sont déployées sur chaque site central. Tous les appels vers des utilisateurs au sein de l’entreprise sont transférés par le fournisseur de services de téléphonie de l’entreprise à un site central. La logique de routage sur le site central détermine si l’appel doit être routé par le biais de l’intranet ou du RTC.

#### <a name="gateway-location"></a>Emplacement de la passerelle

L’emplacement de la passerelle détermine également les types de passerelles que vous choisissez et la manière dont ils sont configurés. Il existe des dizaines de protocoles RTC qui ne constituent aucune norme internationale. S’il ne s’agit pas de votre passerelle, il n’y a pas de problème, mais si vous trouvez des passerelles dans plusieurs pays/régions, chacune d’elles doit être configurée conformément aux normes RTC de ce pays/cette région. Par ailleurs, les passerelles certifiées pour le fonctionnement, par exemple le Canada, peuvent ne pas être certifiées en Inde, au Brésil ou en Union européenne.

#### <a name="gateway-size-and-number"></a>Taille et nombre de la passerelle

Les passerelles RTC dont la plupart des organisations envisageront de déployer la plage de 2 à la taille des ports 960. (Il y a encore plus de passerelles, mais elles sont principalement utilisées par les fournisseurs de services de téléphonie.) Lorsque vous évaluez le nombre de ports requis par votre organisation, vous devez suivre les instructions suivantes :

- Les organisations ayant une utilisation du service de téléphonie léger (un appel RTC par utilisateur par heure) doivent allouer un port pour tous les 15 utilisateurs. Par exemple, si vous avez 20 utilisateurs, vous aurez besoin d’une passerelle avec deux ports.

- Les organisations présentant une utilisation modérée de la téléphonie (deux appels RTC par utilisateur et par heure) doivent allouer un port pour chaque 10 utilisateurs. Par exemple, si vous avez des utilisateurs 100, vous aurez besoin d’un total de 10 ports alloués à une ou plusieurs passerelles.

- Les organisations ayant une utilisation importante de la téléphonie (au moins trois appels RTC par utilisateur et par heure) doivent allouer un port pour chaque cinquième utilisateur. Par exemple, si vous avez des utilisateurs 47 000, vous aurez besoin d’un total de ports 9 400 alloués entre au moins 10 passerelles de grande taille.

- Des ports supplémentaires peuvent être acquis au fur et à mesure de l’augmentation du nombre d’utilisateurs ou du volume de trafic au sein de votre organisation.

Pour tout nombre d’utilisateurs que vous devez prendre en charge, vous avez le choix entre le déploiement de plus petit, de passerelles plus grandes ou plus petites. En règle générale, un minimum de deux passerelles pour une organisation est recommandé pour garantir la disponibilité en cas d’échec d’une passerelle.

Chaque passerelle RTC que vous déployez doit avoir au moins un serveur de médiation correspondant.


