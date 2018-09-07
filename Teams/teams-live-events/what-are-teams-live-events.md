---
title: Quelles sont les équipes live événements ?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
description: Découvrez comment Live événements permettent aux utilisateurs de diffusion vidéo et de contenu à grande audiences en ligne dans Microsoft Teams, Yammer et Microsoft Stream.
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfdee5d1cf43c358d2b6a36aad66c38d3e9d8ec9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870588"
---
# <a name="what-are-teams-live-events"></a>Quelles sont les équipes live événements ?
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>Vue d’ensemble
Événements en direct dans 365 de Microsoft permettent aux utilisateurs de diffusion vidéo et de contenu au grand public en ligne. Événements en direct Microsoft 365 mettez vidéo en direct à un nouveau niveau, en privilégiant une connexion tout au long du cycle de vie mission avec les participants avant, pendant et après les événements en direct. Vous pouvez créer un événement en direct où réside votre audience, équipe ou la Communauté, à l’aide de Microsoft Stream, Microsoft Teams, ou Yammer.  

Teams Microsoft assure la collaboration basée sur la conversation, appel, réunions et des événements live, donc vous pouvez développer l’audience de vos réunions. Événements live Teams Microsoft est une extension de réunions d’équipes, permettant aux utilisateurs de diffusion de contenu de réunion et vidéo à un grand public en ligne. Ils sont destinés à un-à-plusieurs communications où l’hôte de l’événement entraîne les interactions et la participation d’audience est principalement à visualiser le contenu partagé par l’hôte. Les participants peuvent voir l’événement direct ou enregistré dans Yammer, équipes et/ou Microsoft Stream et peuvent interagir avec les présentateurs à l’aide de modéré Q & A ou conversation Yammer. 

Les équipes live événements sont considérés comme étant la prochaine version de diffusion de réunion Skype et finira par remplacent les fonctionnalités fournies dans Skype réunion diffusion. Lors de la publication de la version d’évaluation d’événements en direct équipes, nous continuera prendre en charge de Skype réunion diffusion, sans interruption de service pour les événements de nouveau ou futurs. Toutefois, nous vous invitons à essayer équipes des événements en direct pour tirer parti de toutes les nouvelles fonctionnalités très intéressantes, y compris le nombre de participants, de partage d’écran et prise en charge des encodeurs matérielles et logicielles externes. 

Par conséquent, nous allons commencer. Tout d’abord, examinez le diagramme suivant qui présente les composants de niveau élevés impliquées dans 365 Microsoft les événements en direct et comment ils sont connectés. 

![Événements live équipes](../media/teams-live-events.png)

## <a name="key-components"></a>Principaux composants
Par conséquent, vous pouvez le voir dans l’image ci-dessus, il existe quatre composants clés qui sont utilisés avec les événements en temps réel dans Microsoft Teams.

### <a name="scheduling"></a>La planification
Les équipes offre la possibilité pour les organisateurs créer un événement avec le participant approprié des autorisations, désigner les événements membres de l’équipe, sélectionnez la méthode de production et inviter des participants. Si l’événement live a été créé à partir d’un groupe de Yammer, les participants direct sera en mesure d’utiliser Yammer conversation pour interagir avec des personnes dans l’événement. 

### <a name="production"></a>Production
Les événements dans 365 Microsoft live prend en charge un large éventail de scénarios de production, incluez un événement de démarrage rapide à l’aide des webcams ou d’un événement de codage externe à l’aide d’équipement de qualité studio. L’entrée vidéo est la base des événements Live et il peut varier d’une webcam doit être unique à une production vidéo professionnelle caméra multiple. Vous pouvez choisir de ces options en fonction de leurs besoins du projet et de votre budget. Il existe deux façons de générer des événements :

- **Démarrage rapide de production**: la méthode de production de démarrage rapide permet aux utilisateurs de créer leurs événements en direct à l’aide de réunions d’équipes. Cette option est idéale et une option plus rapide si vous souhaitez utiliser les périphériques audio et vidéos connecté à l’ordinateur ou invitez des présentateurs à distance pour participer à l’événement. Cette option permet aux utilisateurs d’utiliser leurs webcams facilement et de partager leur écran comme entrée dans l’événement. 


- **Production de codage externe**: encodeurs externes permettent aux utilisateurs de créer leurs événements directement à partir d’un matériel externe ou un encodeur basé sur logiciel avec [Flux Microsoft](https://stream.microsoft.com)live. Cette option est recommandée si vous disposez déjà d’équipement de qualité studio (par exemple, le mixage media) les prise en charge de la diffusion en continu à un service RTMP (Real-Time Messaging Protocol). Ce type de production est généralement utilisé dans les événements à grande échelle telles que des conférences entre les cadres – où un flux unique à partir d’un mixage multimédia est diffusée à l’audience. 

### <a name="streaming-platform"></a>Plateforme de diffusion en continu
La plate-forme de diffusion en continu live événement est composée des quatre éléments suivants :

- **Services multimédias Azure** [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) vous donne la qualité de la diffusion des services de diffusion en continu vidéo pour atteindre le plus grand public sur les appareils mobiles les plus populaires d’aujourd'hui.   Media Services améliore l’accessibilité, de distribution et l’évolutivité et rend facile et économique en continu dans votre magasin local ou dans le monde entier, tout en protégeant votre contenu.
- **Réseau Azure livraison de contenu (CDN)**  Une fois votre flux de données publié, il est fourni par le biais du [Azure réseau CDN (Content Delivery)](https://docs.microsoft.com/azure/cdn/). Azure Media Services fournit CDN intégrée pour transmettre en continu des points de terminaison. Ainsi, pour les flux de données à afficher dans le monde entier avec aucune mise en mémoire tampon.
- **Enterprise Content Delivery Network (eCDN)**  L’objectif d’eCDN consiste à prendre le contenu vidéo à partir d’internet et distribuer le contenu dans toute l’entreprise sans affecter les performances réseau. Vous pouvez utiliser une des options suivantes eCDN partenaires certifiés pour optimiser votre réseau pour les événements Live organisées au sein de votre organisation :
    - Ruche
    - Kollective
    - Ramp
- **Expérience de participant**  L’expérience de participant est le plus important d’événements en direct et il est fondamental que les participants peuvent participer à l’événement live sans avoir des problèmes. L’expérience de participant utilise le lecteur Media Azure et fonctionne sur le bureau, navigateur et mobile (Android, iOS). Office 365 propose Yammer et les équipes deux concentrateurs de collaboration, ainsi que le participant live expérience est intégrée à ces outils de collaboration. Les événements live en fonction de codage externe sont également accessibles par les participants dans les [Outils d’administration](#administrative-tools).

## <a name="planning-for-live-events"></a>Planification des événements en direct
Lorsque vous planifiez les événements en direct équipes destiné à contenir des grandes réunions dans votre générer, il existe plusieurs facteurs que vous devez prendre en compte avant de commencer à définir ascendants. 

### <a name="who-can-create-and-schedule-live-events"></a>Qui peut créer et planifier les événements live ? 
Les conditions préalables suivantes sont requises pour l’utilisateur planifier un événement live équipes.

Voici les licences qui doivent être affectés :  
- Une licence Office 365 entreprise E3 ou E5. 
- Un Teams Microsoft, les Skype pour les entreprises et de licence Microsoft Stream.

Il est important de savoir qu’une licence Office 365 est nécessaire pour participer à un événement live en tant qu’utilisateur authentifié mais cela dépend de la méthode de production utilisée :

- **Production de début pour rapide**  L’utilisateur doit être affecté à une licence Microsoft Teams.
- **Production d’encodeur pour externe** L’utilisateur doit être affecté à une licence Microsoft Stream.

Pour plus d’informations sur les licences, voir [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).

L’utilisateur doit avoir :
- Planifier des réunions privées dans les équipes activés (*- AllowPrivateMeetingScheduling TeamsMeetingPolicy le paramètre = True*).
- Live planification d’événements dans les équipes activés (*- AllowBroadcastScheduling TeamsMeetingBroadcastPolicy le paramètre = True*).
- Autorisations pour créer des événements en temps réel dans Microsoft Stream (pour la [production de codage externe](#production)).

> [!IMPORTANT]
> Office 365 invités, les utilisateurs fédérés et anonymes ne peuvent pas être invitées en tant que producteurs ou présentateurs dans les événements live équipes. Toutefois, vous pouvant joindre invités et des utilisateurs fédérés en tant que participants anonymes événement en direct. 
 
### <a name="who-can-watch-live-events"></a>Qui peut voir les événements en direct ?

|**Visibilité de participant**           |**Guide de démarrage rapide** |**Codage externe**  |
|------------------------------|-------------|------------------|
|Public (utilisateurs anonymes)      |  Oui        |  Non              |
|Utilisateurs invités                   |  Non         |  Non              |
|Tout le monde dans une entreprise fédérée |  Non         |  Non              |
|Tout le monde de société           |  Oui        |  Oui             |
|Propres groupes / personnes      |  Oui        |  Oui             |
 
### <a name="teams-live-events-and-skype-meeting-broadcast"></a>Événements en direct équipes et la diffusion de réunion Skype
Le tableau suivant met en évidence les fonctionnalités principales et les fonctionnalités offertes par les événements en direct et les différences entre la diffusion de réunion Skype. 

|**Fonctionnalité**   |**Diffusion de réunion Skype** |**Événements live équipes (démarrage rapide)** |**Événements live équipes (codage externe)** |
|---------|---------|---------|---------|
|Taille maximale d’audience |10 000 participants |10 000 participants * |10 000 participants * |
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
|Partenaire eCDN prise en charge |& #x 2714 ; (La ruche, Kollective, Ramp) |& #x 2714 ; (Ruche, Kollective) |& #x 2714 ; (La ruche, Kollective, Ramp) |
|Rapport de participation à une diffusion postérieures aux producteurs |& #x 2714 ; |& #x 2714 ; (version feature) |X |
|Analyse du public ressenti – vote Live et sondages |& #x 2714 ; (Pulse Microsoft) |X |X |

> [!IMPORTANT]
> Les limites définies peuvent être modifiés.

### <a name="regional-availability"></a>Disponibilité régionale
Vous pouvez utiliser événements live équipes dans plusieurs régions du monde. Les informations suivantes affichent la disponibilité pour les participants et les membres de l’équipe événement. 

> [!IMPORTANT]
> La région pour l’événement est automatiquement sélectionnée en fonction de l’organisateur et l’organisation Office 365.

**Disponible dans ces régions.**
- Amérique
- Europe/Afrique
- Asie-Pacifique
- Accédez au Canada Local

**Exclusions et considérations**
- **Accédez variables locales :** Royaume-Uni Unitied (Royaume-Uni), en Inde et autres variables atteindre des équipes Microsoft locales ne sont pas pris en charge actuellement.
- **Chine :** Les participants et les membres de l’équipe événement ne sera pas en mesure d’utiliser des événements en direct équipes car Azure CDN n’est pas accessible en Chine. Une solution de contournement consiste à utiliser une connexion VPN, qui obtient le client connecté au CDN via le réseau d’entreprise du client de la société.

## <a name="setting-up-for-live-events"></a>Configuration pour les événements en direct
Lorsque vous configurez pour les événements en direct, il existe plusieurs étapes à suivre :

### <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Étape 1 : Configurer votre réseau pour les événements live dans Microsoft Teams
Les événements live démarrage rapide requièrent pour [préparer le réseau de votre organisation pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

### <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
Disposer des attributions de licence approprié pour [qui peut créer et planifier les événements live ?](#who-can-create-and-schedule-live-events) et [qui peut surveiller les événements en direct ?](#who-can-watch-live-events).

### <a name="step-3-enable-live-event-scheduling-for-users"></a>Étape 3 : Activer la planification d’événements live pour les utilisateurs
Planification d’événements Live est activée par défaut pour les utilisateurs des équipes, mais si vous sont souhaitant aux utilisateurs de planifier des événements de codage externe des étapes supplémentaires que vous devez faire.

#### <a name="for-quick-start-events"></a>Pour les événements de démarrage rapide
Utilisez le paramètre *AllowBroadcastScheduling* dans **TeamsMeetingBroadcastPolicy** dans PowerShell équipes pour contrôler si l’utilisateur peut créer des événements en temps réel dans les équipes ou non. Vous en apprendrez plus sur la gestion des TeamsMeetingBroadcastPolicy [ici](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Si vous n’avez pas attribué une stratégie personnalisée assignée aux utilisateurs, les utilisateurs obtenez la stratégie *globale* , qui est activée par défaut de l’enregistrement.

Vérifiez que le paramètre *AllowBroadcastScheduling* est définie sur *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Affecter l’utilisateur à la stratégie *globale* , exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

##### <a name="user-scenarios"></a>Scénarios utilisateur
**Vous que tous les utilisateurs de votre société à être en mesure de créer des événements en direct.**

Si les utilisateurs sont affectés à la stratégie *Glocal* , exécuter et vérifiez *AllowBroadcastScheduling* * est défini sur *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si les utilisateurs sont affectés à une stratégie de la stratégie *globale* , exécutez la commande suivante et vérifiez que l’option *-AllowBroadcastScheduling* est définie sur *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Vous souhaitez direct planification désactivé 100 % au sein de votre organisation.**

Désactiver la planification de la diffusion, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Affecter tous les utilisateurs de votre organisation à la stratégie *globale* , exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Vous souhaitez un grand nombre d’utilisateurs à être en mesure de créer des événements en temps réel, mais souhaitez empêcher un ensemble d’utilisateurs de leur création.**

Attribuer la stratégie *globale* à l’aide de la **Grant-CsTeamsMeetingBroadcastPolicy** pour certains utilisateurs (que vous souhaitez activé), mais exécutez la commande suivante et vérifiez que *AllowBroadcastScheduling* est définie sur *True*, tout d’abord :
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Puis affecter un ou plusieurs utilisateurs à la stratégie *globale* , exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Créer et attribuer une stratégie permettant de désactiver la planification à l’aide de l’applet de commande **Grant-CsTeamsMeetingBroadcastPolicy** pour les autres utilisateurs (désactivé). 

Créer la nouvelle stratégie alors qu’il est désactivé, exécutez :
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Désactiver la planification, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Puis affecter des utilisateurs à cette stratégie, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Vous live événements doivent être désactivée pour un grand nombre d’utilisateurs, mais que vous souhaitez autoriser un ensemble d’utilisateurs pour les créer.**

Désactiver la planification de la diffusion, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Puis affecter ces utilisateurs à la stratégie *globale* , exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Créer et attribuer une stratégie d’activation de la planification, exécutez :
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Activer la planification, exécutez :
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Puis affecter des utilisateurs à cette stratégie, exécutez :
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

#### <a name="for-external-encoder-events"></a>Pour les événements de codage externe
Vous devez effectuer les opérations suivantes pour activer la planification d’événements Live pour ces utilisateurs.

##### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Étape 1 : Activer Microsoft Stream pour les utilisateurs dans votre organisation **
Stream Microsoft est disponible dans le cadre des abonnements Office 365 éligibles ou en tant que service autonome. Pour plus d’informations, voir [Présentation des flux de licences](https://docs.microsoft.com/stream/license-overview) .

> ! [Note] Stream Microsoft n’est pas inclus dans les plans Business Essentials et entreprise Premium.  

Pour plus d’informations sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs peuvent accéder à Microsoft Stream. Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).

##### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Étape 2 : Vérifiez que les utilisateurs habilités à direct création de flux Microsoft **
Par défaut, les administrateurs peuvent créer codage externe événements en direct. L’administrateur Microsoft Stream peut [permettre aux utilisateurs supplémentaires pour la création de l’événement live](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) dans le flux.  

##### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Étape 3 : Vérifiez l’événement live organisateurs souhaitez la stratégie d’entreprise définie par le flux de données d’administration **
Si un administrateur de Microsoft Stream a [configurer une stratégie d’instructions entreprise](https://docs.microsoft.com/stream/company-policy-and-consent) et exige que les employés accepter cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent faire avant de créer un événement en direct (avec la production de codage externe) dans Microsoft Teams. Avant la mise en œuvre la fonctionnalité événements en temps réel de l’organisation, assurez-vous que les utilisateurs qui créeront des ces événements en direct ont accepté à la stratégie. 

### <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Étape 4 : Configurer eCDN fournisseur pour les événements live dans Microsoft Teams 
Lecture de vidéos direct utilise adaptive vitesse de transmission en continu (TBD), mais il s’agit d’un flux de monodiffusion, ce qui signifie que chaque visionneuse est l’obtention de leur propres flux vidéo à partir d’internet. Pour les événements en direct ou vidéos envoyés à une grande partie de votre organisation, il peut être une grande quantité de bande passante internet consommée par des utilisateurs. Pour les organisations qui veulent réduire ce trafic internet pour les événements en direct, des événements live solutions intégrées à Microsoft approuvé partenaires de remise vidéo proposant des logiciels définis réseaux (SDNs) ou des réseaux de livraison de contenu d’entreprise (eCDNs). Ces SDN / eCDN plateformes permettent aux organisations d’optimiser la bande passante réseau sans compromettre les utilisateurs finaux une expérience de visualisation. Nos partenaires peuvent aider à activer une distribution vidéo plus évolutive et efficace entre votre réseau d’entreprise.

**Le programme d’installation & achat votre solution en dehors de Microsoft Teams** Obtenir de l’aide avec montée en puissance de diffusion vidéo en tirant parti de partenaires de Microsoft remise vidéo approuvé. Avant de pouvoir activer un fournisseur de remise vidéo à utiliser avec Microsoft Teams, vous devez acheter et du programme d’installation de la solution SDN/eCDN extérieur et Microsoft Teams distincte.

Les solutions SDN/eCDN suivantes sont intégrées préalable et peuvent être le programme d’installation pour une utilisation avec Microsoft Stream.

- **La ruche de diffusion en continu** fournit une solution simple et puissante de distribution vidéo entreprise direct et à la demande. Ruche est une solution logicielle qui ne nécessite aucun matériel supplémentaire ou la bande passante et offre un moyen sécurisé pour activer des milliers d’utilisateurs vidéo simultanés sans impact sur votre réseau. Pour les clients souhaitant pour comprendre que rencontre la vidéo de l’impact sur leur réseau avant l’achat d’une solution SDN/eCDN, la ruche de diffusion en continu fournit également une solution d’analytique basés sur navigateur pour les clients de Microsoft. [En savoir plus](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective** est une nuage, smart homologation distribution plateforme qui tire parti de votre infrastructure de réseau existant pour fournir un contenu, dans de nombreux écrans, (live flux vidéo, vidéo à la demande, mises à jour logicielles, les correctifs de sécurité, etc.) plus rapide, plus fiable, avec moins de bande passante. Notre plateforme sécurisée est approuvée par les institutions financières plus grandes du monde et aucun matériel supplémentaire, le programme d’installation et de maintenance faciles. [En savoir plus](http://www.kollective.com)
 
- **Ramp OmniCache** assure la distribution réseau nouvelle génération et transparente livraison de contenu vidéo sur des réseaux étendus globaux, aider les producteurs événement optimiser la bande passante réseau et prend en charge les diffusions événement réussie en direct et à la demande diffusion en continu. La prise en charge pour Ramp OmniCache pour les événements de démarrage rapide live seront prochainement disponibles.  [En savoir plus](http://www.ramp.com) 
 
> [!NOTE] 
> Sélectionnées **termes du fournisseur 3e partie de la stratégie de confidentialité et de service**, qui régit l’utilisation de la solution du fournisseur eCDN sujette à votre solution eCDN que vous avez choisie. L’utilisation de la solution du fournisseur eCDN ne sera pas soumis aux conditions de licence en volume Microsoft ou des termes du contrat de Services en ligne. Si vous n’acceptez pas les **termes du contrat de 3 fournisseur tiers**, puis n’activez pas la solution eCDN dans Microsoft Teams. 

**Configurer un eCDN pour « Démarrage rapide » des événements en direct** Vous pouvez configurer le fournisseur eCDN pour les événements live dans Teams Microsoft à l’aide de PowerShell. 

> [!NOTE] 
> Un fournisseur unique eCDN peut être configuré pour votre organisation. 

***La ruche*** Vous pouvez utiliser l’applet de commande [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell pour configurer eCDN fournisseur. Tout d’abord obtenir l’URL de modèle de code et les API de licence de votre contact ruche puis exécutez la commande suivante :
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** Vous pouvez utiliser l’applet de commande [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell pour configurer eCDN fournisseur. Tout d’abord obtenir le jeton d’API et l’URL de modèle API à partir de votre contact Kollective, puis exécutez la commande suivante :
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Configurer un eCDN pour les événements live « Codage externe »** 

Si vous envisagez de créer des événements en temps réel qui utilisent des encodeurs externes, vous devrez également [configurer votre fournisseur eCDN avec flux de données Microsoft](https://docs.microsoft.com/stream/network-caching) . 

## <a name="configure-live-events"></a>Configurer des événements en direct

### <a name="set-up-event-support-link"></a>Configurer le lien de prise en charge des événements
Il s’agit le lien qui s’affichera pour les participants de l’événement en direct. 

Dans Windows PowerShell, exécutez la commande suivante :
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>Configurer les options de visibilité de participant
Ainsi, événement live organisateurs créer des événements avec visibilité attendee approprié.

|**Valeurs**  |**Comportement**  |
|---------|---------|
|Tout le monde     |L’utilisateur dispose d’une option pour créer des événements en temps réel avec la visibilité attendee suivantes : Public, tout le monde dans la société et des personnes spécifiques. |
|EveryoneInCompany     |L’utilisateur dispose d’une option pour créer des événements en temps réel avec la visibilité attendee suivantes : tout le monde dans la société et des personnes spécifiques. L’utilisateur ne peut pas créer des événements en temps réel qui peuvent être contrôlés par des utilisateurs anonymes.|
|InvitedUsers |L’utilisateur peut uniquement créer des événements en temps réel qui sont limitées à des personnes spécifiques entré par l’organisateur de l’événement. L’utilisateur ne peut pas créer des événements live avec Public et tout le monde dans l’authentification de la société. |

Utilisez le paramètre BroadcastAttendeeVisibility dans TeamsMeetingBroadcastPolicy dans PowerShell pour contrôler si les utilisateurs peuvent planifier la diffusion des événements qui peuvent être surveillés par les participants anonymes. 

Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui a la valeur EveryoneInCompany par défaut. 
 
Dans Windows PowerShell, exécutez ce qui suit pour permettre aux utilisateurs de créer des événements anonyme dans la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>Configurer les options d’enregistrement
> [!NOTE]
> Cette option ne s’applique aux événements qui utilisent la méthode de production de démarrage rapide uniquement.

Cela permet d’administrateurs au contrôle si les événements live sont toujours enregistrées, jamais enregistré, ou si l’organisateur de l’événement peut décider d’enregistrer l’événement ou non.  

|**Valeurs**  |**Comportement**  |
|---------|---------|
|Toujours activé |Les événements live organisées par cet utilisateur sont toujours enregistrées. L’utilisateur n’est pas une option pour remplacer. Si l’événement live est enregistré, les membres de l’équipe des événements sont en mesure de télécharger l’enregistrement après l’événement et les participants peuvent suivre l’événement après l’événement. |
|AlwaysDisabled |Les événements live organisées par cet utilisateur ne sont jamais enregistrées. L’utilisateur n’est pas une option pour remplacer. Si l’événement live est enregistré, aucun enregistrement n’est créé pour les membres de l’équipe d’événement et les participants ne peuvent pas voir l’événement après l’avoir sur. |
|UserOverride |Utilisateur peut décider si l’événement live est enregistré afin qu’un fichier d’enregistrement peut être créé pour les membres de l’équipe d’événement et les participants peuvent suivre l’événement après l’événement. |

Utilisez le paramètre *BroadcastRecordingMode* dans **TeamsMeetingBroadcastPolicy** dans PowerShell pour contrôler des options des événements live créés par l’organisateur de l’événement live d’enregistrement.

Dans Windows PowerShell, exécutez l’applet de commande suivante pour mettre à jour le mode d’enregistrement de la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurer la transcription en temps réel et traduction dans événements live équipes (bientôt disponible)
> [!NOTE]
> Cette option ne s’applique aux événements qui utilisent la méthode de production de démarrage rapide uniquement.

Cela permet d’organisateurs d’événement live activer les légendes en temps réel et translation pour les participants de l’événement en direct. 

Utilisez le paramètre *AllowBroadcastTranscription* dans **TeamsMeetingBroadcastPolicy** dans PowerShell pour contrôler si les participants direct sera en mesure de voir la transcription et traduction. Pour plus d’informations sur la gestion des **TeamsMeetingBroadcastPolicy** avec Office 365 PowerShell ici.  

Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui possède la transcription et traduction désactivée par défaut.

Dans Windows PowerShell, exécutez l’applet de commande suivante pour activer la transcription et traduction sur des participants de l’événement dans la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="administrative-tools"></a>Outils d’administration 
Bien que Microsoft directement aux contrôles de tous les centres de données Office 365 en ligne et est chargé de performances globales du système, il peut contrôler qu’une partie des éléments qui associent pour fournir l’expérience pour les utilisateurs d’Office 365. Les entreprises se sont responsables pour les connexions réseau vers les centres de données, le réseau du client étendu (WAN), et du client réseau local (LAN). En outre, ils sont chargés de périphériques de l’utilisateur et leur configuration.Ils sont également chargés de gérer les licences requises par l’utilisateur pour n’importe quelle fonctionnalité souhaitée, y compris, mais non limité à la possibilité de gérer ces fonctionnalités, pour tant que l’utilisateur a besoin d’accéder à la fonctionnalité.

Clients pouvant utiliser les outils suivants pour gérer un grand nombre de tâches associées d’équipes événements en direct.
- [Centre d’administration Microsoft Office 365](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams et Skype pour le centre d’administration Business en ligne](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Centre d’administration de Microsoft Stream](https://stream.microsoft.com)
- [À distance Windows PowerShell](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?
Lorsqu’il s’agit de Windows PowerShell, il des informations supplémentaires sur la gestion des utilisateurs et les utilisateurs autorisés ou non autorisés. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype pour Business Online à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
 - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
 - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>Rubriques connexes : 
- [Événements en direct entre Microsoft 365 dans Yammer et Microsoft Stream Microsoft Teams](https://docs.microsoft.com/stream/live-event-m365)
- [Événements en direct dans Microsoft Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Événements en direct dans Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Événements en direct dans Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)
