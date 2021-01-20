---
title: Disponibilité des applications d’approbation dans Teams
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
description: En savoir plus sur la disponibilité de l’application Approbations dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909518"
---
# <a name="teams-approvals-app-availability"></a>Disponibilité de l’application Approbations Teams

L’application Approbations est disponible en tant qu’application personnelle pour tous les utilisateurs de Microsoft Teams.
L’application Approbations permet d’apporter un moyen simple d’audit, de conformité, d’imputation et de flux de travail à des approbations structurées et non structurées dans Teams.

 ![affiche l’application Approbations](media/approvals-selection.png)

Les utilisateurs peuvent épingler l’application Approbations pour l’enregistrer dans la barre de menus.

 ![affiche l’application Approbations avec l’option épingler](media/approvalApp-pin.png)

La première approbation créée à partir de l’application Approbations déclenche la mise en service de la solution d’approbation dans l’environnement de service de données communs par défaut. Les approbations créées à partir de l’application Approbations seront stockées dans l’environnement CDS par défaut.

Cet article décrit la exigences et les rôles de l’application Approbations.

## <a name="required-permissions-and-licenses"></a>Autorisations et licences requises

Pour utiliser l’application Approbations, vous devez être autorisé à utiliser les éléments suivants :

- Autorisations de création d’une base de données CDS Microsoft.

- Un compte sur [flow.microsoft.com](https://flow.microsoft.com/)

- Rôle d’administrateur dans l’environnement cible.

- Licence pour [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 ou Dynamics 365.

## <a name="storage-with-cds"></a>Stockage avec CDS

Le modèle de données commun (CDM) est le langage de données partagé utilisé par les applications d’analyse et d’entreprise dans les CDS. Il se compose d’un ensemble de schémas de données standardisés et extensibles publiés par Microsoft et nos partenaires, qui permet la cohérence des données et leur signification au sein des applications et des processus d’entreprise. En savoir plus sur [le modèle de données courant de la plateforme Microsoft Power Platform.](https://docs.microsoft.com/power-automate/get-started-approvals)

En savoir plus sur le [flux de travail Approbation.](https://docs.microsoft.com/power-automate/modern-approvals)

## <a name="approvals-teams-app-permissions"></a>Autorisations de l’application Teams Approbations

L’application Teams Approbations vous permet d’accéder aux fonctionnalités suivantes :

- Recevoir les messages et les données que vous lui fournissez.

- Vous envoyer des messages et des notifications.

- Restituer des applications et des boîtes de dialogue personnelles sans en-tête fourni par Teams.

- Accédez à vos informations de profil, telles que votre nom, votre adresse de messagerie, le nom de votre entreprise et votre langue préférée.

- Recevoir les messages et les données que les membres d’une équipe lui fournissent dans un canal.

- Envoyer des messages et des notifications dans un canal.

- Accédez aux informations de votre équipe :
  - nom de l’équipe
  - liste des canaux
  - liste (noms et adresses de courrier du membre de l’équipe).

- Utilisez les informations de l’équipe pour les contacter.

## <a name="disable-the-approvals-app"></a>Désactiver l’application Approbations

L’application Approbations est disponible par défaut. Vous pouvez désactiver l’application dans le Centre d’administration Teams.

  1. Connectez-vous au Centre d’administration Teams.

  2. Développez **les applications Teams,** puis **sélectionnez Gérer les applications.**

  3. Recherchez l’application Approbations.

![Affiche la navigation dans le Centre d’administration avec l'> Gérer les applications mise en évidence](media/manage-approval-apps.png)

  4. Sélectionnez Approbations.

  5. Sélectionnez le basculement pour désactiver l’application pour votre organisation.

![affiche les détails de l’application Approbations](media/approvals-details.png)

## <a name="retention-policy"></a>Stratégie de rétention

Les approbations créées à partir de l’application Approbations sont stockées dans l’environnement CDS par défaut, qui ne prend pas en charge les sauvegardes pour le moment. En savoir plus sur la [restauration et la restauration des environnements - Power Platform Microsoft \| Docs.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)

## <a name="auditing"></a>Audit

L’application Approbations enregistre les événements d’audit dans le Centre de sécurité et conformité Microsoft 365. Vous pouvez afficher le journal d’audit.

1. Allez sur le site de conformité Microsoft 365.

2. Sélectionnez la section **Audit.**

3. Recherchez des activités sous **les activités d’approbation de Microsoft Teams.**

Vous pouvez rechercher les activités suivantes :

- Créer une demande d’approbation

- Afficher les détails de la demande d’approbation

- Demande d’approbation approuvée

- Demande d’approbation refusée

- Demande d’approbation annulée

- Demande d’approbation partagée

- Fichier joint à une demande d’approbation

- Demande d’approbation résignée

- Signature électronique ajoutée à la demande d’approbation

Pour accéder à d’autres approbations d’audit au sein du flux, activez et configurez l’audit dans l’environnement par défaut pour les entités d’approbation principale approbation, demande d’approbation et réponse d’approbation. Les opérations de création, de mise à jour et de suppression sont des événements auditables pour les enregistrements Approbation. En savoir plus sur [l’audit des données et l’activité des utilisateurs pour la sécurité et la conformité - Power Platform \| Microsoft Docs.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)

L’audit peut être davantage personnalisé dans le Centre de sécurité et conformité [Microsoft 365.](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)

1. Pour utiliser les rapports préconfigurés, connectez-vous à Microsoft 365 Sécurité et conformité.

2. Sélectionnez **Recherches & investigation.**

3. Recherchez dans le journal d’audit et sélectionnez **l’onglet Activités de Dynamics 365.**

En savoir plus sur [la journalisation de l’activité de Microsoft Dataverse](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)et des applications pilotées par un modèle - Plateforme Power.

## <a name="security"></a>Sécurité

À partir de l’application Approbations Teams, les utilisateurs ont accès à créer des approbations et à afficher les approbations qu’ils ont envoyées et reçues. Les utilisateurs n’ont pas accès aux approbations créées par d’autres personnes, sauf s’ils sont un répondant ou une visionneuse de la demande.

> [!Note]
> Un utilisateur pourra voir le rôle de visionneuse d’une demande s’il fait partie de la conversation ou du canal sur lequel l’approbation a été créée. Ils ne pourront pas agir sur la demande s’ils n’ont pas reçu ce rôle lors de la création de l’approbation.
