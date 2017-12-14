---
title: "Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/21/2016
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
description: "Cette rubrique définit les conditions de performances du réseau pour les services Skype Entreprise Online et indique comment vous pouvez opter pour l'utilisation d'Internet ou d'ExpressRoute pour établir une connectivité entre votre réseau et Skype Entreprise Online en fonction de votre évaluation de la connectivité réseau. Si vous avez décidé de déployer Azure ExpressRoute pour bénéficier d'une connectivité dédiée à Office 365, ce document fournit également des instructions de planification des connexions ExpressRoute selon différents scénarios de déploiement de Skype Entreprise Online."
---

# Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online

Cette rubrique définit les conditions de performances du réseau pour les services Skype Entreprise Online et indique comment vous pouvez opter pour l'utilisation d'Internet ou d'ExpressRoute pour établir une connectivité entre votre réseau et Skype Entreprise Online en fonction de votre évaluation de la connectivité réseau. Si vous avez décidé de déployer Azure ExpressRoute pour bénéficier d'une connectivité dédiée à Office 365, ce document fournit également des instructions de planification des connexions ExpressRoute selon différents scénarios de déploiement de Skype Entreprise Online.
  
La qualité multimédia en temps réel (audio, vidéo et partage d'applications) sur IP est largement impactée par la qualité de la connectivité réseau de bout en bout. Pour bénéficier d'une qualité optimale pour Skype Entreprise Online, assurez-vous de la bonne qualité de la connexion entre votre réseau d'entreprise et Skype Entreprise Online. La meilleure façon d'y parvenir est de configurer la connectivité du réseau interne et du cloud en fonction de la capacité de votre réseau à s'adapter au volume du trafic maximal de Skype Entreprise Online sur l'ensemble des connexions.
  
Azure ExpressRoute n'est pas obligatoire pour les services Office 365, dont Skype Entreprise Online. Cependant, Azure ExpressRoute est l'une des options de déploiement mises à votre disposition pour assurer que la connectivité à Office 365 réponde aux exigences de performance réseau de Skype Entreprise, et garantir une qualité multimédia optimale avec Skype Entreprise Online.
  
> [!TIP]
> Bien que cette rubrique fournisse des informations d'ordre général sur l'amélioration des performance réseau, elle n'a pas pour objet de fournir des instructions complètes d'évaluation du réseau. Pour obtenir la liste des partenaires Skype Entreprise Online qui peuvent vous aider à mesurer les performances réseau dans le cadre d'une évaluation du réseau approfondie et complète, visitez [Solutions pour partenaires Skype Entreprise](http://partnersolutions.skypeforbusiness.com/). 
  
## Conditions requises de connectivité réseau pour Skype Entreprise Online

### Facteurs impactant la qualité multimédia de Skype Entreprise Online

De nombreux facteurs contribuent à la qualité multimédia en temps réel (audio, vidéo et partage d'applications), dont notamment les dispositifs utilisés, l'environnement et la connectivité réseau. 
  
#### Périphériques

Dans une session de média en temps réel, les périphériques de capture et d'affichage utilisés par tous les participants, tels que des casques et des webcams, ont un fort impact sur la qualité audio et vidéo globale. Les périphériques de qualité inférieure ou dont les pilotes sont incorrects produiront globalement des sons et des images de moins bonne qualité. Les périphériques certifiés ou de bonne qualité, en revanche, améliorent l'annulation d'écho, le filtrage du bruit et la résolution vidéo, et réduisent les temps de latence.
  
Bien qu'aucun périphérique multimédia audio et vidéo certifié ne soit obligatoire, il est vivement recommandé d'utiliser des périphériques certifiés pour Skype Entreprise Online pour garantir une expérience optimale. Pour obtenir la liste des périphériques recommandés pour Skype Entreprise, voir [Téléphones et périphériques pour Skype Entreprise](https://technet.microsoft.com/en-us/office/dn947482). Vous pouvez utiliser le [tableau de bord de qualité d'appel Skype Entreprise Online](https://support.office.com/en-us/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c?ui=en-US&amp;rs=en-US&amp;ad=US), accessible dans le ** centre d'administration Skype Entreprise**, pour vérifier que les périphériques utilisés fonctionnent correctement et surveiller la qualité multimédia audio et vidéo.
  
> [!TIP]
> **Un périphérique certifié est requis pour garantir une qualité multimédia optimale sur Skype Entreprise**.
  
Il est important de savoir que tous les périphériques multimédia, les clients et les serveurs Skype Entreprise par lesquels les médias passent engendrent une certaine quantité de temps de latence. La latence du traitement matériel et logiciel associée à la latence du réseau ont un fort impact sur la latence globale de bout en bout, à laquelle elles contribuent, mais aussi sur l'expérience utilisateur.
  
#### Environnement

L'environnement des locaux dans lesquels les utilisateurs se rencontrent et utilisent des périphériques audio et vidéo est un autre facteur important pour la qualité audio et vidéo. Les utilisateurs qui appellent à partir d'un environnement bruyant produiront des échos et un son audio sourd et difficilement audible. Les utilisateurs dans un environnement sombre ou de luminosité faible ne seront pas en mesure de produire une qualité d'image lumineuse et nette pour la vidéo. Dans une salle de conférence, l'emplacement du microphone et du périphérique vidéo ont un impact direct sur la qualité du son et de l'image que les participants recevront.
  
Pour améliorer l'expérience audio et vidéo d'un utilisateur, dans Skype Entreprise, sélectionnez **Outils** > **Options** > **Périphérique audio** ou **Périphérique vidéo** pour modifier le périphérique utilisé et personnaliser ses paramètres. Vous pouvez également vérifier la qualité audio d'un appel en cliquant sur **Vérifier la qualité de l'appel**. L'option **Vérifier la qualité de l'appel** indique la qualité et les problèmes détectés lors de l'appel de test.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### Réseau

La qualité multimédia en temps réel sur le réseau IP est fortement affectée par la qualité de la connectivité du réseau, mais surtout par la quantité de :
  
- **Latence** Il s'agit du temps nécessaire à un paquet IP pour passer d'un point A à un point B sur le réseau. Ce retard de propagation sur le réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, à laquelle s'ajoute la surcharge des divers routeurs intermédiaires. La latence se mesure en durée unidirectionnelle ou durée de l'aller-retour (Round-trip Time, RTT).
    
- **Perte de paquets** Souvent définie comme le pourcentage de paquets perdus dans un laps de temps donné. La perte de paquets influe directement sur la qualité audio, de petits paquets individuels perdus, pratiquement sans impact, aux pertes en rafale dos-à-dos à l'origine de coupures audio complètes.
    
- **Gigue entre les arrivées de paquets ou simplement gigue** Il s'agit de la variation moyenne de délai entre les paquets successifs. La plupart des logiciels de VoIP modernes, dont Skype Entreprise, peuvent s'adapter à certains niveaux de gigue à l'aide de tampons. C'est seulement lorsque la gigue est supérieure au tampon qu'un participant constatera une instabilité.
    
> [!NOTE]
> La mise en tampon destinée à lutter contre la gigue augmente la latence de bout en bout. 
  
Lorsque le nombre de sessions média en temps réel simultanées de Skype Entreprise est élevé et vient s'ajouter au trafic réseau généré par d'autres services Office 365 et d'autres applications d'entreprise, il est essentiel de vous assurer que la bande passante est suffisante sur l'intégralité du chemin réseau qui relie votre réseau à Skype Entreprise Online. Vous évitez ainsi les encombrements du réseau et assurez l'excellence de la qualité multimédia en temps réel (audio, vidéo et partage d'applications). 
  
#### Mise en œuvre de la qualité de service (QoS) sur des réseaux encombrés

En outre, l'encombrement du trafic sur un réseau impacte considérablement la qualité multimédia. Pour autoriser les paquets audio et vidéo à se déplacer plus rapidement sur le réseau et à être prioritaires sur tout autre trafic sur un réseau encombré, la qualité de service (QoS) peut aider à mettre en place une expérience utilisateur optimale pour les communications audio et vidéo.
  
QoS vous permet d'attribuer une priorité plus élevée aux paquets réseau qui transportent des données audio ou vidéo. Le fait d'affecter une priorité supérieure à ces paquets permet aux communications audio et vidéo de s'effectuer plus rapidement, et avec moins d'interruption, que les sessions réseau impliquant des opérations telles que des transferts de fichiers, de la navigation web ou des sauvegardes de bases de données. En effet, les paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données par défaut bénéficient d'une priorité « meilleur effort » et l'impact de l'encombrement du réseau est alors atténué. Si vous n'attribuez pas une priorité plus élevée aux paquets multimédia (audio, vidéo et partage d'applications) et les laissez également en priorité « meilleur effort », ils seront aussi traités avec le reste du trafic réseau. En fonction de l'encombrement du réseau, cela risque potentiellement d'engendrer une baisse de la qualité audio et vidéo pour vos utilisateurs.
  
Il est vivement recommandé d'implémenter QoS sur votre réseau pour vous assurer que l'encombrement du réseau au sein de votre réseau n'aura aucun impact. Cependant, pour que cela ait un impact maximum, tous les terminaux de réseau doivent prendre en charge QoS. Cela signifie qu'ils doivent tous tenir compte du marquage et de la hiérarchisation QoS au sein du réseau Microsoft. Cependant, le trafic acheminé via une connexion publique telle qu'Internet entre votre réseau d'entreprise et le réseau Microsoft ne conserve pas le marquage et les priorités QoS. Les connexions privées entre votre réseau et Office 365 qui utilisent [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) constituent une solution de déploiement qui conserve les marquages et la hiérarchisation QoS et augmente donc la qualité audio et vidéo globale pour vos utilisateurs.
  
## Conditions requises de performances réseau pour une connexion à Skype Entreprise Online
<a name="bk_NetworkPerf"> </a>

Les médias en temps réel de Skype Entreprise passent par un grand nombre de périphériques, d'applications client, de logiciels serveurs et de réseaux. La latence de bout en bout des médias en temps réel est la quantité totale de latence survenant sur l'ensemble des composants et des segments de réseau. La qualité de la connexion réseau de bout en bout est déterminée par le segment de réseau présentant la moins bonne qualité. Ce segment agit comme un goulot d'étranglement pour ce trafic réseau.
  
Le schéma suivant représente le flux audio unidirectionnel d'une conférence entre un participant Skype Entreprise et un autre.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Dans ce scénario de téléconférence, le chemin multimédia est constitué des segments réseau suivants :
  
1. **Connexion de l'utilisateur 1 au périmètre du réseau Microsoft** Celle-ci comprend généralement une connexion réseau telle que WiFi ou Ethernet, la connexion WAN de l'utilisateur 1 au point de sortie d'Internet (votre périphérique de périmètre réseau) et la connexion Internet entre le périmètre de votre réseau et celui du réseau Microsoft.
    
2. **Connexion au sein du réseau Microsoft** Établie entre le périmètre Microsoft et le centre de données Skype Entreprise Online dans lequel les serveurs de téléconférence A/V sont utilisés.
    
3. **Connexion au sein du réseau Microsoft** Établie entre le centre de données Skype Entreprise et le réseau de périmètre Microsoft.
    
4. **Connexion entre le réseau de périmètre Microsoft et l'utilisateur 2** Inclut la connexion entre votre réseau de périmètre et celui de Microsoft, la connexion WAN entre l'utilisateur 2 et le point de sortie d'Internet (votre réseau de périmètre) et une connexion réseau, par exemple WiFi ou Ethernet.
    
Le schéma suivant illustre la répartition des composants et des segments réseau d'un appel RTC de Skype Entreprise Online :
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Dans un scénario d'appel RTC, le chemin multimédia passe par les segments réseau suivants :
  
1. **Connexion entre un appelant client Skype Entreprise et le réseau de périmètre Microsoft** Inclut généralement une connexion réseau telle que WiFi ou Ethernet, la connexion WAN entre l'appelant client Skype Entreprise et le point de sortie Internet (votre périphérique de périmètre réseau), et la connexion Internet entre votre réseau de périmètre et celui de Microsoft.
    
2. **Connexion au sein du réseau Microsoft** Établie entre le périmètre Microsoft et le centre de données Skype Entreprise Online, dans lequel un serveur de médiation est utilisé.
    
3. **Connexion au sein du réseau Microsoft** Établie entre le centre de données Skype Entreprise et le réseau de périmètre Microsoft.
    
4. **Connexion entre le réseau Microsoft et les partenaires fournisseurs de services RTC** Il s'agit de la connexion qui existe pour passer un appel RTC à partir du client Skype Entreprise extérieur au réseau Microsoft.
    
### Conditions requises de performances réseau entre un client Skype Entreprise et le réseau de périmètre Microsoft
<a name="bk_SfBClienttoEdge"> </a>

Pour bénéficier d'une qualité optimale sur Skype Entreprise, les objectifs ou seuils de mesure de performances suivants sont requis pour une connexion établie entre le réseau de votre entreprise et le réseau de périmètre Microsoft. Ce segment du réseau comprend votre réseau interne, notamment toutes ses connexions WiFi et Ethernet, et le trafic entre les sites de la société via une connexion WAN, par exemple MPLS (Multiprotocol Label Switching), ainsi que les connexions partenaires Internet ou ExpressRoute vers le réseau de périmètre Microsoft.
  
> [!CAUTION]
> **La connectivité entre un client Skype Entreprise sur votre réseau d'entreprise et les services Office 365 doit répondre aux exigences et aux seuils de performances réseau suivantes.**
  
|||
|:-----|:-----|
|**Mesure** <br/> |**Cible** <br/> |
|Latence (unidirectionnelle)  <br/> |< 50 ms  <br/> |
|Latence (RTT ou durée de l'aller-retour)  <br/> |< 100 ms  <br/> |
|Perte de paquets en rafale  <br/> |< 10 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |< 1 % sur un intervalle de 15 s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |< 30 ms sur un intervalle de 15 s  <br/> |
|Réorganisation des paquets  <br/> |< 0,05 % paquets désorganisés  <br/> |
   
 **Autres objectifs de performances requis :**
  
- Microsoft dispose de plus de 160 réseaux de périmètre dans le monde. Nous travaillons avec les principaux fournisseurs de services Internet (FSI) au monde par le biais de ces sites de périmètre. L'objectif de mesure de latence présuppose que le ou les sites de votre entreprise et les périmètres Microsoft sont sur le même continent.
    
- La connexion entre le ou les sites de votre entreprise et le réseau de périmètre Microsoft inclut un accès réseau de premier saut, qui peut être WiFi ou d'une autre technologie sans fil. 
    
- L'objectif de performance de réseau présuppose une planification appropriée de la bande passante et/ou de la qualité de service. Autrement dit, il s'applique directement au trafic multimédia en temps réel de Skype Entreprise lorsque la connexion réseau est sous une charge de pointe.
    
### Performances réseau requises entre votre périmètre réseau et le réseau de périmètre Microsoft
<a name="bk_YourNetworkEdge"> </a>

Voici les objectifs ou seuils de performances réseau requis pour une connexion entre votre périmètre réseau et le réseau de périmètre Microsoft. Ce segment du réseau exclut le réseau interne ou le WAN du client, et est fourni à titre indicatif pour tester votre trafic réseau envoyé sur Internet, ou par l'intermédiaire d'un réseau partenaire ExpressRoute. Il peut également être utilisé pour négocier un contrat de niveau de service (SLA) avec votre fournisseur ExpressRoute.
  
> [!CAUTION]
> **La connectivité entre le périmètre de votre réseau d'entreprise et le réseau de périmètre Microsoft doit répondre aux conditions et aux seuils de performances réseau ci-dessous.**
  
|||
|:-----|:-----|
|**Mesure** <br/> |**Cible** <br/> |
|Latence (unidirectionnelle)  <br/> |< 30 ms  <br/> |
|Latence (RTT)  <br/> |< 60 ms  <br/> |
|Perte de paquets en rafale  <br/> |< 1 % sur un intervalle de 200 ms  <br/> |
|Perte de paquets  <br/> |< 0,1 % sur un intervalle de 15 s  <br/> |
|Gigue entre les arrivées de paquets  <br/> |< 15 ms sur un intervalle de 15 s  <br/> |
|Réorganisation des paquets  <br/> |< 0,01% paquets désorganisés  <br/> |
   
 **Autres objectifs de performances requis :**
  
- L'objectif de performance nécessite que la connexion entre l'un des périmètres réseau de votre société et son réseau de périmètre Microsoft le plus proche soit établie sur le même continent.
    
- L'objectif de performances réseau présuppose que la bande passante et/ou la qualité de service appropriée a été planifiée. Cela vaut également pour Skype pour le trafic multimédia en temps réel de Skype Entreprise lorsque la connexion réseau est sous une charge de pointe. Pour planifier correctement la bande passante et la QoS, reportez-vous à [ExpressRoute et QoS dans Skype Entreprise Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## Mesure des performances du réseau
<a name="bk_NetworkPerf"> </a>

Pour mesurer les performances réelles du réseau, notamment la latence et la perte de paquets, entre n'importe quel site du réseau de l'entreprise et un périmètre Microsoft, vous pouvez utiliser des outils tels que ping, pour effectuer des tests par rapport à divers services de relais multimédia Skype Entreprise exécutés à partir du périmètre et des centres de données Microsoft. 
  
Pour tester les connexions Internet au réseau Microsoft, il est recommandé de mener des tests par rapport aux VIP suivants des relais multimédia Skype Entreprise. La  *VIP Anycast*  renvoie l'adresse IP d'un relais multimédia sur le site de périmètre Microsoft le plus proche de l'emplacement du test.
  
||||
|:-----|:-----|:-----|
|**Adresse IP** <br/> |**Type** <br/> |**Emplacement** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |Adresse IP Anycast dans le monde  <br/> |
   
 **Voici quelques recommandations générales à suivre pour évaluer les performances du réseau :**
  
- Vous devez évaluer votre réseau interne, ainsi que les connexions à Office 365.
    
- Vous devez évaluer et recueillir des données pour l'ensemble de vos réseaux sur une période prolongée. Il est recommandé d'effectuer vos tests de performances réseau sur une période minimale d'une semaine, de manière à identifier des modes d'utilisation propres à chaque jour et heure ouvrable. Vous pourrez ainsi identifier les heures de pointe.
    
- Vous devez prendre de nombreux échantillons des mesures de performances réseau. Il est recommandé de prendre une mesure toutes les 10 minutes à partir d'un site de l'entreprise sur l'ensemble de la période de collecte de données. Pour comparer les conditions de performances réseau pour Skype Entreprise, prenez la valeur de mesure du 90e centile dans cet échantillon de jeux de données. 
    
- Vous devez évaluer en permanence les performances réseau. L'utilisation du réseau varie dans le temps en fonction des changements de modes d'utilisation, de nouvelles applications d'entreprise qui consomment une bande passante importante et des modifications apportées aux sites organisationnels ou physiques de votre entreprise. Il est important de surveiller en permanence les performances de votre réseau par rapport à ces conditions et objectifs/seuils requis et d'effectuer les ajustements appropriés pour assurer la qualité multimédia en temps réel la plus optimale. 
    
## Mesure des performances du réseau en utilisant des machines virtuelles Azure
<a name="bk_NetworkPerf"> </a>

Au lieu d'effectuer des tests par rapport aux sites de réseau de périmètre Microsoft, il existe des solutions d'évaluation du réseau de la part des clients et des partenaires de Skype Entreprise qui tirent parti de la configuration du test des services dans le cloud Microsoft Azure. Dans ces solutions, les outils d'évaluation du réseau testent la latence, la perte de paquets et la gigue par rapport à des terminaux personnalisés configurés en tant que service dans le cloud Azure. En conséquence, le trafic réseau test est acheminé à travers un segment de réseau supplémentaire, qui est la connexion au sein du réseau Microsoft entre les réseaux de périmètre et les centres de données Azure qui hébergent le service d'évaluation du réseau.
  
Pour les solutions d'évaluation du réseau basées sur des services de test hébergés par Azure. Nous vous conseillons d'effectuer l'évaluation du réseau au sein du pays et/ou de la région. Par exemple, pour les sites des clients situés dans l'est des États-Unis, l'évaluation doit être effectuée par rapport à une instance du service de test hébergée dans la région du centre de données Azure de l'est des États-Unis. 
  
Voici les objectifs de latence (RTT) pour la configuration de l'évaluation du réseau basée sur le service Azure. Les objectifs de latence unidirectionnelle seront la moitié des objectifs de latence RTT correspondants. Les objectifs de perte de paquets et de gigue restent les mêmes que ceux définis pour les tests basés sur un relais multimédia Skype.
  
|||||
|:-----|:-----|:-----|:-----|
|**Région du client** <br/> |**Région Azure** <br/> |**Votre périmètre réseau - Azure Round-trip Time (RTT)** <br/> |**Votre site - Azure Round-trip Time (RTT)** <br/> |
|Centre des États-Unis  <br/> |Centre des États-Unis  <br/> |99  <br/> |139  <br/> |
|Est des États-Unis  <br/> |Est des États-Unis  <br/> |86  <br/> |126  <br/> |
|Centre Nord des États-Unis  <br/> |Centre Nord des États-Unis  <br/> |97  <br/> |137  <br/> |
|Centre Sud des États-Unis  <br/> |Centre Sud des États-Unis  <br/> |94  <br/> |134  <br/> |
|Ouest des États-Unis  <br/> |Ouest des États-Unis  <br/> |94  <br/> |134  <br/> |
|Hawaï États-Unis  <br/> |Ouest des États-Unis  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|Canada Est  <br/> |Canada Est  <br/> |131  <br/> |171  <br/> |
|Europe du Nord  <br/> |Europe du Nord  <br/> |99  <br/> |139  <br/> |
|Europe de l'Ouest  <br/> |Europe de l'Ouest  <br/> |95  <br/> |135  <br/> |
|Asie de l'Est  <br/> |Asie de l'Est  <br/> |118  <br/> |158  <br/> |
|Asie du Sud-Est  <br/> |Asie du Sud-Est  <br/> |97  <br/> |137  <br/> |
|Japon Est  <br/> |Japon Est  <br/> |111  <br/> |151  <br/> |
|Japon Ouest  <br/> |Japon Ouest  <br/> |118  <br/> |158  <br/> |
|Brésil Sud  <br/> |Brésil Sud  <br/> |70  <br/> |110  <br/> |
|Australie Est  <br/> |Australie Est  <br/> |124  <br/> |164  <br/> |
|Australie Sud-Est  <br/> |Australie Sud-Est  <br/> |124  <br/> |164  <br/> |
|Centre de l'Inde  <br/> |Centre de l'Inde  <br/> |103  <br/> |143  <br/> |
|Sud de l'Inde  <br/> |Sud de l'Inde  <br/> |103  <br/> |143  <br/> |
|Inde de l'Ouest  <br/> |Inde de l'Ouest  <br/> |103  <br/> |143  <br/> |
|Est de la Chine  <br/> |Est de la Chine  <br/> |120  <br/> |160  <br/> |
|Nord de la Chine  <br/> |Nord de la Chine  <br/> |120  <br/> |160  <br/> |
   
## Qualité multimédia et ExpressRoute
<a name="bk_NetworkPerf"> </a>

Azure ExpressRoute pour Office 365 est une connexion réseau dédiée permettant d'établir des connexions à Office 365. Cette solution offre aux clients la possibilité de contrôler le chemin emprunté par leur trafic réseau Office 365. Ils éliminent ainsi les imprévus d'acheminement associés à Internet, où les données sont transportées par des opérateurs, des fournisseurs et des FAI inconnus. Le trafic réseau envoyé via ExpressRoute passe directement du réseau de partenaires ExpressRoute au réseau de Microsoft. Pour les clients, Office 365 semble ainsi être situé sur leur propre centre de données hors site, accessible avec une connexion dédiée.
  
Azure ExpressRoute est disponible pour toutes les offres de licence Office 365. Toutefois, le complément Azure ExpressRoute Premium est nécessaire pour permettre à Office 365 d'activer un acheminement mondial. Les clients Office 365 possédant au moins 500 postes qui mettent en œuvre ExpressRoute peuvent obtenir le  *complément ExpressRoute Premium*  requis sans frais supplémentaires.
  
### ExpressRoute est-il requis pour obtenir une bonne qualité multimédia ?

Azure ExpressRoute n'est pas une condition requise pour obtenir la qualité multimédia la plus optimale pour Skype Entreprise Online. Toutefois, c'est l'une des options de déploiement qui vous assurent que votre connectivité cloud répond aux objectifs ou aux seuils de performances réseau de Skype Entreprise.
  
Office 365 est un service hautes performances et sécurisé qui utilise Internet. Nous continuons à investir dans de nouvelles fonctionnalités de sécurité et dans des nœuds de périmètre régionaux en vue d'améliorer en permanence la sécurité et les performances. Azure ExpressRoute n'est pas obligatoire pour les services Office 365, dont Skype Entreprise Online. Azure ExpressRoute est l'une des options de déploiement disponibles qui vous aideront à garantir que la connectivité à Office 365 répond aux exigences de performances réseau de Skype Entreprise et assure la qualité multimédia le plus optimale pour Skype Entreprise Online.
  
Pour assurer la qualité multimédia de Skype Entreprise Online, il est important que la connexion entre les sites de votre entreprise et le réseau de périmètre Microsoft réponde aux objectifs de performance indiqués à la section [Conditions requises de performances réseau entre un client Skype Entreprise et le réseau de périmètre Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge) et que la connexion entre vos périmètres réseau et les réseaux de périmètre Microsoft répondent aux objectifs de performances indiqués au paragraphe[Performances réseau requises entre votre périmètre réseau et le réseau de périmètre Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_YourNetworkEdge). 
  
Il est également important que la connectivité réseau physique de votre entreprise, notamment votre réseau interne et la connectivité cloud, soit adaptée aux volumes des pics de trafic multimédia. Azure ExpressRoute est l'une des nombreuses solutions qui aideront les clients à garantir que leur connectivité cloud pour Skype Entreprise Online respecte toutes ces conditions de performances.
  
### ExpressRoute est-il nécessaire pour les contrats de niveau de service (SLA) de qualité vocale ?

Non, ExpressRoute n'est pas obligatoire pour le SLA de qualité vocale de Skype Entreprise Online. Le [SLA de qualité vocale Skype Entreprise Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) est applicable à n'importe quel appel admissible passé par n'importe quel utilisateur du service vocal Skype Entreprise Online disposant de la licence et de l'abonnement appropriés pour effectuer tout type d'appel VoIP ou RTC. Un SLA de qualité vocale doit spécifier que toutes les conditions suivantes sont remplies :
  
- Appels à partir de téléphones IP certifiés Microsoft.
    
- Connexions Ethernet filaires.
    
- Problèmes de qualité vocale liés à des problèmes du réseau Microsoft.
    
> [!NOTE]
> Le SLA de qualité vocale exclut les appels dont la mauvaise qualité provient de problèmes issus de réseaux non Microsoft, y compris le partenaire ExpressRoute et d'autres réseaux. 
  
### Internet ou Azure ExpressRoute ?

Avant de choisir des options de connectivité réseau pour Skype Entreprise Online, les clients doivent évaluer leur réseau et leur connectivité Internet actuelle à l'aide des informations fournies à la section [Conditions requises de performances réseau pour une connexion à Skype Entreprise Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_NetworkPerf).
  
Si les performances du réseau via la connexion Internet actuelle sont configurées sur une capacité suffisante pendant les heures de pointe et qu'elles répondent aux exigences de performance du réseau entre les sites et les réseaux de périmètre Microsoft, et entre vos périmètres réseau et les réseaux de périmètre Microsoft, vous pouvez continuer à utiliser votre connexion Internet existante pour vous connecter à Skype Entreprise Online.
  
Sur les sites de l'entreprise où les conditions de performances du réseau ne sont pas respectées, il est vivement recommandé de déterminer avec vos fournisseurs de services réseau comment améliorer vos performances réseau globales. Toutefois, si elles ne sont toujours pas satisfaites, Azure ExpressRoute peut contribuer à assurer que la connectivité cloud de Skype Entreprise Online vous aide à répondre aux conditions de performances du réseau.
  
Azure ExpressRoute offre les avantages supplémentaires suivants :
  
- Un contrat de niveau de service (SLA) sur la disponibilité de connexion entre votre réseau et le réseau Microsoft. ExpressRoute offre un SLA de disponibilité garantie à 99,9 %.
    
- Bande passante prévue et garantie requise pour les services Office 365. Pour y parvenir, vous pouvez diriger uniquement le trafic d'Office 365 ou de Skype Entreprise par ExpressRoute, puis faire passer le reste du trafic Internet par d'autres points d'entrée/sortie Internet de votre réseau.
    
- ExpressRoute est conçu pour préserver les marquages de la qualité de service DSCP entre votre réseau et celui de Microsoft.
    
Pour plus d'informations sur la QoS ExpressRoute et la planification des capacités, reportez-vous à [ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### Puis-je configurer Azure ExpressRoute pour Skype Entreprise Online uniquement ?

Oui, vous pouvez configurer Azure ExpressRoute pour assurer une excellente connectivité entre le réseau de votre entreprise et Skype Entreprise Online uniquement. Vos utilisateurs bénéficieront ainsi de la qualité multimédia en temps réel la plus optimale, mais vous pourrez continuer à vous connecter à d'autres services Office 365 sur Internet.
  
Le protocole de passerelle frontière (BGP) est un protocole de routage sur Internet utilisé pour acheminer le trafic réseau sur Internet. Il est destiné à échanger les informations de routage entre les systèmes autonomes (AS) trouvés sur Internet. Les valeurs de communautés BGP sont des balises d'attribut qui peuvent être appliquées aux itinéraires entrants ou sortants. Les communautés BGP sont souvent utilisées pour signaler au système autonome de réception la liaison entrante qu'il doit utiliser pour atteindre une destination spécifique en fonction de la zone géographique, du type de service ou d'autres critères.
  
Avec la prise en charge des communautés BGP, Microsoft marquera les préfixes et les routages avec les valeurs de communauté BGP appropriées en fonction du service auquel ils appartiennent. Microsoft marquera également les préfixes publiés via l'homologation publique et l'homologation Microsoft avec les valeurs de communauté appropriées indiquant la région dans laquelle les préfixes sont hébergés. Vous pouvez compter sur les valeurs de communauté pour prendre des décisions de routage avisées et offrir aux clients un routage optimal. Vous pouvez utiliser la valeur de la communauté Skype Entreprise Online pour configurer une connexion ExpressRoute uniquement pour Skype Entreprise Online. Pour en savoir plus, consultez la rubrique [Configuration requise pour le routage ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## Scénarios de connectivité ExpressRoute pour Skype Entreprise Online
<a name="bk_NetworkPerf"> </a>

Si, après avoir lu les recommandations ci-dessous, vous pensez qu'ExpressRoute est fait pour vous, voici quelques conseils pour trouver et choisir le nombre de connexions ExpressRoute dont vous avez besoin.
  
### Déploiement de Skype Entreprise Online - Un seul site

Si tous vos utilisateurs utilisent le service Skype Entreprise Online, que tous vos bureaux se situent au même emplacement physique et que vous décidez de déployer Azure ExpressRoute, nous vous conseillons de configurer une seule connexion ExpressRoute entre le site de votre entreprise et [l'emplacement d'homologation ExpressRoute ](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) le plus proche.
  
Le schéma suivant vous montre un exemple de ce type de déploiement. Dans cet exemple, Contoso est une université située à Orlando, FL. Contoso compte 10 000 professeurs d'université et étudiants. Les tests Internet réalisés entre leur emplacement et les sites périphériques Microsoft ont révélé un taux de perte de paquets supérieur à 5 % pendant les heures de cours (heures de pointe). Pour pallier ce problème, Contoso a choisi ExpressRoute pour créer une connexion dédiée à Office 365 avec une bande passante généreusement approvisionnée afin d'éviter la congestion du réseau pour Office 365, et plus particulièrement du trafic en temps réel de Skype Entreprise Online. Désormais, les utilisateurs se connectent au cloud de Microsoft via ExpressRoute sur le site MeetMe d'Atlanta, GA.
  
![ExpressRoute Single Site.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### Déploiement de Skype Entreprise Online - Plusieurs sites sur le même continent

Si votre entreprise utilise les services Skype Entreprise Online sur plusieurs sites de la même région ou du même continent, et que vous avez choisi de déployer Azure ExpressRoute, nous vous conseillons de connecter votre site principal via ExpressRoute, puis de créer éventuellement un circuit d'homologation ExpressRoute supplémentaire pour les sites qui ne répondent pas aux critères de performance réseau requis.
  
Dans l'exemple suivant, Contoso est une agence de voyage américaine, qui détient son siège social à New York et des bureaux dans l'ensemble des États-Unis. Leurs sites sont interconnectés via un réseau WAN MPLS pour se connecter à Office 365. Pour cela, ils ont créé une connexion ExpressRoute entre leur routeur Internet situé à Hoboken, New Jersey et le site MeetMe de New York. 
  
Avec cette configuration, le trafic réseau entre la plupart de ses sites et le réseau Microsoft (site périphérique de New York) est conforme aux critères de performances réseau de la connexion du client à Skype Entreprise Online décrits dans la section [Conditions requises de performances réseau entre un client Skype Entreprise et le réseau de périmètre Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge). Cependant, le temps de latence entre les bureaux de Contoso situés sur la côte Ouest et ceux de New York est supérieur à 50 millisecondes, aller. De plus, la connexion New York-Honolulu, le deuxième plus grand bureau de Contoso, affiche un temps de latence supérieur à 80 millisecondes, aller. Pour offrir aux utilisateurs de ces bureaux un accès de qualité à ses outils, Contoso a décidé de déployer une autre connexion ExpressRoute sur la côte Ouest entre son site de San José et le site ExpressRoute MeetMe de la Silicon Valley.
  
![Express Router Multi-site on the same continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### Déploiement de Skype Entreprise Online - Plusieurs sites sur différents continents

Si tous vos utilisateurs utilisent Skype Entreprise Online, que vos bureaux sont situés à différents emplacements physiques sur plusieurs continents et que vous décidez de déployer Azure ExpressRoute, nous vous conseillons de configurer au moins une connexion ExpressRoute pour chaque continent, entre le site principal du continent et son [emplacement d'homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) le plus proche. Selon le rapport qualité-prix, vous pouvez déployer des connexions ExpressRoute supplémentaires depuis des sites qui ne répondent pas aux critères de performance réseau requis.
  
Dans l'exemple suivant, Contoso est un grand cabinet d'avocats qui possède des bureaux dans des grandes villes d'Amérique du Nord et d'Europe. Après avoir évalué leur connexion Internet et les performances de leur réseau interne, Contoso a décidé de déployer deux connexions ExpressRoute en Amérique du Nord et un circuit ExpressRoute pour tous ses bureaux européens.
  
![ExpressRoute with multiple sites and continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### Déploiement hybride

Si vous disposez d'un déploiement local de Lync ou de Skype Entreprise, que vous décidez d'implémenter un déploiement hybride de Skype Entreprise Online et que vous souhaitez déployer Azure ExpressRoute, nous vous conseillons de créer au moins une connexion ExpressRoute pour chaque site périphérique Lync ou Skype Entreprise Online et au moins une connexion ExpressRoute pour chaque continent où vous possédez des bureaux. Selon le rapport qualité-prix, vous pouvez choisir de déployer des connexions ExpressRoute supplémentaires sur chaque continent pour les bureaux qui ne répondent pas aux critères de performance réseau.
  
Si vous optez pour un déploiement local de Skype Entreprise, nous vous recommandons de consulter le [Guide de déploiement et de planification du serveur Edge](https://technet.microsoft.com/en-us/library/mt346417.aspx). Pour résumer, les serveurs Edge doivent être accessibles depuis l'extérieur de votre réseau. Pour cela, vous devez assigner une adresse IP publique routable au serveur Edge ou utiliser la traduction d'adresses de réseau (NAT, Network Address Translation).
  
Dans l'exemple suivant, Contoso dispose d'un déploiement local de la plate-forme Voix de Skype Entreprise. L'entreprise souhaite migrer les utilisateurs locaux vers les services en ligne d'Office 365. Elle a également décidé d'utiliser un déploiement hybride pour que tous les utilisateurs locaux et en ligne puissent continuer à utiliser l'infrastructure RTC existante. Le centre de données local de Contoso et les serveurs de Skype Entreprise se situent à Chicago. Pour le déploiement, Contoso a décidé de configurer une seule connexion ExpressRoute entre son centre de données de Chicago et le site ExpressRoute de Chicago. Ils ont également créé une autre connexion ExpressRoute sur la côte Ouest pour optimiser le routage des utilisateurs de leur site d'Honolulu.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### Déploiement de Skype Entreprise Online avec la version Cloud Connector

La version Cloud Connector de Skype Entreprise Online est une offre hybride comprenant un ensemble de machines virtuelles (VM) qui met en œuvre une connectivité RTC locale. En déployant une topologie Skype Entreprise Server minimale dans un environnement virtualisé, vous pourrez envoyer et recevoir des appels avec des téléphones fixes et mobiles par le biais de l'infrastructure RTC vocale locale existante.
  
Si vous décidez de déployer Azure ExpressRoute et la version Cloud Connector, nous vous conseillons de créer au moins une connexion ExpressRoute pour chaque continent, entre le site principal et [l'emplacement d'homologation ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) le plus proche. Selon le rapport qualité-prix, vous pouvez déployer des connexions ExpressRoute supplémentaires sur chaque continent, pour les sites qui ne répondent pas aux critères de performance réseau.
  
Si vous disposez d'un déploiement local de Skype Entreprise, consultez le [Guide de planification pour la version Cloud Connector de Skype Entreprise](https://technet.microsoft.com/EN-US/library/mt605227.aspx). En particulier, les services Access Edge et A/V Edge doivent disposer d'adresses IP publiques et être accessibles depuis les centres de données Office 365.
  
Dans l'exemple suivant, Contoso est un cabinet européen d'experts-comptables qui possède des bureaux dans plusieurs villes et pays/régions d'Europe. Lorsqu'ils ont souscrit à Skype Entreprise Online, ils ont décidé de déployer la version Cloud Connector pour chaque pays/région où ils possèdent des bureaux pour continuer à utiliser leur infrastructure RTC et leurs fournisseurs existants. Suite aux tests menés sur tous leurs sites et sur le réseau périphérique de Microsoft, ils ont décidé qu'une seule connexion ExpressRoute à Londres suffirait à remplir les critères de performance réseau de la connexion du client à Skype Entreprise décrits dans la section [Conditions requises de performances réseau entre un client Skype Entreprise et le réseau de périmètre Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge).
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Voici une autre solution de déploiement pour Contoso. Dans cet exemple, ils ont décidé de créer une connexion ExpressRoute sur chaque site où la version Cloud Connector est déployée.
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## Voir aussi
<a name="bk_NetworkPerf"> </a>

#### 

[ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](20c654da-30ee-4e4f-a764-8b7d8844431d.md)

