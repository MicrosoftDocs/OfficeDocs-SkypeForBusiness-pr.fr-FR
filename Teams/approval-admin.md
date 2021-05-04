---
title: Disponibilité des applications Approbations dans Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: En savoir plus sur la disponibilité des applications Approbations dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129793"
---
# <a name="teams-approvals-app-availability"></a>Disponibilité de l’application Approbations Teams

L’application Approbations est disponible en tant qu’application personnelle pour tous les utilisateurs de Microsoft Teams.
L’application Approbations offre un moyen simple d’apporter des audits, de la conformité, de la responsabilité et des flux de travail à des approbations structurées et non structurées dans Teams.

 ![affiche l’application Approbations](media/approvals-selection.png)

Les utilisateurs peuvent épingler l’application Approbations pour l’enregistrer dans la barre de menus.

 ![affiche l’application Approbations avec l’option épingler](media/approvalApp-pin.png)

La première approbation créée à partir de l’application Approbations déclenche la mise en service de la solution d’approbation dans l’environnement de service de données courant (CDS) par défaut. Les approbations créées à partir de l’application Approbations seront stockées dans l’environnement CDS par défaut.

Cet article décrit la exigences et les rôles de l’application Approbations.

> [!NOTE]
> Cette fonctionnalité n'a pas encore été publiée pour les utilisateurs des services Cloud de la communauté du secteur public (Cloud de la communauté du secteur public), Cloud de la communauté du secteur public High (GCCH) et Department of Defense (DOD).

## <a name="required-permissions-and-licenses"></a>Autorisations et licences requises

Pour utiliser l’application Approbations, vous devez avoir une autorisation pour les éléments suivants :

- Autorisations pour créer une base de données CDS Microsoft.

- Un compte sur [flow.microsoft.com](https://flow.microsoft.com/)

- Rôle d’administrateur dans l’environnement cible.

- Licence pour une [Power Automate](/power-automate/get-started-approvals), Office 365 ou Dynamics 365.

## <a name="storage-with-cds"></a>Stockage avec CDS

Le modèle de données commun (CDM) est le langage de données partagé utilisé par les applications professionnelles et analytiques dans les CDS. Il s'agit d'un ensemble de schémas de données standardisés et extensibles publiés par Microsoft et ses partenaires, qui permettent d'assurer la cohérence des données et de leur signification entre les applications et les processus métier. En savoir plus sur [Modèle de données courant de Microsoft Power Platform](/power-automate/get-started-approvals).

En savoir plus sur le [flux d’approbation](/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Autorisations de l’application Autorisations Teams

L’application Approbations Teams vous permet d’accéder aux fonctionnalités suivantes :

- Recevoir les messages et les données que vous lui fournissez.

- Vous envoyer des messages et des notifications.

- Rendre les applications et les boîtes de dialogue personnelles sans en-tête fourni par Teams.

- Accéder à vos informations de profil telles que votre nom, adresse e-mail, nom de votre entreprise et la langue par défaut.

- Recevoir les messages et les données que les membres d’une équipe lui fournissent dans un canal.

- Envoyer des messages et des notifications dans un canal.

- Accédez aux informations de votre équipe :
  - nom de l'équipe
  - liste des canaux
  - liste de présence (noms et adresses de courrier des membres de l’équipe).

- Utilisez les informations de l'équipe pour les contacter.

## <a name="disable-the-approvals-app"></a>Gérer l'application Approbations

L’application Approbations est disponible par défaut. Vous pouvez désactiver l’application dans le Centre d’administration Teams.

  1. Se connecter au Centre d’administration de Microsoft Teams.

  2. Développez **Applications Teams** et sélectionnez **Gérer les applications**.

  3. Recherchez l’application Approbations.

     ![affiche la navigation du Centre d’administration avec l’écran Applications Teams > Gérer les applications mis en évidence](media/manage-approval-apps.png)

  4. Sélectionnez Approbations.

  5. Sélectionnez le bouton bascule pour désactiver l’application pour votre organisation.

     ![affiche les détails de l’application Approbations](media/approvals-details.png)

## <a name="retention-policy"></a>Stratégie de rétention

Les approbations créées à partir de l’application Approbations sont stockées dans l’environnement CDS par défaut, qui ne prend pas en charge les sauvegardes pour le moment. En savoir plus sur la [Sauvegarde et restauration des environnements : Plateforme Power \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Audit

L’application Approbations enregistre les événements d’audit dans le Centre de sécurité et conformité Microsoft 365. Vous pouvez afficher le journal d’audit.

1. Accédez au site de conformité Microsoft 365.

2. Sélectionnez la section **Audit**.

3. Recherchez des activités sous **Activités d’approbation de Microsoft Teams**.

Vous pouvez rechercher les activités suivantes :

- Créer une demande d’approbation

- Afficher les détails de la demande d’approbation

- Demande d’approbation approuvée

- Demande d’approbation rejetée

- Demande d’approbation annulée

- Demande d’approbation partagée

- Fichier joint à une demande d’approbation

- Demande d'approbation réaffectée

- Ajout d’une signature électronique à une demande d’approbation

- Affichage des détails de la demande de signature électronique

- Demande de signature électronique examinée

- Demande de signature électronique annulée

Pour accéder à davantage d’approbations d’audit dans flux, activez et configurez l'audit dans l'environnement par défaut pour les entités d'approbation primaires Approbation, Demande d'approbation et Réponse d'approbation. Les opérations de création, de mise à jour et de suppression sont des événements auditables pour les enregistrements d’approbation. En savoir plus sur [Audit des données et de l’activité des utilisateurs pour des raisons de sécurité et de conformité : Plateforme Power \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

L’audit peut être personnalisé davantage dans le [Centre de conformité et sécurité Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Pour utiliser les rapports préconfigurés, connectez-vous à Conformité et sécurité Microsoft 365.

2. Sélectionnez **Recherche et enquête**.

3. Recherchez dans le journal d’audit et sélectionnez l’onglet **Activités Dynamics 365**.

En savoir plus sur [Journalisation des activités de Microsoft Dataverse et des applications pilotées par les modèles :Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sécurité

À partir de l’application Approbations Teams, les utilisateurs ont accès à la création de nouvelles approbations et à l’affichage des approbations envoyées et reçues. Les utilisateurs n’ont pas accès aux approbations créées par d’autres personnes, sauf s’ils répondent ou visualisent la demande.

> [!Note]
> Un utilisateur a le rôle de visionneuse d’une demande s’il fait partie de la conversation ou du canal sur lequel l’approbation a été créée. Il ne peut pas agir sur la demande si ce rôle ne lui a pas été affecté lors de la création de l’approbation.

## <a name="approvals-e-signature-integration"></a>Intégration de la signature électronique Approbations

Les approbations de signature électronique créées à partir de l'application Approbations sont stockées dans l'environnement cloud du fournisseur sélectionné. Pour plus d'informations sur le stockage autour du contrat de signature électronique, consultez la documentation de stockage du fournisseur sélectionné.

Pour utiliser la fonctionnalité de signature électronique de l'application Approbations, vous devez avoir les éléments suivants :

- Licence du fournisseur de signature électronique que vous choisissez d'utiliser. Pour obtenir une licence pour votre organisation, vous devez vous rendre sur le site du fournisseur.

Pour la fonctionnalité de signature électronique Approbations, les partenaires de signature tiers apparaissent par défaut dans l'Teams Approbations. Vous pouvez désactiver des fournisseurs de signature électronique spécifiques en accédant aux paramètres de l'application dans Teams d'administration.

1. Dans le Teams d'administration, sous **Gérer** les applications, sélectionnez l'application **Approbations,** puis **Paramètres.**

2. Par défaut, un bascule est placé à côté de chaque fournisseur de signature électronique (à droite). Faites glisser le curseur vers la gauche pour désactiver un fournisseur de signature électronique spécifique. Si un administrateur Teams désactive un fournisseur, les utilisateurs finaux ne le voient pas lors de la création d'une approbation. Les utilisateurs finaux ne pourront pas non plus afficher les demandes de signature électronique qui ont été faites avec ce fournisseur.

Les approbations de signature électronique créées à partir de l'application Approbations sont stockées dans le cloud du fournisseur sélectionné. Vous devrez donc vous rendre sur le site du fournisseur pour exporter des données relatives aux signatures électronique. Consultez la documentation du fournisseur sur l'exportation et la rétention de ces contrats.
