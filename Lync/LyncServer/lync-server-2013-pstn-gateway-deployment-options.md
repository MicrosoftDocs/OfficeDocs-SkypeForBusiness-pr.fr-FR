---
title: 'Lync Server 2013 : Options de déploiement de passerelle RTC'
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
ms.openlocfilehash: 5b2f3cd153a6dc8d101f44a3f087f0ccedfa9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Options de déploiement de passerelle RTC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>Passerelles RTC

Les passerelles de réseau téléphonique commuté (PSTN) sont des composants matériels tiers qui convertissent le signalement et le contenu multimédia entre l’infrastructure vocale d’entreprise et le RTC, directement ou par le biais d’une connexion de lignes SIP. Dans chaque topologie, la passerelle arrête le RTC. La passerelle est isolée dans son propre sous-réseau et est connectée au réseau d’entreprise par le biais du serveur de médiation.

En règle générale, une entreprise avec plusieurs sites déploie une ou plusieurs passerelles sur chaque site. Les sites de succursale peuvent se connecter au RTC par le biais d’une passerelle ou d’une unité de branchement survivant qui combine les passerelles et les serveurs dans une seule boîte. Si les sites de succursales utilisent une passerelle, un serveur d’inscription et de médiation sont requis sur le site, sauf si la liaison WAN est résiliente. Un ou plusieurs serveurs de médiation, qui sont colocalisés sur des serveurs frontaux, peuvent router les appels pour les passerelles d’une ou plusieurs sur chaque site. Nous vous recommandons d’utiliser le Bureau d’enregistrement, le serveur de médiation et la passerelle requis sur le site comme une unité de branchement Survivable.

Le nombre, la taille et l’emplacement des passerelles RTC est peut-être la décision la plus importante et onéreuse lors de la planification de l’infrastructure vocale de votre entreprise.

Voici les principales questions à prendre en considération. Gardez à l’esprit que les réponses à ces questions sont interdépendantes.

  - Combien de passerelles RTC sont-elles nécessaires ? La réponse dépend du nombre d’utilisateurs, du nombre d’appels simultanés (chargement du trafic) et du nombre de sites (chaque site en nécessite une).

  - Quelle est la taille des passerelles ? La réponse dépend du nombre d’utilisateurs au niveau du site et du chargement du trafic.

  - Où se trouvent les passerelles ? La réponse dépend en partie de la topologie et en partie de la distribution géographique de votre organisation.

Vous devez également tenir compte des options de topologie de votre passerelle (pour plus de détails, voir topologies de passerelle plus loin dans cette rubrique).

<div>

## <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Les serveurs de médiation peuvent acheminer les appels par le biais de plusieurs passerelles, contrôleurs de frontière de session (SBCs) fournis par des fournisseurs de services de téléphonie Internet ou d’une combinaison des deux. Par ailleurs, plusieurs serveurs de médiation du pool peuvent interagir avec plusieurs passerelles. L’itinéraire logique défini entre un serveur de médiation et une passerelle est appelé *Trunk*. Lorsqu’un utilisateur interne place un appel RTC, la logique de routage sortante du pool frontal détermine le Trunk à transférer au-delà de toutes les combinaisons possibles qui peuvent être disponibles pour le routage d’un appel particulier. En cas d’équilibrage de la charge DNS, si un appel ne parvient pas à accéder à une passerelle en raison d’un problème lié à un serveur de médiation particulier dans le pool, l’appel est répété vers un autre serveur de médiation du pool.

Pour plus d’informations sur la planification de plusieurs passerelles, voir [M :N Trunk dans Lync Server 2013](lync-server-2013-m-n-trunk.md).

Pour plus d’informations sur les autres améliorations du routage sortant, voir [itinéraires vocaux dans Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Topologies de passerelle

Lorsque vous prenez en considération les questions fondamentales du déploiement de la passerelle, procédez comme suit :

1.  Déterminez les sites pour lesquels vous souhaitez fournir une connectivité PSTN en utilisant Enterprise Voice.

2.  Évaluez le trafic sur chaque site (nombre d’utilisateurs et nombre moyen d’appels par heure par utilisateur).

3.  Déploiement d’une ou plusieurs passerelles sur chaque site pour gérer le trafic anticipé.

La topologie de passerelle distribuée qui en résulte est illustrée dans la figure suivante.

**Topologie de passerelle distribuée**

![Diagramme de topologie de passerelle distribuée](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagramme de topologie de passerelle distribuée")

Avec cette topologie, les appels entre les travailleurs sur chaque site et entre les sites sont tous routés par le biais de votre intranet. Les appels vers le RTC sont routés via le réseau IP d’entreprise vers les passerelles les plus proches de l’emplacement des numéros de destination. Mais si votre organisation prend en charge des douzaines ou des centaines, voire des milliers de sites disséminés sur un ou plusieurs continents, le nombre d’institutions financières et d’autres grandes entreprises est important. Dans ce cas, le déploiement d’une passerelle séparée sur chaque site n’est pas pratique.

Pour résoudre ce problème, de nombreuses entreprises de grande taille préfèrent le déploiement d’un ou de plusieurs sites centraux de téléphonie de grande taille, comme illustré dans la figure ci-dessous.

**Topologie de site central de téléphonie**

![Topologie de la passerelle du centre de données](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologie de la passerelle du centre de données")

Dans cette topologie, plusieurs passerelles de grande taille suffisantes pour s’adapter à la charge d’utilisateurs prévue sont déployées sur chaque site central. Tous les appels vers des utilisateurs au sein de l’entreprise sont transférés par le fournisseur de services de téléphonie de l’entreprise à un site central. La logique de routage sur le site central détermine si l’appel doit être routé par le biais de l’intranet ou du RTC.

</div>

<div>

## <a name="gateway-location"></a>Emplacement de la passerelle

L’emplacement de la passerelle détermine également les types de passerelles que vous choisissez et la manière dont ils sont configurés. Il existe des dizaines de protocoles RTC qui ne constituent aucune norme internationale. S’il ne s’agit pas de votre passerelle, il n’y a pas de problème, mais si vous trouvez des passerelles dans plusieurs pays/régions, chacune d’elles doit être configurée conformément aux normes RTC de ce pays/cette région. Par ailleurs, les passerelles certifiées pour le fonctionnement, par exemple le Canada, peuvent ne pas être certifiées en Inde, au Brésil ou en Union européenne.

</div>

<div>

## <a name="gateway-size-and-number"></a>Taille et nombre de la passerelle

Les passerelles RTC dont la plupart des organisations envisageront de déployer la plage de 2 à la taille des ports 960. (Il y a encore plus de passerelles, mais elles sont principalement utilisées par les fournisseurs de services de téléphonie.) Lorsque vous évaluez le nombre de ports requis par votre organisation, vous devez suivre les instructions suivantes :

  - Les organisations ayant une utilisation du service de téléphonie léger (un appel RTC par utilisateur par heure) doivent allouer un port pour tous les 15 utilisateurs. Par exemple, si vous avez 20 utilisateurs, vous aurez besoin d’une passerelle avec deux ports.

  - Les organisations présentant une utilisation modérée de la téléphonie (deux appels RTC par utilisateur et par heure) doivent allouer un port pour chaque 10 utilisateurs. Par exemple, si vous avez des utilisateurs 100, vous aurez besoin d’un total de 10 ports alloués à une ou plusieurs passerelles.

  - Les organisations ayant une utilisation importante de la téléphonie (au moins trois appels RTC par utilisateur et par heure) doivent allouer un port pour chaque cinquième utilisateur. Par exemple, si vous avez des utilisateurs 47 000, vous aurez besoin d’un total de ports 9 400 alloués entre au moins 10 passerelles de grande taille.

  - Des ports supplémentaires peuvent être acquis au fur et à mesure de l’augmentation du nombre d’utilisateurs ou du volume de trafic au sein de votre organisation.

Pour tout nombre d’utilisateurs que vous devez prendre en charge, vous avez le choix entre le déploiement de plus petit, de passerelles plus grandes ou plus petites. En règle générale, un minimum de deux passerelles pour une organisation est recommandé pour garantir la disponibilité en cas d’échec d’une passerelle.

Chaque passerelle RTC que vous déployez doit avoir au moins un serveur de médiation correspondant.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

