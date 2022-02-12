---
title: Gérer l’application Bookings dans Microsoft Teams
author: dmaguire
ms.author: serdars
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
ms.openlocfilehash: 147089c51ebc6d3e5eb6bf567579c9aa7fc5f2ce
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763728"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gérer l’application Bookings dans Microsoft Teams

L'application Bookings de Microsoft Teams offre un moyen simple de planifier des rendez-vous en personne ou virtuels, tels que des visites médicales, des consultations financières, des entretiens, une assistance à la clientèle, des heures d'ouverture des bureaux de l'éducation, et bien plus encore. Pour en savoir plus, [voir Visites virtuelles avec Teams et l’application Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Les planificateurs peuvent gérer plusieurs calendriers des services et du personnel, ainsi que les communications avec les participants internes et externes à partir d’une même expérience. Les rendez-vous virtuels eux-mêmes sont Microsoft Teams réunions, ce qui offre des fonctionnalités de visioconférence robustes.

> [!NOTE]
> Seuls les planificateurs doivent avoir l'application Bookings installée dans Teams. Les membres du personnel qui effectuent des rendez-vous virtuels ou y participent n’ont pas besoin de l’application. Ils peuvent simplement rejoindre des rendez-vous à partir de leur calendrier Outlook Teams ou à partir du Teams de la réunion dans leur e-mail de confirmation de réservation.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Conditions préalables à l'utilisation de l'application Bookings dans Teams

- La boîte aux lettres Exchange doit être dans Exchange Online. Les boîtes aux lettres Exchange Server locaux ne sont pas pris en charge.

- Microsoft Bookings doit être désactivé pour l’organisation.

- Les utilisateurs doivent avoir une licence appropriée. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 et Business Standard sont pris en charge.

- Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions doivent avoir une licence qui prend en charge la Teams de la réunion.

- Vos systèmes doivent respecter toutes les [conditions préalables navigateur et logiciels](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilité de Bookings dans Teams

L’application Microsoft Bookings pour Teams est disponible sur le bureau et sur le web. Il se trouve sous [Applications dans Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **Gérer les** applications dans le Teams d’administration.

### <a name="control-access-to-bookings-within-your-organization"></a>Contrôler l’accès à Bookings au sein de votre organisation

Plusieurs méthodes s’offrent à vous pour contrôler qui a accès à l’application Bookings et à des fonctionnalités spécifiques de l’application.

Pour savoir comment activer ou désactiver Microsoft Bookings dans le Centre d'administration Microsoft 365 et comment créer une stratégie d’application Bookings permettant aux utilisateurs sélectionnés de créer des calendriers Bookings, voir Obtenir l’accès à [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).

Vous pouvez également créer [une stratégie Teams de configuration d’une application pour épingler l’application Bookings pour certains utilisateurs](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Paramètres de stratégie de réunion recommandés

Pour activer la meilleure expérience pour Bookings, créez une stratégie de réunion Teams permettant d’admettre automatiquement  tous les membres de votre organisation et d’affecter la stratégie à votre personnel. Cela permet au personnel de rejoindre automatiquement le rendez-vous et d’activer l’expérience de salle d’accueil pour les participants externes. En savoir plus sur [l’accès automatique aux](meeting-policies-participants-and-guests.md#automatically-admit-people) réunions.

## <a name="optional-staff-approvals-setting"></a>Paramètre d’approbation facultative du personnel

Dans le cadre d’un paramètre de confidentialité supplémentaire, vous pouvez choisir d’obliger les membres du personnel à s’y prendre avant que leurs informations de disponibilité ne soient partagées via Bookings et avant qu’ils ne soient pris en rendez-vous.  

Pour activer ce paramètre, sélectionnez **Centre d'administration Microsoft 365** \> **Paramètres** \> **Paramètres**, puis **Bookings**.

Une fois ce paramètre désactivé, le personnel reçoit un courrier électronique dans lequel il est invité à approuver l’appartenance à un calendrier de réservation.  

Cette fonctionnalité est déployée progressivement dans le monde entier pour les clients Microsoft 365 et Office 365. Si toutes les options ne sont pas encore disponibles dans votre environnement, vérifiez à nouveau rapidement.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Modifier votre domaine par défaut lors de la configuration des boîtes aux lettres Bookings

Lors de la configuration d’une boîte aux lettres Bookings, le domaine de courrier par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé. Toutefois, cela peut poser des problèmes lors de l'envoi d'invitations de réunion à des destinataires externes. Il est possible que votre invitation soit signalée en tant que courrier indésirable et déplacée vers le dossier de courrier indésirable du destinataire, de sorte que le destinataire ne voie jamais votre invitation.

Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres Bookings. Pour plus d’informations sur la façon de faire, consultez [FAQ sur les domaines](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si vous devez modifier le domaine par défaut alors que votre boîte aux lettres Bookings a déjà été créée, vous pouvez le faire avec PowerShell :

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Pour plus d’informations, consultez la documentation PowerShell pour la cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Si vous utilisez une configuration hybride Exchange, nous vous recommandons de tester de façon exhaustive le flux de courrier électronique entre les environnements local Exchange et Exchange Online lors de la modification du domaine par défaut.

## <a name="sending-feedback"></a>Envoi de commentaires

Vos commentaires sont les bienvenus :

  - Expérience utilisateur ou facilité d’utilisation
  - Lacunes dans les fonctionnalités ou fonctionnalités manquantes
  - Bogues ou problèmes
  
Pour envoyer des commentaires, sélectionnez le bouton Aide situé en bas Teams barre de navigation gauche, puis sélectionnez Signaler un **problème pour** **TOUS les** problèmes. Indiquez au début de votre rapport de commentaires que vous envoyez des commentaires sur Bookings afin que nous pouvons facilement identifier les problèmes de Bookings.

## <a name="related-articles"></a>Articles connexes

[Gérer l’expérience de jointisation pour les Teams virtuelles sur les navigateurs mobiles](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentation Bookings pour les utilisateurs finaux](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
