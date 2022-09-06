---
title: Configurer Operator Connect
author: CarolynRowe
ms.author: crowe
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
description: En savoir plus sur la configuration de Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7397ade44b1e7ee68c176c51bb1af9880ca0373
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606533"
---
# <a name="configure-operator-connect"></a>Configurer Operator Connect

Cet article explique comment configurer Operator Connect. Avant de configurer Operator Connect, veillez à lire [Plan for Operator Connect pour](operator-connect-plan.md) plus d’informations sur les prérequis et les licences.

## <a name="enable-an-operator"></a>Activer un opérateur

Vous pouvez activer, modifier et supprimer des opérateurs dans le Centre d’administration Teams. Dans le volet de navigation gauche, accédez à **Opérateurs de > voix**.

Pour activer un opérateur :

1. **Choisissez un opérateur.** Sous l’onglet **Tous les opérateurs** , filtrez les opérateurs disponibles par région ou service pour trouver l’opérateur approprié pour vos besoins vocaux. Sélectionnez ensuite l’opérateur que vous souhaitez activer.  

2. **Sélectionnez des pays.** Sous **Paramètres de l’opérateur**, sélectionnez les pays que vous souhaitez activer avec votre opérateur sélectionné.

3. **Fournir des informations de contact** Vos informations de contact, y compris votre nom complet et votre adresse e-mail, seront partagées automatiquement avec votre opérateur. Vous pouvez modifier ces informations ultérieurement. En outre, vous devez fournir la taille de l’entreprise, et vous aurez la possibilité de fournir votre numéro de téléphone. Les opérateurs utiliseront ces informations pour vous contacter pour plus d’informations sur Operator Connect.

4. Acceptez l’avis de transfert de données.

5. **Ajoutez votre opérateur.** Sélectionnez **Ajouter en tant qu’opérateur** à enregistrer.

## <a name="set-up-phone-numbers"></a>Configurer des numéros de téléphone

La façon dont vous configurez les numéros de téléphone varie selon que vous configurez des numéros pour les nouveaux utilisateurs ou que vous déplacez des numéros existants à partir des forfaits d’appels Microsoft ou du routage direct.

- Si vous devez acquérir des numéros de téléphone pour les nouveaux utilisateurs, consultez [Acquérir des numéros pour les nouveaux utilisateurs Teams](#acquire-numbers-for-new-teams-users).

- Si vous souhaitez déplacer des numéros existants des forfaits d’appels vers Operator Connect, consultez [Déplacer les numéros des forfaits d’appels vers Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).

- Si vous souhaitez déplacer des numéros existants du routage direct vers Operator Connect, consultez [Déplacer des numéros du routage direct vers Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="assign-numberes-to-emergency-addresses"></a>Affecter des numéros à des adresses d’urgence

L’adresse d’urgence est un emplacement statique associé à un nombre. Une fois que vous avez créé des adresses d’urgence dans le Centre d’administration Teams, la façon dont vous attribuez les adresses, ou les modifiez ultérieurement, dépend de votre opérateur.

Pour affecter des numéros à des adresses d’urgence, votre opérateur implémente l’un des trois scénarios suivants :

- L’opérateur affecte des adresses d’urgence aux numéros de téléphone et vous permet de les modifier ultérieurement dans le Centre d’administration Teams.

- L’opérateur n’affecte pas d’adresses et vous permet d’attribuer des adresses d’urgence aux numéros de téléphone dans le Centre d’administration Teams.

- L’opérateur affecte des adresses d’urgence aux numéros de téléphone et ne vous permet pas de les modifier. Dans ce scénario, vous devez contacter votre opérateur pour apporter des modifications aux numéros de téléphone et à leur adresse d’urgence affectée.

Pour plus d’informations sur les appels d’urgence, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md) et [planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="acquire-numbers-for-new-teams-users"></a>Acquérir des numéros pour les nouveaux utilisateurs Teams

Pour acquérir des numéros pour les nouveaux utilisateurs teams, procédez comme suit :

1. **Attribuez une licence de système téléphonique.** Vous pouvez attribuer une licence système téléphonique à vos utilisateurs à partir du Centre d'administration Microsoft 365 ou à l’aide de PowerShell. Pour plus d’informations, consultez [Affecter des licences de module complémentaire Teams aux utilisateurs](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Les utilisateurs qui recevront des numéros de téléphone acquis avec Operator Connect doivent être en mode TeamsOnly. Si votre organisation est en mode TeamsOnly, tous vos utilisateurs sont en mode TeamsOnly. Pour vérifier cela, dans le Centre d’administration Teams, accédez aux **paramètres de mise à niveau teams > Teams**. Si votre organisation est en mode Îles, vérifiez si des utilisateurs spécifiques sont en mode TeamsOnly. Accédez à **Utilisateurs** et sélectionnez un compte d’utilisateur. Sous l’onglet **Compte** , sous **Mise à niveau de Teams,** le mode de coexistence doit être défini sur « TeamsOnly ».

3. **Acquérir des nombres.** Accédez au site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour obtenir la liste des sites web des opérateurs, accédez au [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, consultez [Rechercher votre ID de locataire Microsoft 365](/onedrive/find-your-office-365-tenant-id) pour plus d’informations.

4. **Attribuez des nombres.** Une fois que votre opérateur aura terminé la commande, il chargera les numéros vers votre locataire. Vous pouvez afficher les numéros et le fournisseur dans le Centre d’administration Teams en accédant à **Voice > Numéros de téléphone**. Attribuez des numéros aux utilisateurs à partir du Centre d’administration Teams ou à l’aide de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](#assign-numbers).

> [!NOTE]
> En plus [d’obtenir des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md), vous pouvez obtenir des numéros de téléphone payants ou gratuits pour des services tels que l’audioconférence (pour les ponts de conférence), les standards automatiques et les files d’attente d’appels (également appelés numéros de service). Les numéros de téléphone de service disposent d'une capacité d'appels simultanés plus élevée que les numéros de téléphone d'utilisateur ou d'abonné. Par exemple, un numéro de service peut gérer des centaines d’appels simultanément, tandis que le numéro de téléphone d’un utilisateur ne peut gérer que quelques appels simultanément. Pour obtenir des numéros de service, contactez votre opérateur.

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Déplacer des numéros de forfaits d’appels vers Operator Connect

1. Contactez votre opérateur pour porter vos numéros vers Operator Connect. Consultez le [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) pour trouver le site web de votre opérateur.

2. Une fois que votre opérateur a terminé l’ordre de portage, il charge les numéros vers votre locataire.

3. Attribuez des numéros Operator Connect aux utilisateurs à l’aide du Centre d’administration Teams ou de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Déplacer des numéros du routage direct vers Operator Connect

Pour passer du routage direct à Operator Connect avec des numéros de téléphone locaux ou en ligne, suivez les étapes ci-dessous :

#### <a name="step-1---identify-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Étape 1 : identifier si les numéros de routage direct existants sont affectés en ligne ou localement.

Vérifiez que l’utilisateur se voit attribuer un numéro de routage direct en exécutant la commande module Teams PowerShell :

```PowerShell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
```

Vérifiez qu’il `NumberType` s’agit de DirectRouting.

La façon dont vous supprimez vos numéros de routage direct existants varie selon que le nombre est attribué localement ou en ligne. Pour vérifier, exécutez la commande de module Teams PowerShell suivante :
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

S’il `OnPremLineUri` est rempli avec un numéro de téléphone E.164, le numéro de téléphone a été attribué localement et synchronisé avec Microsoft 365.

**Pour migrer les numéros de routage direct existants affectés en ligne à Operator Connect**, contactez votre opérateur. Pour trouver le site web de votre opérateur, consultez le [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). À la date et à l’heure convenues, votre opérateur migre vos numéros du routage direct vers Operator Connect.

**Pour migrer les numéros de routage direct affectés localement à Operator Connect**, exécutez la commande PowerShell Skype Entreprise Server suivante :
>[!IMPORTANT]
> Le numéro de téléphone sera hors service pendant la migration. Coordonnez-vous donc avec votre opérateur Operator Connect avant de commencer.

```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

Le temps nécessaire à la suppression dépend de votre configuration. Pour vérifier si le numéro local a été supprimé et si les modifications ont été synchronisées de l’environnement local vers Microsoft 365, exécutez la commande module Teams PowerShell suivante : 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
Une fois les modifications synchronisées avec le répertoire en ligne Microsoft 365, la sortie attendue est la suivante : 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```




```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

La suppression du numéro de téléphone peut prendre jusqu’à 10 minutes. Dans de rares cas, cela peut prendre jusqu’à 24 heures. Pour vérifier si le numéro de téléphone a été supprimé, exécutez la commande module Teams PowerShell suivante : 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Étape 2 : Supprimer la stratégie de routage vocal en ligne associée à votre utilisateur

Une fois le nombre non attribué, supprimez la stratégie de routage vocal en ligne associée à votre utilisateur en exécutant la commande module Teams PowerShell suivante :

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Étape 3 : Acquérir des numéros de téléphone

Accédez au site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour trouver le site web de vos opérateurs, consultez le [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, consultez [Rechercher votre ID de locataire Microsoft 365](/onedrive/find-your-office-365-tenant-id) pour plus d’informations.

#### <a name="step-4---assign-phone-numbers"></a>Étape 4 : Attribuer des numéros de téléphone

Une fois que votre opérateur aura terminé la commande, il chargera les numéros vers votre locataire. Vous pouvez afficher les numéros et le fournisseur dans le Centre d’administration Teams en accédant à **Voice > Numéros de téléphone**. Attribuez des numéros Operator Connect aux utilisateurs à l’aide du Centre d’administration Teams ou de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](#assign-numbers).

### <a name="assign-numbers"></a>Attribuer des nombres

Pour plus d’informations sur l’affectation de numéros de téléphone à vos utilisateurs, consultez [Affecter, modifier ou supprimer un numéro de téléphone pour un utilisateur](assign-change-or-remove-a-phone-number-for-a-user.md).

## <a name="manage-your-operators"></a>Gérer vos opérateurs

Sous l’onglet **Mes opérateurs** , vous pouvez afficher vos opérateurs et leur état et apporter les modifications suivantes à vos sélections :  

- Gérer les services d’opérateur par pays
- Suspendre un opérateur
- Supprimer un opérateur

> [!NOTE]
> Avant de supprimer un opérateur de votre organisation ou d’un pays, vous devez supprimer tous les numéros de téléphone affectés aux utilisateurs de l’organisation ou du pays et contacter l’opérateur pour libérer les numéros.

## <a name="release-numbers"></a>Numéros de publication

Pour libérer des numéros de téléphone à partir du Centre d’administration Teams, accédez à la page **Numéros de téléphone** et sélectionnez un numéro.

- Si le numéro de téléphone n’est pas attribué à un utilisateur, sélectionnez **Libérer**.

- Si le numéro de téléphone est attribué à un utilisateur, vous devez annuler l’affectation du numéro. Sélectionnez **Modifier**, puis **Supprimez l’utilisateur**. Après avoir enregistré vos modifications, sélectionnez **Release**.

## <a name="related-topics"></a>Rubriques connexes

- [Planifier les standards automatiques teams et les files d’attente d’appels](plan-auto-attendant-call-queue.md)
