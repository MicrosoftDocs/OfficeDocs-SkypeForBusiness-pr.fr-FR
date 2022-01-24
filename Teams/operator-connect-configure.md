---
title: Configurer l’Connecter
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
description: En savoir plus sur la configuration de la Connecter.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9abb37e195e602281c8fad0cdf052e35bf35cc67
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2022
ms.locfileid: "62181067"
---
# <a name="configure-operator-connect"></a>Configurer l’Connecter

Cet article décrit comment configurer l’opérateur Connecter. Avant de configurer l’Connecter, n’oubliez pas de lire [l’information plan](operator-connect-plan.md) pour les Connecter opérateur pour plus d’informations sur les conditions préalables et les licences.

## <a name="enable-an-operator"></a>Activer un opérateur

Vous pouvez activer, modifier et supprimer des opérateurs dans le Centre Teams’administration. Dans le volet de navigation gauche, allez à **Voice > Opérateurs.**

Pour activer un opérateur :

1. **Choisissez un opérateur.** Dans **l’onglet Tous les** opérateurs, filtrez les opérateurs disponibles par région ou service pour trouver l’opérateur qui vous permet de répondre à vos besoins vocables. Sélectionnez ensuite l’opérateur que vous voulez activer.  

2. **Sélectionnez les pays.** Sous **Paramètres de l’opérateur,** sélectionnez les pays que vous voulez activer avec l’opérateur sélectionné.

3. **Fournir des informations de contact** Vos informations de contact, y compris votre nom complet et votre adresse de messagerie, seront automatiquement partagées avec votre opérateur. Vous pourrez modifier ces informations ultérieurement. De plus, vous devez fournir la taille de l’entreprise et vous avez la possibilité de fournir votre numéro de téléphone. Les opérateurs utilisent ces informations pour vous contacter avec plus de détails sur les opérateurs Connecter.

4. Acceptez l’avis de transfert de données.

5. **Ajoutez votre opérateur.** Sélectionnez **Ajouter en tant qu’opérateur** pour enregistrer.

## <a name="set-up-phone-numbers"></a>Configurer des numéros de téléphone

La configuration des numéros de téléphone varie selon que vous définissez des numéros pour de nouveaux utilisateurs ou que vous déplacez des numéros existants à partir de plans d’appel Microsoft ou d’un routage direct.

- Si vous devez acquérir des numéros de téléphone pour de nouveaux utilisateurs, consultez Acquérir les numéros pour [les nouveaux Teams utilisateurs.](#acquire-numbers-for-new-teams-users)

- Si vous voulez déplacer des numéros existants des plans d’appels vers des plans d’Connecter, consultez Déplacer les numéros des plans d’appels vers les plans [d’Connecter.](#move-numbers-from-calling-plans-to-operator-connect)

- Si vous voulez déplacer des numéros existants du routage direct vers l’opérateur Connecter, voir Déplacer les numéros du routage direct vers l’opérateur [Connecter.](#move-numbers-from-direct-routing-to-operator-connect)

### <a name="acquire-numbers-for-new-teams-users"></a>Acquérir des numéros pour les nouveaux Teams utilisateurs

Pour acquérir des nombres pour les nouveaux Teams utilisateurs, suivez les étapes suivantes :

1. **Attribuez une Système téléphonique licence de licence.** Vous pouvez attribuer une licence Système téléphonique utilisateur à vos utilisateurs à partir du Centre d'administration Microsoft 365 ou à l’aide de PowerShell. Pour plus d’informations, [voir Attribuer Teams de module complémentaire aux utilisateurs.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. Les utilisateurs qui seront affectés à des numéros de téléphone acquis avec l Connecter doivent être en mode TeamsOnly. Si votre organisation est en mode TeamsOnly, tous vos utilisateurs sont en mode TeamsOnly. Pour le vérifier, dans le Teams d’administration, consultez les **Teams > Teams de mise à niveau.** Si votre organisation est en mode Îles, vérifiez si des utilisateurs spécifiques sont en mode TeamsOnly. Sélectionnez **un compte** d’utilisateur dans Utilisateurs. Dans **l’onglet** Compte, **Teams mise à niveau,** le mode coexistence doit être réglé sur « TeamsOnly ».

3. **Acquérir des nombres.** Allez sur le site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour obtenir la liste des sites web d’opérateurs, voir l Microsoft 365 [de Connecter de recherche.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, voir Rechercher votre [ID](/onedrive/find-your-office-365-tenant-id) Microsoft 365 client pour plus d’informations.

4. **Attribuer des nombres.** Une fois la commande terminée par votre opérateur, celui-là charge les numéros vers votre client. Vous pouvez afficher les numéros et le fournisseur dans le centre d Teams’administration en cantant sur les numéros > Téléphone **voix.** Attribuez des numéros à des utilisateurs à partir Teams centre d’administration ou à l’aide de PowerShell. Pour plus d’informations, voir [Attribuer des numéros.](#assign-numbers)

> [!NOTE]
> Outre l’obtention de numéros de téléphone pour vos [utilisateurs,](getting-phone-numbers-for-your-users.md)vous pouvez obtenir des numéros de téléphone gratuits ou gratuits pour des services tels que l’audioconférence (pour les ponts de conférence), le attendant automatique et les files d’attente (également appelées numéros de service). Les numéros de téléphone de service disposent d'une capacité d'appels simultanés plus élevée que les numéros de téléphone d'utilisateur ou d'abonné. Par exemple, un numéro de service peut gérer des centaines d’appels simultanément, alors qu’un numéro de téléphone d’utilisateur ne peut gérer que quelques appels à la fois. Pour obtenir des numéros de service, contactez votre opérateur.

### <a name="emergency-addresses"></a>Adresses d’urgence

L’adresse de secours est un emplacement statique associé à un nombre. Une fois les adresses de secours Teams créés dans le Centre d’administration, la manière dont vous les affectez ou les modifiez ultérieurement dépend de votre opérateur.

Pour affecter des numéros à des adresses d’urgence, votre opérateur implémente l’un des trois scénarios suivants :

- L’opérateur attribue des adresses d’urgence aux numéros de téléphone et vous permet de les modifier ultérieurement dans le Teams d’administration.

- L’opérateur n’attribue pas d’adresses et vous permet d’attribuer des adresses d’urgence aux numéros de téléphone dans le Teams d’administration.

- L’opérateur attribue des adresses d’urgence aux numéros de téléphone et ne vous permet pas de les modifier. Dans ce scénario, vous devez contacter votre opérateur pour apporter des modifications aux numéros de téléphone et à l’adresse d’urgence qui lui est affectée.

Pour plus d’informations sur les appels d’urgence, voir [Gérer](what-are-emergency-locations-addresses-and-call-routing.md) les appels d’urgence et [Planifier et configurer des appels d’urgence dynamiques.](configure-dynamic-emergency-calling.md)

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Déplacer des numéros du plan d’appel vers le plan d’Connecter

1. Contactez votre opérateur pour le portage de vos numéros vers l’opérateur Connecter. Consultez [Microsoft 365'Connecter de l’opérateur](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) pour trouver le site web de votre opérateur.

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
   Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <value of OnPremLineURI> -PhoneNumberType DirectRouting 
   ```

2. Supprimez l’utilisation PSTNUsage associée à vos utilisateurs, sans quoi les appels seront acheminés vers la passerelle spécifiée dans l’utilisation PSTN. Pour savoir comment supprimer l’utilisation PSTN, voir [Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)

3. Allez sur le site web de votre opérateur pour commander et acquérir des numéros de téléphone. Pour trouver le site web de vos opérateurs, consultez le [Microsoft 365 de Connecter’annuaire.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) Vous devez fournir votre ID de locataire. Si vous ne connaissez pas votre ID de locataire, voir Rechercher votre [ID](/onedrive/find-your-office-365-tenant-id) Microsoft 365 client pour plus d’informations.

4. Une fois la commande terminée par votre opérateur, celui-là charge les numéros vers votre client. Vous pouvez afficher les numéros et le fournisseur dans le centre d Teams’administration en cantant sur les numéros > Téléphone **voix.** Affectez des numéros Connecter aux utilisateurs à l’aide du Centre Teams’administration de l’utilisateur ou de PowerShell. Pour plus d’informations, voir [Attribuer des numéros.](#assign-numbers)

### <a name="assign-numbers"></a>Attribuer des numéros

Pour plus d’informations sur l’attribution de numéros de téléphone à vos utilisateurs, voir Attribuer, modifier ou supprimer un numéro de téléphone [pour un utilisateur.](assign-change-or-remove-a-phone-number-for-a-user.md)

## <a name="manage-your-operators"></a>Gérer vos opérateurs

Dans **l’onglet Mes opérateurs,** vous pouvez afficher vos opérateurs et leur statut, et apporter les modifications suivantes à vos sélections :  

- Gérer les services d’opérateur par pays
- Suspendre un opérateur
- Supprimer un opérateur

> [!NOTE]
> Avant de supprimer un opérateur de votre organisation ou d’un pays, vous devez supprimer tous les numéros de téléphone affectés aux utilisateurs au niveau de l’organisation ou du pays et contacter l’opérateur pour qu’il relâche ces numéros.

## <a name="release-numbers"></a>Numéros de publication

Pour libérer des numéros de téléphone à partir Teams centre d’administration, allez à la page **Téléphone numéros de téléphone** et sélectionnez un numéro.

- Si le numéro de téléphone n’est pas attribué à un utilisateur, sélectionnez **Publication.**

- Si le numéro de téléphone est affecté à un utilisateur, vous devez désaffecter ce numéro. Sélectionnez **Modifier,** puis **supprimer l’utilisateur.** Après avoir enregistrer vos modifications, sélectionnez **Publication.**

## <a name="related-topics"></a>Sujets associés

- [Planifier les appels Teams automatiques et les files d’attente d’appels](plan-auto-attendant-call-queue.md)
