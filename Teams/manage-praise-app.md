---
title: Gérer l’application compliment dans le centre d’administration teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: En savoir plus sur les paramètres d’administration dans l’application compliment dans le centre d’administration Microsoft teams
ms.openlocfilehash: a04287ca6873d4dee9c58302ca563b167a592f3a
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324028"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gérer l’application compliment dans le centre d’administration Microsoft teams

Dans Microsoft Teams, l’application compliments permet aux utilisateurs d’afficher une reconnaissance aux membres de leur organisation ou Classroom. Avec une sélection de jeux de badges à partir desquels vous pouvez créer vos propres badges, compliment est conçu pour vous aider à reconnaître les efforts qui s’appliquent à la vaste gamme de tâches que les utilisateurs d’équipes effectuent, des enseignants aux travailleurs de première ligne.

Les administrateurs peuvent contrôler les badges disponibles pour leur organisation à partir du centre d’administration Teams. Dans le volet de navigation de gauche, sélectionnez **applications teams > gérer les applications**. Ouvrez compliment dans le [catalogue d’applications du client](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog)et accédez à **paramètres**.

## <a name="use-built-in-badge-sets"></a>Utiliser les jeux de badges intégrés

Les ensembles prédéfinis sont des ensembles de badges conçus par Microsoft pour l’application compliments. Ces jeux ne peuvent pas être modifiés par les administrateurs. L’ensemble de badges par défaut est déjà activé et disponible dans l’application compliments. Pour modifier la disponibilité du jeu par défaut ou de tous les jeux de badges, activez ou désactivez le bouton bascule correspondant. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Badges par défaut

L’ensemble de badges par défaut est conçu pour aider les utilisateurs de équipes à reconnaître leurs homologues pour aller au-delà de leur œuvre.

![Aperçu du jeu de badges par défaut](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Badges de formations sociales et émotionnelles pour l’éducation

Les enseignants peuvent reconnaître les étudiants individuels pour les réalisations et les comportements de connaissances sociales et émotionnelles (SEL) avec des badges illustrant ces concepts.

![Préversion des badges de formations sociales et émotionnelles pour l’éducation](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Créer vos propres badges

Activez le bouton bascule **badges personnalisés** et sélectionnez **créer un badge personnalisé**. À partir de là, vous pouvez concevoir un badge personnalisé dans le volet latéral. Vous pouvez créer jusqu’à 25 badges personnalisés. 

1. Entrez un nom de badge. Il s’agit du nom qui s’affichera sur le badge lorsque les utilisateurs envoient les compliments.

2. Définissez vos couleurs de badge. Pour définir les couleurs du texte et de l’arrière-plan de votre badge, vous devez entrer les couleurs sous forme de valeurs hexadécimales (hex).

   > [!TIP]
   > Si vous débutez avec les valeurs hexadécimales, cet article inclut une [brève présentation](#hex-colors-intro) pour vous montrer comment les utiliser.

3. Télécharger une image de badge. Le type de fichier accepté est. PNG. La taille du fichier image doit être inférieure à 40 Ko et comporter au maximum 216 X 216 pixels.
![Badge avec champs d’arrière-plan, de texte et d’image libellés](media/praise-app-badge-fields.png)

4. Localisez votre nom de badge : sous **noms de badges localisés**, sélectionnez **Ajouter**. Sélectionnez le paramètre régional souhaité dans la liste déroulante. Entrez ensuite le nom du badge dans la langue désignée.

5. Exclure votre badge des paramètres régionaux spécifiques : sous **exclure le badge de ces paramètres régionaux**, sélectionnez **Ajouter**. Dans la liste déroulante, sélectionnez les paramètres régionaux que vous voulez exclure.

6. Sélectionnez **appliquer**. Votre nouveau badge s’affichera désormais dans la table badges personnalisés.

> [!NOTE]
> Si les étapes 4 et 5 sont ignorées, le badge sera dans la langue par défaut de tous les paramètres régionaux.
>
> Lorsque vous avez terminé d’apporter des modifications à votre sélection de badge, veillez à sélectionner l’option **soumission**. Quelques heures peuvent s’écouler avant que ces modifications soient disponibles pour votre organisation.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Spécifier des couleurs à l’aide de valeurs hexadécimales

Les valeurs de couleur hexadécimales sont des chaînes de six chiffres hexadécimaux qui représentent l’intensité du rouge (RR), du vert (GG) et du bleu (BB) dans une couleur spécifique sur une échelle de 00 à FF. Lorsque vous placez les valeurs des trois couleurs conjointement, vous obtenez une valeur hex : #RRGGBB

Par exemple, la valeur Hex pour le rouge Color est #FF0000, car la valeur rouge est définie sur la valeur la plus élevée possible, FF et vert et bleu sont chaque jeu à la valeur la plus basse possible, 00.

Pour explorer les différentes couleurs et leurs valeurs hexadécimales, consultez le [Sélecteur de couleurs Bing](https://www.bing.com/search?q=color+picker).

Vous trouverez ci-dessous une liste de couleurs d’exemple pour commencer :

|Couleur  |Valeur hex|
|-------|---------|
|![couleur hexadécimale #FF6666](media/hexColor1.png)|  #FF6666   |
|![couleur hexadécimale #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![couleur hexadécimale #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![couleur hexadécimale #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![couleur hexadécimale #800080](media/hexColor5.png)|  #800080   |
|![couleur hexadécimale #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Recommandations en matière de création de badges personnalisés

**Envoyez tous vos badges en une fois.** Dans la mesure où le traitement des nouveaux badges peut prendre un certain temps, il est préférable d’ajouter tous les badges personnalisés à la table avant de les soumettre.

**Lorsque vous sélectionnez des couleurs, n’oubliez pas d’accessibilité.** Davantage de couleurs sont bien meilleures que d’autres.  Définissez le contraste entre les couleurs de texte et d’arrière-plan pour faciliter la lecture du nom de badge. Par exemple, si vous avez choisi une couleur d’arrière-plan foncée, choisissez une couleur de texte claire.

**Lorsque vous sélectionnez une image, tenez compte des dimensions du badge.** Pour une qualité optimale, nous vous recommandons de télécharger un fichier image de 216 x 216 pixels (qui est le nombre maximal de dimensions). Évitez d’étirer ou de déformer l’image pour l’ajuster à ces dimensions.

**Si votre image de badge n’est pas rectangulaire, rendez l’image transparente.** Vous devez le faire avant de télécharger le fichier image pour encomplimenter.

![Gauche : badge avec image non transparente, droite : badge avec image transparente](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Ressources du jeu de badges

Les jeux de badges intégrés ne peuvent pas être modifiés, de sorte que lorsqu’un jeu intégré est activé, tous les badges du jeu sont ajoutés à l’application compliments. Si vous souhaitez ajouter des badges spécifiques à partir d’un ensemble intégré et en ignorer d’autres, recréez les badges que vous voulez utiliser comme badges personnalisés. Vous pouvez télécharger l’image de badge et rechercher les couleurs de texte et d’arrière-plan des badges à partir d’ensembles prédéfinis dans les tableaux ci-dessous.

### <a name="default-badges-assets"></a>Composants de badge par défaut

</br>

|Nom de badge     |Fichier image  |Couleur du texte | Couleur d’arrière-plan |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Extraordinaire        |[PNG impressionnant](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Éco          |[Autocar PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Découragé        |[PNG recommandée](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Créatrice       |[PNG Creative](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Incluant      |[PNG inclusive](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Type cœur     |[Type coeur PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Pointe     |[PNG au leadership](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Optimisation       |[PNG optimisé](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Solveur de problème |[Erreur « PNG » dans PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Lecteur d’équipe    |[PNG du lecteur d’équipe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Merci      |[Remerciements PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Badges de formations sociales et émotionnelles pour les ressources pour l’éducation

</br>

|Nom de badge        |Fichier image  |Couleur du texte | Couleur d’arrière-plan |
|------------------|------------|---------- |--------|
|Communication     |[PNG de communication](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Réflexion critique |[PNG de réflexion critique](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosité         |[PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Path           |[PNG pathn](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Poursuite de l’objectif      |[PNG de la poursuite de l’objectif](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivation        |[PNG de motivation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistance       |[PNG de persistance](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Domaine           |[Respecter le PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Centres    |[PNG de responsabilité](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Auto-sensibilisation    |[PNG à la prise en charge automatique](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Auto-gestion   |[PNG d’auto-gestion](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Attention    |[PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
