---
title: Visites virtuelles avec Microsoft teams et l’application Réservations
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: Microsoft teams et les visites virtuelles à l’aide de l’application Réservations
ms.openlocfilehash: 0c88feec8a90b2794e93fb9c51bffafabf942748
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766957"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visites virtuelles avec Microsoft teams et l’application Réservations

L’application livres de Microsoft teams vous permet de planifier facilement des rendez-vous en personne et des rendez-vous virtuels, tels que les visites de santé, les consultations financières, les entretiens, le support client, les heures consacrées au bureau et bien plus encore.

Les planificateurs peuvent gérer plusieurs calendriers de départements et de membres du personnel, ainsi que des communications avec les participants internes et externes à partir d’une seule et même interface. Les rendez-vous virtuels eux-mêmes sont conservés par le biais des réunions de Microsoft Teams, qui offrent de puissantes fonctionnalités de visioconférence.

> [!NOTE]
> Pour les seuls planificateurs, l’application réservations doit être installée dans Teams. Le personnel responsable ou participant aux rendez-vous virtuel n’a pas besoin de l’application. Ils peuvent simplement joindre des rendez-vous à partir du calendrier Outlook ou teams ou d’un lien dans leur adresse de messagerie de confirmation de réservation.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Conditions préalables à l’utilisation de l’application Réservations dans teams

- La boîte aux lettres Exchange doit être dans Exchange Online. Les boîtes aux lettres Exchange Server locales ne sont pas prises en charge.

- La documentation Microsoft doit être activée pour l’organisation.

- Les utilisateurs doivent disposer d’une licence appropriée. Office 365 a3, a5, E3 et E5, ainsi que Microsoft 365 Business standard, a3, a5, E3 et E5 sont pris en charge.

- Tous les utilisateurs de l’application réservations et de tous les membres du personnel participant à la réunion doivent disposer d’une licence qui prend en charge la planification des réunions Teams.

- Vos systèmes doivent répondre à la [Configuration requise pour les logiciels et les navigateurs](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilité des réservations dans teams

L’application Microsoft bookings pour teams est disponible sur l’ordinateur de bureau et sur le Web. Vous pouvez le trouver sous [applications dans Microsoft teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **gérer les applications** dans le centre d’administration Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Contrôler l’accès aux réservations au sein de votre organisation

Il existe plusieurs méthodes pour contrôler les utilisateurs qui ont accès à l’application réservations et à des fonctionnalités spécifiques de l’application. Pour plus d’informations sur l’activation ou la désactivation de Microsoft bookings dans le centre d’administration 365 Microsoft et sur la création d’une stratégie d’application de documentation pour permettre aux utilisateurs sélectionnés de créer des calendriers de classeurs, voir [accéder à la documentation Microsoft](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Vous pouvez également apprendre à [créer une stratégie d’application teams pour épingler l’application réservations pour certains utilisateurs](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Paramètres de stratégie de réunion recommandés

Pour garantir une meilleure utilisation des réservations, créez une stratégie de réunion du personnel pour admettre automatiquement tous les membres **de votre organisation** . Cela permettra aux membres du personnel de rejoindre automatiquement le rendez-vous et d’activer la salle d’attente pour les participants externes. Vous pouvez en savoir plus sur l' [admission automatique de personnes à une réunion](meeting-policies-in-teams.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Paramètre facultatif d’approbation du personnel

En tant que paramètre de confidentialité supplémentaire, vous pouvez choisir d’exiger que le personnel s’abonne pour que les informations de disponibilité du programme soient partagées par le biais de réservations et avant d’être réservées à un rendez-vous.  

Pour activer ce paramètre, accédez à paramètres des paramètres du **Centre d’administration Microsoft 365** \> **Settings** \> **Settings** , puis sélectionnez **réservations** .

Lorsque ce paramètre est activé, le personnel reçoit un message électronique lui demandant d’approuver l’appartenance à un calendrier de réservation.  

Cette fonctionnalité est déployée progressivement à travers le monde pour les clients Microsoft 365 et Office 365. Si toutes les options ne sont pas encore disponibles dans votre environnement, revenez à la prochaine version.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Modification de votre domaine par défaut lors de la configuration de la boîte aux lettres de réservations

Lorsque vous configurez une boîte aux lettres de réservations, le domaine de messagerie par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé. Toutefois, cela peut poser des problèmes lors de l’envoi d’invitations de réunion à des destinataires externes ; votre invitation peut être signalée comme courrier indésirable et déplacée vers le dossier courrier indésirable du destinataire, afin que le destinataire ne puisse jamais voir votre invitation.

Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres de réservations. Pour plus d’informations sur la façon de procéder, consultez le [Forum aux questions](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)sur les domaines.

Si vous devez modifier le domaine par défaut après la création de la boîte aux lettres de manuel, vous pouvez le faire avec PowerShell :

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Pour plus d’informations, consultez la documentation PowerShell pour l’applet de passe [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Si vous utilisez une configuration Exchange hybride, nous vous conseillons de tester soigneusement le flux de messagerie entre Exchange et Exchange Online lors de la modification du domaine par défaut.

## <a name="sending-feedback"></a>Envoi de commentaires

Vos commentaires sont les suivants :

  - Utilisation ou convivialité
  - Lacunes de fonctionnalités ou fonctionnalités manquantes
  - Bogues ou problèmes
  
Pour envoyer des commentaires, cliquez sur le bouton **aide** en bas de la barre de navigation gauche de teams, puis cliquez sur **signaler un problème** pour **tous les** problèmes. Veuillez noter au début de votre rapport de commentaires que vous envoyez des commentaires sur « réservations » pour nous permettre d’identifier facilement les problèmes liés aux réservations.

## <a name="related-topics"></a>Sujets associés

[Documentation relative aux réservations pour les utilisateurs finaux](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
