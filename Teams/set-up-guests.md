---
title: Activer ou désactiver l’accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Découvrez comment activer ou désactiver la fonctionnalité d'accès invité dans Microsoft Teams en tant qu'administrateur d'Office 365.
ms.openlocfilehash: 1658ef97dd172209a965088caa2842a71e09e4e7
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839195"
---
# <a name="turn-guest-access-in-microsoft-teams-on-or-off"></a>Activer ou désactiver l’accès invité dans Microsoft Teams

Cet article explique comment configurer les paramètres d’accès invité , notamment les appels, les réunions et les conversations , dans Teams. L’accès invité dans Teams nécessite également la configuration d’autres paramètres dans Microsoft 365, notamment les paramètres dans Azure AD, Groupes Microsoft 365 et SharePoint. Si vous êtes prêt à commencer à inviter des personnes à faire partie d'une équipe, lisez ce qui suit :

- Pour configurer l’accès invité pour Teams à des fins d’utilisation générale, consultez [Collaborer avec des invités dans une équipe](/microsoft-365/solutions/collaborate-as-team).
- Pour collaborer avec une organisation partenaire qui utilise Azure Active Directory et autoriser les invités à s’inscrire automatiquement pour l’accès d’équipe, consultez [créer un extranet B2B avec des invités gérés](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Si vous voulez simplement rechercher, appeler, discuter et configurer des réunions avec des personnes d’autres organisations, utilisez [Accès externe](manage-external-access.md).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurer l’accès invité dans le centre d’administration de Teams

1. Se connecter au [Centre d’administration de Microsoft Teams](https://admin.teams.microsoft.com/).

2. Sélectionnez **l’accès** **UsersGuest** > .

3. Définissez **Autoriser l’accès invité dans Teams** **sur Activé**.

    ![Autoriser le commutateur d’accès invité défini sur Activé .](media/guest-access-setting.png)

4. Sous **Appel**, **Réunion** et **Messagerie**, sélectionnez **Activé** ou **Désactivé** pour chaque fonctionnalité, en fonction de ce que vous souhaitez autoriser pour les invités.

      - **Passer des appels privés** : mettre ce paramètre sur **On** pour permettre aux invités d’effectuer des appels privés.
      - **Vidéo IP** : activez **ce paramètre pour** permettre aux invités d’utiliser la vidéo dans leurs appels et réunions.
      - **Mode de partage d’écran** : ce paramètre contrôle la disponibilité du partage d’écran pour les invités.
          - Mettre ce paramètre sur **Désactivé** pour supprimer la possibilité pour les invités de partager leurs écrans dans Teams.
          - Activez ce paramètre sur **Application unique** pour autoriser le partage d’applications individuelles.
          - Activez ce paramètre sur **Écran entier** pour autoriser le partage d’écran entier.
      - **Meet Now** : activez **ce paramètre pour** permettre aux invités d’utiliser la fonctionnalité Meet Now dans Microsoft Teams.
      - **Modifier les messages envoyés** : mettre ce paramètre sur **On** pour permettre aux invités de modifier les messages électroniques qu’ils ont envoyés précédemment.
      - **Supprimer les messages envoyés** : activez **ce paramètre pour** permettre aux invités de supprimer les messages qu’ils ont envoyés précédemment.
      - **Conversation** : mettre ce paramètre sur **On** pour donner aux invités la possibilité d’utiliser la conversation dans Teams.
      - **Giphy dans les conversations** : activez **ce paramètre pour** permettre aux invités d’utiliser Giphys dans les conversations. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu.
      - **Évaluation du contenu Giphy** : sélectionner une note dans la liste déroulante :
          - **Autoriser tout le contenu** : les invités pourront insérer tous les Giphys dans des conversations, quelle que soit l’évaluation du contenu.
          - **Modéré** : les invités pourront insérer Giphys dans les conversations, mais seront relativement limités pour le contenu adulte.
          - **Strict** : les invités peuvent insérer des giphys dans les conversations, mais ne pourront pas insérer de contenu pour adultes.
      - **Mèmes dans les conversations** : activez **ce paramètre pour** permettre aux invités d’utiliser Memes dans les conversations.
      - **Autocollants dans les conversations** : activez **ce paramètre pour** permettre aux invités d’utiliser des autocollants dans les conversations.
      - **Lecteur immersif pour les messages** : activez **ce paramètre pour** permettre aux invités d’utiliser [le lecteur immersif dans Teams](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a).

    ![Paramètres des autorisations d’invité dans Teams.](media/manage-guest-access-image1.png)

5. Sélectionnez **Enregistrer**.

## <a name="turning-guest-access-off"></a>Désactivation de l’accès invité

Si vous désactivez l’accès invité dans Teams, les invités existants perdent l’accès à leur équipe. Toutefois, ils ne sont pas supprimés de l’équipe. Ils sont toujours visibles par les membres de l’équipe et peuvent être @mentionés. Si vous réactivez l’accès invité Teams, celui-ci retrouvera l’accès.

Si vous envisagez de laisser l’accès invité désactivé, vous pouvez conseiller aux propriétaires de votre équipe de supprimer manuellement les comptes invités de leurs équipes. Si ces invités n’y ont pas accès, la visibilité de leur compte dans l’équipe peut semer la confusion chez les autres membres.


## <a name="see-also"></a>Voir aussi

[Configurer la collaboration sécurisée avec Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloquer les invités d’une équipe spécifique](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
