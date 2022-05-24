---
title: Créer un modèle d’équipe personnalisé dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: aaglick
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer un modèle d’équipe personnalisé dans Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a6d5d119d3b941bae1f3eedc3033a364df2b18a
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646283"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Créer un modèle d’équipe personnalisé dans Microsoft Teams

**Les modèles personnalisés ne sont pas encore pris en charge pour les clients EDU.**

Un modèle d’équipe personnalisé est une structure d’équipe prédéfinie avec un ensemble de canaux, d’onglets et d’applications. Vous pouvez développer un modèle qui vous aide à créer rapidement l’espace de collaboration approprié. Votre modèle d’équipe personnalisé utilise vos paramètres préférés.  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


Pour commencer :

1. Se connecter au Centre d’administration de Microsoft Teams.

2. Dans la navigation de gauche, développez **Teams** >  **ModèlesTeam**.

3. Sélectionnez **Ajouter**.

    ![Image de la boîte de dialogue Modèles d’équipe avec Ajouter mis en surbrillance.](media/team-templates-new.png)

4. Dans la section **Modèles** d’équipe, sélectionnez **Créer un nouveau modèle**.

5. Dans la section **Paramètres du modèle** , renseignez les champs suivants, puis sélectionnez **Suivant** :
    - Nom du modèle
    - Descriptions courtes et longues du modèle
    - Visibilité des paramètres régionaux  

    ![Image de la boîte de dialogue d’affectation de noms des paramètres des modèles d’équipe.](media/template-add-a-name.png)

6. Dans la section **canaux, onglets et applications** , ajoutez les canaux et applications dont votre équipe a besoin.

    1. Dans la section **Canaux** , sélectionnez **Ajouter**.
    2. Dans la boîte de dialogue **Ajouter, nommez** le canal.
    3. Ajoutez une description.
    4. Déterminez si le canal doit être affiché par défaut.
    5. Recherchez un nom d’application que vous souhaitez ajouter au canal.
    6. Sélectionnez **Appliquer** lorsque vous avez terminé.

    ![Image de l’écran Canaux, onglets et applications des modèles d’équipe.](media/template-channels-tabs-apps.png)

8. Sélectionnez **Envoyer** une fois l’opération terminée.

Votre nouveau modèle s’affiche dans la liste **des modèles d’équipe** . Le modèle peut être utilisé pour créer une équipe dans Teams.

> [!Note]
> L’affichage d’un changement de modèle personnalisé dans la galerie peut prendre jusqu’à 24 heures.

## <a name="customizing-website-tab-apps"></a>Personnalisation des applications onglet site web

> [!Note]
> Cette fonctionnalité est en préversion anticipée

Vous pouvez spécifier des URL pour les onglets du site web pour les canaux dans les modèles d’équipe personnalisés. Les utilisateurs finaux qui créent des équipes avec des modèles ont des onglets de site web prédéfinies sur l’URL de site spécifiée.

Pour commencer :

1. Créez un modèle d’équipe ou modifiez un modèle d’équipe existant.

2. Dans la section Canaux, ajoutez un nouveau canal ou sélectionnez un canal existant, puis **sélectionnez Modifier**.

3. Dans la section **Ajouter une application pour ce modèle** , ajoutez une application de site web.

    ![ajouter une application pour cette option de modèle.](media/add-an-app-template.png)

4. Sélectionnez l’icône de modification et entrez l’URL de votre choix.

    ![ajouter une URL d’application.](media/add-url-app-template.png)

5. Sélectionnez **Enregistrer** pour les modifications de votre application onglet, puis **Sélectionnez Appliquer** pour enregistrer vos modifications.

## <a name="known-issues"></a>Problèmes connus

**Problème** : Si vous avez créé une équipe à partir d’un modèle personnalisé qui contenait des onglets personnalisés supplémentaires, vous pouvez voir des onglets vides à la place de vos applications onglet personnalisées. Vos onglets par défaut (tels que **Publications**, **Fichiers** et **Wiki**) s’affichent comme prévu.

**Solution** : pour résoudre ce problème, supprimez l’onglet personnalisé et ajoutez un nouvel onglet avec la même application. Si vous ne disposez pas des autorisations nécessaires pour supprimer l’onglet personnalisé et ajouter un nouvel onglet, contactez le propriétaire de l’équipe pour obtenir de l’aide.

Nous travaillons actuellement sur un correctif pour les futures équipes créées à partir de modèles personnalisés.

**Problème** : lorsque vous utilisez Teams dans le navigateur, certains sites web ne prennent pas en charge le rendu dans un onglet Teams.

![message d’erreur du navigateur.](media/browser-error-message.png)

**Solution** : si vous rencontrez des difficultés pour afficher le contenu de l’onglet site web, vous êtes redirigé vers l’ouverture de l’onglet dans une page web distincte ou l’ouverture de Teams dans l’application de bureau à la place pour afficher votre application onglet site web.

## <a name="related-topics"></a>Voir aussi

- [Démarrage avec des modèles d’équipe dans le Centre d’administration](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer un modèle à partir d’une équipe existante](create-template-from-existing-team.md)
- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](create-template-from-existing-template.md)
