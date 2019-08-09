---
title: Liste de contrôle de l’accès invité Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Utilisez cette liste de contrôle pour configurer l’accès invité dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83cd25ed9f675f04f090255cbc387275c0dee90d
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253917"
---
<a name="teams-guest-access-checklist"></a>Liste de vérification de l’accès invité teams
==========================================

Utilisez cette liste de vérification pour vous aider à activer et configurer la fonctionnalité d’accès invité dans Microsoft Teams, conformément aux préférences de votre organisation.

> [!NOTE] 
> Pour les restrictions de collaboration [, voir Activer la collaboration externe B2B et gérer qui peut inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="understand-the-limitations-for-guests"></a>Comprendre les limites applicables aux invités

L’interface des invités a des limitations par conception. Assurez-vous de bien comprendre le fonctionnement des invités afin de ne pas tenter de résoudre un problème qui ne pose pas de problème. Par exemple, voici une liste des fonctionnalités qui ne sont pas disponibles pour un invité dans Microsoft teams:

- OneDrive entreprise
- Recherche de personnes en dehors de teams
- Calendrier, réunions planifiées ou détails de la réunion
- PSTN
- Organigramme hiérarchique
- Créer ou réviser une équipe
- Rechercher une équipe
- Télécharger des fichiers dans une conversation de personne à personne
- Les invités peuvent toujours Rechercher et Rechercher des utilisateurs (en dehors de leur équipe) s’ils connaissent l’ID de courrier complet de l’utilisateur. Pour éviter ce problème, les administrateurs informatiques peuvent utiliser les modèles tels que la recherche dans l' [Annuaire](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) et permettent de limiter les invités à leur propre gal virtuelle.

Pour plus d’informations, reportez-vous à [l’interface utilisateur](guest-experience.md) et [accès invité dans les groupes Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

### <a name="guest-access-vs-external-access-federation"></a>Accès invité et accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> Pour le moment, Microsoft Teams ne prend pas en charge le rôle d’invité invité. Au minimum, le bouton bascule «les membres peuvent inviter» doit être défini sur «Oui» pour que l’accès invité puisse travailler dans Microsoft Teams. Si vous définissez «les membres peuvent inviter» sur «non», puis activez l’accès invité aux groupes Office 365 et Microsoft Teams, les administrateurs peuvent contrôler les invitations invitées dans votre annuaire. Lorsque les invités sont dans l’annuaire, ils peuvent être ajoutés à des équipes par des membres non administrateurs qui sont des propriétaires d’équipe.

## <a name="if-your-guests-are-seeing-license-errors"></a>Si vos invités voient des erreurs de licence

L’accès invité dans Microsoft teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence. Si vous rencontrez des erreurs de gestion des licences, veillez à lire les [recommandations](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) en matière de gestion des licences interentreprises pour comprendre les exigences en matière de licences dont dispose votre organisation afin que vos utilisateurs puissent inviter des invités à votre organisation.

Quelques points à garder à l’esprit:

- Les invités sont des utilisateurs extérieurs à votre organisation. Vos employés, entrepreneurs et prestataires de site, et ainsi de suite ne peuvent pas être ajoutés comme invités. Il en va de même pour vos affiliés.
- Les licences invité sont comptabilisées au niveau de l’organisation d’invitation. Tenez compte de ce qui suit lorsque vous calculez le nombre de licences dont vous avez besoin.
- Les licences sont comptabilisées au niveau de votre organisation, que les invités invités proviennent d’un autre client Office 365 ou utilisent leurs adresses de messagerie personnelles.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Étape 1: configurer les paramètres d’Azure AD Business-to-Business

1. Connectez-vous au [portail Azure](https://portal.azure.com) en tant qu’administrateur client.
2. Sélectionnez > **utilisateurs**d' **Azure Active Directory** > **paramètres utilisateur**.
3. Sous **utilisateurs externes**, sélectionnez **gérer les paramètres de collaboration externes**.
   > [!NOTE]
   > Les **paramètres de collaboration externes** sont également disponibles à partir de la page **relations d’organisation** . Dans Azure Active Directory, sous **Manage (gérer**), accédez à**paramètres**de l' **organisation** > .
4. Dans la page **paramètres de collaboration externe** , sélectionnez les stratégies que vous souhaitez activer.

  - **Les autorisations des utilisateurs invités sont limitées**: cette stratégie détermine les autorisations des invités dans votre annuaire. Sélectionnez **Oui** pour bloquer les invités de certaines tâches d’annuaire, comme l’énumération des utilisateurs, des groupes ou d’autres ressources de l’annuaire. Sélectionnez **non** pour permettre aux invités d’accéder aux données de l’annuaire en tant qu’utilisateurs réguliers dans votre annuaire.
   - Les **administrateurs et les utilisateurs du rôle d’invité invité peuvent inviter**: pour permettre aux administrateurs et aux utilisateurs du rôle «invité invité» d’inviter des invités, définissez cette stratégie sur **Oui**.
   - **Les membres peuvent inviter**: pour autoriser les membres non administrateur de votre annuaire à inviter des invités, attribuez la valeur **Oui**à cette stratégie.
   
       > [!NOTE]
       > Si vous définissez des **membres comme invités** sur **non** , puis activez l’accès invité aux groupes Office 365 et Microsoft Teams, l’administrateur peut contrôler les invitations des invités à votre annuaire. Lorsque les invités sont dans l’annuaire, ils peuvent être ajoutés à des équipes par des membres non administrateurs qui sont des propriétaires d’équipe. Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).
   
   - Les **invités peuvent inviter**: pour permettre aux invités d’inviter d’autres personnes, attribuez la valeur **Oui**à cette stratégie.
   - **Activer le mot de passe unique pour les invités (** préversion): pour plus d’informations sur la fonctionnalité de code secret unique, voir [authentification par code électronique unique (Preview) par courrier électronique](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).

   - **Restrictions de collaboration**: pour plus d’informations sur l’autorisation ou le blocage d’invitations dans des domaines spécifiques, voir [autoriser ou bloquer les invitations d’utilisateurs B2B d’organisations spécifiques](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
    
## <a name="-step-2-configure-office-365-groups"></a>□ Étape 2: configurer les groupes Office 365

1. Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **des services & des** > compléments**Office 365**.
2. Veillez à **ce que les membres du groupe qui se trouvent en dehors de l’organisation aient accès au contenu du groupe** . **** Si ce paramètre est désactivé, les invités ne seront pas en mesure d’accéder aux contenus du groupe.
3. Assurez-vous que **les propriétaires de groupe peuvent ajouter des personnes en dehors de l’organisation aux groupes** est **activé**. Si ce paramètre est désactivé, les propriétaires d’équipe ne peuvent pas ajouter de nouveaux invités. Ce paramètre doit être activé pour prendre en charge l’accès invité.

     ![La capture d’écran indique le bouton bascule groupes d’Office 365](media/guest-access-checklist-office365.png)

Pour obtenir des instructions détaillées sur la configuration de ces paramètres, voir [gérer l’accès invité dans les groupes office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) et [contrôler l’accès invité dans les groupes Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Étape 3: activer l’accès invité au niveau du client

Au minimum, vous devez activer l’accès invité de Microsoft teams dans le **Centre d’administration Microsoft teams**. 

1. Dans le centre d’administration Teams, sélectionnez > **accès invité aux**paramètres à l' **échelle de l’organisation**.
2. Activez l’option **autoriser l’accès invité dans Microsoft teams** . ****

    ![Capture d’écran montrant un exemple de bouton bascule pour les paramètres d’équipe](media/guest-access-checklist-set-up-guests-image1.png)

3. Dans la même page, configurez les autres paramètres invités dont vous avez besoin.
4. Cliquez sur **Enregistrer**.

Pour obtenir des instructions détaillées, voir [activer ou désactiver l’accès invité à Microsoft teams](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Étape 4: configurer le partage dans Office 365 

Assurez-vous que les utilisateurs peuvent ajouter des invités. Voici comment procéder:

1. Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **sécurité & confidentialité**.

     ![Capture d’écran illustrant un exemple de paramètres de services](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Dans **partage**, sélectionnez **modifier**.

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Définissez **permettre aux utilisateurs d’ajouter des invités à cette organisation** , puis cliquez sur **Enregistrer**. ****

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Ce paramètre est équivalent au paramètre les **membres peuvent inviter** dans les **paramètres** > de l’utilisateur**les utilisateurs externes** d’Azure ad.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ L’étape 5: vérifier le paramètre de partage dans SharePoint

1. Connectez-vous au centre d’administration Microsoft 365.
2. Cliquez sur **Centre d’administration**, puis sélectionnez **SharePoint**.
3. Dans le centre d’administration SharePoint, sélectionnez **partage**.
4. Assurez-vous que l’option ne pas autoriser le partage à l' **extérieur de votre organisation** n’est *pas* sélectionnée.
 
     ![Capture d’écran illustrant un exemple de bouton bascule SparePoint en ligne.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Étape 6: activer des paramètres spécifiques pour les canaux 

Dans l’application Teams, au niveau de l’équipe individuelle, configurez des autorisations d’invité pour permettre aux invités de créer, mettre à jour et supprimer des canaux. Outre les administrateurs, les propriétaires d’équipe peuvent configurer ce paramètre.

![Capture d’écran montrant un exemple de bascule des paramètres d’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Pour plus d’informations, y compris des vidéos sur les procédures, voir [accès invité dans Microsoft teams](guest-access.md).


## <a name="troubleshooting"></a>Résolution des problèmes

Si vous rencontrez des problèmes lors de l’ajout d’invités dans Microsoft Teams, voir le [Guide de résolution des problèmes d’accès invité](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


