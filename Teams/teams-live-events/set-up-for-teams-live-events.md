---
title: Configurer des événements live dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Découvrez les étapes pour configurer live pour les événements dans Microsoft Teams, y compris la préparation de votre réseau, attribution de licences, activation de la planification pour les utilisateurs et configuration d’un fournisseur eCDN d’événements live.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354363"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurer des événements live dans Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Lorsque vous configurez pour les événements en direct, il existe plusieurs étapes à suivre :

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Étape 1 : Configurer votre réseau pour les événements live dans Microsoft Teams
Les événements live démarrage rapide requièrent pour [préparer le réseau de votre organisation pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
Disposer des attributions de licence approprié pour [qui peut créer et planifier les événements live ?](#who-can-create-and-schedule-live-events) et [qui peut surveiller les événements en direct ?](#who-can-watch-live-events).

## <a name="step-3-enable-live-event-scheduling-for-users"></a>Étape 3 : Activer la planification d’événements live pour les utilisateurs
Planification d’événements Live est activée par défaut pour les utilisateurs des équipes, mais si vous sont souhaitant aux utilisateurs de planifier des événements de codage externe des étapes supplémentaires que vous devez faire.

### <a name="for-quick-start-events"></a>Pour les événements de démarrage rapide
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

#### <a name="user-scenarios"></a>Scénarios utilisateur
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

### <a name="for-external-encoder-events"></a>Pour les événements de codage externe
Vous devez effectuer les opérations suivantes pour activer live événement planification pour les utilisateurs.

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Étape 1 : Activer Microsoft Stream pour les utilisateurs dans votre organisation **
Stream Microsoft est disponible dans le cadre des abonnements Office 365 éligibles ou en tant que service autonome. Pour plus d’informations, voir [Présentation des flux de licences](https://docs.microsoft.com/stream/license-overview) .

> ! [NOTE] Stream Microsoft n’est pas inclus dans les plans Business Essentials et entreprise Premium.  

Pour plus d’informations sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs peuvent accéder à Microsoft Stream. Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Étape 2 : Vérifiez que les utilisateurs habilités à direct création de flux Microsoft **
Par défaut, les administrateurs peuvent créer codage externe événements en direct. L’administrateur Microsoft Stream peut [permettre aux utilisateurs supplémentaires pour la création de l’événement live](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) dans le flux.  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Étape 3 : Vérifiez l’événement live organisateurs souhaitez la stratégie d’entreprise définie par le flux de données d’administration **
Si un administrateur de Microsoft Stream a [configurer une stratégie d’instructions entreprise](https://docs.microsoft.com/stream/company-policy-and-consent) et exige que les employés accepter cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent faire avant de créer un événement en direct (avec la production de codage externe) dans les équipes. Avant la mise en œuvre la fonctionnalité événements en temps réel de l’organisation, assurez-vous que les utilisateurs qui créeront des ces événements en direct ont accepté à la stratégie. 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Étape 4 : Configurer eCDN fournisseur pour les événements live dans Microsoft Teams 
Lecture de vidéos direct utilise adaptive vitesse de transmission en continu (TBD), mais il s’agit d’un flux de monodiffusion, ce qui signifie que chaque visionneuse est l’obtention de leur propres flux vidéo à partir d’internet. Pour les événements en direct ou vidéos envoyés à une grande partie de votre organisation, il peut être une grande quantité de bande passante internet consommée par des utilisateurs. Pour les organisations qui veulent réduire ce trafic internet pour les événements en direct, des événements live solutions intégrées à Microsoft approuvé partenaires de remise vidéo proposant des logiciels définis réseaux (SDNs) ou des réseaux de livraison de contenu d’entreprise (eCDNs). Ces SDN / eCDN plateformes permettent aux organisations d’optimiser la bande passante réseau sans compromettre les utilisateurs finaux une expérience de visualisation. Nos partenaires peuvent aider à activer une distribution vidéo plus évolutive et efficace entre votre réseau d’entreprise.

**Le programme d’installation & achat votre solution en dehors de Microsoft Teams** Obtenir de l’aide avec montée en puissance de diffusion vidéo en tirant parti de partenaires de Microsoft remise vidéo approuvé. Avant de pouvoir activer un fournisseur de remise vidéo être utilisés dans les équipes, vous devez acheter et du programme d’installation de la solution SDN/eCDN extérieur et distincte des équipes.

Les solutions SDN/eCDN suivantes sont intégrées préalable et peuvent être le programme d’installation pour une utilisation avec Microsoft Stream.

- **La ruche de diffusion en continu** fournit une solution simple et puissante de distribution vidéo entreprise direct et à la demande. Ruche est une solution logicielle qui ne nécessite aucun matériel supplémentaire ou la bande passante et offre un moyen sécurisé pour activer des milliers d’utilisateurs vidéo simultanés sans impact sur votre réseau. Pour les clients souhaitant pour comprendre que rencontre la vidéo de l’impact sur leur réseau avant l’achat d’une solution SDN/eCDN, la ruche de diffusion en continu fournit également une solution d’analytique basés sur navigateur pour les clients de Microsoft. [En savoir plus](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** est une nuage, smart homologation distribution plateforme qui tire parti de votre infrastructure de réseau existant pour fournir un contenu, dans de nombreux écrans, (live flux vidéo, vidéo à la demande, mises à jour logicielles, les correctifs de sécurité, etc.) plus rapide, plus fiable, avec moins de bande passante. Notre plateforme sécurisée est approuvée par les institutions financières plus grandes du monde et aucun matériel supplémentaire, le programme d’installation et de maintenance faciles. [En savoir plus](http://www.kollective.com).
 
- **Ramp OmniCache** assure la distribution réseau nouvelle génération et transparente livraison de contenu vidéo sur des réseaux étendus globaux, aider les producteurs événement optimiser la bande passante réseau et prend en charge les diffusions événement réussie en direct et à la demande diffusion en continu. La prise en charge pour Ramp OmniCache pour les événements de démarrage rapide live seront prochainement disponibles.  [En savoir plus](http://www.ramp.com). 
 
> [!NOTE] 
> Sélectionnées **termes du fournisseur 3e partie de la stratégie de confidentialité et de service**, qui régit l’utilisation de la solution du fournisseur eCDN sujette à votre solution eCDN que vous avez choisie. L’utilisation de la solution du fournisseur eCDN ne sera pas soumis aux conditions de licence en volume Microsoft ou des termes du contrat de Services en ligne. Si vous n’acceptez pas les **termes du contrat de 3 fournisseur tiers**, puis n’activez pas la solution eCDN dans les équipes. 

**Configurer un eCDN pour « Démarrage rapide » des événements en direct** Vous pouvez configurer le fournisseur eCDN pour les événements live dans les équipes à l’aide de PowerShell. 

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

## <a name="next-steps"></a>Étapes suivantes
Accédez à [Confgure équipes événements en direct](configure-teams-live-events.md).
