---
title: Liste de contrôle de l’accès invité Microsoft équipes
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Cette liste de vérification permet de configurer l’accès invité dans l’accès des invités aux équipes Microsoft.
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a>Liste de contrôle de l’accès invité équipes
==========================================

Utilisez cette liste de vérification pour vous aider à activer et configurer la fonction accès invité dans Microsoft Teams en fonction des préférences de votre organisation.




## <a name="--enable-guest-access-at-the-tenant-level"></a>□ Activer invité l’accès au niveau du client

Au minimum, vous devez activer Microsoft Teams pour tous les utilisateurs du type de licence **invité**. Pour obtenir des instructions détaillées, voir [Activer ou désactiver l’accès invité pour les équipes de Microsoft](set-up-guests.md).

![Capture d’écran montre un exemple d’un bouton Paramètres des équipes](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a>□ Activer des paramètres spécifiques pour les canaux 
Dans l’application d’équipes, au niveau de l’équipe individuels, configurer les autorisations invité afin que les invités peuvent créer, mettre à jour et supprimer des canaux. En plus des administrateurs, les propriétaires de l’équipe peuvent configurer ce paramètre.

![Capture d’écran montre un exemple d’un bouton bascule de paramètres d’équipe/canal](media/guest-access-checklist-TeamsSettings2.png)


Pour plus d’informations, y compris les vidéos de procédure, reportez-vous à la section [accès invité dans des équipes de Microsoft](guest-access.md).



## <a name="--configure-sharing-in-office-365"></a>□ Configurer le partage dans Office 365 

□ Assurez-vous que les utilisateurs peuvent ajouter des invités. Voici comment :

1. Dans le centre d’administration Office 365, cliquez sur **paramètres** > **sécurité et confidentialité**.
![Capture d’écran montre un exemple de paramètres de Services](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. Dans le **partage**, sélectionnez **Modifier**. ![Capture d’écran montre un exemple d’un bouton de modification des paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. La valeur **permettent aux utilisateurs de l’ajouter de nouveau invités à cette organisation** **sur**, puis cliquez sur **Enregistrer**. ![Capture d’écran montre un exemple d’un bouton Paramètres de partage](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> Ce paramètre est équivalent au paramètre **peuvent inviter des membres** dans les paramètres de l’utilisateur > utilisateurs externes dans Active Directory Azure.  




## <a name="-configure-office-365-groups"></a>□ Configurer des groupes d’Office 365

Dans le centre d’administration Office 365, cliquez sur **paramètres** > **Services et compléments** > **Groupes d’Office 365**.

Veillez à **que laisser les membres du groupe en dehors du contenu de groupe d’accès organisation** est définie sur **On**. Si ce paramètre est désactivé, les invités ne seront en mesure d’accéder à n’importe quel contenu de groupe.

Assurez-vous que **vous permettent d’ajouter des personnes à l’extérieur de l’organisation à des groupes de propriétaires de groupe** est définie sur **On**. Si ce paramètre est désactivé, les propriétaires de l’équipe ne seront en mesure d’ajouter de nouveaux invités. (Toutefois, si un administrateur a ajouté un utilisateur invité à AD Azure, puis le propriétaire de l’équipe serait en mesure d’ajouter cet utilisateur à l’équipe.) Au minimum, ce paramètre doit être « on » pour prendre en charge de l’accès invité.

Pour obtenir des instructions détaillées sur la configuration de ces paramètres, reportez-vous à la section « Office 365 groupes » [Autoriser l’accès invité dans des équipes de Microsoft](Teams-dependencies.md) et [Autoriser/bloquer l’accès invité à des groupes d’Office 365](https://go.microsoft.com/fwlink/?linkid=869658).
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>Configurer les paramètres □ dans Azure AD entreprise-entreprise (B2B)
1. Connexion à https://portal.azure.com.
2. Dans le volet gauche, cliquez sur **Azure Active directory** .
3. Sous **Gérer**, cliquez sur **paramètres de l’utilisateur**.
4. **Les utilisateurs externes**, assurez-vous que **peuvent inviter des membres** est définie sur **Oui**. ![Capture d’écran montre un exemple d’un bouton Paramètres du DAS. ](media/guest-access-checklist-AADSettings1.png)

    

► Au minimum pour prendre en charge des invités, **peuvent inviter des membres** doit être définie à **Oui**.

> > [!NOTE]
> Si vous définissez **peuvent inviter des membres** **non** et activez l’accès invité dans Office 365 groupes et Teams de Microsoft, les administrateurs peuvent contrôler des invitations des invités dans votre répertoire. Après que les invités sont dans le répertoire, ils peuvent être ajoutés aux équipes par les membres non-admin (propriétaires d’équipe).


Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).







## <a name="-verify-sharing-setting-in-sharepoint"></a>Paramètre de partage vérifier □ dans SharePoint
1. Connectez-vous au Centre d'administration Office 365.
2. Cliquez sur **Admin center**et sélectionnez **SharePoint**.
3. Dans le centre d’administration SharePoint, sélectionnez le **partage**.
4. Assurez-vous que l’option pour **ne pas autoriser le partage à l’extérieur de votre organisation** n’est *pas* sélectionnée. ![Capture d’écran montre un exemple d’un bouton de bascule Sparepoint les paramètres en ligne. ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>Types et licences de compte □ vérifier

- **Compte de licence pour les équipes**: pour un compte « Invité » est associé à une racine dans un compte d’utilisateur réel dans certains autres clients Office 365, ce compte utilisateur réel doit posséder une licence pour les équipes de « Invité ». 
- **Compte doit être Office 365 école ou au travail de compte, ou MSA**: actuellement, les utilisateurs qui ont une adresse de messagerie correspondant à un compte Microsoft (MSA) Active Directory Azure, Office 365 travail ou compte de l’établissement peuvent être ajoutés en tant qu’invité. 
 
## <a name="-configure-environment"></a>Environnement de configuration □


Invités doivent utiliser une authentification multifacteur (AMF) si le locataire hébergement l’exige.
Pour plus d’informations, consultez [modèles d’identité et d’authentification dans des équipes de Microsoft](identify-models-authentication.md).

## <a name="-understand-limitations-for-guests"></a>Limitations de comprendre □ pour les visiteurs

L’expérience de l’invité a des limitations à la conception. Assurez-vous que vous comprenez l’expérience invité afin de ne pas tenter de réparer quelque chose qui n’est pas un problème.
Par exemple, voici une liste de quelques-unes des fonctionnalités qui n’est pas disponible à un invité dans Microsoft Teams :

- OneDrive pour les entreprises
- En dehors des équipes de recherche de personnes
- Calendrier, réunions planifiées ou détails de la réunion
- PSTN
- Organigramme hiérarchique
- Créer ou modifier une équipe
- Recherchez une équipe
- Télécharger des fichiers à une conversation de personne à personne

Pour plus d’informations, consultez [Nouveautés de l’expérience d’invité](guest-experience.md) et [l’accès invité dans groupes d’Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).




## <a name="troubleshooting"></a>Identification et résolution des problèmes

Si vous avez des problèmes avec ajout d’invités dans Teams de Microsoft, consultez le [Guide de dépannage de l’accès invité](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


