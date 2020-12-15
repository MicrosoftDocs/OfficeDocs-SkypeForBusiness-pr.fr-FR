---
title: Homologations disponibilité des applications dans teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: En savoir plus sur la disponibilité des applications approbations dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675178"
---
# <a name="teams-approvals-app-availability"></a>Les équipes approuvent la disponibilité des applications

[!INCLUDE [preview-feature](includes/preview-feature.md)]

L’application approbations est disponible sous la forme d’une application personnelle pour tous les utilisateurs de Microsoft Teams.
L’application approbations fournit un moyen simple de mettre en place un audit, une conformité, une responsabilité et des flux de travail pour les approbations structurées et non structurées dans Teams.

 ![affiche l’application approbations](media/approvals-selection.png)

Les utilisateurs peuvent épingler l’application approbations pour l’enregistrer dans la barre de menus.

 ![affiche l’application approbations avec l’option code confidentiel](media/approvalApp-pin.png)

La première approbation créée à partir de l’application approbations déclenche la mise en service de la solution d’approbation dans l’environnement de CD-services communs par défaut. Les approbations créées à partir de l’application approbations seront stockées dans l’environnement des CD par défaut.

Cet article décrit les exigences et rôles de l’application approbations.

## <a name="required-permissions-and-licenses"></a>Autorisations et licences requises

Pour utiliser l’application approbations, vous devez disposer des autorisations pour les éléments suivants :

- Autorisations de création d’une base de données Microsoft CDS.

- Un compte sur [Flow.Microsoft.com](https://flow.microsoft.com/)

- Rôle d’administrateur dans l’environnement cible.

- Licence pour une [automate](https://docs.microsoft.com/power-automate/get-started-approvals), une 365 ou une dynamique 365.

## <a name="storage-with-cds"></a>Stockage avec CD

Le modèle de données commun (CDM) est le langage de données partagé utilisé par les applications métier et d’analyse des CD. Il s’agit d’un ensemble de schémas de données standardisés et automatisés publiés par Microsoft et par nos partenaires, qui permettent de faire une cohérence entre les données et leur signification sur les applications et les processus métiers. En savoir plus sur le [modèle de données commun de Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).

En savoir plus sur le [flux de travail approbation](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Autorisations de l’application équipes d’approbations

L’application équipes d’approbation vous permet d’accéder aux fonctionnalités suivantes :

- Recevoir des messages et des données que vous leur fournissez ;

- Vous envoyer des messages et des notifications.

- Afficher des applications personnelles et des boîtes de dialogue sans en-tête fourni par Teams.

- Accédez à vos informations de profil, telles que votre nom, votre adresse de messagerie, le nom de votre société et la langue par défaut.

- Recevez des messages et des données que les membres de l’équipe y fournissent dans un canal.

- Envoyer des messages et des notifications dans un canal.

- Accédez aux informations de votre équipe :
  - nom de l’équipe
  - liste de canaux
  - liste (noms des membres de l’équipe et adresses de courrier).

- Utilisez les informations de l’équipe pour les contacter.

## <a name="disable-the-approvals-app"></a>Désactiver l’application approbations

L’application approbations est disponible par défaut. Vous pouvez désactiver l’application dans le centre d’administration Teams.

  1. Connectez-vous au centre d’administration Teams.

  2. Développez **applications teams** , puis sélectionnez **gérer les applications**.

  3. Recherchez l’application approbations.

![affiche la navigation dans le centre d’administration avec les applications teams > gérer les applications en surbrillance](media/manage-approval-apps.png)

  4. Sélectionnez approbations.

  5. Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.

![affiche les détails de l’application approbations](media/approvals-details.png)

## <a name="retention-policy"></a>Stratégie de rétention

Les approbations créées à partir de l’application approbations sont stockées dans l’environnement des CD par défaut, qui ne prend pas en charge les sauvegardes pour le moment. Apprenez-en davantage sur la manière de [sauvegarder et de restaurer des environnements : \| documents Microsoft](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Audit

L’application approbations enregistre les événements d’audit dans le centre de sécurité et conformité Microsoft 365. Vous pouvez afficher le journal d’audit.

1. Accédez au site de conformité M365.

2. Sélectionnez la section **audit** .

3. Recherchez des activités dans les **activités d’approbations de Microsoft teams**.

Vous pouvez rechercher les activités suivantes :

- Créer une demande d’approbation

- Afficher les détails de la demande d’approbation

- Demande d’approbation approuvée

- Demande d’approbation rejetée

- Demande d’approbation annulée

- Demande d’approbation partagée

- Fichier joint à une demande d’approbation

- Demande d’approbation réaffectée

- A ajouté une signature électronique à la demande d’approbation

Pour accéder à d’autres approbations d’audit au sein d’un flux, activez et configurez l’audit dans l’environnement par défaut pour l’approbation des entités d’approbation principales, la demande d’approbation et la réponse d’approbation. Les opérations de création, de mise à jour et de suppression sont des événements pouvant être audité pour les enregistrements approbation. En savoir plus sur [les données d’audit et l’activité des utilisateurs pour la sécurité et la conformité- \| documentation Microsoft sur la plateforme](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

Les contrôles peuvent être personnalisés davantage dans le [Centre de sécurité et conformité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Pour utiliser les rapports préconfigurés, connectez-vous à Office 365 Security and Compliance.

2. Sélectionnez **rechercher & examen**.

3. Recherchez dans le journal d’audit et sélectionnez l’onglet **activités de Dynamics 365** .

En savoir plus sur la journalisation de l’activité des applications basées sur Microsoft Dataverse et celles basées sur le [modèle-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sécurité

À partir de l’application approbation des équipes, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations qu’ils ont envoyées et reçues. Les utilisateurs ne peuvent pas accéder aux approbations créées par d’autres personnes, sauf s’il s’agit d’un répondeur ou d’une visionneuse de la requête.

> [!Note]
> Un utilisateur aura le rôle de visionneuse d’une demande s’il fait partie d’une conversation ou d’un canal de création de l’approbation. Ils ne seront pas en mesure d’effectuer une action sur la demande s’ils n’ont pas donné ce rôle lors de la création de l’approbation.
