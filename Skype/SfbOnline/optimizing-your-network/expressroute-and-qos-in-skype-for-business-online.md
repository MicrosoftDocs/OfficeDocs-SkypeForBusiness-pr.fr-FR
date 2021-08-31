---
title: ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 'Learn about using Azure ExpressRoute to have a network with bandwidth requirements and Quality of Service capability for a business class user experience. '
ms.openlocfilehash: 32d9a3f6be35077f274f0a8ab9facc462a3fe6b4
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729783"
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute et qualité de service (QoS) dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Connecter à Microsoft 365 ou Office 365 via une connexion réseau dédiée à l’aide d’Azure ExpressRoute pour Microsoft 365 ou Office 365 et Skype Entreprise Online. Votre connexion dédiée pour vos applications Skype Entreprise offre des performances fiables et prévisibles et protège vos données confidentielles contre l'Internet public. Vous pouvez désormais acheter une meilleure connexion réseau vers Microsoft 365 ou Office 365 et Skype Entreprise Online qui offre une fiabilité et une grande prévisibilité, ainsi qu’un SLA de temps de disponibilité.
  
> [!NOTE]
> Une nouvelle version de l’outil de calcul de bande passante est disponible : [Skype Entreprise, outil de calcul de bande passante.](https://go.microsoft.com/fwlink/?LinkId=715766) Toutefois, les instructions de ce document utilisent l’outil de calcul de bande passante Lync 2010 et Lync 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype Entreprise Online et ExpressRoute

En travaillant avec un partenaire ExpressRoute de Microsoft, vous pouvez connecter plusieurs applications Microsoft 365 et Office 365, notamment Skype Entreprise Online dans le cloud sur une connexion dédiée. Toutefois, les fonctionnalités de communication voix et vidéo en temps réel pour Skype Entreprise nécessitent des services réseau qui sont spécifiquement configurés pour prendre en charge ces Microsoft 365 ou Office 365 charges de travail en temps réel. Cela comprend un réseau disposant de suffisamment de bande passante pour exécuter le volume de trafic nécessaire et prendre en charge la qualité de service (QoS) afin d'offrir à vos utilisateurs une expérience de qualité professionnelle.
  
Ce document est conçu pour vous aider, en tant qu'administrateurs et concepteurs de réseaux, à comprendre les défis spécifiques nécessaires à la prise en charge de communications en temps réel, ainsi que les outils fournis par Microsoft pour la conception d'un réseau prenant en charge ces exigences, et vous guider lors de la procédure de conception à l'aide d'une étude de cas. 
  
La première partie de ce document vous guidera dans une étude de cas afin de vous aider à concevoir un réseau à l'aide de l'[outil de calcul de bande passante Lync 2010 et Lync 2013](https://go.microsoft.com/fwlink/?LinkId=690282) pour estimer la configuration réseau requise pour un déploiement Skype Entreprise ExpressRoute multisite de grande ampleur. La seconde partie de ce document aborde les concepts fondamentaux de la qualité de service (QoS), étudie en détail les aspects techniques de la prise en charge des communications Skype Entreprise en temps réel, et les types de services réseau requis.
  
Toutes les informations figurant ici fournissent une approche technique détaillée de QoS et d'ExpressRoute, permettent d'appréhender les défis spécifiques d'ExpressRoute auxquels vous êtes confronté et offrent une bonne connaissance des outils et techniques qui vous permettront de déployer avec succès ExpressRoute sur votre réseau Skype Entreprise. 
  
## <a name="getting-started"></a>Prise en main

Lorsque vous vous préparez pour ExpressRoute pour Skype Entreprise, il est judicieux d'étudier les différents modèles de connexion ExpressRoute et les différents choix de partenaires et de lieux et de se documenter sur l'achat et la fourniture d'ExpressRoute au sein de votre entreprise. Voici quelques ressources pour bien commencer : 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Tarification ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentation ExpressRoute](/azure/expressroute/)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Partie 1 : Étude de cas - ExpressRoute pour Dewey Law, LLC.

Cette étude de cas concernant la société Dewey Law, LLC vous explique comment mettre en place un réseau, commander des services d'accès réseau et déterminer les besoins en bande passante pour la prise en charge d'ExpressRoute pour Skype Entreprise Online.
  
 **Contexte** Dewy Law LLC est un grand cabinet d'avocats américain comptant un total de 790 avocats et de 5 580 employés, répartis sur 78 sites. L'entreprise est sise à New York, avec trois implantations régionales à Chicago, San Francisco et Dallas, ainsi que 24 grandes succursales et 50 succursales plus petites disséminées dans tout le pays. L'entreprise gère des affaires complexes et volumineuses, dont la charge est répartie sur plusieurs sites. Cette structure implique donc un trafic réseau considérable entre les bureaux.
  
Dewy Law LLC est une entreprise relativement jeune, dont les avocats et les autres membres du personnel sont très à l'aise avec la technologie qu'ils utilisent au quotidien pour la plupart de leurs tâches professionnelles. 
  
 **Répartition des utilisateurs par lieux et postes**
  
|Personnel |**Siège social (New York)**|**Bureaux régionaux (3)**|**Grandes succursales (24)**|**Petites succursales (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Direction  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partenaires  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Associés  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Assistants juridiques  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Cadres administratifs  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|Informatique et administration générale  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Total par site  <br/> |1 070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Total par catégorie de site  <br/> |1 070  <br/> |1 035  <br/> |1 680  <br/> |1 800  <br/> |
   
### <a name="setting-up-the-network"></a>Configuration du réseau

Pour fournir des services en temps réel d'une qualité élevée et constante à Dewey Law LLC, certaines conditions de base doivent être remplies :
  
- L'entreprise souhaite fournir des services vocaux pendant les pannes électriques, aussi ses commutateurs et routeurs de répartition réseau doivent-ils distribuer les données par le biais de connexions PoE (Power over Ethernet) selon la norme IEEE 802.3af ou 802.3at.
    
- Les commutateurs et les routeurs réseau doivent également utiliser des sources d'alimentation sans interruption (UPS) afin de continuer à fonctionner en cas de panne de courant.
    
    Ils ont une Wi-Fi connexions réseau à leurs bureaux locaux. Nous vous recommandons donc vivement d’utiliser un partenaire d’infrastructure Skype Entreprise Wi-Fi certifié à partir de [Skype Entreprise Solutions.](https://go.microsoft.com/fwlink/?LinkId=690281)
    
    > [!TIP]
    >  Des points d'accès sans fil 802.11n et 802.11ac sont recommandés.
  
- Plus important encore, tous les réseaux locaux de tous les sites doivent être configurés pour offrir la qualité de service (QoS). Cela comprend les PC, les ordinateurs portables et les dispositifs réseau, comme les commutateurs et les routeurs.
    
Maintenant que vous avez abordé les concepts de base, pour fournir des services vocaux de qualité d'entreprise à Dewey Law LLC, nous recommandons d'utiliser le service IP MPLS (Multi-Protocol Label Switching) d'un partenaire de service réseau qui se connectera au service Azure ExpressRoute. MPLS fournit un service IP avec des garanties de performance en termes de retard, de gigue et de perte de paquets. Toutefois, si MPLS n'est pas disponible, il est possible d'utiliser la carte Ethernet connectée à l'un de nos partenaires d'échange de données ExpressRoute.
  
Les fournisseurs MPLS offrent plusieurs niveaux de service, mais chacun d'eux utilisent des termes différents pour les identifier. Vous devez travailler en étroite collaboration avec votre fournisseur pour s’assurer qu’il comprend les données que vous avez entrées dans l’outil de calcul de bande passante [Lync 2010 et Lync 2013,](https://go.microsoft.com/fwlink/?LinkID=690282) ainsi que les options disponibles, et qui sont recommandées pour les différentes applications de charge de travail Microsoft 365 et Office 365 en temps réel.
  
Il existe deux options pour l'association des données d'applications Skype Entreprise aux classes MPLS de service appropriées :
  
- Marquage des points de terminaison du trafic à l'aide de DSCP (DiffServ Control Point)
    
- Liste de contrôle d'accès (ACL) réseau
    
Pour mettre en œuvre le marquage des points de terminaison, vous devez configurer toutes les machines Windows de Dewey Law LLC connectées à un domaine. Pour marquer chaque paquet avec le marquage DSCP (DiffServ Control Point), puis mettre en œuvre la QoS sur tous les commutateurs et les routeurs réseau de tous les sites afin de s'assurer que les marquages QoS sont conservés et ne sont pas supprimés. Les marqueurs DSCP sur les paquets réseau indiquent au fournisseur de services leur ordre de priorité. **La section QoS de la deuxième partie contient des informations supplémentaires.**
  
Pour l'affectation basée sur une liste de contrôle d'accès réseau, les marqueurs de priorité DSCP sont mis en œuvre sur le routeur en amont et basés sur le port source UDP. Les plages de ports recommandées pour chaque application sont répertoriées à la section 2.6.1.1 de la planification, de la surveillance et de la résolution des problèmes réseau avec [Lync Server.](https://go.microsoft.com/fwlink/?LinkId=690286) Il est important de coordonner cela avec la conception et la mise en œuvre globales de QoS chez Dewey Law LLC et de connaître les différentes stratégies de QoS et les différences de marquage de paquets potentielles.
  
Chaque fournisseur de services réseau ExpressRoute possédera une classe de service (QoS) adaptée à la voix et à la vidéo en temps réel. Cette classe de service COS est appelée « acheminement accéléré » (EF) pour la voix et « acheminement assuré » (AF) pour la vidéo. Vous devez être très prudent lors du dimensionnement de la quantité de bande passante que vous achetez pour le trafic voix EF. La classe de service voix est inflexible si vous envoyez une quantité de trafic voix supérieure à ce que permet la classe de service.
  
> [!TIP]
>  Tout le trafic envoyé en excès sur la classe de service voix du fournisseur de services est éliminé immédiatement, ce qui a un effet direct sur la qualité de la voix.
  
En examinant la conception globale pour Dewey Law LLC, il est extrêmement important de déterminer avec précision la quantité de bande passante réseau dont ils ont besoin pour soutenir le trafic voix sur leur réseau et ils doivent marquer chaque paquet voix (et seulement les paquets voix) avec le réglage DSCP pour la voix (c'est-à-dire DSCP EF 46).
  
Pour implémenter la QoS sur leur réseau d’entreprise, les points de terminaison ou les routeurs doivent marquer chaque paquet avec l’indicateur de priorité Layer 3 approprié (c’est-à-dire DSCP). Tout le long du chemin réseau, l'option QoS doit être activée sur chaque commutateur et chaque routeur. Il suffit que l'option QoS ne soit pas activée sur un commutateur ou sur un routeur réseau pour que les marqueurs QoS des paquets voix ou vidéo qui transitent par cet appareil soient supprimés au passage. Cela désactive QoS sur tous les commutateurs et routeurs en aval, ce qui réduit le rôle d'ExpressRoute sur le réseau.
  
De ce fait, l'association des priorités QoS Layer 3 et Layer 2 doit également être définie à chaque point. Les mécanismes de priorité Layer 2 sont définis dans les normes IEEE 802.1p pour les réseaux filaires et IEEE 802.11e/WMM pour les réseaux Wi-Fi. Mieux encore, le routeur réseau faisant face au réseau MPLS du fournisseur de services réseau doit maintenir les paramètres DSCP sur tous les paquets sortants afin de garantir la classe de service MPLS appropriée. 
  
> [!TIP]
>  Pour plus d’informations sur la mise en place de la qualité de qualité de vie, reportez-vous à la section 2.6 Planification, surveillance et dépannage réseau avec [Lync Server.]( https://go.microsoft.com/fwlink/?LinkId=760669) Pour plus d'informations sur les exigences de planification du réseau, vous pouvez également vous reporter à la rubrique [Planification de la configuration réseau requise pour Skype Entreprise 2015](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md).
  
### <a name="ordering-network-access-services"></a>Commande de services d'accès réseau

Après la mise en place des prérequis et des mécanismes réseau QoS pour la prise en charge d'ExpressRoute, l'étape suivante consiste à passer commande des services d'accès réseau ExpressRoute. Lors de la commande de services d'accès ExpressRoute pour Dewey Law LLC à partir du partenaire fournisseur de services réseau Microsoft, vous devrez indiquer deux éléments :
  
- La quantité totale de bande passante requise pour connecter chaque site à ExpressRoute et Microsoft 365 ou Office 365.
    
- La bande passante totale requise pour chaque classe de service nécessaire à la prise en charge des applications Skype Entreprise utilisées par Dewey Law LLC. La bande passante de classe de service nécessaire dépend du volume de trafic attendu pour chaque application Skype Entreprise, comme la voix, la vidéo, la messagerie instantanée, la présence et le partage d'écran.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Détermination de la bande passante nécessaire pour les applications Skype Entreprise

Dans l'étude de cas Dewey Law LLC, une fois que vous avez déterminé la bande passante totale nécessaire, vous devez savoir comment elle doit être partagée entre les différentes classes de service. Vous devez, par exemple, définir la quantité de bande passante pour chaque application Skype Entreprise.
  
Pour définir ces exigences sur chacun des sites Dewey Law LLC, vous allez utiliser l'[outil de calcul de bande passante Lync 2010 et Lync 2013](https://go.microsoft.com/fwlink/?LinkID=690282). Ce calculateur est un outil basé sur Excel, qui vous permet de spécifier l'utilisation prévue des différentes applications Skype Entreprise, dont la voix, la vidéo, la conférence et le partage d'écran. Le calculateur va générer automatiquement une estimation des besoins en bande passante et en CoS pour chaque site sur leur réseau. Lorsque vous téléchargez l'outil de calcul de la bande passante Lync 2010 et Lync 2013, le guide d'utilisation, qui est également téléchargé, vous donnera des détails sur son utilisation. 
  
Pour plus de facilité, les différentes cellules de la feuille de calcul sont désignées par des couleurs :
  
- **Vert** Il s'agit des zones de saisie des données générales.
    
- **Jaune** Il s'agit des zones de saisie des données avancées. Vous pouvez modifier ces éléments, mais vous devez le faire avec précaution.
    
- **Rouge** Les valeurs de ces zones en lecture seule ne sont pas modifiables, car elles sont verrouillées.
    
- **Gris** Il s'agit de zones en affichage seul. Elles comportent les résultats ou les données issues des zones de saisie générales.
    
Chez Dewey Law LLC, la procédure de conception commence par la répartition des utilisateurs dans différents personnages. Pour chaque personnage que vous définissez, vous pouvez indiquer l'utilisation attendue des différentes applications Skype Entreprise (« Aucun », « Bas », « Moyen », « Haut » ou l'un des trois paramètres « Personnalisé » définis). Ces sélections figurent dans la feuille de calcul « Persona » (Personnage). L'utilisation spécifique est indiquée pour chaque option (« Bas », « Moyen » ou « Haut »), mais il est possible de modifier les valeurs par défaut. En identifiant le nombre d'utilisateurs pour chaque rôle sur chaque site, l'outil de calcul permet de calculer la bande passante totale nécessaire pour chaque emplacement.
  
Vous pouvez également spécifier les codecs audio et vidéo utilisés, indiquer si la correction des erreurs de transfert est utilisée et si d'autres paramètres système affecteront les exigences de bande passante. Vous pouvez utiliser les paramètres par défaut de l'outil de calcul de bande passante Lync 2010 et Lync 2013 ou sélectionner d'autres codecs et paramètres système. Pour la conception de site Dewey Law LLC, il est possible d'utiliser les paramètres par défaut. Toutefois, un menu déroulant comportant toutes les options disponibles permet de modifier les paramètres par défaut. La feuille de calcul « Codecs » répertorie la bande passante utilisée pour chaque option. Lorsque vous modifiez un paramètre, la modification du mélange de bande passante et de classe de service (CoS) est mise à jour sur chaque site. Cette fonctionnalité vous permet de tester les différentes configurations potentielles et de constater l'impact des modifications sur la bande passante nécessaire.
  
Pour Dewey Law LLC, nous avons défini trois rôles : « Cadre/Partenaire », « Associé/Assistant juridique » et « Administrateurs informatiques ». Le tableau ci-dessous montre comment nous avons défini les profils d'utilisation pour les différentes applications Skype Entreprise de chaque personnage.
  
 **Personnages et profils d'utilisation (colonnes A à P de la feuille de travail « Persona »)**
  
|**Personnage**|**Messagerie instantanée/Présence**|**Sessions P2P audio**|**Sessions P2P vidéo**|**Conférences audio**|**Conférences vidéo**|**Partage de Bureau**|**Audioconférence**|**Lync 2010 RTV_Type**|**Utilisateurs distants**|**Lync 2013 Contenu audio stéréo**|**Lync 2013 Qualité vidéo**|**Lync 2013 Fenêtre Comportement des utilisateurs pour les sessions P2P vidéo**|**Lync 2013 Utilisation des vues multiples**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Cadre/ Partenaire  <br/> |Haut  <br/> |Moyen  <br/> |Bas  <br/> |Moyen  <br/> |Moyen  <br/> |Aucun  <br/> |Moyen  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Optimal  <br/> |Classique  <br/> |Classique  <br/> |
|Associé/ Assistant juridique  <br/> |Haut  <br/> |Moyen  <br/> |Bas  <br/> |Moyen  <br/> |Haut  <br/> |Haut  <br/> |Moyen  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Moyen  <br/> |Classique  <br/> |Classique  <br/> |
|Administrateurs informatiques  <br/> |Haut  <br/> |Moyen  <br/> |Aucun  <br/> |Bas  <br/> |Aucun  <br/> |Aucun  <br/> |Moyen  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Moyen  <br/> |Classique  <br/> |Classique  <br/> |
   
Vous devrez saisir les informations dans le tableau **Répartition des utilisateurs par emplacements et postes** ci-dessus dans la feuille de calcul « Sites » de l'outil de calcul de bande passante Lync 2010 et Lync 2013. Comme le nombre d'utilisateurs est identique dans les bureaux régionaux, les utilisateurs sont affectés au même site, auquel trois instances sont associées. La même approche s'applique aux grandes et aux petites succursales comptant respectivement 24 et 50 utilisateurs par site.
  
Après avoir spécifié les paramètres pour chaque rôle, vous devez entrer le nombre d'utilisateurs ayant ce rôle sur chaque site dans la feuille de calcul « Sites ». Le nombre total des utilisateurs de tous les sites est mis à jour automatiquement. Étant donné qu’aucun utilisateur n’est à l’Microsoft 365 ou au Office 365, tous doivent être entrés dans les lignes « Branches » de la feuille de calcul. L'outil de calcul de bande passante Lync 2010 et Lync 2013 remplit ensuite les colonnes « Best Effort Class », « Data Traffic Class » et « Real-time traffic class » de la table « WAN BW per QoS traffic class ». Le tableau ci-dessous comporte ces données.
  
> [!TIP]
>  La feuille de calcul complète comprend également le nombre maximal de sessions simultanées pour chaque application, mais nous avons supprimé ces colonnes pour gagner de la place.
  
 **Rôles par site - (Colonnes A, D, I et AI à AX de la feuille de calcul « Sites »)**
  
|**Nom du site**|**Nombre total d'utilisateurs sur le site**|**Nombre total de sites comme celui-ci**|**Profil utilisateur 1**|**Profil 1 de l'utilisateur**|**Profil utilisateur 2**|**Profil 2 de l'utilisateur**|**Profil utilisateur 3**|**Profil 3 de l'utilisateur**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Siège social  <br/> |1070  <br/> |1  <br/> |Cadre/Partenaire  <br/> |170  <br/> |Associé/Assistant juridique  <br/> |700  <br/> |Administrateurs informatiques  <br/> |200  <br/> |
|Bureaux régionaux  <br/> |345  <br/> |3  <br/> |Cadre/Partenaire  <br/> |60  <br/> |Associé/Assistant juridique  <br/> |225  <br/> |Administrateur informatique  <br/> |60  <br/> |
|Grandes succursales  <br/> |70  <br/> |24  <br/> |Cadre/Partenaire  <br/> |11  <br/> |Associé/Assistant juridique  <br/> |50  <br/> |Administrateur informatique  <br/> |9  <br/> |
|Petites succursales  <br/> |36  <br/> |50  <br/> |Cadre/Partenaire  <br/> |6  <br/> |Associé/Assistant juridique  <br/> |25  <br/> |Administrateur informatique  <br/> |1  <br/> |
   
 **Bande passante nécessaire par application et par site en kbits/s (Colonnes A et BQ à LF de la feuille de calcul « Sites »)**
  
|**Site**|**Bande passante pour les pics d'activité SIP (Session Initiation Protocol)/messagerie instantanée**|**Bande passante audio pour les pics d'activité P2P intersite**|**Bande passante vidéo pour les pics d'activité P2P intersite**|**Bande passante pour les pics d’utilisation de l’audioconférence**|**Bande passante pour les pics d’utilisation des conférences vidéo**|**Bande passante pour les pics d'activité de partage WAN**|**Bande passante pour les pics d'activité de réseau WAN pour les appels RTC**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Siège social  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Bureaux régionaux  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Grandes succursales  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |
|Petites succursales  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |
   
Dans la feuille de calcul, les colonnes les plus importantes sont probablement celles qui décrivent la bande passante du réseau WAN par catégorie de qualité de service. Cela est illustré dans le tableau ci-dessous. Ces données récapitulent les informations que vous devrez indiquer au prestataire de services réseau pour demander la connexion d'accès à chacun de vos sites. Lorsque vous calculez la bande passante totale, pensez à multiplier la bande passante pour chaque type de sites de succursale par le nombre de sites du même type. Pour vous connecter avec votre partenaire de services réseau ExpressRoute, vous pouvez consulter [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
Il est très important de ne pas dépasser la bande passante dans la classe de service voix ou EF (Acheminement accéléré). Un ensemble aléatoire de paquets sera donc ignoré donc au lieu de réduire la qualité d'un appel ou d'un groupe d'appels, tous les appels en cours peuvent être concernés. Il est également important que seule la voix soit marquée avec DSCP pour EF (par exemple, DSCP = 46), autrement la file d'attente risquerait de déborder en cas d'ajout de trafic autre que du trafic vocal.
  
> [!TIP]
>  Là encore, même si la classe de service EF offre la meilleure garantie de performances, si vous dépassez la bande passante définie, les paquets supplémentaires seront annulés immédiatement.
  
 **Bande passante agrégée par site par classe de trafic QoS - (colonnes A et ML MR de la feuille de calcul « Sites ) »**
  
|**Nom du site**|**Classe Meilleur effort (DSCP 0)**|**Classe Trafic de données (DSCP personnalisé)**|**Classe Trafic en temps réel (DSCP 34, AF41)**|**Classe Trafic prioritaire (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Siège social  <br/> |0.00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Bureaux régionaux  <br/> |0.00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Grandes succursales  <br/> |0.00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Petites succursales  <br/> |0.00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Mise en place du plan d'action

Nous pouvons calculer la bande passante totale qui traversera le réseau WAN et la quantité de bande passante qui traversera ExpressRoute à l'aide des estimations de bande passante figurant dans le tableau **Par application par site** ci-dessus. La partie du trafic qui traverse ExpressRoute exclut la bande passante P2P intersite.

 
|**Site**|**Bande passante pour les pics d'activité SIP (Session Initiation Protocol)/messagerie instantanée**|**Bande passante pour les pics d’utilisation de l’audioconférence**|**Bande passante pour les pics d’utilisation des conférences vidéo**|**Bande passante pour les pics d'activité de partage WAN**|**Bande passante pour les pics d'activité de réseau WAN pour les appels RTC**|**Trafic ExpressRoute total <br/> par classe de site (c’est-à-dire <br/> durée totale et nombre de <br/> sites)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Siège social** <br/> |1 070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Bureaux régionaux** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Grandes succursales** <br/> |70  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Petites succursales** <br/> |36  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Cela signifie que le trafic de Skype Entreprise Online traversant l'itinéraire express sera de 114 Mbits/s environ, de sorte que Dewey devra souscrire au moins à l'abonnement à 200 Mbits/s pour ExpressRoute. Plusieurs circuits ExpressRoute peuvent être achetés à différents emplacements P2P ExpressRoute. Cela pourrait être recommandé si les sites de Dewey se trouvent dans des régions géographiques différentes ou pour fournir une résilience au cas où la connexion au circuit d'ExpressRoute échouerait. Si vous acquérez des circuits ExpressRoute dans plusieurs régions Azure, le complément premium d'ExpressRoute sera nécessaire à la réception d'une connectivité globale sur ExpressRoute.
  
Maintenant que vous avez la quantité totale de bande passante requise et les numéros de bande passante de classe de service (CoS), vous pouvez placer vos commandes auprès du ou des fournisseurs de services réseau sélectionnés. N’oubliez pas d’inclure des estimations pour le trafic d’autres applications et services. Nous proposons des conseils de planification du réseau pour d’autres services Microsoft 365 et Office 365, y compris les calculateurs de bande passante pour les Exchange et OneDrive. L’abonnement à la bande passante pour le fournisseur de services réseau sera plus élevé, car le trafic intra-site devra être rajouté. L’outil de calcul de bande passante Lync 2010 et Lync 2013 fournit uniquement une estimation du trafic attendu. Par conséquent, il est recommandé de confirmer la capacité du réseau à prendre en charge ce volume de trafic lors d’un test de contrainte. 
  
> [!TIP]
> Il est vivement recommandé d'effectuer un test de contrainte lors de l'évaluation préliminaire du réseau. 
  
Un test de contrainte implique la conception et la configuration de l'infrastructure, puis son exécution avec le volume escompté de trafic de simulation lors de la surveillance des performances. Vos estimations de trafic peuvent être inexactes dans certaines régions, mais au moins vous pouvez vous assurer qu'il peut prendre en charge le volume de trafic prévu par l'outil de calcul de bande passante de Lync 2010 et Lync 2013. Il est recommandé d'exécuter le test de contrainte pendant quelques jours au minimum, mais une période de test plus longue permet d'affiner les valeurs. Toutefois, l'extension de la période du test de contrainte doit être comparée au coût des services réseau à payer pour ce trafic réseau qui n'est pas lié à des utilisateurs réels. Microsoft a certifié différents fournisseurs dans le cadre de son programme IT Pro Tools pour fournir des outils de gestion et d'exploitation, dont des outils de contrainte de préévaluation du réseau. Skype Entreprise fournit également des intégrateurs système (SI), qui acceptent les outils IT Pro Tools certifiés et peuvent évaluer le réseau à votre place. Pour en savoir plus, reportez-vous à la rubrique [Solutions Skype Entreprise : outils IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
Un test de contrainte permet de s'assurer que le réseau peut prendre en charge le volume de trafic requis, mais en réalité l'outil de calcul Lync 2010 et Lync 2013 peut être désactivé pour différentes raisons. Vous devez également envisager de poursuivre la surveillance des réseaux de vos sites en évaluant en continu le réseau une fois que celui-ci est déployé pour vous assurer que la bande passante suffit et que les mécanismes de QoS fonctionnent correctement. Il est important de continuer à surveiller les performances du réseau à mesure que le nombre d'utilisateurs réels mis en ligne augmente.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Partie 2 : QoS ExpressRoute Skype Entreprise

Le service ExpressRoute de Microsoft fournit une connexion dédiée au cloud Azure, mais les services de communication de charge de travail en temps réel Office 365 auront besoin de services réseau avec une bande passante suffisante pour prendre en charge le volume de trafic et la qualité de service afin d'offrir à vos utilisateurs une expérience de qualité professionnelle. Une connexion compatible avec la qualité de service doit être configurée de bout en bout (PC, commutateurs et routeurs réseau connectés au cloud), car toute partie du chemin ne prenant pas en charge la qualité de service risquerait de dégrader la qualité de tout l'appel.
  
L’objectif de cette section est de vous aider à comprendre les défis liés à la prise en charge du trafic en temps réel dans un réseau IP, ainsi que la configuration et la prise en charge d’un déploiement ExpressRoute de charges de travail Microsoft 365 ou Office 365 en temps réel à l’aide d’un fournisseur de services ExpressRoute Exchange ou d’un partenaire Fournisseur de services réseau de Microsoft.
  
La qualité de service est acceptée à partir de vos réseaux exclusivement sur des circuits de réseau ExpressRoute et est utilisée au sein du réseau Microsoft pour le trafic Skype Entreprise. Aujourd'hui, des parties de certaines connexions sortantes de Microsoft ont des valeurs DSCP manquantes pour Skype Entreprise. Jusqu'à ce que le trafic sortant soit entièrement marqué avec des valeurs DSCP, nous vous encourageons à suivre les directives pour ajouter des marquages QoS au trafic à votre limite du réseau comme décrit dans la section **Mise en œuvre de la qualité de service en utilisant la Liste de contrôle d'accès au réseau (ACL)** de cet article.
  
### <a name="the-real-time-problem"></a>Problème du temps réel

L'exécution de services voix et vidéo de qualité professionnelle impose des exigences particulières sur un réseau IP. Le trafic en temps réel utilise le protocole RTP (Real-time Transport Protocol), qui s'appuie sur le protocole UDP (User Datagram Protocol). Contrairement au protocole TCP (Transmission Control Protocol), qui quantifie et teste chaque message à la recherche d'erreurs et comporte d'autres mécanismes de détection et de retransmission de messages perdus ou erronés, le protocole UDP n'offre pas ce type de fiabilité. Si les messages sont endommagés par des erreurs ou se perdent en raison de débordements de la mémoire tampon, ils sont perdus définitivement. Le protocole UDP a été sélectionné pour être utilisé avec le protocole RTP, car, en raison de la nature du trafic en temps réel, même si les messages perdus étaient renvoyés, ils arriveraient bien trop tard pour avoir un impact positif sur les flux de messages voix.
  
Conscients de l'impact de la perte de paquets voix, les concepteurs disposaient de deux approches pour améliorer les performances voix et vidéo sur IP :
  
- L'augmentation de la résilience du codage/décodage voix en cas de perte de paquets. Cela peut être effectué soit en utilisant la correction des erreurs de forward (FEC) pour corriger un pourcentage d’erreurs rencontrées, fonctionnalité trouvée dans Microsoft 365 ou Office 365 Real Time Transport, soit en concevant des systèmes de décodage voix qui tentent de masquer l’effet des paquets perdus, caractéristique des codecs Microsoft. 
    
- Sélectionnez des services de transport qui utilisent les mécanismes de QoS pour garantir les performances du réseau en matière de retard, de perte de paquets, de gigue et de variation de délai entre les paquets.
    
Le codage voix résilient résout seulement le problème de perte de paquets. Il est donc important qu'un réseau utilisé pour exécuter en temps réel la voix et la vidéo possède des mécanismes qui réduisent le retard et la gigue. Même avec un codage résilient, si le nombre de paquets perdus est excessif, la station réceptrice ne disposera pas d'informations suffisantes pour reconstruire une version intelligible du signal voix. Le pourcentage de paquets perdus qui entraînerait une dégradation notable de la qualité du signal voix varie selon la technique de codage vocal utilisée. Dans tous les cas cependant, la perte de chaînes est très problématique si elle survient dans des paquets successifs.
  
Il est essentiel de réduire le retard, car un retard excessif peut affecter le flux de la conversation et créer une gêne pour les haut-parleurs. Selon les meilleures pratiques, le retard de bout en bout pour les communications vocales (ce que nous appelons le retard « de bouche à oreille ») doit être inférieur à 150 millisecondes (ms). Il s'agit d'un retard unidirectionnel et non pas d'un retard « aller-retour ». Bien sûr, le délai de transmission augmentera sur les liens de transmission plus longs, comme dans le cas de communications qui traversent les océans en raison du retard de propagation ou de l'acheminement physique du signal dans le câble.
  
Un retard supérieur à 150 ms dans une communication unidirectionnelle a un effet étrange sur le locuteur. En raison du décalage, celui-ci répète les derniers mots prononcés, car il estime que le destinataire n'a pas entendu le message en totalité. Cela entraîne une collision avec la réponse différée provenant de l'extrémité distante. Si vous avez déjà parlé sur un canal satellite, vous reconnaîtrez cet effet. Sur un canal satellite, le retard unidirectionnel est d'environ 250 ms, ce qui est bien supérieur au retard autorisé.
  
 **Paramètres réseau recommandés pour des communications vocales de qualité professionnelle**
  
|**Paramètre**|**Valeur recommandée**|
|:-----|:-----|
|Gigue des paquets entre arrivées (moyenne)  <br/> |≤ 5 ms  <br/> |
|Gigue des paquets entre arrivées (maximale)  <br/> |≤ 40 ms  <br/> |
|Taux de perte de paquets (moyenne)  <br/> |Approche 0 %  <br/> |
|Latence unilatérale du réseau  <br/> |≤ 100 ms (doit inclure les vérifications du retard par rapport à la distance géographique)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute dans le cadre d'un réseau vocal de qualité professionnelle

ExpressRoute offre une connexion dédiée par le biais d'un fournisseur de services réseau ou d'un fournisseur Exchange dans l'une des trois options de connexion : 
  
- Colocalisation Exchange du cloud
    
- Connexion Ethernet point à point
    
- Connexion tout point à tout point (IPVPN)
    
Cela offre des avantages de haute disponibilité (99,9 % du contrat de niveau de service), un acheminement fiable sécurisé (pas de transit Internet), qui n'est pas affecté par des variations de trafic Internet et respecte les repères de qualité de service pour hiérarchiser le trafic (la qualité de service est définie ci-dessous). ExpressRoute, accompagné d'un réseau WAN bien planifié, peut vous fournir un réseau vocal de qualité professionnelle.
  
Vous pouvez utiliser ExpressRoute pour le transit de données à partir de bureaux ou de centres de données (dans le cas d'une topologie hybride) connectés au circuit. Les données des utilisateurs hors site (par exemple, à partir de bureaux à domicile ou lors de déplacements) n'exploiteront pas le circuit ExpressRoute sauf si les utilisateurs sont connectés à un VPN. Elles ne doivent pas être incluses aux estimations de bande passante pour mesurer le circuit ExpressRoute. Si vous êtes un client international, vous pouvez acquérir des circuits ExpressRoute dans chaque région et utiliser des balises de communauté BGP pour informer les règles d'acheminement afin que le trafic soit dirigé vers le circuit ExpressRoute préféré (généralement le plus proche de chaque site), tandis que les autres circuits offrent une redondance en cas de panne affectant un seul circuit. 
  
### <a name="if-expressroute-isnt-an-option"></a>Cas dans lesquels ExpressRoute n'est pas une option possible

Il est parfois impossible de connecter tous les sites à ExpressRoute pour des raisons de coûts, une incapacité à répondre aux conditions requises d'ExpressRoute ou des restrictions de votre fournisseur de services réseau actuel. Si vous ne pouvez pas utiliser ExpressRoute, vous devez tout de même suivre les directives ci-dessous concernant le marquage de la qualité de service dans votre réseau et planifier les contrats avec votre fournisseur de services réseau afin de garantir une bande passante suffisante et la prise en charge de la hiérarchisation du trafic en fonction de la qualité de service.
  
De plus, si vous avez des bureaux dans différentes régions, mais que vous ne disposez pas de circuits ExpressRoute dans toutes les régions, vous devez utiliser les balises de communauté BGP de la région lors de la configuration de l'acheminement pour le trafic en direction/en provenance des bureaux satellites afin d'éviter un transit longue distance inutile. Par exemple, imaginez une société qui dispose d'une organisation Skype Entreprise Online hébergée aux États-Unis, mais qui a des succursales en Europe et ne possède qu'un seul circuit ExpressRoute dans la Silicon Valley. La majeure partie du trafic de Skype Entreprise Online sera acheminée vers un centre de données dans lequel l'organisation est hébergée (par exemple, les téléconférences avec d'autres utilisateurs dans l'entreprise). L'utilisation du circuit ExpressRoute peut être préférée pour la plupart du trafic. Toutefois, si un utilisateur en Europe devait participer à une téléconférence hébergée par une autre société dont l'organisation est située en Europe, la destination des éléments multimédias de cet appel serait le centre de données européen dans lequel se trouve la seconde société. L'acheminement du trafic par le biais du circuit ExpressRoute de la Silicon Valley serait un itinéraire moins direct que par Internet. Si c'est le cas, vous souhaitez peut-être configurer les routeurs dans votre réseau (par exemple, dans les bureaux européens) pour inspecter les balises de communauté lors de l'élaboration de règles d'acheminement et mettre en place un acheminement par Internet plutôt que par le biais du circuit ExpressRoute de la Silicon Valley pour le trafic comportant des balises dans la région européenne.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Concepts de base de qualité de service (QoS)/classe de service (CoS)

En technologie IP, la qualité de service (QoS) décrit un mécanisme qui permet de hiérarchiser les priorités de traitement des paquets. Selon la définition de l'Union Internationale des Télécommunications (UIT), QoS comprend tous les aspects de la qualité d'une connexion, dont le retard, la perte, le rapport signal-bruit, les interférences, l'écho, les interruptions, la réponse de fréquence, les niveaux de puissance sonore, etc. Ce que nous appelons QoS pour les réseaux de paquets porte le nom plus approprié de « classe de service » (CoS), qui se concentre sur l'amélioration des performances en termes de retard, d'instabilité et de perte de paquets, mais nous continuerons à utiliser le terme QoS, car il est plus courant.
  
L'utilisation de QoS sur un réseau IP implique deux composants principaux :
  
- La réservation d'une quantité définie de bande passante sur chaque lien pour le trafic en temps réel. Si cette bande passante n'est pas nécessaire pour le trafic en temps réel à tout moment, elle peut être utilisée pour les autres communications. En règle générale, il est conseillé de ne pas affecter plus de 30 % de la capacité d'un lien au trafic vocal.
    
- Le marquage des paquets avec un indicateur de priorité dans l'en-tête indique aux commutateurs et aux routeurs la priorité du paquet dans le chemin réseau.
    
Lorsqu'un paquet est reçu sur un commutateur ou un routeur, il est déplacé vers une file d'attente de sortie du prochain saut ou de la prochaine étape. Il existe des files d'attente de sortie différentes pour les niveaux de priorité différents. Un commutateur ou un routeur utilise un algorithme qui sert la file d'attente de priorité supérieure plus fréquemment que les files d'attente de priorité inférieure.
  
La difficulté réside dans les différentes techniques de qualité de service mises en œuvre en Layer 2 (couche Ethernet ou Wi-Fi) et Layer 3 (couche IP). Il peut être nécessaire de configurer ces mises en œuvre de la qualité de service au niveau de chaque commutateur et routeur du réseau, ainsi que dans l'interface entre votre réseau et le réseau du fournisseur de services réseau.
  
Il existe deux options de mappage des applications Skype Entreprise aux classes de service appropriées :
  
- Marquage des points de terminaison utilisant DSCP (Differentiated Services Control Point) 
    
- Liste de contrôle d'accès (ACL) réseau
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Marquage des points de terminaison - DSCP (Differentiated Services Control Point)

DiffServ (Differentiated Services) est considéré comme un mécanisme « grossier » de classification et de gestion du trafic réseau et de fourniture de QoS dans les réseaux IP. Les routeurs et les autres appareils qui mettent en œuvre les fonctions Layer 3 utilisent DSCP (DiffServ Control Point) pour définir la priorité du paquet. QoS est mise en œuvre par l'insertion d'une valeur DSCP sur 6 bits (autorisant 64 niveaux de priorité différents) dans le champ Services différenciés (anciennement le champ « Type de service ») dans l'en-tête IP. Les niveaux de priorité sont généralement définis comme suit :
  
 **Paramètres DSCP recommandés**
  
|**Catégorie de trafic**|**Traitement (marquage DSCP)**|**Charge de travail de Skype Entreprise**|
|:-----|:-----|:-----|
|**Voix** <br/> |EF (46)  <br/> |Skype Entreprise et fonctionnalités vocales de Lync  <br/> |
|**Interactive** <br/> |AF41 (34)  <br/> |Vidéo  <br/> |
||AF21 (18)  <br/> |Partage d'application  <br/> |
|**Par défaut** <br/> |AF11 (10)  <br/> |Transfert de fichiers  <br/> |
||CS0 (0)  <br/> |une autre valeur  <br/> |
   
 **En-tête IP version 4**
  
![En-tête IPv4.](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS Layer 2 : norme IEEE 802.1p/multimédia Wi-Fi (IEEE 802.11e)

Même si DSCP est le mécanisme standard pour la mise en œuvre de QoS en Layer 3, il existe des mécanismes Layer 2 pour les connexions filaires (Ethernet) et les connexions sans fil (Wi-Fi). Le mécanisme QoS pour les réseaux filaires est défini dans la norme IEEE 802.1p. Le mécanisme QoS WLAN est défini dans la norme IEEE 802.11e, ce que la Wi-Fi Alliance appelle « Wi-Fi Multi-Media Certified » (WMM Certified).
  
La norme IEEE 802.1p utilise un point de code de priorité (PCP) 3 bits pour identifier la priorité du message. Le PCP appartient à un champ 32 bits de l'entête Ethernet qui comporte également l'identificateur VLAN. Les définitions des valeurs de PCP sont incluses ci-dessous.
  
 **Valeurs de PCP IEEE 802.1p**
  
|**Valeur PCP**|**Priorité**|**Acronyme**|**Types de trafic**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Contrôle du réseau  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Contrôle inter réseau  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Voix  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Vidéo  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Applications critiques  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Excellent effort  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |Meilleur effort  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Arrière-plan  <br/> |
   
La norme IEEE 802.1p est mise en œuvre quasiment de la même façon que DSCP avec le trafic trié dans des files d'attente de priorités différentes pour chaque niveau de priorité, mais la nature du trafic multimédia partagé des WLAN implique une approche différente. Même si le point d'accès et le client gèrent des files d'attente de sortie distinctes pour les différents niveaux de priorité, il existe également des différences relatives à l'envoi des trames sur le canal radio.
  
Dans un réseau Wi-Fi, tous les clients associés à un point d'accès partagent un seul canal en semi-duplex (seule une station client ou seul le point d'accès peut envoyer les données à la fois). Pour réduire le risque de collisions sur le canal radio, avant l'envoi d'une trame, la station attend que le canal soit inactif pendant une certaine période appelée « Espacement intertrame », si le canal est occupé lorsqu'une station vient à envoyer des données, la durée d'attente est aléatoire. Si l'expéditeur ne reçoit pas de message de confirmation du destinataire une fois que la trame est envoyée, il part du principe qu'une collision ou un incident s'est produit et définit un intervalle aléatoire avant d'essayer d'accéder au canal radio pour retenter l'envoi. L'intervalle de désactivation est aléatoire pour réduire la probabilité de nouvelle collision entre les deux mêmes stations.
  
Pour définir la priorité d'accès au canal radio, la norme IEEE 802.11e/WMM définit différents intervalles d'attente de prétransmission appelés « Espacements intertrames arbitrés » (AFIS) et d'autres intervalles de désactivation pour les classes de trafic différentes. Quatre niveaux de priorité appelés « Catégories d'accès » sont définis.
  
La priorité est définie en affectant des valeurs AFIS plus courtes aux trames de priorité supérieure. Par conséquent, si une station attend d'envoyer une trame voix et qu'une autre attend d'envoyer une trame de données, la trame voix sera toujours envoyée en premier. Techniquement, les trames voix et vidéo reçoivent la même valeur AFIS, mais la plage des intervalles de temporisation pour les trames vidéo est plus élevée. Ainsi, alors qu'une trame voix et vidéo peut entrer en collision à la première tentative, la trame voix sera toujours retransmise plus tôt. La corrélation entre IEEE 802.1p et IEEE 802.11e est indiquée ci-dessous :
  
 **Mappage des média IEEE 802.11e/Wi-Fi (WMM) et 802.1P**
  
|**Catégorie d'accès WMM**|**WMM Description**|**Valeur PCP 802.1p**|**Désignation 802.1p**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Voix  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Vidéo  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Meilleur effort Données  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4 (AC_BK)  <br/> |Arrière-plan Données  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
L'association recommandée en Layer 3 aux priorités en Layer 2 est représentée ici :
  
 **Associations recommandées pour les priorités en Layer 3 avec Layer 2**
  
|&nbsp; |**Marqueurs Layer 3**|**Layer 2 (valeur de PCP)**|**Wi-Fi (catégorie d'accès)**|
|:-----|:-----|:-----|:-----|
|Contrôle du réseau  <br/> |Comportement par saut (PHB) - sélecteur de classe (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valeur DSCP -48  <br/> |
|Voix  <br/> |Comportement par saut (PHB) - Acheminement accéléré (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valeur DSCP - 46  <br/> |
|Conférence vidéo  <br/> |Comportement par saut (PHB) - Acheminement assuré (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valeur DSCP - 34  <br/> |
|Signalisation d'appel  <br/> |Comportement par saut (PHB) - sélecteur de classe (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valeur DSCP - 24  <br/> |
|Données de faible latence  <br/> |Comportement par saut (PHB) - Acheminement assuré (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valeur DSCP -18  <br/> |
|Données haut débit  <br/> |Comportement par saut (PHB) - Acheminement assuré (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valeur DSCP - 10  <br/> |
|Meilleur effort  <br/> |Comportement par saut (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valeur DSCP - 0  <br/> |
   
Il est important de noter qu'il y a une incompatibilité dans le codage des priorités pour IEEE 802.1p et WMM. La valeur PCP 802.1p est de 5 pour la voix, cependant, dans le mappage d'équivalence standard avec WMM, PCP 5 est traduit en catégorie d'accès 2 (CA), la catégorie d'accès WMM pour la vidéo (AC_VI). Si cela est possible, vous devez remplacer ce mappage afin de permettre la conversion de PCP 5 en AC 1 ou d'éviter simplement l'utilisation de la voix et de la vidéo sur le même réseau Wi-Fi tant que l'Alliance Wi-Fi n'a pas résolu ce problème. Pour plus d’informations sur le Wi-Fi, [voir Les éléments de catalogue Wi-Fi.]( https://go.microsoft.com/fwlink/?LinkId=690322)
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Mise en œuvre de QoS à l'aide d'une liste de contrôle d'accès (ACL) réseau

L'autre méthode de mise en œuvre de QoS dans une configuration réseau ExpressRoute consiste à utiliser une liste de contrôle d'accès (ACL) réseau. Dans cette approche, au lieu que les points de terminaison insèrent le marquage DSCP dans l'en-tête de chaque paquet, le marquage peut être effectué par un routeur en amont basé sur le port UDP source. Tous les commutateurs et les routeurs doivent toujours être configurés pour prendre en charge QoS afin de vérifier que les paramètres DSCP sont conservés. Mieux encore, le routeur connecté au réseau du fournisseur de services doit conserver les paramètres DSCP dans l'en-tête de chaque paquet, car il s'agit d'instructions que vous avez saisies pour indiquer au fournisseur de services la façon dont le paquet doit être traité.
  
Les plages de ports recommandées pour chaque application Skype Entreprise sont répertoriées à la section 2.6.1.1 du guide planification, surveillance et dépannage réseau avec [Lync Server.](https://go.microsoft.com/fwlink/?LinkId=690286) Il est important de coordonner cela avec l'approche globale de l'entreprise vis-à-vis de QoS, et vous devez être conscient des différentes stratégies de QoS et des différences de marquage de paquets potentielles.
  
Même si la principale raison d'utiliser les services réseau QoS et MPLS est de garantir une expérience utilisateur excellente pour la voix et la vidéo en temps réel, ces fonctionnalités peuvent s'appliquer aux applications de données. Au lieu de traiter toutes les applications de la même façon, les réseaux MPLS permettent aux entreprises de hiérarchiser les priorités entre applications de données. Avec MPLS, les applications en temps réel, comme les transactions de carte de crédit ou le partage d'applications, peuvent être prioritaires par rapport aux applications dont le trafic est moins urgent, comme la messagerie électronique.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Présentation des types de services réseau IP- IP et MPLS de base

À l'origine, le transfert de paquets IP fonctionnait sur le principe de « meilleur effort ». Cela signifiait que les routeurs transmettant ces paquets IP faisaient de leur mieux pour les livrer à destination, mais sans garantir le moment et la bonne fin de la transmission. Voici comment les services Internet de base, dont votre connexion Internet résidentielle, fonctionnent aujourd'hui. L'idée était que si la fiabilité était nécessaire pour une application spécifique, elle serait fournie à un niveau supérieur dans la pile de protocoles. Le protocole TCP (Transmission Control Protocol) est le mécanisme de livraison fiable. Le protocole UDP (User Datagram Protocol), qui est utilisé pour la voix et la vidéo en temps réel, est le mécanisme de livraison non fiable (c'est-à-dire de « meilleur effort »). 
  
MPLS (Multi-Protocol Label Switching) a été développé comme un moyen pour les fournisseurs de services réseau d'offrir un service IP avec des garanties de performance en termes de retard, de gigue et de perte de paquets. Pour garantir ces performances, MPLS exploite en partie le côté imprévisible du traitement IP traditionnel. Tout d'abord, au lieu de laisser chaque paquet trouver son chemin entre routeurs jusqu'à sa destination (chaque paquet risquant de prendre une route entre la source et la destination), MPLS achemine tous les paquets sur une connexion à « circuit virtuel » à l'aide d'une route fixe appelée chemin à commutation d'étiquettes (LSP). En cas d'échec de l'un des liens dans ce chemin, tous les LSP utilisant ce lien sont redirigés rapidement.
  
Lorsqu'un paquet est envoyé dans le réseau MPLS, le routeur de périphérie du fournisseur de services réseau ajoute un en-tête supplémentaire au paquet, qui comprend une étiquette utilisée pour le transfert sur le LSP approprié. L'étiquette est supprimée par le routeur de périphérie à l'autre extrémité du réseau MPLS.
  
Non seulement MPLS simplifie le processus de transfert, mais il indique également au système de gestion réseau les connexions qui sont établies sur chaque lien du réseau. En contrôlant la façon dont le trafic est acheminé sur le réseau, l'opérateur peut garantir la qualité de service fournie par chaque chemin. Par conséquent, contrairement aux performances de meilleur effort des réseaux IP traditionnels ou de base, les opérateurs MPLS fournissent un service IP aux performances prévisibles. Le mode de fonctionnement du LSP rend MPLS plus sûr que les services Internet traditionnels. Par conséquent, avec le service IP de base, nous espérons que le réseau soit suffisamment performant pour fournir des prestations voix, des techniques d'utilisation de bonne qualité, comme FEC, ainsi qu'un codage voix plus résilient. Avec MPLS, ces performances sont garanties.
  
Les fournisseurs MPLS offrent plusieurs niveaux de service, mais chacun d'eux utilisent des termes différents pour les identifier. Vous devez travailler en étroite collaboration avec votre fournisseur pour vous assurer qu’il comprenne les sorties de l’outil de calcul de bande passante [Lync 2010 et Lync 2013,](https://go.microsoft.com/fwlink/?LinkID=690282) ainsi que les options recommandées pour les différentes applications Charge de travail en temps réel Microsoft 365 ou Office 365.
  
## <a name="conclusion"></a>Conclusion

Skype Entreprise améliore la gestion des communications d'entreprise. Plutôt que d'avoir un téléphone connecté à un PBX, un système de conférences vidéo autonome, une plate-forme séparée pour le courrier électronique, un service extérieur pour les audioconférences et des fonctionnalités de messagerie instantanée et de présence, Skype Entreprise regroupe toutes ces fonctionnalités dans une interface utilisateur unique.
  
La fourniture constante de services voix et vidéo en temps réel de qualité professionnelle nécessite une infrastructure réseau compatible avec QoS de bout en bout. Cela pourrait inclure des services LAN et WAN. Microsoft propose des outils comme l'[outil de calcul de bande passante Lync 2010 et Lync 2013](https://go.microsoft.com/fwlink/?LinkID=690282) pour estimer la capacité du réseau dont vous aurez besoin pour les différents services. Il existe également des partenaires dans le programme Outils informatiques Pro [Solutions Skype Entreprise](https://go.microsoft.com/fwlink/?LinkID=690307) : Outils de Pro informatiques qui proposent des outils pour préévaluer l’infrastructure réseau et prendre en charge la surveillance, la signalement et la résolution des problèmes. Sans une infrastructure réseau dimensionnée et configurée correctement, votre déploiement ExpressRoute Skype Entreprise risque de ne pas répondre aux attentes de votre utilisateur en termes de qualité et de cohérence.
  
Des outils d'entreprise efficaces doivent avoir un fonctionnement fiable et homogène et fournir une expérience encourageant les utilisateurs à les adapter. D'un point de vue réseau, cela signifie qu'il faut disposer d'une infrastructure réseau, à la fois locale et globale, fixe et mobile, permettant cela. La planification, la conception, la mise en œuvre et la maintenance de cette infrastructure ne sont pas toujours aisées. Le matériel, les outils et les services réseau qui permettent d'y parvenir sont disponibles aujourd'hui, mais les informaticiens doivent être conscients que ceux-ci sont conçus, mis en œuvre et maintenus d'une manière qui garantit que les utilisateurs bénéficient d'un ensemble de services de communication et de collaboration qui leur permettent de travailler efficacement et que l'organisation peut tirer pleinement profit des possibilités de cette technologie. 
  
## <a name="related-topics"></a>Sujets associés

[Documentation ExpressRoute](/azure/expressroute/)

  
