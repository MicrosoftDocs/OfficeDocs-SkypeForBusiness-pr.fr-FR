---
title: Notes de publication pour Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Les administrateurs peuvent lire les notes de publication de l Salles Microsoft Teams, qui résisent les améliorations cumulatives apportées à Salles Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3350068646420dcd9a53b1a56c6a144783956e44
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504091"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Notes de publication pour Salles Microsoft Teams

Cet article décrit les améliorations cumulatives apportées à Salles Microsoft Teams.

Il existe deux types de mises à jour salles Teams : salles Teams mises à jour d’application et Teams client web. 

salles Teams mises à jour de l’application se produisent via le Microsoft Store ou par le biais [d’une mise à jour manuelle](manual-update.md). Cette mise à jour de l’application Windows plateforme universelle (UWP) installée localement sur l’appareil.

Teams mises à jour client web se produisent via les services Teams de distribution d’application web. Il s’agit d’un service cloud qui ne nécessite pas de mise à jour de l’application UWP locale installée sur l’appareil.

Pour plus d’informations sur la façon d Teams mises à jour, voir [Teams processus de mise à jour](../teams-client-update.md)

salles Teams est régi par la politique de cycle de vie moderne. Pour [plus d Teams, voir le processus de mise à jour](../teams-client-update.md#servicing-agreement).

## <a name="version-history"></a>Historique des versions

|Publication |Publié sur <br/> Microsoft Store |
|--- |--- |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Teams Web-Client publication | Décembre 2021 |
|Teams Web-Client publication | Octobre 2021 |
|4.10.10.0 |10/1/2021 |
|4.9.12.0 |07/28/2021 |
|4.8.31.0 |05/12/2021 |
|4.8.25.0 |04/22/2021 |
|4.8.19.0 |04/06/2021 |
|4.7.19.0 |02/03/2021 |
|4.7.15.0 |12/11/2020 |
|4.6.23.0 |10/19/2020 |
|4.6.20.0 |09/30/2020 |
|4.5.37.0 |08/14/2020 |
|4.5.35.0 |07/23/2020 |
|4.4.63.0 |06/25/2020 |
|4.4.41.0 |05/06/2020 |
|4.4.25.0 |03/31/2020 |
|4.3.42.0 |03/02/2020 |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8) |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Salles Microsoft Teams présentation des fonctionnalités et résolution des problèmes

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introduit dans cette mise à jour :
- Correctif pour l’encadrement de la caméra qui permet d’améliorer tout le contenu en vue Caméra.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introduit dans cette mise à jour :
- Disposition Ligne avant (aperçu) pour MTR sur Windows <sup>1</sup> 
- Paramètre Administrateur de définir la disposition ligne avant comme disposition par défaut  
- Mise à jour de l’application Conférence maintenant et appel Teams uniquement, Teams modes client <sup>par défaut1,2</sup>
- Basculer entre plusieurs caméras vidéo dans Teams <sup>réunions1</sup> 
- Paramètre de caméra vidéo par défaut 
- Cortana mise à jour de l’icône Appuyer-pour-parler sur la console MTR 
- Azure AD Premium’inclusion d’une licence dans Room Standard et Premium références S SKUS 
- AAD d’accès conditionnel3<sup></sup> 
- Cortana activation vocale activée par défaut dans OOBE
- Prise en charge des contrôles PTZ <sup>distants4</sup>

> <sup>1 Ces</sup> fonctionnalités sont en cours de déploiement à l’Teams client web et seront déployer au cours des prochaines semaines. Pour plus [d’informations, voir Teams mises à](../teams-client-update.md) jour.
> 
> <sup>2</sup> salles Teams sur Windows s’exécutant en Microsoft Teams uniquement ou Skype Entreprise et Microsoft Teams (par défaut) sont mises à jour avec les nouvelles expériences De réunion et d’appel, mais les autres modes ne sont pas impactés par cette mise à jour.
> 
> <sup>3</sup> En savoir plus sur la configuration de stratégies d’accès AAD [conditionnelle](../rooms/rooms-authentication.md#azure-ad-conditional-access) pour les salles Teams.
> 
> <sup>4</sup> Cette fonctionnalité nécessite que les administrateurs informatiques configurent Teams de bureau des contrôles PTZ distants du client.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>salles Teams mise à jour du client web (décembre 2021)

Introduit dans cette mise à jour :
- La disposition vidéo fractionner sur deux fronts de salle s’affiche lorsque le contenu n’est pas partagé

### <a name="teams-rooms-web-client-update-october-2021"></a>salles Teams mise à jour du client web (octobre 2021)

Introduit dans cette mise à jour :
- Contrôle de liste unifiée avec le client de bureau Teams avec regroupement de réunions structurées, options et contrôles de réunion pour les présentateurs/participants, lever l’ordre de tri des main et la possibilité d’inviter des utilisateurs à partir de la conversation ou de l’invitation à une réunion directement à partir de la liste 
- Alignement des contrôles d’appel à barres universelles avec le client de bureau dans les contrôles d’appel de réunion, le bouton Disposition et les informations de statut de réunion
- Prise en charge de la galerie dynamique pour les affichages à une et à deux face des salles
- Unified layout picker for front of room layout option consolidated
- Mettre à la une ou épingler plusieurs participants dans Teams réunions
- Prise en charge des réunions de grande taille avec contrôle du présentateur/participants accessible en appuyant sur la liste des participants
- Possibilité de verrouiller une réunion pour des réunions où la salle est organisateur, ainsi que la connaissance d’une réunion verrouillée
- Prise en charge de la consommation en mode Présentateur (météo) lorsqu’un utilisateur distant partage du contenu avec l’option mode Présentateur
- Prise en charge des réactions Teams réunions 


> [!NOTE]
> Les mises à jour du client web sont disponibles pour tous les salles Teams les versions 4.10 et 4.9 de l’application. Les administrateurs pourront bientôt s’inscrire salles Teams programme de prévisualisation publique afin d’obtenir rapidement un aperçu des fonctionnalités du client Web.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introduit dans cette mise à jour :
- La fonctionnalité De salle à distance permet aux utilisateurs de contrôler les fonctionnalités de base de la salle à l’Teams sur leur appareil mobile *
- Logitech scribe content camera support for BIP button for sharing into meeting
- Les bulles de conversation fournissent des notifications pour les discussions de réunion afin d’attirer l’attention sur ce qui est dit à l’aide de la conversation de réunion *
- La prise en charge des grandes galerie et du mode Ensemble est désormais disponible dans Cloud de la communauté du secteur public High
- Nouvelles compétences ajoutées à Cortana, Ajouter une personne par nom à la réunion et Appeler par nom 
- Cortana Push to Talk est activé par défaut sur tous les appareils. Pour en savoir plus, [consultez Cortana’assistance vocale dans Teams](../cortana-in-teams.md).

> [!NOTE]
> Prise en charge 19H1 non prise en charge. La version min du système d’exploitation prise en charge par 4.10 est de 19H2.

> [!NOTE]
> *Ces fonctionnalités sont déployées à l’aide Teams service et fonctionneront avec toutes les versions d’application supérieures à 4,9.

> [!NOTE]
> Pour participer à la réunion programmée à partir de Teams Mobile app et MTR-W, recherchez le compte de la salle dans la liste de l’application Teams Mobile et appuyez sur le menu « Contrôler cette salle » et vous pouvez contrôler les contrôles d’appel à partir de l’application.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introduit dans cette mise à jour :
- Microsoft Teams seul mode est désormais disponible dans les paramètres de l’application. Vous n’avez donc plus besoin de configurer Skype Entreprise compte client. Dans ce mode, les appareils connectés au Teams seul mode rejoignent Skype Entreprise réunions en tant qu’utilisateur invité.
- Correctif pour l’audio HDMI qui réduit le volume des appels. La fonctionnalité audio HDMI est automatiquement activée pour tous les appareils avec l’application build 4.9.12.0.

> [!NOTE]
> Une Skype Entreprise en fin de vie, il est recommandé de mettre à Teams mode uniquement.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introduit dans cette mise à jour :
- Windows 10 20H2 support 

> [!NOTE]
> Crestron UC-Engine (date de la version BIOS contenant « KYSKLi ») salles Teams des problèmes de compatibilité et des pilotes mis à jour seront fournis par les système CENTREM dans un futur proche. Windows 10 20H2 ne sera pas proposé sur ces appareils. Pour plus d’informations sur Windows prise en charge des versions, voir [Windows 10 prise en charge de la publication](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introduit dans cette mise à jour :
- Résoudre un problème dans lequel les informations de salle sur salles Teams consoles d’urgence n’indiquent pas les comptes de salle masqués dans la liste d’adresses globale (LA GAL)

> [!NOTE]
> Les clients GCCH peuvent télécharger le package de mise à niveau à partir de la mise à [jour manuelle d’Salles Microsoft Teams appareil](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introduit dans cette mise à jour :
- Cloud de la communauté du secteur public de la prise en charge des hautes valeurs (GCCH) pour salles Teams. Les clients GCCH disposent d’salles Teams existants peuvent télécharger la version 4.8.19.0 à partir de la mise à jour manuelle [d’Salles Microsoft Teams appareil](manual-update.md)
- Participer à des réunions de zoom avec une meilleure qualité vidéo (prise en charge de 720p) et recevoir la galerie de vidéos des participants
- Skype Entreprise bannière d’échec de la inscription supprimée pour Teams mode par défaut. Ce changement prend en charge la suppression d’Skype Entreprise infrastructure
- Teams l’examen des liens permettant de participer à des réunions traite désormais les liens vers la protection avancée contre les menaces Microsoft Defender Coffre pour permettre la jointation transparente des Teams externes
- Correctif pour les problèmes de mise à l’échelle de contenu Skype Entreprise les réunions lorsque le PC de la sharer dispose d’un jeu d’ID DPI personnalisé Windows
- Correctifs en matière de qualité et de fiabilité

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introduit dans cette mise à jour :
- Correctifs en matière de qualité et de fiabilité

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introduit dans cette mise à jour :

- Partager le système audio HDMI pour les participants à Teams réunion
- Cortana de voix (aperçu)
- Empêchez la désmutation en fonction des autorisations audio lorsque Teams salle rejoint en tant que participant. Pour plus d’informations, [voir Gérer les autorisations audio des participants dans Teams réunions](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Mettre en valeur la vidéo d’une personne à partir Teams console de salle et utiliser les vidéos à la une sur les écrans des salles

> [!NOTE]
> Cortana de voix sont disponibles pour certains périphériques audio pour les locataires situés aux États-Unis. D’autres pays ou régions seront ajoutés ultérieurement. Pour plus d’informations, [voir Cortana’assistance vocale dans Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introduit dans cette mise à jour :

- Correctif pour le demi-écran blanc lors de l’facturation du clavier à l’écran dans Teams réunion

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introduit dans cette mise à jour :

- Afficher plus de vidéos avec la galerie de vidéos 3x3 devant les écrans des salles  
- Démarrer les sous-titres locaux en direct de MTR
- Participer à des réunions de zoom à partir salles Teams avec une rejoindre directement l’invité (prévisualisation)

> [!NOTE]
> La galerie de vidéos 3x3 et les sous-titres en direct locaux sont remis par le biais du service Microsoft Teams’équipe. Ces fonctionnalités sont disponibles pour tous les salles Teams’application avec l’application 4.5.37.0 et versions supérieures.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introduit dans cette mise à jour :

- Réunions coordonnées entre Microsoft Teams et Surface Hub 2S
- Correctif pour l Skype échec de la Windows 10 de la mise à jour [KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) ou de la mise à jour Windows 10 [KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) est installé

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introduit dans cette mise à jour :

- Participer à des réunions Cisco WebEx à partir salles Teams avec l’accès invité direct
- Teams’enablement du Centre d’administration et l’inscription automatique
- Windows 10 prise en charge de la version 1909
- Basculer vers la disposition de la galerie de vidéos même lorsque du contenu est présent
- Prise en charge des mains levées virtuelles pour le participant et commandes pour le présentateur
- Paramètre de volume ajustable par défaut pour la conférence et le haut-parleur par défaut
- Rechercher et appeler des utilisateurs fédérés (client) depuis Teams Room

> [!IMPORTANT]
> La version 4.5 est la dernière version prise en charge Windows 10 version 1803. Les versions futures ne seront pas proposées aux systèmes Windows 10 version 1803. Pour plus d’informations sur Windows prise en charge des versions, voir [Windows 10 prise en charge de la publication](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introduit dans cette mise à jour :

- Correctifs en matière de qualité et de fiabilité
- Correctif pour le problème « l’application ne se lance pas après la mise à jour vers 4.4.41.0 »

> [!NOTE]
> Si votre appareil ne se met pas à jour automatiquement vers la version 4.4.63.0, suivez les étapes de l’application Salles Microsoft Teams ne démarre pas après la mise à jour vers la [version 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) pour résoudre le problème.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introduit dans cette mise à jour :

- Correctifs de fiabilité pour le démarrage de l’application Windows 10 Kiosk

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introduit dans cette mise à jour :

- Prise en charge de l’authentification moderne pour Exchange et Skype Entreprise
- Prise en charge des appels d’urgence Teams d’urgence dynamiques (composants de service requis et Teams des anneaux clients)
- Possibilité de désactiver le contenu en double hors réunion pour les salles à affichage double à l’aide de XML
- Écran de d’accueil de l’application
- Notifications sur le logiciel Open Source (OSS) dans les paramètres de l’appareil

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introduit dans cette mise à jour :

- Mises à jour de stratégie pour « mises Windows jour pour les entreprises »
- Correctif pour les événements d’appareil signalant une erreur dans le moniteur Azure

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introduit dans cette mise à jour :

- Correctif pour un problème de resizing/scintillement de fenêtre visible dans certaines configurations
- Suppression du traitement du calendrier pour les réunions tierces
- Cortana statut supprimé

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introduit dans cette mise à jour :

- Réponse automatique aux appels de proximité et paramètre d’administration pour contrôler ce
- Actualisation de l Paramètres de l’interface utilisateur de l’appareil avec l’ajout de la configuration de l’appareil sous l’onglet À propos
- Contrôle de salle de retour à l’écran principal
- Salle de réunion référence SKU disponible dans Cloud de la communauté du secteur public
- Prise en charge de la caméra de Surface Pro système basé sur un système (build d’application minimale requise : 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introduit dans cette mise à jour :

- Windows 10 1903. Windows 10 mise à jour 1903 est proposée dans quelques jours après la mise à jour de l’application
- Les correctifs pour le clavier à l’écran ne s’affichent pas correctement

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introduit dans cette mise à jour :

- Nouvelle fonctionnalité de caméra de contenu qui permet aux utilisateurs d’inclure intelligemment un tableau blanc traditionnel dans leur Teams réunion
- Améliorations supplémentaires apportées à l’interface utilisateur de la console pour réduire l’encombrement et la Paramètres dans une nouvelle barre latérale accessible via La suite sur la console
- Bouton Partage d’état désactivé si le câble de contenu local n’est pas connecté ou si une caméra de contenu n’est pas connectée
- Correction d’un problème avec le clavier tactile dans lequel il ne parait pas s’affiche la première fois uniquement après un redémarrage du système MTR
- Correctifs en matière de qualité et de fiabilité

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introduit dans cette mise à jour :

- Skype’application du store Room System a été renommée en « Salles Microsoft Teams »
- Salles Microsoft Teams’interface utilisateur de la console réaligne sur Microsoft Teams
- Mise à jour du thème : ne garder une image d’arrière-plan personnalisée que devant les écrans de salle, tout en rendant l’arrière-plan de la console neutre pour garantir que les contrôles de l’interface utilisateur de la console répondent au contraste de couleurs — conditions d’accessibilité
- Barre universelle pour les contrôles d’appel en réunion pour les Teams/réunions afin d’offrir une expérience cohérente avec les clients Microsoft Teams PC/Web/<sup>Mobile1</sup>
- Évaluation de la qualité des commentaires après Teams/<sup>réunions1</sup>
- Recevoir/afficher des Microsoft Whiteboard au Salles Microsoft Teams avant de la salle lorsqu’il est partagé à partir d’un PC/Web/mobile Teams client <sup>12</sup> <sup></sup>
- Prise en charge supprimée pour Windows 10 mises à niveau vers la version 1809 en raison de problèmes de compatibilité avec Salles Microsoft Teams client. Windows 10 prise en charge de la version 19H1 sera ajoutée dans les prochaines versions

<sup>1 Microsoft Teams</sup> de service à l’aide Teams anneaux. Cette fonctionnalité peut être disponible plus tôt ou plus tard que la mise à jour du client 4.0.105.0

<sup>2 Nécessite</sup> que les administrateurs informatiques les Microsoft Whiteboard. Par ailleurs, si vous avez un écran tactile avant de la salle, vous devez étalonner plusieurs écrans tactiles à l’aide des paramètres de Windows avec connexion de l’administrateur de l’appareil pour commencer à utiliser Microsoft Whiteboard pour la collaboration à partir d’une salle affichée partagée dans une réunion Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introduit dans cette mise à jour :

- Corrige un problème avec la fonctionnalité « Donner des commentaires »
- Optimisations en préparation de la prochaine mise à niveau Salles Microsoft Teams appareil à Windows 10 version 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introduit dans cette mise à jour :

- Correctif pour le bogue « bloquer au démarrage de l’application » qui a affecté les appareils sur Windows 10 build RS2.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introduit dans cette mise à jour :

- Clavier DTMF pour les Microsoft Teams P2P et les appels PSTN. Pour définir Microsoft Teams client d’appel par défaut, les administrateurs doivent définir IsTeamsDefaultClient sur true
- Épinglez la vidéo entrante d’un participant distant en plein écran devant l’affichage de la salle. Utiliser la commande « Épingler » depuis la liste des participants de la console
- Améliorations apportées aux notifications de salle d’attente avec l’ajout de la notification Avant salle
- Icône de l’affichage avant de la salle supprimée lorsque Bluetooth balise n’est pas activée sur Salles Microsoft Teams appareil
- Correctif pour le problème de contrôle du volume dans Teams réunions

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introduit dans cette mise à jour :

- Afficher du contenu au premier plan (FoR) sur des systèmes de salle à écran double
- Améliorations de l’interface utilisateur au premier plan et au niveau des salles
- Prise en charge côté client TLS 1.2. Pour les clients locaux, l’activation de la communication sur TLS 1.2 pour Salles Microsoft Teams nécessite la mise à jour cumulative Skype Entreprise Server 2015 9 (CU9) ou la mise à jour cumulative Skype Entreprise Server 2019 cumulative 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introduit dans cette mise à jour :

- Prise en charge de l’affichage double (avant de la salle) Teams réunions

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introduit dans cette mise à jour :

- Correctifs en matière de qualité et de fiabilité

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introduit dans cette mise à jour :

- Modifications de code nécessaires pour préparer l’Salles Microsoft Teams pour une mise à Windows 10 la version 1803
- Résoudre le problème de mise en forme des E/SLA localisées (en particulier en norvégien) qui empêche l’avancement au-delà de la fenêtre de configuration OOBE de l’UELA
- Modifications de code requises pour exécuter Salles Microsoft Teams application sur les systèmes de salle Lync hérités. En savoir plus [ici](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introduit dans cette mise à jour :

- Correctif pour l’application Crestron qui ne se lance pas, normalement accessible lorsque le bouton d’application sur un appareil Crestron SR est enfoncé. Salles Microsoft Teams redémarrage de l’application est requis après l’installation de 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introduit dans cette mise à jour :

- Améliorations de la fonctionnalité « Signaler un problème » en mode Teams (équivalent à « Faire des commentaires » en mode Skype Entreprise’écran)
- Activer la possibilité de passer du mode Teams au mode Skype Entreprise pour les appels SIP
- Améliorations apportées à l’accessibilité (Narrateur, Loupe)
- Redémarrage automatique de l’application requis après application des modifications de mise en service XML
- Correctifs divers

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introduit dans cette mise à jour :

- Cette mise à jour permet la prise Skype Entreprise *et* Teams prise en charge des réunions sur les appareils des systèmes de salle. Teams est désactivée par défaut une fois la mise à jour appliquée. Les administrateurs peuvent activer Teams localement dans les paramètres de l’appareil ou via une push XML distante.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introduit dans cette mise à jour :

- Corrigez l’erreur de correction observée sur certains systèmes au lancement de l’application.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introduit dans cette mise à jour :

- Modifications permettant à Microsoft de gérer plus flexibly Windows mises à jour.
- Aucune modification de l’expérience utilisateur final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introduit dans cette mise à jour :

- Correction pour corriger les problèmes de réactivité de la console observés sur Surface Pro appareils 2017 connectés à deux écrans avant et à la vidéo la plus rapide
- Vérification automatique pour vérifier que le système exécute le script de mise en service le plus récent

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introduit dans cette mise à jour :

- Correctif pour améliorer le comportement du clavier d’exploitation (clavier à l’écran) dans les systèmes Window 10 version 1709
- Améliorations pour préparer les futures mises à jour du système d’exploitation

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introduit dans cette mise à jour :

- Application mise à jour pour améliorer la télémétrie

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introduit dans cette mise à jour :

- Résout un problème pour lequel des problèmes de joint lors de réunions intermittentes peuvent se produire
- Corrige un problème connu pour entraîner un « raccrocher » d’appareil

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introduit dans cette mise à jour :

- Correction de bogues/incidents pour améliorer la stabilité
- Prise en charge de la console de taille variable
- Traitement audio périphérique avec rechargement (liste d’informations sur les médias supplémentaires)
- Optimisations qui permettent aux professionnels de l’informatique de créer des images de do-it-yourself avec Windows 10 mise à jour de janvier 1709 et ultérieures.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introduit dans cette mise à jour :

- Résout un problème avec la fonctionnalité « Donner des commentaires ».

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introduit dans cette mise à jour :

- Prise en charge du [matériel de la station d’accueil Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Prise en charge [de l’entreprise LogitechS](https://www.logitech.com/product/brio)
- Résout un problème dans lequel les écrans (console et face avant de la salle) ne parviennent pas à entrer en mode veille lorsqu’il n’y a aucune activité dans la salle

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introduit dans cette mise à jour :

- S’exécute sur Surface Pro tablette (2017)
- Prend Windows 10 Entreprise jour de Créateur de projets (langue anglaise, build 1703)
- Prise en charge [du matériel de la station d’accueil de Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Prise en charge OEM des contrôles d’environnement (Crestron)

La version 64 bits de l’édition anniversaire de Windows 10 Entreprise (anglais, version 1607) n’est plus prise en charge à partir de la version Salles Microsoft Teams 3.0.12.0 (mise à jour 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introduit dans cette mise à jour :

- Résout les problèmes observés lors de la recherche d’utilisateurs fédérés via le champ de recherche Participants. Avant ce correctif, les résultats de recherche pour les utilisateurs fédérés externes n’ont peut-être pas été résolus correctement et ont renvoyé des résultats incorrects.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introduit dans cette mise à jour :

- Dual-Screen prise en charge (pour la parité du système héritée)
- Thèmes (thèmes intégrés et possibilité de définir un thème personnalisé)
- Possibilité d’offrir des commentaires pour les builds publiques
- Télémétrie améliorée autour de la fiabilité des réunions
- Amélioration de la rapports CES
- Possibilité pour l’administrateur informatique de configurer des appareils à distance

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introduit dans cette mise à jour :

- Sélection de l’utilisateur dans l’application des périphériques USB audio et vidéo de salle de réunion
- Rapports d’état intégrés de la console de salle pour les clients utilisant la suite Microsoft Operations Management, désormais Azure Monitor

### <a name="release-to-market-1272016"></a>Publication sur Le Marché (07/12/2016)

**Fonctionnalité(s) :**

 **Conçue pour Skype Entreprise**

- Participation aux réunions Skype en un clic
- Réunion Skype expérience optimisée pour les salles avec une vidéo HD à remplissage d’écran et un audio large bande HD
- Tous les participants peuvent se connecter à la réunion Skype à l’aide du dispositif de leur choix où qu’ils soient
- Invitez des contacts via votre annuaire qui vous indiquera leur disponibilité, ou via un appel téléphonique
- Prise en charge de la conférence PSTN Skype Entreprise et de la fonction d’appel PSTN pour remplacer le téléphone de conférence autonome de votre salle de réunion

 **Conversion d’un espace de réunion**

- Optimisation de l’application de réunion Skype dédiée pour le centre du contrôleur tactile et large écran d’affichage
- Réutiliser les investissements existants devant l’affichage ou les projecteurs de la salle
- Fonctionne avec tout type d’espace de réunion, allant des petites salles aux vastes espaces de conférence
- Des périphériques audio et vidéo Skype Entreprise certifiés sont disponibles pour différentes tailles d’espace
- Ingest câblé intégré pour projeter le partage du Bureau sur la salle et sur la Réunion Skype

 **Facilité de déploiement, simplicité de gestion**

- Appliance toujours en veille qui détecte automatiquement l’écran lorsqu’il détecte des personnes dans la pièce
- Déploiement simple et mise à jour de l’application de réunion Skype UWP (plateforme Windows universelle)
- L’AppLocker de Windows verrouille l’appareil sur l’application de réunion Skype
- Surveiller et gérer en tant qu’appareil Windows 10 Entreprise via Intune et Configuration Manager (MDM)
- Fiabilité pour l’entreprise
- Effort de formation minime des utilisateurs finaux, grâce à l’interface utilisateur Skype familière
- S’exécute sur Surface Pro 4 tablette

<a name="See"> </a>
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Préparer votre environnement](rooms-prep.md)

[Prise en charge Salles Microsoft Teams versions de la branche actuelle](rooms-lifecycle-support.md)

[Problèmes connus](known-issues.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)
