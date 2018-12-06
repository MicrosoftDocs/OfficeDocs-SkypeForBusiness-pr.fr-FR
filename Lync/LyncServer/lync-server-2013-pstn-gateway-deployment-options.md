---
title: 'Lync Server 2013 : Options de déploiement de passerelle RTC'
TOCTitle: Options de déploiement de passerelle RTC
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398899(v=OCS.15)
ms:contentKeyID: 49298913
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Options de déploiement de passerelle RTC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

## Passerelles RTC

Les passerelles RTC (réseau téléphonique commuté) sont des composants matériels tiers qui convertissent la signalisation et les médias entre l’infrastructure Voix Entreprise et le réseau téléphonique commuté, directement ou via une connexion à des jonctions SIP. Quelle que soit la topologie utilisée, la passerelle permet le raccordement au réseau téléphonique commuté. La passerelle est isolée dans son propre sous-réseau et est connectée au réseau de l’entreprise via le serveur de médiation.

Une entreprise constituée de plusieurs sites déploie généralement une ou plusieurs passerelles sur chaque site. Les sites de succursale peuvent se connecter au RTC via une passerelle ou via un Survivable Branch Appliance qui regroupe la passerelle et les serveurs dans un unique boîtier. Si des sites de succursale utilisent une passerelle, il est nécessaire d’installer un serveur d’inscriptions et un serveur de médiation sur le site, sauf si la liaison de réseau étendu est résistante. Un ou plusieurs serveurs de médiation, colocalisés sur des serveurs frontaux, peuvent acheminer les appels pour une ou plusieurs passerelles, sur chaque site. Nous recommandons de déployer le serveur d’inscriptions, le serveur de médiation et la passerelle requis sur le site en tant que Survivable Branch Appliance.

Déterminer le nombre, la taille et l’emplacement des passerelles RTC est peut-être la décision la plus importante et la plus coûteuse que vous devrez prendre lors de la planification de votre infrastructure Voix Entreprise.

Voici les principales questions à se poser. N’oubliez pas que les réponses à ces questions sont toutes interdépendantes.

  - Combien de passerelles RTC sont nécessaires ? La réponse dépend du nombre d’utilisateurs, du nombre anticipé d’appels simultanés (charge du trafic) et du nombre de sites (chaque site a besoin d’une passerelle).

  - Quelle doit être la taille des passerelles ? La réponse dépend du nombre d’utilisateurs sur le site et de la charge du trafic.

  - Quel doit être l’emplacement des passerelles ? La réponse dépend en partie de la topologie et de la répartition géographique de votre entreprise.

Vous devriez également tenir compte des options au niveau de la topologie de votre passerelle (pour plus d’informations, reportez-vous à la section Topologies de passerelles dans la suite de cette rubrique).

## M:N Prise en charge des jonctions

Les serveurs de médiation peuvent acheminer les appels via plusieurs passerelles, via plusieurs contrôleurs de frontière de session fournis par les fournisseurs de services de téléphonie Internet ou via une combinaison des deux. De plus, plusieurs serveurs de médiation du pool peuvent interagir avec plusieurs passerelles. L’acheminement logique défini entre un serveur de médiation et la passerelle est appelée une *jonction* . Quand un utilisateur interne passe un appel RTC, la logique de routage du trafic sortant sur le pool de serveurs frontaux sélectionne la jonction via laquelle le trafic est acheminé parmi toutes les combinaisons possibles disponibles pour l’acheminement de cet appel. Avec l’équilibrage de la charge DNS, si un appel n’atteint pas une passerelle en raison d’un problème avec un serveur de médiation du pool, une nouvelle tentative d’appel sera émise vers un autre serveur de médiation du pool.

Pour plus d’informations sur la planification de plusieurs passerelles, reportez-vous à [Jonction M:N dans Lync Server 2013](lync-server-2013-m-n-trunk.md).

Pour plus d’informations sur les autres améliorations apportées au routage du trafic sortant, reportez-vous à [Itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-voice-routes.md).

## Topologies de passerelles

Quand vous examinez les questions fondamentales relatives au déploiement des passerelles, procédez comme suit :

1.  Comptez les sites que vous souhaitez connecter au réseau RTC en utilisant Voix Entreprise.

2.  Évaluez le trafic sur chacun d’eux (nombre d’utilisateurs et nombre moyen d’appels par heure et par utilisateur).

3.  Déployez une ou plusieurs passerelles sur chaque site pour gérer le trafic prévu.

La topologie de passerelles distribuées résultante est présentée à la figure suivante.

**Topologie de passerelles distribuées**

![Diagramme de topologie de passerelle distribuée](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagramme de topologie de passerelle distribuée")

Avec cette topologie, les appels entre collaborateurs sur chaque site et entre les sites sont tous routés sur votre intranet. Les appels qui parviennent au réseau téléphonique commuté sont routés sur le réseau IP de l’entreprise vers les passerelles les plus proches de l’emplacement des numéros de destination. Mais que se passe-t-il si votre entreprise prend en charge des douzaines ou des centaines, voire des milliers de sites répartis sur plusieurs continents, comme c’est le cas de nombreuses institutions financières et grandes entreprises ? Dans ces cas, le déploiement d’une passerelle distincte sur chaque site n’est pas pratique.

Pour résoudre ce problème, de nombreuses grandes entreprises préfèrent déployer des sites centraux importants, comme illustré dans la figure suivante.

**Topologie des sites centraux de téléphonie**

![Topologie de passerelle de centre de données](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologie de passerelle de centre de données")

Dans cette topologie, plusieurs passerelles de grande taille, suffisantes pour gérer la charge anticipée pour les utilisateurs, sont déployées sur chaque site central. Tous les appels à destination des utilisateurs de l’entreprise sont transmis par le fournisseur de services téléphoniques de la société vers un site central. La logique de routage définie sur le site central détermine si l’appel doit être routé sur l’intranet ou vers le réseau téléphonique commuté.

## Emplacement de la passerelle

L’emplacement de la passerelle peut également déterminer les types de passerelles que vous choisissez et leur configuration. Il existe des douzaines de protocoles RTC, dont aucun n’est un standard mondial. Si toutes vos passerelles se situent dans un seul pays ou une seule région, cela n’est pas un problème, mais si vous les placez dans plusieurs pays/régions, chacune d’elles doit être configurée en fonction des normes RTC du pays ou de la région. De plus, les passerelles certifiées pour fonctionner, par exemple, au Canada, peuvent ne pas être certifiées en Inde, au Brésil ou dans l’Union européenne.

## Taille et nombre des passerelles

La taille des passerelles RTC que la plupart des entreprises envisagent de déployer peut aller de 2 et 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.) Lors de l’estimation du nombre de ports requis dans votre entreprise, suivez les instructions suivantes :

  - Les entreprises dont l’utilisation de la téléphonie est faible (un appel RTC par utilisateur et par heure) doivent allouer un port pour 15 utilisateurs. Par exemple, si votre entreprise regroupe 20 utilisateurs, vous avez besoin d’une passerelle dotée de deux ports.

  - Les entreprises dont l’utilisation de la téléphonie est modérée (deux appels RTC par utilisateur et par heure) doivent allouer un port pour 10 utilisateurs. Par exemple, si votre entreprise regroupe 100 utilisateurs, vous avez besoin d’un total de 10 ports alloués sur une ou plusieurs passerelles.

  - Les entreprises dont l’utilisation de la téléphonie est forte (trois appels RTC ou plus par utilisateur et par heure) doivent allouer un port pour cinq utilisateurs. Par exemple, si votre entreprise regroupe 47 000 utilisateurs, vous avez besoin d’un total de 9 400 ports alloués sur au moins 10 passerelles de grande envergure.

  - D’autres ports peuvent être acquis à mesure que le nombre d’utilisateurs ou la quantité de trafic augmente dans votre entreprise.

Pour un nombre donné d’utilisateurs à prendre en charge, vous pouvez choisir de déployer plusieurs passerelles de petite taille, ou bien un nombre inférieur de passerelles de grande taille. En règle générale, il est recommandé d’installer au moins deux passerelles dans l’entreprise pour garantir la disponibilité en cas de panne de l’une d’elles.

Chaque passerelle RTC que vous déployez doit comporter au moins un serveur de médiation correspondant.

