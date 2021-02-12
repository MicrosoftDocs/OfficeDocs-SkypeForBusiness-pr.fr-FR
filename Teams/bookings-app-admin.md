---
title: Visites virtuelles avec Microsoft Teams et l’application Bookings
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams et visites virtuelles avec l’application Bookings
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125747"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visites virtuelles avec Microsoft Teams et l’application Bookings

L’application Bookings dans Microsoft Teams offre un moyen simple de planifier des rendez-vous en personne et virtuelles, tels que des visites médicales, des consultations financières, des entretiens, un support client, des heures d’ouverture du bureau dans le cadre de l’éducation, etc.

Les planningurs peuvent gérer plusieurs calendriers de service et de personnel, ainsi que les communications avec les participants internes et externes, à partir d’une seule expérience. Les rendez-vous virtuels eux-mêmes sont placés via les réunions Microsoft Teams, qui offrent de solides fonctionnalités de visioconférence.

> [!NOTE]
> Seuls les plannings doivent avoir l’application Bookings installée dans Teams. Pour diriger des rendez-vous virtuels ou participer à des rendez-vous virtuels, le personnel n’a pas besoin de l’application. Ils peuvent simplement rejoindre des rendez-vous à partir de leur calendrier Outlook ou Teams, ou à partir d’un lien dans leur e-mail de confirmation de réservation.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Conditions préalables à l’utilisation de l’application Bookings dans Teams

- La boîte aux lettres Exchange doit se trouver dans Exchange Online. Les boîtes aux lettres Exchange Server locaux ne sont pas pris en charge.

- Microsoft Bookings doit être désactivé pour l’organisation.

- Les utilisateurs doivent avoir une licence appropriée. Office 365 A3, A5, E3 et E5, ainsi que Microsoft 365 Business Standard, A3, A5, E3 et E5 sont pris en charge.

- Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions doivent avoir une licence qui prend en charge la planification de réunions Teams.

- Vos systèmes doivent satisfaire toutes les [conditions requises pour le logiciel et le navigateur.](hardware-requirements-for-the-teams-app.md)

## <a name="availability-of-bookings-in-teams"></a>Disponibilité de Bookings dans Teams

L’application Microsoft Bookings pour Teams est disponible sur le bureau et sur le web. Il est possible de le trouver sous [Applications dans Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous Gérer les applications **dans** le Centre d’administration Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Contrôler l’accès à Bookings au sein de votre organisation

Plusieurs méthodes s’offrent à vous pour contrôler les personnes qui ont accès à l’application Bookings et pour accéder à des fonctionnalités spécifiques de l’application. Pour savoir comment activer ou désactiver Microsoft Bookings dans le Centre d’administration Microsoft 365, et comment créer une stratégie d’application Bookings pour permettre à des utilisateurs sélectionnés de créer des calendriers Bookings, voir Obtenir l’accès à [Microsoft Bookings.](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce) Vous pouvez également découvrir comment créer [une stratégie d’application Teams pour épingler l’application Bookings pour certains utilisateurs.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Paramètres de stratégie de réunion recommandés

Pour activer la meilleure expérience pour Bookings, créez une stratégie de réunion pour le personnel enseignant afin d’admettre automatiquement tous **les membres de votre organisation.** Cela permet au personnel de rejoindre automatiquement le rendez-vous et d’activer l’expérience de la salle d’accueil pour les participants externes. Vous pouvez en savoir plus [sur l’accès automatique aux réunions.](meeting-policies-in-teams.md#automatically-admit-people)

### <a name="optional-staff-approvals-setting"></a>Paramètre d’approbation facultative du personnel enseignant

En tant que paramètre de confidentialité supplémentaire, vous pouvez demander au personnel de s’y prendre avant que ses informations de disponibilité ne soient partagées via Bookings et qu’il soit possible de réserver un rendez-vous.  

Pour activer ce paramètre, allez dans paramètres du Centre d’administration **Microsoft 365,** \>  \> puis **sélectionnez Bookings.**

Une fois ce paramètre désactivé, le personnel reçoit un courrier électronique dans lequel il est invité à approuver l’adhésion à un calendrier de réservation.  

Cette fonctionnalité est progressivement déployée dans le monde entier pour les clients Microsoft 365 et Office 365. Si toutes les options ne sont pas encore disponibles dans votre environnement, vérifiez à nouveau rapidement.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Modification de votre domaine par défaut lors de la configuration de boîtes aux lettres Bookings

Lors de la configuration d’une boîte aux lettres Bookings, le domaine de courrier par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé. Toutefois, cela peut poser des problèmes lors de l’envoi d’invitations à des réunions à des destinataires externes. Il est possible que votre invitation soit signalée comme courrier indésirable et déplacée vers le dossier Courrier indésirable du destinataire, afin que le destinataire ne puisse jamais voir votre invitation.

Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres Bookings. Pour plus d’informations sur la façon de faire, consultez le [Forum aux questions des domaines.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)

Si vous devez modifier le domaine par défaut une fois votre boîte aux lettres Bookings créée, vous pouvez le faire avec PowerShell :

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Pour plus d’informations, consultez la documentation PowerShell de [l’cmdlet Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

> [!NOTE]
> Si vous utilisez une configuration Exchange hybride, nous vous recommandons de tester de façon exhaustive le flux de courrier électronique entre les services exchange locaux et Exchange Online lors de la modification du domaine par défaut.

## <a name="sending-feedback"></a>Envoi de commentaires

Vos commentaires sont les bienvenus :

  - Expérience utilisateur ou facilité d’utilisation
  - Fonctionnalités manquantes ou manquantes
  - Bogues ou problèmes
  
Pour envoyer des  commentaires, cliquez sur le bouton Aide situé en bas de la barre de navigation gauche de Teams, puis cliquez sur Signaler un problème **pour** **TOUS les** problèmes. Notez au début de votre rapport de commentaires que vous envoyez des commentaires sur Bookings afin que nous pouvons facilement identifier les problèmes de Bookings.

## <a name="related-topics"></a>Sujets associés

[Documentation sur Bookings pour les utilisateurs finaux](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
