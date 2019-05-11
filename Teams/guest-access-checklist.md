---
title: Liste de contrôle de l’accès invité Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Utilisez cette liste de vérification pour vous aider à configurer l’accès invité dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a49090f8ce82d825fc0eb153910d377429595922
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919031"
---
<a name="teams-guest-access-checklist"></a>Liste de contrôle l’accès aux équipes invité
==========================================

Utilisez cette liste de vérification pour vous aider à activer et configurer la fonctionnalité d’accès invité dans Microsoft Teams selon les préférences de votre organisation.

## <a name="understand-the-limitations-for-guests"></a>Comprendre les limites pour les visiteurs

L’expérience de l’invité présente les limitations par sa conception. Assurez-vous que vous comprenez l’expérience invité afin de ne pas essayer de résoudre un élément qui n’est pas un problème. Par exemple, voici une liste de certaines des fonctionnalités qui n’est pas disponible pour un invité dans Microsoft Teams :

- OneDrive entreprise
- Recherche de personnes en dehors des équipes
- Calendrier, les réunions planifiées ou détails de la réunion
- PSTN
- Organigramme hiérarchique
- Créer ou modifier une équipe
- Rechercher une équipe
- Télécharger les fichiers dans une conversation de personne à personne

Pour plus d’informations, voir [Nouveautés de l’expérience de l’invité](guest-experience.md) et [l’accès invité dans des groupes d’Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

### <a name="guest-access-vs-external-access-federation"></a>Accès invité et accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Si vos invités constatez des erreurs de licence

Accès invité dans Microsoft Teams utilise Azure Active Directory entreprise à entreprise (B2B) et son modèle de licence. Si vous voyez la gestion des licences des erreurs, veillez à lire le Guide de gestion des licences B2B pour comprendre les conditions de licence qu'a de votre organisation afin que vos utilisateurs soient en mesure d’invités à votre organisation.

N’oubliez pas les opérations suivantes :

- Pour chaque payante licence Azure AD que vous attribuez à un utilisateur, vos utilisateurs peuvent inviter jusqu'à cinq utilisateurs invités sous l’allocation de l’utilisateur externe.
- Les invités sont les utilisateurs en dehors de votre organisation. Vos employés, sous-traitants sur site, les agents sur site et ainsi de suite ne peut pas être ajoutés en tant qu’invités. Les mêmes s’applique à vos filiales.
- Les licences invité sont comptabilisées par rapport à l’organisation invitation. Considérez cela lorsque vous calculez le nombre de licences dont vous avez besoin.
- Si les invités provenant d’un autre client Office 365 ou sont à l’aide de leurs adresses de messagerie personnels, les licences sont comptabilisées par rapport à votre organisation.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Étape 1 : configurer les paramètres dans Azure AD pour entreprises

1. Se connecter àhttps://portal.azure.com
2. Dans le volet gauche, cliquez sur **Azure Active directory** .
3. Sous **Gérer**, cliquez sur **paramètres de l’utilisateur**.
4. Dans la liste **des utilisateurs externes**, cliquez sur **externe gérer les paramètres de collaboration**.
5. Dans la page **paramètres de collaboration externe** Assurez-vous que **les membres peuvent inviter** est définie sur **Oui**.

      ![Capture d’écran montre un exemple d’une bascule de paramètres DAS. ](media/guest-access-checklist-AADSettings1.png)

    Pour prendre en charge les visiteurs, **les membres peuvent inviter** doit être définie sur **Oui**. 
   
> [!NOTE] 
> Si vous la valeur **membres peuvent inviter** **non** et ensuite activez l’accès invité dans Office 365 groupes et Teams Microsoft, les administrateurs peuvent contrôler les invitations aux invités dans votre répertoire. Une fois que les invités sont dans le répertoire, ils peuvent être ajoutés aux équipes par les membres non-admin qui sont propriétaires d’équipe.

Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).


## <a name="-step-2-configure-office-365-groups"></a>□ Étape 2 : configurer des groupes d’Office 365

1. Dans le centre d’administration Microsoft 365, accédez à **paramètres** > **& Services complémentaires** > **Groupes d’Office 365**.
2. Assurez-vous que **laisser les membres du groupe en dehors du contenu de groupe organisation access** est **activé**. Si ce paramètre est désactivé, les invités sera en mesure d’accéder au contenu de groupe.
3. Assurez-vous que **vous permettent d’ajouter des personnes à l’extérieur de l’organisation aux groupes de propriétaires de groupe** est **activé**. Si ce paramètre est désactivé, les propriétaires de l’équipe sera en mesure d’ajouter de nouveaux invités. Au minimum, ce paramètre doit correspondre à la prise en charge l’accès invité.

     ![Capture d’écran montre la bascule groupes Office 365](media/guest-access-checklist-office365.png)

Pour obtenir des instructions détaillées sur la configuration de ces paramètres, voir la section « Office 365 groupes » dans [Autoriser l’accès invité dans les équipes Microsoft](Teams-dependencies.md)et [gérer l’accès invité dans des groupes d’Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) .
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Étape 3 : activer l’accès invité au niveau du client

Au minimum, vous devez activer l’accès invité pour Teams Microsoft dans le **Centre d’administration équipes Microsoft**. 

1. Dans le centre d’administration équipes, sélectionnez **paramètres à l’échelle de la société** > **accès invité**.
2. Configurer le commutateur **Autoriser l’accès invité dans les équipes Microsoft** **sur**.

    ![Capture d’écran montre un exemple d’un bouton de paramètres d’équipes](media/guest-access-checklist-set-up-guests-image1.png)

3. Sur la même page Configurer d’autres paramètres d’invité dont vous avez besoin.
4. Cliquez sur **Enregistrer**.

Pour obtenir des instructions détaillées, voir [Activer ou désactiver l’accès invité aux équipes de Microsoft](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Étape 4 : configurer le partage dans Office 365 

Assurez-vous que les utilisateurs peuvent ajouter des invités. Voici comment :

1. Dans le centre d’administration Microsoft 365, accédez à **paramètres** > **sécurité & confidentialité**.

     ![Capture d’écran montre un exemple des paramètres des services](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Dans **partage**, sélectionnez **Modifier**.

     ![Capture d’écran montre un exemple d’un partage bascule de paramètres](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. La valeur **permettent aux utilisateurs ajouter de nouveaux invités à cette organisation** **sur**, puis cliquez sur **Enregistrer**.

     ![Capture d’écran montre un exemple d’un partage bascule de paramètres](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Ce paramètre est équivalent au paramètre **d’Inviter des membres** dans **les paramètres utilisateur** > **des utilisateurs externes** dans Azure AD.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Étape 5 : Vérifiez le paramètre partage dans SharePoint

1. Connectez-vous au centre d’administration Microsoft 365.
2. Cliquez sur **Centre d’administration**, puis sélectionnez **SharePoint**.
3. Dans le centre d’administration SharePoint, sélectionnez le **partage**.
4. Assurez-vous que l’option pour **ne pas autoriser le partage en dehors de votre organisation** n’est *pas* sélectionnée.
 
     ![Capture d’écran montre un exemple d’un bouton Paramètres SparePoint en ligne.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Étape 6 : activer les paramètres spécifiques pour les canaux 

Dans l’application d’équipes, au niveau équipe individuels, configurez des autorisations invité afin que les invités peuvent créer, mettre à jour et supprimer des chaînes. En plus des administrateurs, les propriétaires de l’équipe peuvent configurer ce paramètre.

![Capture d’écran montre un exemple d’un bouton bascule les paramètres de l’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Pour plus d’informations, notamment des vidéos de procédures, voir [accès invité dans les équipes Microsoft](guest-access.md).


## <a name="troubleshooting"></a>Résolution des problèmes

Si vous avez des problèmes avec ajout invités dans Microsoft Teams, consultez le [Guide de dépannage de l’accès invité](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


