---
title: Créer un modèle d’équipe personnalisé dans Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer un modèle d’équipe personnalisé dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e017ac0795d2fdd65d89c0532469e8e269ee0e58
ms.sourcegitcommit: e9f8e1a085cbcd2592d3386fdbcfca8a6e032b10
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50173090"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Créer un modèle d’équipe personnalisé dans Microsoft Teams

**Les modèles personnalisés ne sont pas encore pris en charge pour les clients EDU.**

Un modèle d’équipe personnalisé est une structure d’équipe prédéfinise avec un ensemble de canaux, d’onglets et d’applications. Vous pouvez développer un modèle qui vous permet de créer rapidement l’espace de collaboration qui vous permet de créer le bon espace de collaboration. Votre modèle d’équipe personnalisé utilise vos paramètres préférés.  

Pour commencer :

1. Connectez-vous au Centre d’administration Teams.

2. Dans le groupe de navigation de gauche, **développez les modèles Teams**  >  **Team.**

3. Cliquez sur **Ajouter**.

![Image de la boîte de dialogue Modèles d’équipe avec L’ajout mis en évidence.](media/team-templates-new.png)

4. Dans la section **Modèles d’équipe,** **sélectionnez Créer un tout nouveau modèle.**

5. Dans la section **Paramètres du modèle,** complétez les champs suivants, puis cliquez sur **Suivant**:
    - Nom du modèle
    - Descriptions brèves et longues du modèle
    - Visibilité des paramètres régionaux  

![Image de la boîte de dialogue Paramètres des modèles d’équipe.](media/template-add-a-name.png)

6. Dans la section **Canaux, onglets et** applications, ajoutez les canaux et applications dont votre équipe a besoin.

    1. Dans la section **Canaux,** cliquez sur **Ajouter.**
    2. Dans la boîte **de** dialogue Ajouter, nommez le canal.
    3. Ajoutez une description.
    4. Décidez si le canal doit être affiché par défaut.
    5. Recherchez un nom d’application que vous souhaitez ajouter au canal.
    6. Cliquez sur **Appliquer** quand vous avez terminé.

![Image de l’écran des modèles d’équipe de canaux, d’onglets et d’applications.](media/template-channels-tabs-apps.png)

8. Cliquez sur **Envoyer** lorsque vous avez terminé.

Votre nouveau modèle est affiché dans la liste **des modèles d’équipe.** Le modèle peut être utilisé pour créer une équipe dans Teams.

> [!Note]
> 24 heures peuvent être nécessaire pour que les utilisateurs de Teams voient un modèle personnalisé dans la galerie.

## <a name="known-issues"></a>Problèmes connus 

**Problème**: si vous avez créé une équipe à partir d’un modèle personnalisé qui contenait d’autres onglets personnalisés, vous pouvez voir des onglets vides à la place de vos applications d’onglets personnalisées. Vos onglets par défaut (par exemple, **Publications,** **Fichiers** et **Wiki)** s’afficheront comme prévu.

**Solution**: pour résoudre ce problème, supprimez l’onglet personnalisé et ajoutez un nouvel onglet avec la même application. Nous travaillons actuellement au développement d’un correctif pour tous les modèles personnalisés à partir du 08/02/2021.

## <a name="related-topics"></a>Sujets associés

- [Utiliser des modèles d’équipe dans le Centre d’administration](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer un modèle à partir d’une équipe existante](create-template-from-existing-team.md)
- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](create-template-from-existing-template.md)
