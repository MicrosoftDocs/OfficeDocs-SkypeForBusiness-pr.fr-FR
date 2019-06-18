---
title: Configurer des événements en direct dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez les étapes nécessaires à la configuration des événements en direct dans Teams, y compris la préparation de votre réseau, l’attribution de licences, l’utilisation de stratégies pour activer les fonctionnalités d’événement en direct et la planification pour les utilisateurs et la configuration d’un fournisseur de distribution tiers.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7f69f036e01c86dd02eabf7f229a80f0c51c520
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2019
ms.locfileid: "35012996"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurer des événements en direct dans Microsoft Teams

Lorsque vous configurez des événements en direct, vous devez suivre plusieurs étapes:

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>Étape 1: configuration de votre réseau pour les événements en direct dans teams
Les événements en direct produits dans teams vous demandent de [préparer le réseau de votre organisation aux équipes](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
Vérifiez que vous disposez des attributions de licence appropriées pour les [personnes autorisées à créer et à planifier des événements](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events) en direct et [qui peuvent regarder des événements en direct](plan-for-teams-live-events.md#who-can-watch-live-events).

## <a name="step-3-set-up-live-events-policies"></a>Étape 3: configurer les stratégies d’événements dynamiques
Les stratégies d’événements dynamiques permettent de contrôler les utilisateurs de votre organisation qui peuvent contenir des événements en direct et les fonctionnalités disponibles dans les événements qu’ils créent. Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies d’événements dynamiques personnalisés. Lorsque vous créez une stratégie personnalisée, attribuez-la à un utilisateur ou à un groupe d’utilisateurs de votre organisation.

> [!NOTE]
> Les utilisateurs de votre organisation obtiendront la stratégie globale sauf si vous créez et attribuez une stratégie personnalisée. Par défaut, la planification d’événements en temps réel est activée pour les utilisateurs Teams, la transcription est désactivée, tous les membres de l’organisation peuvent participer aux événements en direct et le paramètre d’enregistrement est défini sur toujours enregistrer. 

### <a name="create-or-edit-a-live-events-policy"></a>Création ou modification d’une stratégie d’événements en direct
<a name="bkcreatepolicy"> </a>

**![Icône illustrant le logo](../media/teams-logo-30x30.png) de Microsoft teams à l’aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, accédez à **réunions** > **Live Events**. 
2. Effectuez l’une des actions suivantes :
- Si vous voulez modifier la stratégie par défaut existante, sélectionnez **globale (par défaut pour l’organisation)**. 
- Si vous voulez créer une nouvelle stratégie personnalisée, sélectionnez **nouvelle stratégie**. 
- Si vous voulez modifier une stratégie personnalisée, sélectionnez-la, puis choisissez **modifier**. 

    Voici les paramètres que vous pouvez modifier pour répondre aux besoins de votre organisation.

    ![Capture d’écran des paramètres de stratégie d’événements en temps réel] (../media/teams-live-events-policies.png "Capture d’écran des paramètres de stratégie d’événements en temps réel dans le centre d’administration Microsoft teams") 

|Paramètre  |Description  |
|---------|---------|
|**Nom**     |Il s’agit du nom de la stratégie qui s’affiche dans la page stratégies d’événements dynamiques. Il ne peut pas contenir plus de 64 caractères, ni contenir des caractères spéciaux.          |
|**Description**    |Utilisez cette opération pour ajouter une description conviviale de la stratégie.         |
|**Autoriser la planification**     |L’activation de cette option permet aux utilisateurs de votre organisation de créer et de planifier des événements en direct dans Teams. Il est important de savoir que si vous souhaitez que les utilisateurs planifient un événement en direct obtenu à l’aide d’une application ou d’un appareil externe, vous devez effectuer des étapes supplémentaires. Pour en savoir plus, voir [permettre aux utilisateurs de planifier des événements qui ont été produits avec un appareil ou une application externe](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).     |
|**Autoriser la transcription pour les participants** (bientôt disponible) |Ce paramètre ne peut être appliqué qu’aux événements produits dans Teams. L’activation de cette fonction permet aux participants en temps réel d’afficher des légendes et des traductions en temps réel lors de l’événement.         |
|**Qui peut participer à des événements en direct programmés**    |Choisissez l’une des options suivantes.<br><br>**Tout le monde** Les utilisateurs peuvent créer des événements en direct que tout le monde, y compris les personnes externes à votre organisation, peuvent participer. Ce paramètre active le type d’autorisation **public** dans teams lorsqu’un utilisateur planifie un événement en direct.<br> **Tout le monde au sein de l’organisation** Les utilisateurs peuvent créer des événements en direct que seules les personnes de votre organisation peuvent participer. Les utilisateurs ne peuvent pas créer d’événements en direct qui sont contrôlés par des utilisateurs anonymes. Ce paramètre active le type d’autorisation à l’échelle de l' **organisation** dans teams lorsqu’un utilisateur planifie un événement en direct.<br> **Utilisateurs ou groupes spécifiques** Les utilisateurs peuvent créer des événements en direct qui peuvent être participants à des utilisateurs ou des groupes spécifiques de votre organisation. Les utilisateurs ne peuvent pas créer d’événements en direct qui sont contrôlés par tous les utilisateurs de votre organisation ou par des utilisateurs anonymes. Ce paramètre active le type d’autorisation **personnes et groupes** dans teams lorsqu’un utilisateur planifie un événement en direct.       |
|**Paramètre d’enregistrement**  <br>     | Ce paramètre ne peut être appliqué qu’aux événements produits dans Teams. Choisissez l’une des options suivantes. <br><br> **Toujours enregistrer** Les événements en direct créés par les utilisateurs sont toujours enregistrés. Après l’événement, les membres de l’équipe peuvent télécharger l’enregistrement et les participants peuvent la voir. <br> **Ne jamais enregistrer** Les événements en direct créés par les utilisateurs ne sont jamais enregistrés. <br>L' **organisateur peut enregistrer ou non** Les utilisateurs peuvent décider d’enregistrer l’événement en direct. S’il est enregistré, après l’événement, les membres de l’équipe peuvent télécharger l’enregistrement et les participants peuvent la voir.      

Vous pouvez également effectuer cette opération à l’aide de Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique [Utiliser PowerShell pour définir les stratégies d’événements dynamiques dans teams](set-teams-live-events-policies-using-powershell.md). 

### <a name="assign-a-live-events-policy-to-users"></a>Assigner une stratégie d’événements en direct aux utilisateurs 

Si vous avez créé une stratégie d’événements dynamiques personnalisée, attribuez-la aux utilisateurs pour que la stratégie soit active. 

![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft teams

1. Dans le volet de navigation gauche, accédez à **utilisateurs**, puis sélectionnez l’utilisateur.
2. En regard de **stratégies affectées**, choisissez **modifier**. 
3. Sélectionnez la stratégie d’événements en direct que vous voulez attribuer, puis cliquez sur **Enregistrer**. 

Vous pouvez également affecter une stratégie d’événements en direct à un ou plusieurs utilisateurs comme suit:

![Icône affichant le logo Microsoft teams](../media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft teams

1. Accédez à **réunions** > **Live Events**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>Permettre aux utilisateurs de planifier des événements qui ont été produits avec une application ou un appareil externe

Pour que les utilisateurs puissent planifier des événements produits avec une application ou un appareil externe, vous devez également procéder comme suit:

1. Activez Microsoft Stream pour les utilisateurs de votre organisation. Le flux est disponible dans le cadre des abonnements Office 365 éligibles ou d’un service autonome. Le flux n’est pas inclus dans les offres Business Essentials ou Business Premium. Pour plus d’informations, voir [vue d’ensemble des licences de flux](https://docs.microsoft.com/stream/license-overview) .

      Apprenez-en davantage sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365 de manière à](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) ce que les utilisateurs puissent accéder au flux. Assurez-vous que le flux n’est pas bloqué pour les utilisateurs tels que définis dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).

2. Assurez-vous que les utilisateurs ont une autorisation de création d’événements en direct dans le flux. Par défaut, les administrateurs peuvent créer des événements avec un appareil ou une application externe. L’administrateur de flux peut [permettre aux utilisateurs supplémentaires de créer des événements en direct](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) dans le flux.  

3. Assurez-vous que les organisateurs d’événements en direct peuvent être envoyés à la stratégie d’entreprise définie par l’administrateur de flux. Si un administrateur de flux a [configuré une stratégie d’instructions de société](https://docs.microsoft.com/stream/company-policy-and-consent) et nécessite l’acceptation des employés de cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent le faire avant de créer un événement en direct (avec une application ou un appareil externe) dans Teams. Avant de déployer la fonctionnalité événements en direct au sein de l’organisation, assurez-vous que les utilisateurs qui créeront ces événements en direct pourront être envoyés à la stratégie. 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>Étape 4: configurer une solution de distribution vidéo pour les événements en direct dans teams
La lecture de vidéos d’événements en direct utilise le flux de débit adaptatif (ABR), mais il s’agit d’un flux de monodiffusion, ce qui signifie que chaque visionneuse obtient son propre flux vidéo à partir d’Internet. Pour les événements en direct ou les vidéos envoyées à de grandes parties de votre organisation, il est possible qu’il y ait une quantité importante de bande passante Internet consommée par les utilisateurs. Pour les organisations qui souhaitent réduire le trafic Internet pour les événements en direct, les solutions d’événements en direct sont intégrées aux partenaires de distribution de contenu vidéo de Microsoft qui proposent des réseaux de distribution de contenu (SDNs) ou des réseaux de distribution de contenu d’entreprise (eCDNs). Ces plates-formes SDN/eCDN permettent aux organisations d’optimiser la bande passante du réseau sans sacrifier les expériences d’affichage des utilisateurs finaux. Nos partenaires peuvent vous permettre d’offrir une distribution vidéo plus évolutive et plus efficace sur votre réseau d’entreprise.

**Achat et configuration de votre solution en dehors de teams** Obtenez une aide pour la mise à l’échelle de la vidéo grâce aux partenaires de distribution de vidéo approuvés par Microsoft. Avant de pouvoir configurer un fournisseur de remise vidéo pour une utilisation avec Teams, vous devez acheter et configurer la solution SDN/eCDN en dehors de teams.

Les solutions SDN/eCDN suivantes sont pré-intégrées et peuvent être configurées pour être utilisées avec le flux.

- La fonction **streaming en continu** fournit une solution simple et puissante pour une distribution vidéo professionnelle en direct et à la demande. Hive est une solution logicielle qui ne nécessite pas de matériel ou de bande passante supplémentaire et offre un moyen sécurisé d’activer des milliers de visionneuses vidéo simultanées sans impact sur votre réseau. Pour les clients qui cherchent à comprendre la vidéo d’impact sur leur réseau avant de procéder à l’achat d’une solution SDN/eCDN, la fonction de diffusion en continu de ruche fournit également une solution d’analyse basée sur le navigateur pour les clients Microsoft. [En savoir plus](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** est une plateforme de distribution d’homologation intelligente basée sur le Cloud qui tire parti de votre infrastructure réseau existante pour diffuser du contenu, sous différentes formes, (diffusion en continu de vidéos, vidéo à la demande, mises à jour de logiciels, correctifs de sécurité, etc.) plus rapide, plus fiabilité et réduction de la bande passante. Notre plate-forme sécurisée est digne de confiance par les plus grandes institutions financières du monde et sans aucun matériel supplémentaire, aucune configuration et maintenance n’est facile. [En savoir plus](http://www.kollective.com).
 
- **RAMP OmniCache** fournit une distribution réseau nouvelle génération et garantit une remise transparente du contenu vidéo sur les réseaux WAN généraux, permettant aux producteurs d’événements d’optimiser la bande passante du réseau et de prendre en charge les diffusions d’événements en direct et à la demande. transmission. La prise en charge de RAMP OmniCache pour les événements en direct produits dans teams sera bientôt prise en charge. [En savoir plus](http://www.ramp.com). 
 
> [!NOTE] 
> Votre solution SDN ou eCDN sélectionnée est soumise aux **conditions générales de service et à la politique de confidentialité du prestataire**tiers, qui régit l’utilisation de la solution du fournisseur. Votre utilisation de la solution du fournisseur ne sera pas soumise aux termes du contrat de licence en volume Microsoft ou des services en ligne. Si vous n’êtes pas d’accord avec les **conditions du fournisseur**tiers, n’activez pas la solution dans Teams. 

Après avoir configuré la solution SDN ou eCDN, vous pouvez configurer le fournisseur pour les événements en direct dans Teams. 

## <a name="next-steps"></a>Étapes suivantes
Accédez à [configurer les paramètres des événements en direct dans teams](configure-teams-live-events.md).

### <a name="related-topics"></a>Voir aussi
- [Que sont les événements en direct Teams ?](what-are-teams-live-events.md)
- [Offre pour les événements en direct Teams](plan-for-teams-live-events.md)
- [Configurer les paramètres des événements en direct dans teams](configure-teams-live-events.md)

