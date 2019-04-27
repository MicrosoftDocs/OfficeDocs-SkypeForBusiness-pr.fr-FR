---
title: Notes de publication
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: Cet article décrit les améliorations cumulatives dans les salles d’équipes Microsoft.
ms.openlocfilehash: 7c628a130593c900e79daa872645394415e1aa73
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362765"
---
# <a name="release-notes"></a>Notes de publication 

Cet article décrit les améliorations cumulatives dans les salles d’équipes Microsoft.


##  <a name="version-history"></a>Historique des versions

| Version | Publié sur <br>Magasin de Microsoft | 
| ---     | ---  |
| 4.0.78.0 | 14/03/2019   |
| 4.0.76.0 | 04/03/2019   |
| 4.0.64.0 | 14/12/2018   |
| 4.0.51.0 | 17/11/2018   | 
| 4.0.31.0 | 16/10/2018   | 
| 4.0.27.0 |  10/1/2018    | 
| 4.0.19.0 |  08/31/2018    |   
| 4.0.18.0 |  27/08/2018    |   
| 4.0.8.0 |  07/06/2018    |   
| 3.1.115.0|  18/06/2018    |
| 3.1.113.0|  13/06/2018    |   
| 3.1.112.0|  06/05/2018    |   
| 3.1.104.0|  04/16/2018    |            
| 3.1.100.0|  16/03/2018    |            
| 3.1.99.0 | 3/14/2018      |  
| 3.1.98.0    | 3/8/2018    |   
|  3.0.16.0    |  27/11/2017   |
| 3.0.15.0 | 10/3/2017  |            
| 3.0.12.0 |  9/1/2017  |            
| 3.0.8.0 | 16/11/2017 | 
| 3.0.6.0 | 16/11/2017 | 
| 2.0.2.0  | 15/03/2017 | 
| RTM (1.0.8) | 12/7/2016  | 


## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Résolution de présentation et des problèmes de fonctionnalité salles d’équipes Microsoft


### <a name="40780-03142018"></a>4.0.78.0 (14/03/2018)
Introduite dans cette mise à jour :
- Correctif de bogue « se bloquer au démarrage de l’application » qui est affectée de périphériques sur build Windows 10 RS2 héritée.  


### <a name="40760-03042019"></a>4.0.76.0 (04/03/2019)
Introduite dans cette mise à jour :
- Clavier DTMF pour les réunions Microsoft équipes P2P et appels PSTN. Pour rendre Microsoft Teams votre client appelant par défaut, administrateurs doivent définir IsTeamsDefaultClient sur true
- Épingler vidéo entrant d’un participant à distance en mode plein écran sur le devant de l’affichage de la salle. Utilisez la commande « Pin » à partir de la liste des participants dans la console
- Améliorations apportées à des notifications de salle d’attente avec ajout de notification avant de salle
- Avant de l’affichage de la salle supprime l’icône de conversion forcée lors de la balise Bluetooth n’est pas activé sur le périphérique de système de salle
- Correctif pour le problème de contrôle de volume dans les réunions d’équipes


### <a name="40640-12142018"></a>4.0.64.0 (14/12/2018)
Introduite dans cette mise à jour :
- Afficher le contenu sur les deux salle de frontal (pour) affiche sur les systèmes de salle double écran
- Améliorations de l’interface utilisateur avant de salle et de thèmes
- TLS 1.2 prise en charge de côté client. Pour sur les clients du site, l’activation de communication via TLS 1.2 pour les salles d’équipes Microsoft nécessite Skype pour Business Server 2015 Cummulative mise à jour 9 (cumulative 9) ou Skype pour les entreprises Server 2019 Cummulative mise à jour 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (17/11/2018)
Introduite dans cette mise à jour :
- Prise en charge du double affichage (avant de salle) pour les réunions d’équipes 

### <a name="40310-10162018"></a>4.0.31.0 (16/10/2018)
Introduite dans cette mise à jour :
- Correctifs de qualité et la fiabilité 

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)
Introduite dans cette mise à jour : 
- Modifications du code nécessaires pour préparer l’application Microsoft équipes salles mise à niveau de Windows 10 Version 1803 ultérieure
- Corriger le problème à la mise en forme avec localisées CLUF - spécifiquement norvégien -, ce qui empêche de passer au-delà de fenêtre de paramètres EULA OOBE
- Modifications du code nécessaires pour rendre les applications Microsoft équipes salles s’exécutent sur les systèmes de salle de Lync. Plus d’informations, consultez la rubrique [ici](https://aka.ms/lrsupgrade).
 

### <a name="40190-8312018"></a>4.0.19.0 (31/8/2018)
Introduite dans cette mise à jour : 
- Correctif pour application Crestron ne pas lancer qui serait normalement accessible en appuyant sur le bouton d’application sur les appareils Crestron SR. Redémarrage de l’application Microsoft équipes salles requis après l’installation de 4.0.19.0. 

### <a name="40180-08272018"></a>4.0.18.0 (27/08/2018)
Introduite dans cette mise à jour : 
- Améliorations des fonctionnalités de « Signaler un problème » en mode équipes (équivalent de « Commenter » dans Skype pour le mode de l’entreprise)
- Permet de capacité de secours à partir des équipes Skype pour le mode d’entreprise pour les appels SIP
- Améliorations d’accessibilité (le Narrateur, la Loupe)
- Automatiquement le redémarrage de l’application nécessaire après les modifications de configuration XML ont été appliquées
- Correctifs divers

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)
Introduite dans cette mise à jour : 
- Cette mise à jour permet à la fois Skype pour professionnels *et* équipes réunions prise en charge sur les périphériques de systèmes de salle.  Les équipes est désactivée par défaut une fois la mise à jour est appliquée.  Administrateurs peuvent permettent aux équipes localement dans Paramètres du périphérique, ou via un push xml à distance.

### <a name="311150-06182018"></a>3.1.115.0 (18/06/2018)
Introduite dans cette mise à jour : 
- Corriger les erreur adresse observé sur certains systèmes lors du démarrage de l’application.

### <a name="311130-06132018"></a>3.1.113.0 (13/06/2018)
Introduite dans cette mise à jour : 
- Modifications de l’activation de Microsoft plus flexible gérer les mises à jour Windows.
- Aucune modification à l’utilisateur final.

### <a name="311120-06052018"></a>3.1.112.0 (05/06/2018)
Introduite dans cette mise à jour : 
- Corriger les problèmes observés sur des appareils 2017 Surface Pro est connectés à deux affiche plan de salle et vidéo d’acquisition la réactivité de console adresse
- Vérification automatique pour vous assurer que le système est exécuté le script dernière mise en service.

### <a name="311040-04162018"></a>3.1.104.0 (16/04/2018)
Introduite dans cette mise à jour : 
- Correctif pour améliorer le clavier visuel (clavier visuel) comportement dans les systèmes fenêtre 10 Version 1709
- Améliorations apportées à préparer les mises à jour du système d’exploitation future

### <a name="311000-03162018"></a>3.1.100.0 (16/03/2018)
Introduite dans cette mise à jour :  
- Application de mises à jour pour améliorer la télémétrie.

### <a name="31990-03142018"></a>3.1.99.0 (14/03/2018)
Introduite dans cette mise à jour : 
- Correctifs un problème où réunion intermittente joindre les problèmes pouvant survenir.
- Résout un problème connu pour entraîner un blocage « périphériques ».

### <a name="31980--382018"></a>3.1.98.0 (2018/8/3)
Introduite dans cette mise à jour : 
- Correctifs de bogue/incident pour améliorer la stabilité
- Prise en charge pour la taille d’une variable de console
- Traitement audio périphérique déchargement (création de listes autorisées supports supplémentaires)
- Optimisations permettant aux professionnels de l’informatique créer des images personnalisables avec mise à jour de Windows 10 Version 1709 janvier et versions ultérieures.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (27/11/2017)
Introduite dans cette mise à jour :  
- Résout un problème avec la fonctionnalité « Commenter ».

### <a name="30150-1032017"></a>3.0.15.0 (10, 3/2017)
Introduite dans cette mise à jour : 
- Prise en charge de [Polycom MSR série](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) ancre matériel
- Prise en charge de la [Logitech Brio](https://www.logitech.com/en-us/product/brio)
- Résout un problème où affiche (console et salle de plan) ne pas passer en mode veille lorsqu’il n’existe aucune activité de la salle.


### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)
Introduite dans cette mise à jour :   
- S’exécute sur une tablette (2017) Surface Pro  
- Prend en charge la mise à jour du créateur de contenu d’entreprise 10 Windows (en anglais, build 1703)    
- Prise en charge des [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) ancre matériel    
- Codage OEM tel prise en charge pour les contrôles de l’environnement (Crestron)
    
La version 64 bits de Windows 10 entreprise anniversaire edition (en anglais, version 1607) n’est plus pris en charge à compter de salles d’équipes Microsoft version 3.0.12.0 (mise à jour 3). 

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017) 
Introduite dans cette mise à jour : 
- Résout les problèmes observés lorsque recherche fédérée utilisateurs via le champ de recherche des Participants. Antérieures à ce correctif, résultats de la recherche pour les utilisateurs fédérés externes non résolues correctement et renvoyé à la place des résultats incorrects. 

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017) 
Introduite dans cette mise à jour : 
- Double écran prise en charge (parité système hérité)   
- Themability (thèmes intégrés et la possibilité de définir le thème personnalisé) 
- Possibilité de faire part de vos commentaires pour les versions publiques     
- Amélioration de télémétrie autour de la fiabilité de participer à la réunion     
- Création de rapports de OMS supplémentaires     
- Possibilité pour l’administrateur informatique configurer les périphériques à distance  <!--  - Front-of-Room UX shows room details pre-meeting U2  --> 


### <a name="2020-03152017"></a>2.0.2.0 (15/03/2017)
Introduite dans cette mise à jour : 
- Sélection de l’utilisateur dans l’application de périphériques USB audio et vidéo de salle de réunion
- État de console intégrée salle création de rapports pour les clients qui utilisent Microsoft Operations Management Suite, maintenant Azure moniteur  

### <a name="release-to-market--1272016"></a>Publication sur le marché (12/7/2016)
**L’ou les composants :** 

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
- S’exécute sur des tablettes Surface Pro 4
 

<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Préparer votre environnement](srs-v2-prep.md)

[Prise en charge pour les salles d’équipes Microsoft versions actuelles de succursale](srs2-lifecycle-support.md)

[Problèmes connus pour les salles d’équipes Microsoft](known-issues.md)

[Planifier des équipes Microsoft salles](skype-room-systems-v2-0.md)

[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)
