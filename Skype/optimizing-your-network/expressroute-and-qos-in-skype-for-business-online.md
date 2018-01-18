---
title: "ExpressRoute et QoS dans Skype pour l’activité en ligne"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Découvrez comment utiliser Azure ExpressRoute d’un réseau avec les besoins en bande passante et des capacités de qualité de Service pour une expérience utilisateur de classe entreprise. "
ms.openlocfilehash: 7073840031013d41013762b190ccdc568840cceb
ms.sourcegitcommit: 61127a5723fe58545b0b19edb2e2d4260965eb4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2017
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute et QoS dans Skype pour l’activité en ligne

Se connecter à Office 365 via une connexion de réseau dédié à l’aide de ExpressRoute d’Azure pour Office 365 et Skype pour l’activité en ligne. Votre connexion dédiée pour votre Skype pour les applications d’entreprise vous offre des performances fiables et prévisibles, ainsi que la confidentialité à l’internet public. Vous pouvez maintenant acheter une meilleure connexion réseau vers Office 365 et Skype pour entreprise en ligne qui ajoute la prévisibilité, fiabilité de classe entreprise et est fourni avec un contrat SLA de durée active.
  
> [!NOTE]
> Une nouvelle version de la calculatrice de la bande passante est disponible : [Skype pour les entreprises, la bande passante calculatrice](https://go.microsoft.com/fwlink/?LinkId=715766). Toutefois, les instructions de ce document utilisent le Lync 2010 et Calculatrice de bande passante 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype pour les activités en ligne et ExpressRoute

Travaillez avec des partenaires de ExpressRoute de Microsoft, vous pouvez connecter une variété d’applications Office 365, notamment Skype pour Business Online dans le nuage sur une connexion dédiée. Toutefois, les voix en temps réel et les capacités de communications vidéo pour Skype pour les entreprises exigent des services réseau qui sont spécialement configurés pour prendre en charge de ces charges de travail en temps réel d’Office 365. Cela inclut un réseau disposant d’une bande passante suffisante pour porter le volume nécessaire de trafic et de prendre en charge de la qualité de Service (QoS) pour fournir une expérience de classe entreprise pour vos utilisateurs.
  
Ce document est conçu pour vous, les administrateurs et les concepteurs de réseau comprendre les défis particuliers que nécessaires pour prendre en charge les communications en temps réel, les outils fournis par Microsoft pour vous aider dans la conception d’un réseau capable de prendre en charge ceux configuration requise et vous guident tout au long du processus de conception à l’aide d’une étude de cas. 
  
La première partie de ce document vous guide tout au long une étude de cas pour vous aider dans la conception du réseau à l’aide [Lync 2010 et Calculatrice de bande passante 2013](https://go.microsoft.com/fwlink/?LinkId=690282) pour estimer la configuration réseau requise pour un Skype volumineux, sur plusieurs sites pour le déploiement de Business ExpressRoute. La deuxième partie de ce document vous donne les concepts fondamentaux de la qualité de Service (QoS), un approfondi pour les détails techniques spécifiques de prise en charge de Skype pour les communications en temps réel de l’entreprise et des types de services réseau spécifiques Si nécessaire.
  
Toutes les informations ici vous donne les détails techniques et présentation de qualité de service et de ExpressRoute, une compréhension des défis spécifiques que vous allez être confronté à et vous offrent une connaissance des outils et des techniques qui vous permettront avec succès déployer un ExpressRoute sur votre Skype pour le réseau d’entreprise. 
  
## <a name="getting-started"></a>Mise en route

Lorsque vous préparez pour ExpressRoute pour Skype pour les entreprises, il est judicieux d’examiner les différents modèles de connexion ExpressRoute et les différents choix de partenaires et d’emplacements et de lire les modalités d’achat et de provisionner des ExpressRoute au sein de votre entreprise. Voici quelques ressources pour vous aider à démarrer : 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Tarification de la ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentation de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Partie 1 : étude de cas - ExpressRoute Dewey Law, LLC.

Cette étude de cas, Dewey, Law, LLC. Affiche la configuration d’un réseau, les services d’accès réseau ordre et déterminer les exigences de bande passante pour prendre en charge des ExpressRoute pour Skype pour l’activité en ligne.
  
 **Arrière-plan** Loi de dewy LLC. un grand national cabinet 790 avocats et un total de 5,580 employés est réparti sur plusieurs 78 emplacements. L’entreprise possède un siège social à New York, trois bureaux régionaux à Chicago, San Francisco et Dallas, ainsi que de grand de 24 et 50 petites succursales réparties dans tout le pays. L’entreprise gère les cas de vastes et complexes avec la charge de travail généralement répartie sur deux ou plusieurs des bureaux. Ayant des résultats de cette conception réseau considérable de trafic réseau entre les bureaux.
  
Loi de dewy LLC. est une entreprise relativement jeune et les avocats et autres membres du personnel sont très à l’aise avec la technologie considérablement en dépendent pour leur travail quotidien. 
  
 **Distribution des utilisateurs en positions et d’emplacements**
  
||**Siège social (NY)**|**Bureaux régionaux (3)**|**Succursales de grande taille (24)**|**Petites succursales (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Exécutif  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partenaires  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Associe  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Paralegal  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Administrateurs de direction  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|INFORMATIQUE et d’administration générale  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Total par site  <br/> |1,070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Total par classe de site  <br/> |1,070  <br/> |1,035  <br/> |1,680  <br/> |1 800  <br/> |
   
### <a name="setting-up-the-network"></a>Configuration du réseau

Pour fournir des services en temps réel de cohérence et de haute qualité pour Dewey Law LLC., il y a quelques exigences de notions de base qui doivent être remplies :
  
- Ils souhaitent fournir des services de voix pendant une panne de courant pour leurs routeurs et les commutateurs de distribution réseau doivent fournir l’alimentation via Ethernet (PoE) IEEE 802.3af ou 802.3at.
    
- Les commutateurs et les routeurs réseau doivent également utiliser des sources d’alimentation sans interruption (UPS) afin qu’ils peuvent continuer à fonctionner pendant une panne de courant.
    
    Ils ont une connexion Wi-Fi à leurs bureaux LAN, nous vous recommandons fortement qu’ils utilisent un Skype certifiée pour partenaire d’infrastructure métier Wi-Fi de [Skype pour Solutions d’entreprise](https://go.microsoft.com/fwlink/?LinkId=690281).
    
    > [!TIP]
    >  points d’accès sans fil 802.11n et 802.11ac sont recommandés.
  
- Et, plus important encore, tous les réseaux LAN dans tous les bureaux doivent être configuré pour fournir la qualité de Service (QoS). Cela inclut les PC, ordinateurs portables et n’importe quel matériel de réseau tels que les commutateurs et les routeurs.
    
Maintenant que vous avez les bases couverts, afin de fournir des services de téléphonie de qualité entreprise pour Dewey Law LLC., nous recommandons à l’aide du service de commutation d’étiquette multiprotocole (MPLS) IP à partir d’un partenaire de service de réseau qui se connecte au service de ExpressRoute d’Azure. MPLS propose un service IP avec des garanties de performances pour la perte de paquets, l’instabilité et retard. Toutefois, si MPLS n’est pas disponible, Ethernet connecté à l’un de nos ExpressRoute partenaires de données exchange peuvent également être utilisés.
  
Fournisseurs de MPLS offrent plusieurs classes de niveaux de service, mais chaque utilisation des termes différents pour les identifier. Vous devrez travailler en étroite collaboration avec votre fournisseur pour s’assurer qu’ils comprennent les données que vous avez entrée dans [Lync 2010 et la calculatrice de la bande passante 2013](https://go.microsoft.com/fwlink/?LinkID=690282) et les options disponibles et sont recommandés pour la charge de travail en temps réel Office 365 différent applications.
  
Il existe deux options pour comment les données de Skype pour des applications d’entreprise peuvent être mappées aux classes de service MPLS appropriés :
  
- Marquage de point de terminaison du trafic à l’aide du Point de contrôle de DiffServ (DSCP)
    
- Network Access Control List (ACL) sur
    
Pour implémenter le marquage du point de terminaison, vous devez configurer toutes les machines Windows de domaine joint pour sous la rosée loi LLC. Pour marquer chaque paquet avec le marquage de Point de contrôle de DiffServ (DSCP) approprié et ensuite implémenter QoS sur tous les routeurs et les commutateurs réseau sur tous les sites office pour vous assurer que la qualité de service, marques sont conservées et ne sont pas supprimés. Les marquages de DSCP dans des paquets réseau indiquent le fournisseur de services de paquet réseau est la priorité. **Il y a plus d’informations sur DSCP dans la section de QoS dans la partie 2.**
  
Réseau d’affectation basée sur les ACL, les marquages de priorité DSCP sont mises en œuvre au niveau d’un routeur en amont et sont basées sur le port UDP source. Les plages de port recommandé pour chaque application sont répertoriées dans la Section 2.6.1.1 de [Planification de réseau, de surveillance et de dépannage avec Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286). Il est important de coordonner cela avec l’implémentation de QoS et la conception globales de loi LLC sous la rosée et être informés des différentes stratégies de QoS et le potentiel pour le marquage des incompatibilités des paquets.
  
Chaque fournisseur de services réseau ExpressRoute aura une classe de service (QoS) qui est appropriée pour la vidéo et vocales en temps réel. Ce COS est appelée « Expedited transfert » (EF) pour voix et « Assured Forwarding » (AF) pour la vidéo. Vous devez être très prudent dans la quantité de bande passante que vous achetez pour la voix du trafic d’EF de dimensionnement. La raison est que la classe de la voix du service est très implacables en cas de vous envoyez du trafic voix plus que la classe de service est mis en service pour.
  
> [!TIP]
>  Tout le trafic envoyé sur la classe voix de service plus les engagement du fournisseur de services est supprimé immédiatement qui dirigera une qualité de voix effet.
  
Lorsque vous examinez la conception globale de sous la rosée loi LLC. Il est extrêmement important que vous déterminiez précisément la quantité de bande passante réseau dont ils ont besoin pour prendre en charge le trafic vocal sur leur réseau et être marquant chaque paquet voix (et uniquement les paquets de voix) avec la valeur DSCP pour voix (c'est-à-dire DSCP EF 46).
  
Pour mettre en œuvre QoS au sein de leur entreprise, réseau, les routeurs ou points de terminaison doit marquer chaque paquet avec l’indicateur de priorité de couche 3 (c'est-à-dire DSCP) approprié. Le long du tracé de l’ensemble du réseau, chaque commutateur et du routeur doivent avoir activé l’option de qualité de service. La QoS marques sur les paquets de voix ou vidéo passant par ce commutateur ou le routeur peuvent être de même qu’un seul commutateur réseau ou un routeur qui n’a pas activé de QoS, supprimé. Cela désactive efficacement QoS dans tous les commutateurs en aval et les routeurs qui diminue la valeur de la ExpressRoute.
  
Cela nécessite également que l’association des priorités de couche 3 et de couche 2 QoS est défini à chaque point. Les mécanismes de priorité de couche 2 sont définis dans IEEE 802 .1p pour les réseaux câblés et 802.11e / WMM pour réseaux Wi-Fi. Plus important encore, le routeur du réseau face à réseau du fournisseur de services réseau MPLS doit conserver les paramètres DSCP sur tous les paquets sortants afin qu’ils conserveront la classe MPLS appropriée du service. 
  
> [!TIP]
>  Pour plus d’informations concernant la configuration de la qualité de service, reportez-vous à la Section 2.6 de [Planification de réseau, de surveillance et de dépannage avec Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669). Vous pouvez également voir [planifier la configuration réseau requise pour Skype pour entreprise 2015](https://go.microsoft.com/fwlink/?LinkId=690287) pour la planification des besoins du réseau plus.
  
### <a name="ordering-network-access-services"></a>Ordre de tri Access Services de réseau

Une fois que les conditions préalables du réseau QoS et les mécanismes en place pour prendre en charge les ExpressRoute, l’étape suivante consiste à passer une commande pour les services d’accès réseau ExpressRoute. Lorsque vous commandez des services d’accès ExpressRoute pour LLC de droit sous la rosée du partenaire de fournisseur de services réseau Microsoft, vous devrez fournir deux choses :
  
- Le montant total de la bande passante requise pour connecter chaque site à ExpressRoute et Office 365.
    
- La bande passante totale requise pour chaque classe de service qui est nécessaire pour prendre en charge des applications de gestion qui sont utilisées au LLC de droit sous la rosée Skype. La classe de service requis de la bande passante est pilotée par le volume de trafic prévu à partir de chaque de la Skype différents pour les applications métier comme des voix, vidéo, messagerie instantanée, présence et le partage d’écran.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Détermination des exigences de bande passante pour Skype pour des Applications d’entreprise

Pour Dewey Law LLC., une fois que vous avez déterminé la bande passante totale requise vous devez maintenant savoir comment ce montant total de la bande passante doit être divisé entre les différentes classes de service. Par exemple, la bande passante pour chaque Skype pour une application d’entreprise.
  
Pour déterminer ces exigences à chacun des sous la rosée loi LLC. sites, que vous allez utiliser [Calculatrice de la bande passante 2013 et de Lync 2010](https://go.microsoft.com/fwlink/?LinkID=690282). Cette calculatrice est un outil basé sur Excel qui vous permet de spécifier l’usage prévu de le Skype différents pour les applications commerciales, y compris des voix, vidéo, conférence et partage d’écran. La calculatrice utilisera pour générer automatiquement une estimation de la bande passante et CoS exigences pour chaque site sur leur réseau. Lorsque vous téléchargez le Lync 2010 et Calculatrice de bande passante 2013, un guide utilisateur également être téléchargé que qui vous donnera plus d’informations sur l’utilisation. 
  
Pour vous aider dans la feuille de calcul, les cellules différentes de la feuille de calcul apparaissent en couleurs :
  
- **Vert** Il s’agit de zones d’entrée de données générales.
    
- **Jaune** Ceux-ci sont des zones d’entrée de données. Vous pouvez modifier ces paramètres, mais le faire avec précaution.
    
- **Rouge** Ces zones en lecture seule et sont des valeurs d’entrée verrouillées et ne peut pas être modifiées.
    
- **Gris** Il s’agit de zones d’affichage uniquement. Ils sont les résultats ou les données à partir des zones d’entrée générales.
    
Le processus de conception pour sous la rosée loi LLC. commence par la caractérisation de leurs utilisateurs dans différentes 'personnages'. Pour chaque personnage que vous définissez, vous pouvez spécifier leur utilisation prévue de la Skype différents pour des applications d’entreprise ('None', 'Faible', 'Moyennes', 'Élevées' ou un des trois paramètres définis 'Custom'). Ces sélections sont disponibles dans la feuille de calcul 'Personnage'. L’utilisation spécifique pour chaque choix (« Bas », « Moyen » ou « Haute ») est fournie, mais les valeurs par défaut pour chaque choix peuvent être modifiés. En identifiant le nombre d’utilisateurs pour chaque personnage qui se trouve dans chaque site, la calculatrice peut calculer la bande passante totale requise pour chaque emplacement.
  
Vous pouvez également spécifier l’audio et codecs vidéo utilisés, utilisation de correction aval des erreurs et également autres paramètres système qui affectent les besoins en bande passante. Vous pouvez utiliser les paramètres par défaut dans le Lync 2010 et Calculatrice de bande passante 2013 ou sélectionnez différents codecs et autres paramètres système. Conception du site sous la rosée loi LLC, les paramètres par défaut peuvent être destinés. Toutefois, pour modifier à partir de la valeur par défaut les paramètres est un menu déroulant avec tous les choix disponibles. Les bandes passantes utilisées pour chaque choix figurent dans la feuille de calcul « Codecs ». Lorsque vous modifiez un paramètre, la modification de la bande passante et de la classe de service (CoS) combinaison sur chaque site est mis à jour. Cette fonctionnalité permet à tester différentes configurations possibles pour eux et voir l’impact de modifications sur les exigences de bande passante.
  
Nous avons défini trois personnages pour Dewey Law LLC., ' Exécutif/partenaire', ' Associer/Paralegal' et « Administrateurs informatiques ». Le tableau ci-dessous montre comment nous avons défini les profils d’utilisation pour les divers Skype pour les applications métier pour chaque personnage.
  
 **Les personnages et les profils d’utilisation (« Personnage » feuille de calcul - colonnes A à P)**
  
|**Personnage**|**Messagerie instantanée/présence**|**P2P audio**|**Vidéo de P2P**|**Audio de la conférence**|**Conférence vidéo**|**Partage du bureau**|**Audioconférence**|**Lync 2010 RTV_Type**|**Remote Users**|**Lync 2013 stereo audio**|**Lync 2013 video quality**|**Comportement d’utilisateurs Lync 2013 pour la fenêtre de la vidéo P2P**|**Utilisation des vues multiples de Lync 2013**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Direction / partenaire  <br/> |Élevée  <br/> |Moyenne  <br/> |Low  <br/> |Moyenne  <br/> |Moyenne  <br/> |Aucun  <br/> |Moyenne  <br/> |CAF  <br/> |0%  <br/> |0%  <br/> |Best  <br/> |Par défaut  <br/> |Par défaut  <br/> |
|Associer / Paralegal  <br/> |Élevée  <br/> |Moyenne  <br/> |Low  <br/> |Moyenne  <br/> |Élevée  <br/> |Élevée  <br/> |Moyenne  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Moyenne  <br/> |Par défaut  <br/> |Par défaut  <br/> |
|IT admins  <br/> |Élevée  <br/> |Moyenne  <br/> |Aucun  <br/> |Faible  <br/> |Aucun   <br/> |Aucun  <br/> |Moyenne  <br/> |CAF  <br/> |0%  <br/> |0%  <br/> |Moyenne  <br/> |Par défaut  <br/> |Par défaut  <br/> |
   
Vous devez entrer les informations dans la table de la **Distribution des utilisateurs en positions et d’emplacements** ci-dessus dans la feuille de calcul « Sites » de la Lync 2010 et Calculatrice de bande passante 2013. Comme le nombre d’utilisateurs dans les bureaux régionaux est identique, ils sont définis pour un 'Site' et indiqués qu’il existait trois instances de celui-ci. A effectuer la même opération pour les succursales de grandes et petites il y a eu 24 à 50 utilisateurs dans les sites, respectivement.
  
Après avoir spécifié les paramètres pour chaque personnage, vous devez entrer le nombre d’utilisateurs dans chaque personnage sur chaque site dans la feuille de calcul « Sites ». Le nombre total d’utilisateurs pour tous les sites est automatiquement mis à jour. Dans la mesure où les utilisateurs ne sont pas à l’emplacement d’Office 365, ils doivent tous être saisis dans les lignes « Succursales » de la feuille de calcul. The Lync 2010 and 2013 Bandwidth Calculator then populates the 'Best Effort Class', 'Data Traffic Class' and 'Real-time traffic class' columns in the 'WAN BW per QoS traffic class' table. This is shown in the data in the table below.
  
> [!TIP]
>  The full spreadsheet also includes the maximum number of simultaneous sessions for each application, but we deleted those columns to save space.
  
 **Personas by site - ('Sites' Worksheet- Columns A, D, I and AI through AX)**
  
|**Nom du site**|**Total Users in Site**|**Ce type de Sites total**|**Profil de l’utilisateur 1**|**L’utilisateur du profil 1**|**Profil de l’utilisateur 2**|**L’utilisateur du profil 2**|**User Profile 3**|**User's of Profile 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Headquarters  <br/> |1070  <br/> |1  <br/> |Executive/Partner  <br/> |170  <br/> |Associate/Paralegal  <br/> |700  <br/> |Administrateurs informatiques  <br/> |200  <br/> |
|Bureaux régionaux  <br/> |345  <br/> |3  <br/> |Exécutif/partenaire  <br/> |60  <br/> |Associer/Paralegal  <br/> |225  <br/> |Administrateur informatique  <br/> |60  <br/> |
|Large branch offices  <br/> |70  <br/> |24  <br/> |Executive/Partner  <br/> |11  <br/> |Associate/Paralegal  <br/> |50  <br/> |IT admin  <br/> |9  <br/> |
|Small branch offices  <br/> |36  <br/> |50  <br/> |Executive/Partner  <br/> |6  <br/> |Associate/Paralegal  <br/> |25  <br/> |IT admin  <br/> |1  <br/> |
   
 **Bande passante requise par l’application par site en Kbits/s (« Feuille de calcul Sites »-colonnes A et BQ par le biais de saut de ligne)**
  
|**Site**|**Pic de SIP / bande passante de messagerie instantanée**|**Pic de bande passante Intersite homologue Audio**|**Pic de bande passante vidéo de poste Intersite**|**Peak Audio Conferencing bandwidth**|**Peak Video Conferencing bandwidth**|**Peak WAN Share bandwidth**|**Peak WAN bandwidth for PSTN Calls**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Headquarters  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Regional Offices  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Large Branches  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |
|Small Branches  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |
   
Probably the most important columns in the spreadsheet are those that describe the WAN bandwidth by QoS class. This is shown in the table below. This data summarizes the information you will need to provide to the network service provider to order the access connection at each of your sites. When calculating total bandwidth, please remember to multiply the bandwidth for each type of branch sites by the number of sites of the same type. To connect with your ExpressRoute network services partner, you can see [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
It is very important that you don't exceed the bandwidth in the voice or 'Expedited Forwarding' (EF) class of service. A random set of packets will be discarded so rather than reducing the quality of a single call or group of calls, all of the calls in progress can be impacted. It is also important that only voice be marked with the DSCP for EF (i.e. DSCP = 46) or the voice queue could overflow when of non-voice traffic is added.
  
> [!TIP]
>  Again, while the EF class of service offers the best performance guarantee, if you exceed the defined bandwidth, any additional packets will immediately be discarded.
  
 **Aggregate bandwidth per site by QoS traffic class - ('Sites' Worksheet- Columns A and ML through MR)**
  
|**Nom du site**|**Classe de meilleur effort (DSCP 0)**|**Data traffic class (DSCP custom)**|**Real-time traffic class (DSCP 34, AF41)**|**Priority traffic class (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Headquarters  <br/> |0,00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Regional Offices  <br/> |0,00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Branches de grande taille  <br/> |0,00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Small Branches  <br/> |0,00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Mettre votre projet en action

We can calculate the total bandwidth that will traverse the WAN and the amount of bandwidth that will traverse ExpressRoute, using the bandwidth estimates from the **Per application Per site** table above. The portion of traffic that traverses ExpressRoute excludes the inter-site peer bandwidth.

 
|**Site**|**Peak SIP / IM bandwidth**|**Peak Audio Conferencing bandwidth**|**Peak Video Conferencing bandwidth**|**Peak WAN Share bandwidth**|**Pic de bande passante WAN pour les appels RTPC**|**Nombre total de ExpressRoute<br/>le trafic par classe de site<br/>(c'est-à-dire total<br/>fois le nombre de sites)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Siège social** <br/> |1,070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Bureaux régionaux** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Branches de grande taille** <br/> |70  <br/> |102,00  <br/> |600,00 €  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Petites succursales** <br/> |36  <br/> |76.50  <br/> |600,00 €  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Cela signifie que Skype pour le trafic en ligne Business qui va parcourir la voie express sera environ 114 Mbits/s, sous la rosée auront besoin d’au moins l’abonnement 200 Mbits/s pour ExpressRoute. Plusieurs circuits ExpressRoute peuvent être achetés en différents endroits d’homologation ExpressRoute. Cela pourrait être recommandé si les sites de sous la rosée sont dans différentes régions géographiques ou de fournir la résilience dans le cas où un échec de connexion au circuit de ExpressRoute. Si vous achetez des circuits ExpressRoute dans plusieurs régions d’Azure, le complément de la prime ExpressRoute devront recevoir la connectivité globale sur ExpressRoute.
  
Maintenant que vous disposez de la quantité totale de la bande passante requise et la classe de service (CoS) les numéros de la bande passante vous pouvez placer vos commandes avec le réseau sélectionné service fournisseur (s). N’oubliez pas d’inclure les estimations de trafic pour les autres applications et services. Nous vous proposons réseau planification pour d’autres services Office 365, y compris les calculatrices de bande passante pour Exchange et OneDrive. Abonnement de la bande passante pour le fournisseur de services réseau sera plus élevé car le trafic intra-site devra être rajoutés. Le Lync 2010 et Calculatrice de bande passante 2013 fournit uniquement une estimation du trafic prévu, par conséquent, il est recommandé de confirmer la capacité du réseau pour prendre en charge le volume de trafic de réalisation d’un test de stress. 
  
> [!TIP]
> Votre réseau de test de contrainte est fortement recommandée lorsque vous effectuez une évaluation préliminaire du réseau. 
  
Un test de stress implique la création et configuration de l’infrastructure, puis de l’exécuter avec le volume prévu de trafic simulé lors de l’analyse des performances. Des estimations de trafic peuvent être inexactes dans certaines zones, mais au moins, vous pouvez être sûr qu’il peut prendre en charge le volume de trafic la Lync 2010 et prévisible de la calculatrice de la bande passante 2013. Il est recommandé que vous exécuter le test de stress pour un minimum de quelques jours, mais en l’exécutant pour de longues périodes peut vous aider à affiner les numéros. Cependant, la prolongation de la durée du test de contrainte doit être tempéré par le coût des services réseau réel que vous payez qui ne sont pas transportant le trafic de réseau utilisateur réel. Microsoft a certifié un nombre de fournisseurs dans le cadre de son programme informatique de Pro Tools pour fournir des outils de gestion et des opérations réseau, y compris les outils de contrainte de l’évaluation préliminaire de réseau. Skype pour entreprise fournit également un système intégrateurs de systèmes (SI) qui peut prendre les outils Pro informatique certifiés et qui peut effectuer l’évaluation de réseau pour vous. Vous pouvez en savoir plus, visitez [Skype pour Solutions d’entreprise : IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
Tests de stress fournit un élément de confirmation que le réseau peut prendre en charge le volume de trafic qui sera nécessaire, mais en réalité le Lync 2010 et 2013 données de calcul de la bande passante peuvent être désactivé pour différentes raisons. Vous devez également envisager de continuer de surveiller vos réseaux de sites en procédant à une évaluation du réseau une fois qu’il est déployé pour garantir la bande passante est suffisante et que les mécanismes QoS fonctionnent correctement. Il est important de continuer à surveiller les performances du réseau, comme des utilisateurs plus réels sont mises en ligne.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Partie 2 : Skype de ExpressRoute entreprise QoS

Le service ExpressRoute de Microsoft fournit une connexion dédiée pour le nuage Azure, mais les services de communication des Office 365 en temps réel des charges de travail nécessiteront des services réseau avec une bande passante suffisante pour porter le volume de trafic et sont capables de prendre en charge Expérience de la qualité de Service (QoS) pour offrir un utilisateur de niveau professionnel. Une qualité de service capable connexion doit être configurée de bout en bout (PC, commutateurs réseau et les routeurs vers le nuage) comme n’importe quelle partie du chemin d’accès qui ne parvient pas à prendre en charge de QoS pourrait dégrader la qualité de l’appel de toute.
  
L’objectif de cette section est de vous aider à comprendre les défis lors de la prise en charge de trafic en temps réel dans un réseau IP et la configuration et la prise en charge d’un déploiement réussi de la ExpressRoute d’Office 365 en temps réel des charges de travail à l’aide de Microsoft ExpressRoute Exchange Partenaire fournisseur ou fournisseur de services réseau.
  
QoS est acceptée à partir de vos réseaux exclusivement sur les circuits de réseau ExpressRoute et est utilisée dans le réseau de Microsoft pour Skype pour le trafic de l’entreprise. Aujourd'hui, des parties de certaines connexions sortantes à partir de Microsoft ont des valeurs DSCP manquantes pour Skype pour les entreprises. Jusqu'à ce que le trafic sortant est entièrement marqué avec les valeurs DSCP, vous êtes invités à suivre les instructions pour ajouter des marques de qualité de service pour le trafic au niveau de la frontière du réseau comme décrit dans la section **Implémentation de QoS à l’aide de la liste de contrôle d’accès réseau (ACL)** de ce article.
  
### <a name="the-real-time-problem"></a>Le problème en temps réel

Fourniture de services de voix et la vidéo de qualité entreprise place les demandes particulières sur un réseau IP. Le trafic en temps réel utilise le protocole de Transport en temps réel (RTP) qui est exécutée à l’aide du protocole UDP (User Datagram). Contrairement au protocole TCP (Transmission Control) qui numérote et teste chaque message d’erreur et inclut d’autres mécanismes pour détecter et retransmettre des messages perdus ou erronés, UDP ne fournit pas de la fiabilité de ce type. Si les messages sont endommagés par des erreurs ou sont perdues en raison de débordements de tampon, ils sont perdus. UDP a été choisi pour être utilisé avec le protocole RTP parce que la nature du trafic en temps réel est que même si les messages perdus ont été renvoyées, ils seraient arrivent beaucoup trop tard pour avoir un impact positif sur le flux de message vocal.
  
Connaître l’impact des paquets vocaux perdues, concepteurs a proposé deux approches afin d’améliorer les performances de la voix et la vidéo sur IP :
  
- Rendre la voix de codage/décodage plus souple lorsque les paquets sont perdus. Pour ce faire par une ou l’autre à l’aide de correction aval des erreurs (FEC) pour corriger un pourcentage de l’a rencontré des erreurs, qui est une possibilité trouvé dans Office 365 en temps réel Transport ou par la voix de conception décodage des systèmes qui tentent de se masquer l’effet de la perte de paquets qui est une caractéristique de codecs Microsoft. 
    
- Utilisez les services de transport de qualité de mécanismes de service permet de garantir les performances du réseau en ce qui concerne le retard, perte de paquets et l’instabilité et la variation de retard entre les paquets.
    
Codage vocal résilient traite uniquement le problème de perte de paquets, il est donc important qu’un réseau utilisé pour transporter la voix en temps réel et vidéo ont des mécanismes qui réduisent le délai et gigue. Même avec un codage robuste, si trop de paquets sont perdus, la station réceptrice n’aurez pas suffisamment d’informations pour reconstruire une version reconnaissable du signal vocal. Le pourcentage de perte de paquets qui entraînerait une dégradation significative de la qualité de la voix varie en fonction de la voix de codage technique qui est utilisée. Dans tous les cas toutefois, perte de chaînes de paquets successives est très problématique.
  
Il est important de minimiser le délai car délai excessif peut avoir un impact sur le déroulement de la conversation et créer une gêne pour les haut-parleurs. Meilleures pratiques indiquent que délai de bout en bout pour la voix (ce que nous appelons délai de « bouche à oreille ») doit être maintenu en deçà de 150 millisecondes (MS). unidirectionnelle, délai pas 'rond voyage ». Bien sûr le délai augmente sur les liaisons de transmission plus semblables à ceux qui passent entre les océans, étant donnés le délai de propagation ou le temps que nécessaire pour que le signal se déplacer physiquement via le câble.
  
Lorsque le délai est supérieur à 150 millisecondes. à sens unique, elle a un effet étrange sur le haut-parleur. Dérangeant, une horloge s’éteint dans le cerveau du présentateur qui les rendre à penser que le destinataire n’a pas entendu les et ils répéter la dernière chose qu’il dit. Cela crée un conflit avec la réponse différée en provenance de l’extrémité. Si vous avez jamais parlée sur un canal de satellite vous reconnaît cet effet. Sur un canal de satellite le délai à sens unique est d’environ 250 millisecondes. qui est bien au-delà du délai autorisé.
  
 **Paramètres réseau recommandés pour la voix de niveau entreprise**
  
|**Paramètre**|**Valeur recommandée**|
|:-----|:-----|
|Notamment l’instabilité de paquet d’arrivée (moyenne)  <br/> |≤ 5 MS  <br/> |
|Notamment l’instabilité de paquet d’arrivée (maximum)  <br/> |≤ 40MS  <br/> |
|Taux de perte de paquet (moyenne)  <br/> |approche de 0 %  <br/> |
|Une façon de latence du réseau  <br/> |≤ 100ms (doit inclure des contrôles de retard par rapport à la distance géographique)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute en tant que partie d’un réseau de voix entreprise grade

ExpressRoute offre une connexion dédiée via un fournisseur de Service de réseau (NSP) ou un fournisseur de Exchange (EXP) dans une des 3 options de connexion : 
  
- Nuage Exchange Colocation
    
- Connexion Ethernet de point à point
    
- Connexion de (IPVPN) à tout
    
Cela offre des avantages de la haute disponibilité (99,9 % de disponibilité du SLA) et un routage fiable qui est sécurisé (pas de transit internet), affectés par les variations dans le trafic Internet et respecte les marques de qualité de Service pour hiérarchiser le trafic (QoS est expliquée ci-dessous) . ExpressRoute, ainsi que d’un WAN bien planifié peut vous fournir un réseau de voix entreprise grade.
  
Vous pouvez utiliser ExpressRoute pour le transit des données à partir des bureaux ou des centres de données (si topologie d’hybrides) qui sont connectés au circuit. Données hors site des utilisateurs (par exemple, à partir de bureaux à domicile ou en déplacement, etc.) ne sont pas exploiter le circuit ExpressRoute, sauf si les utilisateurs sont connectés par VPN et ne doivent pas être compris dans les estimations de la bande passante pour le circuit ExpressRoute de dimensionnement. Si vous êtes un client international, vous pouvez acheter des circuits ExpressRoute dans chaque région et permet d’informer les règles de routage afin que le trafic est dirigé vers le circuit ExpressRoute par défaut (en général le plus proche un pour chaque site), alors que les balises de communauté BGP circuits offrent la redondance en cas de panne de courant affectant un même circuit. 
  
### <a name="if-expressroute-isnt-an-option"></a>Si ExpressRoute n’est pas une option

Il se peut qu’il ne soit pas possible de connecter tous les sites à ExpressRoute, soit en raison de coûts, incapacité à respecter les conditions préalables de ExpressRoute, ou des limitations de votre NSP en cours. Si vous ne pouvez pas utiliser ExpressRoute vous sont toujours recommandées à suivre les conseils ci-dessous pour le marquage QoS au sein de votre réseau et de planifier les contrats avec vos NSP pour garantir suffisamment de bande passante et de prise en charge de la hiérarchisation du trafic basée sur la qualité de service.
  
En outre, si vous avez des bureaux dans plusieurs régions, mais que vous n’avez pas les circuits ExpressRoute dans toutes les régions doivent utiliser les balises de communauté BGP région lors de la configuration du routage du trafic vers/depuis des bureaux satellites, afin que le transit de trajet de long inutiles peut être évitée. Par exemple, considérez une société qui possède un Skype pour organisation commerciale en ligne hébergée aux États-Unis, mais avec des filiales en Europe et la société n’a qu’un seul circuit de ExpressRoute dans la Silicon Valley. La plupart de la Skype pour le trafic en ligne Business est acheminé vers un centre de données où l’organisation est hébergée (par exemple, des appels de conférence avec d’autres utilisateurs au sein de la société), utilisant le circuit ExpressRoute est préférable pour la plupart du trafic. Toutefois, si un utilisateur en Europe pour joindre une téléconférence hébergée par une autre société dont l’organisation se trouve en Europe, la destination des médias dans cet appel serait le centre de données européen où se trouve la deuxième société. Acheminement du trafic via le circuit de ExpressRoute dans la Silicon Valley serait une route moins directe que serait possible via Internet. Dans ce cas, vous souhaiterez configurer les routeurs au sein de votre réseau (par exemple, les bureaux européens) pour vérifier les balises de la Communauté lorsque les règles de fabrication de routage et de routage via Internet plutôt que d’ExpressRoute de la Silicon Valley circuit pour le trafic qui a Balises de la région Europe.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Concepts de base de la qualité de Service (QoS) / classe de Service (CoS)

Dans la période d’enquête, qualité de Service (QoS) décrit un mécanisme qui est utilisé pour fournir la priorité de gestion pour certains paquets sur d’autres. En fonction de la définition de l’Union internationale des télécommunications (UIT), QoS comprend tous les aspects de qualité d’une connexion, y compris le délai, perte, rapport signal-bruit, DIAPHONIE, echo, interruptions, réponse en fréquence, les niveaux de volume et ainsi de suite. Ce que nous faisons référence à QoS dans les réseaux de paquets est plus correctement d’appelé la classe de Service (CoS) qui met l’accent sur l’amélioration des performances de perte de paquets, l’instabilité et retard, mais nous continuons à utiliser le terme QoS tel qu’il est plus couramment utilisé.
  
Fourniture de QoS dans une adresse IP réseau appelle pour deux composants principaux :
  
- La réservation d’un montant défini de bande passante sur chaque lien pour le trafic en temps réel ; Si cette bande passante n’est pas nécessaire pour le trafic en temps réel, à tout moment, il peut être utilisé pour un autre trafic. L’idée directrice est que pas plus de 30 % de la capacité de n’importe quel lien doivent être affectées pour le trafic vocal.
    
- Marquer les paquets avec un indicateur de priorité dans l’en-tête indiquant les commutateurs et les routeurs dans le chemin d’accès de la priorité du paquet qui doit être affecté.
    
Lorsqu’un paquet est reçu sur un commutateur ou un routeur, il est déplacé à une file d’attente de sortie pour le tronçon suivant ou le saut. Il existe des files d’attente de sortie différentes pour les différents niveaux de priorité. Un commutateur ou un routeur utilise un algorithme qui dessert la file d’attente de haute priorité plus fréquemment que les files d’attente de priorité inférieures.
  
Le défi est qu’il existe différentes techniques de qualité de service qui sont mises en œuvre au niveau de la couche 2 (c'est-à-dire la couche Ethernet ou Wi-Fi) et 3 (c'est-à-dire la couche IP). Ces différentes implémentations de QoS peut-être être configurés dans chaque commutateur et du routeur dans le réseau, ainsi que l’interface entre votre réseau et du fournisseur de services réseau.
  
Il existe deux options pour comment les données à partir de la Skype différents pour les applications commerciales peuvent être mappées aux classes de service appropriés :
  
- Marquage de point de terminaison du trafic à l’aide de la Differentiated Services contrôle Point (DSCP) 
    
- Liste de contrôle d’accès (ACL) du réseau-en fonction
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Point de terminaison du trafic marquage dissociés Point de contrôle des Services (DSCP)

Services différenciés (DiffServ) correspond à un mécanisme de « grains grossiers » pour la classification et de gérer le trafic réseau et de fourniture de QoS dans les réseaux IP. Les routeurs et autres périphériques qui implémentent les fonctions de la couche 3 utilisent le Point de contrôle DiffServ (DSCP) pour définir la priorité du paquet. Qualité de service est implémentée par l’insertion d’une valeur DSCP de 6 bits dans le champ de la Differentiated Services (anciennement le champ « Type de Service ») dans l’en-tête IP ; 6 bits permet de 64 niveaux de priorité différents. Les niveaux de priorité sont généralement définies comme illustré ici.
  
 **Paramètres de DSCP recommandés**
  
|**Classe de trafic**|**Traitement (marquage DSCP)**|**Skype pour les charges de travail métier**|
|:-----|:-----|:-----|
|**Voix** <br/> |EF (46)  <br/> |Skype pour la voix entreprise et Lync  <br/> |
|**Interactive** <br/> |AF41 (34)  <br/> |Vidéo  <br/> |
||AF21 (18)  <br/> |Partage d'application  <br/> |
|**Par défaut** <br/> |AF11 (10)  <br/> |Transfert de fichiers  <br/> |
||CS0 (0)  <br/> |Autre chose  <br/> |
   
 **En-tête d’IP Version 4**
  
![En-tête IPv4](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS de couche 2 : IEEE 802.1 p/Wi-Fi multimédia (IEEE 802.11e)

DSCP est le mécanisme standard de l’implémentation de QoS au niveau de la couche 3, il existe différents mécanismes de qualité de service de couche 2 pour (par exemple, Ethernet) de réseau câblé et sans fil (c'est-à-dire les réseaux Wi-Fi). Le mécanisme de QoS pour les réseaux câblés est défini dans la norme IEEE 802 .1p ; le mécanisme de qualité de service de réseau local sans fil est défini dans IEEE 802.11e, ce qui identifie le Wi-Fi Alliance comme « Certifiés Wi-Fi multimédia » (WMM certifié).
  
L’IEEE 802 .1p utilise un Point de Code de priorité de 3 bits (PCP) pour identifier la priorité du message ; le PCP fait partie d’un champ de 32 bits dans l’en-tête Ethernet qui contient également l’identificateur de réseau local virtuel. Vous trouverez ci-dessous les définitions pour les valeurs de la PCP.
  
 **Valeurs de PCP IEEE 802 .1p**
  
|**Valeur de PCP**|**Priorité**|**Acronyme**|**Types de trafic**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |CONTEXTE DE NOMMAGE  <br/> |Contrôle de réseau  <br/> |
|6  <br/> |6  <br/> |INTERSOCIÉTÉS (IC)  <br/> |Contrôle de réseau d’interconnexion  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Audio  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Vidéo  <br/> |
|3  <br/> |3  <br/> |AUTORITÉ DE CERTIFICATION  <br/> |Applications critiques  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Excellent travail  <br/> |
|0  <br/> |1  <br/> |ÊTRE  <br/> |Effort optimal  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Arrière-plan  <br/> |
   
Où IEEE 802 .1p est implémenté de la même façon que DSCP du trafic triés dans les files d’attente de priorité différent pour chaque niveau de priorité, mais la nature des fichiers multimédias partagés des appels de réseaux locaux sans fil à une approche différente. Alors que le point d’accès et le client mettre à jour les files d’attente de sortie distincts pour les différents niveaux de priorité, il existe également les différences dans comment les images sont envoyées sur le canal radio.
  
Dans un réseau Wi-Fi, tous les clients associés à un point d’accès partagent un canal unique et semi-duplex (c'est-à-dire qu’un seul client station ou un point d’accès peut envoyer à la fois). Pour réduire le risque de collisions sur le canal radio, avant l’envoi d’une trame que la station attend que le canal d’inactivité pendant une période définie, appelée « Espacement intertrame », si le canal est occupé lors de la passe d’une station à envoyer, elle rétrograde un péri de temps aléatoire Od. Une fois que la trame est envoyée, si l’expéditeur ne reçoit pas un message d’accusé de réception du destinataire, il suppose une collision ou autre erreur s’est produite et il effectue un retour un intervalle aléatoire avant de tenter d’accéder le canal radio qu’à la renvoyer. L’intervalle de recul est aléatoire pour réduire la probabilité que les deux stations de mêmes entreront en collision à nouveau.
  
Pour classer par priorité les accès à la radio channel, IEEE 802.11e / WMM définit différents intervalles d’attente avant transmission appelées « Arbitrée entre les trames espacements » (AFIS) et des différentes plages de recul les différentes classes de trafic ; quatre niveaux de priorité appelées « Accès aux catégories » sont définies.
  
La priorité est donnée en assignant des valeurs AFIS plus courts pour les cadres de priorité plus élevés. Par conséquent, si un poste est en attente pour envoyer une trame vocale et un autre est en attente pour envoyer une trame de données, le cadre de la voix est toujours envoyé en premier. Techniquement, vocaux et des images vidéo sont affectés à la même valeur AFIS, mais la plage des intervalles de recul pour images vidéo est plus élevée. Ainsi, lors d’une voix et l’image vidéo respecte à la première tentative, le cadre de la voix est toujours retransmis plus tôt. La corrélation entre IEEE 802 .1p et IEEE 802.11e est illustrée ci-dessous :
  
 **IEEE 802.11e / Wi-Fi multimédia (WMM) à P 802.1 mise en correspondance**
  
|**Catégories d’accès WMM**|**Description de WMM**|**Valeur de PCP 802 .1p**|**Désignation de 802.1P**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Audio  <br/> |7 (111)  <br/> |CONTEXTE DE NOMMAGE  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Vidéo  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Les données d’Effort  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |ÊTRE  <br/> |
|4 (AC_BK)  <br/> |Données d’arrière-plan  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
L’association recommandée de couche 3 dans les priorités de couche 2 est illustrée ici :
  
 **Recommandé de couche 3 associations de priorité de couche 2**
  
||**Marques de couche 3**|**Couche 2 (valeur de PCP)**|**Wi-Fi (catégorie d’accès)**|
|:-----|:-----|:-----|:-----|
|Contrôle de réseau  <br/> |Par un comportement par pas (PHB) - sélecteur de classe (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valeur DSCP -48  <br/> |
|Audio  <br/> |Par un comportement (par pas PHB)-Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valeur DSCP - 46  <br/> |
|Conférence vidéo  <br/> |Par un comportement par pas (PHB) - Assured Forwarding (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valeur DSCP - 34  <br/> |
|Appel de signalisation  <br/> |Par un comportement par pas (PHB) - sélecteur de classe (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valeur DSCP - 24  <br/> |
|Données de latence faible  <br/> |Par un comportement (par pas PHB)-Assured Forwarding (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valeur DSCP -18  <br/> |
|Haut débit de données  <br/> |Par un comportement par pas (PHB) - Assured Forwarding (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valeur DSCP - 10  <br/> |
|Effort optimal  <br/> |Par un comportement par pas (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valeur DSCP - 0  <br/> |
   
Il est important de noter qu’il existe une incohérence dans le codage de priorité IEEE 802 .1p et WMM. Le 802 .1p que celui du PCP de valeur pour la voix est 5, toutefois, dans le mappage standard équivalence WMM, PCP 5 est traduite Access 2 de catégorie, la catégorie d’accès WMM pour la vidéo (AC_VI). Si possible remplacer ce mappage afin que PCP 5 se traduit par l’accès aux catégories 1, ou si vous éviter tout simplement à l’aide de voix et la vidéo sur le même réseau Wi-Fi jusqu'à ce que le Wi-Fi Alliance résout ce problème. Pour plus d’informations sur le Wi-Fi, consultez [Les articles du catalogue Wi-Fi]( https://go.microsoft.com/fwlink/?LinkId=690322).
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>L’implémentation de QoS à l’aide de la liste de contrôle d’accès réseau (ACL)

La méthode de substitution de l’implémentation de QoS dans une configuration de ExpressRoute est d’utiliser la liste de contrôle d’accès réseau (ACL). Dans cette approche, au lieu des points finaux Insérez le marquage DSCP approprié dans l’en-tête de chaque paquet, le marquage peut être effectué par un routeur en amont, basé sur le port UDP source. Tous les commutateurs et routeurs doivent toujours être configurés pour prendre en charge de QoS pour conserver les paramètres de DSCP. Plus important encore, le routeur connecté au réseau de la téléphonie doit mettre à jour le DSCP de l’en-tête de chaque paquet, comme ce paramètre DSCP est essentiellement vos instructions au fournisseur de services réseau pour le paquet doit être traité.
  
Les plages de port recommandé pour chaque Skype pour application métier sont répertoriés dans la Section 2.6.1.1 du guide de [Planification de réseau, de surveillance et le dépannage avec Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286) . Il est important que cette être coordonnés avec l’approche globale de l’organisation à QoS et soyez à l’affût pour différentes stratégies de qualité de service et les incompatibilités de commentaire de paquet potentielles.
  
Alors qu’il est la principale raison que les services réseau MPLS et de qualité de service sont utilisés pour garantir une utilisation efficace de la voix en temps réel et la vidéo, ces mêmes capacités peuvent également être appliquées à des applications de données. Au lieu de traiter également à toutes les applications, les réseaux MPLS permettent aux organisations de donner la priorité à certaines applications de données sur les autres. Avec MPLS, des applications en temps réel telles que les transactions de carte de crédit ou de partage d’écran peuvent être prioritaires sur réduire le trafic de temps sensibles comme la messagerie électronique.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Comprendre les types d’IP réseau Services base IP et MPLS

Le transfert des paquets IP d’origine fonctionne sur le principe du « meilleur effort ». Cela signifiait que les routeurs de transmettre les paquets IP devrait faire de leur mieux pour les remettre à leurs destinataires, mais il y a absolument aucune garantie concernant lorsqu’ou si elles seraient arrivent à destination. Qui est la base services Internet, y compris votre connexion Internet domestique, travail dès aujourd'hui. L’idée était que si la fiabilité était requise pour une application particulière, elle doit être fournie à un niveau plus élevé dans la pile de protocole. Le mécanisme de remise fiable est le protocole TCP (Transmission Control). Le protocole UDP (User Datagram), qui est utilisé pour la voix en temps réel et la vidéo, est peu fiable (c'est-à-dire « optimal ») livraison mécanisme. 
  
Commutation d’étiquette multiprotocole (MPLS) a été développé en tant que moyen pour les fournisseurs de services réseau offre une IP service avec des performances garanties pour retard, instabilité et de perte de paquets. Pour fournir ces garanties de performances, MPLS prend certaines d’imprévisibilité sur IP traditionnel. Tout d’abord, plutôt que chaque paquet trouver son routeur à routeur vers sa destination (dont le résultat peut être que chaque paquet prend un itinéraire différent à partir de la source vers la destination), MPLS achemine tous les paquets sur une connexion « circuit virtuel » avec un itinéraire fixe appelée un chemin LSP (Label Switched). Si un des liens de ce chemin d’accès échoue, tous les prestataires de services linguistiques en utilisant ce lien sont rapidement redirigés.
  
Lorsqu’un paquet est envoyé au réseau MPLS routeur de bordure du fournisseur de services réseau ajoute un en-tête supplémentaire pour le paquet qui contient une étiquette qui sert à le transférer sur le LSP approprié. L’étiquette est supprimée par le routeur de bord à l’autre extrémité du réseau MPLS.
  
En regard de simplifier le processus de transfert, l’autre avantage que MPLS fournit est que le système de gestion de réseau saura quelles connexions sont en cours sur tous les liens dans le réseau. En contrôlant la façon dont le trafic est routé via le réseau, l’opérateur peut garantir la QoS fournit chaque chemin d’accès. Donc les meilleures performances d’effort de IP traditionnel ou de base, à la différence des opérateurs MPLS peuvent fournir un service IP avec des performances prévisibles. Que LSP rend également MPLS par nature plus sécurisé que les services Internet classiques. Ainsi, avec le service de base IP nous pouvons espérer que que le réseau effectue bien suffisant pour fournir des voix de bonne qualité et d’utiliser des techniques comme la FEC et plus robuste vocodage pour améliorer les chances, mais à l’aide de MPLS, nous pouvons être sûrs de celui-ci.
  
Les fournisseurs MPLS offrent plusieurs classe malheureusement utilise des termes différents pour identifier les dégradés de service. Vous devez travailler en étroite collaboration avec votre fournisseur pour s’assurer qu’ils comprennent les sorties [Lync 2010 et Calculatrice de bande passante 2013](https://go.microsoft.com/fwlink/?LinkID=690282) et les options recommandées pour les applications Office 365 en temps réel des charges de travail différentes.
  
## <a name="conclusion"></a>Conclusion

Skype pour entreprise améliore la façon dont les communications de l’entreprise sont effectuées. Au lieu d’avoir un téléphone connecté à un PBX, un système de vidéoconférence autonome, une plate-forme distincte pour le courrier électronique, un service externe de conférence audio et d’un véhicule pour la messagerie instantanée et de présence, Skype pour entreprise peut réunir toutes ces fonctionnalités dans une interface utilisateur unique.
  
Fournir des services d’entreprise qualité en temps réel services vocaux et vidéo nécessite une infrastructure de réseau de bout en bout qui est capable de fournir QoS. Qui inclut à la fois les services WAN et LAN. Microsoft fournit des outils tels que [Calculatrice de la bande passante 2013 et de Lync 2010](https://go.microsoft.com/fwlink/?LinkID=690282) pour estimer la capacité du réseau que vous aurez besoin pour les différents services. Il existe également des partenaires du programme IT Pro Tools [Skype pour Solutions d’entreprise : IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307) qui offrent des outils au préalable évaluer l’infrastructure de réseau et la prise en charge de la surveillance, de reporting et de dépannage. Sans une infrastructure réseau correctement dimensionnés et configurés, vous risquez d’avoir un Skype ExpressRoute de déploiement d’entreprise qui ne respecte pas les attentes de l’utilisateur de qualité et de cohérence.
  
Outils d’entreprise doivent effectuer de manière fiable, cohérente et fournir une expérience utilisateur qui encourage l’adoption par les utilisateurs. À partir d’un point de vue réseau qui signifie ayant une infrastructure de réseau, tel que zone locaux et étendu, fixe et mobile, qui permettre que cela se produise. Planification, de conception, d’implémentation et de maintenance cette infrastructure n’est pas toujours une fonction (FEAT) simple. Le matériel, les outils et les services de réseau pour ce faire sont disponibles dès aujourd'hui, mais il est de la responsabilité des professionnels de l’informatique pour vérifier qu’ils sont conçus, mis en oeuvre et maintenues d’une manière qui garantit que les utilisateurs obtiennent un ensemble de services de collaboration et de communication qui permettre à ces derniers de travailler efficacement et de manière efficace et que l’organisation peut tirer pleinement parti de ce que cette technologie peut offrir. 
  
## <a name="related-topics"></a>Rubriques connexes

[Documentation de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

