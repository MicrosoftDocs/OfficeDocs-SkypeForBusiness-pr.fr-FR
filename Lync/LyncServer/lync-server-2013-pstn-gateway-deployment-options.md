---
title: 'Lync Server 2013 : options de déploiement de la passerelle PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2761473e609f8891af14387858ca76bc2a247baa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512461"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Options de déploiement de passerelle PSTN dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>Passerelles PSTN

Les passerelles du réseau téléphonique commuté (PSTN) sont des composants matériels tiers qui convertissent la signalisation et les médias entre l’infrastructure Voix Entreprise et le réseau téléphonique commuté, directement ou via une connexion à des jonctions SIP. Quelle que soit la topologie utilisée, la passerelle permet le raccordement au réseau téléphonique commuté. La passerelle est isolée dans son propre sous-réseau et est connectée au réseau d’entreprise via le serveur de médiation.

Une entreprise constituée de plusieurs sites déploie généralement une ou plusieurs passerelles sur chaque site. Les sites de succursale peuvent se connecter au RTC par le biais d’une passerelle ou d’un Survivable Branch appliance qui combine passerelle et serveurs dans un seul et même boîtier. Si les sites de succursale utilisent une passerelle, un serveur d’inscriptions et de médiation est requis sur le site, sauf si la liaison de réseau étendu est résiliente. Un ou plusieurs serveurs de médiation, colocalisés sur des serveurs frontaux, peuvent acheminer les appels pour une ou plusieurs passerelles de chaque site. Nous vous recommandons de déployer le serveur d’inscriptions, le serveur de médiation et la passerelle requis sur site sous la forme d’un Survivable Branch appliance.

Il est peut-être nécessaire de déterminer le nombre, la taille et l’emplacement des passerelles PSTN lors de la planification de votre infrastructure voix entreprise.

Voici les principales questions à se poser. N’oubliez pas que les réponses à ces questions sont toutes interdépendantes.

  - Combien de passerelles PSTN sont nécessaires ? La réponse dépend du nombre d’utilisateurs, du nombre anticipé d’appels simultanés (charge du trafic) et du nombre de sites (chaque site a besoin d’une passerelle).

  - Quelle doit être la taille des passerelles ? La réponse dépend du nombre d’utilisateurs sur le site et de la charge du trafic.

  - Quel doit être l’emplacement des passerelles ? La réponse dépend en partie de la topologie et de la répartition géographique de votre entreprise.

Vous devriez également tenir compte des options au niveau de la topologie de votre passerelle (pour plus d’informations, voir la section Topologies de passerelles plus loin dans cette rubrique).

<div>

## <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Les serveurs de médiation peuvent acheminer les appels via des passerelles multiples, des contrôleurs de frontière de session (SBC) fournis par des fournisseurs de services de téléphonie Internet ou une combinaison des deux. De plus, plusieurs serveurs de médiation dans le pool peuvent interagir avec plusieurs passerelles. L’itinéraire logique défini entre un serveur de médiation et une passerelle est appelé *jonction*. Lorsqu’un utilisateur interne passe un appel RTC, la logique de routage sortant sur le pool frontal choisit la jonction à acheminer en dehors de toutes les combinaisons possibles pouvant être disponibles pour le routage de cet appel particulier. Avec l’équilibrage de la charge DNS, si un appel ne parvient pas à joindre une passerelle en raison d’un problème avec un serveur de médiation particulier dans le pool, l’appel sera retenté sur un autre serveur de médiation du pool.

Pour plus d’informations sur la planification de plusieurs passerelles, voir [M :N jonction dans Lync Server 2013](lync-server-2013-m-n-trunk.md).

Pour plus d’informations sur les autres améliorations de routage sortant, consultez la rubrique [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Topologies de passerelles

Quand vous examinez les questions fondamentales relatives au déploiement des passerelles, procédez comme suit :

1.  Comptez les sites à partir desquels vous souhaitez fournir la connectivité PSTN à l’aide de voix entreprise.

2.  Évaluez le trafic sur chacun d’eux (nombre d’utilisateurs et nombre moyen d’appels par heure et par utilisateur).

3.  Déployez une ou plusieurs passerelles sur chaque site pour gérer le trafic prévu.

La topologie de passerelles distribuées résultante est présentée à la figure suivante.

**Topologie de passerelles distribuées**

![Diagramme de topologie de passerelle distribuée](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagramme de topologie de passerelle distribuée")

Avec cette topologie, les appels entre collaborateurs sur chaque site et entre les sites sont tous routés sur votre intranet. Les appels qui parviennent au réseau téléphonique commuté sont routés sur le réseau IP de l’entreprise vers les passerelles les plus proches de l’emplacement des numéros de destination. Mais que se passe-t-il si votre entreprise prend en charge des douzaines ou des centaines, voire des milliers de sites répartis sur plusieurs continents, comme c’est le cas de nombreuses institutions financières et grandes entreprises ? Dans ces cas, le déploiement d’une passerelle distincte sur chaque site n’est pas pratique.

Pour résoudre ce problème, de nombreuses grandes entreprises préfèrent déployer un ou quelques grands sites centraux de téléphonie, comme illustré dans la figure suivante.

**Topologie des sites centraux de téléphonie**

![Topologie de passerelle du centre de données](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologie de passerelle du centre de données")

Dans cette topologie, plusieurs grandes passerelles sont suffisantes pour s’accommoder de la charge utilisateur prévue sont déployées sur chaque site central. Tous les appels à destination des utilisateurs de l’entreprise sont transmis par le fournisseur de services téléphoniques de la société vers un site central. La logique de routage sur le site central détermine si l’appel doit être acheminé via l’intranet ou le RTC.

</div>

<div>

## <a name="gateway-location"></a>Emplacement de la passerelle

L’emplacement de la passerelle peut également déterminer les types de passerelles que vous choisissez et leur configuration. Il existe des douzaines de protocoles PSTN, dont aucun n’est un standard mondial. Si toutes vos passerelles se situent dans un seul pays ou une seule région, cela n’est pas un problème, mais si vous les placez dans plusieurs pays/régions, chacune d’elles doit être configurée en fonction des normes PSTN du pays ou de la région. De plus, les passerelles qui sont certifiées pour fonctionner, par exemple, au Canada, peuvent ne pas être certifiées en Inde, au Brésil ou dans l’Union européenne.

</div>

<div>

## <a name="gateway-size-and-number"></a>Taille et nombre des passerelles

La taille des passerelles PSTN que la plupart des entreprises envisagent de déployer peut aller de 2 et 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.) Lors de l’estimation du nombre de ports requis dans votre entreprise, suivez les instructions suivantes :

  - Les entreprises dont l’utilisation de la téléphonie est faible (un appel PSTN par utilisateur et par heure) doivent allouer un port pour 15 utilisateurs. Par exemple, si votre entreprise regroupe 20 utilisateurs, vous avez besoin d’une passerelle dotée de deux ports.

  - Les entreprises dont l’utilisation de la téléphonie est modérée (deux appels PSTN par utilisateur et par heure) doivent allouer un port pour 10 utilisateurs. Par exemple, si votre entreprise regroupe 100 utilisateurs, vous avez besoin d’un total de 10 ports alloués sur une ou plusieurs passerelles.

  - Les entreprises dont l’utilisation de la téléphonie est forte (trois appels PSTN ou plus par utilisateur et par heure) doivent allouer un port pour cinq utilisateurs. Par exemple, si votre entreprise regroupe 47 000 utilisateurs, vous avez besoin d’un total de 9 400 ports alloués sur au moins 10 passerelles de grande envergure.

  - D’autres ports peuvent être acquis à mesure que le nombre d’utilisateurs ou la quantité de trafic augmente dans votre entreprise.

Pour un nombre donné d’utilisateurs à prendre en charge, vous pouvez choisir de déployer plusieurs passerelles de petite taille, ou bien un nombre inférieur de passerelles de grande taille. En règle générale, il est recommandé d’installer au moins deux passerelles dans l’entreprise pour garantir la disponibilité en cas de panne de l’une d’elles.

Chaque passerelle PSTN que vous déployez doit disposer d’au moins un serveur de médiation correspondant.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

