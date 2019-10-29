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
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753319"
---
<a name="microsoft-teams-guest-access-checklist"></a>Liste de contrôle de l’accès invité Microsoft Teams
==========================================

Utilisez cette liste de vérification pour vous aider à activer et configurer l’accès invité dans Microsoft Teams.

> [!IMPORTANT]
> Il est possible que vous deviez attendre 24 heures pour que vos modifications soient prises en compte. 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>Étape 1 : activer l’accès invité pour le niveau de l’organisation au sein de l’Organisation

Pour activer l’accès invité, accédez au **Centre d’administration Microsoft teams**. 

1. Dans le centre d’administration Teams, sélectionnez > **accès invité aux**paramètres à l' **échelle de l’organisation**.
2. Activez l’option **autoriser l’accès invité dans Microsoft teams** **.**

    ![Capture d’écran montrant un exemple de bouton bascule pour les paramètres d’équipe](media/guest-access-checklist-set-up-guests-image1.png)

3. Dans la même page, activez ou désactivez les paramètres d' **appel**, de **réunion**et de **messagerie** pour les invités.
4. Cliquez sur **Enregistrer**.

> [!TIP]
> Si vous utilisez les paramètres par défaut dans les groupes Azure Active Directory, SharePoint Online et Office 365, il est possible que vous ayez terminé de configurer l’accès invité. Dans ce cas, vous pouvez ignorer les étapes restantes. Si vous n’êtes pas sûr, ou si vous utilisez des paramètres personnalisés pour les groupes AAD, SharePoint Online ou Office 365, poursuivez le reste des étapes décrites dans cette liste de vérification.


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>Étape 2 : configurer les paramètres d’entreprise pour les entreprises d’Azure AD

1. Connectez-vous au [portail Azure](https://portal.azure.com) en tant qu’administrateur client.
2. Sélectionnez > **utilisateurs**d' **Azure Active Directory** > **paramètres utilisateur**.
3. Sous **utilisateurs externes**, sélectionnez **gérer les paramètres de collaboration externes**.
   > [!NOTE]
   > Les **paramètres de collaboration externes** sont également disponibles à partir de la page **relations d’organisation** . Dans Azure Active Directory, sous **Manage (gérer**), accédez à**paramètres**de l' **organisation** > .
4. Dans la page **paramètres de collaboration externe** , sélectionnez les stratégies que vous souhaitez activer.

  - **Les autorisations des utilisateurs invités sont limitées**: cette stratégie détermine les autorisations des invités dans votre annuaire. Sélectionnez **Oui** pour bloquer les invités de certaines tâches d’annuaire, comme l’énumération des utilisateurs, des groupes ou d’autres ressources de l’annuaire. Sélectionnez **non** pour permettre aux invités d’accéder aux données de l’annuaire en tant qu’utilisateurs réguliers dans votre annuaire.
   - Les **administrateurs et les utilisateurs du rôle d’invité invité peuvent inviter**: pour permettre aux administrateurs et aux utilisateurs du rôle « invité invité » d’inviter des invités, définissez cette stratégie sur **Oui**.
   - **Les membres peuvent inviter**: pour autoriser les membres non administrateur de votre annuaire à inviter des invités, attribuez la valeur **Oui**à cette stratégie.
   
       > [!NOTE]
       > Si vous définissez des **membres comme invités** sur **non** , puis activez l’accès invité aux groupes Office 365 et Microsoft Teams, l’administrateur peut contrôler les invitations des invités à votre annuaire. Lorsque les invités sont dans l’annuaire, ils peuvent être ajoutés à des équipes par des membres non administrateurs qui sont des propriétaires d’équipe. Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).
       > [!IMPORTANT]
       > Pour que l’accès invité puisse fonctionner du tout dans Teams, vous devez définir **les membres peuvent inviter** sur **Oui**.   
   - Les **invités peuvent inviter**: pour permettre aux invités d’inviter d’autres personnes, attribuez la valeur **Oui**à cette stratégie.
       > [!IMPORTANT]
       > Pour l’instant, Teams ne prend pas en charge le rôle d’invité invité, donc même si vous définissez les **invités peuvent inviter** sur **Oui**, les invités ne peuvent pas inviter d’autres invités dans Teams.
   - **Activer le mot de passe unique pour les invités (** préversion) : pour plus d’informations sur la fonctionnalité de code secret unique, voir [authentification par code électronique unique (Preview) par courrier électronique](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
   - **Restrictions de collaboration**: pour plus d’informations sur l’autorisation ou le blocage d’invitations dans des domaines spécifiques, voir [autoriser ou bloquer les invitations d’utilisateurs B2B d’organisations spécifiques](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
      > [!NOTE]
      > Pour des restrictions de collaboration, voir [activer la collaboration externe B2B et gérer qui peut inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
 
Pour plus d’informations sur le contrôle de qui peut ajouter des invités, voir [Permettre une collaboration B2B externe et gérer qui peut inviter des invités](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).


## <a name="step-3-configure-office-365-groups"></a>Étape 3 : configurer les groupes Office 365

1. Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **des services & des** > compléments**Office 365**.
2. Veillez **à**ce que **les membres du groupe qui se trouvent en dehors de l’organisation aient accès au contenu du groupe** . Si ce paramètre est désactivé, les invités ne seront pas en mesure d’accéder aux contenus du groupe.
3. Assurez-vous que **les propriétaires de groupe peuvent ajouter des personnes en dehors de l’organisation aux groupes** est **activé**. Si ce paramètre est désactivé, les propriétaires d’équipe ne peuvent pas ajouter de nouveaux invités. Ce paramètre doit être activé pour prendre en charge l’accès invité.

     ![La capture d’écran indique le bouton bascule groupes d’Office 365](media/guest-access-checklist-office365.png)

Pour obtenir des instructions détaillées sur la configuration de ces paramètres, voir [gérer l’accès invité dans les groupes office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) et [contrôler l’accès invité dans les groupes Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="step-4-configure-sharing-in-office-365"></a>Étape 4 : configurer le partage dans Office 365 

Assurez-vous que les utilisateurs peuvent ajouter des invités. Voici comment procéder :

1. Dans le centre d’administration 365 de Microsoft, accédez à **paramètres** > **sécurité & confidentialité**.

     ![Capture d’écran illustrant un exemple de paramètres de services](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Dans **partage**, sélectionnez **modifier**.

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Définissez **permettre aux utilisateurs d’ajouter des invités à cette organisation** **, puis**cliquez sur **Enregistrer**.

     ![La capture d’écran illustre un exemple de bascule paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Ce paramètre est équivalent au paramètre les **membres peuvent inviter** dans les **paramètres** > de l’utilisateur**les utilisateurs externes** d’Azure ad.  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Étape 5 : vérifier le paramètre de partage dans SharePoint

C’est un peu d’une prétease Brain. L’accès invité dans Teams ne fonctionne pas si le paramètre **ne pas autoriser le partage à l’extérieur de votre organisation** est sélectionné dans le centre d’administration SharePoint.

1. Connectez-vous au centre d’administration Microsoft 365.
2. Cliquez sur **Centre d’administration**, puis sélectionnez **SharePoint**.
3. Dans le centre d’administration SharePoint, sélectionnez **partage**.
4. Assurez-vous que l’option ne pas autoriser le partage à l' **extérieur de votre organisation** n’est *pas* sélectionnée.
 
     ![Capture d’écran illustrant un exemple de bouton bascule SparePoint en ligne.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>Étape 6 : configurer les autorisations des utilisateurs invités

Dans l’application Teams, au niveau de l’équipe individuelle, configurez des autorisations d’invité pour contrôler si les invités peuvent créer, mettre à jour ou supprimer des canaux. Les administrateurs des équipes et les propriétaires d’équipe peuvent configurer ces paramètres.

![Capture d’écran montrant un exemple de bascule des paramètres d’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Pour en savoir plus sur l’accès invité, voir [accès invité dans Microsoft teams](guest-access.md) et [activation ou désactivation de l’accès invité à Microsoft teams](set-up-guests.md).


## <a name="troubleshooting"></a>Résolution des problèmes

Si vous rencontrez des problèmes pour configurer l’accès invité ou ajouter des invités dans Microsoft Teams, utilisez les ressources suivantes pour vous aider :

[Résoudre les problèmes liés à l’accès invité dans Microsoft teams](troubleshoot-guest-access.md)

[Résolution des problèmes dans teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



