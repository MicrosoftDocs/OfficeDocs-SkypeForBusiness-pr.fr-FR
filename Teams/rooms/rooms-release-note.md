---
title: Notes de publication pour Salles Microsoft Teams (Windows)
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
description: Administration pouvez lire les notes de publication de Salles Microsoft Teams, qui répertorient les améliorations cumulatives apportées à Salles Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03a23ecb47fb0efca19ce3a7085a1fcc41b80dc3
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674196"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Notes de publication pour Salles Microsoft Teams

Cet article décrit les améliorations cumulatives apportées aux Salles Microsoft Teams.

Il existe deux types de mises à jour pour salles Teams : salles Teams mises à jour d’application et Teams web-client. 

salles Teams mises à jour de l’application se produisent via le Microsoft Store ou via [une mise à jour manuelle](manual-update.md). Cela met à jour l’application plateforme Windows universelle (UWP) installée localement sur l’appareil.

Teams mises à jour du client web se produisent via les services de distribution d’applications web Teams. Il s’agit d’un service cloud qui ne nécessite pas de mise à jour de l’application UWP locale installée sur l’appareil.

Pour plus d’informations sur la façon dont les mises à jour Teams, consultez [Teams processus de mise à jour](../teams-client-update.md)

salles Teams est régie par la politique de cycle de vie moderne. Pour plus d’informations[, consultez Teams processus de mise à jour](../teams-client-update.md#servicing-agreement).

## <a name="version-history"></a>Historique des versions

|Libération |Publié sur <br/> Microsoft Store |
|--- |--- |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|version Teams Web-Client | Décembre 2021 |
|version Teams Web-Client | Octobre 2021 |
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

### <a name="4121260-4272022"></a>4.12.126.0 (4/27/2022)

Introduit dans cette mise à jour :
- Les administrateurs informatiques peuvent inscrire un appareil Teams salles pour recevoir des fonctionnalités en préversion publique via le paramètre XML. Une fois inscrit, l’appareil commence à recevoir les fonctionnalités bêta. Toutes les fonctionnalités qui passent aux tests bêta sont annoncées à [Microsoft Teams préversion publique - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1,2</sup>  
- L’administrateur informatique peut définir la résolution et la mise à l’échelle de l’affichage avant de la salle à distance via les paramètres XML<sup>2</sup>
- L’administrateur informatique peut désactiver la suppression du bruit Microsoft via le paramètre XML<sup>3</sup> 
- L’administrateur informatique peut remplacer le nettoyage du dossier de téléchargement sur l’appareil via le paramètre de clé de Registre<sup>4</sup>
- Permettre aux utilisateurs de participer à Teams réunion hébergée sur un autre cloud (c’est-à-dire, le client GCCH peut participer à Teams réunions hébergées sur le cloud commercial et inversement) 
- Teams salles bloquent désormais le lancement du navigateur edge à partir d’URL dans PowerPoint Live en tant que mesure de sécurité supplémentaire pour Teams salles avec affichages tactiles 
- L’expérience De réunion maintenant est améliorée pour ajouter des instructions permettant aux utilisateurs d’inviter des utilisateurs à la salle 
- Prise en charge de Windows 10 version des fonctionnalités 21H2 pour les salles Teams   
- Nouveau point d’entrée Cortana sur l’écran d’accueil, le bouton Partager/présenter est de retour 

> <sup>1</sup> Les instructions pour l’inscription de la préversion publique MTR Windows appareils sont disponibles [ici](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2</sup> La résolution et la mise à l’échelle de l’affichage avant de la salle à distance via XML sont disponibles [ici](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)
>
> <sup>3</sup> À ce stade, seul le paramètre administrateur est en cours de publication. Le contrôle utilisateur et l’activation de la suppression du bruit suivront la publication de la version 4.12 en mai 2022. 
>
> <sup>4</sup> Les instructions de nettoyage de l’appareil sont disponibles [ici](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)
> 
> 
> [!NOTE]
> Windows 10 mise à jour des fonctionnalités 21H2 sera mise à jour après 7 jours d’installation de l’application, ou les administrateurs peuvent utiliser la mise à jour manuelle à la place pour s’installer plus rapidement. Salles Microsoft Teams version 4.12 de l’application avec ces modifications, commencera à être déployée en avril 2022 et terminera le déploiement dans 2 à 3 semaines. Les mises à jour de l’application sont remises via Windows magasin et l’application est installée automatiquement. Cette opération est déployée sur Salles Microsoft Teams sur Windows uniquement. Ce que vous devez faire pour vous préparer : vous souhaiterez peut-être informer vos utilisateurs de cette expérience mise à jour et mettre à jour votre formation et votre documentation selon les besoins.

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introduit dans cette mise à jour :
- Correctif de bogue pour le cadrage de caméra qui améliorera tout le contenu en mode caméra.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introduit dans cette mise à jour :
- Disposition de la ligne avant (préversion) pour MTR sur Windows <sup>1</sup> 
- Administration paramètre pour définir la disposition de la ligne frontale comme valeur par défaut  
- Rencontrez maintenant et appelez la mise à jour de l’application pour Teams uniquement, Teams modes client par défaut<sup>1,2</sup>
- Basculer entre plusieurs caméras vidéo dans Teams réunions<sup>1</sup> 
- Paramètre de caméra vidéo par défaut 
- Cortana mise à jour de l’icône de transmission (push-to-talk) sur la console MTR 
- Azure AD Premium 1 inclusion de licence dans Room Standard et les références SKU Premium 
- Les stratégies d’accès conditionnel AAD prennent en charge<sup>3</sup> 
- Cortana activation vocale activée par défaut dans OOBE
- Les contrôles PTZ distants prennent<sup>en charge 4</sup>

> <sup>1</sup> Ces fonctionnalités sont déployées à l’aide de Teams client web et seront déployées dans les prochaines semaines. Pour plus d’informations, consultez [Teams mises à jour](../teams-client-update.md).
> 
> <sup>2</sup> salles Teams sur Windows en cours d’exécution dans Microsoft Teams uniquement ou Skype Entreprise et Microsoft Teams (par défaut) sont mises à jour avec de nouvelles expériences de réunion et d’appel, mais d’autres modes ne sont pas affectés par cette mise à jour.
> 
> <sup>3</sup> Consultez les détails supplémentaires sur la configuration des stratégies [d’accès conditionnel AAD](../rooms/rooms-authentication.md#azure-ad-conditional-access) pour salles Teams.
> 
> <sup>4</sup> Cette fonctionnalité nécessite que les administrateurs informatiques configurent Teams application de contrôles PTZ à distance client de bureau.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>mise à jour du client web salles Teams (décembre 2021)

Introduit dans cette mise à jour :
- Fractionner la disposition vidéo sur deux écrans front of Room lorsque le contenu n’est pas partagé

### <a name="teams-rooms-web-client-update-october-2021"></a>mise à jour du client web salles Teams (octobre 2021)

Introduit dans cette mise à jour :
- Contrôle de liste unifiée avec Teams client de bureau avec regroupement de réunions structurées, options de réunion et contrôles pour les présentateurs/participants, augmenter l’ordre de tri des mains et la possibilité d’inviter des utilisateurs à partir d’une conversation ou d’une invitation à une réunion directement à partir de la liste 
- Alignement des contrôles d’appel de barre universelle avec le client de bureau dans les contrôles d’appel de réunion, le bouton Disposition et les informations d’état de la réunion
- Prise en charge dynamique de la galerie pour les affichages d’une seule et double face de la salle
- Sélecteur de disposition unifié pour l’option de disposition avant de la salle consolidée
- Mettre à la une ou épingler plusieurs participants aux réunions Teams
- Prise en charge des réunions volumineuses avec les contrôles présentateur/participants accessibles en appuyant sur le participant à partir de la liste
- Possibilité de verrouiller une réunion pour les réunions où la salle est organisatrice, ainsi que la sensibilisation à la réunion verrouillée
- Prise en charge de la consommation en mode présentateur (météo) lorsqu’un utilisateur distant partage du contenu avec l’option d’affichage présentateur
- Prise en charge des réactions dans les réunions Teams 

> [!NOTE]
> Les mises à jour du client web sont disponibles pour tous les salles Teams avec les versions d’application 4.10 et 4.9. Les administrateurs pourront s’inscrire à salles Teams programme de préversion publique pour bénéficier prochainement d’un aperçu des fonctionnalités du client web.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introduit dans cette mise à jour :
- La salle distante permet aux utilisateurs de contrôler les fonctionnalités de base de la salle à l’aide de Teams sur leur mobile *
- Prise en charge de la caméra de contenu logitech pour le bouton BLE pour le partage dans la réunion
- Les bulles de conversation fournissent des notifications pour la conversation de réunion pour attirer l’attention sur ce qui est dit à l’aide de la conversation de réunion *
- La grande galerie et la prise en charge du mode Ensemble sont désormais disponibles dans Cloud de la communauté du secteur public High
- Nouvelles compétences ajoutées à Cortana, Ajouter une personne par nom à la réunion et Appeler par nom 
- Cortana Push to Talk est activé par défaut sur tous les appareils. Pour en savoir plus, consultez [Cortana assistance vocale dans Teams](../cortana-in-teams.md).

> [!NOTE]
> Prise en charge déconseillée de 19H1. La version minimale du système d’exploitation prise en charge par la version 4.10 est 19H2.

> [!NOTE]
> *Ces fonctionnalités sont déployées à l’aide Teams service et fonctionnent avec toutes les versions d’application supérieures à 4.9.

> [!NOTE]
> Pour participer à la réunion planifiée à partir de Teams’application mobile et MTR-W, recherchez le compte de salle dans la liste de présence dans l’application Teams Mobile, appuyez sur le menu « Contrôler cette salle » et vous pouvez contrôler les contrôles d’appel à partir de l’application.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introduit dans cette mise à jour :
- Microsoft Teams seul mode est désormais disponible dans les paramètres de l’application, vous n’avez donc plus besoin de configurer un compte Skype Entreprise. Dans ce mode, les appareils connectés à Teams seul mode rejoignent Skype Entreprise réunions en tant qu’utilisateur invité.
- Correction de l’audio HDMI à l’origine d’un volume d’appels inférieur. La fonctionnalité audio HDMI est automatiquement activée pour tous les appareils avec la build d’application 4.9.12.0.

> [!NOTE]
> Avec Skype Entreprise fin de vie, il est recommandé de mettre à jour vers Teams mode uniquement.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introduit dans cette mise à jour :
- prise en charge de Windows 10 20H2 

> [!NOTE]
> Crestron UC-Engine (date de version du BIOS contenant « KYSKLi ») salles Teams présentent des problèmes de compatibilité et les pilotes mis à jour seront bientôt fournis par les OEM système. Windows 10 20H2 ne sera pas proposé à ces appareils. Pour plus d’informations sur Windows prise en charge des versions, consultez [Windows 10 prise en charge des versions](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introduit dans cette mise à jour :
- Résolution d’un problème où les informations de salle sur salles Teams consoles n’apparaissent pas pour les comptes de salle masqués dans la liste d’adresses globale (GAL)

> [!NOTE]
> Les clients GCCH peuvent télécharger le package de mise à niveau à partir de [la mise à jour manuelle d’un appareil Salles Microsoft Teams](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introduit dans cette mise à jour :
- prise en charge de Cloud de la communauté du secteur public High (GCCH) pour salles Teams. Les clients GCCH disposant d’appareils salles Teams existants peuvent télécharger la version 4.8.19.0 à partir de [la mise à jour manuelle d’un appareil Salles Microsoft Teams](manual-update.md)
- Participer à des réunions Zoom avec une meilleure qualité vidéo (support 720p) et recevoir la galerie vidéo des participants
- Skype Entreprise bannière d’échec de connexion supprimée pour Teams mode par défaut. Ce changement prend en charge la suppression de l’infrastructure Skype Entreprise par les organisations
- Teams l’analyse des liens de jointure des réunions gère désormais les liens Coffre Microsoft Defender Advanced Threat Protection pour permettre la jonction à des Teams externes en toute transparence
- Résolution du problème de mise à l’échelle de contenu partagé dans Skype Entreprise réunions lorsque le PC du partageur a un ppp personnalisé défini dans Windows
- Correctifs de qualité et de fiabilité

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introduit dans cette mise à jour :
- Correctifs de qualité et de fiabilité

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introduit dans cette mise à jour :

- Partager l’audio HDMI aux participants à Teams réunion
- Cortana compétences vocales (préversion)
- Empêchez le son en fonction des autorisations audio lorsque salles Teams joint en tant que participant. Pour plus d’informations, consultez [Gérer les autorisations audio des participants dans Teams Réunions](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Mettre en évidence la vidéo d’une personne à partir de Teams console Room et utiliser la vidéo à la une sur les écrans de salle

> [!NOTE]
> Cortana compétences vocales sont disponibles pour sélectionner des périphériques audio pour les locataires situés dans le États-Unis. D’autres pays ou régions seront ajoutés à l’avenir. Pour plus d’informations, consultez [Cortana assistance vocale dans Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introduit dans cette mise à jour :

- Correction du demi-écran blanc lors de l’appel du clavier visuel dans Teams réunion

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introduit dans cette mise à jour :

- Voir d’autres vidéos avec galerie de vidéos 3x3 devant les écrans de la salle  
- Démarrer des sous-titres locaux en direct à partir de MTR
- Participer à des réunions Zoom à partir de salles Teams avec participation directe à un invité (préversion)

> [!NOTE]
> La galerie de vidéos 3x3 et les sous-titres en direct locaux sont fournis par le biais du service Microsoft Teams. Ces fonctionnalités sont disponibles pour tous les appareils salles Teams avec la version 4.5.37.0 et ultérieure de l’application.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introduit dans cette mise à jour :

- Réunions coordonnées entre Microsoft Teams et Surface Hub 2S
- Correction de l’échec de connexion Skype For Business lorsque [Windows 10 mise à jour KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) ou [Windows 10 mise à jour KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) est installée

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introduit dans cette mise à jour :

- Participer à des réunions Cisco WebEx à partir de salles Teams avec participation directe d’invités
- Teams Administration l’activation et l’inscription automatique du Centre
- prise en charge des versions de Windows 10 1909
- Basculer vers la disposition de la galerie vidéo même lorsque du contenu est présent
- Prise en charge des mains levées virtuelles pour les participants et contrôles pour le présentateur
- Paramètre de volume par défaut réglable pour la conférence et le haut-parleur par défaut
- Rechercher et appeler des utilisateurs fédérés (locataire) à partir de Teams Room

> [!IMPORTANT]
> La version 4.5 est la dernière version à prendre en charge Windows 10 version 1803 ; les versions ultérieures ne seront pas proposées aux systèmes sur Windows 10 version 1803. Pour plus d’informations sur Windows prise en charge des versions, consultez [Windows 10 prise en charge des versions](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introduit dans cette mise à jour :

- Correctifs de qualité et de fiabilité
- Correction du problème « l’application ne sera pas lancée après la mise à jour vers la version 4.4.41.0 »

> [!NOTE]
> Si votre appareil ne se met pas automatiquement à jour vers la version 4.4.63.0, suivez les étapes décrites dans [Salles Microsoft Teams application ne démarre pas après la mise à jour vers la version 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) pour résoudre le problème.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introduit dans cette mise à jour :

- Correctifs de fiabilité pour le démarrage de l’application dans Windows 10 Kiosk

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introduit dans cette mise à jour :

- Prise en charge de l’authentification moderne pour Exchange et Skype Entreprise
- Prise en charge des appels d’urgence dynamiques pour les Teams (composants de service requis et libérés à l’aide d’anneaux clients Teams)
- Possibilité de désactiver le contenu en double hors réunion pour les doubles affichages de salles à l’aide de XML
- Écran de démarrage de l’application
- Notifications de logiciels open source (OSS) dans les paramètres de l’appareil

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introduit dans cette mise à jour :

- Mises à jour de stratégie pour « mises à jour Windows pour les entreprises »
- Correctif pour les événements d’appareil signalant une erreur dans Azure Monitor

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introduit dans cette mise à jour :

- Correction d’un problème de redimensionnement/de scintillement de fenêtre qui s’affiche dans certaines configurations
- Suppression du traitement du calendrier pour les réunions tierces
- Cortana paramètre d’état supprimé

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introduit dans cette mise à jour :

- Réponse automatique aux appels basés sur la proximité et paramètre d’administration pour contrôler ce
- Actualisation de l’interface utilisateur Administration Paramètres de l’appareil avec ajout de la configuration de l’appareil sous l’onglet À propos
- Contrôle de salle à l’écran principal
- référence SKU Salle de réunion disponible dans Cloud de la communauté du secteur public
- Prise en charge de la caméra de contenu pour le système basé sur Surface Pro (build d’application minimale requise : 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introduit dans cette mise à jour :

- Windows 10 support de 1903. Windows 10 mise à jour 1903 est proposée quelques jours après la mise à jour de l’application
- Correctifs pour le clavier visuel qui ne s’affiche pas de manière fiable

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introduit dans cette mise à jour :

- Nouvelle fonctionnalité de caméra de contenu qui permet aux utilisateurs d’inclure intelligemment un tableau blanc traditionnel dans leur réunion Teams
- Améliorations supplémentaires apportées à l’interface utilisateur de la console pour réduire l’encombrement et déplacer Paramètres dans une nouvelle barre latérale accessible via Plus sur la console
- Bouton Partager désactivé si le câble de contenu local n’est pas connecté ou si une caméra de contenu n’est pas connectée
- Correction d’un problème avec le clavier tactile où il ne s’affichait pas la première fois seulement après le redémarrage du système MTR
- Correctifs de qualité et de fiabilité

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introduit dans cette mise à jour :

- Skype app Room System Store renommer « Salles Microsoft Teams »
- Salles Microsoft Teams interface utilisateur de la console réalignée à Microsoft Teams
- Mise à jour du thème : conservez uniquement l’image d’arrière-plan personnalisée devant les écrans de la salle, tout en faisant de l’arrière-plan de la console une couleur neutre pour garantir que les contrôles d’interface utilisateur de la console respectent le contraste de couleurs : exigences d’accessibilité
- Barre universelle pour les contrôles d’appel en réunion pour les appels/réunions Teams afin de fournir une expérience cohérente avec Microsoft Teams clients PC/Web/Mobile<sup>1</sup>
- Évaluation des commentaires sur la qualité des appels après Teams appels/réunions<sup>1</sup>
- Réception/rendu Microsoft Whiteboard sur Salles Microsoft Teams devant l’affichage de la salle lorsqu’elle est partagée à partir du client TEAMS PC/Web/Mobile<sup>1</sup> <sup>2</sup>
- Suppression de la prise en charge des mises à niveau de Windows 10 version 1809 en raison de problèmes de compatibilité avec Salles Microsoft Teams client. Windows 10 prise en charge de la version 19H1 sera ajoutée dans les versions ultérieures

<sup>1</sup> déploiement de service Microsoft Teams à l’aide d’anneaux Teams. Cette fonctionnalité peut être disponible avant ou après la mise à jour du client 4.0.105.0

<sup>2</sup> Exige que les administrateurs informatiques activent Microsoft Whiteboard. En outre, si vous disposez d’un écran tactile devant la salle, vous devez étalonner plusieurs écrans tactiles à l’aide de paramètres Windows avec connexion administrateur d’appareil pour commencer à utiliser Microsoft Whiteboard pour la collaboration à partir d’un affichage de salle partagé dans une réunion Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introduit dans cette mise à jour :

- Résout un problème avec la fonctionnalité « envoyer des commentaires »
- Optimisations en préparation de la prochaine mise à niveau de l’appareil Salles Microsoft Teams vers Windows 10 version 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introduit dans cette mise à jour :

- Correction du bogue « Blocage au démarrage de l’application » qui affectait les appareils sur la build Windows 10 RS2 héritée.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introduit dans cette mise à jour :

- Clavier DTMF pour Microsoft Teams réunions P2P et appels RTC. Pour Microsoft Teams votre client appelant par défaut, les administrateurs doivent définir IsTeamsDefaultClient sur true
- Épinglez la vidéo entrante d’un participant distant en plein écran devant l’écran de la salle. Utiliser la commande « Épingler » à partir de la liste des participants sur la console
- Améliorations apportées aux notifications lobby avec ajout de la notification Front of Room
- Icône de cast d’affichage devant la salle supprimée lorsque Bluetooth balise n’est pas activée sur Salles Microsoft Teams appareil
- Correction d’un problème de contrôle de volume dans Teams réunions

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introduit dans cette mise à jour :

- Afficher du contenu sur les deux écrans avant de la salle (FoR) sur les systèmes de salle à double écran
- Améliorations de l’interface utilisateur du thème et de l’avant de la salle
- Prise en charge côté client de TLS 1.2. Pour les clients locaux, l’activation de la communication via TLS 1.2 pour Salles Microsoft Teams nécessite Skype Entreprise Server mise à jour cumulative 9 (CU9) 2015 ou Skype Entreprise Server mise à jour cumulative 1 (CU1) 2019.

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introduit dans cette mise à jour :

- Prise en charge de l’affichage double (devant de la salle) pour les réunions Teams

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introduit dans cette mise à jour :

- Correctifs de qualité et de fiabilité

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introduit dans cette mise à jour :

- Modifications de code nécessaires pour préparer l’application Salles Microsoft Teams pour une mise à niveau ultérieure Windows 10 version 1803
- Résolution d’un problème de mise en forme avec des EULA localisées (en particulier en norvégien) qui empêche l’avancement au-delà de la fenêtre d’installation OOBE du CLUF
- Modifications de code nécessaires pour que Salles Microsoft Teams application s’exécute sur les systèmes Lync Room hérités. En savoir plus [ici](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introduit dans cette mise à jour :

- Correctif logiciel pour l’application Crestron qui ne démarre pas, ce qui serait normalement accessible lorsque l’utilisateur appuie sur le bouton d’application sur un appareil Crestron SR. Salles Microsoft Teams redémarrage de l’application requis après l’installation de la version 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introduit dans cette mise à jour :

- Améliorations de la fonctionnalité « Signaler un problème » en mode Teams (équivalent de « Envoyer des commentaires » en mode Skype Entreprise)
- Activer la possibilité de revenir d’Teams au mode Skype Entreprise pour les appels SIP
- Améliorations de l’accessibilité (Narrateur, loupe)
- Redémarrer automatiquement l’application lorsque cela est nécessaire après l’application des modifications de l’approvisionnement XML
- Correctifs divers

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introduit dans cette mise à jour :

- Cette mise à jour permet la prise en charge des réunions Skype Entreprise *et* Teams sur les appareils Room Systems. Teams est désactivé par défaut une fois la mise à jour appliquée. Les administrateurs peuvent activer Teams localement dans les paramètres de l’appareil ou via une transmission push xml distante.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introduit dans cette mise à jour :

- Correction pour résoudre l’erreur observée sur certains systèmes pendant le lancement de l’application.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introduit dans cette mise à jour :

- Modifications permettant à Microsoft de gérer plus flexiblement les mises à jour Windows.
- Aucune modification de l’expérience de l’utilisateur final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introduit dans cette mise à jour :

- Correction des problèmes de réactivité de la console observés sur Surface Pro appareils 2017 connectés à deux écrans front-of-room et à la réception vidéo
- Vérification automatisée pour vérifier que le système exécute le dernier script d’approvisionnement

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introduit dans cette mise à jour :

- Correctif pour améliorer le comportement du kit OSK (clavier visuel) dans les systèmes windows 10 version 1709
- Améliorations apportées à la préparation des futures mises à jour du système d’exploitation

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introduit dans cette mise à jour :

- Application mise à jour pour améliorer la télémétrie

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introduit dans cette mise à jour :

- Résout un problème où des problèmes intermittents de participation à une réunion peuvent se produire
- Résout un problème connu pour entraîner une expérience de blocage de l’appareil

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introduit dans cette mise à jour :

- Correctifs de bogues/incidents pour améliorer la stabilité
- Prise en charge de la console de taille variable
- Déchargement du traitement audio périphérique (liste d’autorisation multimédia supplémentaire)
- Optimisations qui permettent aux professionnels de l’informatique de créer des images do-it-yourself avec Windows 10 mise à jour de janvier 1709 et versions ultérieures.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introduit dans cette mise à jour :

- Résout un problème avec la fonctionnalité « Envoyer des commentaires ».

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introduit dans cette mise à jour :

- Prise en charge du matériel d’ancrage [de la série MSR Polycom](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Prise en charge de [Logitech Brio](https://www.logitech.com/product/brio)
- Résout un problème où les affichages (console et salle principale) ne parviennent pas à passer en mode veille en l’absence d’activité dans la salle

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introduit dans cette mise à jour :

- S’exécute sur une tablette Surface Pro (2017)
- Prend en charge Windows 10 Entreprise Creator’s Update (langue anglaise, build 1703)
- Prise en charge du matériel d’ancrage [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Prise en charge OEM pour les contrôles d’environnement (Crestron)

La version 64 bits de Windows 10 Entreprise Édition anniversaire (langue anglaise, version 1607) n’est plus prise en charge à compter de Salles Microsoft Teams version 3.0.12.0 (mise à jour 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introduit dans cette mise à jour :

- Résout les problèmes observés lors de la recherche d’utilisateurs fédérés via le champ de recherche Participants. Avant ce correctif, les résultats de recherche des utilisateurs fédérés externes n’étaient peut-être pas résolus correctement et renvoyaient à la place des résultats incorrects.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introduit dans cette mise à jour :

- prise en charge Dual-Screen (pour la parité système héritée)
- Thèmes (thèmes intégrés et possibilité de définir un thème personnalisé)
- Possibilité d’envoyer des commentaires pour les builds publiques
- Amélioration de la télémétrie autour de la fiabilité des jointures de réunion
- Amélioration des rapports OMS
- Possibilité pour les Administration informatiques de configurer des appareils à distance

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introduit dans cette mise à jour :

- Sélection par l’utilisateur dans l’application des périphériques USB audio et vidéo de salle de réunion
- Rapports d’état de la console de salle intégrée pour les clients utilisant Microsoft Operations Management Suite, désormais Azure Monitor

### <a name="release-to-market-1272016"></a>Mise sur le marché (7/12/2016)

**Fonctionnalités :**

 **Conçue pour Skype Entreprise**

- Participation aux réunions Skype en un clic
- Réunion Skype expérience optimisée pour les salles avec vidéo HD et audio hd large bande
- Tous les participants peuvent se connecter à la réunion Skype à l’aide du dispositif de leur choix où qu’ils soient
- Invitez des contacts via votre annuaire qui vous indiquera leur disponibilité, ou via un appel téléphonique
- Prise en charge de la conférence PSTN Skype Entreprise et de la fonction d’appel PSTN pour remplacer le téléphone de conférence autonome de votre salle de réunion

 **Conversion d’un espace de réunion**

- Optimisation de l’application de réunion Skype dédiée pour le centre du contrôleur tactile et large écran d’affichage
- Réutiliser les investissements existants dans l’affichage ou les projecteurs de votre salle
- Fonctionne avec tout type d’espace de réunion, allant des petites salles aux vastes espaces de conférence
- Des périphériques audio et vidéo Skype Entreprise certifiés sont disponibles pour différentes tailles d’espace
- Ingestion câblée intégrée au partage de bureau de projet dans la salle et au Réunion Skype

 **Facilité de déploiement, simplicité de gestion**

- Appliance always-on qui réveille automatiquement les écrans lorsqu’elle détecte des personnes dans la pièce
- Déploiement simple et mise à jour de l’application de réunion Skype UWP (plateforme Windows universelle)
- L’AppLocker de Windows verrouille l’appareil sur l’application de réunion Skype
- Surveillé et géré en tant qu’appareil Windows 10 Entreprise via Intune et Configuration Manager (GPM)
- Fiabilité pour l’entreprise
- Effort de formation minime des utilisateurs finaux, grâce à l’interface utilisateur Skype familière
- S’exécute sur Surface Pro 4 tablette

<a name="See"> </a>
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Préparer votre environnement](rooms-prep.md)

[Prise en charge des versions Salles Microsoft Teams Current Branch](rooms-lifecycle-support.md)

[Problèmes connus](known-issues.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)
