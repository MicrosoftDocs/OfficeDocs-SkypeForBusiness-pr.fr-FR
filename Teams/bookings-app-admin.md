---
title: Gérer l’application Bookings dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- tier2
- highpri
- m365initiative-meetings
ms.reviewer: ''
description: Découvrez comment gérer l’application Bookings dans Teams pour les utilisateurs de votre organisation.
ms.openlocfilehash: 66e3d0450eaad1843c94833cb7bb6d417959eb8c
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727756"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gérer l’application Bookings dans Microsoft Teams

L’application Bookings dans Microsoft Teams offre un moyen simple de planifier des rendez-vous en personne et virtuels. Par exemple, les visites médicales, les consultations financières, les entrevues, le support client et les heures de bureau de l’éducation. Pour en savoir plus, consultez [Rendez-vous virtuels avec Teams et l’application Bookings](/microsoft-365/frontline/bookings-virtual-appointments).

Les planificateurs peuvent gérer plusieurs calendriers et communications du service et du personnel avec les participants internes et externes, à partir d’une seule expérience. Les rendez-vous virtuels sont organisés via des réunions Teams qui offrent des fonctionnalités de vidéoconférence robustes.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Conditions préalables à l’utilisation de l’application Bookings dans Teams

* La boîte aux lettres Exchange est en Exchange Online. Les boîtes aux lettres Exchange Server locales ne sont pas prises en charge.
* Microsoft Bookings est disponible pour l’organisation.
* Les utilisateurs disposent d’une licence appropriée. Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 et Business Standard sont pris en charge.
* Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions disposent d’une licence qui prend en charge la planification des réunions Teams.
* [Prérequis pour les logiciels et les navigateurs](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilité de Bookings dans Teams

L’application Bookings pour Teams est disponible sur le bureau et sur le web. Il se trouve sous [Applications dans Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **Gérer les applications** dans le Centre d’administration Teams.

## <a name="control-access-to-bookings-within-your-organization"></a>Contrôler l’accès à Bookings au sein de votre organisation

Plusieurs méthodes s’offrent à vous pour contrôler qui a accès à l’application Bookings et à des fonctionnalités spécifiques de l’application. Vous pouvez rendre Microsoft Bookings application disponible ou la désactiver à partir de Centre d'administration Microsoft 365. Vous pouvez également créer une stratégie d’application Bookings pour permettre à certains utilisateurs de créer des calendriers Bookings. Consultez [Obtenir l’accès à Microsoft Bookings](/microsoft-365/bookings/get-access).

Vous pouvez également [créer une stratégie de configuration d’application Teams pour épingler l’application Bookings à certains utilisateurs](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Paramètres de stratégie de réunion recommandés

Pour activer la meilleure expérience pour Bookings, créez une stratégie de réunion Teams pour admettre automatiquement **tout le monde dans votre organisation** et attribuer la stratégie à votre personnel. La stratégie permet au personnel de rejoindre automatiquement le rendez-vous et d’activer l’expérience de salle d’attente pour les participants externes. Découvrez [comment admettre automatiquement des personnes aux réunions](meeting-policies-participants-and-guests.md#automatically-admit-people).

Pour plus d’informations sur les stratégies de réunion, consultez [Gérer les stratégies de réunion dans Teams](meeting-policies-in-teams.md) et [Stratégies de réunion et expiration des réunions dans Teams](meeting-expiration.md).

## <a name="sms-text-notifications"></a>Notifications par SMS

![Icône d’informations](media/info.png) **Cette fonctionnalité est déplacée vers [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (préversion). Les utilisateurs peuvent continuer à utiliser cette fonctionnalité pendant la période de préversion. Après la préversion, les utilisateurs ont besoin d’une licence Teams Premium.**

> [!NOTE]
> Nous fournirons des notifications SMS illimitées jusqu’au 1er mars 2023 (précédemment le 31 janvier 2023) pour les clients disposant de licences Bookings. À mesure que nous approchons de la fin de la période de promotion, nous fournirons des détails supplémentaires sur les exigences de licence. Contactez l’équipe ou le support technique de votre compte pour recevoir les détails des tarifs après la période de promotion.

Vous pouvez contrôler si des notifications SMS peuvent être envoyées à des participants externes pour des rendez-vous virtuels planifiés par votre personnel au sein de votre organisation.

Par défaut, ce paramètre est activé et les notifications sms sont activées pour tous les calendriers Bookings de votre organisation. N’oubliez pas que les administrateurs et les planificateurs de Bookings peuvent choisir ultérieurement de désactiver ou d’activer les notifications PAR SMS en fonction des besoins dans les [types de rendez-vous planifiés](/microsoft-365/frontline/bookings-virtual-appointments#scheduled-appointment-type) et les rendez-vous individuels planifiés.

Pour configurer ce paramètre, accédez à la Centre d'administration Microsoft 365 \> **Paramètres** \> **de l’organisation**, puis choisissez **Bookings**. Activez ou désactivez la case **à cocher Autoriser Microsoft à envoyer des notifications par SMS** .

En savoir plus sur la configuration des [notifications sms pour votre organisation](/microsoft-365/bookings/turn-bookings-on-or-off).

## <a name="optional-staff-approvals-setting"></a>Paramètre d’approbation facultative du personnel

Vous pouvez demander au personnel de s’inscrire avant que Bookings ne partage ses informations de disponibilité et avant que d’autres personnes puissent planifier un rendez-vous avec eux.

Pour activer ce paramètre, accédez à la Centre d'administration Microsoft 365 \> **Paramètres** \> **De l’organisation**, puis choisissez **Bookings**. Cochez la case **Exiger les approbations du personnel** .

Lorsque ce paramètre est activé, le personnel reçoit un e-mail dans lequel il est invité à approuver l’adhésion à un calendrier de réservation.  

En savoir plus sur [la configuration du paramètre d’approbations du personnel](/microsoft-365/bookings/turn-bookings-on-or-off).

## <a name="changing-your-default-domain-when-setting-up-a-bookings-mailbox"></a>Modification de votre domaine par défaut lors de la configuration d’une boîte aux lettres Bookings

Lors de la configuration d’une boîte aux lettres Bookings, le domaine de courrier par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé. Toutefois, le domaine par défaut peut entraîner des problèmes lors de l’envoi d’invitations à une réunion à des destinataires externes. Par exemple, votre invitation peut être marquée comme courrier indésirable et déplacée vers le dossier de courrier indésirable du destinataire, de sorte que le destinataire peut ne jamais voir votre invitation.

Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres Bookings. Consultez [questions fréquentes (FAQ) sur les domaines](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365).

Si vous devez modifier le domaine par défaut après avoir créé votre boîte aux lettres Bookings, utilisez PowerShell.

```powerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Pour plus d’informations, consultez [Définir une boîte aux lettres](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Si vous utilisez une configuration Exchange hybride, nous vous recommandons de tester minutieusement le flux de messagerie entre Exchange local et Exchange Online lors de la modification du domaine par défaut.

## <a name="send-feedback"></a>Envoyer des commentaires

Vos commentaires sont les bienvenus :

* Expérience utilisateur ou facilité d’utilisation
* Lacunes dans les fonctionnalités ou fonctionnalités manquantes
* Bogues ou problèmes
  
Pour envoyer des commentaires, sélectionnez l’option **Aide** en bas de la barre de navigation de gauche de Teams, puis sélectionnez **Signaler un problème** pour **TOUS les** problèmes. Indiquez au début de votre rapport de commentaires que vous envoyez des commentaires sur « Bookings » afin que nous puissions facilement identifier les problèmes liés à Bookings.

## <a name="related-articles"></a>Articles connexes

[Gérer l’expérience de participation pour Teams Rendez-vous virtuels sur les navigateurs](/microsoft-365/frontline/browser-join)


  [Documentation Bookings pour les utilisateurs finaux](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
