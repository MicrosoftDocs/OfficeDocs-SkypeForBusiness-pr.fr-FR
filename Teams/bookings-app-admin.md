---
title: Visites virtuelles dans Microsoft Teams et l’application Bookings
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams et les visites virtuelles avec l’application Bookings
ms.openlocfilehash: cf6154099db5b6c6b52b9d82b4e58cd6c00c07b3
ms.sourcegitcommit: 1c2364fbefd95151f0847a35e8bc7c4c1b3892f5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58935860"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visites virtuelles dans Microsoft Teams et l’application Bookings

L'application Bookings de Microsoft Teams offre un moyen simple de planifier des rendez-vous en personne ou virtuels, tels que des visites médicales, des consultations financières, des entretiens, une assistance à la clientèle, des heures d'ouverture des bureaux de l'éducation, et bien plus encore.

Les planificateurs peuvent gérer plusieurs calendriers des services et du personnel, ainsi que les communications avec les participants internes et externes à partir d’une même expérience. Les rendez-vous virtuels eux-mêmes se déroulent via les réunions Microsoft Teams, qui offrent de solides capacités de vidéoconférence.

> [!NOTE]
> Seuls les planificateurs doivent avoir l'application Bookings installée dans Teams. Le personnel effectuant ou participant à des rendez-vous virtuels n'a pas besoin de l'application. Ils peuvent simplement rejoindre les rendez-vous à partir de leur calendrier Outlook ou Teams ou à partir d'un lien dans leur courriel de confirmation de réservation.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Conditions préalables à l'utilisation de l'application Bookings dans Teams

- La boîte aux lettres Exchange doit être dans Exchange Online. Les boîtes aux lettres sur serveur Exchange local ne sont pas prises en charge.

- Microsoft Bookings doit être désactivé pour l’organisation.

- Les utilisateurs doivent avoir une licence appropriée. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3 et E5, Business Standard sont pris en charge.

- Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions doivent avoir une licence qui prend en charge la planification de réunions Teams.

- Vos systèmes doivent respecter toutes les [Conditions préalables navigateur et logiciels](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilité de Bookings dans Teams

L’application Microsoft Bookings pour Teams est disponible sur le bureau et sur le web. Elle se trouve sous [Applications dans Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **Gérer les applications** dans le Centre d’administration Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Contrôler l’accès à Bookings au sein de votre organisation

Plusieurs méthodes s’offrent à vous pour contrôler qui a accès à l’application Bookings et à des fonctionnalités spécifiques de l’application. Pour savoir comment activer ou désactiver Microsoft Bookings dans le Centre d’administration Microsoft 365, et créer une stratégie d’application Bookings pour autoriser les utilisateurs sélectionnés à créer des calendriers Bookings, consultez [Accéder à Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Vous pouvez également découvrir comment [Créer une stratégie d’application Teams pour épingler l’application Bookings à certains utilisateurs](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Paramètres de stratégie de réunion recommandés

Pour optimiser l'expérience de Bookings, créez une stratégie de réunion du personnel pour admettre automatiquement **Tous les membres de votre organisation**. Cela permettra au personnel de rejoindre automatiquement le rendez-vous et d’activer l’expérience de salle d’évaluation pour les participants externes. Vous pouvez en savoir plus sur l'[admission automatique des personnes aux réunions](meeting-policies-participants-and-guests.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Paramètre d’approbation facultative du personnel

Dans le cadre d’un paramètre de confidentialité supplémentaire, vous pouvez choisir d’obliger les membres du personnel à s’y prendre avant que leurs informations de disponibilité ne soient partagées via Bookings et avant qu’ils ne soient pris en rendez-vous.  

Pour activer ce paramètre, accédez au **Centre d’administration Microsoft 365** \> **Paramètres** \> **Paramètres**, puis sélectionnez **Bookings**.

Avec ce paramètre désactivé, le personnel reçoit un courrier électronique dans lequel il est invité à approuver l’appartenance à un calendrier de réservation.  

Cette fonctionnalité est déployée progressivement dans le monde entier pour les clients Microsoft 365 et Office 365. Si toutes les options ne sont pas encore disponibles dans votre environnement, vérifiez à nouveau dans peu de temps.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Modifier votre domaine par défaut lors de la configuration des boîtes aux lettres Bookings

Lors de la configuration d’une boîte aux lettres Bookings, le domaine de courrier par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé. Toutefois, cela peut poser des problèmes lors de l'envoi d'invitations de réunion à des destinataires externes. Il est possible que votre invitation soit signalée en tant que courrier indésirable et déplacée vers le dossier de courrier indésirable du destinataire, de sorte que le destinataire ne voie jamais votre invitation.

Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres Bookings. Pour plus d’informations sur la façon de faire, consultez [FAQ sur les domaines](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si vous devez modifier le domaine par défaut alors que votre boîte aux lettres Bookings a déjà été créée, vous pouvez le faire avec PowerShell :

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Pour plus d’informations, consultez la documentation PowerShell pour la cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Si vous utilisez une configuration Exchange hybride, nous vous recommandons de tester minutieusement le flux de courrier entre Exchange local et Exchange Online lorsque vous modifiez le domaine par défaut.

## <a name="sending-feedback"></a>Envoi de commentaires

Vos commentaires sont les bienvenus :

  - Expérience utilisateur ou facilité d’utilisation
  - Lacunes dans les fonctionnalités ou fonctionnalités manquantes
  - Bogues ou problèmes
  
Pour envoyer des commentaires, cliquez sur le bouton **Aide** situé en bas de la barre de navigation gauche de Teams, puis cliquez sur **Signaler un problème** pour **TOUS** les problèmes. Veuillez noter au début de votre rapport de commentaires que vous envoyez des commentaires sur « Bookings » afin que nous pouvons facilement identifier les problèmes de Bookings.

## <a name="related-topics"></a>Rubriques connexes

[Gérer l’expérience de jointisation pour Teams visites virtuelles sur les navigateurs mobiles](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentation Bookings pour les utilisateurs finaux](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
