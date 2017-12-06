---
title: "Optimisation de votre réseau pour Skype Entreprise Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
description: "Les conditions suivantes sont réellement importantes garantir la réussite et la santé à long terme pour tous les Skype entreprise Online fonctionnalités vous configurez pour votre organisation. Nous indique certains d'entre vous sont très techniques : ce document vous est destiné, mais il existe certains d'entre vous qui ne sont pas. Si vous avez besoin d'aide de la configuration de Skype entreprise Online, vous devez lire ce document afin de vous familiariser avec les choses que vous devez prendre en considération. Il vous donnera également à aborder lorsque vous travaillez avec le Centre de FastTrack Microsoft, vos équipes de compte et les Services Microsoft, ou les partenaires Microsoft de déterminer comment vous peut répondre à ces exigences."
---

# Optimisation de votre réseau pour Skype Entreprise Online

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](b363bdca-b00d-4150-96c3-ec7eab5a8a43.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43). 
  
Les conditions suivantes sont réellement importantes garantir la réussite et la santé à long terme pour tous les Skype entreprise Online fonctionnalités vous configurez pour votre organisation. Nous indique certains d'entre vous sont très techniques : ce document vous est destiné, mais il existe certains d'entre vous qui ne sont pas. Si vous avez besoin d'aide de la configuration de Skype entreprise Online, vous devez lire ce document afin de vous familiariser avec les choses que vous devez prendre en considération. Il vous donnera également à aborder lorsque vous travaillez avec le [Centre de FastTrack Microsoft](https://fasttrack.microsoft.com/office), vos équipes de compte et les Services Microsoft, ou [les partenaires Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search) de déterminer comment vous peut répondre à ces exigences.
  
## Aperçu rapide

Skype Entreprise vous permet de communiquer avec vos collègues et partenaires professionnels au sein de votre société ou dans le monde entier.
  
Avec Skype Entreprise, vous pouvez :
  
- Démarrer des conversations à l'aide de la messagerie instantanée, de l'appel audio ou vidéo
    
- Savoir si vos contacts sont disponibles en ligne, en réunion, ou en présentation
    
- Définir une sécurité de niveau professionnel pour vos réunions
    
- Diffuser en ligne pour un nombre élevé de participants
    
-  Présenter votre écran lors de réunions ou en donner le contrôle à des participants
    
- Utiliser Skype Entreprise dans d'autres programmes Office pour discuter, passer un appel, ou participer à une réunion en un clic
    
## Pourquoi cela est-il si important ?

La qualité multimédia en temps réel (audio, vidéo et partage d'applications) sur IP est largement impactée par la qualité de la connectivité réseau de bout en bout. Pour bénéficier d'une qualité optimale pour Skype Entreprise Online, assurez-vous de la bonne qualité de la connexion entre votre réseau d'entreprise et Skype Entreprise Online. La meilleure façon d'y parvenir est de configurer la connectivité du réseau interne et du cloud en fonction de la capacité de votre réseau à s'adapter au volume du trafic maximal de Skype Entreprise Online sur l'ensemble des connexions.
  
Utilisez un [partenaires Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search), vous pouvez vous connecter divers notamment Skype entreprise Online dans le cloud à votre réseau et vocale en temps réel et des fonctions de communications vidéo pour Skype pour les applications Office 365 Entreprise nécessitent des services de réseau doivent être configurés spécialement pour prendre en charge ces charges de travail en temps réel d'Office 365. Cela inclut un réseau possédant une bande passante suffisante pour effectuer le volume de trafic requis et prendre en charge de la qualité de Service (qualité de service) pour offrir un environnement de classe entreprise pour vos utilisateurs.
  
En plus des présentes informations, d'autres ressources peuvent vous aider à planifier et à déployer les services et fonctionnalités Skype Entreprise Online de façon appropriée, et à vous assurer que vos services de réseau sont conformes aux exigences :
  
- [Flux d'appels avec ExpressRoute](call-flow-using-expressroute.md)
    
- [ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)
    
## Mise en œuvre de la qualité de service (QoS) pour Skype Entreprise Online

Avant de passer à Skype entreprise Online, vous devez prendre un aperçu de la capacité de votre réseau pour gérer audio, vidéo et le trafic de session de partage. Comme avec d'autres services Office 365, Microsoft a disponibles pour télécharger la [Skype entreprise bande passante calculatrice](https://www.microsoft.com/en-us/download/details.aspx?id=19011) qui est utilisée pour déterminer le trafic réseau requis pour chacun de vos sites de société. Vous devez effectuer modélisation de l'utilisation, y compris les flux de communication en temps réel du trafic multimédia et la quantité de Skype pour le trafic entreprise par emplacement de la société, de modélisation calculer le volume de trafic et l'analyse de l'impact de ce trafic sur votre réseau global. Une fois que vous avez terminé qui, analyse de ces données doit fournir les recommandations de l'endroit où votre réseau doit être amélioré et vous recommandons de tailles de file d'attente pour fournir une expérience de l'utilisateur final excellente.
  
Skype pour le trafic en temps réel d'entreprise est sensible à la perte de paquets, retard et gigue, qui se produisent fréquemment dans les réseaux saturés. Qualité de Service (qualité de service) - parfois appelé classe de Service - doit également être déployée sur WAN externes gérées, gérée LAN interne et réseaux Wi-Fi enterprise. Cela vous aidera à hiérarchiser correctement Skype pour le trafic en temps réel d'entreprise tels que les fonctionnalités audio et vidéo sur un autre trafic non - en temps réel sur des réseaux locaux et sur WAN, création d'une meilleure expérience pour l'utilisateur final.
  
Skype pour le son de l'entreprise doit être déployé dans le FE (expédiées de transfert - DSCP 46) file d'attente et Skype pour la vidéo de l'entreprise doivent être déployé dans le AF41 (assuré de transfert - DSCP 34) file d'attente. C'est vrai même pour le trafic égal à égal et conférences, indépendamment que système téléphonique dans Office 365 ou autres fonctionnalités de téléphonie sont déployées.
  
Lors de la qualité de service existante stratégies est peut-être déjà en place sur le réseau local et WAN pour d'autres produits de la téléphonie IP, Skype entreprise permet aux utilisateurs d'être mobiles et pour passer d'un emplacement à l'autre lors de l'utilisation du service. Pour cette raison, les stratégies de qualité de service doivent être marqués du réseau local, les WAN et les réseaux sans fil afin de vous assurer que toutes les Skype pour le trafic entreprise est priorité sur des réseaux gérées.
  
Pour vous aider à déterminer la taille de votre réseau, téléchargez l'[outil de calcul de bande passante de Skype Entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=19011).
  
Pour en savoir plus sur la qualité multimédia et la QoS, reportez-vous à la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
Pour plus d'informations sur la configuration et la gestion de qualité de service, voir [Gestion de la qualité de Service](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## Contournement des proxys et des périphériques d'optimisation du réseau WAN

Tous les Office 365, y compris Skype entreprise Online est chiffré et n'est généralement pas en mesure à inspecter par les périphériques de proxy. C'est pourquoi nous vous recommandons d'ignorer les périphériques proxy pour Office 365 trafic réseau, telle que définie en tant que connexions qu'apporter de vos utilisateurs à [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Dans la mesure où les périphériques proxy seront susceptible d'introduire retard dans Skype en temps réel pour des flux de données multimédias entreprise Online, que nous vous recommandons vivement d'ignorer les périphériques proxy au minimum pour que le trafic.
  
Microsoft recommande d'exclure les URL d'Office 365 utilisant des fichiers PAC pour envoyer du trafic Office 365 vers un pare-feu. 
  
Voici quelques ressources supplémentaires qui peuvent également être utiles :
  
- [Optimisation des performances d'Office 365 à l'aide de lignes de référence et de l'historique des performances](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Planification du réseau et de la migration pour Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Générateur de proxy PAC d'Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Utilisation du contrôleur d'optimisation du réseau WAN ou des périphériques de trafic/d'inspection avec Office 365](https://aka.ms/kb2690045)
    
- [Acheminement avec ExpressRoute pour Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## Contournement du double chiffrement

Pour fournir aux utilisateurs la meilleure possible expérience audio et vidéo, vous devez implémenter une solution qui empêche Skype pour les éléments multimédias Business (audio et vidéo) de parcourir un tunnel de réseau privé virtuel (VPN). Tous les Skype pour le trafic entreprise est chiffré avec sécurité TLS (Transport Layer) et les charges de travail multimédia sont chiffrés avec Secure en temps réel protocole SRTP (). Signalisation est chiffré avec TLS et les charges de travail multimédia sont chiffrés avec SRTP. Envoi de que ce trafic via le tunnel VPN ajoute une couche de chiffrement et les sauts de réseau supplémentaire entre le client et Office 365 supplémentaire, qui peuvent entraîner une session dégradée car elle augmente gigue, perte de paquets et la latence.
  
Une option pour empêcher Skype pour le trafic entreprise parcourir le tunnel VPN est fractionné tunnel. Pour mettre en œuvre tunnel fractionnement, les clients peuvent consulter avec leur fournisseur VPN sur les caractéristiques de la procédure à suivre dans leurs logiciels.
  
> [!NOTE]
> Cela est uniquement requis pour les charges de travail multimédia de Skype Entreprise et n'est pas applicable aux autres services d'Office 365. 
  
Ressources supplémentaires :
  
- [Activation du média Lync pour contourner un tunnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Plus d'informations sur l'accès direct, la tunnellisation fractionnée et la tunnellisation forcée](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Activer l'accès direct](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## Assurer l'ouverture des ports et protocoles appropriés

Les clients doivent assurer l'accessibilité des URL et des adresses IP requises pour le service d'Office 365. Pour obtenir ume liste complète de l'ensemble des adresses IP et des URL de Skype Entreprise Online, reportez-vous à la rubrique [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
  
Les clients Skype Entreprise utilisent divers ports et protocoles. Le sens et le flux du trafic du réseau d'une session Skype Entreprise variera en fonction du type d'interactions (P2P ou à plusieurs) et de l'utilisation du partage de contenu et des communications voix/vidéo. Vous devez examiner et ouvrir la liste des ports et protocoles, en portant une attention particulière aux ports sources et de destination. Par exemple, le trafic audio utilise uniquement 20 ports (50000-50019 TCP/UDP) côté client, mais le port de destination peut être compris dans une plage de ports de 10k (50000-59999 TCP/UDP) côté service. Cela inclut également l'ouverture des ports TCP 443 et UDP 3478 sur le pare-feu.
  
Une configuration du réseau supplémentaire peut être également requise pour prendre en charge Skype Entreprise Online.
  
Vous pouvez exécuter le test FastTrack Cloudapp à partir de vos ordinateurs clients pour vérifier que la configuration est correcte :
  
- **Amérique du Nord :**
    
  - [Analyse du réseau à l'aide de Fast Track d'Office 365 (Amérique du Nord)](http://na1-fasttrack.cloudapp.net/)
    
  - [https://137.117.72.96](https://137.117.72.96)
    
- **Zone EMEA :**
    
  - [Analyse du réseau à l'aide de Fast Track d'Office 365 (EMEA)](http://em1-fasttrack.cloudapp.net/)
    
  - [https://137.116.212.202](https://137.116.212.202)
    
- **Zone APAC :**
    
  - [Analyse du réseau à l'aide de Fast Track d'Office 365 (Asie-Pacifique)](http://ap1-fasttrack.cloudapp.net)
    
  - [https://168.63.169.67](https://168.63.169.67)
    
Vous pouvez également voir, [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## Utilisation de téléphones et de périphériques optimisés pour Skype Entreprise

Dans une session mutlimédia en temps réel, les périphériques de média utilisés par tous les participants, tels que des casques et des webcams, ont un fort impact sur la qualité audio et vidéo globale. Les périphériques de qualité inférieure ou dont les pilotes sont incorrects produiront globalement des sons et des images de moins bonne qualité. Les périphériques certifiés ou de bonne qualité, en revanche, améliorent l'annulation d'écho, le filtrage du bruit et la résolution vidéo, et réduisent les temps de latence.
  
Téléphones et appareils faire une grande différence de la qualité de l'audio et vidéo pour les utilisateurs finaux. La Skype pour le programme de certification d'entreprise est une évolution du programme « Lync Compatible » et valide que l'appareil est conforme aux normes de Microsoft pour l'audio et vidéo. Il existe un certain nombre de téléphones IP, USB périphériques audio et vidéo, PC et périphériques de salle qui ont été testés et certifiés par Microsoft de la réunion. Vous devez examiner la liste des périphériques qui sont optimisés pour Skype entreprise et travail fournir différents appareils afin de répondre aux besoins différents et les préférences de vos utilisateurs finaux de votre organisation.
  
Pour plus d'informations sur les périphériques pris en charge et certifiés, reportez-vous aux rubriques suivantes :
  
- [Obtention de numéros de téléphone pour Skype Entreprise Online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Téléphones et de périphériques optimisés pour Skype Entreprise](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Catalogue de solutions pour périphériques personnels](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Téléphones et de périphériques certifiés pour Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
L'environnement des locaux dans lesquels les utilisateurs se rencontrent et utilisent des périphériques audio et vidéo est un autre facteur important pour la qualité audio et vidéo. Les utilisateurs qui appellent à partir d'un environnement bruyant produiront des échos et un son audio sourd et difficilement audible. Les utilisateurs dans un environnement sombre ou de luminosité faible ne seront pas en mesure de produire une qualité d'image lumineuse et nette pour la vidéo. Dans une salle de conférence, l'emplacement du microphone et du périphérique vidéo ont un impact direct sur la qualité du son et de l'image que les participants recevront.
  
Pour obtenir une image plus claire d'utilisation d'expérience audio et vidéo d'un utilisateur le Skype entreprise application **Outils** > **Options** > **Périphérique Audio** ou **Périphérique vidéo** apporter des modifications à l'appareil en cours d'utilisation et la personnalisation de ses paramètres. Vous pouvez également vérifier la qualité d'un appel audio en cliquant sur **Vérifier la qualité des appels**. S'ils cliquent sur **Vérifier la qualité des appels**, ils peuvent signaler puis la qualité et les problèmes rencontrés avec l'appel de test.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## Rubriques connexes

[ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online](expressroute-and-qos-in-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

