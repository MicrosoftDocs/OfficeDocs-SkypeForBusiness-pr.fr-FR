---
title: Gérer l’application Bookings dans Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Découvrez comment gérer l’application Bookings dans Teams pour les utilisateurs de votre organisation.
ms.openlocfilehash: 3032704fe935f1d4d316741400e8a4b5841f8685
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070583"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gérer l’application Bookings dans Microsoft Teams

L’application Bookings Microsoft Teams permet de planifier des rendez-vous virtuels et en personne de manière simple. Par exemple, visites médicales, consultations financières, entretiens, support client et heures d’ouverture du bureau pour l’éducation. Pour en savoir plus, [consultez les visites virtuelles avec Teams et l’application Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Les planningurs peuvent gérer plusieurs calendriers de service et du personnel et les communications avec des participants internes et externes, à partir d’une expérience unique. Les rendez-vous virtuels sont Microsoft Teams au cours de réunions qui offrent des fonctionnalités de visioconférence robustes.

> [!NOTE]
> Seuls les planificateurs doivent avoir l'application Bookings installée dans Teams. Les membres du personnel qui effectuent des rendez-vous virtuels ou y participent n’ont pas besoin de l’application. Ils peuvent simplement rejoindre des rendez-vous à partir de leur calendrier Outlook ou Teams ou à partir du Teams de la réunion dans leur e-mail de confirmation de réservation.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Conditions préalables d’utilisation de l’application Bookings dans Teams

* La boîte Exchange lettres est dans Exchange Online. Les boîtes aux lettres Exchange Server locaux ne sont pas pris en charge.
* Microsoft Bookings est disponible pour l’organisation.
* Les utilisateurs ont une licence appropriée. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 et Business Standard sont pris en charge.
* Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions ont une licence qui prend en charge la Teams de la réunion.
* [Conditions préalables pour les logiciels et les navigateurs](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilité de Bookings dans Teams

L’application Microsoft Bookings pour Teams est disponible sur le bureau et sur le web. Il se trouve sous [Applications dans Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **Gérer les** applications dans le Teams d’administration.

### <a name="control-access-to-bookings-within-your-organization"></a>Contrôler l’accès à Bookings au sein de votre organisation

Plusieurs méthodes s’offrent à vous pour contrôler qui a accès à l’application Bookings et à des fonctionnalités spécifiques de l’application. Vous pouvez rendre l’application Microsoft Bookings disponible ou la désactiver Centre d'administration Microsoft 365. Vous pouvez également créer une stratégie d’application Bookings pour permettre à certains utilisateurs de créer des calendriers Bookings. Voir [Obtenir l’accès à Microsoft Bookings](/microsoft-365/bookings/get-access).

Vous pouvez également créer [une stratégie Teams de configuration d’une application pour épingler l’application Bookings pour certains utilisateurs](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Paramètres de stratégie de réunion recommandés

Pour activer la meilleure expérience pour Bookings, créez une stratégie Teams réunion pour admettre automatiquement tous les membres  de votre organisation et affecter la stratégie à votre personnel. La stratégie permet au personnel de rejoindre le rendez-vous automatiquement et d’activer l’expérience de salle d’accueil pour les participants externes. Découvrez [comment admettre automatiquement des personnes à des réunions](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Paramètre d’approbation facultative du personnel

Vous pouvez demander au personnel de s’y rendre avant que Bookings ne partage ses informations de disponibilité et avant que d’autres personnes ne peuvent planifier un rendez-vous avec eux.

Pour activer ce paramètre, sélectionnez **Centre d'administration Microsoft 365** \> **Paramètres** \> **Paramètres**, puis **Bookings**.

Une fois ce paramètre désactivé, le personnel reçoit un courrier électronique dans lequel il est demandé d’approuver l’appartenance à un calendrier de réservation.  

Cette fonctionnalité est déployée progressivement dans le monde entier pour les clients Microsoft 365 et Office 365. Si toutes les options ne sont pas encore disponibles dans votre environnement, vérifiez à nouveau rapidement.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Modification de votre domaine par défaut lors de la configuration de la boîte aux lettres Bookings

Lors de la configuration d’une boîte aux lettres Bookings, le domaine de courrier par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé. Toutefois, le domaine par défaut peut poser des problèmes lors de l’envoi d’invitations à des réunions à des destinataires externes. Par exemple, votre invitation peut être marquée comme courrier indésirable et déplacée vers le dossier Courrier indésirable du destinataire, afin que le destinataire ne puisse jamais voir votre invitation.

Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres Bookings. Consultez le [Forum aux questions des domaines](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si vous devez modifier le domaine par défaut après avoir créé votre boîte aux lettres Bookings, utilisez PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consultez la documentation PowerShell sur la cmdlet [Définir la](/powershell/module/exchange/mailboxes/set-mailbox) boîte aux lettres.

> [!NOTE]
> Si vous utilisez une configuration hybride Exchange, nous vous recommandons de tester de façon exhaustive le flux de courrier électronique entre les environnements local Exchange et Exchange Online lors de la modification du domaine par défaut.

## <a name="send-feedback"></a>Envoyer des commentaires

Vos commentaires sont les bienvenus :

* Expérience utilisateur ou facilité d’utilisation
* Lacunes dans les fonctionnalités ou fonctionnalités manquantes
* Bogues ou problèmes
  
Pour envoyer des commentaires, sélectionnez **l’option** d’aide en bas Teams barre de navigation gauche, puis sélectionnez Signaler un **problème pour** **TOUS les** problèmes. Indiquez au début de votre rapport de commentaires que vous envoyez des commentaires sur Bookings afin que nous pouvons facilement identifier les problèmes de Bookings.

## <a name="related-articles"></a>Articles connexes

[Gérer l’expérience de jointisation pour les Teams virtuelles sur les navigateurs mobiles](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentation Bookings pour les utilisateurs finaux](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
