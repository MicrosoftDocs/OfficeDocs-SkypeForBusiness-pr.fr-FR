---
title: Configurer l’Connecter
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
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
description: En savoir plus sur la configuration de la Connecter.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689889"
---
# <a name="configure-operator-connect"></a>Configurer l’Connecter

>[!NOTE]
>L’Connecter est actuellement disponible uniquement en **prévisualisation publique.** La prévisualisation publique vous permet de tester les fonctionnalités à venir et de fournir des commentaires. Les fonctionnalités incluses dans la prévisualisation publique peuvent ne pas être complètes, subi des modifications et ne sont pas pris en charge dans Office 365 Secteur Public Clouds.

Cet article décrit comment configurer l’Connecter. Avant de configurer l’Connecter, n’oubliez pas de lire [l’information plan](operator-connect-plan.md) pour les Connecter opérateur pour plus d’informations sur les conditions préalables et les licences.

## <a name="enable-an-operator"></a>Activer un opérateur

Vous pouvez activer, modifier et supprimer des opérateurs dans le Centre Teams’administration. Dans le volet de navigation gauche, allez à **Voice > Opérateurs.**

Pour activer un opérateur :

1. **Choisissez un opérateur.** Dans **l’onglet Tous** les opérateurs, filtrez les opérateurs disponibles par région ou service pour trouver l’opérateur qui vous permet de répondre à vos besoins vocables. Sélectionnez ensuite l’opérateur que vous voulez activer.  

2. **Sélectionnez les pays.** Sous **Paramètres de l’opérateur,** sélectionnez les pays que vous voulez activer avec l’opérateur sélectionné.

3. **Fournir des informations de contact (facultatif).** Si vous souhaitez que les opérateurs vous contactent pour obtenir des informations supplémentaires sur la Connecter opérateur, cochez la case et fournissez vos informations de contact.  

4. **Acceptez l’avis de transfert de données.**

5. **Ajoutez votre opérateur.** Sélectionnez **Ajouter en tant qu’opérateur** pour enregistrer.

## <a name="set-up-phone-numbers"></a>Configurer des numéros de téléphone

La configuration des numéros de téléphone varie selon que vous définissez des numéros pour de nouveaux utilisateurs ou que vous souhaitez déplacer des numéros existants à partir de plans d’appel Microsoft ou d’un routage direct.

- Si vous devez acquérir des numéros de téléphone pour de nouveaux utilisateurs, voir Acquérir des numéros pour [les nouveaux Teams utilisateurs.](#acquire-numbers-for-new-teams-users)

- Si vous voulez déplacer des numéros existants des forfaits d’appels vers des Connecter, consultez Déplacer les numéros des plans d’appels vers les plans [d’Connecter.](#move-numbers-from-calling-plans-to-operator-connect)

- Si vous voulez déplacer des numéros existants du routage direct vers l’opérateur Connecter, voir Déplacer les numéros du routage direct vers l’opérateur [Connecter.](#move-numbers-from-direct-routing-to-operator-connect)

>[!IMPORTANT]
>**Adresses d’urgence :** Les adresses de secours associées à un numéro acquis auprès de l’opérateur sont gérées directement avec l’opérateur. Contactez l’opérateur pour apporter des modifications.

### <a name="acquire-numbers-for-new-teams-users"></a>Acquérir des numéros pour les nouveaux Teams utilisateurs

Pour acquérir des numéros pour les nouveaux Teams utilisateurs, suivez les étapes suivantes :

1. **Attribuez une Système téléphonique licence de licence.** Vous pouvez attribuer une licence Système téléphonique utilisateur à vos utilisateurs à partir du Microsoft 365 d’administration de l’entreprise ou à l’aide de PowerShell. Pour plus d’informations, [voir Attribuer Teams de module complémentaire aux utilisateurs.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. **Assurez-vous d’être en mode TeamsOnly.** Pour vérifier, dans le centre Teams d’administration, allez dans les paramètres à l’échelle de **l’organisation > Teams mise à niveau.** Le mode de coexistence ne doit être réglé que sur Teams.

3. **Créer et valider des adresses de secours.** Dans le centre Teams d’urgence, allez à **Emplacements >** d’urgence pour configurer les adresses de secours. Pour en savoir plus, [consultez Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation.](add-change-remove-emergency-location-organization.md)

4. **Acquérir des nombres.** Allez sur le site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour obtenir une liste des sites web d’opérateurs, voir [Opérateurs.](#operators) Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, voir Rechercher votre [ID Microsoft 365 client pour](/onedrive/find-your-office-365-tenant-id) plus d’informations.

5. **Attribuer des nombres.** Une fois que votre opérateur a terminé la commande, il télécharge les numéros de test dans votre client. Vous pouvez afficher les numéros et le fournisseur dans le Centre d Teams’administration en vous > Téléphone **les numéros.** Attribuez des numéros à des utilisateurs à l’aide du Teams d’administration ou de PowerShell. Pour plus d’informations, voir [Attribuer des numéros.](#assign-numbers)
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Déplacer des numéros du plan d’appel vers le plan d’Connecter

1. Contactez votre opérateur pour le portage de vos numéros vers l’opérateur Connecter. Consultez [les](#operators) opérateurs pour trouver le site web de votre opérateur.

2. Une fois que votre opérateur a terminé la demande de portage, vous pouvez retirer l’affectation des numéros de téléphone du plan d’appels de vos utilisateurs et supprimer la licence du plan d’appels. Votre opérateur peut ensuite charger les numéros sur votre client.

3. Affectez des numéros Connecter aux utilisateurs à l’aide du Centre Teams’administration de l’utilisateur ou de PowerShell. Pour plus d’informations, voir [Attribuer des numéros.](#assign-numbers)

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Déplacer des nombres du routage direct vers l’opérateur Connecter

1. Supprimez le numéro de téléphone existant de l’utilisateur comme suit :  

   Obtenez l’URI On-prem Line existante en exécutant la commande PowerShell suivante :

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   Supprimez l’URI On-prem Line en exécutant la commande PowerShell suivante :  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. Supprimez les problèmes d’utilisation PSTNUsage associés à vos utilisateurs, sans quoi les appels seront acheminés vers la passerelle spécifiée dans l’utilisation PSTN. Pour savoir comment supprimer l’utilisation PSTN, voir [Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)

3. Allez sur le site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour obtenir une liste des sites web d’opérateurs, voir [Opérateurs.](#operators) Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, voir Rechercher votre [ID Microsoft 365 client pour](/onedrive/find-your-office-365-tenant-id) plus d’informations.

4. Une fois que votre opérateur a terminé la commande, il télécharge les numéros de test dans votre client. Vous pouvez afficher les numéros et le fournisseur dans le Centre d Teams’administration en vous > Téléphone **les numéros.** Affectez des numéros Connecter aux utilisateurs à l’aide du Centre Teams’administration de l’utilisateur ou de PowerShell. Pour plus d’informations, voir [Attribuer des numéros.](#assign-numbers)

   

### <a name="assign-numbers"></a>Attribuer des numéros

Que vous ajoutiez de nouveaux utilisateurs Teams ou que vous entagiez des utilisateurs existants à l’Connecter, les étapes à suivre pour attribuer des numéros sont les suivantes :

Pour attribuer des numéros à l’aide Teams centre d’administration, voir **Téléphone numéros.** Les étapes sont identiques à l’affectation de numéros pour les forfaits d’appels. Pour plus d’informations, [voir Attribuer un numéro de téléphone à un utilisateur.](assign-change-or-remove-a-phone-number-for-a-user.md)

Pour attribuer des numéros à l’aide de PowerShell, utilisez l'Set-CsOnlineVoiceUser de cmdlet suivante :

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

Par exemple :

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

Pour plus d’informations sur l’attribution de numéros de téléphone à vos utilisateurs, voir Attribuer, modifier ou supprimer un numéro de téléphone [pour un utilisateur.](assign-change-or-remove-a-phone-number-for-a-user.md)



## <a name="manage-your-operators"></a>Gérer vos opérateurs

Dans l’onglet Mes opérateurs, vous pouvez afficher vos opérateurs et leur statut, et apporter les modifications suivantes à vos sélections :  

- Gérer les services d’opérateur par pays
- Suspendre un opérateur
- Supprimer un opérateur

> [!NOTE]
> Avant de supprimer un opérateur de votre organisation ou d’un pays, vous devez supprimer tous les numéros de téléphone affectés à des utilisateurs de l’organisation ou du pays et contacter l’opérateur pour qu’il les publie.

## <a name="operators"></a>Opérateurs

Vous pouvez acquérir des numéros de téléphone à partir des opérateurs suivants en vous rendre sur les sites web liés ici :


|Opérateur  |Site web de l’opérateur  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
