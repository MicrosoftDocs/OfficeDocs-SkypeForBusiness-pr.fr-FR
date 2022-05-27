---
title: Configurer Conférence en connexion à l'opérateur
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
description: En savoir plus sur la configuration de Conférence en connexion à l'opérateur.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ade65551ad30c15fd209aa542781edce44bd76dd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676026"
---
# <a name="configure-operator-connect-conferencing"></a>Configurer Conférence en connexion à l'opérateur

Cet article explique comment configurer Conférence en connexion à l'opérateur pour votre organisation et vos utilisateurs.

Avant de configurer Conférence en connexion à l'opérateur, lisez [Plan for Conférence en connexion à l'opérateur pour](operator-connect-conferencing-plan.md) plus d’informations sur les avantages et les exigences de licence.

Les rubriques traitées dans cet article sont les suivantes :

- [Configurer un opérateur](#set-up-an-operator)
- [Acquérir des numéros pour votre pont Audioconférence](#acquire-numbers-for-your-audio-conferencing-bridge)
- [Modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [Envoi d’appels sortants à partir de réunions Microsoft Teams par le biais d’un opérateur](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [Gérer vos opérateurs](#manage-your-operators)
- [Libérer des numéros de votre pont Audioconférence](#release-numbers-from-your-audio-conferencing-bridge)
- [Informations supplémentaires sur la gestion de Microsoft Audioconférence](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>Configurer un opérateur

Vous pouvez configurer, modifier et supprimer des opérateurs dans le centre d’administration Teams. Dans le volet de navigation gauche, accédez à **Opérateurs de > voix**.

Pour configurer un opérateur :

1. **Choisissez un opérateur.** Sous l’onglet **Tous les opérateurs** , filtrez les opérateurs disponibles par région ou service pour trouver l’opérateur approprié pour vos besoins vocaux. Ensuite, sélectionnez l’opérateur que vous souhaitez utiliser. Pour Conférence en connexion à l'opérateur, vérifiez que la conférence de votre opérateur est **répertoriée** en tant que produit disponible.

2. **Sélectionnez des pays.** Sous **Paramètres de l’opérateur**, sélectionnez les pays que vous souhaitez activer avec votre opérateur sélectionné.

3. **Fournir des informations de contact** Vos informations de contact, y compris votre nom complet et votre adresse e-mail, seront partagées avec votre opérateur. Vous pouvez modifier ces informations ultérieurement. En outre, vous devez fournir la taille de l’entreprise, avec la possibilité de fournir votre numéro de téléphone. Les opérateurs utilisent ces informations pour vous contacter avec plus de détails sur Conférence en connexion à l'opérateur.

4. Acceptez l’avis de transfert de données.

5. **Ajoutez votre opérateur.** Sélectionnez **Ajouter en tant qu’opérateur** à enregistrer.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>Acquérir des numéros pour votre pont Audioconférence

Le pont Audioconférence de votre organisation inclut des numéros de téléphone disponibles pour tous les utilisateurs de votre organisation afin de participer à Microsoft Teams réunions avec des numéros de téléphone RTC. Vous pouvez voir les numéros de téléphone associés au pont Audioconférence de votre organisation dans le centre de Teams Administration sous **Meetings > Conference Bridges**.

Pour acquérir des numéros de téléphone pour votre pont Audioconférence, procédez comme suit :

1. **Audioconférence licence d’abonnement standard ou de Conférence en connexion à l'opérateur.** Les utilisateurs qui ont besoin de numéros Conférence en connexion à l'opérateur pour participer aux réunions qu’ils organisent doivent disposer d’une licence d’abonnement Standard Audioconférence ou d’une licence Conférence en connexion à l'opérateur qui leur est attribuée. Pour plus d’informations, consultez [Plan for Conférence en connexion à l'opérateur](operator-connect-conferencing-plan.md).

2. **Acquérir des nombres.** Accédez au site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour obtenir la liste des sites web des opérateurs, accédez au [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, consultez [Rechercher votre ID de locataire Microsoft 365](/onedrive/find-your-office-365-tenant-id). Une fois que votre opérateur aura terminé la commande, il chargera les numéros vers votre locataire. Vous pouvez afficher les nombres et le fournisseur dans le centre d’administration Teams en accédant aux **numéros De voix > Téléphone**.

3. **Attribuez des numéros à votre pont Audioconférence.** Vous pouvez affecter des numéros à votre pont Audioconférence à partir du centre d’administration Teams sous **Meetings > Conference Bridges > Add**. Pour plus d’informations, consultez [Modifier les numéros de téléphone sur votre pont Audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

>[!NOTE]
>Vous ne pouvez pas affecter Conférence en connexion à l'opérateur nombres en tant que nombres par défaut d’un pont. Une fois qu’un numéro de téléphone est affecté à votre pont Audioconférence, ce numéro est répertorié dans la **page Rechercher un numéro local** inclus dans les invitations aux réunions des utilisateurs de votre organisation disposant d’une licence Audioconférence ou d’une licence Conférence en connexion à l'opérateur.
>
>Pour acheminer les appels sortants via un opérateur, consultez [**l’envoi d’appels sortants à partir de Teams réunions via une section opérateur**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) plus bas dans cet article.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>Modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs

 Cette étape est facultative.

Les numéros de téléphone par défaut d’un utilisateur sont ceux inclus dans les invitations à la réunion lorsqu’il planifie une réunion. Vous pouvez mettre à jour les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs du centre Teams Administration sous **Utilisateurs > Gérer les utilisateurs**. Pour mettre à jour les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs, sélectionnez l’utilisateur, puis **sélectionnez Modifier** dans la section **Audioconférence**.

Une fois les modifications appliquées, les nouvelles invitations aux réunions des organisateurs incluent les nouveaux numéros de téléphone par défaut. Toutefois, les invitations aux réunions existantes qui ont été planifiées avant la modification conserveront les numéros par défaut d’origine.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>Envoi d’appels sortants à partir de réunions Microsoft Teams par le biais d’un opérateur

Si vous disposez d’un abonnement Microsoft Audioconférence Standard ou d’une licence Conférence en connexion à l'opérateur, vous pouvez configurer le service Audioconférence pour router tout ou un ensemble d’appels sortants à partir de réunions Teams via votre opérateur en configurant un Audioconférence stratégie de routage.

>[!NOTE]
>Avec une licence Conférence en connexion à l'opérateur, les appels sortants peuvent uniquement passer par votre opérateur. Si vous avez Conférence en connexion à l'opérateur licences, vous devez configurer le service comme décrit ci-dessous pour activer les appels sortants depuis Teams réunions vers des numéros de téléphone.

Vous pouvez appliquer Audioconférence stratégies de routage au niveau de l’utilisateur, ce qui signifie que votre opérateur achemine uniquement les appels sortants à partir de Teams réunions organisées par les utilisateurs avec la stratégie associée. Vous pouvez également appliquer ces stratégies au niveau global, ce qui signifie que votre opérateur achemine les appels sortants à partir de Teams réunions organisées par tous les utilisateurs de votre organisation.

À l’aide de PowerShell, créez la nouvelle stratégie de routage Audioconférence de votre organisation. Pour spécifier un opérateur comme itinéraire principal pour les appels sortants à partir de Teams réunions, suivez les étapes ci-dessous à l’aide des commandes PowerShell indiquées :

1. [Étape 1 : Ajouter une nouvelle chaîne à la stratégie d’utilisation PSTN en ligne](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [Étape 2 : Créer une stratégie de routage vocal en ligne](#step-2-create-a-new-online-voice-route-policy)
3. [Étape 3 : Créer une stratégie de routage en ligne Audioconférence](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [Étape 4 : Affecter la nouvelle stratégie aux utilisateurs](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>Étape 1 : Ajouter une nouvelle chaîne à la stratégie d’utilisation PSTN en ligne

Lisez [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) pour plus d’informations sur l’utilisation de cette applet de commande.

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>Étape 2 : Créer une stratégie de routage vocal en ligne

Lisez [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) pour plus d’informations sur l’utilisation de cette applet de commande.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>Étape 3 : Créer une stratégie de routage en ligne Audioconférence

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>Étape 4 : Affecter la nouvelle stratégie aux utilisateurs

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>Pour définir une stratégie de routage Audioconférence comme globale et l’appliquer à tous les utilisateurs de votre organisation, vous pouvez utiliser le ``-Global`` paramètre au lieu du ``-Identity`` paramètre. Par exemple, ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"``.

Lorsque vous créez une stratégie de routage Audioconférence et l’appliquez à un utilisateur, l’opérateur qui fournit le numéro de téléphone spécifié dans le ``BridgeSourcePhoneNumber`` paramètre achemine Teams appels sortants vers des numéros de téléphone RTC. En outre, le ``BridgeSourcePhoneNumber`` paramètre spécifie le numéro de téléphone à utiliser comme numéro de téléphone d’identification de ligne d’appel des appels sortants vers des numéros de téléphone RTC.

Le modèle spécifié dans le ``NumberPattern`` formulaire est de forme régulière, et il spécifie les appels à acheminer via votre opérateur. Le ``"\d+"`` modèle de l’exemple ci-dessus correspond à tous les appels sortants de Teams réunions. Vous pouvez également définir le paramètre NumberPattern en tant que  ``"^\+1(425|206)(\d{7})$"``, qui correspond aux numéros composés avec les formats suivants : +1 425 XXX XX XX ou +1 206 XXX XX XX XX, ou ``"^\+1(\d{10})$"``, qui correspond aux numéros composés au format suivant : +1 425 XXX XX XX.

Une fois que vous avez affecté une stratégie de routage Audioconférence à un utilisateur, tous les appels de leurs réunions à un numéro de téléphone correspondant à l’expression régulière spécifiée dans leur Audioconférence itinéraires de stratégie de routage via votre opérateur, y compris **m’appeler aux** appels et appels lancés via **l’option Inviter une personne ou composer une réunion numérotée**.

## <a name="manage-your-operators"></a>Gérer vos opérateurs

Sous l’onglet **Mes opérateurs** , vous pouvez afficher vos opérateurs, leur état et apporter les modifications suivantes à vos sélections :

- Gérer les services d’opérateur par pays
- Suspendre un opérateur
- Supprimer un opérateur

>[!NOTE]
>Avant de supprimer un opérateur de votre organisation ou d’un pays, vous devez supprimer tous les numéros de téléphone affectés aux utilisateurs et à votre pont Audioconférence, puis contacter l’opérateur pour libérer les numéros.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>Libérer des numéros de votre pont Audioconférence

Pour libérer les numéros de téléphone de votre pont Audioconférence à partir du centre d’administration Teams, consultez **Étapes lorsque vous désattribuez un numéro de téléphone de service pour un pont de conférence** dans [Modifier les numéros de téléphone sur votre pont Audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge).

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Informations supplémentaires sur la gestion de Microsoft Audioconférence

Pour plus d’informations sur la gestion de Microsoft Audioconférence pour votre organisation, consultez les articles suivants :

- Gestion des paramètres de service Microsoft Audioconférence pour votre organisation : [gérez les paramètres de Audioconférence de votre organisation dans Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- Gestion du paramètre de service Microsoft Audioconférence des utilisateurs de votre organisation : [gérer les paramètres de Audioconférence pour un utilisateur dans Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Modification des langues de standard automatique de vos numéros de téléphone Audioconférence : [définissez les langues du standard automatique pour Audioconférence dans Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
