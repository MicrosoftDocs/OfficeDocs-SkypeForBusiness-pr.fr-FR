---
title: Configurer l’Connecter conférence
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Découvrez comment configurer l’opérateur Connecter Conferencing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257507"
---
# <a name="configure-operator-connect-conferencing"></a>Configurer l’Connecter conférence

Cet article explique en détail comment configurer l’opérateur Connecter conférence pour votre organisation et vos utilisateurs.

Avant de configurer la Connecter conférence de l’opérateur, lisez Plan pour l’opérateur Connecter [conférence](operator-connect-conferencing-plan.md) pour plus d’informations sur les avantages et les exigences en matière de gestion des licences.

Les rubriques abordés dans cet article sont les suivantes :

- [Configurer un opérateur](#set-up-an-operator)
- [Acquérir des numéros pour votre pont d’audioconférence](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Envoi d’appels sortants à partir Microsoft Teams réunions par le biais d’un opérateur](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Gérer vos opérateurs](#manage-your-operators)
- [Publier les numéros de votre pont d’audioconférence](#release-numbers-from-your-audio-conferencing-bridge)
- [Informations supplémentaires sur la gestion de l’audioconférence Microsoft](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurer un opérateur

Vous pouvez configurer, modifier et supprimer des opérateurs dans le Centre Teams’administration. Dans le volet de navigation gauche, allez à **Voice > Opérateurs.**

Pour configurer un opérateur :

1. **Choisissez un opérateur.**   Dans  **l’onglet Tous les** opérateurs, filtrez les opérateurs disponibles par région ou service pour trouver l’opérateur qui   vous permet de répondre à vos besoins vocables. Ensuite, sélectionnez l’opérateur que vous voulez utiliser. Pour l Connecter conférence de conférence, vérifiez que la liste **Conférence** est répertoriée en tant que produit disponible pour votre opérateur.

2. **Sélectionnez les pays.**   Sous  **Paramètres de l’opérateur,** sélectionnez les pays que vous voulez activer avec l’opérateur sélectionné.

3. **Fournir des informations de contact**   Vos informations de contact, y compris votre nom complet et votre adresse de messagerie, seront partagées avec votre opérateur. Vous pourrez modifier ces informations ultérieurement. En outre, vous devez fournir la taille de l’entreprise, avec la possibilité de fournir votre numéro de téléphone. Les opérateurs utilisent ces informations pour vous contacter afin d’obtenir plus de détails sur l’Connecter conférence.

4. Acceptez l’avis de transfert de données.

5. **Ajoutez votre opérateur.**   Sélectionnez  **Ajouter en tant qu’opérateur**   pour enregistrer.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Acquérir des numéros pour votre pont d’audioconférence

Le pont d’audioconférence de votre organisation inclut des numéros de téléphone disponibles pour tous les utilisateurs de votre organisation qui peuvent participer Microsoft Teams réunions en ligne avec des numéros de téléphone PSTN. Vous pouvez voir les numéros de téléphone associés au pont d’audioconférence de votre organisation dans le Centre d’administration Teams sous Ponts de > **conférence.**

Pour acquérir des numéros de téléphone pour votre pont d’audioconférence, suivez les étapes suivantes :

1. **Abonnement ou opérateur AudioConférence Standard Connecter licence Conférence.** Les utilisateurs qui ont besoin de numéros d’opérateur Connecter Conferencing pour participer aux réunions qu’ils organisent doivent avoir une licence d’abonnement AudioConférence Standard ou une licence Opérateur Connecter Conférence qui leur est attribuée. Pour plus d’informations, [voir Plan d’Connecter conférence.](operator-connect-conferencing-plan.md)

2. **Acquérir des nombres.**   Allez sur le site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour obtenir la liste des sites web d’opérateurs, voir l Microsoft 365 [de Connecter de recherche.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, voir Rechercher votre [ID Microsoft 365 client.](/onedrive/find-your-office-365-tenant-id) Une fois la commande terminée par votre opérateur, celui-là charge les numéros vers votre client. Vous pouvez afficher les numéros et le fournisseur dans le centre d Teams’administration en cantant sur les numéros > Téléphone **voix.**

3. **Attribuez des numéros à votre pont de conférence audio.** Vous pouvez affecter des numéros à votre pont de conférence audio à partir du centre d’administration Teams sous Réunions et ponts > **conférence > Ajouter.** Pour plus d’informations, [voir Modifier les numéros de téléphone sur votre pont d’audioconférence.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

>[!NOTE]
>Vous ne pouvez pas affecter les numéros d’Connecter de conférence par défaut d’un pont. Lorsqu’un numéro de téléphone est affecté à votre pont de conférence audio, il est répertorié dans la page Rechercher un numéro **local** inclus dans les invitations aux réunions des utilisateurs de votre organisation titulaires d’une licence d’audioconférence ou d’un opérateur Connecter Conférence.
>
>Pour router les appels sortants via un opérateur, consultez la section Envoi d’appels [**sortants**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) à partir Teams les réunions via une section de l’opérateur plus bas dans cet article.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs

 Cette étape est facultative.

Les numéros de téléphone par défaut d’un utilisateur sont inclus dans ses invitations lorsqu’il planifiera une réunion. Vous pouvez mettre à jour les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs dans le Centre d’administration Teams sous Utilisateurs > **Gérer les utilisateurs.** Pour mettre à jour les numéros de téléphone inclus dans  les invitations aux réunions des utilisateurs, sélectionnez l’utilisateur, puis sélectionnez Modifier dans la section **Audioconférence.**

Une fois les modifications appliquées, les nouvelles invitations aux réunions des organisateurs incluront les nouveaux numéros de téléphone par défaut. Toutefois, les invitations aux réunions existantes qui ont été programmées avant la modification conservent les numéros par défaut d’origine.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Envoi d’appels sortants à partir Microsoft Teams réunions par le biais d’un opérateur

Si vous avez un abonnement Microsoft Audioconférence Standard ou une licence d’opérateur Connecter Conferencing, vous pouvez configurer le service d’audioconférence pour router tout ou partie des appels sortants des réunions Teams via votre opérateur en configurant une stratégie de routage de l’audioconférence.

>[!NOTE]
>Avec une licence Connecter de conférence, les appels sortants peuvent uniquement passer par votre opérateur. Si vous avez des licences d Connecter conférence de conférence, vous devez configurer le service comme décrit ci-dessous pour activer les appels sortants des réunions Teams vers des numéros de téléphone.

Vous pouvez appliquer des stratégies de routage d’audioconférence au niveau de l’utilisateur, ce qui signifie que votre opérateur a route uniquement les appels sortants des réunions Teams organisées par les utilisateurs ayant la stratégie associée. Vous pouvez également appliquer ces stratégies au niveau global, ce qui signifie que votre opérateur a route les appels sortants à partir de Teams réunions organisées par tous les utilisateurs de votre organisation.

À l’aide de PowerShell, créez la nouvelle stratégie de routage de l’audioconférence de votre organisation. Pour spécifier un opérateur comme itinéraire principal pour les appels sortants de Teams réunions, suivez les étapes ci-dessous à l’aide des commandes PowerShell indiquées :

1. [Étape 1 : ajouter une nouvelle chaîne à la stratégie d’utilisation PSTN en ligne](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Étape 2 : créer une stratégie d’itinéraire vocal en ligne](#step-2-create-a-new-online-voice-route-policy)
3. [Étape 3 : créer une stratégie de routage d’audioconférence en ligne](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Étape 4 : affecter la nouvelle stratégie aux utilisateurs](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Étape 1 : ajouter une nouvelle chaîne à la stratégie d’utilisation PSTN en ligne

Pour plus d’informations sur l’utilisation de cette cmdlet, lisez [Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage)

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Étape 2 : créer une stratégie d’itinéraire vocal en ligne

Pour plus d’informations sur l’utilisation de cette cmdlet, lisez [Set-CsOnlineVoiceRoute.](/powershell/module/skype/set-csonlinevoiceroute)

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Étape 3 : créer une stratégie de routage d’audioconférence en ligne

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Étape 4 : affecter la nouvelle stratégie aux utilisateurs

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>Pour définir une stratégie de routage d’audioconférence comme globale et l’appliquer à tous les utilisateurs de votre organisation, vous pouvez utiliser le paramètre à la ``-Global`` place du ``-Identity`` paramètre. Par exemple, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` .

Lorsque vous créez une stratégie de routage d’audioconférence et l’appliquez à un utilisateur, l’opérateur qui fournit le numéro de téléphone spécifié dans les itinéraires du paramètre Teams des appels sortants vers des numéros de téléphone ``BridgeSourcePhoneNumber`` PSTN. En outre, le paramètre spécifie le numéro de téléphone à utiliser comme numéro de téléphone d’identification de ligne d’appel des appels sortants vers des numéros de téléphone ``BridgeSourcePhoneNumber`` PSTN.

Le modèle spécifié dans la forme est de type regex, et spécifie les appels ``NumberPattern`` à router via votre opérateur. Le modèle de l’exemple ci-dessus correspond à tous les appels ``"\d+"`` sortants Teams réunions. Vous pouvez également définir le paramètre NumberPattern qui correspond aux numéros composés avec les  ``“^\+1(425|206)(\d{7})$”`` formats suivants : +1 425 XXX XX XX ou +1 206 XXX XX XX, ou qui correspond aux numéros composés au format suivant : ``“^\+1(\d{10})$”`` +1 425 XXX XX XX.

Une fois que vous affectez une stratégie de routage de l’audioconférence à un utilisateur, tous les appels entre ses réunions et  un numéro de téléphone qui  correspond à la stratégie de routage de l’audioconférence spécifiée traversent votre opérateur, y compris m’appeler aux appels et appels lancés par l’intermédiaire de l’option Inviter quelqu’un ou composer un numéro de réunion.

## <a name="manage-your-operators"></a>Gérer vos opérateurs

Dans **l’onglet Mes** opérateurs, vous pouvez afficher vos opérateurs, leur statut et apporter les modifications   suivantes à vos sélections :

- Gérer les services d’opérateur par pays
- Suspendre un opérateur
- Supprimer un opérateur

>[!NOTE]
>Avant de supprimer un opérateur de votre organisation ou d’un pays, vous devez supprimer tous les numéros de téléphone affectés aux utilisateurs et votre pont de conférence audio, puis contactez l’opérateur pour libérer les numéros.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Publier les numéros de votre pont d’audioconférence

Pour libérer des numéros de téléphone à partir de votre pont de conférence audio à partir du Centre d’administration Teams, consultez les étapes d’affectation d’un numéro de téléphone de **service** dans le pont de conférence. Modifiez les numéros de téléphone sur votre pont de conférence [audio.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Informations supplémentaires sur la gestion de l’audioconférence Microsoft

Pour plus d’informations sur la gestion de l’audioconférence Microsoft pour votre organisation, consultez les articles suivants :

- Gestion des paramètres du service d’audioconférence Microsoft pour votre organisation : gérer les [paramètres](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) d’audioconférence de votre organisation dans Microsoft Teams

- Gestion du paramètre du service d’audioconférence Microsoft des utilisateurs de votre organisation : gérer les [paramètres](manage-the-audio-conferencing-settings-for-a-user-in-teams.md) d’audioconférence d’un utilisateur dans Microsoft Teams

- Modification des langues du attendant automatique de vos numéros de téléphone d’audioconférence : définir les langues du attendant automatique pour [l’audioconférence dans Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
