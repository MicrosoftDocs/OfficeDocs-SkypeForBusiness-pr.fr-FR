---
title: Implémenter la qualité de service dans Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Préparez le réseau de votre organisation à la qualité de service (QoS) dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.qos
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e72b4b4fdfdbe6d31ca3543d23b67cb515568e4f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194538"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implémenter la qualité de Service (QoS) dans les équipes Microsoft

Cet article vous aide à préparer le réseau de votre organisation de qualité de Service (QoS) dans Microsoft Teams. Si vous prenez en charge un groupe important d’utilisateurs et ils rencontrez un des problèmes évoqués ci-dessous, vous devrez probablement implémenter QoS. Une petite entreprise avec un petit nombre d’utilisateurs n’est pas nécessaire QoS, mais encore il doit être utile.

QoS est un moyen permettant d’en temps réel le trafic réseau (par exemple, les flux audio ou vidéo) qui est sensible aux délais réseau « réduction à la ligne « devant le trafic est moins sensible (comme le téléchargement d’une nouvelle application, où une seconde supplémentaire à télécharger n’est pas très important). Qualité de service identifie et marque tous les paquets de flux de données en temps réel (à l’aide des objets de stratégie de groupe Windows et une fonctionnalité de routage appelée basée sur le Port Access Control Lists, informations complémentaires sur ceux se trouve en bas) qui permet à votre réseau pour donner à la voix, vidéo et flux de partage d’écran un partie de la bande passante réseau dédiée.

Sans une forme de qualité de service, vous pouvez voir les problèmes suivants de qualité vocale et vidéo :

- Gigue – paquets de médias arrivant à différents taux, ce qui peuvent aboutir à des mots ou des syllabes dans les appels manquants.
- Perte de paquets – paquets perdus, qui peut également entraîner la qualité vocale et sévère de comprendre la reconnaissance vocale.
- Retard délai d’aller-retour (durée aller-retour) – paquets de médias prend beaucoup de temps pour atteindre leurs destinations, qui entraîne des retards conséquents entre deux correspondants dans une conversation, à l’origine de parler sur chacun des autres personnes.

Le moins complexe pour résoudre ces problèmes consiste à augmenter la taille de connexions de données, à la fois en interne et vers internet. Puisqu’il s’agit souvent envisageable, QoS permet de gérer plus efficacement les ressources dont vous disposez au lieu d’ajouter de nouvelles ressources. Pour entièrement résoudre les problèmes de qualité vous utiliser QoS sur l’implémentation, puis vous ajoutez connectivité uniquement en cas d’absolue nécessité.

QoS être efficaces, vous devez appliquer les paramètres QoS cohérentes bout en bout dans votre organisation (Cela inclut tous les ordinateurs des utilisateurs, commutateurs réseau et les routeurs à internet), parce que n’importe quelle partie du chemin d’accès ne parvient pas à prendre en charge vos priorités QoS peut diminuer la qualité des appels, vidéo et partage d’écran.

_La figure 1. La relation entre les réseaux d’une organisation et les services Office 365_

![La relation entre les réseaux d’une organisation et les services Office 365 : réseau et périphériques de se connectent à un réseau d’interconnexion, qui se connecte à son tour avec les services Office 365 Cloud voix et de conférence sur site.](media/Qos-in-Teams-Image1.png)

Dans la plupart des cas, le réseau de connexion de votre entreprise vers le nuage sera un réseau non géré où vous ne serez pas en mesure de définir les options de qualité de service de manière fiable. Un choix disponible à l’adresse QoS de bout en bout est [ExpressRoute Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), mais nous vous recommandons d’implémenter QoS sur votre réseau local. Cette augmentation de la qualité des charges de travail de communication en temps réel au sein de votre déploiement et éviter les goulots d’étranglement.

## <a name="verify-your-network-is-ready"></a>Vérifiez que votre réseau est prêt

Si vous envisagez une implémentation de qualité de service, vous devez déjà avoir déterminé vos besoins en bande passante et les autres [exigences de réseau](prepare-network.md). Calculs de bande passante pour Microsoft Teams sont complexes et pour aider, une calculatrice a été créée. Pour accéder à la Calculatrice, accédez au [Planificateur réseau](https://aka.ms/bwcalc/) dans MyAdvisor.
  
  Encombrement du trafic réseau considérablement impact sur la qualité des médias. Un manque de bande passante entraîne une dégradation des performances et une expérience utilisateur médiocre. À mesure que l’utilisation et à l’adoption des équipes augmente, utiliser des rapports, [appelez Analytique et appelez le tableau de bord qualité](difference-between-call-analytics-and-call-quality-dashboard.md) pour identifier les problèmes et puis procédez aux ajustements à l’aide de la qualité de service et des ajouts de bande passante sélective.

### <a name="vpn-considerations"></a>Considérations en matière de réseau privé virtuel

QoS ne fonctionne comme prévu lorsqu’elle est implémentée sur tous les liens entre les appelants. Si vous utilisez QoS sur un réseau interne et un utilisateur se connecte à partir d’un emplacement distant, vous pouvez classer uniquement au sein de votre réseau interne, gérée. Bien que les sites distants peuvent recevoir une connexion gérée en implémentant un réseau privé virtuel (VPN), un réseau privé virtuel par héritage ajoute la surcharge de paquets et crée des retards dans le trafic en temps réel. Nous vous recommandons d’éviter d’exécuter le trafic des communications en temps réel via une connexion VPN.

> [!NOTE]
> Utilisateurs distants connectés VPN doivent implémenter fractionné tunnel pour optimiser la qualité de l’expérience utilisateur. Le document [Guide de déploiement-VPN fractionné Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) est disponible à partir de MyAdvisor et a plus d’informations.

Dans une organisation globale avec liens gérées qui couvrent continents, il est vivement recommandé QoS, car la bande passante pour ces liens est limitée par rapport à votre réseau local.

## <a name="introduction-to-qos-queues"></a>Introduction aux files d’attente de QoS

Pour fournir la qualité de service, les périphériques réseau doivent disposer d’un moyen de classer le trafic et doivent être en mesure de faire la distinction audio ou vidéo à partir du reste du trafic réseau.

Le trafic réseau quand un routeur, le trafic est placé dans une file d’attente. Si une stratégie de QoS n’est pas configurée, il n'est qu’une seule file d’attente et toutes les données sont traitées comme première-, sorti avec la même priorité. Cela signifie que le trafic vocal (qui est très sensible aux délais) peut être bloqué derrière le trafic où un délai de quelques millisecondes supplémentaires ne serait pas un problème.

Lorsque vous implémentez la qualité de service, vous définissez plusieurs files d’attente à l’aide d’une de plusieurs fonctionnalités de gestion de congestion (tels que Cisco priorité et basé sur une classe Weighted Fair Queueing [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) et les fonctionnalités de prévention de congestion (tel que pondérée aléatoire au début détection de [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).

_La figure 2. Exemples de files d’attente de QoS_

![La bande passante disponible total est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui ont été attribués à des priorités différentes.] (media/Qos-in-Teams-Image2.png "La bande passante disponible total est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui ont été attribués à des priorités différentes.")

Analogie est que QoS crée virtuel « voies covoiturage » dans vos données réseau afin de certains types de données rarement ou jamais rencontrent un délai d’attente. Une fois que vous créez ces pistes, vous pouvez régler leur taille relative et gérer plus efficacement la bande passante de connexion qu'ont, tout en offrant une expérience de qualité professionnelle pour les utilisateurs de votre organisation.

## <a name="select-a-qos-implementation-method"></a>Sélectionnez une méthode de mise en œuvre de QoS

Vous pouvez implémenter QoS via basée sur le port de mise en réseau, à l’aide de listes de contrôle d’accès (ACL) sur les routeurs de votre réseau. Balisage basé sur le port est la méthode la plus fiable, car elle fonctionne dans les environnements mixtes Windows et Mac et est la plus simple à implémenter. Les clients mobiles ne fournissent un mécanisme pour marquer le trafic à l’aide de valeurs DSCP, afin qu’ils nécessite cette méthode.  

À l’aide de cette méthode, routeur de votre réseau examine un paquet entrant, et si le paquet est arrivé à l’aide d’une plage de ports ou un port donnée, il identifie comme un certain type de média et le place dans la file d’attente pour ce type, ajout d’une marque [DSCP](https://tools.ietf.org/html/rfc2474) prédéterminée à l’adresse IP En-tête de paquet afin que les autres périphériques puissent reconnaître son type de trafic et lui donner une priorité dans leur file d’attente.

Bien que cela fonctionne sur plusieurs plates-formes, il marque uniquement le trafic sur le bord de réseau étendu (pas à l’ordinateur client) et crée des frais de gestion. Vous devez consulter la documentation fournie par le fabricant pour obtenir des instructions sur l’implémentation de cette méthode.

* * *

Vous pouvez également implémenter des stratégies QoS sont implémentées à l’aide d’un objet de stratégie de groupe (GPO) pour diriger les périphériques clients pour insérer une marque DSCP dans les en-têtes de paquets IP identifiant en tant que type particulier de trafic (par exemple, voix). Routeurs et autres équipements réseau peuvent être configurés pour reconnaître ce et placer le trafic dans une file d’attente distinct, priorité plus élevée.

Bien que ce scénario est entièrement valide, il ne fonctionne que pour les clients à un domaine Windows. Tous les périphériques qui n’est pas un client Windows à un domaine ne sont pas être activé pour le marquage DSCP marquage. Clients tels que Mac OS les balises codé en dur et permet d’identifier toujours le trafic.

Sur le signe plus côté, contrôler le marquage via la stratégie de groupe DSCP garantit que tous les ordinateurs à un domaine reçoivent les mêmes paramètres et que seul un administrateur peut gérer. Les clients qui peuvent utiliser l’objet stratégie de groupe seront balisés sur le périphérique d’origine et périphériques réseau configuré peuvent reconnaître le flux de données en temps réel par le code DSCP, puis lui attribuer une priorité appropriée.

* * *

Nous vous recommandons une combinaison de marquage DSCP au point de terminaison et ACL basées sur des ports sur les routeurs, si possible. À l’aide d’un objet de stratégie de groupe pour intercepter la plupart des clients, ainsi que le marquage de DSCP basée sur le port permet de garantir que mobile, Mac et les autres clients reçoivent toujours traitement QoS (au moins partiellement).

Marquage DSCP peut être comparée à un affranchissement marquages qui indiquent aux travailleurs postal la priorité est la livraison et la meilleure façon de procéder au tri pour la livraison. Une fois que vous avez configuré votre réseau de manière donne la priorité au flux de données en temps réel, de perte de paquets et en retard doit diminuer considérablement.

Une fois que tous les périphériques du réseau utilisent les classifications de même, les marques et les priorités, il est possible pour réduire ou éliminer reporter, perte de paquets et la gigue en modifiant la taille des plages de port affecté à des files d’attente utilisés pour chaque type de trafic. Du point de vue des équipes, l’étape de configuration plus importante est la classification et le marquage des paquets, mais pour QoS de bout en bout aboutisse, vous devez également Alignez soigneusement la configuration de l’application avec la configuration réseau sous-jacente. Une fois QoS est entièrement implémentée, une gestion courante est une question d’ajuster les plages de ports attribués à chaque type de trafic selon les besoins et l’utilisation réelle de votre organisation.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Choisissez les plages de ports initiale pour chaque type de média

La valeur DSCP indique un réseau configuré en conséquence quelle priorité donner un paquet ou un flux, si la marque DSCP est affectée par les clients ou le réseau lui-même en fonction des paramètres ACL. Chaque charge de travail multimédia obtient sa propre valeur DSCP unique (les autres services peuvent permettre à des charges de travail partager un marquage DSCP, n’est pas le cas des équipes) et une plage de ports définie et distincte utilisée pour chaque type de média. Autres environnements peuvent avoir une stratégie de QoS existante en place, qui vous aideront à déterminer la priorité des charges de réseau.

La taille relative des plages de ports pour différentes charges de travail en flux continu en temps réel définit la proportion de la bande passante disponible totale dédié à cette charge de travail. Pour revenir à l’analogie postal notre précédemment : une lettre avec un horodatage « Avion » peut obtenir prise au sein d’une heure pour l’aéroport le plus proche, tandis qu’un package de petite taille marquées « Courrier en nombre « mark peut attendre un jour avant le déplacement sur le terrain sur une série de camions.

Le tableau suivant montre le marquage DSCP requis d’équipes avec ExpressRoute et les ports associés des files d’attente de la charge de travail. Ces plages peuvent servir un bon point de départ pour les clients qui ne savez pas comment utiliser dans leurs propres environnements. Pour des informations complémentaire, consultez les [Exigences de qualité de service d’ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Recommandé de plages de ports initiale_

|Type de trafic multimédia| Plage de ports client source |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50,019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50,020 – 50,039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/écran| 50,040 – 50,059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Connaître les éléments suivants lorsque vous utilisez ces paramètres :

- Si vous envisagez d’implémenter ExpressRoute dans le futur et n’ont pas encore implémenté QoS, nous vous recommandons que vous suivez les instructions afin que les valeurs DSCP sont les mêmes à partir de l’expéditeur au récepteur.
- Tous les clients, y compris les clients mobiles et les périphériques d’équipes, utiliseront ces plages de ports et seront affectés par une stratégie DSCP que vous implémentez qui utilise ces plages de ports source. Seuls les clients qui continueront à utiliser des ports dynamiques sont les clients basés sur navigateur (autrement dit, les clients qui permettent aux participants de participer à des réunions à l’aide de leurs navigateurs).
- Bien que le client Mac utilise les mêmes plages de ports, il utilise également des valeurs codées en dur pour (EF) les paramètres audio / vidéo (AF41). Ces valeurs ne sont pas configurables.
- Si vous devez ajuster les plages de ports pour améliorer l’expérience utilisateur plus loin, les plages de ports ne peuvent pas se superposer et doivent être adjacentes.

## <a name="migrate-qos-to-teams"></a>Migrer de QoS aux équipes

Si vous avez déployé précédemment Skype pour Business en ligne, y compris le marquage QoS et les plages de ports et sont à présent les équipes de déploiement, les équipes respectent la configuration existante et utiliseront les mêmes plages de ports et marquer comme le Skype pour client d’entreprise. Dans la plupart des cas, aucune configuration supplémentaire n’est nécessaire.

> [!NOTE]
> Si vous utilisez des applications nom QoS balisage via la stratégie de groupe, vous devez ajouter Teams.exe comme nom d’application.

## <a name="qos-implementation-steps"></a>Étapes d’implémentation de QoS

Un très haut niveau, l’implémentation de QoS requiert comme suit :

1. [Vérifiez que votre réseau est prêt](#verify-your-network-is-ready)
2. [Sélectionnez une méthode de mise en œuvre de QoS](#select-a-qos-implementation-method)
3. [Choisissez les plages de ports initiale pour chaque type de média](#choose-initial-port-ranges-for-each-media-type)
4. Mettre en œuvre les paramètres QoS :
   1. Sur les Clients à l’aide d’un objet de stratégie de groupe pour [définir des plages de ports du périphérique client et les marques](QoS-in-Teams-clients.md)
   2. Sur les routeurs (voir la documentation du fabricant) ou d’autres périphériques réseau. Il peut s’agir des listes ACL basées sur le port ou en définissant simplement les files d’attente de qualité de service et des marquages DSCP ou tous ces.

      > [!IMPORTANT]
      > Nous vous recommandons d’implémenter ces stratégies de qualité de service à l’aide des ports clients source et une adresse IP source et de destination de « indifférent ». Ceci permet de détecter les deux le trafic multimédia entrant et sortant sur le réseau interne.  

   3. Dans le [Centre d’administration équipes](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)
5. [Valider l’implémentation de QoS](#validate-the-qos-implementation) en analysant les équipes le trafic sur le réseau.

Lorsque vous préparez implémenter QoS, n’oubliez pas les instructions suivantes :

- Le chemin le plus court vers Office 365 est préférable.
- Fermeture des ports uniquement entraîne une dégradation de la qualité.
- Les obstacles intermédiaires, tels que des serveurs proxy, ne sont pas recommandés.
- Limite le nombre de tronçons :
  - Client à côté du réseau – tronçons de 3 à 5.
  - Fournisseur de services Internet à côté du réseau Microsoft – 3 tronçons
  - Côté du réseau Microsoft vers une destination finale – non pertinents

Pour plus d’informations sur la configuration des ports de pare-feu, accédez à [Office 365 URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md).

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestion des ports source dans le centre d’administration équipes

Les équipes, QoS source les ports utilisés par les différentes charges de travail doivent être activement gérés et ajustées si nécessaire. En vous référant au tableau de [plages de ports et d’un marquage DSCP](#port-ranges-and-dscp-markings), les plages de ports sont variables, mais le marquage DSCP n’est pas configurables. Une fois que vous avez implémenté ces paramètres, vous pouvez constater que les ports plus ou moins sont nécessaires pour un type de média donné. [Analytique d’appel et appel du tableau de bord qualité](difference-between-call-analytics-and-call-quality-dashboard.md) doivent être utilisés dans une prise de décision pour ajuster les plages de ports après l’implémentation d’équipes, et régulièrement en fonction des besoins.

> [!NOTE]
> Si vous avez déjà configuré QoS basée sur les plages de ports source et des marquages DSCP pour Skype pour Business en ligne, la même configuration s’applique aux équipes et aucune autre client ou les modifications du réseau pour le mappage sera nécessaires si vous avez à [défini les plages utilisé dans le centre d’administration équipes](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) pour correspondre à ce qui a été configuré pour Skype pour Business Online.

Si vous avez précédemment déployé Skype pour Business Server locale, vous devrez peut-être revoir vos stratégies QoS et les ajuster selon vos besoins pour correspondre aux paramètres de plage de ports que vous avez vérifié fournir une expérience utilisateur de qualité pour les équipes.

## <a name="validate-the-qos-implementation"></a>Valider l’implémentation de QoS

Pour l’ensemble de valeurs QoS pour être efficaces, DSCP par l’objet de stratégie de groupe doit être présent aux deux extrémités d’un appel. En analysant le trafic généré par le client d’équipes, vous pouvez vérifier que la valeur DSCP n’est pas modifiée ou supprimée lorsque le trafic de la charge de travail des équipes parcourt les déplacements via le réseau.

De préférence, vous capturez le trafic réseau à la sortie. Vous pouvez utiliser la mise en miroir de port sur un commutateur ou un routeur pour cela.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilisez le Moniteur réseau pour vérifier les valeurs DSCP

Le Moniteur réseau est un outil que vous pouvez [télécharger à partir de Microsoft](https://www.microsoft.com/download/4865) pour analyser le trafic réseau.

1. Sur l’ordinateur exécutant le Moniteur réseau, connectez-vous au port qui a été configuré pour capturer les paquets de début et de la mise en miroir de port.

2. Émettre un appel à l’aide du client équipes. Assurez-vous que le support a été établie avant de raccrocher l’appel.

3. Arrêtez la capture.

4. Dans le champ de **Filtre d’affichage** , utilisez l’adresse IP source de l’ordinateur qui effectue l’appel et affiner le filtre en définissant la valeur DSCP 46 (hex d’arrêt 0xb8) comme critères de recherche, comme illustré dans l’exemple suivant :

    Source == « 192.168.137.201 » et IPv4.DifferentiatedServicesField == d’arrêt 0xb8

    ![Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, affichant des filtres à appliquer.] (media/Qos-in-Teams-Image4.png "Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, affichant des filtres à appliquer.")

5. Sélectionnez **Appliquer** pour activer le filtre.

6. Dans la fenêtre de **Cadre résumé** , sélectionnez le premier paquet UDP.

7. Dans la fenêtre **Détails de la trame** , développez l’élément de liste IPv4 et notez la valeur à la fin de la ligne qui commence par **le marquage DSCP**.

    ![Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres DSCP.] (media/Qos-in-Teams-Image5.png "Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres DSCP.")

Dans cet exemple, la valeur DSCP est définie à 46. Cela est correct, car le port source utilisé est 50019, qui indique qu’il s’agit d’une charge de travail voix.

Répétez la vérification pour chaque charge de travail qui a été marquée par la stratégie de groupe.

## <a name="more-information"></a>Plus d’informations

[Vidéo : Planification du réseau](https://aka.ms/teams-networking)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

[Exigences ExpressRoute QoS](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
