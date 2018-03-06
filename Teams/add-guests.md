---
title: "Ajouter un invité à une équipe"
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/23/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "Découvrez les outils disponibles pour qu'un administrateur ajoute de nouveaux utilisateurs invités à une organisation, y compris les clients web et de bureau de Microsoft Teams et le portail de collaboration Azure Active Directory B2B."
appliesto:
- Microsoft Teams
ms.openlocfilehash: b885aec6cfd2ca40603a195009b6e001c7e7226e
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
<a name="add-a-guest-to-a-team"></a>Ajouter un invité à une équipe
=====================

Seuls les utilisateurs disposant d'une adresse de messagerie correspondant à un compte scolaire ou professionnel Azure Active Directory ou Office 365 peuvent être ajoutés en tant qu'utilisateurs invités.


En tant qu'administrateur, vous pouvez ajouter un nouvel utilisateur invité à l'organisation de deux manières : 
- Les administrateurs globaux qui sont propriétaires d'une équipe et les propriétaires d'équipe peuvent ajouter un invité à une équipe via les clients de bureau ou Web Microsoft Teams.
- Ajoutez des invités à votre organisation via Azure Active Directory B2B Collaboration. Azure Active Directory B2B Collaboration permet à un administrateur global d'inviter et d'autoriser un ensemble d'utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) de 2 000 lignes au maximum dans le portail B2B Collaboration. Pour plus d'informations, consultez la section [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).



Azure Active Directory B2B Collaboration permet aux organisations d'imposer l'accès conditionnel et les stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B. Ces stratégies peuvent être imposées au niveau du client, de l'application ou d'un utilisateur spécifique, de la même manière qu'elles sont activées pour les employés à plein temps et les membres de l'organisation. Ces stratégies sont imposées au niveau de l'organisation des ressources. Pour plus d'informations, reportez-vous à la rubrique [Accès conditionnel pour les utilisateurs de B2B collaboration](https://go.microsoft.com/fwlink/?linkid=857454). Les utilisateurs invités individuels ne peuvent pas être bloqués.



Les invités que vous avez déjà ajoutés via des groupes Azure Active Directory B2B, Office 365 ou SharePoint Online sont déjà prêts. L'administrateur Office 365 ou un propriétaire d'équipe peut les ajouter dans ses équipes respectives. Si une équipe est déjà rattachée à un groupe Office 365 et qu'un invité est ajouté au groupe, l'invité obtient l'accès à l'équipe. L'ajout d'un invité via le groupe Office 365 ne génère pas d'e-mail d'invitation, un membre de l'équipe devra donc l'en informer.

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).



Vous pouvez suivre l'ajout d'invités dans Azure Active Directory ou dans le Centre de sécurité &amp; conformité d'Office 365. L'ajout d'un invité dans Microsoft Teams est audité et journalisé comme activité d'administration de groupe Azure AD « Membre ajouté au groupe ». Pour plus de détails, reportez-vous aux documents [Audit et création de rapports relatifs à un utilisateur B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=858884) et [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité &amp; conformité d'Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

