---
title: Configurer Teams Phone Mobile
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
description: En savoir plus sur la configuration de Teams Phone Mobile.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e0e5c349610e9f8ad73b9b7a50b4c219304ea4
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551678"
---
# <a name="configure-teams-phone-mobile"></a>Configurer Teams Phone Mobile

Pour obtenir la liste des opérateurs participant au programme Téléphonie Microsoft Teams Mobile et des pays ou régions où leur service est disponible, consultez [Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/connect-mobile).

Cet article explique comment configurer Teams Phone Mobile. Avant de configurer Teams Phone Mobile, veillez à lire [Plan for Teams Phone Mobile pour](operator-connect-mobile-plan.md) plus d’informations sur les avantages, les prérequis et les licences.

## <a name="enable-an-operator"></a>Activer un opérateur

Vous pouvez activer, modifier et supprimer des opérateurs dans le Centre d’administration Teams. Dans le volet de navigation gauche, accédez à **Opérateurs de > voix**.

Pour activer un opérateur :

1. Choisissez un opérateur qui prend en charge Teams Phone Mobile. Sous l’onglet **Tous les opérateurs** , filtrez les opérateurs disponibles par région ou service pour trouver l’opérateur approprié prenant en charge Teams Phone Mobile. Sélectionnez ensuite l’opérateur que vous souhaitez activer.

2. Sous **Paramètres de l’opérateur**, sélectionnez les pays que vous souhaitez activer avec votre opérateur sélectionné.

3. **Fournissez des informations de contact.** Vos informations de contact, y compris votre nom complet et votre adresse e-mail, seront partagées automatiquement avec votre opérateur. Vous pouvez modifier ces informations ultérieurement. En outre, vous devez fournir la taille de l’entreprise, et vous aurez la possibilité de fournir votre numéro de téléphone. Les opérateurs utiliseront ces informations pour vous contacter avec plus de détails sur Teams Phone Mobile.

4. Acceptez l’avis de transfert de données.

5. Sélectionnez **Ajouter en tant qu’opérateur** à enregistrer.

## <a name="set-up-phone-numbers"></a>Configurer des numéros de téléphone

Si vous souhaitez ajouter des numéros de téléphone avec carte SIM payante de votre entreprise existante à Teams, contactez votre opérateur pour vous assurer que vous disposez de l’abonnement Mobile Mobile Teams éligible et qu’il peut charger vos numéros dans Teams. Une fois que votre opérateur a terminé la commande, vous pouvez affecter ces numéros aux utilisateurs. 

Pour trouver le site web de votre opérateur, consultez le [répertoire Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, consultez [Rechercher votre ID de locataire Microsoft 365](/onedrive/find-your-office-365-tenant-id.md). Vous pouvez porter un numéro de téléphone de bureau ou un numéro de téléphone filaire existant vers un abonnement vocal sans fil s’il est pris en charge dans votre région et par votre opérateur. 

La façon dont vous configurez les numéros de téléphone varie selon que vous configurez des numéros pour les nouveaux utilisateurs ou que vous déplacez des numéros existants à partir de Microsoft Calling Plans, Operator Connect ou du routage direct.

- [Acquérir des numéros pour les nouveaux utilisateurs Teams](#acquire-numbers-for-new-teams-users).  

- [Déplacez les numéros des forfaits d’appels vers Teams Phone Mobile](#move-numbers-from-calling-plans-to-teams-phone-mobile).  

- [Déplacer des numéros d’Opérateur Connect vers Teams Phone Mobile](#move-numbers-from-operator-connect-to-teams-phone-mobile).  

- [Déplacer des numéros du routage direct vers Teams Phone Mobile](#move-numbers-from-direct-routing-to-teams-phone-mobile).  


### <a name="assign-numbers-to-emergency-addresses"></a>Affecter des numéros à des adresses d’urgence

L’adresse d’urgence est un emplacement statique associé à un nombre lorsqu’il est accessible par le biais de points de terminaison/clients Microsoft Teams. Une fois que vous avez créé des adresses d’urgence dans le Centre d’administration Teams, la façon dont vous attribuez les adresses, ou les modifiez ultérieurement, dépend de votre opérateur.

Pour affecter des numéros aux adresses d’urgence utilisées par les points de terminaison Microsoft Teams, votre opérateur implémente l’un des trois scénarios suivants :

- L’opérateur affecte des adresses d’urgence aux numéros de téléphone et vous permet de les modifier ultérieurement dans le Centre d’administration Teams.

- L’opérateur n’affecte pas d’adresses et vous permet d’attribuer des adresses d’urgence aux numéros de téléphone dans le Centre d’administration Teams.

- L’opérateur affecte des adresses d’urgence aux numéros de téléphone et ne vous permet pas de les modifier. Dans ce scénario, vous devez contacter votre opérateur pour apporter des modifications aux numéros de téléphone et à leur adresse d’urgence affectée.

Lorsque des appels sont effectués via le numéroteur natif du smartphone compatible SIM, votre opérateur peut utiliser les coordonnées géographiques ou la tour de cellule qui gère l’appel à un emplacement d’urgence approximatif pour obtenir de l’aide.

Pour plus d’informations sur les appels d’urgence, consultez [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md) et [planifier et configurer les appels d’urgence dynamiques](configure-dynamic-emergency-calling.md).

### <a name="acquire-numbers-for-new-teams-users"></a>Acquérir des numéros pour les nouveaux utilisateurs Teams

Pour acquérir des numéros pour les nouveaux utilisateurs teams, procédez comme suit :

1. **Attribuez une licence système téléphonique et une licence de module complémentaire Teams Phone Mobile.** Vous pouvez attribuer une licence système téléphonique et une licence de module complémentaire Teams Phone Mobile à vos utilisateurs à partir du Centre d'administration Microsoft 365 ou à l’aide de PowerShell. Pour plus d’informations, consultez [Affecter des licences de module complémentaire Teams aux utilisateurs](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **Les utilisateurs qui recevront des numéros de téléphone acquis avec Teams Phone Mobile doivent être en mode TeamsOnly.** Si votre organisation est en mode TeamsOnly, tous vos utilisateurs sont en mode TeamsOnly. 

   Pour vérifier, dans le Centre d’administration Teams, accédez aux **paramètres de mise à niveau teams > Teams**. Si votre organisation est en mode Îles, vérifiez si des utilisateurs spécifiques sont en mode TeamsOnly. Accédez à **Utilisateurs** et sélectionnez un compte d’utilisateur. Sous l’onglet **Compte** , sous **Mise à niveau de Teams,** le mode de coexistence doit être défini sur TeamsOnly.

3. **Acquérir des nombres.** Accédez au site web de votre opérateur ou contactez-le pour commander et acquérir des numéros de téléphone mobiles compatibles SIM avec le service Mobile Mobile Teams activé. 

   Une fois que votre opérateur aura terminé la commande, il chargera les numéros mobiles compatibles SIM sur votre locataire. Vous pouvez afficher les numéros et le fournisseur dans le Centre d’administration Teams en accédant à **Voice > Numéros de téléphone**. 

4. **Attribuez des nombres.** Vous pouvez affecter des numéros aux utilisateurs à partir du Centre d’administration Teams ou à l’aide de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-calling-plans-to-teams-phone-mobile"></a>Déplacer des numéros des forfaits d’appels vers Teams Phone Mobile

1. Assurez-vous que vous disposez d’abonnements Microsoft 365 éligibles pour Teams Phone Mobile et la licence de module complémentaire Teams Phone Mobile. Vous devez [supprimer le numéro de téléphone à déplacer pour les utilisateurs respectifs](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). 

2. Contactez votre opérateur pour porter vos numéros vers Teams Phone Mobile sur un plan vocal sans fil éligible qui est compatible SIM. 

3. Une fois que votre opérateur a terminé l’ordre de portage, il charge les numéros vers votre locataire.  Vous pouvez afficher les numéros et le fournisseur dans le Centre d’administration Teams en accédant à **Voice > Numéros de téléphone**. 

4. Vous pouvez affecter des numéros aux utilisateurs à l’aide du Centre d’administration Teams ou de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-operator-connect-to-teams-phone-mobile"></a>Déplacer des numéros d’Opérateur Connect vers Teams Phone Mobile

1. Assurez-vous que vous disposez d’abonnements Microsoft 365 éligibles pour Teams Phone Mobile et la licence de module complémentaire Teams Phone Mobile. Vous devez [supprimer le numéro de téléphone à déplacer pour les utilisateurs respectifs](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). Contactez votre fournisseur Operator Connect existant pour supprimer les numéros de téléphone de votre locataire.

2. Contactez votre opérateur pour porter vos numéros vers Teams Phone Mobile sur un plan vocal sans fil éligible qui est compatible SIM. 

3. Une fois que votre opérateur a terminé l’ordre de portage, il charge les numéros vers votre locataire. Vous pouvez afficher les numéros et le fournisseur dans le Centre d’administration Teams en accédant à **Voice > Numéros de téléphone**. 

4. Vous pouvez affecter des numéros aux utilisateurs à l’aide du Centre d’administration Teams ou de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-direct-routing-to-teams-phone-mobile"></a>Déplacer des numéros du routage direct vers Teams Phone Mobile   

Pour déplacer des numéros du routage direct vers Teams Phone Mobile, vous devez effectuer les étapes suivantes :

1. [Déterminez si les numéros de routage direct existants sont affectés en ligne ou localement](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises).

2. [Migrez les numéros du routage direct vers Teams Phone Mobile](#migrate-the-numbers-from-direct-routing-to-teams-phone-mobile).

2. [Supprimez la stratégie de routage vocal en ligne associée à votre utilisateur](#remove-the-online-voice-routing-policy-associated-with-your-user).

3. [Acquérir des numéros de téléphone](#acquire-phone-numbers).

4. [Attribuez des numéros de téléphone](#assign-phone-numbers).

Ces étapes sont décrites plus en détail dans les sections suivantes.

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Déterminez si les numéros de routage direct existants sont affectés en ligne ou localement.

La façon dont vous supprimez vos numéros de routage direct existants varie selon que le nombre est attribué localement ou en ligne.

1. Tout d’abord, vérifiez que l’utilisateur se voit attribuer un numéro de routage direct en exécutant la commande Teams PowerShell suivante. NumberType doit être DirectRouting :

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. Déterminez si le nombre est affecté en ligne ou localement en exécutant la commande Teams PowerShell suivante :

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   Si OnPremLineUri est rempli avec un numéro de téléphone E.164, le numéro de téléphone a été attribué localement et synchronisé avec Microsoft 365.

#### <a name="migrate-the-numbers-from-direct-routing-to-teams-phone-mobile"></a>Migrer les numéros du routage direct vers Teams Phone Mobile

Pour migrer des nombres, suivez les étapes ci-dessous.  

> [!Important]
> Pendant la migration, le numéro de téléphone est hors service. Coordonnez-vous avec votre opérateur Teams Phone Mobile avant de commencer la migration.

- **Pour migrer les numéros de routage direct existants affectés en ligne à Teams Phone Mobile**, contactez votre opérateur. Pour trouver le site web de votre opérateur, consultez [l’annuaire Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). À la date et à l’heure convenues, votre opérateur migre vos numéros du routage direct vers Teams Phone Mobile. Cela peut impliquer la suppression du numéro de téléphone en cours de migration de votre locataire et l’ajouter à nouveau en tant que nouveau numéro de téléphone associé à Teams Phone Mobile.

- **Pour migrer les numéros de routage direct affectés localement à Teams Phone Mobile**, exécutez la commande PowerShell Skype Entreprise Server suivante :

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  Pour vérifier si le numéro local a été supprimé et si les modifications ont été synchronisées de l’environnement local vers Microsoft 365, exécutez la commande Teams PowerShell suivante :

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

Une fois les modifications synchronisées avec le répertoire en ligne Microsoft 365, la sortie attendue est la suivante :

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

Pour vérifier si le numéro de téléphone a été supprimé, exécutez la commande Teams PowerShell suivante :

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> Le temps nécessaire à la suppression dépend de votre configuration. La suppression du numéro de téléphone peut prendre jusqu’à 10 minutes. Dans de rares cas, cela peut prendre jusqu’à 24 heures. 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>Supprimer la stratégie de routage vocal en ligne associée à votre utilisateur

Une fois le nombre non attribué, supprimez la stratégie de routage vocal en ligne associée à votre utilisateur en exécutant la commande Teams PowerShell suivante :

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>Obtenir les numéros de téléphone

Contactez votre opérateur pour porter vos numéros vers Teams Phone Mobile sur un plan vocal sans fil éligible qui est compatible SIM.

Une fois que votre opérateur aura terminé la commande, il chargera les numéros vers votre locataire. Vous pouvez afficher les numéros et le fournisseur dans le Centre d’administration Teams en accédant à **Voice > Numéros de téléphone**. 

#### <a name="assign-phone-numbers"></a>Attribuer des numéros de téléphone

Vous pouvez affecter des numéros Teams Phone Mobile aux utilisateurs à l’aide du Centre d’administration Teams ou de PowerShell. Pour plus d’informations, consultez [Affecter des numéros](assign-change-or-remove-a-phone-number-for-a-user.md).


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

## <a name="manage-user-incoming-calling-policies"></a>Gérer les stratégies d’appel entrant de l’utilisateur

Vous pouvez gérer les stratégies d’appel entrantes d’un utilisateur à l’aide du Centre d’administration Teams ou de PowerShell. Par défaut, les appels entrants pour les utilisateurs de Teams Phone Mobile sonnent d’abord l’application Teams sur l’appareil mobile compatible SIM de l’utilisateur. 

- Si la préférence d’appel entrant d’un utilisateur est définie sur l’application Teams, tous les appels entrants sonnent l’application Teams sur le smartphone compatible SIM et tous les autres points de terminaison Teams sur d’autres appareils simultanément. 

- Si la préférence d’appel entrant d’un utilisateur est définie sur l’appelant natif, tous les appels entrants sonnent le numéroteur natif sur le smartphone compatible SIM et sonnent simultanément tous les autres points de terminaison Teams sur d’autres appareils. 

### <a name="use-the-teams-admin-center"></a>Utiliser le Centre d’administration Teams

Pour gérer les stratégies d’appel entrant d’un utilisateur à l’aide du Centre d’administration Teams :

1. Sous l’onglet Voix, sélectionnez **Stratégies de mobilité**. 

2. Pour ajouter une nouvelle stratégie mobile, cliquez sur **Ajouter**.

3. Sélectionnez un nom, ajoutez une description de la stratégie, puis choisissez l’une des options suivantes dans l’option de liste **déroulante Sélectionner un numéroteur mobile** :

   -  **Microsoft Teams** doit d’abord sonner l’application Teams sur le smartphone compatible SIM. 

   - **Native Dialer** pour faire sonner native Dialer sur le smartphone compatible SIM d’abord.

4. Affectez les stratégies aux utilisateurs. Consultez [Affecter des stratégies](assign-policies-users-and-groups.md).


### <a name="use-powershell"></a>Utiliser PowerShell

1. Connectez-vous à votre locataire : Connect-MicrosoftTeams.
 
2. Créez d’abord des stratégies pour que les appels entrants sonnent le numéroteur natif ou l’application Teams. (Vous pouvez choisir le nom de la stratégie ; cet exemple utilise TeamsFirst et NativeFirst.) 

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. Accorder des stratégies aux utilisateurs : 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. Vérifiez les stratégies utilisateur : 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. Vérifiez toutes les options de stratégie de mobilité : 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








