---
title: Gérer l’application Bookings dans Microsoft Teams
author: mkbond007
ms.author: mabond
manager: serdars
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
ms.openlocfilehash: 45ce6c29cd7bfbaedf53c1b75178142a925157cb
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695037"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gérer l’application Bookings dans Microsoft Teams

L’application Bookings dans Microsoft Teams offre un moyen simple de planifier des rendez-vous en personne et virtuels. Par exemple, les visites médicales, les consultations financières, les entretiens, le support client et les heures de bureau de l’éducation. Pour en savoir plus, consultez [Rendez-vous virtuels avec Teams et l’application Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Les planificateurs peuvent gérer plusieurs calendriers et communications de service et de personnel avec des participants internes et externes, à partir d’une expérience unique. Les rendez-vous virtuels sont organisés via des réunions Microsoft Teams qui offrent des fonctionnalités de vidéoconférence robustes.

> [!NOTE]
> Seuls les planificateurs doivent avoir l'application Bookings installée dans Teams. Le personnel qui effectue ou participe à des rendez-vous virtuels n’a pas besoin de l’application. Ils peuvent simplement rejoindre des rendez-vous à partir de leur calendrier Outlook ou Teams ou du lien de réunion Teams dans leur e-mail de confirmation de réservation.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Conditions préalables à l’utilisation de l’application Bookings dans Teams

* La boîte aux lettres Exchange est en Exchange Online. Les boîtes aux lettres Exchange Server locales ne sont pas prises en charge.
* Microsoft Bookings est disponible pour l’organisation.
* Les utilisateurs disposent d’une licence appropriée. Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 et Business Standard sont pris en charge.
* Tous les utilisateurs de l’application Bookings et tout le personnel participant aux réunions disposent d’une licence qui prend en charge la planification des réunions Teams.
* [Prérequis pour les logiciels et les navigateurs](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilité de Bookings dans Teams

Microsoft Bookings application pour Teams est disponible sur le bureau et le web. Il se trouve sous [Applications dans Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **Gérer les applications** dans le Centre d’administration Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Contrôler l’accès à Bookings au sein de votre organisation

Plusieurs méthodes s’offrent à vous pour contrôler qui a accès à l’application Bookings et à des fonctionnalités spécifiques de l’application. Vous pouvez rendre Microsoft Bookings application disponible ou la désactiver à partir de Centre d'administration Microsoft 365. Vous pouvez également créer une stratégie d’application Bookings pour permettre à certains utilisateurs de créer des calendriers Bookings. Consultez [Obtenir l’accès à Microsoft Bookings](/microsoft-365/bookings/get-access).

Vous pouvez également [créer une stratégie de configuration d’application Teams pour épingler l’application Bookings à certains utilisateurs](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Paramètres de stratégie de réunion recommandés

Pour bénéficier de la meilleure expérience possible pour Bookings, créez une stratégie de réunion Teams pour admettre automatiquement **tout le monde dans votre organisation** et affecter la stratégie à votre personnel. La stratégie permet au personnel de rejoindre automatiquement le rendez-vous et d’activer l’expérience de salle d’attente pour les participants externes. Découvrez [comment admettre automatiquement des personnes à des réunions](meeting-policies-participants-and-guests.md#automatically-admit-people).

Pour plus d’informations sur les stratégies de réunion, consultez [Gérer les stratégies de réunion dans Teams](meeting-policies-in-teams.md) et les [stratégies de réunion et l’expiration de la réunion dans Teams](meeting-expiration.md).

## <a name="optional-staff-approvals-setting"></a>Paramètre d’approbation facultative du personnel

Vous pouvez demander au personnel d’accepter avant que Bookings partage ses informations de disponibilité de planification et avant que d’autres personnes puissent planifier un rendez-vous avec eux.

Pour activer ce paramètre, accédez à **Centre d'administration Microsoft 365** \> **Paramètres**\>, puis sélectionnez **Réservations**.

Avec ce paramètre activé, le personnel reçoit un e-mail dans lequel il est demandé d’approuver l’adhésion à un calendrier de réservation.  

Cette fonctionnalité est déployée progressivement dans le monde entier pour les clients Microsoft 365 et Office 365. Si toutes les options ne sont pas encore disponibles dans votre environnement, revenez bientôt.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Modification de votre domaine par défaut lors de la configuration de la boîte aux lettres Bookings

Lors de la configuration d’une boîte aux lettres Bookings, le domaine de courrier par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé. Toutefois, le domaine par défaut peut entraîner des problèmes lors de l’envoi d’invitations à une réunion à des destinataires externes. Par exemple, votre invitation peut être marquée comme courrier indésirable et déplacée vers le dossier indésirable du destinataire, de sorte que le destinataire peut ne jamais voir votre invitation.

Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres Bookings. Consultez les [questions fréquentes (FAQ) sur les domaines](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si vous devez modifier le domaine par défaut après avoir créé votre boîte aux lettres Bookings, utilisez PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consultez la documentation PowerShell pour définir l’applet de commande [Boîte aux lettres](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Si vous utilisez une configuration hybride Exchange, nous vous recommandons de tester soigneusement le flux de messagerie entre Exchange local et Exchange Online lors de la modification du domaine par défaut.

## <a name="send-feedback"></a>Envoyer des commentaires

Vos commentaires sont les bienvenus :

* Expérience utilisateur ou facilité d’utilisation
* Lacunes dans les fonctionnalités ou fonctionnalités manquantes
* Bogues ou problèmes
  
Pour envoyer des commentaires, sélectionnez l’option **Aide** en bas de la barre de navigation de gauche de Teams, puis sélectionnez **Signaler un problème** pour **TOUS les** problèmes. Indiquez au début de votre rapport de commentaires que vous envoyez des commentaires sur « Bookings » afin que nous puissions identifier facilement les problèmes liés à Bookings.

## <a name="related-articles"></a>Articles connexes

[Gérer l’expérience de jointure pour les rendez-vous virtuels Teams sur les navigateurs](expand-teams-across-your-org/browser-join.md)


  [Documentation Bookings pour les utilisateurs finaux](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
