---
title: Configurer des événements live dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Découvrez les étapes pour configurer live pour les événements d’équipes, y compris la préparation de votre réseau, attribution de licences, à l’aide de stratégies pour activer les fonctionnalités de l’événement en direct pour les utilisateurs de planification et configuration d’un fournisseur tiers distribution.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: a92f227b7f625da02e003622c8ff87e744206443
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2018
ms.locfileid: "25748156"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurer des événements live dans Microsoft Teams

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Lorsque vous configurez des événements en direct, il existe plusieurs étapes à suivre :

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Étape 1 : Configurer votre réseau pour les événements live dans Microsoft Teams
Démarrage rapide des événements live requièrent pour [préparer le réseau de votre organisation pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
Disposer des attributions de licence approprié pour [qui peut créer et planifier les événements live ?](#who-can-create-and-schedule-live-events) et [qui peut surveiller les événements en direct ?](#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Étape 3 : Configurer les stratégies d’événements en direct
Les stratégies sont utilisées pour contrôler les personnes de votre organisation peuvent contenir des événements en direct et les fonctionnalités qui sont disponibles dans les événements qu’ils créent des événements en direct. Vous pouvez utiliser la stratégie par défaut ou créer un ou plus personnalisé live stratégies d’événements. Après avoir créé une stratégie personnalisée, assignez-le à un utilisateur ou des groupes d’utilisateurs de votre organisation.

> [!NOTE]
> Les utilisateurs de votre organisation reçoivent la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Par défaut dans la stratégie globale, planification d’événements live est activée pour les utilisateurs des équipes, transcription est désactivée, tout le monde dans l’organisation peut participer à des événements en direct, et le paramètre d’enregistrement est défini à toujours enregistrer. 

### <a name="create-or-edit-a-live-events-policy"></a>Créer ou modifier une stratégie d’événements en direct

**![les équipes-logo-30x30.png](../media/teams-logo-30x30.png) avec le modèle Microsoft Teams & Skype entreprise centre d’administration**

1. Dans la navigation de gauche, accédez à des **réunions** > **stratégies d’événements en direct**. 
2. Effectuez l’une des actions suivantes :
- Si vous souhaitez modifier la stratégie par défaut existant, choisissez **Global (valeur par défaut à l’échelle de l’organisation)**. 
- Si vous souhaitez créer une nouvelle stratégie personnalisée, cliquez sur **nouvelle stratégie**. 
- Si vous souhaitez modifier une stratégie personnalisée, sélectionnez la stratégie, puis cliquez sur **Modifier**. 

    Voici les paramètres que vous pouvez modifier pour répondre aux besoins de votre organisation.

    ![Capture d’écran de live les paramètres de stratégie des événements] (../media/teams-live-events-policies.png "Capture d’écran de live les paramètres de stratégie des événements dans les équipes Microsoft & Skype entreprise centre d’administration") 

|Paramètre  |Description  |
|---------|---------|
|**Nom**     |Il s’agit du nom de la stratégie qui s’affiche dans la page de stratégies d’événements en direct. Il ne peut pas dépasser 64 caractères ou contient des caractères spéciaux.          |
|**Description**    |Permet d’ajouter une description conviviale de la stratégie.         |
|**Autoriser la planification**     |Activer cette fonctionnalité permet aux utilisateurs de votre organisation de créer et de planifier des événements en temps réel dans les équipes. Il est important de savoir si vous souhaitez que les utilisateurs à planifier des événements en direct codage externe, il existe des étapes supplémentaires que vous devez effectuer. Pour plus d’informations, voir [permettent aux utilisateurs de planifier des événements de codage externe](#enable-users-to-schedule-external-encoder-events).     |
|**Transcription autoriser des participants** (bientôt disponible) |Ce paramètre peut être appliqué uniquement aux événements de démarrage rapide. Participants direct des légendes en temps réel et une traduction pendant l’événement permet d’activer cette fonctionnalité.         |
|**Qui peut participer à des événements live planifiés**    |Choisissez une des options suivantes.<br> <br> **Tout le monde** Les utilisateurs peuvent créer des événements en direct tout le monde, y compris les personnes extérieures à votre organisation, peut participer. <br> **Tout le monde dans l’organisation** Les utilisateurs peuvent créer des événements en direct que seules les personnes de votre organisation peuvent participer. Les utilisateurs ne peuvent pas créer des événements live sont assistés par des utilisateurs anonymes. <br> **Utilisateurs ou groupes spécifiques** Les utilisateurs peuvent créer des événements en direct que seuls des utilisateurs spécifiques ou peuvent participer à des groupes de votre organisation. Les utilisateurs ne peuvent pas créer des événements live sont assistés par tout le monde dans votre organisation ou par les utilisateurs anonymes.        |
|**Paramètre d’enregistrement**  <br>     | Ce paramètre peut être appliqué uniquement aux événements de démarrage rapide. Choisissez une des options suivantes. <br><br> **Toujours enregistrer** Événements Live créés par les utilisateurs sont toujours enregistrées. Après l’événement, membres de l’équipe événement peuvent télécharger l’enregistrement et les participants peuvent suivre l’événement. <br> **Ne jamais faire enregistrer** Événements Live créés par les utilisateurs ne sont jamais enregistrées. <br>**Organisateur peut enregistrer ou non** Les utilisateurs peuvent décider s’il faut enregistrer l’événement live. S’il est enregistré, après l’événement, membres de l’équipe événement peuvent télécharger l’enregistrement et les participants peuvent suivre l’événement.      

Vous pouvez également procéder ainsi à l’aide de Windows PowerShell. Pour plus d’informations, voir [Utilisation de PowerShell pour définir des stratégies d’événements en direct dans les équipes](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Affecter une stratégie d’événements en direct à des utilisateurs 

Si vous avez créé une stratégie d’événements personnalisés en direct, attribuer aux utilisateurs de la stratégie soit actif. 

![les équipes-logo-30x30.png](../media/teams-logo-30x30.png) Avec le modèle Microsoft Teams & Skype entreprise centre d’administration

1. Dans la navigation de gauche, accédez à des **utilisateurs**, puis sélectionnez l’utilisateur.
2. En regard de **stratégies attribuées**, cliquez **sur Modifier**. 
3. Sélectionnez la stratégie d’événements en direct à attribuer, puis cliquez sur **Enregistrer**. 

### <a name="enable-users-to-schedule-external-encoder-events"></a>Permettre aux utilisateurs de planifier des événements de codage externe

Pour les utilisateurs à planifier des événements de codage externe, vous devez également procédez comme suit :

1. Activer Microsoft Stream pour les utilisateurs de votre organisation. Stream Microsoft est disponible dans le cadre des abonnements Office 365 éligibles ou en tant que service autonome. Stream Microsoft n’est pas inclus dans les plans Business Essentials et entreprise Premium. Pour plus d’informations, voir [Présentation des flux de licences](https://docs.microsoft.com/stream/license-overview) .

      Pour plus d’informations sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs peuvent accéder à Microsoft Stream. Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).

2. Vérifiez les utilisateurs ont l’autorisation de création d’événement live dans Microsoft Stream. Par défaut, les administrateurs peuvent créer codage externe événements en direct. L’administrateur Microsoft Stream peut [permettre aux utilisateurs supplémentaires pour la création de l’événement live](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) dans le flux.  

3. Vérifiez les événements live organisateurs souhaitez la stratégie d’entreprise définie par l’administrateur de flux de données. Si un administrateur de Microsoft Stream a [configurer une stratégie d’instructions entreprise](https://docs.microsoft.com/stream/company-policy-and-consent) et exige que les employés accepter cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent faire avant de créer un événement en direct (avec la production de codage externe) dans les équipes. Avant de déployer la fonctionnalité d’événements en temps réel dans l’organisation, assurez-vous que les utilisateurs qui créeront des ces événements en direct ont accepté à la stratégie. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Étape 4 : Configurer une solution de distribution vidéo pour les événements live d’équipes
Lecture de vidéos direct utilise adaptive vitesse de transmission en continu (TBD), mais il s’agit d’un flux de monodiffusion, ce qui signifie que chaque visionneuse est l’obtention de leur propres flux vidéo à partir d’internet. Pour les événements en direct ou vidéos envoyés à une grande partie de votre organisation, il peut être une grande quantité de bande passante internet consommée par des utilisateurs. Pour les organisations qui veulent réduire ce trafic internet pour les événements en direct, des événements live solutions intégrées à Microsoft approuvé partenaires de remise vidéo proposant des logiciels définis réseaux (SDNs) ou des réseaux de livraison de contenu d’entreprise (eCDNs). Ces plateformes SDN/eCDN permettent aux organisations d’optimiser la bande passante réseau sans compromettre les utilisateurs finaux affichage des expériences. Nos partenaires peuvent aider à activer une distribution vidéo plus évolutive et efficace entre votre réseau d’entreprise.

**Achat et configurer votre solution en dehors des équipes** Obtenir de l’aide avec montée en puissance de diffusion vidéo en tirant parti de partenaires de Microsoft remise vidéo approuvé. Avant de pouvoir activer un fournisseur de remise vidéo être utilisés dans les équipes, vous devez acheter et configurer la solution SDN/eCDN extérieur et distincte des équipes.

Les solutions SDN/eCDN suivantes sont intégrées préalable et peuvent être configurées pour être utilisé avec Microsoft Stream.

- **La ruche de diffusion en continu** fournit une solution simple et puissante de distribution vidéo entreprise direct et à la demande. Ruche est une solution logicielle qui ne nécessite aucun matériel supplémentaire ou la bande passante et offre un moyen sécurisé pour activer des milliers d’utilisateurs vidéo simultanés sans impact sur votre réseau. Pour les clients souhaitant pour comprendre que rencontre la vidéo de l’impact sur leur réseau avant l’achat d’une solution SDN/eCDN, la ruche de diffusion en continu fournit également une solution d’analytique basés sur navigateur pour les clients de Microsoft. [En savoir plus](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** est une nuage, smart homologation distribution plateforme qui tire parti de votre infrastructure de réseau existant pour fournir un contenu, dans de nombreux écrans, (live flux vidéo, vidéo à la demande, mises à jour logicielles, les correctifs de sécurité, etc.) plus rapide, plus fiable, avec moins de bande passante. Notre plateforme sécurisée est approuvée par les institutions financières plus grandes du monde et aucun matériel supplémentaire, le programme d’installation et de maintenance faciles. [En savoir plus](http://www.kollective.com).
 
- **Ramp OmniCache** assure la distribution réseau nouvelle génération et transparente livraison de contenu vidéo sur des réseaux étendus globaux, aider les producteurs événement optimiser la bande passante réseau et prend en charge les diffusions événement réussie en direct et à la demande diffusion en continu. La prise en charge pour Ramp OmniCache pour les événements de démarrage rapide live seront prochainement disponibles.  [En savoir plus](http://www.ramp.com). 
 
> [!NOTE] 
> Votre solution SDN ou eCDN choisie est soumis à sélectionnées **termes du fournisseur 3e partie de la stratégie de confidentialité et de service**, qui régit l’utilisation de la solution du fournisseur. L’utilisation de la solution du fournisseur ne sera pas soumis aux conditions de licence en volume Microsoft ou des termes du contrat de Services en ligne. Si vous n’acceptez pas les **termes du contrat de 3 fournisseur tiers**, puis n’activez pas la solution dans les équipes. 

Après avoir configuré la solution SDN ou eCDN, vous êtes prêt à configurer le fournisseur pour les événements en direct dans les équipes. 

## <a name="next-steps"></a>Étapes suivantes
Accédez à [Confgure live paramètres des événements dans les équipes](configure-teams-live-events.md).

### <a name="related-topics"></a>Rubriques connexes
- [Quelles sont les équipes live événements ?](what-are-teams-live-events.md)
- [Planifier des équipes événements en direct](plan-for-teams-live-events.md)
- [Confgure live paramètres des événements dans les équipes](configure-teams-live-events.md)

