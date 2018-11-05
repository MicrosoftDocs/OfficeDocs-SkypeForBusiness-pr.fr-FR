---
title: Présentation de la conférence A/V dans Lync Server 2013
TOCTitle: Présentation de la conférence A/V dans Lync Server 2013
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49298121
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation de la conférence A/V dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La conférence A/V permet d’établir des communications audio et vidéo en temps réel entre vos utilisateurs. Lorsque vous déployez la conférence, vous pouvez choisir d’activer et d’utiliser la conférence web et la conférence A/V, ou uniquement la conférence web.

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de média de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique.

Avant d’activer les utilisateurs pour la conférence A/V, assurez-vous que votre réseau est en mesure de gérer la charge qui en résulte. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur. Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V. Ceci est important pour les réseaux restreints, tels que les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, voir [Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Pour plus d’informations sur les exigences de bande passante multimédia, voir [Configuration requise de la bande passante pour le trafic multimédia dans Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio tels que des casques pour y prendre part. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo tels que des webcams pour les utilisateurs. Nous vous recommandons d’utiliser des périphériques de communications unifiées (UC) certifiés par Microsoft pour tous les types de périphériques, afin de garantir des performances optimales à l’utilisateur. Pour plus d’informations sur les périphériques certifiés UC, voir « Téléphones et périphériques pour Lync » à l’adresse [http://go.microsoft.com/fwlink/?linkid=263861\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=263861%26clcid=0x40c). Pour les périphériques audio ou vidéo, le déploiement des périphériques et la formation des utilisateurs sont des étapes importantes qu’il convient de planifier soigneusement.

Les sections suivantes décrivent les fonctionnalités de conférence audio et vidéo et fournissent des informations sur la gestion de la bande passante et la sélection de clients appropriés.

## Fonctionnalités d’audioconférence

Lync Server 2013 fournit plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’expérience d’audioconférence de l’utilisateur, parmi lesquelles :

  - **Désactivation du micro des participants**   Le présentateur peut utiliser ce paramètre pour désactiver le micro de tous les participants audio de la conférence et placer celle-ci dans un état où les personnes qui ne sont pas des présentateurs ne peuvent pas réactiver leur micro.

  - **Annonces d’entrée/sortie de conférence**   Si vous avez activé la conférence rendez-vous, les présentateurs peuvent utiliser ce paramètre pour activer ou désactiver les annonces d’entrée et de sortie afin de limiter les distractions durant une conférence.

  - **Ajout d’un utilisateur à l’aide d’un appel sortant**   Les présentateurs et participants qui disposent de cette autorisation peuvent ajouter des numéros PSTN aux conférences et faire en sorte qu’une conférence compose ces numéros.

## Fonctionnalités de visioconférence

Lync Server 2013 fournit plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’expérience de visioconférence de l’utilisateur, parmi lesquelles :

  - **Vue Galerie**   Dans les visioconférences qui comportent plus de deux personnes, les utilisateurs voient automatiquement tous les participants à la conférence. Si celle-ci comporte plus de cinq participants, la vidéo des participants les plus actifs apparaît sur la ligne supérieure et seule la photo apparaît pour les autres participants. La vidéo à plusieurs est activée par défaut. Pour plus d’informations sur la configuration ou la désactivation de la vidéo à plusieurs, voir [Configuration de la bande passante vidéo dans Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vidéo panoramique**   Si un périphérique de visioconférence RoundTable est installé dans la salle de conférence, cette fonctionnalité offre une vue à 360 degrés de la salle de conférence. Le clip vidéo panoramique est disponible uniquement avec les périphériques RoundTable.

  - **Mode vidéo Présentateur uniquement**   Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo du présentateur soit affichée. Ceci empêche toute distraction lors des réunions à grande échelle, lorsque plusieurs flux vidéo sont disponibles et verrouillés à différentes sources. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable.

  - **Vidéo HD** Les utilisateurs peuvent avoir des résolutions pouvant aller jusqu’à 1080 p HD dans les appels à deux et les conférences à plusieurs.

  - **Vidéo à la une**   Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo d’un participant sélectionné qui est une source vidéo soit visible par les autres participants à la conférence. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable pour la vidéo panoramique.

