---
title: Notes de publication
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: Cet article présente les améliorations cumulatives apportées aux salles de Microsoft Teams.
ms.openlocfilehash: 8461c3c7f1a3b132e3cabad81eeb211c28e8ef3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288459"
---
# <a name="release-notes"></a>Notes de publication 

Cet article présente les améliorations cumulatives apportées aux salles de Microsoft Teams.


##  <a name="version-history"></a>Historique des versions

| Communiquer | Publié sur <br>Microsoft Store | 
| ---     | ---  |
| 4.0.85.0 | 04/08/2019   |
| 4.0.78.0 | 03/14/2019   |
| 4.0.76.0 | 03/04/2019   |
| 4.0.64.0 | 12/14/2018   |
| 4.0.51.0 | 11/17/2018   | 
| 4.0.31.0 | 10/16/2018   | 
| 4.0.27.0 |  10/1/2018    | 
| 4.0.19.0 |  08/31/2018    |   
| 4.0.18.0 |  08/27/2018    |   
| 4.0.8.0 |  07/06/2018    |   
| 3.1.115.0|  06/18/2018    |
| 3.1.113.0|  06/13/2018    |   
| 3.1.112.0|  06/05/2018    |   
| 3.1.104.0|  04/16/2018    |            
| 3.1.100.0|  03/16/2018    |            
| 3.1.99.0 | 3/14/2018      |  
| 3.1.98.0    | 3/8/2018    |   
|  3.0.16.0    |  11/27/2017   |
| 3.0.15.0 | 10/3/2017  |            
| 3.0.12.0 |  9/1/2017  |            
| 3.0.8.0 | 11/16/2017 | 
| 3.0.6.0 | 11/16/2017 | 
| 2.0.2.0  | 03/15/2017 | 
| RTM (1.0.8) | 12/7/2016  | 

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Présentation de la fonctionnalité salles de Microsoft teams et résolution des problèmes

### <a name="40850-0482018"></a>4.0.85.0 (04/8/2018)

Présenté dans cette mise à jour:

- Correction d’un problème lié à la fonctionnalité «envoyer des commentaires» 
- Optimisations pour préparer la mise à jour de l’appareil MTR vers Windows 10 version 1809

### <a name="40780-03142018"></a>4.0.78.0 (03/14/2018)

Présenté dans cette mise à jour:

- Correction du bogue «se bloquer lors du démarrage de l’application» qui affectait des périphériques ayant subi des problèmes sur les versions antérieures de Windows 10 RS2.  


### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Présenté dans cette mise à jour:

- Pavé numérique DTMF pour les réunions P2P et les appels RTC de Microsoft Teams. Pour que Microsoft teams appelle votre client par défaut, les administrateurs doivent définir IsTeamsDefaultClient sur true.
- Épingler la vidéo entrante d’un participant distant en plein écran sur l’écran d’accueil de la salle. Utiliser la commande «épingler» dans la liste des participants de la console
- Améliorations apportées aux notifications de salle d’attente grâce à l’ajout de la notification de salle
- L’option d’affichage précédant la salle supprime l’icône de diffusion lorsque la balise Bluetooth n’est pas activée sur l’appareil système d’une salle
- Résoudre le problème de contrôle du volume dans les réunions teams


### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Présenté dans cette mise à jour:

- Afficher le contenu à la fois sur les systèmes de salle à deux écrans
- Améliorations apportées à l’interface utilisateur et au premier plan de la salle
- Prise en charge du client TLS 1,2. Pour les clients sur site, l’activation de communciation sur TLS 1,2 pour Microsoft teams cummulative nécessite Skype entreprise Server 2015 Update 9 (CU9) ou Skype entreprise Server 2019 cummulative Update 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Présenté dans cette mise à jour:

- Prise en charge de l’affichage double (avant la salle) pour les réunions teams 

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Présenté dans cette mise à jour:

- Correctifs de qualité et de fiabilité

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Présenté dans cette mise à jour:
 
- Modifications du code nécessaires pour préparer l’application Microsoft teams pour une version ultérieure de Windows 10 version 1803
- Résoudre le problème de mise en forme des CLUF localisés-en particulier du norvégien, qui empêche d’avancer au-delà de la fenêtre de configuration de EULA
- Modifications du code nécessaires à l’exécution de l’application Microsoft teams En savoir plus [ici](https://aka.ms/lrsupgrade).
 
### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)
Présenté dans cette mise à jour:

- Le correctif logiciel pour l’application Crestron ne se lance pas, ce qui devrait normalement être accessible en appuyant sur le bouton application sur des appareils Crestron SR. Redémarrage de l’application Microsoft teams Room requis après l’installation d' 4.0.19.0. 

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)
Présenté dans cette mise à jour:

- Améliorations de la fonctionnalité «signaler un problème» en mode équipes (équivalent de «envoyer des commentaires» en mode Skype entreprise)
- Possibilité de basculer entre teams et le mode Skype entreprise pour les appels SIP
- Améliorations apportées à l’accessibilité (narrateur, loupe)
- Redémarrer automatiquement l’application quand il est requis après l’application des modifications de mise en service XML
- Correctifs divers

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Présenté dans cette mise à jour:
- Cette mise à jour permet la prise en charge des réunions Skype entreprise *et* teams sur les appareils de systèmes de salle.  Teams est désactivé par défaut une fois que la mise à jour est appliquée.  Les administrateurs peuvent activer les équipes localement dans les paramètres de l’appareil ou à l’aide d’une Poussée XML distante.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Présenté dans cette mise à jour:

- Correction de l’erreur d’adresse observée sur certains systèmes lors du lancement de l’application.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)
Présenté dans cette mise à jour:

- Modification permettant à Microsoft de gérer plus facilement les mises à jour Windows.
- Aucune modification de l’utilisation des utilisateurs finaux.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Présenté dans cette mise à jour:

- Résoudre les problèmes de réactivité de la console de gestion des problèmes observés sur les appareils surface Pro 2017 connectés à deux affichages de la salle et de l’acquisition vidéo
- Vérification automatisée pour vous assurer que le système exécute le dernier script de mise en service.

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Présenté dans cette mise à jour:

- Correction pour améliorer le comportement de clavier visuel (clavier visuel) dans les systèmes Windows 10 version 1709
- Améliorations pour préparer les mises à jour de systèmes d’exploitation ultérieures

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Présenté dans cette mise à jour: 

- Application mise à jour pour améliorer la télémétrie.

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Présenté dans cette mise à jour:

- Résout un problème lié aux problèmes de réunion intermittente.
- Corrige un problème connu pour le résultat de l’utilisation de l’appareil «blocage».

### <a name="31980--382018"></a>3.1.98.0 (3/8/2018)

Présenté dans cette mise à jour:

- Correctifs de bogues/blocages permettant d’améliorer la stabilité
- Prise en charge de la console de taille variable
- Déchargement du traitement du son pour le son de périphériques (création de médias supplémentaires)
- Optimisations qui permettra aux professionnels de l’informatique de générer des images à la fois avec Windows 10 version 1709 janvier et version ultérieure.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Présenté dans cette mise à jour:
 
- Corrige un problème lié à la fonctionnalité «envoyer des commentaires».

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Présenté dans cette mise à jour:

- Prise en charge du matériel de votre station de [Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Prise en charge de [Logitech brio](https://www.logitech.com/en-us/product/brio)
- Résout un problème dans lequel les écrans (console et avant-première) ne sont pas en mode veille s’il n’y a aucune activité dans la salle.


### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Présenté dans cette mise à jour:

- S’exécute sur une tablette surface Pro (2017)  
- Prend en charge la mise à jour de Windows 10 entreprise Creator (langue anglaise, Build 1703)
- Prise en charge du matériel [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) Dock
- Support OEM pour les contrôles d’environnement (Crestron)

Dans le cadre de la mise à jour de Microsoft teams 3.0.12.0 (Update 3), la version 64 bits de l’édition anniversaire Windows 10 entreprise (langue anglaise, version 1607) n’est plus prise en charge.

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Présenté dans cette mise à jour:

- Résout les problèmes observés lors de la recherche d’utilisateurs fédérés via le champ recherche de participants. Auparavant, il est possible que les résultats de la recherche pour les utilisateurs fédérés externes n’aient pas été résolus correctement et qu’ils aient renvoyé des résultats incorrects.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Présenté dans cette mise à jour:

- Prise en charge de l’affichage double écran (pour la parité du système hérité)
- Fonctionnalités universelles (thèmes intégrés et possibilité de définir un thème personnalisé)
- Possibilité de fournir des commentaires pour les builds publiques
- Télémétrie améliorée concernant la fiabilité de la participation à une réunion
- Rapports OMS supplémentaires
- Capacité de l’administrateur informatique à configurer les appareils à distance  <!--  - Front-of-Room UX shows room details pre-meeting U2  -->


### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Présenté dans cette mise à jour:

- Sélection de l’utilisateur dans l’application pour les appareils audio et vidéo de la salle de réunion
- Rapports d’état de la console de salle intégrés pour les clients utilisant Microsoft Operations Management suite, moniteur Azure  

### <a name="release-to-market--1272016"></a>Mise sur le marché (12/7/2016)

**Fonction (s):**

 **Conçue pour Skype Entreprise**
  
- Participation aux réunions Skype en un clic
- Optimisation de l’expérience de réunion Skype pour les espaces équipés de vidéo HD plein écran et d’audio HD large bande
- Tous les participants peuvent se connecter à la réunion Skype à l’aide du dispositif de leur choix où qu’ils soient
- Invitez des contacts via votre annuaire qui vous indiquera leur disponibilité, ou via un appel téléphonique
- Prise en charge de la conférence PSTN Skype Entreprise et de la fonction d’appel PSTN pour remplacer le téléphone de conférence autonome de votre salle de réunion

  **Conversion d’un espace de réunion**
  
- Optimisation de l’application de réunion Skype dédiée pour le centre du contrôleur tactile et large écran d’affichage
- Réutilisation des investissements existants de votre écran d’affichage ou vos projecteurs
- Fonctionne avec tout type d’espace de réunion, allant des petites salles aux vastes espaces de conférence
- Des périphériques audio et vidéo Skype Entreprise certifiés sont disponibles pour différentes tailles d’espace
- Réception par câble intégrée pour la projection du bureau partagé vers la salle et la réunion Skype

  **Facilité de déploiement, simplicité de gestion**
  
- Appareil fonctionnant en continu qui active l’écran d’affichage lorsqu’il détecte des personnes dans la salle
- Déploiement simple et mise à jour de l’application de réunion Skype UWP (plateforme Windows universelle)
- L’AppLocker de Windows verrouille l’appareil sur l’application de réunion Skype
- Contrôle et gestion similaires à un appareil Windows 10 Enterprise via Intune et SCCM (MDM)
- Fiabilité pour l’entreprise
- Effort de formation minime des utilisateurs finaux, grâce à l’interface utilisateur Skype familière
- S’exécute sur une tablette surface Pro 4

<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Préparer votre environnement](srs-v2-prep.md)

[Prise en charge des versions de succursales actuelles de Microsoft teams](srs2-lifecycle-support.md)

[Problèmes connus de Microsoft teams](known-issues.md)

[Plan pour les salles de Microsoft teams](skype-room-systems-v2-0.md)

[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)
