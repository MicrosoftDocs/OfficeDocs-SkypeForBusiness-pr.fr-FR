---
title: Quelles sont les équipes live événements ?
author: TonySmith
ms.author: tonysmit
manager: serdars
ms.date: 7/11/2018
ms.topic: article
ms.service: msteams
ms.reviwer: tonysmit
description: Découvrez comment Live événements permettent aux utilisateurs de diffusion vidéo et de contenu à grande audience en ligne Microsoft Teams, Yammer et Microsoft Stream.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a00d9e25b68380a6b44346f0eef628b8aa5c1308
ms.sourcegitcommit: 11adc15c5191d7bf6bb37058cae3d54649c25e97
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2018
ms.locfileid: "20364641"
---
# <a name="what-are-teams-live-events"></a>Quelles sont les équipes live événements ?
**Résumé**: Découvrez comment live événements permettent aux utilisateurs de diffusion vidéo et de contenu à grande audience en ligne Microsoft Teams, Yammer et Microsoft Stream.

## <a name="overview"></a>Vue d’ensemble
Événements en direct dans 365 de Microsoft permettent aux utilisateurs de diffusion vidéo et de contenu au grand public en ligne dans Microsoft Teams, Yammer et [Flux de Microsoft](https://docs.microsoft.com/en-us/stream/).    

Teams Microsoft offre collaboration basée sur la conversation, l’appel, réunions et des événements live, vous pouvez développer l’audience de vos réunions.  Événements live Teams Microsoft est une extension de réunions d’équipes, permettant aux utilisateurs de diffusion vidéo, le contenu et la réunion à un grand public en ligne. Ceux-ci sont destinés à un nombre de communications où l’hôte de l’événement entraîne les interactions et la participation d’audience est principalement à visualiser le contenu partagé par l’hôte. Les participants peuvent voir l’événement direct ou enregistré dans Yammer, équipes et/ou Microsoft Stream et peut interagir avec les présentateurs via modéré Q & r ou conversation Yammer. 

Les équipes événements live est considérée comme la prochaine version de diffusion de réunion Skype et finira par remplacent les fonctionnalités fournies dans Skype réunion diffusion. Pour la version d’évaluation d’événements en direct, Microsoft continuera prendre en charge de Skype réunion diffusion, sans interruption de service pour les événements de nouveau ou futurs. Nous vous invitons à essayer d’événement dans les équipes à tirer parti des nouvelles fonctionnalités, notamment, de partage d’écran et le nombre de participants, en direct et prise en charge des encodeurs matérielles et logicielles externes. 

Connexes : [les équipes Microsoft live vue d’ensemble des événements](https://support.office.com/en-us/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US).

## <a name="key-components"></a>Principaux composants
Le diagramme suivant illustre les composants de niveau élevés impliqués dans 365 Microsoft les événements en direct. 

![Événements live équipes](media/teams-live-events.png)

### <a name="scheduling"></a>La planification
Les équipes offre la possibilité pour les organisateurs créer un événement avec le participant approprié des autorisations, désigner des membres de l’équipe événement, sélectionnez inviter les participants production méthode. Si l’événement live a été créé à partir d’un groupe de Yammer, les participants direct sera en mesure d’utiliser Yammer conversation pour interagir avec l’équipe de l’événement. 

### <a name="production"></a>Production
Les événements dans 365 Microsoft live prend en charge un large éventail de scénarios de production, incluez un événement de démarrage rapide à l’aide des webcams ou d’un événement de codage externe à l’aide d’équipement de qualité studio. L’entrée vidéo est la base des événements live et il peut varier d’une webcam doit être unique à une production vidéo professionnelle caméra multiple. Clients peuvent choisir de ces options en fonction de leurs besoins du projet et de votre budget. 
- **Guide de démarrage rapide**: la méthode de démarrage rapide permet à utilisateur générer leurs événements en direct à l’aide de réunions d’équipes. Cette option est idéale si vous souhaitez utiliser l’audio et des périphériques vidéo connecté à l’ordinateur de bureau et/ou invitant des présentateurs à distance / spéciaux pour participer à l’événement.  Cette option permet aux utilisateurs d’utiliser leurs webcams facilement et de partager leur écran comme entrée à la diffusion.  
- **Codage externe (bientôt disponible)**: encodeurs externes permettent aux utilisateurs de créer leurs événements live directement à partir d’un matériel externe ou un logiciel d’encodeur avec Microsoft Stream.  Cette option est recommandée si vous disposez déjà d’un équipement de qualité studio (par exemple, le mixage media) qui prend en charge la diffusion en continu à un service RTMP.  Cette option est généralement utilisée dans les événements à grande échelle telles que des conférences entre les cadres – où un flux unique à partir d’un mixage multimédia est diffusée à l’audience.  

### <a name="streaming-platform"></a>Plateforme de diffusion en continu
Cela est composée des éléments suivants.

#### <a name="azure-media-services"></a>Services multimédias Azure
[Azure Media Services](https://docs.microsoft.com/en-us/azure/media-services/previous/) vous donne la qualité de la diffusion des services de diffusion en continu vidéo pour atteindre le plus grand public sur les appareils mobiles les plus populaires d’aujourd'hui. Media Services améliore l’accessibilité, de distribution et l’évolutivité et rend facile et économique en continu dans votre magasin local et dans le monde entier, tout en protégeant votre contenu.

#### <a name="azure-content-delivery-network-cdn"></a>Réseau Azure livraison de contenu (CDN)
Une fois votre flux de données publié, il est fourni par le biais du [Azure réseau CDN (Content Delivery)](https://docs.microsoft.com/en-us/azure/cdn/). Azure Media Services fournit CDN intégrée pour la diffusion en continu-points de terminaison. Ainsi, pour votre flux de données à afficher dans le monde entier avec aucune mise en mémoire tampon. 

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise Content Delivery Network (eCDN) 
L’objectif d’eCDN consiste à prendre le contenu vidéo à partir d’internet et distribuer le contenu de l’entreprise sans affecter les performances réseau. Vous pouvez utiliser ce qui suit partenaires certifiés pour optimiser votre réseau pour les événements live : 
- Ruche
- Kollective
- Ramp (bientôt disponible au démarrage rapide)

### <a name="attendee-experience"></a>Expérience de participant
L’expérience de participant est le plus important d’événements en direct et il est fondamental que les participants peuvent participer à l’événement live sans problème. L’expérience de participant utilise le lecteur Media Azure et fonctionne sur le bureau, navigateur et mobile (Android, iOS). Microsoft 365 fournit Yammer et les équipes deux concentrateurs de collaboration, ainsi que le participant live expérience est intégrée à ces outils de collaboration.  Les événements live en fonction de codage externe sont également accessibles par les participants dans le portail Microsoft Stream.

## <a name="prerequisites"></a>Conditions requises

### <a name="who-can-create-live-events"></a>Qui peut créer des événements en direct
Les conditions préalables suivantes sont requises pour l’utilisateur planifier un événement en direct de la période d’aperçu :   
- Utilisateur dispose d’une licence Office 365 entreprise E3 ou E5. 
- Utilisateur est activé pour Microsoft Teams, Skype pour Business Online et Microsoft Stream.
- Utilisateur est activé pour la planification de la réunion privée dans les équipes (TeamsMeetingPolicy-AllowPrivateMeetingScheduling est défini sur True).
- Utilisateur est activé pour la planification d’événements live dans les équipes (TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling est défini sur True).
- Utilisateur dispose d’autorisations pour créer des événements en temps réel dans Microsoft Stream (pour la production de codage externe).

> [!NOTE]
> O365 invités, les utilisateurs fédérés et anonymes ne peuvent pas être invitées en tant que producteurs ou présentateurs dans les événements live équipes. 
 
### <a name="who-can-watch-live-event"></a>Qui peut voir direct
Consultez le tableau ci-dessous pour voir qui peuvent participer à un événement en direct. 

|Visibilité de participant           |Guide de démarrage rapide  |Codage externe  |
|------------------------------|-------------|------------------|
|Public (utilisateurs anonymes)      |  Oui        |  Non              |
|Les utilisateurs invités *                   |  Non         |  Non              |
|Tout le monde dans fédérés société * |  Non         |  Non              |
|Tout le monde de société           |  Oui        |  Oui             |
|Propres groupes / personnes      |  Oui        |  Oui             |
* Utilisateurs invités et fédérés peuvent joindre en tant que participants anonymes événement en direct.

Une licence Office 365 est nécessaire pour participer à un événement live en tant qu’un utilisateur authentifié, en fonction de la méthode de production.

- **Production de début pour rapide**: l’utilisateur doit être un utilisateur d’équipes.
- **Production d’encodeur pour externes**: l’utilisateur doit être un utilisateur de flux de données.
 
## <a name="capabilities"></a>Fonctionnalités
Le tableau suivant met en évidence les fonctionnalités principales offertes dans les événements en direct et les différences entre la diffusion de réunion Skype. 

|Fonctionnalité   |Diffusion de réunion Skype |Événements live équipes (démarrage rapide) |Événements live équipes (codage externe) |
|---------|---------|---------|---------|
|Taille maximale d’audience |10 000 participants |10 000 participants |10 000 participants |
|Création de l’événement en direct |   Portail du service de diffusion de réunion de Skype |Les équipes, Yammer via des équipes | Les équipes, Yammer via des équipes de flux |
|Engagement de l’audience – Yammer |& #x 2714 ; |& #x 2714 ; (expérience intégrée) |& #x 2714 ; (expérience intégrée) |
|Engagement de l’audience – modéré de Q & r |& #x 2714 ;  |& #x 2714 ; |& #x 2714 ; |
|Client producteur sur Windows |& #x 2714 ; (Skype pour les entreprises) |& #x 2714 ; (Équipes) |& #x 2714 ; (Incorporer des équipes via le flux de flux) |
|Client producteur sur Mac |X  | & #x 2714 ; (Équipes) |& #x 2714 ; (Incorporer des équipes via le flux de flux) |
|Nombre de participants dans l’interface utilisateur producteur |X  |& #x 2714 ; (Équipes) |& #x 2714 ; (Incorporer des équipes via le flux de flux) |
|Permet à plusieurs présentateurs |& #x 2714 ; (Skype pour les entreprises) |& #x 2714 ; (Équipes) |N/D  |
Inviter un présentateur au cours de la réunion |& #x 2714 ; (Skype pour les entreprises) |X |N/D |
|Jointure présentateur sur le Web et Mobile |& #x 2714 ; (Skype pour les entreprises)  |X |N/D |
|Présentateur – accès PSTN |X |& #x 2714 ; (Équipes) |N/D |
|Présenter un écran |X |& #x 2714 ; (Équipes) |N/D |
|Présenter un fichier PowerPoint (PPT partage) |& #x 2714 ; |X (atténué via le partage d’écran) |N/D |
|Enregistrement de la réunion en fonction de nuage |& #x 2714 ; |& #x 2714 ; |& #x 2714 ; |
|Automatique publier un enregistrement dans le flux de Microsoft |X |X |& #x 2714 ; |
|Traduction et légendes en temps réel |& #x 2714 ; |& #x 2714 ; (bientôt disponible) |X |
|Légendes dans enregistrements live |& #x 2714 ; |& #x 2714 ; (bientôt disponible) |& #x 2714 ; |
|Contrôles DVR Attendee (pause, arrière) |& #x 2714 ; |& #x 2714 ; |& #x 2714 ; |
|Partenaire eCDN prise en charge |& #x 2714 ; (La ruche, Kollective, Ramp) |& #x 2714 ; (bientôt disponible) |& #x 2714 ; (La ruche, Kollective, Ramp) |
|Rapport de participation à une diffusion postérieures aux producteurs |& #x 2714 ; |& #x 2714 ; (bientôt disponible) |X |
|Analyse du public ressenti – vote Live et sondages |& #x 2714 ; (Pulse Microsoft) |X |X |

## <a name="planning--setup"></a>Planification et configuration
Cet article explique comment vous pouvez configurer les utilisateurs avec des équipes live événements dans votre organisation.

1. Vérifier les [événements en direct régionale disponibilité pour les équipes](#configure-live-events) pour comprendre les régions événements en direct sont actuellement disponibles dans.
2. Si vous n’avez pas déjà fait, définir [Skype pour Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e) pour votre organisation.
3. Si vous avez des participants rejoignant à partir du réseau d’entreprise, tenez compte des embarquement et [la configuration d’un fournisseur eCDN - recommandés par Microsoft](#set-up-ecdn-provider-for-teams-live-events) pour optimiser la bande passante du réseau. 
4. Vérifiez les attributions de licence approprié pour [qui peut créer des événements en direct](#who-can-create-live-events) et [qui peut surveiller les événements en direct](#who-can-watch-live-event). 
5. [Activer la planification d’événements live](#enable-live-event-scheduling-for-the-user) pour les utilisateurs qui doivent être en mesure de créer des événements en temps réel de votre société. Cela est nécessaire pour les événements de codage externe & démarrage rapide. 
6. Pour les événements de codage externe, [Activer les utilisateurs pour la création d’événements en direct dans le portail d’administration de flux de données de Microsoft](#enable-microsoft-stream-for-users-in-the-organization).  

### <a name="regional-availability-for-teams-live-events"></a>Disponibilité régionale pour les événements live équipes
Vous pouvez utiliser des événements en direct équipes dans plusieurs régions. Les informations suivantes affichent la disponibilité pour les participants et les membres de l’équipe événement. La région pour l’événement est automatiquement sélectionnée en fonction de l’organisateur et le client Office 365.

#### <a name="regions-available"></a>Régions disponibles
- Amérique
- Europe/Afrique
- Asie-Pacifique

#### <a name="exclusions"></a>Exclusions
- Passez des variables locales
  - Au Royaume-Uni, en Inde et autres variables atteindre des équipes Microsoft locales ne sont pas pris en charge actuellement.
- Accédez à Local - Canada 
  - Dans l’aperçu, les clients peuvent créer des événements, mais leurs données seront hébergées dans la région Amérique du Nord.
- Chine
  - Les participants et les membres de l’équipe événement ne sera pas en mesure d’utiliser des événements en direct équipes car Azure CDN n’est pas accessible en Chine. Une solution de contournement consiste à utiliser une connexion VPN, qui obtient le client connecté au CDN via le réseau d’entreprise du client de la société.

### <a name="set-up-your-network-for-teams-live-events"></a>Configurez votre réseau pour les équipes événements en direct 
Accédez à [configuration du réseau pour les événements live équipes](https://review.docs.microsoft.com/en-us/MicrosoftTeams/teams-live-events-set-up-your-network?branch=teams-live-events).

### <a name="set-up-ecdn-provider-for-teams-live-events"></a>Fournisseur eCDN pour les équipes de configurer des événements en direct
À venir.

### <a name="enable-live-event-scheduling-for-the-user"></a>Activer la planification d’événements live pour l’utilisateur
La planification d’événements live est activée par défaut pour un utilisateur d’équipes.  

Utilisez le paramètre AllowBroadcastScheduling dans TeamsMeetingBroadcastPolicy dans PowerShell équipes pour contrôler si l’utilisateur peut créer des événements en temps réel dans les équipes ou non.  Vous pouvez en savoir plus sur la gestion des TeamsMeetingBroadcastPolicy avec Office 365 PowerShell [ici](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui est activée par défaut de l’enregistrement. 

 Pour un utilisateur de secours pour la stratégie globale, utilisez l’applet de commande suivante pour supprimer l’affectation d’une stratégie spécifique pour un utilisateur.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Pour modifier la valeur de AllowBroadcastScheduling dans la stratégie globale, utilisez l’applet de commande suivante :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="scenarios"></a>Scenarios
**Je veux tous les utilisateurs de votre société pour être en mesure de créer des événements en direct.**
1. Confirmer Global CsTeamsMeetingBroadcastPolicy a AllowBroadcastScheduling = True.
2. Vérifiez tous les utilisateurs ont la globale ou CsTeamsMeetingBroadcastPolicy l’une des stratégies CsTeamsMeetingBroadcastPolicy avec AllowBroadcastScheduling = True.

**Je souhaite la majorité des mes utilisateurs puissent créer des événements en direct, mais je veux désactiver sélectivement des utilisateurs spécifiques qui ne sont pas autorisés à.**
1. Confirmer Global CsTeamsMeetingBroadcastPolicy a AllowBroadcastScheduling = True.
2. Vérifiez la majorité des utilisateurs ont le globale ou CsTeamsMeetingBroadcastPolicy l’une des stratégies CsTeamsMeetingBroadcastPolicy avec AllowBroadcastScheduling = True.
3. Vérifiez tous les autres utilisateurs ont été accordées à l’une des stratégies CsTeamsMeetingBroadcastPolicy avec AllowBroadcastScheduling = False.

**Je veux planification d’événements live à 100 % désactivé.**
1. Confirmer Global CsTeamsMeetingBroadcastPolicy a AllowBroadcastScheduling = False.
2. Confirmer le Global CsTeamsMeetingBroadcastPolicy ou l’une des stratégies CsTeamsMeetingBroadcastPolicy avec AllowBroadcastScheduling ont été accordées à tous les utilisateurs = False.

**Je veux événements en direct à désactivé pour la majorité des utilisateurs, mais activer des utilisateurs spécifiques pour les événements en direct.** 
1. Confirmer Global CsTeamsMeetingBroadcastPolicy a AllowBroadcastScheduling = False.
2. Vérifiez la majorité des utilisateurs ont été accordées le Global CsTeamsMeetingBroadcastPolicy ou l’une des stratégies CsTeamsMeetingBroadcastPolicy avec AllowBroadcastScheduling = False.
3. Vérifiez tous les autres utilisateurs ont été accordées à l’une des stratégies CsTeamsMeetingBroadcastPolicy avec AllowBroadcastScheduling = True.

### <a name="enable-creation-of-external-encoder-based-live-events-for-users"></a>Activer la création d’événements live encodeur externes pour les utilisateurs

#### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Activer Microsoft Stream pour les utilisateurs dans l’organisation
Stream Microsoft est disponible dans le cadre des abonnements Office 365 éligibles ou en tant que service autonome. Pour plus d’informations, voir [Présentation des flux de licences](https://docs.microsoft.com/en-us/stream/license-overview) . Remarque Microsoft Stream n’est pas inclus dans les plans Business Essentials et entreprise Premium.  

Pour plus d’informations sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs peuvent accéder à Microsoft Stream.  Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [cet article](https://docs.microsoft.com/en-us/stream/disable-user-organization).

#### <a name="ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Vérifiez les utilisateurs ont l’autorisation de création d’événement live dans Microsoft Stream
Par défaut, tout le monde peut créer du contenu dans le flux de données, une fois que le flux est activée et la licence est attribuée à l’utilisateur. Administrateur de Microsoft Stream peut [empêcher les employés pour la création de contenu](https://docs.microsoft.com/en-us/stream/restrict-uploaders) dans le flux. Les utilisateurs qui figurent dans cette liste restreinte ne sera pas en mesure d’enregistrer les réunions.

#### <a name="ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Vérifiez les événements live organisateurs souhaitez la stratégie d’entreprise définie par l’administrateur de flux
Si un administrateur de Microsoft Stream a [configurer une stratégie d’instructions entreprise](https://docs.microsoft.com/en-us/stream/company-policy-and-consent) et exige que les employés accepter cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent faire avant de créer un événement en direct (avec la production de codage externe) dans Microsoft Teams. Avant de vous déploiement événements live fonctionnalité dans l’organisation, assurez-vous que les utilisateurs qui créeront des ces événements en direct ont accepté à la stratégie. 

## <a name="configure-live-events"></a>Configurer des événements en direct

### <a name="set-up-event-support-link-coming-soon"></a>Configurer le lien de prise en charge d’événement (bientôt disponible)
Il s’agit le lien qui s’affichera pour les participants de l’événement en direct. 

PowerShell

Dans Windows PowerShell, exécutez l’applet de commande suivante :
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>Configurer les options de visibilité de participant
Ainsi, événement live organisateurs créer des événements avec visibilité attendee approprié.

|Valeurs  |Comportement  |
|---------|---------|
|Tout le monde     |L’utilisateur dispose d’une option pour créer des événements en temps réel avec la visibilité attendee suivantes : Public, tout le monde dans la société et des personnes spécifiques. |
|EveryoneInCompany     |L’utilisateur dispose d’une option pour créer des événements en temps réel avec la visibilité attendee suivantes : tout le monde dans la société et des personnes spécifiques. L’utilisateur ne peut pas créer des événements en temps réel qui peuvent être contrôlés par des utilisateurs anonymes.|
|InvitedUsers |L’utilisateur peut uniquement créer des événements en temps réel qui sont limitées à des personnes spécifiques entré par l’organisateur de l’événement.  L’utilisateur ne peut pas créer des événements live avec Public et tout le monde dans l’authentification de la société. |

PowerShell

Utilisez le paramètre BroadcastAttendeeVisibility dans TeamsMeetingBroadcastPolicy dans PowerShell pour contrôler si les utilisateurs peuvent planifier la diffusion des événements qui peuvent être surveillés par les participants anonymes. Pour plus d’informations sur la gestion des TeamsMeetingBroadcastPolicy avec Office 365 PowerShell ici.  

Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui a la valeur EveryoneInCompany par défaut. 
 
Dans Windows PowerShell, exécutez la cmdlet suivante pour permettre aux utilisateurs de créer des événements anonyme dans la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Configurer les options d’enregistrement
> [!NOTE]
> Cette option ne s’applique aux événements qui utilisent la méthode de production de démarrage rapide uniquement.

Cela permet d’administrateurs au contrôle si les événements live sont toujours enregistrées, jamais enregistrées ou si l’organisateur de l’événement peut décider d’enregistrer l’événement ou non.  

|Valeurs  |Comportement  |
|---------|---------|
|Toujours activé |Les événements live organisées par cet utilisateur sont toujours enregistrées.  Utilisateur n’est pas une option pour remplacer.  Si l’événement live est enregistré, les membres de l’équipe des événements sont en mesure de télécharger l’enregistrement après l’événement et les participants peuvent suivre l’événement après l’événement. |
|AlwaysDisabled |Les événements live organisées par cet utilisateur ne sont jamais enregistrées.  Utilisateur n’est pas une option pour remplacer.  Si l’événement live est enregistré, aucun enregistrement n’est créé pour les membres de l’équipe d’événement et les participants ne peuvent pas voir l’événement après l’avoir sur. |
|UserOverride |Utilisateur peut décider si l’événement live est enregistré pour un fichier d’enregistrement peut être créé pour les membres de l’équipe d’événement et les participants peuvent suivre l’événement après l’événement. |

PowerShell

Utilisez le paramètre BroadcastRecordingMode dans TeamsMeetingBroadcastPolicy dans PowerShell pour contrôler des options des événements live créés par l’organisateur de l’événement live d’enregistrement.

Dans Windows PowerShell, exécutez l’applet de commande suivante pour mettre à jour le mode d’enregistrement de la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurer la transcription en temps réel et traduction dans événements live équipes (bientôt disponible)
> [!NOTE]
> Cette option ne s’applique aux événements qui utilisent la méthode de production de démarrage rapide uniquement.

Cela permet d’organisateurs d’événement live activer les légendes en temps réel et translation pour les participants de l’événement en direct. 

PowerShell

Utilisez le paramètre AllowBroadcastTranscription dans TeamsMeetingBroadcastPolicy dans PowerShell pour contrôler si les participants direct sera en mesure de voir que vous pouvez en savoir plus sur la gestion des TeamsMeetingBroadcastPolicy avec Office 365 PowerShell ici.  

Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui possède la transcription et traduction désactivée par défaut.

Dans Windows PowerShell, exécutez l’applet de commande suivante pour activer la transcription et traduction sur des participants de l’événement dans la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $True 
```
## <a name="self-service-administration-tools"></a>Outils d’administration en libre-service 
Bien que Microsoft directement aux contrôles de tous les centres de données Office 365 en ligne et est chargé de performances globales du système, il peut contrôler qu’une partie des éléments qui associent pour fournir l’expérience pour les utilisateurs d’Office 365. Les entreprises se sont responsables pour les connexions réseau vers les centres de données, le réseau du client étendu (WAN), et du client réseau local (LAN). En outre, ils sont chargés de périphériques de l’utilisateur et leur configuration.Ils sont également chargés de gérer les licences requises par l’utilisateur pour n’importe quelle fonctionnalité souhaitée, y compris, mais non limité à la possibilité de gérer ces fonctionnalités, pour tant que l’utilisateur a besoin d’accéder à la fonctionnalité.

Clients pouvant utiliser les outils suivants pour gérer un grand nombre de tâches associées d’équipes événements en direct.
- [Centre d’administration Microsoft Office 365](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams et Skype pour le centre d’administration Business en ligne](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Centre d’administration de Microsoft Stream
- [À distance Windows PowerShell](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?
- Lorsqu’il s’agit de Windows PowerShell, toutes ses sur la gestion des utilisateurs et que les utilisateurs sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :

- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

