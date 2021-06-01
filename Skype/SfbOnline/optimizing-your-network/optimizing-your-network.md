---
title: Optimiser votre réseau
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Les conditions requises suivantes sont particulièrement importantes pour la garantie de l'intégrité et du bon fonctionnement à long terme de l'ensemble des fonctionnalités Skype Entreprise Online que vous configurez pour votre organisation. Ce document s'adresse aux utilisateurs occupant un poste très technique, mais nous savons que tous les utilisateurs ne le sont pas. Si vous avez besoin d'aide pour configurer Skype Entreprise Online, vous devez lire ce document pour vous familiariser avec les éléments que vous devez prendre en compte. Il vous donne également des informations à discuter lorsque vous travaillez avec le Microsoft FastTrack Center, vos équipes de services Microsoft et de compte, ou avec des partenaires Microsoft pour déterminer comment vous pouvez répondre à ces exigences.
ms.openlocfilehash: a32e7864a15945fc9bad64c12466aa376cb924f9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240224"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Optimisation de votre réseau pour Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Les conditions requises suivantes sont particulièrement importantes pour la garantie de l'intégrité et du bon fonctionnement à long terme de l'ensemble des fonctionnalités Skype Entreprise Online que vous configurez pour votre organisation. Ce document s'adresse aux utilisateurs occupant un poste très technique, mais nous savons que tous les utilisateurs ne le sont pas. Si vous avez besoin d'aide pour configurer Skype Entreprise Online, vous devez lire ce document pour vous familiariser avec les éléments que vous devez prendre en compte. Il vous donne également des informations à discuter lorsque vous travaillez avec le [Microsoft FastTrack Center,](https://fasttrack.microsoft.com/office)vos équipes de services Microsoft et de compte, ou avec des partenaires [Microsoft](https://partnercenter.microsoft.com/pcv/search) pour déterminer comment vous pouvez répondre à ces exigences.

## <a name="a-quick-overview"></a>Aperçu rapide

Skype Entreprise vous permet de communiquer avec vos collègues et partenaires professionnels au sein de votre société ou dans le monde entier.

Avec Skype Entreprise, vous pouvez :

- Démarrer des conversations à l'aide de la messagerie instantanée, de l'appel audio ou vidéo

- Savoir si vos contacts sont disponibles en ligne, en réunion, ou en présentation

- Définir une sécurité de niveau professionnel pour vos réunions

- Diffuser en ligne pour un nombre élevé de participants

- Présenter votre écran lors de réunions ou en donner le contrôle à des participants

- Utiliser Skype Entreprise dans d'autres programmes Office pour discuter, passer un appel, ou participer à une réunion en un clic

## <a name="why-is-this-all-so-important"></a>Pourquoi cela est-il si important ?

La qualité multimédia en temps réel (audio, vidéo et partage d'applications) sur IP est largement impactée par la qualité de la connectivité réseau de bout en bout. Pour bénéficier d'une qualité optimale pour Skype Entreprise Online, assurez-vous de la bonne qualité de la connexion entre votre réseau d'entreprise et Skype Entreprise Online. La meilleure façon d'y parvenir est de configurer la connectivité du réseau interne et du cloud en fonction de la capacité de votre réseau à s'adapter au volume du trafic maximal de Skype Entreprise Online sur l'ensemble des connexions.

En travaillant avec un partenaire [Microsoft,](https://partnercenter.microsoft.com/pcv/search)vous pouvez connecter différentes applications Microsoft 365 ou Office 365, notamment Skype Entreprise Online dans le cloud, à votre réseau et les fonctionnalités de communication vocale et vidéo en temps réel pour Skype Entreprise nécessitent des services réseau qui doivent être spécifiquement configurés pour prendre en charge ces charges de travail Microsoft 365 et Office 365 en temps réel. Cela comprend un réseau disposant de suffisamment de bande passante pour exécuter le volume de trafic nécessaire et prendre en charge la qualité de service (QoS) afin d'offrir à vos utilisateurs une expérience de qualité professionnelle.

En plus des présentes informations, d'autres ressources peuvent vous aider à planifier et à déployer les services et fonctionnalités Skype Entreprise Online de façon appropriée, et à vous assurer que vos services de réseau sont conformes aux exigences :

- [Flux d'appels avec ExpressRoute](call-flow-using-expressroute.md)

- [ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)

- [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Mise en œuvre de la qualité de service (QoS) pour Skype Entreprise Online

Avant d'accéder à Skype Entreprise Online, vous devez examiner la capacité de votre réseau en termes de gestion du trafic audio, vidéo et de session de partage. Comme pour d’autres services Microsoft 365 et Office 365, Microsoft peut télécharger l’outil de calcul de bande passante [Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=19011) utilisé pour déterminer le trafic réseau requis pour chacun des sites de votre entreprise. Vous devez effectuer une modélisation d'utilisation, notamment la modélisation des flux multimédia du trafic des communications en temps réel et de la quantité de trafic Skype Entreprise par site, calculer le volume du trafic et analyser l'impact de ce trafic sur l'ensemble de votre réseau. Une fois ces opérations réalisées, l'analyse des données devrait vous fournir des recommandations sur les améliorations à apporter à votre réseau et sur les tailles des files d'attente permettant de fournir une qualité d'expérience excellente à l'utilisateur final.

Le trafic en temps réel de Skype Entreprise est sensible à la perte de paquets, au retard et à la gigue, qui surviennent fréquemment sur des réseaux encombrés. La qualité de service (QoS), parfois dénommée Classe de service, doit également être déployée sur des réseaux WAN externes gérés, des réseaux LAN internes gérés, et des réseaux Wi-Fi d'entreprise. Cela permettra de hiérarchiser correctement les priorités du trafic en temps réel de Skype Entreprise, tel que le trafic audio et vidéo par rapport au trafic en temps différé sur des réseaux locaux et WAN, créant ainsi une meilleure expérience pour les utilisateurs finaux.

Le système audio de Skype Entreprise doit être déployé dans la file d'attente Acheminement accéléré (Expedited Forwarding ou EF - DSCP 46) et le système vidéo de Skype Entreprise doit être déployé dans la file d'attente Acheminement assuré 41 (Assured Forwarding ou AF - DSCP 34). C’est également vrai du trafic d’égal à égal et de conférence, que Système téléphonique dans Microsoft 365 ou Office 365 ou d’autres fonctionnalités téléphoniques soient déployés.

Bien que des stratégies de QoS existantes peuvent être déjà appliquées aux réseaux LAN et WAN pour d'autres produits de téléphonie IP, Skype Entreprise permet aux utilisateurs d'être mobiles et de se déplacer d'un site à l'autre tout en utilisant le service. Par conséquent, les stratégies de QoS doivent être marquées sur les réseaux LAN, WAN et sans fil afin d'assurer que l'ensemble du trafic de Skype Entreprise est traité en priorité sur les réseaux gérés.

Pour vous aider à déterminer la taille de votre réseau, téléchargez l'[outil de calcul de bande passante de Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=19011).

Pour en savoir plus sur la qualité multimédia et la QoS, reportez-vous à la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance.md).

Pour plus d’informations sur la configuration et la gestion de la qualité de service, voir [Gestion de la qualité de service.](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)

## <a name="bypass-proxies-and-wan-optimization-devices"></a>Contournement des proxys et des périphériques d'optimisation du réseau WAN

Tout Microsoft 365 ou Office 365 y compris Skype Entreprise Online est chiffré et ne peut généralement pas être inspecter par des périphériques proxy. Pour ces raisons, nous vous recommandons de contourner les périphériques proxy pour tout le trafic réseau Microsoft 365 et Office 365 défini comme connexions définies par vos utilisateurs aux URL et [plages](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)d’adresses IP Office 365. Les périphériques proxy sont susceptibles d'introduire un retard dans les flux multimédia Skype Entreprise Online en temps réel, nous recommandons donc d'utiliser le moins de périphériques proxy possible pour ce trafic.

Microsoft recommande d’exclure les Microsoft 365 et Office 365'utilisation de fichiers PAC pour envoyer le trafic Microsoft 365 et Office 365 vers un pare-feu.

Voici quelques ressources supplémentaires qui peuvent également être utiles :

- [Microsoft 365 ou Office 365 optimisation des performances à l’aide de lignes de référence et de l’historique des performances](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [Planification du réseau et de la migration pour Microsoft 365 ou Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Générateur de proxy PAC d'Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [Utilisation d’un contrôleur d’optimisation WAN ou d’appareils de trafic/inspection avec Microsoft 365 ou Office 365](/office365/troubleshoot/miscellaneous/office-365-third-party-network-devices)

- [Routage avec ExpressRoute pour Microsoft 365 ou Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>Contournement du double chiffrement

Pour offrir aux utilisateurs la meilleure expérience audio et vidéo possible, vous devez implémenter une solution qui empêche le média Skype Entreprise (audio et vidéo) de traverser un tunnel Réseau privé virtuel (Virtual Private Network, ou VPN). L'ensemble du trafic est chiffré à l'aide du protocole TLS (Transport Layer Security) et les charges de travail multimédia sont chiffrées à l'aide du protocole SRTP (Secure Real Time Protocol). La signalisation est chiffrée à l'aide du protocole TLS et les charges de travail multimédia sont chiffrées à l'aide du protocole SRTP. L’envoi de ce trafic sur le tunnel VPN ajoute une couche supplémentaire de chiffrement et des sauts de réseau supplémentaires entre le client et le Microsoft 365 ou Office 365, ce qui peut entraîner une dégradation de la session car cela augmente la gigue, la perte de paquets et la latence.

La tunnellisation fractionnée est une option permettant d'empêcher le trafic de Skype Entreprise de traverser le tunnel VPN. Pour implémenter la tunnellisation fractionnée, les clients doivent consulter leur fournisseur VPN concernant les spécificités d'exécution liées à leur logiciel.

> [!NOTE]
> Celle-ci est uniquement requise pour la Skype Entreprise charge de travail multimédia et n’est pas applicable aux autres services Microsoft 365'équipe Office 365'équipe.

Ressources supplémentaires :

- [Activation du média Lync pour contourner un tunnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [Plus d'informations sur l'accès direct, la tunnellisation fractionnée et la tunnellisation forcée](/archive/blogs/tomshinder/more-on-directaccess-split-tunneling-and-force-tunneling)

- [Activer l'accès direct](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574163(v=ws.11))

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>Assurer l'ouverture des ports et protocoles appropriés

Les clients doivent s’assurer de l’accessibilité des URL et des adresses IP requises pour le service Microsoft 365 ou Office 365'adresses IP. Pour obtenir ume liste complète de l'ensemble des adresses IP et des URL de Skype Entreprise Online, reportez-vous à la rubrique [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).

Les clients Skype Entreprise utilisent divers ports et protocoles. Le sens et le flux du trafic du réseau d'une session Skype Entreprise variera en fonction du type d'interactions (P2P ou à plusieurs) et de l'utilisation du partage de contenu et des communications voix/vidéo. Vous devez examiner et ouvrir la liste des ports et protocoles, en portant une attention particulière aux ports sources et de destination. Par exemple, le trafic audio utilise uniquement 20 ports (50000-50019 TCP/UDP) côté client, mais le port de destination peut être compris dans une plage de ports de 10k (50000-59999 TCP/UDP) côté service. Cela inclut également l'ouverture des ports TCP 443 et UDP 3478 sur le pare-feu.

Une configuration du réseau supplémentaire peut être également requise pour prendre en charge Skype Entreprise Online.


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Utilisation de téléphones et de périphériques optimisés pour Skype Entreprise

Dans une session mutlimédia en temps réel, les périphériques de média utilisés par tous les participants, tels que des casques et des webcams, ont un fort impact sur la qualité audio et vidéo globale. Les périphériques de qualité inférieure ou dont les pilotes de périphériques sont incorrects produitront une qualité audio globale inférieure pour l’audio et une qualité d’image inférieure pour la vidéo. Les périphériques certifiés ou de bonne qualité, en revanche, améliorent l'annulation d'écho, le filtrage du bruit et la résolution vidéo, et réduisent les temps de latence.

Les téléphones et les périphériques ont un impact considérable sur la qualité de l'audio et de la vidéo pour les utilisateurs finaux. Le programme de certification de Skype Entreprise prend la suite du programme « Lync Compatible » et valide la conformité du périphérique aux normes Microsoft audio et vidéo. De nombreux téléphones IP, périphériques USB audio et vidéo, PC et appareils de salles de réunion ont été testés et certifiés par Microsoft. Vous devez examiner la liste des périphériques optimisés pour Skype Entreprise et veiller à fournir différents périphériques afin de répondre aux besoins divers et préférences personnelles de vos utilisateurs finaux dans votre organisation.

Pour plus d'informations sur les périphériques pris en charge et certifiés, reportez-vous aux rubriques suivantes :  

- [Obtention de numéros de téléphone pour Skype Entreprise Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [Téléphones et de périphériques optimisés pour Skype Entreprise](../../SfbPartnerCertification/certification/devices-ip-phones.md)

- [Catalogue de solutions pour périphériques personnels](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [Téléphones et de périphériques certifiés pour Microsoft Lync](../../SfbPartnerCertification/lync-cert/ip-phones.md)

L'environnement des locaux dans lesquels les utilisateurs se rencontrent et utilisent des périphériques audio et vidéo est un autre facteur important pour la qualité audio et vidéo. Les utilisateurs qui appellent à partir d'un environnement bruyant produiront des échos et un son audio sourd et difficilement audible. Les utilisateurs dans un environnement sombre ou de luminosité faible ne seront pas en mesure de produire une qualité d'image lumineuse et nette pour la vidéo. Dans une salle de conférence, l'emplacement du microphone et du périphérique vidéo ont un impact direct sur la qualité du son et de l'image que les participants recevront.

Pour obtenir une image plus claire de l’expérience audio et vidéo d’un utilisateur, utilisez  >    >  l’application Outils  Skype Entreprise Options périphérique **audio** ou périphérique vidéo pour modifier le périphérique utilisé et personnaliser ses paramètres. Vous pouvez également vérifier la qualité audio d’un appel en cliquant sur **Vérifier la qualité de l’appel.** If they click **Check Call Quality**, they can then report the quality and issues found with the test call.

![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>Sujets associés

[ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)
