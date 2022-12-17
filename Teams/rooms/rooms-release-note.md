---
title: Notes de publication pour Salles Microsoft Teams (Windows)
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
description: Administration pouvez lire les notes de publication de Salles Microsoft Teams, qui répertorient les améliorations cumulatives apportées à Salles Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 256ab81b195d5a758e07c24741b1dc8a7ff13218
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438362"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Notes de publication pour Salles Microsoft Teams

Cet article décrit les améliorations cumulatives apportées à Salles Microsoft Teams.

Il existe deux types de mises à jour pour salles Teams : les mises à jour des applications salles Teams et le client web Teams.

salles Teams mises à jour de l’application se produisent via le Microsoft Store ou via une [mise à jour manuelle](manual-update.md). Mises à jour sont appliquées à l’application plateforme Windows universelle (UWP) installée localement sur l’appareil.

Les mises à jour du client web Teams se produisent via les services de remise d’applications web Teams. Le client web Teams est un service cloud qui ne nécessite pas de mise à jour de l’application UWP locale installée sur l’appareil.

Pour plus d’informations sur la façon dont les mises à jour De Teams sont mises à jour, consultez [Processus de mise à jour Teams](../teams-client-update.md)

salles Teams est régie par la politique de cycle de vie moderne. Pour plus d’informations, consultez [Processus de mise à jour teams](../teams-client-update.md#servicing-agreement).

## <a name="version-history"></a>Historique des versions

|Libération |Publié dans <br/> Microsoft Store |
|--- |--- |
|4.15.54.0 | 12/15/2022 |
|4.14.24.0 |9/2/2022 |
|4.13.132.0 |8/2/2022 |
|4.12.139.0 |7/14/2022 |
|4.12.138.0 |5/26/2022 |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Version du client web Teams | Décembre 2021 |
|Version du client web Teams | Octobre 2021 |
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

### <a name="415540-12152022"></a>4.15.54.0 (12/15/2022)

Introduit dans cette mise à jour :

- Amélioration des notifications en réunion
- Conversation de réunion dans la galerie, la grande galerie et le mode Ensemble <sup>1</sup>
- Démarrer le tableau blanc dans les réunions Teams
- Contrôle de la liste vidéo de salle d’ajustement à l’image
- Prise en charge des réunions de dépassement de capacité
- Participez à des réunions Zoom par ID via la jonction d’invité directe. La prise en charge de la participation aux réunions Zoom par ID a été ajoutée dans cette version et sera activée dans les semaines à venir.
- Correctifs de qualité pour les réunions tierces (direct guest join)
- Correctif pour les informations de licence dans les paramètres indiquant aucune licence lorsque Teams n’est pas connecté
- Un nouveau papier peint par défaut (Indicateur vif) et quatre autres nouveaux fonds d’écran

<sup>1 La</sup> configuration de l’administrateur pour masquer la conversation de réunion de toutes les dispositions de réunion via XML est disponible dans [Gérer les paramètres d’une console Salles Microsoft Teams à distance avec un fichier de configuration XML](xml-config-file.md).

### <a name="414240-922022"></a>4.14.24.0 (9/2/2022)

Introduit dans cette mise à jour :

- Mise à jour de l’expérience de disposition de ligne avant
- Épingler et masquer la vidéo de salle
- Configuration de l’administrateur pour désactiver la galerie fractionnée dans le salles Teams <sup>double affichage 1</sup>
- Les salles Teams à double affichage peuvent désormais afficher jusqu’à 18 flux vidéo de participants
- Prise en charge des licences de salle de base Salles Microsoft Teams Pro et Microsoft Teams

<sup>1 La</sup> configuration de l’administrateur pour la désactivation de la galerie fractionnée via XML est disponible dans [Gérer les paramètres d’une console Salles Microsoft Teams à distance avec un fichier de configuration XML](../rooms/xml-config-file.md).

### <a name="4131320-822022"></a>4.13.132.0 (8/2/2022)

Introduit dans cette mise à jour :

- Participer à une réunion Teams à l’aide de l’ID de réunion
- Chiffrement de bout en bout pour les appels Teams<sup>1</sup> 
- Suppression du bruit dans les réunions Teams<sup>2</sup>
- Partager la mise à jour de l’expérience de la barre d'
- Désactiver le son et réactiver l’état sur la vidéo de votre salle
- Administration paramètre par défaut pour la disposition du contenu uniquement  
- L’authentification moderne est activée par défaut

 <sup>1</sup> Avant de pouvoir activer le chiffrement de bout en bout pour les appels à partir d’un appareil salles Teams, vous devez configurer la stratégie pour le compte d’utilisateur de l’appareil. Vous pouvez mettre à jour la stratégie de l’utilisateur à partir du Centre d’administration Teams ou à l’aide de Teams PowerShell. Pour plus d’informations, consultez [Configurer la stratégie pour le compte d’utilisateur salle Teams.](../teams-end-to-end-encryption.md)

 <sup>2</sup> salles Teams ajout de la prise en charge de la suppression du bruit dans la version 4.12 avec remplacement administrateur.

> [!IMPORTANT]
> Avec cette mise à jour, les nouveaux appareils salles Teams utilisent désormais par défaut l’authentification moderne lors de la connexion à Microsoft Teams et Exchange Online.
>
> Nous vous recommandons vivement de tester vos appareils salles Teams avant la fin du mois d’août en activant l’authentification moderne pour leurs comptes de salle.
>
> Cette modification permet de préparer la prochaine mise à jour dans Exchange Online de désactiver l’authentification de base à partir du 1er octobre 2022. Pour plus d’informations, consultez [Dépréciation de l’authentification de base dans Exchange Online – Mise à jour de mai 2022 ](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-may-2022/ba-p/3301866).  

### <a name="4121390-7142022"></a>4.12.139.0 (7/14/2022)

Introduit dans cette mise à jour :

- Modifie le numéro de version pour permettre aux systèmes affectés par Windows [KB5013942](https://support.microsoft.com/topic/may-10-2022-kb5013942-os-builds-19042-1706-19043-1706-and-19044-1706-60b51119-85be-4a34-9e21-8954f6749504) de réinscrire l’application afin qu’elle puisse être lancée. Il n’y a aucune modification fonctionnelle dans cette version de l’application à partir de la version 4.1.2.138.0.

> [!NOTE]
> Pour plus d’informations, consultez « salles Teams’application ne parvient pas à démarrer après la mise à jour » dans [Problèmes connus dans les salles Teams et les appareils](/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues).

### <a name="4121380-5262022"></a>4.12.138.0 (5/26/2022)

Introduit dans cette mise à jour :
- Correctif de bogue pour plusieurs flux vidéo simultanés de Jabra Panacast 50 (vidéo de réunion, vidéo de caméra de contenu)
- Les réunions intercloud peuvent désormais utiliser un périphérique audio de conférence par défaut
- Correctifs de qualité et de fiabilité

### <a name="4121260-4272022"></a>4.12.126.0 (4/27/2022)

Introduit dans cette mise à jour :
- Les administrateurs informatiques peuvent inscrire un appareil de salles Teams pour recevoir des fonctionnalités en préversion publique via le paramètre XML. Une fois inscrit, l’appareil commence à recevoir des fonctionnalités bêta. Toutes les fonctionnalités qui passent au test bêta sont annoncées dans [Microsoft Préversion publique de Teams - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1,2</sup>  
- L’administrateur informatique peut définir la résolution d’affichage et la mise à l’échelle à distance à l’avant de la salle via les paramètres XML<sup>2</sup>
- L’administrateur informatique peut désactiver Microsoft suppression du bruit via le paramètre XML<sup>3</sup> 
- L’administrateur informatique peut remplacer le nettoyage du dossier de téléchargement sur l’appareil via le paramètre de clé de Registre<sup>4</sup>
- Permettre aux utilisateurs de participer à une réunion Teams hébergée sur un autre cloud (par exemple, le client GCCH peut participer à des réunions Teams hébergées sur le cloud commercial et vice versa) 
- Salles Teams bloque désormais le lancement du navigateur edge à partir d’URL dans PowerPoint Live comme mesure de sécurité supplémentaire pour les salles Teams avec écrans tactiles 
- L’expérience Meet now est améliorée pour ajouter des instructions permettant aux utilisateurs d’inviter des utilisateurs à la salle 
- Prise en charge de Windows 10 version de fonctionnalité 21H2 pour les salles Teams   
- Nouveau point d’entrée Cortana sur l’écran d’accueil, le bouton Partager/présenter est de retour 

> <sup>1</sup> Les instructions pour l’inscription des appareils Windows MTR en préversion publique sont disponibles [ici](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2</sup> La résolution et la mise à l’échelle à distance de l’affichage à l’avant de la salle via XML sont disponibles [ici](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)
>
> <sup>3</sup> À l’heure actuelle, seul le paramètre d’administration est publié. Le contrôle utilisateur et l’activation de la suppression du bruit suivront la version 4.12 en mai 2022. 
>
> <sup>4 Les</sup> instructions de nettoyage de l’appareil sont disponibles [ici](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)
> 
> 
> [!NOTE]
> Windows 10 mise à jour des fonctionnalités 21H2 sera mise à jour après 7 jours d’installation de l’application, ou les administrateurs peuvent utiliser la mise à jour manuelle à la place pour une installation plus rapide. Salles Microsoft Teams version 4.12 de l’application avec ces modifications, commencera à être déployée en avril 2022 et terminera le déploiement dans 2 à 3 semaines. Les mises à jour de l’application sont fournies par le biais du Windows Store et l’application est automatiquement installée. Cette opération est déployée uniquement sur Salles Microsoft Teams sur Windows. Ce que vous devez faire pour vous préparer : vous souhaiterez peut-être informer vos utilisateurs de cette expérience mise à jour et mettre à jour votre formation et votre documentation le cas échéant.

### <a name="411170-332022"></a>4.11.17.0 (3/3/2022)

Introduit dans cette mise à jour :
- Correctif de bogue pour l’encadrement de la caméra qui améliore tout le contenu dans la vue de la caméra.

### <a name="411120-1242022"></a>4.11.12.0 (1/24/2022)

Introduit dans cette mise à jour :
- Disposition de première ligne (préversion) pour MTR sur Windows<sup>1</sup> 
- Administration paramètre pour définir la disposition de ligne avant par défaut  
- Rencontrer maintenant et appeler la mise à jour de l’application pour Teams uniquement, modes client par défaut De Teams<sup>1,2</sup>
- Basculer entre plusieurs caméras vidéo dans les réunions Teams<sup>1</sup> 
- Paramètre de caméra vidéo par défaut 
- Mise à jour de l’icône push-to-talk cortana sur la console MTR 
- Inclusion de licence Azure AD Premium 1 dans les références SKU Room Standard et Premium 
- Prise en charge des stratégies d’accès conditionnel AAD<sup>3</sup> 
- Activation vocale Cortana activée par défaut dans OOBE
- Prise en charge des contrôles PTZ<sup>distants 4</sup>

> <sup>1</sup> Ces fonctionnalités sont déployées à l’aide du client web Teams et seront déployées dans les prochaines semaines. Pour plus d’informations, consultez [Mises à jour de Teams](../teams-client-update.md) .
> 
> <sup>2</sup> Les salles Teams sur Windows s’exécutant dans Microsoft Teams uniquement ou Skype Entreprise et Microsoft Teams (par défaut) sont mises à jour avec de nouvelles expériences de réunion et d’appel, mais les autres modes ne sont pas affectés par cette mise à jour.
> 
> <sup>3</sup> Consultez les détails supplémentaires sur la configuration des stratégies [d’accès conditionnel AAD](../rooms/rooms-authentication.md#azure-ad-conditional-access) pour salles Teams.
> 
> <sup>4</sup> Cette fonctionnalité nécessite que les administrateurs informatiques configurent l’application de contrôles PTZ distants du client de bureau Teams.
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>mise à jour du client web salles Teams (décembre 2021)

Introduit dans cette mise à jour :
- Fractionner la disposition vidéo sur deux écrans devant la salle lorsque le contenu n’est pas partagé

### <a name="teams-rooms-web-client-update-october-2021"></a>mise à jour du client web salles Teams (octobre 2021)

Introduit dans cette mise à jour :
- Contrôle de liste unifié avec le client de bureau Teams avec un regroupement de réunions structuré, des options de réunion et des contrôles pour les présentateurs/participants, lève l’ordre de tri et la possibilité d’inviter des utilisateurs à partir d’une conversation ou d’une invitation à une réunion directement à partir de la liste 
- Alignement des contrôles d’appel de barre universelle avec le client de bureau dans les contrôles d’appel de réunion, le bouton Disposition et les informations d’état de réunion
- Prise en charge de la galerie dynamique pour les écrans frontaux simples et doubles des salles
- Sélecteur de disposition unifié pour l’option de disposition de l’avant de la salle consolidée
- Mettre en vedette ou épingler plusieurs participants dans les réunions Teams
- Prise en charge des grandes réunions avec des contrôles présentateur/participants accessibles en appuyant sur le participant à partir de la liste
- Possibilité de verrouiller une réunion pour les réunions dont la salle est l’organisateur, ainsi que la connaissance de la réunion verrouillée
- Prise en charge de la consommation en mode présentateur (weatherman) lorsqu’un utilisateur distant partage du contenu avec l’option mode Présentateur
- Prise en charge des réactions dans les réunions Teams 

> [!NOTE]
> Les mises à jour du client web sont disponibles pour toutes les salles Teams avec les versions d’application 4.10 et 4.9. Les administrateurs pourront s’inscrire à salles Teams programme en préversion publique pour obtenir bientôt un aperçu des fonctionnalités du client web.

### <a name="410100-1012021"></a>4.10.10.0 (10/1/2021)

Introduit dans cette mise à jour :
- Room remote permet aux utilisateurs de contrôler les fonctionnalités de base de la salle à l’aide de Teams sur leur mobile *
- Prise en charge de la caméra de contenu par Logitech pour le bouton BLE pour le partage dans une réunion
- Les bulles de conversation fournissent des notifications pour dans la conversation de réunion afin d’attirer l’attention sur ce qui est dit à l’aide de la conversation de réunion *
- La prise en charge de la grande galerie et du mode Ensemble est désormais disponible dans GCC High
- Nouvelles compétences ajoutées à Cortana, Ajouter une personne par nom à la réunion et Appeler par nom 
- Cortana Push to Talk est activé par défaut sur tous les appareils. Pour plus d’informations, consultez [Assistance vocale Cortana dans Teams](../cortana-in-teams.md).

> [!NOTE]
> Prise en charge 19H1 déconseillée. La version minimale du système d’exploitation prise en charge par la version 4.10 est 19H2.

> [!NOTE]
> *Ces fonctionnalités sont déployées à l’aide du service Teams et fonctionnent avec toutes les versions d’application supérieures à 4.9.

> [!NOTE]
> Pour participer à la réunion planifiée à partir de l’application Mobile Teams et de MTR-W, recherchez le compte de salle dans la liste dans l’application Mobile Teams et appuyez sur le menu « Contrôler cette salle ». Vous pouvez contrôler les contrôles d’appel à partir de l’application.

### <a name="49120-7282021"></a>4.9.12.0 (7/28/2021)

Introduit dans cette mise à jour :
- Microsoft mode Teams uniquement est désormais disponible dans les paramètres de l’application, vous n’avez donc plus besoin de configurer un compte Skype Entreprise. Dans ce mode, les appareils connectés au mode Teams uniquement rejoignent Skype Entreprise réunions en tant qu’utilisateur invité.
- Correctif pour l’audio HDMI entraînant une diminution du volume des appels. La fonctionnalité audio HDMI est automatiquement activée pour tous les appareils avec la build d’application 4.9.12.0.

> [!NOTE]
> Une fois Skype Entreprise fin de vie atteinte, il est recommandé d’effectuer une mise à jour vers le mode Teams uniquement.

### <a name="48310-05122021"></a>4.8.31.0 (05/12/2021)

Introduit dans cette mise à jour :
- Prise en charge de Windows 10 20H2 

> [!NOTE]
> Crestron UC-Engine (date de version du BIOS contenant « KYSKLi ») salles Teams ont des problèmes de compatibilité et les pilotes mis à jour seront fournis par les oem système dans un avenir proche. Windows 10 20H2 ne sera pas proposée à ces appareils. Pour plus d’informations sur la prise en charge des versions de Windows, consultez [Windows 10 prise en charge des versions](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="48250-04222021"></a>4.8.25.0 (04/22/2021)

Introduit dans cette mise à jour :
- Correction d’un problème où les informations de salle sur salles Teams consoles ne s’affichent pas pour les comptes de salle masqués dans la liste d’adresses globale (GAL)

> [!NOTE]
> Les clients GCCH peuvent télécharger le package de mise à niveau à partir de [Mettre à jour manuellement un appareil Salles Microsoft Teams](manual-update.md)

### <a name="48190-04062021"></a>4.8.19.0 (04/06/2021)

Introduit dans cette mise à jour :
- Prise en charge de GCCH (Government Community Cloud High) pour salles Teams. Les clients GCCH disposant d’appareils salles Teams existants peuvent télécharger la version 4.8.19.0 à partir de [mettre à jour manuellement un appareil Salles Microsoft Teams](manual-update.md)
- Participer à des réunions Zoom avec une meilleure qualité vidéo (prise en charge 720p) et recevoir la galerie de vidéos des participants
- Skype Entreprise bannière d’échec de connexion supprimée pour le mode par défaut de Teams. Cette modification permet aux organisations de supprimer Skype Entreprise infrastructure
- L’analyse des liens de participation aux réunions Teams gère désormais Microsoft Defender liens sécurisés de protection avancée contre les menaces pour permettre de rejoindre des équipes externes en toute transparence
- Correctif pour le problème de mise à l’échelle du contenu partagé dans les réunions Skype Entreprise lorsque le PC du partage a un DPI personnalisé défini dans Windows
- Correctifs de qualité et de fiabilité

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021)

Introduit dans cette mise à jour :
- Correctifs de qualité et de fiabilité

### <a name="47150-12112020"></a>4.7.15.0 (12/11/2020)

Introduit dans cette mise à jour :

- Partager l’audio HDMI avec les participants à la réunion Teams
- Compétences vocales Cortana (préversion)
- Empêchez l’activation en fonction des autorisations audio lorsque salles Teams rejoint en tant que participant. Pour plus d’informations, consultez [Gérer les autorisations audio des participants dans les réunions Teams](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Mettre en avant la vidéo d’une personne à partir de la console salle Teams et consommer la vidéo à la une sur les écrans de salle

> [!NOTE]
> Les compétences vocales Cortana sont disponibles pour certains périphériques audio pour les locataires situés dans le États-Unis. D’autres pays ou régions seront ajoutés à l’avenir. Pour plus d’informations, consultez [Assistance vocale Cortana dans Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (10/19/2020)

Introduit dans cette mise à jour :

- Correctif pour le demi-écran blanc lors de l’appel du clavier visuel dans une réunion Teams

### <a name="46200-09302020"></a>4.6.20.0 (09/30/2020)

Introduit dans cette mise à jour :

- Voir d’autres vidéos avec la galerie de vidéos 3x3 devant les écrans de salle  
- Démarrer des sous-titres locaux en direct à partir de MTR
- Participer à des réunions Zoom à partir de salles Teams avec la jonction d’invité directe (préversion)

> [!NOTE]
> La galerie de vidéos 3x3 et les sous-titres locaux en direct sont fournis via le service Microsoft Teams. Ces fonctionnalités sont disponibles pour tous les appareils salles Teams avec la version d’application 4.5.37.0 et les versions ultérieures.

### <a name="45370-08142020"></a>4.5.37.0 (08/14/2020)

Introduit dans cette mise à jour :

- Réunions coordonnées entre Microsoft Teams et Surface Hub 2S
- Correctif pour l’échec de connexion à Skype Entreprise quand [Windows 10 mise à jour KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) ou [Windows 10 mise à jour KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) est installée

### <a name="45350-07232020"></a>4.5.35.0 (07/23/2020)

Introduit dans cette mise à jour :

- Participer à des réunions Cisco Webex à partir de salles Teams avec la participation d’invité direct
- Activation et inscription automatique du Centre Administration Teams
- Prise en charge des versions Windows 10 1909
- Basculer vers la disposition de la galerie de vidéos même lorsque du contenu est présent
- Prise en charge des mains levées virtuelles pour le participant et des contrôles pour le présentateur
- Paramètre de volume par défaut réglable pour la conférence et l’orateur par défaut
- Rechercher et appeler des utilisateurs fédérés (locataire) à partir de la salle Teams

> [!IMPORTANT]
> La version 4.5 est la dernière version pour prendre en charge Windows 10 version 1803 ; les versions ultérieures ne seront pas proposées aux systèmes sur Windows 10 version 1803. Pour plus d’informations sur la prise en charge des versions de Windows, consultez [Windows 10 prise en charge des versions](./rooms-lifecycle-support.md#windows-10-release-support).

### <a name="44630-06252020"></a>4.4.63.0 (06/25/2020)

Introduit dans cette mise à jour :

- Correctifs de qualité et de fiabilité
- Correctif pour le problème « L’application ne démarre pas après la mise à jour vers la version 4.4.41.0 »

> [!NOTE]
> Si votre appareil ne se met pas automatiquement à jour vers la version 4.4.63.0, suivez les étapes [décrites dans Salles Microsoft Teams’application ne démarre pas après la mise à jour vers la version 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update) pour résoudre le problème.

### <a name="44410-05062020"></a>4.4.41.0 (05/06/2020)

Introduit dans cette mise à jour :

- Correctifs de fiabilité pour le démarrage de l’application dans Windows 10 Kiosque

### <a name="44250-03312020"></a>4.4.25.0 (03/31/2020)

Introduit dans cette mise à jour :

- Prise en charge de l’authentification moderne pour Exchange et Skype Entreprise
- Prise en charge des appels d’urgence dynamiques pour Teams (composants de service requis et libérés à l’aide des anneaux du client Teams)
- Possibilité de désactiver le contenu en double sortie de réunion pour les salles à double affichage à l’aide de XML
- Écran de démarrage de l’application
- Avis sur les logiciels open source (OSS) dans les paramètres de l’appareil

### <a name="43420-03022020"></a>4.3.42.0 (03/02/2020)

Introduit dans cette mise à jour :

- Mises à jour de stratégie pour « Windows Mises à jour entreprise »
- Correctif pour les événements d’appareil signalant une erreur dans Azure Monitor

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Introduit dans cette mise à jour :

- Correctif pour un problème de redimensionnement/scintillement de fenêtre qui est observé dans certaines configurations
- Suppression du traitement du calendrier pour les réunions tierces
- Suppression du paramètre d’état Cortana

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Introduit dans cette mise à jour :

- Réponse automatique aux appels basés sur la proximité et paramètre d’administration pour contrôler cela
- Actualisation de l’interface utilisateur des paramètres Administration de l’appareil avec ajout de la configuration de l’appareil sous l’onglet À propos de
- Retour du contrôle de la salle à l’écran principal
- Référence SKU salle de réunion disponible dans GCC
- Prise en charge de la caméra de contenu pour le système basé sur Surface Pro (build d’application minimale requise : 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Introduit dans cette mise à jour :

- Windows 10 prise en charge de la version 1903. Windows 10 mise à jour 1903 est proposée quelques jours après la mise à jour de l’application
- Correctifs pour le clavier visuel qui ne s’affiche pas de manière fiable

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Introduit dans cette mise à jour :

- Nouvelle fonctionnalité de caméra de contenu qui permet aux utilisateurs d’inclure intelligemment un tableau blanc traditionnel dans leur réunion Teams
- Améliorations supplémentaires apportées à l’interface utilisateur de la console pour réduire l’encombrement et déplacer les paramètres dans une nouvelle barre latérale accessible via Plus sur la console
- Bouton de partage de la barre d’état désactivé si le câble de contenu local n’est pas connecté ou si une caméra de contenu n’est pas connectée
- Correction d’un problème avec le clavier tactile où il n’apparaissait pas la première fois seulement après un redémarrage du système MTR
- Correctifs de qualité et de fiabilité

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Introduit dans cette mise à jour :

- L’application skype Room System Store est renommée « Salles Microsoft Teams »
- interface utilisateur de la console Salles Microsoft Teams réalignée pour Microsoft Teams
- Mise à jour du thème : conservez uniquement l’image d’arrière-plan personnalisée devant les écrans de salle, tout en faisant de l’arrière-plan de la console une couleur neutre pour garantir que les contrôles de l’interface utilisateur de la console répondent au contraste des couleurs ( exigences d’accessibilité)
- Barre universelle pour les contrôles d’appel en réunion pour les appels/réunions Teams afin de fournir une expérience cohérente avec Microsoft clients PC/Web/Mobile<sup>Teams 1</sup>
- Évaluation des commentaires sur la qualité des appels après les appels/réunions Teams<sup>1</sup>
- Recevoir/afficher Microsoft tableau blanc sur Salles Microsoft Teams’affichage avant de la salle lorsqu’il est partagé à partir du client PC/Web/Mobile Teams<sup>1</sup> <sup>2</sup>
- Suppression de la prise en charge des mises à niveau Windows 10 version 1809 en raison de problèmes de compatibilité avec Salles Microsoft Teams client. Windows 10 prise en charge de la version 19H1 sera ajoutée dans les versions ultérieures

<sup>1</sup> Microsoft déploiement du service Teams à l’aide d’anneaux Teams. Cette fonctionnalité peut être disponible avant ou ultérieure à la mise à jour du client 4.0.105.0

<sup>2</sup> Nécessite que les administrateurs informatiques activent Microsoft Tableau blanc. En outre, si vous disposez d’un écran tactile avant de salle, vous devez étalonner plusieurs écrans tactiles à l’aide des paramètres Windows avec la connexion de l’administrateur de l’appareil pour commencer à utiliser Microsoft Tableau blanc pour la collaboration à partir d’un affichage de salle partagé dans une réunion Teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Introduit dans cette mise à jour :

- Correction d’un problème avec la fonctionnalité « Envoyer des commentaires »
- Optimisations en préparation de la prochaine mise à niveau de l’appareil Salles Microsoft Teams vers Windows 10 version 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Introduit dans cette mise à jour :

- Correctif pour le bogue « blocage au démarrage de l’application » qui affectait les appareils sur la build héritée Windows 10 RS2.

### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Introduit dans cette mise à jour :

- Clavier DTMF pour Microsoft les réunions Teams P2P et les appels RTC. Pour que Microsoft Teams soit votre client appelant par défaut, les administrateurs doivent définir IsTeamsDefaultClient sur true
- Épinglez la vidéo entrante d’un participant distant en plein écran devant l’affichage de la salle. Utiliser la commande « Épingler » de la liste des participants sur la console
- Améliorations apportées aux notifications de salle d’attente avec l’ajout d’une notification devant la salle
- Icône de diffusion de l’affichage avant de la salle supprimée lorsque la balise Bluetooth n’est pas activée sur Salles Microsoft Teams appareil
- Correction du problème de contrôle de volume dans les réunions Teams

### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Introduit dans cette mise à jour :

- Afficher le contenu sur les deux écrans Front of Room (FoR) sur les systèmes de salle double écran
- Améliorations de l’interface utilisateur des thèmes et de l’avant de la salle
- Prise en charge côté client de TLS 1.2. Pour les clients locaux, l’activation de la communication via TLS 1.2 pour Salles Microsoft Teams nécessite Skype Entreprise Server mise à jour cumulative 9 (CU9) 2015 ou Skype Entreprise Server mise à jour cumulative 1 (CU1) 2019.

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Introduit dans cette mise à jour :

- Prise en charge du double affichage (avant de la salle) pour les réunions Teams

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Introduit dans cette mise à jour :

- Correctifs de qualité et de fiabilité

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Introduit dans cette mise à jour :

- Modifications de code nécessaires pour préparer l’application Salles Microsoft Teams pour une mise à niveau ultérieure Windows 10 version 1803
- Correction du problème de mise en forme avec les CLUF localisés (en particulier norvégien) qui empêchent d’avancer au-delà de la fenêtre de configuration de l’OOBE du CLUF
- Modifications de code nécessaires pour que Salles Microsoft Teams application s’exécute sur les systèmes de salle Lync hérités. Pour plus [d’informations, cliquez ici](./lrs-migration.md).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Introduit dans cette mise à jour :

- Correctif logiciel pour l’application Crestron qui ne se lance pas et qui est normalement accessible lorsque le bouton de l’application sur un appareil Crestron SR est enfoncé. Salles Microsoft Teams redémarrage de l’application requis après l’installation de la version 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Introduit dans cette mise à jour :

- Améliorations de la fonctionnalité « Signaler un problème » en mode Teams (équivalent de « Envoyer des commentaires » en mode Skype Entreprise)
- Activer la possibilité de revenir de Teams au mode Skype Entreprise pour les appels SIP
- Améliorations de l’accessibilité (Narrateur, Loupe)
- Redémarrer automatiquement l’application si nécessaire après l’application des modifications d’approvisionnement XML
- Correctifs divers

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Introduit dans cette mise à jour :

- Cette mise à jour permet la prise en charge des réunions Skype Entreprise *et* Teams sur les appareils Systèmes de salle. Teams est désactivé par défaut une fois la mise à jour appliquée. Les administrateurs peuvent activer Teams localement dans les paramètres de l’appareil ou via un push xml distant.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Introduit dans cette mise à jour :

- Correction pour résoudre les erreurs observées sur certains systèmes lors du lancement de l’application.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Introduit dans cette mise à jour :

- Modifications permettant Microsoft de gérer de manière plus flexible les Mises à jour Windows.
- Aucune modification de l’expérience de l’utilisateur final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Introduit dans cette mise à jour :

- Correctif pour résoudre les problèmes de réactivité de la console observés sur Surface Pro appareils 2017 connectés à deux écrans devant la salle et à l’ingestion de vidéos
- Vérification automatisée pour s’assurer que le système exécute le dernier script d’approvisionnement

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Introduit dans cette mise à jour :

- Correctif pour améliorer le comportement du clavier visuel (OSK) dans les systèmes Windows 10 Version 1709
- Améliorations apportées pour préparer les futures mises à jour du système d’exploitation

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Introduit dans cette mise à jour :

- Application mise à jour pour améliorer la télémétrie

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Introduit dans cette mise à jour :

- Résolution d’un problème où des problèmes intermittents de participation à une réunion peuvent se produire
- Correction d’un problème connu pour entraîner une expérience de blocage de l’appareil

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Introduit dans cette mise à jour :

- Correctifs de bogues/d’incidents pour améliorer la stabilité
- Prise en charge de la console de taille variable
- Déchargement du traitement audio périphérique (liste d’autorisation de média supplémentaire)
- Optimisations qui permettent aux professionnels de l’informatique de créer des images pratiques avec Windows 10 mise à jour de janvier version 1709 et versions ultérieures.

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Introduit dans cette mise à jour :

- Correction d’un problème avec la fonctionnalité « Envoyer des commentaires ».

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Introduit dans cette mise à jour :

- Prise en charge du matériel de station d’accueil [de la série MSR Polycom](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Prise en charge du [Logitech Brio](https://www.logitech.com/product/brio)
- Résout un problème où les affichages (console et avant-salle) ne parviennent pas à passer en mode veille lorsqu’il n’y a aucune activité dans la salle

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Introduit dans cette mise à jour :

- S’exécute sur une tablette Surface Pro (2017)
- Prend en charge Windows 10 Entreprise Creator’s Update (anglais, build 1703)
- Prise en charge du matériel de station d’accueil [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Prise en charge OEM des contrôles d’environnement (Crestron)

La version 64 bits de Windows 10 Entreprise Édition Anniversaire (langue anglaise, version 1607) n’est plus prise en charge à partir de Salles Microsoft Teams version 3.0.12.0 (mise à jour 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Introduit dans cette mise à jour :

- Résout les problèmes observés lors de la recherche d’utilisateurs fédérés via le champ de recherche Participants. Avant ce correctif, les résultats de la recherche pour les utilisateurs fédérés externes n’ont peut-être pas été correctement résolus et ont retourné des résultats incorrects.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Introduit dans cette mise à jour :

- Dual-Screen prise en charge (pour la parité système héritée)
- Thèmes (thèmes intégrés et possibilité de définir un thème personnalisé)
- Possibilité de donner des commentaires pour les builds publiques
- Amélioration de la télémétrie autour de la fiabilité de la participation à une réunion
- Amélioration de la création de rapports OMS
- Possibilité pour les Administration informatiques de configurer des appareils à distance

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Introduit dans cette mise à jour :

- Sélection d’utilisateurs dans l’application des périphériques USB audio et vidéo de salle de réunion
- Rapports d’état de console de salle intégrés pour les clients utilisant Microsoft Operations Management Suite, désormais Azure Monitor

### <a name="release-to-market-1272016"></a>Mise sur le marché (7/12/2016)

**Fonctionnalité(s) :**

 **Conçue pour Skype Entreprise**

- Participation aux réunions Skype en un clic
- Réunion Skype expérience optimisée pour les salles avec la vidéo HD de remplissage d’écran et l’audio hd large bande
- Tous les participants peuvent se connecter à la réunion Skype à l’aide du dispositif de leur choix où qu’ils soient
- Invitez des contacts via votre annuaire qui vous indiquera leur disponibilité, ou via un appel téléphonique
- Prise en charge de la conférence PSTN Skype Entreprise et de la fonction d’appel PSTN pour remplacer le téléphone de conférence autonome de votre salle de réunion

 **Conversion d’un espace de réunion**

- Optimisation de l’application de réunion Skype dédiée pour le centre du contrôleur tactile et large écran d’affichage
- Réutiliser les investissements existants dans l’écran ou les projecteurs de votre salle
- Fonctionne avec tout type d’espace de réunion, allant des petites salles aux vastes espaces de conférence
- Des périphériques audio et vidéo Skype Entreprise certifiés sont disponibles pour différentes tailles d’espace
- Réception câblée intégrée pour projeter le partage de bureau dans la salle et dans le Réunion Skype

 **Facilité de déploiement, simplicité de gestion**

- Appliance always-on qui réveille automatiquement les écrans lorsqu’il détecte des personnes dans la pièce
- Déploiement simple et mise à jour de l’application de réunion Skype UWP (plateforme Windows universelle)
- L’AppLocker de Windows verrouille l’appareil sur l’application de réunion Skype
- Supervisé et géré en tant qu’appareil Windows 10 Entreprise via Intune et Configuration Manager (GPM)
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
