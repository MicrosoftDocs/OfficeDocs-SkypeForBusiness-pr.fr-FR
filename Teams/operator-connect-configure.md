---
title: Configurer Operator Connect
author: cazawideh
ms.author: czawideh
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
description: Découvrez comment configurer Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d3b56a7935f31413829c89285fc81ee70023ab4
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675766"
---
# <a name="configure-operator-connect"></a>Configurer Operator Connect

Cet article explique comment configurer Operator Connect. Avant de configurer Operator Connect, veillez à lire [Plan for Operator Connect pour](operator-connect-plan.md) plus d’informations sur les prérequis et les licences.

## <a name="enable-an-operator"></a>Activer un opérateur

Vous pouvez activer, modifier et supprimer des opérateurs dans le centre d’administration Teams. Dans le volet de navigation gauche, accédez à **Opérateurs de > voix**.

Pour activer un opérateur :

1. **Choisissez un opérateur.** Sous l’onglet **Tous les opérateurs** , filtrez les opérateurs disponibles par région ou service pour trouver l’opérateur approprié pour vos besoins vocaux. Sélectionnez ensuite l’opérateur que vous souhaitez activer.  

2. **Sélectionnez des pays.** Sous **Paramètres de l’opérateur**, sélectionnez les pays que vous souhaitez activer avec votre opérateur sélectionné.

3. **Fournir des informations de contact** Vos informations de contact, y compris votre nom complet et votre adresse e-mail, seront partagées automatiquement avec votre opérateur. Vous pouvez modifier ces informations ultérieurement. En outre, vous devez fournir la taille de l’entreprise, et vous aurez la possibilité de fournir votre numéro de téléphone. Les opérateurs utiliseront ces informations pour vous contacter avec plus de détails sur Operator Connect.

4. Acceptez l’avis de transfert de données.

5. **Ajoutez votre opérateur.** Sélectionnez **Ajouter en tant qu’opérateur** à enregistrer.

## <a name="set-up-phone-numbers"></a>Configurer des numéros de téléphone

La façon dont vous configurez les numéros de téléphone varie selon que vous configurez des numéros pour les nouveaux utilisateurs ou que vous déplacez des numéros existants à partir des forfaits d’appels Microsoft ou du routage direct.

- Si vous devez acquérir des numéros de téléphone pour les nouveaux utilisateurs, consultez [Acquérir des numéros pour les nouveaux utilisateurs Teams](#acquire-numbers-for-new-teams-users).

- Si vous souhaitez déplacer des numéros existants des plans d’appels vers Operator Connect, consultez [Déplacer les numéros des plans d’appels vers Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).

- Si vous souhaitez déplacer des nombres existants du routage direct vers Operator Connect, consultez [Déplacer les numéros du routage direct vers Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).

### <a name="acquire-numbers-for-new-teams-users"></a>Acquérir des numéros pour les nouveaux utilisateurs Teams

Pour acquérir des numéros pour les nouveaux utilisateurs Teams, procédez comme suit :

1. **Attribuez une licence Système téléphonique.** Vous pouvez attribuer une licence Système téléphonique à vos utilisateurs à partir du Centre d'administration Microsoft 365 ou à l’aide de PowerShell. Pour plus d’informations, consultez [Affecter Teams licences de module complémentaire aux utilisateurs](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. Les utilisateurs qui recevront des numéros de téléphone acquis avec Operator Connect doivent être en mode TeamsOnly. Si votre organisation est en mode TeamsOnly, tous vos utilisateurs sont en mode TeamsOnly. Pour vérifier cela, dans le centre d’administration Teams, accédez à **Teams > Teams paramètres de mise à niveau**. Si votre organisation est en mode Îles, vérifiez si des utilisateurs spécifiques sont en mode TeamsOnly. Accédez à **Utilisateurs** et sélectionnez un compte d’utilisateur. Sous l’onglet **Compte**, sous **Teams mise à niveau,** le mode de coexistence doit être défini sur « TeamsOnly ».

3. **Acquérir des nombres.** Accédez au site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour obtenir la liste des sites web des opérateurs, accédez au [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, consultez [Rechercher votre ID de locataire Microsoft 365](/onedrive/find-your-office-365-tenant-id) pour plus d’informations.

4. **Attribuez des nombres.** Une fois que votre opérateur aura terminé la commande, il chargera les numéros vers votre locataire. Vous pouvez afficher les nombres et le fournisseur dans le centre d’administration Teams en accédant aux **numéros De voix > Téléphone**. Attribuez des numéros aux utilisateurs à partir du centre d’administration Teams ou à l’aide de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](#assign-numbers).

> [!NOTE]
> En plus [d’obtenir des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md), vous pouvez obtenir des numéros de téléphone payants ou gratuits pour des services tels que Audioconférence (pour les ponts de conférence), les standards automatiques et les files d’attente d’appels (également appelés numéros de service). Les numéros de téléphone de service disposent d'une capacité d'appels simultanés plus élevée que les numéros de téléphone d'utilisateur ou d'abonné. Par exemple, un numéro de service peut gérer des centaines d’appels simultanément, tandis que le numéro de téléphone d’un utilisateur ne peut gérer que quelques appels simultanément. Pour obtenir des numéros de service, contactez votre opérateur.

### <a name="emergency-addresses"></a>Adresses d’urgence

L’adresse d’urgence est un emplacement statique associé à un nombre. Une fois que vous avez créé des adresses d’urgence dans le centre d’administration Teams, la façon dont vous affectez les adresses, ou les modifiez ultérieurement, dépend de votre opérateur.

Pour affecter des numéros à des adresses d’urgence, votre opérateur implémente l’un des trois scénarios suivants :

- L’opérateur affecte des adresses d’urgence aux numéros de téléphone et vous permet de les modifier ultérieurement dans le centre d’administration Teams.

- L’opérateur n’affecte pas d’adresses et vous permet d’attribuer des adresses d’urgence aux numéros de téléphone dans le centre d’administration Teams.

- L’opérateur affecte des adresses d’urgence aux numéros de téléphone et ne vous permet pas de les modifier. Dans ce scénario, vous devez contacter votre opérateur pour apporter des modifications aux numéros de téléphone et à leur adresse d’urgence affectée.

Pour plus d’informations sur les appels d’urgence, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md) et [planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Déplacer des numéros des forfaits d’appels vers Operator Connect

1. Contactez votre opérateur pour porter vos numéros vers Operator Connect. Consultez [Microsoft 365 Operator Connect répertoire](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) pour trouver le site web de votre opérateur.

2. Une fois que votre opérateur a terminé la commande de portage, vous pouvez annuler l’affectation des numéros de téléphone du plan d’appel de vos utilisateurs et supprimer la licence du plan d’appel. Ensuite, votre opérateur peut charger les numéros dans votre locataire.

3. Attribuez Operator Connect nombres aux utilisateurs à l’aide du centre d’administration Teams ou de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](#assign-numbers).

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Déplacer des nombres du routage direct vers Operator Connect

Pour déplacer des numéros du routage direct vers Operator Connect, le numéro de routage direct existant qui a été chargé vers votre locataire par votre opérateur doit être supprimé de l’utilisateur auquel il est affecté. Ensuite, une fois le nombre migré vers Operator Connect, vous pouvez le réaffecter à l’utilisateur. Pour passer du routage direct à Operator Connect avec des numéros de téléphone locaux ou en ligne, suivez les étapes ci-dessous :

>[!IMPORTANT]
> Le numéro de téléphone sera hors service pendant la migration. Par conséquent, coordonnez-vous avec votre opérateur Operator Connect avant de commencer.

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>Étape 1 : supprimer les numéros de routage direct existants.

La façon dont vous supprimez vos numéros de routage direct existants varie selon que le nombre est attribué localement ou en ligne. Pour vérifier, exécutez la commande Teams module PowerShell suivante :
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

S’il `OnPremLineUri` est rempli avec un numéro de téléphone E.164, le numéro de téléphone a été attribué localement et synchronisé avec Office 365.
    
**Pour supprimer les numéros de routage direct affectés localement,** exécutez la commande PowerShell Skype Entreprise Server suivante :
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

Le temps nécessaire à la suppression dépend de votre configuration. Pour vérifier si le numéro local a été supprimé et si les modifications ont été synchronisées, exécutez la commande Teams module PowerShell suivante : 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
Une fois les modifications synchronisées avec Office 365 répertoire en ligne, la sortie attendue est la suivante : 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```

<br> **Pour supprimer les numéros de routage direct en ligne existants affectés en ligne,** exécutez la commande Teams module PowerShell suivante :


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

La suppression du numéro de téléphone peut prendre jusqu’à 10 minutes. Dans de rares cas, cela peut prendre jusqu’à 24 heures. Pour vérifier si le numéro de téléphone a été supprimé, exécutez la commande Teams module PowerShell suivante : 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>Étape 2 : Supprimer la stratégie de routage vocal en ligne associée à votre utilisateur

Une fois le nombre non attribué, supprimez la stratégie de routage vocal en ligne associée à votre utilisateur en exécutant la commande Teams module PowerShell suivante :

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>Étape 3 : Acquérir des numéros de téléphone

Accédez au site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour trouver le site web de vos opérateurs, consultez le [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, consultez [Rechercher votre ID de locataire Microsoft 365](/onedrive/find-your-office-365-tenant-id) pour plus d’informations.

#### <a name="step-4---assign-phone-numbers"></a>Étape 4 : Attribuer des numéros de téléphone

Une fois que votre opérateur aura terminé la commande, il chargera les numéros vers votre locataire. Vous pouvez afficher les nombres et le fournisseur dans le centre d’administration Teams en accédant aux **numéros De voix > Téléphone**. Attribuez Operator Connect nombres aux utilisateurs à l’aide du centre d’administration Teams ou de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](#assign-numbers).

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

Pour libérer des numéros de téléphone à partir du centre d’administration Teams, accédez à la page **des numéros Téléphone** et sélectionnez un numéro.

- Si le numéro de téléphone n’est pas attribué à un utilisateur, sélectionnez **Libérer**.

- Si le numéro de téléphone est attribué à un utilisateur, vous devez annuler l’affectation du numéro. Sélectionnez **Modifier**, puis **Supprimez l’utilisateur**. Après avoir enregistré vos modifications, sélectionnez **Release**.

## <a name="related-topics"></a>Voir aussi

- [Planifier Teams standards automatiques et les files d’attente d’appels](plan-auto-attendant-call-queue.md)
