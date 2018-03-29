---
title: Connexions SIP directes dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Les connexions directes SIP sont prises en charge entre Skype pour le serveur de l’entreprise et les passerelles RTPC et IP-PBX de Voix Entreprise.
ms.openlocfilehash: 36b549b20708f0f9b09b8aeadf6f4197b9de1371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="direct-sip-connections-in-skype-for-business-server-2015"></a>Connexions SIP directes dans Skype Entreprise Server 2015
 
Les connexions directes SIP sont prises en charge entre Skype pour le serveur de l’entreprise et les passerelles RTPC et IP-PBX de Voix Entreprise.
  
Vous pouvez utiliser des connexions directes SIP se pour connecter Skype pour Business Server à une des opérations suivantes :
  
- Un IP-PBX 
    
- Une passerelle PSTN
    
Pour mettre en œuvre une connexion directe au SIP, vous suivez essentiellement le même processus de déploiement comme vous le feriez pour implémenter un SIP trunk. Dans les deux cas, vous implémentez la connexion à l’aide de l’interface externe d’un serveur de médiation. La seule différence est que vous connectez puits SIP à une entité externe, par exemple une passerelle ITSP, et vous les connexions directes du SIP à une entité interne au sein de votre réseau local, par exemple un PBX IP ou une passerelle de réseau téléphonique public commuté.
  
## <a name="direct-sip-deployment-options"></a>Options de déploiement SIP direct

### <a name="skype-for-business-server-stand-alone"></a>Skype pour Business Server autonome
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Si votre organisation utilise l’un des déploiements décrites dans cette section, vous pouvez utiliser Skype pour Business Server comme la solution de téléphonie unique pour tout ou partie d’une organisation. Cette section décrit les déploiements suivants en détail :
  
- **Le déploiement incrémentiel :** Cette option suppose que vous disposez d’une infrastructure de private branch exchange (PBX) et que vous avez l’intention d’intégrer progressivement les Voix Entreprise à plus petits groupes ou équipes de votre organisation.
    
- **Déploiement VoIP uniquement :** cette option suppose que vous envisagez de déploiement de Voix Entreprise sur un site qui ne dispose pas d’une infrastructure téléphonique traditionnelle.
    
#### <a name="incremental-deployment"></a>Déploiement incrémentiel

Dans un déploiement incrémentiel, Skype pour Business Server est la solution de téléphonie unique pour les équipes individuelles ou départements, tandis que les autres utilisateurs dans une organisation continuent à utiliser un PBX. Cette stratégie de déploiement incrémentiel fournit une façon de présenter la téléphonie IP dans votre entreprise par le biais des programmes pilotes contrôlés. Groupes de travail dont la communication a besoin sont servies le mieux par Microsoft Unified Communications sont déplacés vers la Voix Entreprise, tandis que les autres utilisateurs restent sur le système PBX existant. Les groupes de travail supplémentaires peuvent être migrées vers Voix Entreprise, en fonction des besoins.
  
L’option incrémentielle est recommandée si vous avez défini clairement qu’ont des exigences de communication commun et qui se prêtent à une gestion centralisée de groupes d’utilisateurs. Cette option est aussi efficace que si vous avez les équipes ou les départements qui sont réparties sur des zones géographiques de large, où les économies de frais longue distances peuvent être importantes. En fait, cette option est utile pour la création d’équipes virtuelles, dont les membres peuvent être répartis dans le monde entier. Vous pouvez créer, modifier ou disperser le telles équipes dans une réponse rapide à un décalage des besoins de l’entreprise.
  
La figure suivante illustre la topologie générique pour le déploiement de Voix Entreprise derrière un standard privé. Il s’agit de la topologie recommandée pour le déploiement incrémentiel.
  
**Option de déploiement incrémentiel**

![Diagramme d’option de migration départementale](../../media/Fig28_Departmental_migration_option.jpg)
  
> [!NOTE]
> Si vous vous connectez à votre Skype pour le déploiement de Business Server à un partenaire agréé de SIP Direct, une passerelle de réseau (RTPC) public commuté entre le serveur de médiation et PBX n’est pas nécessaire. Pour obtenir une liste de partenaires certifiés de SIP Direct, consultez le [Microsoft Unified Communications interopérabilité programme ouvert](https://go.microsoft.com/fwlink/p/?linkId=203309). 
  
> [!NOTE]
> Le chemin d’accès de média indiqué dans la figure a activé le contournement de média (configuration recommandée). Si vous choisissez de désactiver le contournement de média, le chemin d’accès au média est routé via le serveur de médiation. 
  
Dans cette topologie, des services ou groupes de travail sont activés pour les Voix Entreprise. Une passerelle PSTN lie la voix sur IP (VoIP)-activé de groupe de travail au PBX. Les utilisateurs qui sont activés pour les Voix Entreprise, y compris les travailleurs à distance, de communiquer via le réseau IP. Appels par les utilisateurs de Voix Entreprise au RTC et à vos collègues qui ne sont pas activés pour les Voix Entreprise sont acheminées vers la passerelle RTC appropriée. À partir de vos collègues qui sont toujours sur le système PBX ou appelants du réseau public commuté, les appels sont routés vers la passerelle RTC, qui transfère les appels Skype pour Business Server pour le routage.
  
Il existe deux configurations recommandées pour la connexion de Voix Entreprise à une infrastructure PBX existante pour l’interopérabilité : Voix Entreprise derrière la Voix Entreprise devant le PBX et PBX.
  
#### <a name="enterprise-voice-behind-the-pbx"></a>Voix Entreprise derrière le PBX

Lors du déploiement de Voix Entreprise derrière le PBX, tous les appels de RTC arrivent au niveau du PBX, qui route les appels vers les utilisateurs de Voix Entreprise à une passerelle PSTN, appels et pour les utilisateurs des PBX au PBX. 
  
#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Voix Entreprise devant le PBX

Lors du déploiement de Voix Entreprise devant le PBX, tous les appels arrivent à la passerelle RTC, les itinéraires qui appelle pour que les utilisateurs de Voix Entreprise Skype pour Business Server et pour les utilisateurs des PBX, les appels au PBX. Appels au RTC, les utilisateurs à la fois de Voix Entreprise et PBX sont routés via le réseau IP pour la passerelle PSTN la plus économique. Le tableau suivant présente les avantages et les inconvénients de cette configuration.
  
**Avantages et inconvénients du déploiement de Voix Entreprise devant PBX**

|**Avantages**|**Inconvénients**|
|:-----|:-----|
|PBX sert toujours ne pas activées pour la Voix Entreprise des utilisateurs.  <br/> |Passerelles existants ne peuvent pas prend en charge les fonctionnalités ou la capacité que vous souhaitez.  <br/> |
|PBX gère tous les périphériques plus anciens.  <br/> |Nécessite un tronc à partir de la passerelle vers le PBX et de la passerelle vers le serveur de médiation. Vous devrez peut-être plus de puits à partir du fournisseur de service.  <br/> |
|Les utilisateurs de Voix Entreprise conservent le même numéro de téléphone.  <br/> | <br/> |
   
#### <a name="voip-only-deployment"></a>Déploiement VoIP uniquement

Voix Entreprise fournit de nouvelles entreprises, ainsi que les nouveaux sites d’office pour les entreprises existantes, avec la possibilité de mettre en œuvre une solution VoIP complète sans avoir à vous soucier de l’intégration PBX ou à supporter l’important déploiement et la maintenance coûts d’une infrastructure IP-PBX. Cette solution prend en charge les travailleurs sur site et à distance.
  
Dans ce déploiement, tous les appels sont routés via le réseau IP. Appels au RTC sont acheminées vers la passerelle RTC appropriée. Skype pour les entreprises ou Lync Phone Edition est utilisé comme un téléphone logiciel. Contrôle d’appel distant est indisponible et inutiles, car il n’y a pas de téléphones PBX pour les utilisateurs à contrôler. Messagerie vocale et services de standard automatique sont disponibles via le déploiement facultatif d’Exchange messagerie unifiée (MU).
  
> [!NOTE]
> En plus de l’infrastructure de réseau est nécessaire pour prendre en charge Skype pour Business Server, un déploiement VoIP uniquement pouvez utiliser une passerelle petite, qualifiée pour prendre en charge des télécopieurs et des appareils analogiques. 
  
La figure suivante illustre une topologie typique pour un déploiement VoIP uniquement.
  
**Option de déploiement VoIP uniquement**

![Option de déploiement dans un environnement vierge](../../media/Fig29_Greenfield_deployment_option.jpg)
  
> [!NOTE]
> Le chemin d’accès de média indiqué dans la figure a activé le contournement de média (configuration recommandée). Si vous choisissez de désactiver le contournement de média, le chemin d’accès au média est routé via le serveur de médiation. 
  
## <a name="pstn-gateway-deployment-options"></a>Options de déploiement de passerelle PSTN

### <a name="pstn-gateways"></a>Passerelles RTPC

Passerelles de réseau téléphonique public commuté sont des composants de matériel tiers qui traduisent de signalisation et multimédias entre l’infrastructure de Voix Entreprise et le réseau RTPC, soit directement, soit par connexion SIP puits qui y aboutissent. Dans une topologie, la passerelle termine le RTPC. La passerelle est isolée dans son propre sous-réseau et est connectée au réseau d’entreprise via le serveur de médiation.
  
Une entreprise avec plusieurs sites est généralement déployer une ou plusieurs passerelles sur chaque site. Les sites distants peuvent se connecter au RTC via une passerelle, soit via un Survivable Branch Appliance, qui combine la passerelle et les serveurs dans une seule boîte. Si les sites de succursales utilisent une passerelle, un Registre et le serveur de médiation sont requises sur site, à moins que la liaison réseau étendu est résiliente. Un ou plusieurs serveurs de médiation sont colocalisés sur les serveurs frontaux, peut acheminer des appels pour les passerelles d’au moins un sur chaque site. Il est recommandé que le Registre, serveur de médiation et la passerelle requises sur site sont déployés comme une Survivable Branch Appliance.
  
Déterminer le nombre, la taille et l’emplacement des passerelles RTPC, est sans doute la décision plus importante et plus coûteuse que vous devez apporter lors de la planification de votre infrastructure de Voix Entreprise. 
  
Voici les questions essentielles à prendre en compte. N’oubliez pas que les réponses à ces questions sont tous interdépendants.
  
- Les passerelles RTPC combien sont nécessaires ? La réponse dépend du nombre d’utilisateurs, le nombre d’appels simultanés (charge de trafic) et le nombre de sites (chaque site nécessite).
    
- Quelle taille doivent être les passerelles ? La réponse dépend du nombre d’utilisateurs sur le site et sur la charge du trafic.
    
- Où les passerelles doivent se trouver ? La réponse dépend en partie de la topologie et dans la partie de la répartition géographique de votre organisation.
    
 Vous devez également envisager votre passerelle options de topologie (pour plus d’informations, consultez Topologies de passerelle plus loin dans cette rubrique).
  
#### <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Les serveurs de médiation peut acheminer des appels par le biais de plusieurs passerelles, contrôleurs de bordure de Session (SBCs) fournis par les fournisseurs de services de téléphonie Internet, ou une combinaison des deux. En outre, plusieurs serveurs de médiation dans le pool peut interagir avec plusieurs passerelles. L’itinéraire logique définie entre un serveur de médiation et la passerelle est appelée un trunk. Lorsqu’un utilisateur interne place un appel RTC, la logique de routage sortante sur le pool frontal choisit le tronc pour acheminer sur de toutes les combinaisons possibles qui peuvent être disponibles pour le routage de cet appel particulier. Avec l’équilibrage de charge DNS, si un appel échoue atteindre une passerelle suite à un problème avec un serveur de médiation particulier dans le pool, l’appel sera tentée à nouveau sur un autre serveur de médiation dans le pool. 
  
Pour plus d’informations sur la planification de plusieurs passerelles, consultez [trunk n : n dans Skype pour Business Server 2015](m-n-trunk.md).
  
Pour plus d’informations sur les autres améliorations de routage sortantes, consultez [Appeler des itinéraires](http://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).
  
#### <a name="gateway-topologies"></a>Topologies de passerelle

Lorsque vous considérez les questions fondamentales de déploiement de passerelle, procédez comme suit :
  
1. Nombre de sites à laquelle vous souhaitez fournir la connectivité RTPC à l’aide de Voix Entreprise.
    
2. Estimer le trafic sur chaque site (nombre d’utilisateurs) et le nombre moyen d’appels par heure et par utilisateur.
    
3. Déployer un ou plusieurs passerelles sur chaque site de gérer le trafic anticipé.
    
Avec cette topologie, les appels entre les travailleurs sur chaque site et entre différents sites sont acheminés via votre intranet. Appels au RTC sont routés via le réseau IP d’entreprise pour les passerelles qui sont le plus proche de l’emplacement des numéros de destination. Mais que se passe-t-il si votre organisation prend en charge des dizaines ou des centaines ou même des milliers de sites répartis sur un ou plusieurs des continents, comme de nombreuses institutions financières et autres grandes entreprises ? Dans ce cas, il n’est pas pratique de déploiement d’une passerelle distincte sur chaque site.
  
Pour résoudre ce problème, de nombreuses grandes entreprises préfèrent déployer un ou plusieurs sites centraux de téléphonie de grande taille.
  
Dans cette topologie, plusieurs passerelles de grande taille suffisantes pour contenir la charge utilisateur anticipée sont déployés sur chaque site central. Tous les appels aux utilisateurs de l’entreprise sont transmis par le fournisseur de services de téléphone de la société vers un site central. La logique de routage sur le site central détermine si l’appel doit être acheminé sur l’intranet ou au RTC.
  
#### <a name="gateway-location"></a>Emplacement de la passerelle

Emplacement de la passerelle peut également déterminer les types de passerelles que vous choisissez et comment ils sont configurés. Il existe des dizaines de protocoles RTPC, qui est une norme dans le monde entier. Si toutes vos passerelles sont situés dans un pays ou une région unique, ce n’est pas un problème, mais si vous recherchez des passerelles dans plusieurs pays/régions, chacun doit être configuré conformément aux normes RTPC de ce pays ou cette région. En outre, passerelles qui sont certifiés pour une opération, par exemple, le Canada, ne peuvent pas être certifiées de l’Inde, du Brésil ou de l’Union européenne.
  
#### <a name="gateway-size-and-number"></a>Nombre et la taille de la passerelle

Les passerelles RTPC, la plupart des entreprises considère que le déploiement de la plage de taille supérieure à 2 ports jusqu'à 960. (Il existe des passerelles encore plus importante, mais elles sont principalement utilisées par les fournisseurs de services téléphoniques). Lors de l’estimation du nombre de ports que requis par votre organisation, utilisez les instructions suivantes :
  
- Les organisations avec l’utilisation de la téléphonie de lumière (un seul appel RTC par utilisateur et par heure) doivent allouer un port pour tous les utilisateurs de 15. Par exemple, si vous disposez de 20 utilisateurs, vous aurez besoin d’une passerelle avec deux ports.
    
- Les organisations avec une utilisation modérée de téléphonie (deux appels RTPC par utilisateur et par heure) doivent allouer un port pour chaque 10 utilisateurs. Par exemple, si vous disposez de 100 utilisateurs, vous aurez besoin d’un total de 10 ports répartis entre un ou plusieurs des passerelles.
    
- Les organisations avec une utilisation importante de téléphonie (trois ou plus RTPC appels par utilisateur par heure) doivent allouer un port pour cinq utilisateurs. Par exemple, si vous avez des 47,000 utilisateurs, vous aurez besoin d’un total de 9,400 ports répartie entre au moins 10 passerelles de grande taille.
    
- Ports supplémentaires peuvent être posés que le nombre d’utilisateurs ou de la quantité de trafic augmente de votre organisation.
    
Pour un nombre donné d’utilisateurs, que vous devez prendre en charge, vous avez la possibilité de déployer des passerelles moins nombreuses et plus grandes ou petites. En règle générale, un minimum de deux passerelles pour une organisation est recommandé pour maintenir la disponibilité en cas de défaillance d’une passerelle. 
  
Chaque passerelle PSTN que vous déployez doit avoir au moins un serveur de médiation correspondant.
  

